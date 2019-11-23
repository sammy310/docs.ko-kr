---
title: WCF 개발자를 위한 Docker gRPC
description: ASP.NET Core gRPC 응용 프로그램에 대 한 Docker 이미지 만들기
ms.date: 09/02/2019
ms.openlocfilehash: a5aceb4b5270cb828965e990a62db4147012adff
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967835"
---
# <a name="docker"></a>Docker

이 섹션에서는 ASP.NET Core gRPC 응용 프로그램에 대 한 Docker 이미지 생성, Docker, Kubernetes 또는 기타 컨테이너 환경에서 실행할 준비를 설명 합니다. ASP.NET Core MVC 웹 앱 및 gRPC 서비스를 사용 하 여 사용 되는 샘플 응용 프로그램은 GitHub의 [dotnet-아키텍처/grpc-wcf-개발자](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) 리포지토리에서 사용할 수 있습니다.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>ASP.NET Core 응용 프로그램용 Microsoft 기본 이미지

Microsoft는 .NET Core 응용 프로그램 빌드 및 실행을 위한 다양 한 기본 이미지를 제공 합니다. ASP.NET Core 3.0 이미지를 만들기 위해 응용 프로그램을 빌드 및 게시 하기 위한 SDK 이미지와 배포용 런타임 이미지 라는 두 개의 기본 이미지가 사용 됩니다.

