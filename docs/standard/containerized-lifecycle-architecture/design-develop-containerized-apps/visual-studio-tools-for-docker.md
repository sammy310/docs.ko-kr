---
title: Visual Studio Tools for Windows의 Docker
description: Visual Studio 2017 버전 15.7 이상에서 사용할 수 있는 Docker 도구를 가져옵니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 431a0f34ba913c18c35e28ca45660495403bf688
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795596"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a>Windows의 Visual Studio 2017에서 사용 하 여 Docker 도구

Visual Studio 2017 버전 15.7 이상에 포함 된 Docker 도구를 사용 하는 경우 개발자 워크플로 Visual Studio Code 및 Docker CLI를 사용 하 여 비슷합니다 (실제로 동일한 Docker CLI)를 기반 하지만 더 쉽게 시작 하는 것에 프로세스를 간소화 하 고 향상 된 생산성을 제공 합니다. 빌드를 실행 하 고 작업을 구성 합니다. 또한 실행 및 디버그 하 여 컨테이너를 통해 일반적인 `F5` 고 `Ctrl+F5` Visual Studio에서 키입니다. 해당 컨테이너에서 동일한 정의 된 경우에 전체 솔루션을 디버깅할 수 있습니다 `docker-compose.yml` 솔루션 수준 파일입니다.

## <a name="configure-your-local-environment"></a>로컬 환경 구성

Docker에 대 한 Windows의 최신 버전을 계속 하려면 Docker 응용 프로그램 설치 프로그램은 다음 참조에 설명 된 대로 간단 하기 때문에 개발 보다 쉽습니다.

