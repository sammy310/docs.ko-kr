---
title: Docker 기반 애플리케이션의 개발 프로세스
description: Docker 기반 애플리케이션의 개발 옵션을 개괄적으로 살펴봅니다. Windows용 Visual Studio, Mac용 Visual Studio 또는 여러 플랫폼(Windows, macOS, Linux)을 지원하는 Visual Studio Code를 선택할 수 있습니다.
ms.date: 01/13/2021
ms.openlocfilehash: 3a4f4078e745c52e8eca46473668e3319917bfd2
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188298"
---
# <a name="development-process-for-docker-based-applications"></a><span data-ttu-id="a2ae2-104">Docker 기반 애플리케이션의 개발 프로세스</span><span class="sxs-lookup"><span data-stu-id="a2ae2-104">Development process for Docker-based applications</span></span>

<span data-ttu-id="a2ae2-105">*Visual Studio 및 Visual Studio Tools for Docker에 중점을 둔 IDE(통합 개발 환경) 또는 Docker CLI 및 Visual Studio Code에 중점을 둔 CLI/편집기 중 원하는 방식으로 컨테이너화된 .NET 애플리케이션을 개발하세요.*</span><span class="sxs-lookup"><span data-stu-id="a2ae2-105">*Develop containerized .NET applications the way you like, either Integrated Development Environment (IDE) focused with Visual Studio and Visual Studio tools for Docker or CLI/Editor focused with Docker CLI and Visual Studio Code.*</span></span>

## <a name="development-environment-for-docker-apps"></a><span data-ttu-id="a2ae2-106">Docker 앱을 위한 개발 환경</span><span class="sxs-lookup"><span data-stu-id="a2ae2-106">Development environment for Docker apps</span></span>

### <a name="development-tool-choices-ide-or-editor"></a><span data-ttu-id="a2ae2-107">개발 도구 선택: IDE 또는 편집기</span><span class="sxs-lookup"><span data-stu-id="a2ae2-107">Development tool choices: IDE or editor</span></span>

<span data-ttu-id="a2ae2-108">완전하고 강력한 IDE를 선호하든지 아니면 간단하고 민첩한 편집기를 선호하든지 상관없이 Microsoft는 Docker 애플리케이션을 개발하는 데 사용할 수 있는 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-108">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has tools that you can use for developing Docker applications.</span></span>

<span data-ttu-id="a2ae2-109">**Visual Studio(Windows용)** .</span><span class="sxs-lookup"><span data-stu-id="a2ae2-109">**Visual Studio (for Windows).**</span></span> <span data-ttu-id="a2ae2-110">Visual Studio를 사용하여 Docker 기반 .NET 5 애플리케이션을 개발하려면 Visual Studio 2019 버전 16.4 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-110">Docker-based .NET 5 application development with Visual Studio requires Visual Studio 2019 version 16.4 or later.</span></span> <span data-ttu-id="a2ae2-111">Visual Studio 2019에는 Docker용 도구가 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-111">Visual Studio 2019 comes with tools for Docker already built in.</span></span> <span data-ttu-id="a2ae2-112">Docker용 도구를 통해 대상 Docker 환경에서 직접 애플리케이션을 개발하고 실행할 수 있으며, 애플리케이션의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-112">The tools for Docker let you develop, run, and validate your applications directly in the target Docker environment.</span></span> <span data-ttu-id="a2ae2-113">F5 키를 눌러 애플리케이션(단일 컨테이너 또는 여러 컨테이너)을 Docker 호스트에 직접 실행 및 디버그하거나, Ctrl+F5를 눌러 컨테이너를 다시 빌드하지 않고도 애플리케이션을 편집 및 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-113">You can press F5 to run and debug your application (single container or multiple containers) directly into a Docker host, or press CTRL+F5 to edit and refresh your application without having to rebuild the container.</span></span> <span data-ttu-id="a2ae2-114">해당 IDE는 Docker 기반 앱을 위한 가장 강력한 개발 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-114">This IDE is the most powerful development choice for Docker-based apps.</span></span>

<span data-ttu-id="a2ae2-115">**Mac용 Visual Studio.**</span><span class="sxs-lookup"><span data-stu-id="a2ae2-115">**Visual Studio for Mac.**</span></span> <span data-ttu-id="a2ae2-116">Xamarin Studio가 확장된 IDE이며 macOS에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-116">It's an IDE, evolution of Xamarin Studio, running in macOS.</span></span> <span data-ttu-id="a2ae2-117">.NET 5 개발의 경우 버전 8.4 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-117">For .NET 5 development, it requires version 8.4 or later.</span></span> <span data-ttu-id="a2ae2-118">해당 도구는 macOS 머신에서 작업 중인 개발자로, 강력한 IDE도 사용하려는 경우에 권장되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-118">This tool should be the preferred choice for developers working in macOS machines who also want to use a powerful IDE.</span></span>

