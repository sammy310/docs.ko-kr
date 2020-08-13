---
title: Docker 앱을 위한 내부 루프 개발 워크플로
description: Docker 애플리케이션에 대한 “내부 루프” 개발 워크플로에 대해 알아봅니다.
ms.date: 08/06/2020
ms.openlocfilehash: bf837ab53fff2b53cf141b2e621d484cff9b6889
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916205"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="37cac-103">Docker 앱을 위한 내부 루프 개발 워크플로</span><span class="sxs-lookup"><span data-stu-id="37cac-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="37cac-104">전체 DevOps 주기를 포함하는 외부 루프 워크플로를 트리거하기 전에 각 개발자의 머신에서 앱 자체 코딩, 선호하는 언어 또는 플랫폼 사용 및 로컬로 테스트를 모두 시작합니다(그림 4-21).</span><span class="sxs-lookup"><span data-stu-id="37cac-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="37cac-105">그러나 모든 경우 선택하는 언어, 프레임워크 또는 플랫폼과 상관없이 공통되는 중요한 지점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="37cac-106">이 특정 워크플로에서는 항상 Docker 컨테이너를 개발 및 테스트하되, 다른 환경이 아닌 로컬로만 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-106">In this specific workflow, you're always developing and testing Docker containers in no other environments, but locally.</span></span>

![내부 루프 개발 환경의 개념을 보여 주는 다이어그램](./media/docker-apps-inner-loop-workflow/inner-loop-development-context.png)

<span data-ttu-id="37cac-108">**그림 4-21**.</span><span class="sxs-lookup"><span data-stu-id="37cac-108">**Figure 4-21**.</span></span> <span data-ttu-id="37cac-109">내부 루프 개발 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="37cac-109">Inner-loop development context</span></span>

<span data-ttu-id="37cac-110">Docker 이미지의 컨테이너 또는 인스턴스는 다음 구성 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-110">The container or instance of a Docker image will contain these components:</span></span>

- <span data-ttu-id="37cac-111">운영 체제 선택(예: Linux 배포판 또는 Windows)</span><span class="sxs-lookup"><span data-stu-id="37cac-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="37cac-112">개발자가 추가한 파일(예: 앱 이진 파일)</span><span class="sxs-lookup"><span data-stu-id="37cac-112">Files added by the developer (for example, app binaries)</span></span>

- <span data-ttu-id="37cac-113">구성(예: 환경 설정 및 종속성)</span><span class="sxs-lookup"><span data-stu-id="37cac-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="37cac-114">Docker에서 실행할 프로세스에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="37cac-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="37cac-115">Docker를 프로세스로 이용하는 내부 루프 개발 워크플로를 설정할 수 있습니다(다음 섹션에서 설명).</span><span class="sxs-lookup"><span data-stu-id="37cac-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="37cac-116">환경을 설정하는 초기 단계는 한 번만 수행하면 되므로 포함되지 않는 것을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="37cac-117">Visual Studio Code 및 Docker CLI를 사용하여 Docker 컨테이너 내에서 단일 앱 빌드</span><span class="sxs-lookup"><span data-stu-id="37cac-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="37cac-118">앱은 개발자 고유의 서비스와 추가 라이브러리(종속성)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="37cac-119">그림 4-22는 Docker 앱을 빌드할 때 일반적으로 수행해야 하는 기본 단계를 보여준 다음, 각 단계를 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![컨테이너화 된 앱을 만드는 데 필요한 7가지 단계를 보여 주는 다이어그램입니다.](./media/docker-apps-inner-loop-workflow/life-cycle-containerized-apps-docker-cli.png)