> [!TIP]
> 로 Windows에 Docker를 설치 하는 방법에 대 한 자세한 내용은 (<https://docs.docker.com/docker-for-windows/>).

## <a name="docker-support-in-visual-studio-2017"></a>Visual Studio 2017에 docker 지원

두 가지 수준의 Docker 지원 프로젝트에 추가할 수 있습니다. ASP.NET Core 프로젝트에 추가 하기만 하면를 `Dockerfile` 파일을 프로젝트에 Docker 지원을 사용 하도록 설정 합니다. 다음 수준이 추가 하는 컨테이너 오케스트레이션 지원 기능을 `Dockerfile` (이미 존재 하지 않는) 하는 경우 프로젝트에 및 `docker-compose.yml` 솔루션 수준 파일입니다. Docker Compose를 통해 컨테이너 오케스트레이션을 지원, Visual Studio 2017 버전 15.0을 15.7에서에서 기본적으로 추가 됩니다. 컨테이너 오케스트레이션 지원은 Visual Studio 2017 버전 15.8 이상에 옵트인 기능입니다. 나중에는 버전 15.8 Docker Compose 및 Service Fabric을 지원 합니다.

**추가 > Docker 지원** 하 고 **추가 > 컨테이너 오 케 스트레이 터 지원** 명령에는 ASP.NET Core 프로젝트에 대 한 프로젝트 노드의 오른쪽 클릭 메뉴 (또는 상황에 맞는 메뉴)에 위치한  **솔루션 탐색기**그림 4-31에서 표시 된 것 처럼:

![Visual Studio에서 Docker 지원 메뉴 옵션 추가](./media/add-docker-support-menu.png)

**그림 4-31**. Visual Studio 2017 프로젝트에 Docker 지원 추가

### <a name="add-docker-support"></a>Docker 지원 추가

선택 하 여 기존 ASP.NET Core 프로젝트에 Docker 지원을 추가할 수 있습니다 **추가** > **Docker 지원** 에서 **솔루션 탐색기**합니다. 또한 Docker 지원을 프로젝트를 만드는 동안 선택 하 여 사용할 수 있습니다 **Docker 지원 사용** 에 **새 ASP.NET Core 웹 응용 프로그램** 클릭 하면 열리는 대화 상자 **확인** 에 **새 프로젝트** 그림 4-32와 같이 대화 상자.

![Visual Studio에서 새 ASP.NET Core 웹앱에 Docker 지원 사용](./media/enable-docker-support-visual-studio.png)

**그림 4-32**. Visual Studio 2017에서 프로젝트를 만드는 동안 Docker 지원을 사용 하도록 설정

를 추가 하거나 Docker 지원을 사용 하도록 설정 하는 경우 Visual Studio 추가 된 *Dockerfile* 프로젝트 파일입니다.

> [!NOTE]
> 그림 4-33과 같이 ASP.NET 프로젝트 (.NET Framework,.NET Core 프로젝트가 아니라)에 대 한 프로젝트를 만드는 동안 Docker Compose 지원을 사용 하면 컨테이너 오케스트레이션을 지원도 추가 됩니다.

![ASP.NET 프로젝트에 Docker Compose 지원 사용](media/enable-docker-compose-support.png)

**그림 4-33**. Visual Studio 2017의 ASP.NET 프로젝트에 대 한 지원 Docker Compose를 사용 하도록 설정

### <a name="add-container-orchestration-support"></a>컨테이너 오케스트레이션을 지원 추가

다중 컨테이너 솔루션을 작성 하려는 경우 컨테이너 오케스트레이션을 지원 프로젝트에 추가 합니다. 이렇게 하면 실행 하 고 같은 정의 하는 경우 컨테이너 (전체 솔루션)의 그룹을 동시에 디버깅할 수 있습니다 *docker compose.yml* 파일입니다.

컨테이너 오케스트레이션을 지원 기능을 추가 하려면 마우스 오른쪽 단추로 클릭에서 솔루션 또는 프로젝트 노드 **솔루션 탐색기**, 선택한 **추가 > 컨테이너 오케스트레이션을 지원**합니다. 선택한 **Docker Compose** 또는 **Service Fabric** 컨테이너를 관리할 수 있습니다.

프로젝트에 추가 하는 Dockerfile 컨테이너 오케스트레이션을 지원 프로젝트에 추가한 후 표시와 **docker compose** 솔루션에 추가 하는 폴더 **솔루션 탐색기**그림 4-34와 같이:

![Visual Studio의 솔루션 탐색기 내의 Docker 파일](media/docker-support-solution-explorer.png)

**그림 4-34**합니다. Visual Studio 2017의 솔루션 탐색기에서 docker 파일

*docker-compose.yml*이 이미 있는 경우에는 Visual Studio에서 이 파일에 필수 구성 코드 줄을 추가합니다.

## <a name="configure-docker-tools"></a>Docker 도구를 구성 합니다.

주 메뉴에서 선택 **도구 > 옵션**를 확장 하 고 **컨테이너 도구 > 설정**합니다. 컨테이너 도구 설정이 표시 됩니다.

![Visual Studio Docker 도구 옵션을 표시 합니다. 프로젝트 로드 시 필요한 Docker 이미지를 자동으로 풀, 자동으로 백그라운드에서 컨테이너를 시작, 솔루션 닫기, 컨테이너를 자동으로 종료 및 트러스팅 SSL 인증서에 대 한 메시지를 표시 하지 마십시오.](./media/visual-studio-docker-tools-options.png)

**그림 4-35**합니다. Docker 도구 옵션

다음 표에서 이러한 옵션을 설정 하는 방법을 결정 하는 데 도움이 될 수 있습니다.

| 이름 | 기본 설정 | 적용 대상 | 설명 |
| -----|:---------------:|:----------:| ----------- |
| 프로젝트 로드 시 필요한 Docker 이미지를 자동으로 풀 | 켜기 | Docker Compose | 성능 향상된을 위한 프로젝트를 로드할 때 Visual Studio는 Docker 가져오기 작업을 백그라운드에서 시작 이미지가 이미 다운로드 될 때 코드를 실행할 준비가 되도록 또는 다운로드 프로세스. 방금 프로젝트를 로드 하 고 코드를 검색, 경우 해제할 수 있습니다이 필요 하지 않습니다 하는 컨테이너 이미지 다운로드를 방지 합니다. |
| 백그라운드에서 컨테이너를 자동으로 시작 합니다. | 켜기 | Docker Compose | 다시 성능 향상된을 위해 Visual Studio 컨테이너를 만듭니다 볼륨 탑재를 사용 하 여 빌드하고 컨테이너를 실행 하는 데 적합 합니다. 컨테이너를 만들 때 제어 하려는 경우이 해제 합니다. |
| Kill 컨테이너 솔루션에 자동으로 닫기 | 켜기 | Docker Compose | 이 기능을 끌 솔루션을 닫기 또는 Visual Studio를 닫은 후에 계속 실행 하기 위해 솔루션에 대 한 컨테이너를 하려는 경우. |
| Localhost SSL 인증서 신뢰에 대 한 확인 안 함 | 끄기 | ASP.NET Core 2.1 프로젝트 | Localhost SSL 인증서를 신뢰할 수 없는 경우 Visual Studio 묻는 프로젝트를 실행할 때마다이 확인란을 선택 하지 않으면. |

> [!WARNING]
> Localhost SSL 인증서가 신뢰할 수 있는 메시지를 표시 하지 않으려면 확인란을 HTTPS 요청을 웹 앱 또는 서비스에서 런타임에 실패할 수 있습니다. 이런 경우의 선택을 취소 합니다 **표시 안 함** 확인란 프로젝트를 실행 하 고 신뢰 프롬프트를 표시 합니다.

> [!TIP]
> 서비스 구현 및 Visual Studio Tools for Docker 사용에 자세한 내용은 다음 문서를 참조 합니다.
>
>로컬 Docker 컨테이너에서 앱을 디버깅 합니다. <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh>
>
>Visual Studio를 사용 하 여 컨테이너 레지스트리에 ASP.NET 컨테이너를 배포 합니다. <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

>[!div class="step-by-step"]
>[이전](docker-apps-inner-loop-workflow.md)
>[다음](set-up-windows-containers-with-powershell.md)