<span data-ttu-id="a2ae2-119">**Visual Studio Code 및 Docker CLI**.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-119">**Visual Studio Code and Docker CLI**.</span></span> <span data-ttu-id="a2ae2-120">개발 언어를 지원하는 간단하면서 여러 플랫폼에서 사용 가능한 편집기를 선호하는 경우 Visual Studio Code 및 Docker CLI를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-120">If you prefer a lightweight and cross-platform editor that supports any development language, you can use Visual Studio Code and the Docker CLI.</span></span> <span data-ttu-id="a2ae2-121">해당 IDE는 macOS, Linux, Windows의 플랫폼 간 개발 접근 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-121">This IDE is a cross-platform development approach for macOS, Linux, and Windows.</span></span> <span data-ttu-id="a2ae2-122">또한 Visual Studio Code는 Dockerfile용 IntelliSense와 같은 Docker용 확장을 지원하고 편집기에서 Docker 명령을 실행하는 바로 가기 작업도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-122">Additionally, Visual Studio Code supports extensions for Docker such as IntelliSense for Dockerfiles and shortcut tasks to run Docker commands from the editor.</span></span>

<span data-ttu-id="a2ae2-123">[Docker Desktop CE(Community Edition)](https://hub.docker.com/search/?type=edition&offering=community)를 설치하면 단일 Docker CLI를 사용하여 Windows용 앱과 Linux용 앱을 모두 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-123">By installing [Docker Desktop Community Edition (CE)](https://hub.docker.com/search/?type=edition&offering=community), you can use a single Docker CLI to build apps for both Windows and Linux.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a2ae2-124">추가 자료</span><span class="sxs-lookup"><span data-stu-id="a2ae2-124">Additional resources</span></span>

- <span data-ttu-id="a2ae2-125">**Visual Studio**</span><span class="sxs-lookup"><span data-stu-id="a2ae2-125">**Visual Studio**.</span></span> <span data-ttu-id="a2ae2-126">공식 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-126">Official site.</span></span> \
  [https://visualstudio.microsoft.com/vs/](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

- <span data-ttu-id="a2ae2-127">**Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="a2ae2-127">**Visual Studio Code**.</span></span> <span data-ttu-id="a2ae2-128">공식 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-128">Official site.</span></span> \
  <https://code.visualstudio.com/download>

- <span data-ttu-id="a2ae2-129">**Windows CE(Community Edition)를 위한 Docker Desktop** </span><span class="sxs-lookup"><span data-stu-id="a2ae2-129">**Docker Desktop for Windows Community Edition (CE)** </span></span>\
  [https://hub.docker.com/editions/community/docker-ce-desktop-windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows)

- <span data-ttu-id="a2ae2-130">**Mac CE(Community Edition)를 위한 Docker Desktop** </span><span class="sxs-lookup"><span data-stu-id="a2ae2-130">**Docker Desktop for Mac Community Edition (CE)** </span></span>\
  [https://hub.docker.com/editions/community/docker-ce-desktop-mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac)

## <a name="net-languages-and-frameworks-for-docker-containers"></a><span data-ttu-id="a2ae2-131">Docker 컨테이너를 위한 .NET 언어 및 프레임워크</span><span class="sxs-lookup"><span data-stu-id="a2ae2-131">.NET languages and frameworks for Docker containers</span></span>

<span data-ttu-id="a2ae2-132">이 가이드의 이전 섹션에서 언급했듯이 Docker 컨테이너화된 .NET 애플리케이션을 개발할 때 .NET Framework, .NET 5 또는 오픈 소스 Mono 프로젝트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-132">As mentioned in earlier sections of this guide, you can use .NET Framework, .NET 5, or the open-source Mono project when developing Docker containerized .NET applications.</span></span> <span data-ttu-id="a2ae2-133">Linux 또는 Windows 컨테이너를 대상으로 할 때 사용 중인 .NET Framework에 따라 C\#, F\# 또는 Visual Basic으로 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-133">You can develop in C\#, F\#, or Visual Basic when targeting Linux or Windows Containers, depending on which .NET framework is in use.</span></span> <span data-ttu-id="a2ae2-134">.NET 언어에 대한 자세한 내용은 블로그 게시물, [The .NET Language Strategy](https://devblogs.microsoft.com/dotnet/the-net-language-strategy/)(.NET 언어 전략)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2ae2-134">For more details about.NET languages, see the blog post [The .NET Language Strategy](https://devblogs.microsoft.com/dotnet/the-net-language-strategy/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a2ae2-135">[이전](../architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)
>[다음](docker-app-development-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a2ae2-135">[Previous](../architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)
[Next](docker-app-development-workflow.md)</span></span>
