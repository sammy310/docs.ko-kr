---
title: Docker 앱을 위한 내부 루프 개발 워크플로
description: Docker 응용 프로그램의 개발에 대 한 "내부 루프" 워크플로를 알아봅니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 36fcf5769376375854c2a2631e26e8b136df0de6
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920911"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Docker 앱을 위한 내부 루프 개발 워크플로

전체 DevOps에 걸쳐 루프 외부 워크플로 트리거하기 전에 주기, 각 개발자의 컴퓨터에서 해당 앱을 코딩, 해당 기본 설정된 언어 또는 플랫폼을 사용 하 여 및 로컬로 테스트 하 고 (그림 4-21) 시작 하는 것입니다. 있지만 모든 경우에서 해야는 중요 한 점은 공통적으로 선택 하는 언어, 프레임 워크 또는 플랫폼에 관계 없이 합니다. 이 특정 워크플로에서 항상을 개발 하 고 Docker 컨테이너를 로컬로 테스트 합니다.

![1 단계-코드/실행/디버그](./media/image18.png)

**그림 4-21**. 내부 루프 개발 컨텍스트

Docker 이미지의 인스턴스를 컨테이너에 이러한 구성 요소를 포함 됩니다.

-   운영 체제 선택 (예: Linux 배포 또는 Windows)

- 개발자 (예: 응용 프로그램 이진 파일)가 추가 된 파일

-   구성 (예: 환경 설정 및 종속성)

- Docker에서 실행을 처리 하는 것에 대 한 지침

(다음 섹션에서 설명) 프로세스와 Docker를 활용 하는 내부 루프 개발 워크플로를 설정할 수 있습니다. 한 번 수행 해야 하므로 환경을 설정 하는 초기 단계 포함 되지 않았는지를 고려 합니다.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Visual Studio Code 및 Docker CLI를 사용 하 여 Docker 컨테이너 내에서 단일 앱 빌드

앱은 사용자 고유의 서비스와 추가 라이브러리 (종속성)에서 구성 됩니다.

그림 4-22 일반적으로 각 단계에 자세히 설명 뒤에 Docker 앱을 빌드할 때 수행 해야 하는 기본 단계를 보여 줍니다.

![워크플로 개요: 1 단계-코드를 2 단계-Dockerfile을 4 단계를 사용 하 여 정의 하는 이미지 만들기-docker-compose 파일, 5 단계-실행 컨테이너를 사용 하 여 서비스를 정의 또는 구성 된 앱에 6 단계-앱 테스트, 7 단계-외부 루프 (CI/CD 파이프라인)를 시작 하려면 계속 de 푸시 Dockerfile을 3 단계-작성 veloping 합니다.](./media/image19.png)

**그림 4-22**. Docker CLI를 사용 하 여 컨테이너 화 된 Docker 응용 프로그램 수명 주기에 대 한 개략적인 워크플로

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>1단계: Visual Studio Code에서 코딩을 시작 하 고 초기 앱/서비스 기준 만들기

응용 프로그램을 개발 하는 방법은 Docker 없이 이렇게 하는 방법은 비슷합니다. 개발 중에만 배포 및 테스트 하 여 응용 프로그램 또는 서비스 (예: Linux VM 또는 Windows) 로컬 환경에 배치 하는 Docker 컨테이너 내에서 실행 되는 점이 다릅니다.

**로컬 환경 설정**

최신 버전의 Mac 및 Windows 용 Docker 사용 하 여 Docker 응용 프로그램 개발 그 어느 때 보다 훨씬 더 쉽게 하 고 설치는 간단 합니다.

> [!INFORMATION]
>
> 를 Docker에 대 한 Windows 설정에 대 한 이동 <https://docs.docker.com/docker-for-windows/>합니다.
>
>Mac 용 Docker 설정 지침에 대 한 <https://docs.docker.com/docker-for-mac/>합니다.

또한 해야 코드 편집기는 실제로 Docker CLI를 사용 하는 동안 응용 프로그램을 개발할 수 있습니다.

