---
title: Docker 앱을 위한 개발 환경
description: Docker 개발 수명 주기를 지원하는 가장 중요한 개발 도구 옵션을 알아봅니다.
ms.date: 08/06/2020
ms.openlocfilehash: 07b42b2bd05ab16ba0fbf61863b050ee2c9e242b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916027"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="2def5-103">Docker 앱을 위한 개발 환경</span><span class="sxs-lookup"><span data-stu-id="2def5-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="2def5-104">개발 도구 선택: IDE 또는 편집기</span><span class="sxs-lookup"><span data-stu-id="2def5-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="2def5-105">개발자가 완전하고 강력한 IDE를 선호하든 아니면 가볍고 민첩한 편집기를 선호하든, Microsoft에서는 Docker 애플리케이션 개발에 필요한 모든 것을 제공해 드립니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="2def5-106">Visual Studio Code 및 dotnet CLI(Mac, Linux 및 Windows용 플랫폼 간 도구)</span><span class="sxs-lookup"><span data-stu-id="2def5-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="2def5-107">모든 개발 언어를 지원하는 가벼운 플랫폼 간 편집기를 선호하는 경우 Visual Studio Code 및 Docker CLI를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="2def5-108">이러한 제품은 개발자 워크플로를 간소화하는 데 필요한 간단하면서도 강력한 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="2def5-109">"Mac용 Docker" 또는 "Windows용 Docker"(개발 환경)를 설치하면 Docker 개발자는 단일 Docker CLI를 사용하여 Windows 또는 Linux용 앱(런타임 환경)을 모두 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="2def5-110">뿐만 아니라 Visual Studio Code는 Dockerfile용 IntelliSense가 포함된 Docker용 확장 및 편집기에서 Docker 명령을 실행하는 바로 가기 작업을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="2def5-111">Visual Studio Code를 다운로드하려면 <https://code.visualstudio.com/download>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>
>
> <span data-ttu-id="2def5-112">Mac 및 Windows용 Docker를 다운로드하려면 <https://www.docker.com/products/docker>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a><span data-ttu-id="2def5-113">Docker 도구가 포함된 Visual Studio(Windows 개발 머신)</span><span class="sxs-lookup"><span data-stu-id="2def5-113">Visual Studio with Docker Tools (Windows development machine)</span></span>

<span data-ttu-id="2def5-114">기본 제공 Docker 도구를 사용하도록 설정된 Visual Studio 2019를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-114">It's recommend that you use Visual Studio 2019 with the built-in Docker Tools enabled.</span></span> <span data-ttu-id="2def5-115">Visual Studio가 있으면 원하는 Docker 환경에서 직접 애플리케이션을 개발하고, 실행하고, 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-115">With Visual Studio, you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="2def5-116">F5 키를 눌러 Docker 호스트에서 직접 애플리케이션(단일 컨테이너 또는 여러 컨테이너)을 디버그하거나, Ctrl+F5 키를 눌러 컨테이너를 다시 빌드하지 않고 앱을 편집하고 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-116">Press F5 to debug your application (single container or multiple containers) directly in a Docker host, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="2def5-117">이 방법은 Windows 개발자가 Linux 또는 Windows용 Docker 컨테이너를 만들 수 있는 가장 간단하면서도 강력한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-117">It's the simplest and most powerful choice for Windows developers to create Docker containers for Linux or Windows.</span></span>

### <a name="visual-studio-for-mac-mac-development-machine"></a><span data-ttu-id="2def5-118">Mac용 Visual Studio(Mac 개발 머신)</span><span class="sxs-lookup"><span data-stu-id="2def5-118">Visual Studio for Mac (Mac development machine)</span></span>

<span data-ttu-id="2def5-119">Docker 기반 애플리케이션을 개발할 때 [Mac용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-119">You can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) when developing Docker-based applications.</span></span> <span data-ttu-id="2def5-120">Mac용 Visual Studio는 Mac용 Visual Studio Code에 비해 풍부한 IDE를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-120">Visual Studio for Mac offers a richer IDE when compared to Visual Studio Code for Mac.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="2def5-121">언어 및 프레임워크 선택</span><span class="sxs-lookup"><span data-stu-id="2def5-121">Language and framework choices</span></span>

<span data-ttu-id="2def5-122">Microsoft 도구를 사용하여 가장 최신 언어로 Docker 애플리케이션을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-122">You can develop Docker applications using Microsoft tools with most modern languages.</span></span> <span data-ttu-id="2def5-123">다음은 초기 목록이지만, 이 목록으로 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-123">The following is an initial list, but you're not limited to it:</span></span>

- <span data-ttu-id="2def5-124">.NET Core 및 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2def5-124">.NET Core and ASP.NET Core</span></span>
- <span data-ttu-id="2def5-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="2def5-125">Node.js</span></span>
- <span data-ttu-id="2def5-126">이동</span><span class="sxs-lookup"><span data-stu-id="2def5-126">Go</span></span>
- <span data-ttu-id="2def5-127">Java</span><span class="sxs-lookup"><span data-stu-id="2def5-127">Java</span></span>
- <span data-ttu-id="2def5-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="2def5-128">Ruby</span></span>
- <span data-ttu-id="2def5-129">Python</span><span class="sxs-lookup"><span data-stu-id="2def5-129">Python</span></span>

<span data-ttu-id="2def5-130">기본적으로 Linux 또는 Windows에서 Docker가 지원하는 모든 최신 언어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2def5-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2def5-131">[이전](deploy-azure-kubernetes-service.md)
>[다음](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2def5-131">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>