<span data-ttu-id="37cac-121">**그림 4-22**.</span><span class="sxs-lookup"><span data-stu-id="37cac-121">**Figure 4-22**.</span></span> <span data-ttu-id="37cac-122">Docker CLI를 사용하여 Docker 컨테이너화된 애플리케이션 수명 주기에 대한 고급 워크플로</span><span class="sxs-lookup"><span data-stu-id="37cac-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="37cac-123">1단계: Visual Studio Code에서 코딩을 시작하고 초기 앱/서비스 기준선 만들기</span><span class="sxs-lookup"><span data-stu-id="37cac-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="37cac-124">애플리케이션을 개발하는 방법은 Docker 없이 수행하는 방법과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="37cac-125">다른 점은 개발하는 동안 로컬 환경(예: Linux VM 또는 Windows)에 배치된 Docker 컨테이너 내에서 실행하는 애플리케이션 또는 서비스를 배포 및 테스트한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="37cac-126">**로컬 환경 설정**</span><span class="sxs-lookup"><span data-stu-id="37cac-126">**Setting up your local environment**</span></span>

<span data-ttu-id="37cac-127">최신 버전의 Mac용 및 Windows용 Docker Desktop을 사용하면 이전의 어느 때보다 쉽게 Docker 애플리케이션을 개발할 수 있으며 설정도 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-127">With the latest versions of Docker Desktop for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!TIP]
> <span data-ttu-id="37cac-128">Windows용 Docker Desktop 설정 지침은 <https://docs.docker.com/docker-for-windows/>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-128">For instructions on setting up Docker Desktop for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
> <span data-ttu-id="37cac-129">Mac용 Docker Desktop 설정 지침은 <https://docs.docker.com/docker-for-mac/>으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-129">For instructions on setting up Docker Desktop for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="37cac-130">또한 Docker CLI를 사용하는 동안 실제로 애플리케이션을 개발할 수 있도록 코드 편집기가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-130">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="37cac-131">Microsoft는 Windows, Linux 및 macOS에서 지원되는 경량 코드 편집기인 Visual Studio Code를 제공하고, IntelliSense에서 [다양한 언어에 대한 지원](https://code.visualstudio.com/docs/languages/overview)(JavaScript, .NET, Go, Java, Ruby, Python 및 가장 최신 언어), [디버깅](https://code.visualstudio.com/Docs/editor/debugging), [Git와의 통합](https://code.visualstudio.com/Docs/editor/versioncontrol), [확장명 지원](https://code.visualstudio.com/docs/extensions/overview) 등을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-131">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Windows, Linux, and macOS, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="37cac-132">이 편집기는 macOS 및 Linux 개발자에게 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-132">This editor is a great fit for macOS and Linux developers.</span></span> <span data-ttu-id="37cac-133">Windows에서는 Visual Studio를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-133">In Windows, you also can use Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="37cac-134">Windows, Linux 또는 macOS에서의 Visual Studio Code 설치 지침은 <https://code.visualstudio.com/docs/setup/setup-overview/>으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-134">For instructions on installing Visual Studio Code for Windows, Linux, or macOS, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="37cac-135">Mac용 Docker 설정 지침은 <https://docs.docker.com/docker-for-mac/>으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-135">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="37cac-136">Docker CLI로 작업하고 임의의 코드 편집기를 사용하여 코드를 작성할 수 있지만, Docker 확장을 포함하는 Visual Studio Code를 사용하면 작업 영역에서 `Dockerfile` 및 `docker-compose.yml` 파일을 작성하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-136">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="37cac-137">또한 Visual Studio Code IDE에서 작업 및 스크립트를 실행하고 아래의 Docker CLI를 사용하여 Docker 명령을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-137">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="37cac-138">VS Code용 Docker 확장은 다음 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-138">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="37cac-139">자동 `Dockerfile` 및 `docker-compose.yml` 파일 생성</span><span class="sxs-lookup"><span data-stu-id="37cac-139">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="37cac-140">`docker-compose.yml` 및 `Dockerfile` 파일에 대한 구문 강조 표시 및 가리키기 정보</span><span class="sxs-lookup"><span data-stu-id="37cac-140">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="37cac-141">`Dockerfile` 및 `docker-compose.yml` 파일에 대한 IntelliSense(완성판)</span><span class="sxs-lookup"><span data-stu-id="37cac-141">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="37cac-142">`Dockerfile` 파일에 대한 린팅(오류 및 경고)</span><span class="sxs-lookup"><span data-stu-id="37cac-142">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="37cac-143">가장 일반적인 Docker 명령에 대한 명령 팔레트(F1) 통합</span><span class="sxs-lookup"><span data-stu-id="37cac-143">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="37cac-144">이미지 및 컨테이너를 관리하기 위한 탐색기 통합</span><span class="sxs-lookup"><span data-stu-id="37cac-144">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="37cac-145">Azure App Service에 DockerHub 및 Azure 컨테이너 레지스트리의 이미지 배포</span><span class="sxs-lookup"><span data-stu-id="37cac-145">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="37cac-146">Docker 확장을 설치하려면 Ctrl+Shift+P를 누르고 `ext install`을 입력한 후 Install Extension 명령을 실행하여 Marketplace 확장 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-146">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="37cac-147">그런 다음, **docker**를 입력하여 결과를 필터링한 후 그림 4-23과 같이 Docker Support 확장을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-147">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![VS Code용 Docker 확장 보기](media/docker-apps-inner-loop-workflow/install-docker-extension-vs-code.png)

