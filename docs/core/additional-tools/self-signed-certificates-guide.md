---
title: 자체 서명된 인증서 생성 개요
description: .NET Core 및 ASP.NET Core 프로젝트에 대한 기능과 자체 서명된 인증서 사용을 위한 기타 옵션을 추가하는 Microsoft dotnet dev-certs 도구에 대한 개요입니다.
author: angee
ms.date: 11/19/2020
ms.openlocfilehash: d1675abb7d584b72d981f9db739e02269abe662c
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189143"
---
# <a name="generate-self-signed-certificates-with-the-net-cli"></a>.NET CLI를 사용하여 자체 서명된 인증서 생성

자체 서명된 인증서를 사용하면 개발 및 테스트 시나리오에 따라 다양한 방법으로 인증서를 만들어 사용할 수 있습니다.  이 가이드에서는 `dotnet dev-certs`로 자체 서명된 인증서를 사용하는 방법에 대해 설명하고 `PowerShell` 및 `OpenSSL`과 같은 기타 옵션에 대해 설명합니다.

그런 다음 컨테이너에서 호스트되는 [ASP.NET Core 앱](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md)과 같은 예제를 사용하여 인증서가 로드되는지 확인할 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

샘플에서는 .NET Core 3.1 또는 .NET 5를 활용할 수 있습니다.

`dotnet dev-certs`의 경우 적절한 버전의 .NET이 설치되어 있어야 합니다.

* [Windows에 .NET 설치](../install/windows.md)
* [Linux에 .NET 설치](../install/linux.md)
* [macOS에 .NET 설치](../install/macos.md)

