---
title: Docker 앱을 위한 내부 루프 개발 워크플로
description: Docker 응용 프로그램의 개발에 대 한 "내부 루프" 워크플로를 알아봅니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 36fcf5769376375854c2a2631e26e8b136df0de6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050570"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="ad4b1-103">Docker 앱을 위한 내부 루프 개발 워크플로</span><span class="sxs-lookup"><span data-stu-id="ad4b1-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="ad4b1-104">전체 DevOps에 걸쳐 루프 외부 워크플로 트리거하기 전에 주기, 각 개발자의 컴퓨터에서 해당 앱을 코딩, 해당 기본 설정된 언어 또는 플랫폼을 사용 하 여 및 로컬로 테스트 하 고 (그림 4-21) 시작 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="ad4b1-105">있지만 모든 경우에서 해야는 중요 한 점은 공통적으로 선택 하는 언어, 프레임 워크 또는 플랫폼에 관계 없이 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="ad4b1-106">이 특정 워크플로에서 항상을 개발 하 고 Docker 컨테이너를 로컬로 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-106">In this specific workflow, you're always developing and testing Docker containers, but locally.</span></span>

![1 단계-코드/실행/디버그](./media/image18.png)

<span data-ttu-id="ad4b1-108">**그림 4-21**.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-108">**Figure 4-21**.</span></span> <span data-ttu-id="ad4b1-109">내부 루프 개발 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="ad4b1-109">Inner-loop development context</span></span>

<span data-ttu-id="ad4b1-110">Docker 이미지의 인스턴스를 컨테이너에 이러한 구성 요소를 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-110">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="ad4b1-111">운영 체제 선택 (예: Linux 배포 또는 Windows)</span><span class="sxs-lookup"><span data-stu-id="ad4b1-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="ad4b1-112">개발자 (예: 응용 프로그램 이진 파일)가 추가 된 파일</span><span class="sxs-lookup"><span data-stu-id="ad4b1-112">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="ad4b1-113">구성 (예: 환경 설정 및 종속성)</span><span class="sxs-lookup"><span data-stu-id="ad4b1-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="ad4b1-114">Docker에서 실행을 처리 하는 것에 대 한 지침</span><span class="sxs-lookup"><span data-stu-id="ad4b1-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="ad4b1-115">(다음 섹션에서 설명) 프로세스와 Docker를 활용 하는 내부 루프 개발 워크플로를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="ad4b1-116">한 번 수행 해야 하므로 환경을 설정 하는 초기 단계 포함 되지 않았는지를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="ad4b1-117">Visual Studio Code 및 Docker CLI를 사용 하 여 Docker 컨테이너 내에서 단일 앱 빌드</span><span class="sxs-lookup"><span data-stu-id="ad4b1-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="ad4b1-118">앱은 사용자 고유의 서비스와 추가 라이브러리 (종속성)에서 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="ad4b1-119">그림 4-22 일반적으로 각 단계에 자세히 설명 뒤에 Docker 앱을 빌드할 때 수행 해야 하는 기본 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![워크플로 개요: 1 단계-코드를 2 단계-Dockerfile을 4 단계를 사용 하 여 정의 하는 이미지 만들기-docker-compose 파일, 5 단계-실행 컨테이너를 사용 하 여 서비스를 정의 또는 구성 된 앱에 6 단계-앱 테스트, 7 단계-외부 루프 (CI/CD 파이프라인)를 시작 하려면 계속 de 푸시 Dockerfile을 3 단계-작성 veloping 합니다.](./media/image19.png)

<span data-ttu-id="ad4b1-121">**그림 4-22**.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-121">**Figure 4-22**.</span></span> <span data-ttu-id="ad4b1-122">Docker CLI를 사용 하 여 컨테이너 화 된 Docker 응용 프로그램 수명 주기에 대 한 개략적인 워크플로</span><span class="sxs-lookup"><span data-stu-id="ad4b1-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="ad4b1-123">1단계: Visual Studio Code에서 코딩을 시작 하 고 초기 앱/서비스 기준 만들기</span><span class="sxs-lookup"><span data-stu-id="ad4b1-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="ad4b1-124">응용 프로그램을 개발 하는 방법은 Docker 없이 이렇게 하는 방법은 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="ad4b1-125">개발 중에만 배포 및 테스트 하 여 응용 프로그램 또는 서비스 (예: Linux VM 또는 Windows) 로컬 환경에 배치 하는 Docker 컨테이너 내에서 실행 되는 점이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="ad4b1-126">**로컬 환경 설정**</span><span class="sxs-lookup"><span data-stu-id="ad4b1-126">**Setting up your local environment**</span></span>

