---
title: 자체 서명된 인증서 생성 개요
description: .NET Core 및 ASP.NET Core 프로젝트에 대한 기능과 자체 서명된 인증서 사용을 위한 기타 옵션을 추가하는 Microsoft dotnet dev-certs 도구에 대한 개요입니다.
author: angee
ms.date: 11/19/2020
ms.openlocfilehash: b5bf4b719495c2d6ec248e8592367ac452be91c1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032179"
---
# <a name="generate-self-signed-certificates-with-the-net-cli"></a><span data-ttu-id="c30af-103">.NET CLI를 사용하여 자체 서명된 인증서 생성</span><span class="sxs-lookup"><span data-stu-id="c30af-103">Generate self-signed certificates with the .NET CLI</span></span>

<span data-ttu-id="c30af-104">자체 서명된 인증서를 사용하면 개발 및 테스트 시나리오에 따라 다양한 방법으로 인증서를 만들어 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-104">When using self-signed certificates, there are different ways to create and use them for development and testing scenarios.</span></span>  <span data-ttu-id="c30af-105">이 가이드에서는 `dotnet dev-certs`로 자체 서명된 인증서를 사용하는 방법에 대해 설명하고 `PowerShell` 및 `OpenSSL`과 같은 기타 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-105">In this guide, you'll cover using self-signed certificates with `dotnet dev-certs`, and other options like `PowerShell` and `OpenSSL`.</span></span>

<span data-ttu-id="c30af-106">그런 다음 컨테이너에서 호스트되는 [ASP.NET Core 앱](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md)과 같은 예제를 사용하여 인증서가 로드되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-106">You can then validate that the certificate will load using an example such as an [ASP.NET Core app](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md) hosted in a container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c30af-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c30af-107">Prerequisites</span></span>

<span data-ttu-id="c30af-108">샘플에서는 .NET Core 3.1 또는 .NET 5를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-108">In the sample, you can utilize either .NET Core 3.1 or .NET 5.</span></span>

<span data-ttu-id="c30af-109">`dotnet dev-certs`의 경우 적절한 버전의 .NET이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-109">For `dotnet dev-certs`, be sure to have the appropriate version of .NET installed:</span></span>

* [<span data-ttu-id="c30af-110">Windows에 .NET 설치</span><span class="sxs-lookup"><span data-stu-id="c30af-110">Install .NET on Windows</span></span>](../install/windows.md)
* [<span data-ttu-id="c30af-111">Linux에 .NET 설치</span><span class="sxs-lookup"><span data-stu-id="c30af-111">Install .NET on Linux</span></span>](../install/linux.md)
* [<span data-ttu-id="c30af-112">macOS에 .NET 설치</span><span class="sxs-lookup"><span data-stu-id="c30af-112">Install .NET on macOS</span></span>](../install/macos.md)