| 이미지 | Description |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/core/sdk](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | `docker build`를 사용 하 여 응용 프로그램을 빌드하는 데 사용 됩니다. 프로덕션에서는 사용 하지 않습니다. |
| [mcr.microsoft.com/dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | 런타임 및 ASP.NET Core 종속성을 포함 합니다. 프로덕션의 경우. |

각 이미지에는 다른 Linux 배포판을 기반으로 하는 네 가지 변형이 있습니다 (태그로 구분).

| 이미지 태그 | Linux | 참고 |
| --------- | ----- | ----- |
| 3.0-buster, 3.0 | Debian 10 | OS 변형이 지정 되지 않은 경우 기본 이미지입니다. |
| 3.0-알파인 | 알파인 3.9 | 알파인 기본 이미지는 Debian 또는 Ubuntu 1 보다 훨씬 작습니다. |
| 3.0-disco | Ubuntu 19.04 | |
| 3.0-bionic | Ubuntu 18.04 | |

알파인 기본 이미지는 Debian 및 Ubuntu 이미지에 대 한 200 MB와 비교해 100 약 이지만 일부 소프트웨어 패키지 또는 라이브러리는 알파인의 패키지 관리에서 사용 하지 못할 수 있습니다. 사용할 이미지를 잘 모르는 경우 다른 배포판를 사용 해야 하는 경우를 제외 하 고 기본 Debian을 사용 하는 것이 좋습니다.

> [!IMPORTANT]
> 빌드 및 런타임에 동일한 유형의 Linux를 사용 해야 합니다. 하나의 변형에 빌드되고 게시 된 응용 프로그램은 다른 변형에서 작동 하지 않을 수 있습니다.

## <a name="create-a-docker-image"></a>Docker 이미지 만들기

Docker 이미지는 응용 프로그램을 빌드하고 응용 프로그램을 빌드하고 실행 하는 데 필요한 모든 종속성을 설치 하는 데 필요한 모든 명령을 포함 하는 텍스트 파일인 *Dockerfile*에 의해 정의 됩니다. 다음 예제에서는 ASP.NET Core 3.0 응용 프로그램에 대 한 가장 간단한 Dockerfile을 보여 줍니다.

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

Dockerfile에는 두 부분이 있습니다. 첫 번째는 `sdk` 기본 이미지를 사용 하 여 응용 프로그램을 빌드하고 게시 합니다. 두 번째는 `aspnet` 기반에서 런타임 이미지를 만듭니다. 이는 `sdk` 이미지가 런타임 이미지에 대 한 약 200 MB와 비교 하 여 약 900이이 고, 런타임에 대부분의 콘텐츠는 필요 하지 않기 때문입니다.

### <a name="the-build-steps"></a>빌드 단계

| 단계 | Description |
| ---- | ----------- |
| `FROM ...` | 기본 이미지를 선언 하 고 `builder` 별칭을 할당 합니다 (설명에 대해서는 다음 섹션 참조). |
| `WORKDIR /src` | `/src` 디렉터리를 만들고 현재 작업 디렉터리로 설정 합니다. |
| `COPY . .` | 호스트의 현재 디렉터리 아래에 있는 모든 항목을 이미지의 현재 디렉터리에 복사 합니다. |
| `RUN dotnet restore` | 외부 패키지를 복원 합니다 (ASP.NET Core 3.0 프레임 워크는 SDK와 함께 사전 설치 됨). |
| `RUN dotnet publish ...` | 릴리스 빌드를 빌드하고 게시 합니다. `--runtime` 플래그는 필요 하지 않습니다. |

### <a name="the-runtime-image-steps"></a>런타임 이미지 단계

| 단계 | Description |
| ---- | ----------- |
| `FROM ...` | 새 기본 이미지를 선언 합니다. |
| `WORKDIR /app` | `/app` 디렉터리를 만들고 현재 작업 디렉터리로 설정 합니다. |
| `COPY --from=builder ...` | 첫 번째 `FROM` 줄의 `builder` 별칭을 사용 하 여 이전 이미지에서 게시 된 응용 프로그램을 복사 합니다. |
| `ENTRYPOINT [ ... ]` | 컨테이너가 시작 될 때 실행할 명령을 설정 합니다. 런타임 이미지의 `dotnet` 명령은 DLL 파일만 실행할 수 있습니다. |

### <a name="https-in-docker"></a>Docker의 HTTPS

Docker 용 Microsoft의 기본 이미지는 `ASPNETCORE_URLS` 환경 변수를 `http://+:80`로 설정 합니다. 즉, Kestrel은 해당 포트에서 HTTPS 없이 실행 됩니다. [이전 섹션](self-hosted.md)에서 설명한 대로 사용자 지정 인증서와 함께 HTTPS를 사용 하는 경우 Dockerfile의 **런타임 이미지 생성 부분에** 환경 변수를 설정 하 여이를 재정의 해야 합니다.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>. Dockerignore 파일

특정 파일 및 디렉터리를 소스 제어에서 제외 하는 `.gitignore` 파일과 마찬가지로 `.dockerignore` 파일을 사용 하 여 파일 및 디렉터리를 빌드하는 동안 이미지에 복사 하지 않도록 제외할 수 있습니다. 이렇게 하면 복사 시간이 절약 될 뿐만 아니라 PC에서 이미지에 복사 된 `obj` 디렉터리를 사용 하 여 발생 하는 혼동을 방지할 수 있습니다. `bin`에 대 한 항목을 하나 이상 추가 하 고 `.dockerignore` 파일에 `obj` 해야 합니다.

```console
bin/
obj/
```

## <a name="build-the-image"></a>이미지 빌드

단일 응용 프로그램, 즉 단일 Dockerfile이 있는 솔루션의 경우 Dockerfile을 기본 디렉터리에 배치 하는 것이 가장 간단 합니다. 즉, `.sln` 파일과 동일한 디렉터리입니다. 이 경우 이미지를 빌드하려면 Dockerfile을 포함 하는 디렉터리에서 다음 `docker build` 명령을 사용 합니다.

```console
docker build --tag stockdata .
```

혼동 이라는 이름의 `--tag` 플래그 (`-t`으로 줄일 수 있음)는 지정 된 경우 실제 태그를 *포함* 하 여 이미지의 전체 이름을 지정 합니다. 끝에 있는 `.`는 빌드가 실행 될 *컨텍스트* 를 지정 합니다. Dockerfile의 `COPY` 명령에 대 한 현재 작업 디렉터리입니다.

단일 솔루션 내에 여러 응용 프로그램이 있는 경우 각 응용 프로그램에 대 한 Dockerfile을 `.csproj` 파일 옆에 있는 자체 폴더에 유지할 수 있지만, 솔루션과 모든 프로젝트가 이미지에 복사 되도록 기본 디렉터리에서 `docker build` 명령을 계속 실행 해야 합니다. `--file` (또는 `-f`) 플래그를 사용 하 여 현재 디렉터리 아래에 Dockerfile을 지정할 수 있습니다.

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>컴퓨터의 컨테이너에서 이미지를 실행 합니다.

로컬 Docker 인스턴스에서 이미지를 실행 하려면 `docker run` 명령을 사용 합니다.

```console
docker run -ti -p 5000:80 stockdata
```

`-ti` 플래그는 현재 터미널을 컨테이너의 터미널에 연결 하 고 대화형 모드로 실행 합니다. `-p 5000:80`는 컨테이너의 포트 80를 localhost 네트워크 인터페이스의 포트 80에 게시 합니다.

## <a name="push-the-image-to-a-registry"></a>레지스트리에 이미지 푸시

이미지가 작동 하는지 확인 한 후에는 다른 시스템에서 사용할 수 있도록 Docker 레지스트리에 푸시 해야 합니다. 내부 네트워크에서 Docker 레지스트리를 프로 비전 해야 합니다. 이는 [docker의 자체 `registry` 이미지](https://docs.docker.com/registry/deploying/) 를 실행 하는 것 처럼 간단할 수 있습니다 (docker 레지스트리는 docker 컨테이너에서 실행 됨). 그러나 다양 한 포괄적인 솔루션을 사용할 수 있습니다. 외부 공유 및 클라우드 사용을 위해 [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) 또는 [Docker 허브](https://docs.docker.com/docker-hub/repos/)와 같이 다양 한 관리 되는 레지스트리를 사용할 수 있습니다.

Docker 허브에 푸시 하려면 이미지 이름 앞에 사용자 또는 조직 이름을 붙입니다.

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

개인 레지스트리에 푸시 하려면 이미지 이름 앞에 레지스트리 호스트 이름 및 조직 이름을 붙입니다.

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

이미지가 레지스트리에 있으면 개별 Docker 호스트 또는 Kubernetes와 같은 컨테이너 오케스트레이션 엔진에 배포할 수 있습니다.

>[!div class="step-by-step"]
>[이전](self-hosted.md)
>[다음](kubernetes.md)