<span data-ttu-id="ad4b1-127">최신 버전의 Mac 및 Windows 용 Docker 사용 하 여 Docker 응용 프로그램 개발 그 어느 때 보다 훨씬 더 쉽게 하 고 설치는 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-127">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!INFORMATION]
>
> <span data-ttu-id="ad4b1-129">를 Docker에 대 한 Windows 설정에 대 한 이동 <https://docs.docker.com/docker-for-windows/>합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-129">For instructions on setting up Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
><span data-ttu-id="ad4b1-130">Mac 용 Docker 설정 지침에 대 한 <https://docs.docker.com/docker-for-mac/>합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-130">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="ad4b1-131">또한 해야 코드 편집기는 실제로 Docker CLI를 사용 하는 동안 응용 프로그램을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-131">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="ad4b1-132">Microsoft 제공 Mac, Windows, 및 Linux에서 지원 되 고 사용 하 여 IntelliSense를 제공 하는 경량 코드 편집기 인 Visual Studio Code [다양 한 언어에 대 한 지원](https://code.visualstudio.com/docs/languages/overview) (JavaScript,.NET, Go, Java, Ruby, Python 및 가장 최신 언어의 경우) [디버깅](https://code.visualstudio.com/Docs/editor/debugging)를 [Git와 통합](https://code.visualstudio.com/Docs/editor/versioncontrol) 하 고 [확장](https://code.visualstudio.com/docs/extensions/overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-132">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="ad4b1-133">이 편집기는 Linux 및 Mac 개발자를 위한 최적의 선택입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-133">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="ad4b1-134">Windows에도 사용할 수 있습니다 전체 Visual Studio 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-134">In Windows, you also can use the full Visual Studio application.</span></span>

> [!INFORMATION]
>
> <span data-ttu-id="ad4b1-136">를 설치 하는 Visual Studio 코드에 대 한 Windows, Mac 또는 Linux에 대 한 이동 <https://code.visualstudio.com/docs/setup/setup-overview/>합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-136">For instructions on installing Visual Studio Code for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="ad4b1-137">Mac 용 Docker 설정 지침에 대 한 <https://docs.docker.com/docker-for-mac/>합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-137">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="ad4b1-138">Docker 확장을 사용 하 여 Visual Studio Code를 사용 하 여 쉽게 작성 Docker CLI를 사용 하 고 어떤 코드 편집기를 사용 하 여 코드를 작성할 수 있지만 `Dockerfile` 고 `docker-compose.yml` 작업 영역에는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-138">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="ad4b1-139">또한 아래에 있는 Docker CLI를 사용 하 여 Docker 명령을 실행 하려면 Visual Studio 코드 IDE에서 태스크 및 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-139">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="ad4b1-140">VS Code 용 Docker 확장은 다음 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-140">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="ad4b1-141">자동 `Dockerfile` 고 `docker-compose.yml` 파일 생성</span><span class="sxs-lookup"><span data-stu-id="ad4b1-141">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="ad4b1-142">에 대 한 구문 강조 표시 하 고 가리키기 팁 `docker-compose.yml` 고 `Dockerfile` 파일</span><span class="sxs-lookup"><span data-stu-id="ad4b1-142">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="ad4b1-143">IntelliSense (완료)에 대 한 `Dockerfile` 고 `docker-compose.yml` 파일</span><span class="sxs-lookup"><span data-stu-id="ad4b1-143">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="ad4b1-144">에 대 한 lint (오류 및 경고) `Dockerfile` 파일</span><span class="sxs-lookup"><span data-stu-id="ad4b1-144">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="ad4b1-145">가장 일반적인 Docker 명령에 대 한 명령 팔레트 (F1) 통합</span><span class="sxs-lookup"><span data-stu-id="ad4b1-145">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="ad4b1-146">이미지 및 컨테이너를 관리 하기 위한 탐색기 통합</span><span class="sxs-lookup"><span data-stu-id="ad4b1-146">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="ad4b1-147">Azure App Service에 Azure 컨테이너 레지스트리 및 DockerHub에서 이미지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-147">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="ad4b1-148">Docker 확장을 설치 하려면 Ctrl + Shift + P를 눌러 입력 `ext install`, Marketplace 확장 목록을 표시 하려면 확장 설치 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-148">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="ad4b1-149">그런 다음 입력 **docker** 결과 필터링 하 여 다음 그림 4-23에서 언급 했 듯이 Docker 지원 확장을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-149">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![VS Code 용 Docker 확장의 보기입니다.](./media/image20.png)