이 샘플에서는 [Docker 17.06](https://docs.docker.com/release-notes/docker-ce) 이상의 [Docker 클라이언트](https://www.docker.com/products/docker)가 필요합니다.

## <a name="prepare-sample-app"></a>샘플 앱 준비

테스트에 사용하려는 런타임에 따라 [.NET Core 3.1](#net-core-31-sample-app)이나 [.NET 5](#net-5-sample-app)와 같은 샘플 앱을 준비해야 합니다.

이 가이드에서는 [샘플 앱](https://hub.docker.com/_/microsoft-dotnet-samples)을 사용하고 필요에 따라 변경합니다.

### <a name="net-core-31-sample-app"></a>.NET Core 3.1 샘플 앱

샘플 앱 가져오기

```console
git clone https://github.com/dotnet/dotnet-docker/
```

로컬에서 리포지토리로 이동하여 편집기에서 작업 영역을 엽니다.

> [!NOTE]
> dotnet publish 매개 변수를 사용하여 배포를 ‘트리밍’하려면 SSL 인증서를 지원하기 위한 적절한 종속성이 포함되어 있는지 확인해야 합니다.
[dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj)를 업데이트하여 적절한 어셈블리가 컨테이너에 포함되도록 합니다. 참조용으로 자체 포함 배포에 트리밍을 사용할 때 [ssl 인증서를 지원](../deploying/trim-self-contained.md#support-for-ssl-certificates)하도록 .csproj 파일을 업데이트하는 방법을 확인하세요.

`aspnetapp.csproj`에 적절한 대상 프레임워크가 포함되어 있는지 확인합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>.netcoreapp3.1</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

런타임이 .NET Core 3.1을 가리키도록 Dockerfile을 수정합니다.

```Dockerfile
# https://hub.docker.com/_/microsoft-dotnet-core
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /source

# copy csproj and restore as distinct layers
COPY *.sln .
COPY aspnetapp/*.csproj ./aspnetapp/
RUN dotnet restore

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app --no-restore

# final stage/image
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["dotnet", "aspnetapp.dll"]
```

샘플 앱을 가리키고 있는지 확인합니다.

```console
cd .\dotnet-docker\samples\aspnetapp
```

로컬에서 테스트용으로 컨테이너를 빌드합니다.

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

### <a name="net-5-sample-app"></a>.NET 5 샘플 앱

이 가이드에서는 .NET 5에 대한 [샘플 aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples)을 확인해야 합니다.

샘플 앱 [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile)에서 .NET 5를 사용하고 있는지 확인합니다.

호스트 OS에 따라 ASP.NET 런타임을 업데이트해야 할 수 있습니다. 예를 들어 Dockerfile에서 `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime`을 `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime`으로 변경하면 적절한 Windows 런타임을 대상으로 지정하는 데 도움이 됩니다.

예를 들어 Windows에서 인증서를 테스트하는 데 도움이 됩니다.

```Dockerfile
# https://hub.docker.com/_/microsoft-dotnet
FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /source

# copy csproj and restore as distinct layers
COPY *.sln .
COPY aspnetapp/*.csproj ./aspnetapp/
RUN dotnet restore -r win-x64

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app -r win-x64 --self-contained false --no-restore

# final stage/image
# Uses the 2009 release; 2004, 1909, and 1809 are other choices
FROM mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["aspnetapp"]

```

Linux에서 인증서를 테스트하는 경우에는 기존 Dockerfile을 사용할 수 있습니다.

`aspnetapp.csproj`에 적절한 대상 프레임워크가 포함되어 있는지 확인합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

> [!NOTE]
> `dotnet publish` 매개 변수를 사용하여 배포를 ‘트리밍’하려면 SSL 인증서를 지원하기 위한 적절한 종속성이 포함되어 있는지 확인합니다.
[dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj)를 업데이트하여 적절한 어셈블리가 컨테이너에 포함되도록 합니다. 참조용으로 자체 포함 배포에 트리밍을 사용할 때 [ssl 인증서를 지원](../deploying/trim-self-contained.md#support-for-ssl-certificates)하도록 .csproj 파일을 업데이트하는 방법을 확인하세요.

샘플 앱을 가리키고 있는지 확인합니다.

```console
cd .\dotnet-docker\samples\aspnetapp
```

로컬에서 테스트용으로 컨테이너를 빌드합니다.

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

## <a name="create-a-self-signed-certificate"></a>자체 서명된 인증서 만들기

다음과 같은 방법으로 자체 서명된 인증서를 만들 수 있습니다.

- [dotnet dev-certs 사용](#with-dotnet-dev-certs)
- [PowerShell 사용](#with-powershell)
- [OpenSSL 사용](#with-openssl)

### <a name="with-dotnet-dev-certs"></a>dotnet dev-certs 사용

`dotnet dev-certs`를 사용하여 자체 서명된 인증서 작업을 수행할 수 있습니다. 이 예제에서는 PowerShell 콘솔을 사용합니다.

```console
dotnet dev-certs https -ep $env:USERPROFILE\.aspnet\https\aspnetapp.pfx -p crypticpassword
dotnet dev-certs https --trust
```

> [!NOTE]
> 인증서 이름(이 경우 *aspnetapp*.pfx)은 프로젝트 어셈블리 이름과 일치해야 합니다. `crypticpassword`는 사용자가 직접 선택한 암호 대신 사용됩니다. 콘솔에서 “A valid HTTPS certificate is already present.”(유효한 HTTPS 인증서가 이미 있습니다.)를 반환하는 경우 신뢰할 수 있는 인증서가 이미 저장소에 있습니다. 이 인증서는 MMC 콘솔을 사용하여 내보낼 수 있습니다.

인증서에 대한 애플리케이션 비밀을 구성합니다.

```console
dotnet user-secrets -p aspnetapp\aspnetapp.csproj set "Kestrel:Certificates:Development:Password" "crypticpassword"
```

> [!NOTE]
> 참고: 암호는 인증서에 사용된 암호와 일치해야 합니다.

HTTPS용으로 구성된 ASP.NET Core를 사용하여 컨테이너 이미지를 실행합니다.

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -v $env:APPDATA\microsoft\UserSecrets\:C:\Users\ContainerUser\AppData\Roaming\microsoft\UserSecrets -v $env:USERPROFILE\.aspnet\https:C:\Users\ContainerUser\AppData\Roaming\ASP.NET\Https mcr.microsoft.com/dotnet/samples:aspnetapp
```

애플리케이션이 시작되면 웹 브라우저에서 `https://localhost:8001`로 이동합니다.

#### <a name="clean-up"></a>정리

비밀 및 인증서가 사용되지 않는 경우에는 정리해야 합니다.

```console
dotnet user-secrets remove "Kestrel:Certificates:Development:Password" -p aspnetapp\aspnetapp.csproj
dotnet dev-certs https --clean
```

### <a name="with-powershell"></a>PowerShell 사용

PowerShell을 사용하여 자체 서명된 인증서를 생성할 수 있습니다. [PKI 클라이언트](/powershell/module/pkiclient/new-selfsignedcertificate?preserve-view=true&view=win10-ps)를 사용하여 자체 서명된 인증서를 생성할 수 있습니다.

```powershell
$cert = New-SelfSignedCertificate -DnsName @("contoso.com", "www.contoso.com") -CertStoreLocation "cert:\LocalMachine\My"
```

인증서가 생성되지만 테스트 목적으로 브라우저에서 테스트하려면 인증서 저장소에 배치해야 합니다.

```powershell
$certKeyPath = "c:\certs\contoso.com.pfx"
$password = ConvertTo-SecureString 'password' -AsPlainText -Force
$cert | Export-PfxCertificate -FilePath $certKeyPath -Password $password
$rootCert = $(Import-PfxCertificate -FilePath $certKeyPath -CertStoreLocation 'Cert:\LocalMachine\Root' -Password $password)
```

이제 [MMC 스냅인](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)에서 인증서를 볼 수 있어야 합니다.

WSL(Linux용 Windows 하위 시스템)에서 샘플 컨테이너를 실행할 수 있습니다.

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> 볼륨 탑재를 사용하면 호스트에 따라 파일 경로를 다르게 처리할 수 있습니다.  예를 들어 WSL에서는 */c/certs* 를 */mnt/c/certs* 로 바꿀 수 있습니다.

이전에 Windows용으로 빌드된 컨테이너를 사용하는 경우 실행 명령은 다음과 같습니다.

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

애플리케이션이 실행되면 브라우저에서 contoso.com:8001로 이동합니다.

`contoso.com`이 적절한 IP 주소(예: 127.0.0.1)에서 응답하도록 하려면 호스트 항목을 업데이트해야 합니다. 인증서가 인식되지 않으면 컨테이너와 함께 로드되는 인증서도 호스트에서 신뢰되는지와 `contoso.com`에 대한 적절한 SAN/DNS 항목이 있는지 확인합니다.

#### <a name="clean-up"></a>정리

```powershell
$cert | Remove-Item
Get-ChildItem $certFilePath | Remove-Item
$rootCert | Remove-item
```

### <a name="with-openssl"></a>OpenSSL 사용

[OpenSSL](https://www.openssl.org/)을 사용하여 자체 서명된 인증서를 만들 수 있습니다. 이 예제에서는 `OpenSSL`과 함께 WSL/Ubuntu 및 bash 셸을 사용합니다.

그러면 .crt 및 .key가 생성됩니다.

```bash
PARENT="contoso.com"
openssl req \
-x509 \
-newkey rsa:4096 \
-sha256 \
-days 365 \
-nodes \
-keyout $PARENT.key \
-out $PARENT.crt \
-subj "/CN=${PARENT}" \
-extensions v3_ca \
-extensions v3_req \
-config <( \
  echo '[req]'; \
  echo 'default_bits= 4096'; \
  echo 'distinguished_name=req'; \
  echo 'x509_extension = v3_ca'; \
  echo 'req_extensions = v3_req'; \
  echo '[v3_req]'; \
  echo 'basicConstraints = CA:FALSE'; \
  echo 'keyUsage = nonRepudiation, digitalSignature, keyEncipherment'; \
  echo 'subjectAltName = @alt_names'; \
  echo '[ alt_names ]'; \
  echo "DNS.1 = www.${PARENT}"; \
  echo "DNS.2 = ${PARENT}"; \
  echo '[ v3_ca ]'; \
  echo 'subjectKeyIdentifier=hash'; \
  echo 'authorityKeyIdentifier=keyid:always,issuer'; \
  echo 'basicConstraints = critical, CA:TRUE, pathlen:0'; \
  echo 'keyUsage = critical, cRLSign, keyCertSign'; \
  echo 'extendedKeyUsage = serverAuth, clientAuth')

openssl x509 -noout -text -in $PARENT.crt
```

.pfx를 가져오려면 다음 명령을 사용합니다.

```bash
openssl pkcs12 -export -out $PARENT.pfx -inkey $PARENT.key -in $PARENT.crt
```

> [!NOTE]
> .aspnetcore 3.1 예제에서는 `.pfx`와 암호를 사용합니다. `.net 5` 런타임부터 Kestrel은 `.crt` 및 PEM 인코딩 `.key` 파일을 사용할 수도 있습니다.

호스트 OS에 따라 인증서를 신뢰할 수 있어야 합니다. Linux 호스트에서 인증서 ‘신뢰’는 다르며 배포판에 종속됩니다.

이 가이드에서는 다음과 같이 PowerShell을 사용하는 Windows의 예제를 사용합니다.

```powershell
Import-Certificate -FilePath $certFilePath -CertStoreLocation 'Cert:\LocalMachine\Root'
```

.NET Core 3.1의 경우 WSL에서 다음 명령을 실행합니다.

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/path/to/certs/:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

.NET 5부터 Kestrel은 `.crt` 및 PEM 인코딩 `.key` 파일을 사용할 수 있습니다. .NET 5에서는 다음 명령을 사용하여 샘플을 실행할 수 있습니다.

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=/https/contoso.com.key -v /c/path/to/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> WSL에서 볼륨 탑재 경로는 구성에 따라 변경될 수 있습니다.

Windows의 .NET Core 3.1인 경우 `Powershell`에서 다음 명령을 실행합니다.

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

Windows의 .NET 5인 경우 PowerShell에서 다음 명령을 실행합니다.

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=c:\https\contoso.com.key -v c:\certs:C:\https aspnetapp:my-sample
```

애플리케이션이 실행되면 브라우저에서 contoso.com:8001로 이동합니다.

`contoso.com`이 적절한 IP 주소(예: 127.0.0.1)에서 응답하도록 하려면 호스트 항목을 업데이트해야 합니다. 인증서가 인식되지 않으면 컨테이너와 함께 로드되는 인증서도 호스트에서 신뢰되는지와 `contoso.com`에 대한 적절한 SAN/DNS 항목이 있는지 확인합니다.

#### <a name="clean-up"></a>정리

테스트가 완료되면 자체 서명된 인증서를 정리해야 합니다.

```powershell
Get-ChildItem $certFilePath | Remove-Item
```