<span data-ttu-id="37cac-149">**그림 4-23**</span><span class="sxs-lookup"><span data-stu-id="37cac-149">**Figure 4-23**.</span></span> <span data-ttu-id="37cac-150">Visual Studio Code에 Docker 확장 설치</span><span class="sxs-lookup"><span data-stu-id="37cac-150">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="37cac-151">2단계: 기존 이미지와 관련된 DockerFile 만들기(일반 OS 또는 .NET Core, Node.js 및 Ruby와 같은 dev 환경)</span><span class="sxs-lookup"><span data-stu-id="37cac-151">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="37cac-152">빌드할 사용자 지정 이미지 및 배포할 컨테이너마다 `DockerFile`이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-152">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="37cac-153">앱이 단일 사용자 지정 서비스로 구성된 경우 단일 `DockerFile`이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-153">If your app is made up of single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="37cac-154">그러나 앱이 여러 서비스로 구성된 경우(마이크로서비스 아키텍처의 경우와 같이) 서비스마다 한 개의 `Dockerfile`이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-154">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="37cac-155">`DockerFile`은 일반적으로 앱 또는 서비스의 루트 폴더에 배치되며 Docker가 해당 앱 또는 서비스를 설정하고 실행하는 방법을 알 수 있도록 하는 데 필요한 명령을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-155">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="37cac-156">자신의 `DockerFile`을 만들고 코드(node.js, .NET Core 등)와 함께 프로젝트에 추가하거나 새로운 환경인 경우 다음 정보를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-156">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="37cac-157">컨테이너와 관련된 `Dockerfile` 및 `docker-compose.yml` 파일을 사용하는 경우 Docker 확장을 사용하여 안내를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-157">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="37cac-158">결국 이러한 종류의 파일은 이 도구 없이 작성하겠지만 Docker 확장 사용은 학습 진도를 가속화하는 좋은 시작점이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-158">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="37cac-159">그림 4-24에서는 VS Code용 Docker 확장을 사용하여 프로젝트에 docker 파일을 추가하는 단계를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-159">In Figure 4-24, you can see the steps to add the docker files to a project by using the Docker Extension for VS Code:</span></span>

1. <span data-ttu-id="37cac-160">명령 팔레트를 열고 “**docker**”를 입력한 다음, “**작업 영역에 Docker 파일 추가**”를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-160">Open the command palette, type "**docker**" and select "**Add Docker Files to Workspace**".</span></span>
2. <span data-ttu-id="37cac-161">애플리케이션 플랫폼(ASP.NET Core) 선택</span><span class="sxs-lookup"><span data-stu-id="37cac-161">Select Application Platform (ASP.NET Core)</span></span>
3. <span data-ttu-id="37cac-162">운영 체제(Linux) 선택</span><span class="sxs-lookup"><span data-stu-id="37cac-162">Select Operating System (Linux)</span></span>
4. <span data-ttu-id="37cac-163">선택적 Docker Compose 파일 포함</span><span class="sxs-lookup"><span data-stu-id="37cac-163">Include optional Docker Compose files</span></span>
5. <span data-ttu-id="37cac-164">게시할 포트(80, 443) 입력</span><span class="sxs-lookup"><span data-stu-id="37cac-164">Enter ports to publish (80, 443)</span></span>
6. <span data-ttu-id="37cac-165">프로젝트 선택</span><span class="sxs-lookup"><span data-stu-id="37cac-165">Select the project</span></span>