<span data-ttu-id="ad4b1-151">**그림 4-23**</span><span class="sxs-lookup"><span data-stu-id="ad4b1-151">**Figure 4-23**.</span></span> <span data-ttu-id="ad4b1-152">Visual Studio Code의 Docker 확장을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-152">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="ad4b1-153">2단계: 기존 이미지 (일반 OS 또는.NET Core, Node.js 및 Ruby와 같은 개발 환경)와 관련 된 DockerFile 만들기</span><span class="sxs-lookup"><span data-stu-id="ad4b1-153">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="ad4b1-154">필요는 `DockerFile` 만들려는 사용자 지정 이미지 및 컨테이너 배포 당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-154">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="ad4b1-155">앱 구성 된 단일 사용자 지정 서비스를 단일 필요 `DockerFile`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-155">If your app is made up of a single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="ad4b1-156">앱은 여러 서비스 (예: 마이크로 서비스 아키텍처)으로 구성 해야 하나 있지만 `Dockerfile` 서비스 당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-156">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="ad4b1-157">`DockerFile` 일반적으로 앱 또는 서비스의 루트 폴더에 배치 되 고 Docker 설정 하 고 해당 앱 또는 서비스를 실행 하는 방법을 알 수 있도록 필요한 명령을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-157">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="ad4b1-158">만들 수 있습니다 프로그램 `DockerFile` 코드와 함께 프로젝트에 추가 (.NET Core, node.js 등), 또는 환경에 새로운 인 경우 다음 팁을 살펴보시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-158">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
>
> <span data-ttu-id="ad4b1-159">Docker 확장을 사용 하 여 사용 하는 경우 사용자에 게 안내 합니다 `Dockerfile` 및 `docker-compose.yml` Docker 컨테이너와 관련 된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-159">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="ad4b1-160">결국 이러한 종류의이 도구가 없는 경우 파일 작성 것 이지만 Docker 확장을 사용 하 여 배우를 가속화할 수 있는 좋은 시작 지점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-160">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="ad4b1-161">그림 4-24에서 docker를 어떻게 볼 수 있습니다-작성 파일 VS Code 용 Docker 확장을 사용 하 여 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-161">In Figure 4-24, you can see how a docker-compose file is added by using the Docker Extension for VS Code.</span></span>

![VS Code 용 Docker 확장의 콘솔 보기입니다.](./media/image24.png)

<span data-ttu-id="ad4b1-163">**그림 4-24**</span><span class="sxs-lookup"><span data-stu-id="ad4b1-163">**Figure 4-24**.</span></span> <span data-ttu-id="ad4b1-164">Docker 파일을 사용 하 여 추가 된 **작업 영역 명령에 Docker 추가 파일**</span><span class="sxs-lookup"><span data-stu-id="ad4b1-164">Docker files added using the **Add Docker files to Workspace command**</span></span>

