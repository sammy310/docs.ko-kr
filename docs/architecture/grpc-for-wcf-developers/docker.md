---
title: WCF 개발자를 위한 Docker gRPC
description: ASP.NET Core gRPC 응용 프로그램에 대 한 Docker 이미지 만들기
ms.date: 12/15/2020
ms.openlocfilehash: f662dbd67f00b828f3e1dfa47359a450dd1c5900
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938418"
---
# <a name="create-docker-images"></a>Docker 이미지 만들기

이 섹션에서는 ASP.NET Core gRPC 응용 프로그램에 대 한 Docker 이미지 만들기, Docker, Kubernetes 또는 기타 컨테이너 환경에서 실행할 수 있는 방법에 대해 설명 합니다. ASP.NET Core MVC 웹 앱 및 gRPC 서비스를 사용 하 여 사용 되는 샘플 응용 프로그램은 GitHub의 [dotnet-아키텍처/grpc-wcf-개발자](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) 리포지토리에서 사용할 수 있습니다.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>ASP.NET Core 응용 프로그램용 Microsoft 기본 이미지

Microsoft는 .NET Core 응용 프로그램 빌드 및 실행을 위한 다양 한 기본 이미지를 제공 합니다. ASP.NET Core 3.0 이미지를 만들려면 다음 두 가지 기본 이미지를 사용 합니다.

- 응용 프로그램을 빌드 및 게시 하기 위한 SDK 이미지입니다.
- 배포용 런타임 이미지입니다.