![docker 확장을 사용하여 docker 파일을 추가하는 단계](media/docker-apps-inner-loop-workflow/add-docker-files-to-workspace-command.png)

<span data-ttu-id="37cac-167">**그림 4-24**</span><span class="sxs-lookup"><span data-stu-id="37cac-167">**Figure 4-24**.</span></span> <span data-ttu-id="37cac-168">**작업 영역에 Docker 파일 추가** 명령을 사용하여 추가한 Docker 파일</span><span class="sxs-lookup"><span data-stu-id="37cac-168">Docker files added using the **Add Docker files to Workspace** command</span></span>

<span data-ttu-id="37cac-169">DockerFile을 추가하는 경우 사용하는 기본 Docker 이미지가 무엇인지 지정합니다(예: `FROM mcr.microsoft.com/dotnet/core/aspnet`을 사용).</span><span class="sxs-lookup"><span data-stu-id="37cac-169">When you add a DockerFile, you specify what base Docker image you'll be using (like using `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span></span> <span data-ttu-id="37cac-170">일반적으로 [Docker Hub 레지스트리](https://hub.docker.com/)의 공식 리포지토리에서 가져오는 기본 이미지(예: [.NET Core용 이미지](https://hub.docker.com/_/microsoft-dotnet-core/) 또는 [Node.js](https://hub.docker.com/_/node/)용 이미지) 위에 사용자 지정 이미지를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-170">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

> [!TIP]
> <span data-ttu-id="37cac-171">애플리케이션의 모든 프로젝트에 대해 이 절차를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-171">You'll have to repeat this procedure for every project in your application.</span></span> <span data-ttu-id="37cac-172">그러나 확장은 처음 이후에는 생성된 docker-compose 파일을 덮어쓸지 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-172">However, the extension will ask to overwrite the generated docker-compose file after the first time.</span></span> <span data-ttu-id="37cac-173">덮어쓰지 않도록 응답해야 합니다. 그러면 확장은 별도의 docker-compose 파일을 만들어 docker-compose 실행 전에 사용자가 직접 병합할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-173">You should reply to not overwrite it, so the extension creates separate docker-compose files, that you can then merge by hand, prior to running docker-compose.</span></span>

<span data-ttu-id="37cac-174">**_기존의 공식 Docker 이미지 사용_**</span><span class="sxs-lookup"><span data-stu-id="37cac-174">**_Use an existing official Docker image_**</span></span>