<span data-ttu-id="ad4b1-165">사용할 기본 Docker 이미지를 지정 하는 DockerFile에 추가 하면 (사용 하 여 같은 `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span><span class="sxs-lookup"><span data-stu-id="ad4b1-165">When you add a DockerFile, you specify what base Docker image you’ll be using (like using `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span></span> <span data-ttu-id="ad4b1-166">일반적으로 사용자 지정 이미지에서 공식 리포지토리에서 얻을 수 있는 기본 이미지를 기반으로 빌드할 합니다 [Docker Hub 레지스트리에서](https://hub.docker.com/) (같은 [.NET Core에 대 한 이미지](https://hub.docker.com/_/microsoft-dotnet-core/) 나 [Node.js용](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="ad4b1-166">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="ad4b1-167">***기존 공식 Docker 이미지를 사용 하 여***</span><span class="sxs-lookup"><span data-stu-id="ad4b1-167">***Use an existing official Docker image***</span></span>

<span data-ttu-id="ad4b1-168">버전 번호를 사용 하 여 언어 스택의 공식 리포지토리를 사용 하 여 동일한 언어 기능 (개발, 테스트 및 프로덕션 포함)는 모든 컴퓨터에서 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-168">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="ad4b1-169">다음은.NET Core 컨테이너에 대 한 샘플 DockerFile입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-169">The following is a sample DockerFile for a .NET Core container:</span></span>

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

<span data-ttu-id="ad4b1-170">이 경우에 기준으로 이미지 줄에 따라 공식 ASP.NET Core Docker 이미지 (Linux 및 Windows 용 다중 아키텍처)의 버전 2.1 `FROM mcr.microsoft.com/dotnet/core/aspnet:2.1`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-170">In this case, the image is based on version 2.1 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/core/aspnet:2.1`.</span></span> <span data-ttu-id="ad4b1-171">(이 항목에 대 한 자세한 내용은 참조는 [ASP.NET Core Docker 이미지](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) 페이지와 [.NET Core Docker 이미지](https://hub.docker.com/_/microsoft-dotnet-core/) 페이지).</span><span class="sxs-lookup"><span data-stu-id="ad4b1-171">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) page and the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page).</span></span>

<span data-ttu-id="ad4b1-172">DockerFile에서 Docker (예: 포트 80) 런타임 시 사용 하는 TCP 포트로 수신 하도록 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-172">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80).</span></span>

<span data-ttu-id="ad4b1-173">사용하는 언어 및 프레임워크에 따라 Dockerfile에서 추가 구성 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-173">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="ad4b1-174">예를 들어 합니다 `ENTRYPOINT` 된 선 `["dotnet", "MySingleContainerWebApp.dll"]` .NET Core 응용 프로그램을 실행 하는 Docker에 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-174">For instance, the `ENTRYPOINT` line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="ad4b1-175">SDK 및.NET Core CLI를 사용 중인 경우 (`dotnet CLI`)을 빌드하고.NET 응용 프로그램을 실행 하려면이 설정을 서로 다를 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-175">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="ad4b1-176">여기에서 핵심 ENTRYPOINT 줄 및 기타 설정을 응용 프로그램에 대해 선택한 언어 및 플랫폼에 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-176">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!INFORMATION]
>
> <span data-ttu-id="ad4b1-178">.NET Core 응용 프로그램에 대 한 Docker 이미지 작성 하는 방법에 대 한 자세한 내용은 이동 <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-178">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="ad4b1-179">사용자 고유의 이미지를 작성 하는 방법에 대 한 자세한 내용은 이동 <https://docs.docker.com/engine/tutorials/dockerimages/>합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-179">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="ad4b1-180">**다중 아키텍처 이미지 리포지토리를 사용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ad4b1-180">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="ad4b1-181">리포지토리에 단일 이미지 이름에는 Linux 이미지 및 Windows 이미지 같은 플랫폼 변형을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-181">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="ad4b1-182">이 기능은 여러 플랫폼 (즉, Linux 및 Windows)를 포함 하는 단일 리포지토리를 만들려면 (기본 이미지 작성자) Microsoft 같은 공급 업체입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-182">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="ad4b1-183">예를 들어 합니다 [dotnet/코어/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Docker Hub 레지스트리에서 리포지토리 동일한 이미지 이름을 사용 하 여 Linux 및 Windows Nano Server에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-183">For example, the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="ad4b1-184">끌어오기 합니다 [dotnet/코어/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) 이미지 Windows 호스트에서 Linux 변형을 끌어옵니다 Linux 호스트에서 동일한 이미지 이름을 가져오는 반면 Windows 변형을 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-184">Pulling the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="ad4b1-185">***기본 이미지를 처음부터 만들기***</span><span class="sxs-lookup"><span data-stu-id="ad4b1-185">***Create your base image from scratch***</span></span>

<span data-ttu-id="ad4b1-186">이 항목에 설명 된 대로 처음부터 사용자 고유의 Docker 기본 이미지를 만들 수 있습니다 [문서](https://docs.docker.com/engine/userguide/eng-image/baseimages/) Docker에서.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-186">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="ad4b1-187">이 시나리오는 Docker를 사용 하 여 잘 모르는 경우 기본 이미지의 특정 비트를 설정 하려는 경우 수행할 수 있습니다 적합 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-187">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="ad4b1-188">3단계: 에 서비스를 포함 하 여 사용자 지정 Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="ad4b1-188">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="ad4b1-189">앱을 구성 하는 각 사용자 지정 서비스에 대 한 관련된 이미지를 만드는 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-189">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="ad4b1-190">단일 서비스 또는 웹 앱의 앱 옵션을 구성 된 경우에 단일 이미지를 방금 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-190">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
>
> <span data-ttu-id="ad4b1-191">소스 코드를 Git 리포지토리에 푸시할 (연속 통합), 글로벌 환경에서 이미지를 만들 수는에서 때마다 이미지 자동화 된 빌드 프로세스에 의해 만들어집니다 계정 "외부 루프 DevOps 워크플로의"를 고려 하는 경우에 소스 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-191">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="ad4b1-192">그러나 Docker 응용 프로그램은 실제로 제대로 작동 하는지 확인 (Git 등). 소스 제어 시스템에 제대로 작동 하지 않을 수도 코드를 푸시 하지는 않도록 해야 것으로 간주 해당 외부 반복 경로를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-192">But before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="ad4b1-193">따라서 각 개발자는 먼저 로컬에서 테스트 및 개발 하는 완전 한 기능을 푸시하거나 원본 제어 시스템에 변경 하려는 될 때까지 계속 전체 내부 루프 프로세스를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-193">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="ad4b1-194">이미지를 만드는에서 DockerFile을 사용 하 여 로컬 환경에서 사용할 수 그림 4-25에서 설명한 것 처럼 docker build 명령을 (실행할 수도 있습니다 `docker-compose up --build` 여러 컨테이너/서비스에서 구성 된 응용 프로그램에 대 한).</span><span class="sxs-lookup"><span data-stu-id="ad4b1-194">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-25 (you also can run `docker-compose up --build` for applications composed by several containers/services).</span></span>

![이미지를 다운로드 진행률 표시, docker-compose build의 콘솔 출력입니다.](./media/image25.png)

<span data-ttu-id="ad4b1-196">**그림 4-25**</span><span class="sxs-lookup"><span data-stu-id="ad4b1-196">**Figure 4-25**.</span></span> <span data-ttu-id="ad4b1-197">실행 중인 docker 빌드</span><span class="sxs-lookup"><span data-stu-id="ad4b1-197">Running docker build</span></span>

<span data-ttu-id="ad4b1-198">직접 실행 하는 대신 필요에 따라 `docker build` 프로젝트 폴더에서 먼저 생성할 수 있습니다 배포 가능 폴더 실행을 사용 하 여 필요한.NET 라이브러리를 사용 하 여 `dotnet publish` 명령을 실행 하 고 그런 다음 `docker build`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-198">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="ad4b1-199">이 예제에서는 이름을 사용 하 여 Docker 이미지를 만듭니다 `cesardl/netcore-webapi-microservice-docker:first` (`:first` 같은 특정 버전 태그는).</span><span class="sxs-lookup"><span data-stu-id="ad4b1-199">This example creates a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first` (`:first` is a tag, like a specific version).</span></span> <span data-ttu-id="ad4b1-200">여러 컨테이너를 사용 하 여 구성 된 Docker 응용 프로그램에 대해 만들어야 하는 각 사용자 지정 이미지에 대해이 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-200">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="ad4b1-201">있습니다 명령을 찾을 수 있습니다 기존 이미지 로컬 리포지토리 (개발 컴퓨터)에서 docker를 사용 하 여 이미지, 그림 4-26에서와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-201">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-26.</span></span>

![콘솔 출력에서 명령은 docker 이미지를 기존 이미지를 표시 합니다.](./media/image26.png)

<span data-ttu-id="ad4b1-203">**그림 4-26**.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-203">**Figure 4-26**.</span></span> <span data-ttu-id="ad4b1-204">Docker 이미지를 사용 하 여 보기 기존 이미지</span><span class="sxs-lookup"><span data-stu-id="ad4b1-204">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="ad4b1-205">4단계: 여러 서비스를 사용 하 여 구성 된 Docker 앱을 빌드할 때 docker-compose.yml에서 서비스 정의</span><span class="sxs-lookup"><span data-stu-id="ad4b1-205">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="ad4b1-206">사용 하 여는 `docker-compose.yml` 파일에서 다음 단계 섹션에서 설명한 배포 명령을 사용 하 여 구성된 된 응용 프로그램으로 배포할 관련된 서비스 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-206">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="ad4b1-207">해당 파일에서 기본 또는 루트 솔루션 폴더 만들기 이 표시 된 유사한 콘텐츠 있어야 `docker-compose.yml` 파일:</span><span class="sxs-lookup"><span data-stu-id="ad4b1-207">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

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

<span data-ttu-id="ad4b1-208">이 경우에이 파일은 두 서비스를 정의 합니다. (사용자 지정 서비스) 웹 서비스 및 redis 서비스 (인기 있는 캐시 서비스).</span><span class="sxs-lookup"><span data-stu-id="ad4b1-208">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="ad4b1-209">각각에 대 한 구체적인 Docker 이미지를 사용 해야 하므로 각 서비스는 컨테이너로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-209">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="ad4b1-210">이 특정 웹 서비스에 대 한 이미지는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-210">For this particular web service, the image will need to do the following:</span></span>

- <span data-ttu-id="ad4b1-211">현재 디렉터리에서 DockerFile에서 빌드</span><span class="sxs-lookup"><span data-stu-id="ad4b1-211">Build from the DockerFile in the current directory</span></span>

- <span data-ttu-id="ad4b1-212">노출된 된 포트 80 포트 81 호스트 컴퓨터에서 컨테이너에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-212">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

- <span data-ttu-id="ad4b1-213">이미지를 다시 빌드하지 않고 코드를 수정할 수 있도록 컨테이너 내의 모든 코드를 삽입 하려면 호스트에서 프로젝트 디렉터리 탑재</span><span class="sxs-lookup"><span data-stu-id="ad4b1-213">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

- <span data-ttu-id="ad4b1-214">웹 서비스는 redis 서비스에 연결</span><span class="sxs-lookup"><span data-stu-id="ad4b1-214">Link the web service to the redis service</span></span>

<span data-ttu-id="ad4b1-215">Redis 서비스에서 사용 하는 [최신 공개 redis 이미지](https://hub.docker.com/_/redis/) Docker Hub 레지스트리에서 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-215">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="ad4b1-216">[redis](https://redis.io/) 는 인기 있는 캐시 시스템 서버쪽 응용 프로그램에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-216">[redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="ad4b1-217">5단계: 빌드 및 Docker 앱 실행</span><span class="sxs-lookup"><span data-stu-id="ad4b1-217">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="ad4b1-218">앱에 단일 컨테이너만 경우 Docker 호스트 (VM 또는 물리적 서버)에 배포 하 여 실행 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-218">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="ad4b1-219">그러나 경우 앱은 여러 서비스로 구성 된, 해야 *구성*도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-219">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="ad4b1-220">다양 한 옵션을 확인해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-220">Let's see the different options.</span></span>

<span data-ttu-id="ad4b1-221">***옵션 a: 단일 컨테이너 또는 서비스를 실행 합니다.***</span><span class="sxs-lookup"><span data-stu-id="ad4b1-221">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="ad4b1-222">여기에 나와 있는 것 처럼 docker run 명령을 사용 하 여 Docker 이미지를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-222">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="ad4b1-223">이 특정 배포에 대 한 내부 포트 5000에 포트 80에 전송 된 요청 리디렉션 수 됩니다 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-223">For this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="ad4b1-224">이제 응용 프로그램 호스트 수준에서 80 외부 포트에서 수신 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-224">Now the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="ad4b1-225">***옵션 b: 작성 및 다중 컨테이너 응용 프로그램을 실행 합니다.***</span><span class="sxs-lookup"><span data-stu-id="ad4b1-225">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="ad4b1-226">대부분의 엔터프라이즈 시나리오에서 Docker 응용 프로그램을 여러 서비스로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-226">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="ad4b1-227">이러한 경우에 실행할 수 있습니다는 `docker-compose up` 수 이전에 만든 docker compose.yml 파일을 사용 하는 명령 (그림 4-27).</span><span class="sxs-lookup"><span data-stu-id="ad4b1-227">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="ad4b1-228">이 명령을 실행의 모든 해당 관련된 컨테이너를 사용 하 여 구성 된 응용 프로그램을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-228">Running this command deploys a composed application with all of its related containers.</span></span>

![콘솔 출력에서의 docker compose up 명령을 합니다.](./media/image27.png)

<span data-ttu-id="ad4b1-230">**그림 4-27**.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-230">**Figure 4-27**.</span></span> <span data-ttu-id="ad4b1-231">"Docker compose 구성" 명령을 실행 한 결과</span><span class="sxs-lookup"><span data-stu-id="ad4b1-231">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="ad4b1-232">실행 한 후 `docker-compose up`, VM 표현에서에서 그림 4-28에서와 같이 응용 프로그램 및 해당 관련된 컨테이너에 Docker 호스트에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-232">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![다중 컨테이너 응용 프로그램을 실행 하는 VM.](./media/image28.png)

<span data-ttu-id="ad4b1-234">**그림 4-28**.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-234">**Figure 4-28**.</span></span> <span data-ttu-id="ad4b1-235">Docker 컨테이너가 배포된 VM</span><span class="sxs-lookup"><span data-stu-id="ad4b1-235">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="ad4b1-236">6단계: (로컬 CD VM)에서 로컬로 Docker 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="ad4b1-236">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="ad4b1-237">이 단계는 고 앱이 수행 되는 내용에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-237">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="ad4b1-238">간단한.NET Core에서 Web API "Hello World" 단일 컨테이너 또는 서비스로 배포는 DockerFile에서 지정 된 TCP 포트를 제공 하 여 서비스에 액세스할 수만 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-238">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="ad4b1-239">서비스를 이동 하려면 localhost에 설정 되지 않은 경우는이 명령을 사용 하 여 컴퓨터에 대 한 IP 주소를 찾으려면:</span><span class="sxs-lookup"><span data-stu-id="ad4b1-239">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

<span data-ttu-id="ad4b1-240">Docker 호스트에서 브라우저를 열고 해당 사이트로; 이동 그림 4-29에 설명 된 대로 앱/서비스를 실행 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-240">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Localhost/API/값 응답의 브라우저 보기입니다.](./media/image29.png)

<span data-ttu-id="ad4b1-242">**그림 4-29**.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-242">**Figure 4-29**.</span></span> <span data-ttu-id="ad4b1-243">Localhost를 사용 하 여 로컬로 Docker 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="ad4b1-243">Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="ad4b1-244">사용 하 여 배포 된 방법 이기 때문에 포트 80을 사용 하지만 내부 포트 5000에 리디렉션되는 참고 `docker run`앞에서 설명한 대로, 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-244">Note that it's using port 80, but internally it's being redirected to port 5000, because that's how it was deployed with `docker run`, as explained earlier.</span></span>

<span data-ttu-id="ad4b1-245">터미널에서 CURL을 사용 하 여이 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-245">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="ad4b1-246">Windows에서 Docker 설치에서 기본 IP 경우 10.0.75.1, 그림 4-30에서 언급 했 듯이</span><span class="sxs-lookup"><span data-stu-id="ad4b1-246">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-30.</span></span>

![콘솔에서 출력 된 http://10.0.75.1/API/values curl을 사용 하 여](./media/image30.png)

<span data-ttu-id="ad4b1-248">**그림 4-30**.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-248">**Figure 4-30**.</span></span> <span data-ttu-id="ad4b1-249">CURL을 사용 하 여 로컬로 Docker 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="ad4b1-249">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="ad4b1-250">**Docker에서 실행 되는 컨테이너 디버깅**</span><span class="sxs-lookup"><span data-stu-id="ad4b1-250">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="ad4b1-251">Visual Studio Code는 Node.js 및.NET Core 컨테이너 등의 다른 플랫폼을 사용 하는 경우 디버깅 Docker를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-251">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="ad4b1-252">또한 디버깅할 수 있습니다 Docker에서.NET Core 또는.NET Framework 컨테이너 Visual Studio에 대 한 Windows 또는 Mac을 사용 하는 경우 다음 섹션에 설명 된 대로.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-252">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!INFORMATION]
>
> <span data-ttu-id="ad4b1-254">로 Node.js Docker 컨테이너를 디버깅 하는 방법에 대 한 자세한 내용은 <https://blog.docker.com/2016/07/live-debugging-docker/> 고 <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4b1-254">To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ad4b1-255">[이전](docker-apps-development-environment.md)
>[다음](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="ad4b1-255">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