| 이미지 | 설명 |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/sdk](https://hub.docker.com/_/microsoft-dotnet-sdk/) | 로 응용 프로그램을 빌드하는 데 사용 `docker build` 됩니다. 프로덕션에서는 사용 하지 않습니다. |
| [mcr.microsoft.com/dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/) | 런타임 및 ASP.NET Core 종속성을 포함 합니다. 프로덕션의 경우. |

각 이미지에는 다른 Linux 배포판을 기반으로 하는 네 가지 변형이 있습니다 (태그로 구분).

| 이미지 태그 | Linux | 메모 |
| --------- | ----- | ----- |
| 5.0-buster, 5.0 | Debian 10 | OS 변형이 지정 되지 않은 경우 기본 이미지입니다. |
| 5.0-알파인 | 알파인 3.9 | 알파인 기본 이미지는 Debian 또는 Ubuntu 1 보다 훨씬 작습니다. |
| 5.0-disco | Ubuntu 19.04 | |
| 5.0-bionic | Ubuntu 18.04 | |

알파인 기본 이미지는 Debian 및 Ubuntu 이미지의 200 MB와 비교 하 여 약 100입니다. 일부 소프트웨어 패키지 또는 라이브러리는 알파인의 패키지 관리에서 사용 하지 못할 수 있습니다. 사용할 이미지를 잘 모르는 경우 기본 Debian를 선택 해야 합니다.

> [!IMPORTANT]
> 빌드 및 런타임에 동일한 유형의 Linux를 사용 해야 합니다. 하나의 변형에 빌드되고 게시 된 응용 프로그램은 다른 변형에서 작동 하지 않을 수 있습니다.

## <a name="create-a-docker-image"></a>Docker 이미지 만들기

Docker 이미지는 *Dockerfile* 에 의해 정의 됩니다. 이 *Dockerfile* 은 응용 프로그램을 빌드하고 응용 프로그램을 빌드하거나 실행 하는 데 필요한 모든 종속성을 설치 하는 데 필요한 모든 명령을 포함 하는 텍스트 파일입니다. 다음 예제에서는 ASP.NET Core 5.0 응용 프로그램에 대 한 가장 간단한 Dockerfile을 보여 줍니다.

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:5.0 as build

WORKDIR /src

COPY ./StockKube.sln .
COPY ./src/StockData/StockData.csproj ./src/StockData/
COPY ./src/StockWeb/StockWeb.csproj ./src/StockWeb/

RUN dotnet restore

COPY . .

RUN dotnet publish --no-restore -c Release -o /published src/StockData/StockData.csproj

FROM mcr.microsoft.com/dotnet/aspnet:5.0 as runtime

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=build /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

Dockerfile에는 두 부분이 있습니다. 첫 번째는 기본 이미지를 사용 하 여 `sdk` 응용 프로그램을 빌드 및 게시 하 고, 두 번째는 기본에서 런타임 이미지를 만듭니다. `aspnet` 이는 `sdk` 900 이미지가 런타임 이미지에 대 한 약 200 mb와 비교 했 고, 런타임에 대부분의 콘텐츠가 필요 하지 않기 때문입니다.

### <a name="the-build-steps"></a>빌드 단계

| 단계 | 설명 |
| ---- | ----------- |
| `FROM ...` | 기본 이미지를 선언 하 고 별칭을 할당 합니다 `builder` . |
| `WORKDIR /src` | 디렉터리를 만들고 `/src` 현재 작업 디렉터리로 설정 합니다. |
| `COPY . .` | 호스트의 현재 디렉터리 아래에 있는 모든 항목을 이미지의 현재 디렉터리에 복사 합니다. |
| `RUN dotnet restore` | 외부 패키지를 복원 합니다 (ASP.NET Core 3.0 프레임 워크는 SDK와 함께 사전 설치 됨). |
| `RUN dotnet publish ...` | 릴리스 빌드를 빌드하고 게시 합니다. `--runtime`플래그가 필요 하지 않습니다. |

### <a name="the-runtime-image-steps"></a>런타임 이미지 단계

| 단계 | 설명 |
| ---- | ----------- |
| `FROM ...` | 새 기본 이미지를 선언 합니다. |
| `WORKDIR /app` | 디렉터리를 만들고 `/app` 현재 작업 디렉터리로 설정 합니다. |
| `COPY --from=builder ...` | 첫 번째 줄의 별칭을 사용 하 여 이전 이미지에서 게시 된 응용 프로그램을 복사 합니다 `builder` `FROM` . |
| `ENTRYPOINT [ ... ]` | 컨테이너가 시작 될 때 실행할 명령을 설정 합니다. `dotnet`런타임 이미지의 명령은 DLL 파일만 실행할 수 있습니다. |

### <a name="https-in-docker"></a>Docker의 HTTPS

Docker 용 Microsoft 기본 이미지 `ASPNETCORE_URLS` 환경 변수를로 설정 `http://+:80` 합니다. 즉, Kestrel은 해당 포트에서 HTTPS 없이 실행 됩니다. [자체 호스팅 gRPC 응용 프로그램](self-hosted.md)에 설명 된 대로 사용자 지정 인증서와 함께 HTTPS를 사용 하는 경우이 구성을 재정의 해야 합니다. Dockerfile의 런타임 이미지 생성 부분에 환경 변수를 설정 합니다.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/aspnet:5.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>. Dockerignore 파일

`.gitignore`특정 파일 및 디렉터리를 소스 제어에서 제외 하는 파일과 마찬가지로, `.dockerignore` 파일을 사용 하 여 빌드하는 동안 파일 및 디렉터리가 이미지에 복사 되지 않도록 제외할 수 있습니다. 이 파일은 시간 복사를 저장할 뿐 아니라 PC의 디렉터리를 이미지에 복사 하 여 발생 하는 일부 오류를 방지할 수도 있습니다 `obj` . 최소한 파일에 및에 대 한 항목을 추가 해야 `bin` `obj` `.dockerignore` 합니다.

```console
bin/
obj/
```

## <a name="build-the-image"></a>이미지 빌드

`StockKube.sln`서로 다른 두 응용 프로그램 및를 포함 하는 솔루션의 경우 `StockData` `StockWeb` 기본 디렉터리에 각각 dockerfile을 배치 하는 것이 가장 간단 합니다. 이 경우 이미지를 빌드하려면 `docker build` 파일이 있는 디렉터리에서 다음 명령을 사용 `.sln` 합니다.

```console
docker build -t stockdata:1.0.0 -f .\src\StockData\Dockerfile .
```

혼동 명명 된 `--tag` 플래그 (로 줄일 수 있음 `-t` )는 지정 된 경우 실제 태그를 포함 하 여 이미지의 전체 이름을 지정 합니다. 끝에 있는는 `.` 빌드가 실행 되는 컨텍스트를 지정 합니다. Dockerfile의 명령에 대 한 현재 작업 디렉터리입니다 `COPY` .

단일 솔루션 내에 여러 응용 프로그램이 있는 경우 각 응용 프로그램에 대 한 Dockerfile을 파일 옆에 있는 자체 폴더에 유지할 수 있습니다 `.csproj` . 그래도 `docker build` 기본 디렉터리에서 명령을 실행 하 여 솔루션과 모든 프로젝트가 이미지에 복사 되었는지 확인 해야 합니다. `--file`(또는) 플래그를 사용 하 여 현재 디렉터리 아래에 Dockerfile을 지정할 수 있습니다 `-f` .

```console
docker build -t stockdata:1.0.0 -f .\src\StockData\Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>컴퓨터의 컨테이너에서 이미지를 실행 합니다.

로컬 Docker 인스턴스에서 이미지를 실행 하려면 `docker run` 명령을 사용 합니다.

```console
docker run -ti -p 5000:80 stockdata:1.0.0
```

`-ti`플래그는 현재 터미널을 컨테이너의 터미널에 연결 하 고 대화형 모드로 실행 합니다. 는 `-p 5000:80` 컨테이너의 포트 80를 localhost 네트워크 인터페이스의 포트 5000에 게시 합니다.

## <a name="push-the-image-to-a-registry"></a>이미지를 레지스트리로 푸시

이미지가 작동 하는지 확인 한 후 Docker 레지스트리에 푸시하여 다른 시스템에서 사용할 수 있도록 합니다. 내부 네트워크에서 Docker 레지스트리를 프로 비전 해야 합니다. 이 활동은 docker [의 자체 `registry` 이미지](https://docs.docker.com/registry/deploying/) 를 실행 하는 것 처럼 간단할 수 있습니다 (docker 레지스트리는 docker 컨테이너에서 실행 됨). 하지만 사용할 수 있는 여러 가지 포괄적인 솔루션도 있습니다. 외부 공유 및 클라우드 사용을 위해 [Azure Container Registry](/azure/container-registry/) 또는 [Docker 허브](https://docs.docker.com/docker-hub/repos/)와 같이 다양 한 관리 되는 레지스트리를 사용할 수 있습니다.

Docker 허브에 푸시 하려면 이미지 이름 앞에 사용자 또는 조직 이름을 붙입니다.

```console
docker tag stockdata:1.0.0 <myorg>/stockdata:1.0.0
docker push <myorg>/stockdata:1.0.0
```

개인 레지스트리에 푸시 하려면 이미지 이름 앞에 레지스트리 호스트 이름 및 조직 이름을 붙입니다.

```console
docker tag stockdata <internal-registry:5000>/<myorg>/stockdata:1.0.0
docker push <internal-registry:5000>/<myorg>/stockdata:1.0.0
```

이미지가 레지스트리에 있으면 개별 Docker 호스트 또는 Kubernetes와 같은 컨테이너 오케스트레이션 엔진에 배포할 수 있습니다.

>[!div class="step-by-step"]
>[이전](self-hosted.md)
>[다음](kubernetes.md)