<span data-ttu-id="c30af-113">이 샘플에서는 [Docker 17.06](https://docs.docker.com/release-notes/docker-ce) 이상의 [Docker 클라이언트](https://www.docker.com/products/docker)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-113">This sample requires [Docker 17.06](https://docs.docker.com/release-notes/docker-ce) or later of the [Docker client](https://www.docker.com/products/docker).</span></span>

## <a name="prepare-sample-app"></a><span data-ttu-id="c30af-114">샘플 앱 준비</span><span class="sxs-lookup"><span data-stu-id="c30af-114">Prepare sample app</span></span>

<span data-ttu-id="c30af-115">테스트에 사용하려는 런타임에 따라 [.NET Core 3.1](#net-core-31-sample-app)이나 [.NET 5](#net-5-sample-app)와 같은 샘플 앱을 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-115">You'll need to prepare the sample app depending on which runtime you'd like to use for testing, either [.NET Core 3.1](#net-core-31-sample-app) or [.NET 5](#net-5-sample-app).</span></span>

<span data-ttu-id="c30af-116">이 가이드에서는 [샘플 앱](https://hub.docker.com/_/microsoft-dotnet-samples)을 사용하고 필요에 따라 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-116">For this guide, you'll use a [sample app](https://hub.docker.com/_/microsoft-dotnet-samples) and make changes where appropriate.</span></span>

### <a name="net-core-31-sample-app"></a><span data-ttu-id="c30af-117">.NET Core 3.1 샘플 앱</span><span class="sxs-lookup"><span data-stu-id="c30af-117">.NET Core 3.1 sample app</span></span>

<span data-ttu-id="c30af-118">샘플 앱 가져오기</span><span class="sxs-lookup"><span data-stu-id="c30af-118">Get the sample app.</span></span>

```console
git clone https://github.com/dotnet/dotnet-docker/
```

<span data-ttu-id="c30af-119">로컬에서 리포지토리로 이동하여 편집기에서 작업 영역을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-119">Navigate to the repository locally and open up the workspace in an editor.</span></span>

> [!NOTE]
> <span data-ttu-id="c30af-120">dotnet publish 매개 변수를 사용하여 배포를 ‘트리밍’하려면 SSL 인증서를 지원하기 위한 적절한 종속성이 포함되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-120">If you're looking to use dotnet publish parameters to *trim* the deployment, you should make sure that the appropriate dependencies are included for supporting SSL certificates.</span></span>
<span data-ttu-id="c30af-121">[dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj)를 업데이트하여 적절한 어셈블리가 컨테이너에 포함되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-121">Update the [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) to ensure that the appropriate assemblies are included in the container.</span></span> <span data-ttu-id="c30af-122">참조용으로 자체 포함 배포에 트리밍을 사용할 때 [ssl 인증서를 지원](../deploying/trim-self-contained.md#support-for-ssl-certificates)하도록 .csproj 파일을 업데이트하는 방법을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c30af-122">For reference, check how to update the .csproj file to [support ssl certificates](../deploying/trim-self-contained.md#support-for-ssl-certificates) when using trimming for self-contained deployments.</span></span>

<span data-ttu-id="c30af-123">`aspnetapp.csproj`에 적절한 대상 프레임워크가 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-123">Make sure the `aspnetapp.csproj` includes the appropriate target framework:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>.netcoreapp3.1</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

<span data-ttu-id="c30af-124">런타임이 .NET Core 3.1을 가리키도록 Dockerfile을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-124">Modify the Dockerfile to make sure the runtime points to .NET Core 3.1:</span></span>

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

<span data-ttu-id="c30af-125">샘플 앱을 가리키고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-125">Make sure you're pointing to the sample app.</span></span>

```console
cd .\dotnet-docker\samples\aspnetapp
```

<span data-ttu-id="c30af-126">로컬에서 테스트용으로 컨테이너를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-126">Build the container for testing locally.</span></span>

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

### <a name="net-5-sample-app"></a><span data-ttu-id="c30af-127">.NET 5 샘플 앱</span><span class="sxs-lookup"><span data-stu-id="c30af-127">.NET 5 sample app</span></span>

<span data-ttu-id="c30af-128">이 가이드에서는 .NET 5에 대한 [샘플 aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples)을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-128">For this guide, the [sample aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples) should be checked for .NET 5.</span></span>

<span data-ttu-id="c30af-129">샘플 앱 [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile)에서 .NET 5를 사용하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-129">Check sample app [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) is using .NET 5.</span></span>

<span data-ttu-id="c30af-130">호스트 OS에 따라 ASP.NET 런타임을 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-130">Depending on the host OS, the ASP.NET runtime may need to be updated.</span></span> <span data-ttu-id="c30af-131">예를 들어 Dockerfile에서 `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime`을 `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime`으로 변경하면 적절한 Windows 런타임을 대상으로 지정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-131">For example, changing from `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` to `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` in the Dockerfile will help with targeting the appropriate Windows runtime.</span></span>

<span data-ttu-id="c30af-132">예를 들어 Windows에서 인증서를 테스트하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-132">For example, this will help with testing the certificates on Windows:</span></span>

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

<span data-ttu-id="c30af-133">Linux에서 인증서를 테스트하는 경우에는 기존 Dockerfile을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-133">If we're testing the certificates on Linux, you can use the existing Dockerfile.</span></span>

<span data-ttu-id="c30af-134">`aspnetapp.csproj`에 적절한 대상 프레임워크가 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-134">Make sure the `aspnetapp.csproj` includes the appropriate target framework:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

> [!NOTE]
> <span data-ttu-id="c30af-135">`dotnet publish` 매개 변수를 사용하여 배포를 ‘트리밍’하려면 SSL 인증서를 지원하기 위한 적절한 종속성이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-135">If you want to use `dotnet publish` parameters to *trim* the deployment, make sure that the appropriate dependencies are included for supporting SSL certificates.</span></span>
<span data-ttu-id="c30af-136">[dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj)를 업데이트하여 적절한 어셈블리가 컨테이너에 포함되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-136">Update the [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) to ensure that the appropriate assemblies are included in the container.</span></span> <span data-ttu-id="c30af-137">참조용으로 자체 포함 배포에 트리밍을 사용할 때 [ssl 인증서를 지원](../deploying/trim-self-contained.md#support-for-ssl-certificates)하도록 .csproj 파일을 업데이트하는 방법을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c30af-137">For reference, check how to update the .csproj file to [support ssl certificates](../deploying/trim-self-contained.md#support-for-ssl-certificates) when using trimming for self-contained deployments.</span></span>

<span data-ttu-id="c30af-138">샘플 앱을 가리키고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-138">Make sure you're pointing to the sample app.</span></span>

```console
cd .\dotnet-docker\samples\aspnetapp
```

<span data-ttu-id="c30af-139">로컬에서 테스트용으로 컨테이너를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-139">Build the container for testing locally.</span></span>

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="c30af-140">자체 서명된 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="c30af-140">Create a self-signed certificate</span></span>

<span data-ttu-id="c30af-141">다음과 같은 방법으로 자체 서명된 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-141">You can create a self-signed certificate:</span></span>

- [<span data-ttu-id="c30af-142">dotnet dev-certs 사용</span><span class="sxs-lookup"><span data-stu-id="c30af-142">With dotnet dev-certs</span></span>](#with-dotnet-dev-certs)
- [<span data-ttu-id="c30af-143">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="c30af-143">With PowerShell</span></span>](#with-powershell)
- [<span data-ttu-id="c30af-144">OpenSSL 사용</span><span class="sxs-lookup"><span data-stu-id="c30af-144">With OpenSSL</span></span>](#with-openssl)

### <a name="with-dotnet-dev-certs"></a><span data-ttu-id="c30af-145">dotnet dev-certs 사용</span><span class="sxs-lookup"><span data-stu-id="c30af-145">With dotnet dev-certs</span></span>

<span data-ttu-id="c30af-146">`dotnet dev-certs`를 사용하여 자체 서명된 인증서 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-146">You can use `dotnet dev-certs` to work with self-signed certificates.</span></span> <span data-ttu-id="c30af-147">이 예제에서는 PowerShell 콘솔을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-147">This example uses a PowerShell console.</span></span>

```console
dotnet dev-certs https -ep $env:USERPROFILE\.aspnet\https\aspnetapp.pfx -p crypticpassword
dotnet dev-certs https --trust
```

> [!NOTE]
> <span data-ttu-id="c30af-148">인증서 이름(이 경우 *aspnetapp*.pfx)은 프로젝트 어셈블리 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-148">The certificate name, in this case *aspnetapp*.pfx must match the project assembly name.</span></span> <span data-ttu-id="c30af-149">`crypticpassword`는 사용자가 직접 선택한 암호 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-149">`crypticpassword` is used as a stand-in for a password of your own choosing.</span></span> <span data-ttu-id="c30af-150">콘솔에서 “A valid HTTPS certificate is already present.”(유효한 HTTPS 인증서가 이미 있습니다.)를 반환하는 경우 신뢰할 수 있는 인증서가 이미 저장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-150">If console returns "A valid HTTPS certificate is already present.", a trusted certificate already exists in your store.</span></span> <span data-ttu-id="c30af-151">이 인증서는 MMC 콘솔을 사용하여 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-151">It can be exported using MMC Console.</span></span>

<span data-ttu-id="c30af-152">인증서에 대한 애플리케이션 비밀을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-152">Configure application secrets, for the certificate:</span></span>

```console
dotnet user-secrets -p aspnetapp\aspnetapp.csproj set "Kestrel:Certificates:Development:Password" "crypticpassword"
```

> [!NOTE]
> <span data-ttu-id="c30af-153">참고: 암호는 인증서에 사용된 암호와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-153">Note: The password must match the password used for the certificate.</span></span>

<span data-ttu-id="c30af-154">HTTPS용으로 구성된 ASP.NET Core를 사용하여 컨테이너 이미지를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-154">Run the container image with ASP.NET Core configured for HTTPS:</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -v $env:APPDATA\microsoft\UserSecrets\:C:\Users\ContainerUser\AppData\Roaming\microsoft\UserSecrets -v $env:USERPROFILE\.aspnet\https:C:\Users\ContainerUser\AppData\Roaming\ASP.NET\Https mcr.microsoft.com/dotnet/samples:aspnetapp
```

<span data-ttu-id="c30af-155">애플리케이션이 시작되면 웹 브라우저에서 `https://localhost:8001`로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-155">Once the application starts, navigate to `https://localhost:8001` in your web browser.</span></span>

#### <a name="clean-up"></a><span data-ttu-id="c30af-156">정리</span><span class="sxs-lookup"><span data-stu-id="c30af-156">Clean up</span></span>

<span data-ttu-id="c30af-157">비밀 및 인증서가 사용되지 않는 경우에는 정리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-157">If the secrets and certificates are not in use, be sure to clean them up.</span></span>

```console
dotnet user-secrets remove "Kestrel:Certificates:Development:Password" -p aspnetapp\aspnetapp.csproj
dotnet dev-certs https --clean
```

### <a name="with-powershell"></a><span data-ttu-id="c30af-158">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="c30af-158">With PowerShell</span></span>

<span data-ttu-id="c30af-159">PowerShell을 사용하여 자체 서명된 인증서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-159">You can use PowerShell to generate self-signed certificates.</span></span> <span data-ttu-id="c30af-160">[PKI 클라이언트](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true)를 사용하여 자체 서명된 인증서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-160">The [PKI Client](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true) can be used to generate a self-signed certificate.</span></span>

```powershell
$cert = New-SelfSignedCertificate -DnsName @("contoso.com", "www.contoso.com") -CertStoreLocation "cert:\LocalMachine\My"
```

<span data-ttu-id="c30af-161">인증서가 생성되지만 테스트 목적으로 브라우저에서 테스트하려면 인증서 저장소에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-161">The certificate will be generated, but for the purposes of testing, should be placed in a cert store for testing in a browser.</span></span>

```powershell
$certKeyPath = "c:\certs\contoso.com.pfx"
$password = ConvertTo-SecureString 'password' -AsPlainText -Force
$cert | Export-PfxCertificate -FilePath $certKeyPath -Password $password
$rootCert = $(Import-PfxCertificate -FilePath $certKeyPath -CertStoreLocation 'Cert:\LocalMachine\Root' -Password $password)
```

<span data-ttu-id="c30af-162">이제 [MMC 스냅인](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)에서 인증서를 볼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-162">At this point, the certificates should be viewable from an [MMC snap-in](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

<span data-ttu-id="c30af-163">WSL(Linux용 Windows 하위 시스템)에서 샘플 컨테이너를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-163">You can run the sample container in Windows Subsystem for Linux (WSL):</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> <span data-ttu-id="c30af-164">볼륨 탑재를 사용하면 호스트에 따라 파일 경로를 다르게 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-164">Note that with the volume mount the file path could be handled differently based on host.</span></span>  <span data-ttu-id="c30af-165">예를 들어 WSL에서는 */c/certs* 를 */mnt/c/certs* 로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-165">For example, in WSL we may replace */c/certs* with */mnt/c/certs*.</span></span>

<span data-ttu-id="c30af-166">이전에 Windows용으로 빌드된 컨테이너를 사용하는 경우 실행 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-166">If you're using the container built earlier for Windows, the run command would look like the following:</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="c30af-167">애플리케이션이 실행되면 브라우저에서 contoso.com:8001로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-167">Once the application is up, navigate to contoso.com:8001 in a browser.</span></span>

<span data-ttu-id="c30af-168">`contoso.com`이 적절한 IP 주소(예: 127.0.0.1)에서 응답하도록 하려면 호스트 항목을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-168">Be sure that the host entries are updated for `contoso.com` to answer on  the appropriate ip address (for example 127.0.0.1).</span></span> <span data-ttu-id="c30af-169">인증서가 인식되지 않으면 컨테이너와 함께 로드되는 인증서도 호스트에서 신뢰되는지와 `contoso.com`에 대한 적절한 SAN/DNS 항목이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-169">If the certificate isn't recognized, make sure that the certificate that is loaded with the container is also trusted on the host, and that there's appropriate SAN / DNS entries for `contoso.com`.</span></span>

#### <a name="clean-up"></a><span data-ttu-id="c30af-170">정리</span><span class="sxs-lookup"><span data-stu-id="c30af-170">Clean up</span></span>

```powershell
$cert | Remove-Item
Get-ChildItem $certFilePath | Remove-Item
$rootCert | Remove-item
```

### <a name="with-openssl"></a><span data-ttu-id="c30af-171">OpenSSL 사용</span><span class="sxs-lookup"><span data-stu-id="c30af-171">With OpenSSL</span></span>

<span data-ttu-id="c30af-172">[OpenSSL](https://www.openssl.org/)을 사용하여 자체 서명된 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-172">You can use [OpenSSL](https://www.openssl.org/) to create self-signed certificates.</span></span> <span data-ttu-id="c30af-173">이 예제에서는 `OpenSSL`과 함께 WSL/Ubuntu 및 bash 셸을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-173">This example will use WSL / Ubuntu and a bash shell with `OpenSSL`.</span></span>

<span data-ttu-id="c30af-174">그러면 .crt 및 .key가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-174">This will generate a .crt and a .key.</span></span>

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

<span data-ttu-id="c30af-175">.pfx를 가져오려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-175">To get a .pfx, use the following command:</span></span>

```bash
openssl pkcs12 -export -out $PARENT.pfx -inkey $PARENT.key -in $PARENT.crt
```

> [!NOTE]
> <span data-ttu-id="c30af-176">.aspnetcore 3.1 예제에서는 `.pfx`와 암호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-176">The .aspnetcore 3.1 example will use `.pfx` and a password.</span></span> <span data-ttu-id="c30af-177">`.net 5` 런타임부터 Kestrel은 `.crt` 및 PEM 인코딩 `.key` 파일을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-177">Starting with the `.net 5` runtime, Kestrel can also take `.crt` and PEM-encoded `.key` files.</span></span>

<span data-ttu-id="c30af-178">호스트 OS에 따라 인증서를 신뢰할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-178">Depending on the host os, the certificate will need to be trusted.</span></span> <span data-ttu-id="c30af-179">Linux 호스트에서 인증서 ‘신뢰’는 다르며 배포판에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-179">On a Linux host, 'trusting' the certificate is different and distro dependent.</span></span>

<span data-ttu-id="c30af-180">이 가이드에서는 다음과 같이 PowerShell을 사용하는 Windows의 예제를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-180">For the purposes of this guide, here's an example in Windows using PowerShell:</span></span>

```powershell
Import-Certificate -FilePath $certFilePath -CertStoreLocation 'Cert:\LocalMachine\Root'
```

<span data-ttu-id="c30af-181">.NET Core 3.1의 경우 WSL에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-181">For .NET Core 3.1, run the following command in WSL:</span></span>

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/path/to/certs/:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

<span data-ttu-id="c30af-182">.NET 5부터 Kestrel은 `.crt` 및 PEM 인코딩 `.key` 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-182">Starting with .NET 5, Kestrel can take the `.crt` and PEM-encoded `.key` files.</span></span> <span data-ttu-id="c30af-183">.NET 5에서는 다음 명령을 사용하여 샘플을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-183">You can run the sample with the following command for .NET 5:</span></span>

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=/https/contoso.com.key -v /c/path/to/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> <span data-ttu-id="c30af-184">WSL에서 볼륨 탑재 경로는 구성에 따라 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-184">Note that in WSL, the volume mount path may change depending on the configuration.</span></span>

<span data-ttu-id="c30af-185">Windows의 .NET Core 3.1인 경우 `Powershell`에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-185">For .NET Core 3.1 in Windows, run the following command in `Powershell`:</span></span>

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="c30af-186">Windows의 .NET 5인 경우 PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-186">For .NET 5 in Windows, run the following command in PowerShell:</span></span>

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=c:\https\contoso.com.key -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="c30af-187">애플리케이션이 실행되면 브라우저에서 contoso.com:8001로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-187">Once the application is up, navigate to contoso.com:8001 in a browser.</span></span>

<span data-ttu-id="c30af-188">`contoso.com`이 적절한 IP 주소(예: 127.0.0.1)에서 응답하도록 하려면 호스트 항목을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-188">Be sure that the host entries are updated for `contoso.com` to answer on  the appropriate ip address (for example 127.0.0.1).</span></span> <span data-ttu-id="c30af-189">인증서가 인식되지 않으면 컨테이너와 함께 로드되는 인증서도 호스트에서 신뢰되는지와 `contoso.com`에 대한 적절한 SAN/DNS 항목이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-189">If the certificate isn't recognized, make sure that the certificate that is loaded with the container is also trusted on the host, and that there's appropriate SAN / DNS entries for `contoso.com`.</span></span>

#### <a name="clean-up"></a><span data-ttu-id="c30af-190">정리</span><span class="sxs-lookup"><span data-stu-id="c30af-190">Clean up</span></span>

<span data-ttu-id="c30af-191">테스트가 완료되면 자체 서명된 인증서를 정리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30af-191">Be sure to clean up the self-signed certificates once done testing.</span></span>

```powershell
Get-ChildItem $certFilePath | Remove-Item
```
