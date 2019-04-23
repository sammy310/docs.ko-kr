---
title: Docker 앱을 위한 개발 환경
description: Docker 개발 수명 주기를 지 원하는 가장 중요 한 개발 도구 옵션 익히기.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 3a2fcbe3b9380083622b6ce72cea4bab17d7c2ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767945"
---
# <a name="development-environment-for-docker-apps"></a>Docker 앱을 위한 개발 환경

## <a name="development-tools-choices-ide-or-editor"></a>개발 도구 선택: IDE 또는 편집기

든 관계 없이 완전 하 고 강력한 IDE 또는 가볍고 민첩 한 편집기를 선호 하는 경우 Microsoft는 Docker 응용 프로그램 개발에 있어.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code 및 Docker CLI (Mac, Linux 및 Windows 용 플랫폼 간 도구)

모든 개발 언어를 지 원하는 경량, 플랫폼 간 편집기를 원한다 면 Visual Studio Code 및 Docker CLI를 사용할 수 있습니다. 이러한 제품은 개발자 워크플로 간소화 하는 것에 대 한 중요 한 간단 하지만 강력한 환경을 제공 합니다. "Docker에 대 한 Mac" 또는 "Docker에 대 한 Windows" (개발 환경)를 설치 하 여 Docker 개발자 모두 Windows 또는 Linux (런타임 환경)에 대 한 앱을 빌드할 수는 단일 Docker CLI를 사용할 수 있습니다. 또한 Visual Studio Code 편집기에서 Docker 명령을 실행 하는 Dockerfile 및 바로 가기 작업에 대 한 IntelliSense 사용 하 여 Docker에 대 한 확장을 지원 합니다.

> [!NOTE]
>
> Visual Studio Code를 다운로드 하려면로 이동 <https://code.visualstudio.com/download>합니다.
>
> Mac 및 Windows 용 Docker를 다운로드 하려면로 이동 <https://www.docker.com/products/docker>합니다.

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a>Docker 도구 (Windows 개발 컴퓨터)를 사용 하 여 visual Studio

Visual Studio 2017 (이상)를 사용 하는 것이 좋습니다 설정 하는 기본 제공 Docker 도구를 사용 하 여 합니다. Visual Studio를 사용 하 여 개발, 실행 및 선택한 Docker 환경에서 직접 응용 프로그램의 유효성을 검사 수 있습니다. F5 키를 눌러 응용 프로그램을 디버깅 (단일 컨테이너 또는 여러 컨테이너) Docker 호스트에서 직접 또는 Ctrl + f5를 눌러 편집 하 고 컨테이너를 다시 빌드하지 않고 앱을 새로 고칩니다. 해당 하는 Linux 또는 Windows 용 Docker 컨테이너를 만들려면 Windows 개발자를 위한 간단 하 고 가장 강력한 좋습니다.

### <a name="visual-studio-for-mac-mac-development-machine"></a>Visual Studio for Mac (Mac 개발 컴퓨터)

사용할 수 있습니다 [Mac 용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) Docker 기반 응용 프로그램을 개발 하는 경우. Mac 용 visual Studio는 mac 용 Visual Studio Code를 비교할 때 다양 한 IDE

## <a name="language-and-framework-choices"></a>언어 및 프레임 워크 선택

Microsoft 도구를 사용 하 여 가장 최신 언어를 사용 하 여 Docker 응용 프로그램을 개발할 수 있습니다. 다음은 초기 목록에 있지만를 제한 합니다.

- .NET Core 및 ASP.NET Core
- Node.js
- 이동
- Java
- Ruby
- Python

기본적으로, Linux 또는 Windows에서 Docker를 지 원하는 모든 최신 언어를 사용할 수 있습니다.

>[!div class="step-by-step"]
>[이전](deploy-azure-kubernetes-service.md)
>[다음](docker-apps-inner-loop-workflow.md)