<span data-ttu-id="37cac-175">버전 번호가 있는 언어 스택의 공식 리포지토리를 사용하면 모든 머신(개발, 테스트 및 프로덕션 포함)에서 동일한 언어 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-175">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="37cac-176">다음은 .NET Core 컨테이너에 대한 샘플 DockerFile입니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-176">The following is a sample DockerFile for a .NET Core container:</span></span>

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /src
COPY ["src/WebApi/WebApi.csproj", "src/WebApi/"]
RUN dotnet restore "src/WebApi/WebApi.csproj"
COPY . .
WORKDIR "/src/src/WebApi"
RUN dotnet build "WebApi.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "WebApi.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "WebApi.dll"]
```

<span data-ttu-id="37cac-177">이 경우 이미지는 줄 `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1`에 따라 버전 3.1의 공식 ASP.NET Core Docker 이미지(Linux용 및 Windows용 다중 아키텍처)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-177">In this case, the image is based on version 3.1 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1`.</span></span> <span data-ttu-id="37cac-178">(이 주제에 대한 자세한 내용은 [ASP.NET Core Docker 이미지](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) 페이지 및 [.NET Core Docker 이미지](https://hub.docker.com/_/microsoft-dotnet-core/) 페이지를 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="37cac-178">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) page and the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page).</span></span>

<span data-ttu-id="37cac-179">DockerFile에서 Docker에 대해 런타임에 사용할 TCP 포트(예: 포트 80 또는 443)를 수신 대기하도록 지시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-179">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80 or 443).</span></span>

<span data-ttu-id="37cac-180">사용하는 언어 및 프레임워크에 따라 Dockerfile에서 추가 구성 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-180">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="37cac-181">예를 들어 `["dotnet", "WebMvcApplication.dll"]`이 포함된 `ENTRYPOINT` 줄은 Docker에 대해 .NET Core 애플리케이션을 실행하라고 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-181">For instance, the `ENTRYPOINT` line with `["dotnet", "WebMvcApplication.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="37cac-182">SDK 및 .NET Core CLI(`dotnet CLI`)를 사용하여 .NET 애플리케이션을 빌드하고 실행하는 경우 이 설정이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-182">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="37cac-183">여기서 중요한 점은 ENTRYPOINT 줄 및 기타 설정은 애플리케이션에 대해 선택하는 언어 및 플랫폼에 따라 달라진다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-183">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!TIP]
> <span data-ttu-id="37cac-184">.NET Core 애플리케이션용 Docker 이미지 빌드에 대한 자세한 내용은 <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-184">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="37cac-185">자신의 고유한 이미지 빌드에 대해 자세히 알아보려면 <https://docs.docker.com/engine/tutorials/dockerimages/>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-185">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="37cac-186">**다중 아키텍처 이미지 리포지토리 사용**</span><span class="sxs-lookup"><span data-stu-id="37cac-186">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="37cac-187">리포지토리의 단일 이미지 이름은 Linux 이미지 및 Windows 이미지와 같은 플랫폼 변형을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-187">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="37cac-188">이 기능을 통해 Microsoft와 같은 공급업체(기본 이미지 작성자)는 여러 플랫폼(즉, Linux 및 Windows)을 처리하는 단일 리포지토리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-188">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="37cac-189">예를 들어 Docker Hub 레지스트리에서 제공되는 [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) 리포지토리는 동일한 이미지 이름을 사용하여 Linux 및 Windows Nano Server에 대한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-189">For example, the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="37cac-190">Windows 호스트에서 [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) 이미지를 풀하면 Windows 변형을 풀하고, Linux 호스트에서 동일한 이미지 이름을 풀하면 Linux 변형을 풀합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-190">Pulling the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="37cac-191">**_기본 이미지를 처음부터 새로 만들기_**</span><span class="sxs-lookup"><span data-stu-id="37cac-191">**_Create your base image from scratch_**</span></span>

<span data-ttu-id="37cac-192">이 [문서](https://docs.docker.com/engine/userguide/eng-image/baseimages/)에서 설명한 대로 Docker에서 자신의 고유한 Docker 기본 이미지를 처음부터 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-192">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="37cac-193">이 시나리오는 Docker를 이제 막 시작하는 경우 최선이 아닐 수 있지만, 자신의 고유한 기본 이미지에 대해 특정 비트를 설정하려는 경우 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-193">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="37cac-194">3단계: 서비스가 포함된 사용자 지정 Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="37cac-194">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="37cac-195">앱을 구성하는 각 사용자 지정 서비스에 대해 관련된 이미지를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-195">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="37cac-196">앱이 단일 서비스 또는 웹앱으로 구성된 경우 단일 이미지만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-196">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="37cac-197">"외부 루프 DevOps 워크플로"를 고려하는 경우 소스 코드를 Git 리포지토리에 푸시할 때마다(지속적인 통합) 자동화된 빌드 프로세스에 의해 이미지가 생성되므로 해당 이미지는 소스 코드에서 해당 글로벌 환경에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-197">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="37cac-198">그러나 외부 루프 경로로 이동을 고려하기 전에 올바르게 작동하지 않을 수 있는 코드를 원본 제어 시스템(예: Git)에 푸시하지 않도록 Docker 애플리케이션이 실제로 올바르게 작동하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-198">But before you consider going to that outer-loop route, you need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="37cac-199">따라서 각 개발자는 먼저 로컬에서 전체 내부 루프 프로세스를 수행하여 테스트하고 전체 기능 또는 변경 내용을 원본 제어 시스템에 푸시하려 할 때까지 개발을 계속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-199">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="37cac-200">로컬 환경에서 이미지를 만들려고 하며 DockerFile을 사용하는 경우 그림 4-25에 표시된 것처럼 docker build 명령을 사용할 수 있습니다. 이 경우 단일 명령으로 이미지에 태그를 지정하고, 애플리케이션의 모든 서비스용 이미지가 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-200">To create an image in your local environment and using the DockerFile, you can use the docker build command, as shown in Figure 4-25, because it already tags the image for you and builds the images for all services in the application with a simple command.</span></span>

![docker-compose build 명령의 콘솔 출력을 보여 주는 스크린샷입니다.](media/docker-apps-inner-loop-workflow/run-docker-build-command.png)

<span data-ttu-id="37cac-202">**그림 4-25**</span><span class="sxs-lookup"><span data-stu-id="37cac-202">**Figure 4-25**.</span></span> <span data-ttu-id="37cac-203">Docker 빌드 실행</span><span class="sxs-lookup"><span data-stu-id="37cac-203">Running docker build</span></span>

<span data-ttu-id="37cac-204">원할 경우 프로젝트 폴더에서 `docker build`를 실행하는 대신 먼저 run `dotnet publish` 명령을 사용하여 필요한 .NET 라이브러리를 포함하는 배포 가능한 폴더를 생성한 후 `docker build`를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-204">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="37cac-205">이 예제에서는 이름 `explore-docker-vscode/webapi:latest`를 사용하여 Docker 이미지를 만듭니다(`:latest`는 특정 버전과 같은 태그임).</span><span class="sxs-lookup"><span data-stu-id="37cac-205">This example creates a Docker image with the name `explore-docker-vscode/webapi:latest` (`:latest` is a tag, like a specific version).</span></span> <span data-ttu-id="37cac-206">여러 컨테이너를 포함하도록 구성된 Docker 애플리케이션에 대해 만들어야 하는 각 사용자 지정 이미지마다 이 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-206">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span> <span data-ttu-id="37cac-207">그러나 다음 섹션에서는 `docker-compose`를 사용하여 이 작업을 더 쉽게 수행할 수 있다는 사실을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-207">However, we'll see in the next section that it's easier to do this using `docker-compose`.</span></span>

<span data-ttu-id="37cac-208">그림 4-26과 같이 `docker images` 명령을 사용하여 로컬 리포지토리(개발 머신)에서 기존 이미지를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-208">You can find the existing images in your local repository (your development machine) by using the `docker images` command, as illustrated in Figure 4-26.</span></span>

![기존 이미지를 보여주는 docker images 명령의 콘솔 출력](media/docker-apps-inner-loop-workflow/view-existing-images-with-docker-images.png)

<span data-ttu-id="37cac-210">**그림 4-26**.</span><span class="sxs-lookup"><span data-stu-id="37cac-210">**Figure 4-26**.</span></span> <span data-ttu-id="37cac-211">Docker 이미지를 사용하여 기존 이미지 보기</span><span class="sxs-lookup"><span data-stu-id="37cac-211">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="37cac-212">4단계: 여러 서비스를 포함하도록 구성된 Docker 앱을 빌드할 때 docker-compose.yml에서 서비스 정의</span><span class="sxs-lookup"><span data-stu-id="37cac-212">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="37cac-213">`docker-compose.yml` 파일을 통해 다음 단계 섹션에서 설명하는 배포 명령을 사용하여 구성된 애플리케이션으로 배포할 관련 서비스 세트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-213">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="37cac-214">해당 파일을 주 또는 루트 솔루션 폴더에 만들며, 해당 파일은 이 `docker-compose.yml` 파일에 표시된 것과 유사한 콘텐츠를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-214">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

```yml
version: "3.4"

services:
  webapi:
    image: webapi
    build:
      context: .
      dockerfile: src/WebApi/Dockerfile
    ports:
      - 51080:80
    depends_on:
      - redis
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://+:80

  webapp:
    image: webapp
    build:
      context: .
      dockerfile: src/WebApp/Dockerfile
    ports:
      - 50080:80
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://+:80
      - WebApiBaseAddress=http://webapi

  redis:
    image: redis
```

<span data-ttu-id="37cac-215">이 경우 이 파일은 웹 API 서비스(사용자 지정 서비스), 웹 애플리케이션 및 Redis 서비스(인기 있는 캐시 서비스)의 세 가지 서비스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-215">In this particular case, this file defines three services: the web API service (your custom service), a web application, and the Redis service (a popular cache service).</span></span> <span data-ttu-id="37cac-216">각 서비스는 컨테이너로 배포되므로 각 서비스에 대해 구체적인 Docker 이미지를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-216">Each service will be deployed as a container, so you need to use a concrete Docker image for each.</span></span> <span data-ttu-id="37cac-217">이 특정 애플리케이션에서 다음이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-217">For this particular application:</span></span>

- <span data-ttu-id="37cac-218">웹 API 서비스는 `src/WebApi/Dockerfile` 디렉터리의 DockerFile에서 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-218">The web API service is built from the DockerFile in the `src/WebApi/Dockerfile` directory.</span></span>

- <span data-ttu-id="37cac-219">호스트 포트 51080은 `webapi` 컨테이너의 노출된 포트 80으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-219">The host port 51080 is forwarded to the exposed port 80 on the `webapi` container.</span></span>

- <span data-ttu-id="37cac-220">웹 API 서비스는 Redis 서비스에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-220">The web API service depends on the Redis service</span></span>

- <span data-ttu-id="37cac-221">웹 애플리케이션은 내부 주소 `http://webapi`를 사용하여 웹 API 서비스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-221">The web application accesses the web API service using the internal address: `http://webapi`.</span></span>

- <span data-ttu-id="37cac-222">Redis 서비스는 Docker Hub 레지스트리에서 풀한 [최신 공용 redis 이미지](https://hub.docker.com/_/redis/)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-222">The Redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="37cac-223">[Redis](https://redis.io/)는 인기 있는 서버 쪽 애플리케이션용 캐시 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-223">[Redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="37cac-224">5단계: Docker 앱을 빌드하고 실행</span><span class="sxs-lookup"><span data-stu-id="37cac-224">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="37cac-225">앱에 단일 컨테이너만 있는 경우 해당 앱을 Docker 호스트(VM 또는 실제 서버)에 배포하여 실행하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-225">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="37cac-226">그러나 앱이 여러 서비스로 구성된 경우 _앱 구성_도 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-226">However, if your app is made up of multiple services, you need to _compose it_, too.</span></span> <span data-ttu-id="37cac-227">다양한 옵션을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-227">Let's see the different options.</span></span>

<span data-ttu-id="37cac-228">**_옵션 A: 단일 컨테이너 또는 서비스를 실행_**</span><span class="sxs-lookup"><span data-stu-id="37cac-228">**_Option A: Run a single container or service_**</span></span>

<span data-ttu-id="37cac-229">여기에서 보여주는 대로 Docker 실행 명령을 사용하여 Docker 이미지를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-229">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 50080:80 explore-docker-vscode/webapp:latest
```

<span data-ttu-id="37cac-230">이 특정 배포의 경우 호스트의 포트 50080으로 보낸 요청을 내부 포트 80으로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-230">For this particular deployment, we'll be redirecting requests sent to port 50080 on the host to the internal port 80.</span></span>

<span data-ttu-id="37cac-231">**_옵션 B: 여러 컨테이너 애플리케이션을 구성 및 실행_**</span><span class="sxs-lookup"><span data-stu-id="37cac-231">**_Option B: Compose and run a multiple-container application_**</span></span>

<span data-ttu-id="37cac-232">대부분의 엔터프라이즈 시나리오에서 Docker 애플리케이션은 여러 서비스로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-232">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="37cac-233">이 경우 이전에 만든 docker-compose.yml 파일을 사용하는 `docker-compose up` 명령(그림 4-27)을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-233">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you created previously.</span></span> <span data-ttu-id="37cac-234">이 명령을 실행하면 모든 사용자 지정 이미지가 빌드되고 모든 관련 컨테이너로 구성된 애플리케이션이 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-234">Running this command builds all custom images and deploys the composed application with all of its related containers.</span></span>

![docker-compose up 명령의 콘솔 출력](media/docker-apps-inner-loop-workflow/results-docker-compose-up.png)

<span data-ttu-id="37cac-236">**그림 4-27**.</span><span class="sxs-lookup"><span data-stu-id="37cac-236">**Figure 4-27**.</span></span> <span data-ttu-id="37cac-237">"docker-compose up" 명령을 실행한 결과</span><span class="sxs-lookup"><span data-stu-id="37cac-237">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="37cac-238">`docker-compose up`을 실행한 후 그림 4-28에서 보여주듯이 애플리케이션 및 관련 컨테이너를 VM 표시의 Docker 호스트에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-238">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![다중 컨테이너 애플리케이션을 실행하는 VM](./media/docker-apps-inner-loop-workflow/vm-with-docker-containers-deployed.png)

<span data-ttu-id="37cac-240">**그림 4-28**.</span><span class="sxs-lookup"><span data-stu-id="37cac-240">**Figure 4-28**.</span></span> <span data-ttu-id="37cac-241">Docker 컨테이너가 배포된 VM</span><span class="sxs-lookup"><span data-stu-id="37cac-241">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="37cac-242">6단계: Docker 호스트 테스트(로컬로, 로컬 CD VM에서)</span><span class="sxs-lookup"><span data-stu-id="37cac-242">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="37cac-243">이 단계는 앱이 수행하는 기능에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-243">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="37cac-244">단일 컨테이너 또는 서비스로 배포된 간단한 .NET Core 웹 API "Hello World"에서는 DockerFile에 지정된 TCP 포트를 제공하여 서비스에 액세스하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-244">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="37cac-245">Docker 호스트에서 브라우저를 열고 해당 사이트로 이동합니다. 그림 4-29와 같이 앱/서비스가 실행될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-245">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![localhost/API/값에서 오는 응답의 브라우저 보기](media/docker-apps-inner-loop-workflow/test-docker-app-locally-localhost.png)

<span data-ttu-id="37cac-247">**그림 4-29**.</span><span class="sxs-lookup"><span data-stu-id="37cac-247">**Figure 4-29**.</span></span> <span data-ttu-id="37cac-248">브라우저를 사용하여 로컬로 Docker 애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="37cac-248">Testing your Docker application locally by using the browser</span></span>

<span data-ttu-id="37cac-249">포트 50080을 사용하지만 앞에서 설명한 대로 내부적으로는 `docker compose`을 사용하여 배포되는 방법에 따라 포트 80으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-249">Note that it's using port 50080, but internally it's being redirected to port 80, because that's how it was deployed with `docker compose`, as explained earlier.</span></span>

<span data-ttu-id="37cac-250">그림 4-30에 나와 있는 것처럼 터미널에서 CURL을 사용하는 브라우저를 통해 이러한 테스트를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-250">You can test this by using the browser using CURL from the terminal, as depicted in Figure 4-30.</span></span>

![http://localhost:51080/WeatherForecast 에서 얻은 Curl 결과](media/docker-apps-inner-loop-workflow/test-docker-app-locally-curl.png)

<span data-ttu-id="37cac-252">**그림 4-30**.</span><span class="sxs-lookup"><span data-stu-id="37cac-252">**Figure 4-30**.</span></span> <span data-ttu-id="37cac-253">CURL을 사용하여 로컬로 Docker 애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="37cac-253">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="37cac-254">**Docker에서 실행되는 컨테이너 디버깅**</span><span class="sxs-lookup"><span data-stu-id="37cac-254">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="37cac-255">Visual Studio Code는 Node.js 및 다른 플랫폼(예: .NET Core 컨테이너)을 사용하는 경우 디버깅 Docker를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-255">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="37cac-256">또한 다음 섹션에서 설명하는 대로 Windows용 또는 Mac용 Visual Studio를 사용하는 경우 Docker의 .NET Core 또는 .NET Framework 컨테이너를 디버그할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cac-256">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!TIP]
> <span data-ttu-id="37cac-257">Node.js Docker 컨테이너 디버깅에 대한 자세한 내용은 <https://blog.docker.com/2016/07/live-debugging-docker/> 및 <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more> 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37cac-257">To learn more about debugging Node.js Docker containers, see <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="37cac-258">[이전](docker-apps-development-environment.md)
> [다음](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="37cac-258">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
