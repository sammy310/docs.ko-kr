---
title: Docker 앱을 위한 개발 환경
description: Docker 개발 수명 주기를 지 원하는 가장 중요 한 개발 도구 옵션 익히기.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 3a2fcbe3b9380083622b6ce72cea4bab17d7c2ea
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318823"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="fe0cc-103">Docker 앱을 위한 개발 환경</span><span class="sxs-lookup"><span data-stu-id="fe0cc-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="fe0cc-104">개발 도구 선택: IDE 또는 편집기</span><span class="sxs-lookup"><span data-stu-id="fe0cc-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="fe0cc-105">든 관계 없이 완전 하 고 강력한 IDE 또는 가볍고 민첩 한 편집기를 선호 하는 경우 Microsoft는 Docker 응용 프로그램 개발에 있어.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="fe0cc-106">Visual Studio Code 및 Docker CLI (Mac, Linux 및 Windows 용 플랫폼 간 도구)</span><span class="sxs-lookup"><span data-stu-id="fe0cc-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="fe0cc-107">모든 개발 언어를 지 원하는 경량, 플랫폼 간 편집기를 원한다 면 Visual Studio Code 및 Docker CLI를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="fe0cc-108">이러한 제품은 개발자 워크플로 간소화 하는 것에 대 한 중요 한 간단 하지만 강력한 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="fe0cc-109">"Docker에 대 한 Mac" 또는 "Docker에 대 한 Windows" (개발 환경)를 설치 하 여 Docker 개발자 모두 Windows 또는 Linux (런타임 환경)에 대 한 앱을 빌드할 수는 단일 Docker CLI를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="fe0cc-110">또한 Visual Studio Code 편집기에서 Docker 명령을 실행 하는 Dockerfile 및 바로 가기 작업에 대 한 IntelliSense 사용 하 여 Docker에 대 한 확장을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
>
> <span data-ttu-id="fe0cc-111">Visual Studio Code를 다운로드 하려면로 이동 <https://code.visualstudio.com/download>합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>
>
> <span data-ttu-id="fe0cc-112">Mac 및 Windows 용 Docker를 다운로드 하려면로 이동 <https://www.docker.com/products/docker>합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a><span data-ttu-id="fe0cc-113">Docker 도구 (Windows 개발 컴퓨터)를 사용 하 여 visual Studio</span><span class="sxs-lookup"><span data-stu-id="fe0cc-113">Visual Studio with Docker Tools (Windows development machine)</span></span>

<span data-ttu-id="fe0cc-114">Visual Studio 2017 (이상)를 사용 하는 것이 좋습니다 설정 하는 기본 제공 Docker 도구를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-114">We recommend you use Visual Studio 2017 (or later) with the built-in Docker Tools enabled.</span></span> <span data-ttu-id="fe0cc-115">Visual Studio를 사용 하 여 개발, 실행 및 선택한 Docker 환경에서 직접 응용 프로그램의 유효성을 검사 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-115">With Visual Studio, you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="fe0cc-116">F5 키를 눌러 응용 프로그램을 디버깅 (단일 컨테이너 또는 여러 컨테이너) Docker 호스트에서 직접 또는 Ctrl + f5를 눌러 편집 하 고 컨테이너를 다시 빌드하지 않고 앱을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-116">Press F5 to debug your application (single container or multiple containers) directly in a Docker host, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="fe0cc-117">해당 하는 Linux 또는 Windows 용 Docker 컨테이너를 만들려면 Windows 개발자를 위한 간단 하 고 가장 강력한 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-117">It's the simplest and most powerful choice for Windows developers to create Docker containers for Linux or Windows.</span></span>

### <a name="visual-studio-for-mac-mac-development-machine"></a><span data-ttu-id="fe0cc-118">Visual Studio for Mac (Mac 개발 컴퓨터)</span><span class="sxs-lookup"><span data-stu-id="fe0cc-118">Visual Studio for Mac (Mac development machine)</span></span>

<span data-ttu-id="fe0cc-119">사용할 수 있습니다 [Mac 용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) Docker 기반 응용 프로그램을 개발 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-119">You can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) when developing Docker-based applications.</span></span> <span data-ttu-id="fe0cc-120">Mac 용 visual Studio는 mac 용 Visual Studio Code를 비교할 때 다양 한 IDE</span><span class="sxs-lookup"><span data-stu-id="fe0cc-120">Visual Studio for Mac offers a richer IDE when compared to Visual Studio Code for Mac.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="fe0cc-121">언어 및 프레임 워크 선택</span><span class="sxs-lookup"><span data-stu-id="fe0cc-121">Language and framework choices</span></span>

<span data-ttu-id="fe0cc-122">Microsoft 도구를 사용 하 여 가장 최신 언어를 사용 하 여 Docker 응용 프로그램을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-122">You can develop Docker applications using Microsoft tools with most modern languages.</span></span> <span data-ttu-id="fe0cc-123">다음은 초기 목록에 있지만를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-123">The following is an initial list, but you're not limited to it:</span></span>

- <span data-ttu-id="fe0cc-124">.NET Core 및 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fe0cc-124">.NET Core and ASP.NET Core</span></span>
- <span data-ttu-id="fe0cc-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="fe0cc-125">Node.js</span></span>
- <span data-ttu-id="fe0cc-126">이동</span><span class="sxs-lookup"><span data-stu-id="fe0cc-126">Go</span></span>
- <span data-ttu-id="fe0cc-127">Java</span><span class="sxs-lookup"><span data-stu-id="fe0cc-127">Java</span></span>
- <span data-ttu-id="fe0cc-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="fe0cc-128">Ruby</span></span>
- <span data-ttu-id="fe0cc-129">Python</span><span class="sxs-lookup"><span data-stu-id="fe0cc-129">Python</span></span>

<span data-ttu-id="fe0cc-130">기본적으로, Linux 또는 Windows에서 Docker를 지 원하는 모든 최신 언어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0cc-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fe0cc-131">[이전](deploy-azure-kubernetes-service.md)
>[다음](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fe0cc-131">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>