Microsoft 제공 Mac, Windows, 및 Linux에서 지원 되 고 사용 하 여 IntelliSense를 제공 하는 경량 코드 편집기 인 Visual Studio Code [다양 한 언어에 대 한 지원](https://code.visualstudio.com/docs/languages/overview) (JavaScript,.NET, Go, Java, Ruby, Python 및 가장 최신 언어의 경우) [디버깅](https://code.visualstudio.com/Docs/editor/debugging)를 [Git와 통합](https://code.visualstudio.com/Docs/editor/versioncontrol) 하 고 [확장](https://code.visualstudio.com/docs/extensions/overview)합니다. 이 편집기는 Linux 및 Mac 개발자를 위한 최적의 선택입니다. Windows에도 사용할 수 있습니다 전체 Visual Studio 응용 프로그램입니다.

> [!INFORMATION]
>
> 를 설치 하는 Visual Studio 코드에 대 한 Windows, Mac 또는 Linux에 대 한 이동 <https://code.visualstudio.com/docs/setup/setup-overview/>합니다.
>
> Mac 용 Docker 설정 지침에 대 한 <https://docs.docker.com/docker-for-mac/>합니다.

Docker 확장을 사용 하 여 Visual Studio Code를 사용 하 여 쉽게 작성 Docker CLI를 사용 하 고 어떤 코드 편집기를 사용 하 여 코드를 작성할 수 있지만 `Dockerfile` 고 `docker-compose.yml` 작업 영역에는 파일입니다. 또한 아래에 있는 Docker CLI를 사용 하 여 Docker 명령을 실행 하려면 Visual Studio 코드 IDE에서 태스크 및 스크립트를 실행할 수 있습니다.

VS Code 용 Docker 확장은 다음 기능을 제공 합니다.

- 자동 `Dockerfile` 고 `docker-compose.yml` 파일 생성

- 에 대 한 구문 강조 표시 하 고 가리키기 팁 `docker-compose.yml` 고 `Dockerfile` 파일

- IntelliSense (완료)에 대 한 `Dockerfile` 고 `docker-compose.yml` 파일

- 에 대 한 lint (오류 및 경고) `Dockerfile` 파일

- 가장 일반적인 Docker 명령에 대 한 명령 팔레트 (F1) 통합

- 이미지 및 컨테이너를 관리 하기 위한 탐색기 통합

- Azure App Service에 Azure 컨테이너 레지스트리 및 DockerHub에서 이미지를 배포 합니다.

Docker 확장을 설치 하려면 Ctrl + Shift + P를 눌러 입력 `ext install`, Marketplace 확장 목록을 표시 하려면 확장 설치 명령을 실행 합니다. 그런 다음 입력 **docker** 결과 필터링 하 여 다음 그림 4-23에서 언급 했 듯이 Docker 지원 확장을 선택 합니다.

![VS Code 용 Docker 확장의 보기입니다.](./media/image20.png)

**그림 4-23** Visual Studio Code의 Docker 확장을 설치합니다.

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>2단계: 기존 이미지 (일반 OS 또는.NET Core, Node.js 및 Ruby와 같은 개발 환경)와 관련 된 DockerFile 만들기

필요는 `DockerFile` 만들려는 사용자 지정 이미지 및 컨테이너 배포 당 합니다. 앱 구성 된 단일 사용자 지정 서비스를 단일 필요 `DockerFile`합니다. 앱은 여러 서비스 (예: 마이크로 서비스 아키텍처)으로 구성 해야 하나 있지만 `Dockerfile` 서비스 당 합니다.

`DockerFile` 일반적으로 앱 또는 서비스의 루트 폴더에 배치 되 고 Docker 설정 하 고 해당 앱 또는 서비스를 실행 하는 방법을 알 수 있도록 필요한 명령을 포함 합니다. 만들 수 있습니다 프로그램 `DockerFile` 코드와 함께 프로젝트에 추가 (.NET Core, node.js 등), 또는 환경에 새로운 인 경우 다음 팁을 살펴보시기 바랍니다.

> [!TIP]
>
> Docker 확장을 사용 하 여 사용 하는 경우 사용자에 게 안내 합니다 `Dockerfile` 및 `docker-compose.yml` Docker 컨테이너와 관련 된 파일입니다. 결국 이러한 종류의이 도구가 없는 경우 파일 작성 것 이지만 Docker 확장을 사용 하 여 배우를 가속화할 수 있는 좋은 시작 지점이 있습니다.

그림 4-24에서 docker를 어떻게 볼 수 있습니다-작성 파일 VS Code 용 Docker 확장을 사용 하 여 추가 됩니다.

![VS Code 용 Docker 확장의 콘솔 보기입니다.](./media/image24.png)

**그림 4-24** Docker 파일을 사용 하 여 추가 된 **작업 영역 명령에 Docker 추가 파일**

사용할 기본 Docker 이미지를 지정 하는 DockerFile에 추가 하면 (사용 하 여 같은 `FROM mcr.microsoft.com/dotnet/core/aspnet`). 일반적으로 사용자 지정 이미지에서 공식 리포지토리에서 얻을 수 있는 기본 이미지를 기반으로 빌드할 합니다 [Docker Hub 레지스트리에서](https://hub.docker.com/) (같은 [.NET Core에 대 한 이미지](https://hub.docker.com/_/microsoft-dotnet-core/) 나 [Node.js용](https://hub.docker.com/_/node/)).

***기존 공식 Docker 이미지를 사용 하 여***

버전 번호를 사용 하 여 언어 스택의 공식 리포지토리를 사용 하 여 동일한 언어 기능 (개발, 테스트 및 프로덕션 포함)는 모든 컴퓨터에서 사용할 수 있는지 확인 합니다.

다음은.NET Core 컨테이너에 대 한 샘플 DockerFile입니다.

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.1
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

이 경우에 기준으로 이미지 줄에 따라 공식 ASP.NET Core Docker 이미지 (Linux 및 Windows 용 다중 아키텍처)의 버전 2.1 `FROM mcr.microsoft.com/dotnet/core/aspnet:2.1`합니다. (이 항목에 대 한 자세한 내용은 참조는 [ASP.NET Core Docker 이미지](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) 페이지와 [.NET Core Docker 이미지](https://hub.docker.com/_/microsoft-dotnet-core/) 페이지).

DockerFile에서 Docker (예: 포트 80) 런타임 시 사용 하는 TCP 포트로 수신 하도록 지시할 수 있습니다.

사용하는 언어 및 프레임워크에 따라 Dockerfile에서 추가 구성 설정을 지정할 수 있습니다. 예를 들어 합니다 `ENTRYPOINT` 된 선 `["dotnet", "MySingleContainerWebApp.dll"]` .NET Core 응용 프로그램을 실행 하는 Docker에 알려 줍니다. SDK 및.NET Core CLI를 사용 중인 경우 (`dotnet CLI`)을 빌드하고.NET 응용 프로그램을 실행 하려면이 설정을 서로 다를 것입니다. 여기에서 핵심 ENTRYPOINT 줄 및 기타 설정을 응용 프로그램에 대해 선택한 언어 및 플랫폼에 종속 됩니다.

> [!INFORMATION]
>
> .NET Core 응용 프로그램에 대 한 Docker 이미지 작성 하는 방법에 대 한 자세한 내용은 이동 <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>합니다.
>
> 사용자 고유의 이미지를 작성 하는 방법에 대 한 자세한 내용은 이동 <https://docs.docker.com/engine/tutorials/dockerimages/>합니다.

**다중 아키텍처 이미지 리포지토리를 사용 합니다.**

리포지토리에 단일 이미지 이름에는 Linux 이미지 및 Windows 이미지 같은 플랫폼 변형을 포함할 수 있습니다. 이 기능은 여러 플랫폼 (즉, Linux 및 Windows)를 포함 하는 단일 리포지토리를 만들려면 (기본 이미지 작성자) Microsoft 같은 공급 업체입니다. 예를 들어 합니다 [dotnet/코어/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Docker Hub 레지스트리에서 리포지토리 동일한 이미지 이름을 사용 하 여 Linux 및 Windows Nano Server에 대 한 지원을 제공 합니다.

끌어오기 합니다 [dotnet/코어/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) 이미지 Windows 호스트에서 Linux 변형을 끌어옵니다 Linux 호스트에서 동일한 이미지 이름을 가져오는 반면 Windows 변형을 끌어옵니다.

***기본 이미지를 처음부터 만들기***

이 항목에 설명 된 대로 처음부터 사용자 고유의 Docker 기본 이미지를 만들 수 있습니다 [문서](https://docs.docker.com/engine/userguide/eng-image/baseimages/) Docker에서. 이 시나리오는 Docker를 사용 하 여 잘 모르는 경우 기본 이미지의 특정 비트를 설정 하려는 경우 수행할 수 있습니다 적합 되지 않을 수 있습니다.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>3단계: 에 서비스를 포함 하 여 사용자 지정 Docker 이미지 만들기

앱을 구성 하는 각 사용자 지정 서비스에 대 한 관련된 이미지를 만드는 해야 합니다. 단일 서비스 또는 웹 앱의 앱 옵션을 구성 된 경우에 단일 이미지를 방금 해야 합니다.

> [!NOTE]
>
> 소스 코드를 Git 리포지토리에 푸시할 (연속 통합), 글로벌 환경에서 이미지를 만들 수는에서 때마다 이미지 자동화 된 빌드 프로세스에 의해 만들어집니다 계정 "외부 루프 DevOps 워크플로의"를 고려 하는 경우에 소스 코드입니다.
>
> 그러나 Docker 응용 프로그램은 실제로 제대로 작동 하는지 확인 (Git 등). 소스 제어 시스템에 제대로 작동 하지 않을 수도 코드를 푸시 하지는 않도록 해야 것으로 간주 해당 외부 반복 경로를 이동 합니다.
>
> 따라서 각 개발자는 먼저 로컬에서 테스트 및 개발 하는 완전 한 기능을 푸시하거나 원본 제어 시스템에 변경 하려는 될 때까지 계속 전체 내부 루프 프로세스를 수행 해야 합니다.

이미지를 만드는에서 DockerFile을 사용 하 여 로컬 환경에서 사용할 수 그림 4-25에서 설명한 것 처럼 docker build 명령을 (실행할 수도 있습니다 `docker-compose up --build` 여러 컨테이너/서비스에서 구성 된 응용 프로그램에 대 한).

![이미지를 다운로드 진행률 표시, docker-compose build의 콘솔 출력입니다.](./media/image25.png)

**그림 4-25** 실행 중인 docker 빌드

직접 실행 하는 대신 필요에 따라 `docker build` 프로젝트 폴더에서 먼저 생성할 수 있습니다 배포 가능 폴더 실행을 사용 하 여 필요한.NET 라이브러리를 사용 하 여 `dotnet publish` 명령을 실행 하 고 그런 다음 `docker build`합니다.

이 예제에서는 이름을 사용 하 여 Docker 이미지를 만듭니다 `cesardl/netcore-webapi-microservice-docker:first` (`:first` 같은 특정 버전 태그는). 여러 컨테이너를 사용 하 여 구성 된 Docker 응용 프로그램에 대해 만들어야 하는 각 사용자 지정 이미지에 대해이 단계를 수행할 수 있습니다.

있습니다 명령을 찾을 수 있습니다 기존 이미지 로컬 리포지토리 (개발 컴퓨터)에서 docker를 사용 하 여 이미지, 그림 4-26에서와 같이 합니다.

![콘솔 출력에서 명령은 docker 이미지를 기존 이미지를 표시 합니다.](./media/image26.png)

**그림 4-26**. Docker 이미지를 사용 하 여 보기 기존 이미지

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>4단계: 여러 서비스를 사용 하 여 구성 된 Docker 앱을 빌드할 때 docker-compose.yml에서 서비스 정의

사용 하 여는 `docker-compose.yml` 파일에서 다음 단계 섹션에서 설명한 배포 명령을 사용 하 여 구성된 된 응용 프로그램으로 배포할 관련된 서비스 집합을 정의할 수 있습니다.

해당 파일에서 기본 또는 루트 솔루션 폴더 만들기 이 표시 된 유사한 콘텐츠 있어야 `docker-compose.yml` 파일:

```yml
version: '3.4'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

이 경우에이 파일은 두 서비스를 정의 합니다. (사용자 지정 서비스) 웹 서비스 및 redis 서비스 (인기 있는 캐시 서비스). 각각에 대 한 구체적인 Docker 이미지를 사용 해야 하므로 각 서비스는 컨테이너로 배포 됩니다. 이 특정 웹 서비스에 대 한 이미지는 다음을 수행 해야 합니다.

- 현재 디렉터리에서 DockerFile에서 빌드

- 노출된 된 포트 80 포트 81 호스트 컴퓨터에서 컨테이너에 전달 합니다.

- 이미지를 다시 빌드하지 않고 코드를 수정할 수 있도록 컨테이너 내의 모든 코드를 삽입 하려면 호스트에서 프로젝트 디렉터리 탑재

- 웹 서비스는 redis 서비스에 연결

Redis 서비스에서 사용 하는 [최신 공개 redis 이미지](https://hub.docker.com/_/redis/) Docker Hub 레지스트리에서 끌어옵니다. [redis](https://redis.io/) 는 인기 있는 캐시 시스템 서버쪽 응용 프로그램에 대 한 합니다.

### <a name="step-5-build-and-run-your-docker-app"></a>5단계: 빌드 및 Docker 앱 실행

앱에 단일 컨테이너만 경우 Docker 호스트 (VM 또는 물리적 서버)에 배포 하 여 실행 하기만 하면 됩니다. 그러나 경우 앱은 여러 서비스로 구성 된, 해야 *구성*도 합니다. 다양 한 옵션을 확인해 보겠습니다.

***옵션 A: 단일 컨테이너 또는 서비스를 실행 합니다.***

여기에 나와 있는 것 처럼 docker run 명령을 사용 하 여 Docker 이미지를 실행할 수 있습니다.

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

이 특정 배포에 대 한 내부 포트 5000에 포트 80에 전송 된 요청 리디렉션 수 됩니다 것입니다. 이제 응용 프로그램 호스트 수준에서 80 외부 포트에서 수신 대기 합니다.

***옵션 B: 작성 및 다중 컨테이너 응용 프로그램을 실행 합니다.***

대부분의 엔터프라이즈 시나리오에서 Docker 응용 프로그램을 여러 서비스로 구성 됩니다. 이러한 경우에 실행할 수 있습니다는 `docker-compose up` 수 이전에 만든 docker compose.yml 파일을 사용 하는 명령 (그림 4-27). 이 명령을 실행의 모든 해당 관련된 컨테이너를 사용 하 여 구성 된 응용 프로그램을 배포 합니다.

![콘솔 출력에서의 docker compose up 명령을 합니다.](./media/image27.png)

**그림 4-27**. "Docker compose 구성" 명령을 실행 한 결과

실행 한 후 `docker-compose up`, VM 표현에서에서 그림 4-28에서와 같이 응용 프로그램 및 해당 관련된 컨테이너에 Docker 호스트에 배포 합니다.

![다중 컨테이너 응용 프로그램을 실행 하는 VM.](./media/image28.png)

**그림 4-28**. Docker 컨테이너가 배포된 VM

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>6단계: (로컬 CD VM)에서 로컬로 Docker 응용 프로그램 테스트

이 단계는 고 앱이 수행 되는 내용에 따라 달라 집니다.

간단한.NET Core에서 Web API "Hello World" 단일 컨테이너 또는 서비스로 배포는 DockerFile에서 지정 된 TCP 포트를 제공 하 여 서비스에 액세스할 수만 해야 합니다.

서비스를 이동 하려면 localhost에 설정 되지 않은 경우는이 명령을 사용 하 여 컴퓨터에 대 한 IP 주소를 찾으려면:

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

Docker 호스트에서 브라우저를 열고 해당 사이트로; 이동 그림 4-29에 설명 된 대로 앱/서비스를 실행 하 여 표시 됩니다.

![Localhost/API/값 응답의 브라우저 보기입니다.](./media/image29.png)

**그림 4-29**. Localhost를 사용 하 여 로컬로 Docker 응용 프로그램 테스트

사용 하 여 배포 된 방법 이기 때문에 포트 80을 사용 하지만 내부 포트 5000에 리디렉션되는 참고 `docker run`앞에서 설명한 대로, 합니다.

터미널에서 CURL을 사용 하 여이 테스트할 수 있습니다. Windows에서 Docker 설치에서 기본 IP 경우 10.0.75.1, 그림 4-30에서 언급 했 듯이

![콘솔에서 출력 된 http://10.0.75.1/API/values curl을 사용 하 여](./media/image30.png)

**그림 4-30**. CURL을 사용 하 여 로컬로 Docker 응용 프로그램 테스트

**Docker에서 실행 되는 컨테이너 디버깅**

Visual Studio Code는 Node.js 및.NET Core 컨테이너 등의 다른 플랫폼을 사용 하는 경우 디버깅 Docker를 지원 합니다.

또한 디버깅할 수 있습니다 Docker에서.NET Core 또는.NET Framework 컨테이너 Visual Studio에 대 한 Windows 또는 Mac을 사용 하는 경우 다음 섹션에 설명 된 대로.

> [!INFORMATION]
>
> 로 Node.js Docker 컨테이너를 디버깅 하는 방법에 대 한 자세한 내용은 <https://blog.docker.com/2016/07/live-debugging-docker/> 고 <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>입니다.

>[!div class="step-by-step"]
>[이전](docker-apps-development-environment.md)
>[다음](visual-studio-tools-for-docker.md)
