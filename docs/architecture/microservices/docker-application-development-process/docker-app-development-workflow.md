---
title: Docker 앱에 대한 개발 워크플로
description: Docker 기반 애플리케이션 개발 워크플로의 세부 정보를 확인하세요. 먼저 단계별로 살펴보고 Dockerfile 최적화에 대한 세부 정보를 알아본 후 Visual Studio 사용 시 사용 가능한 간소화된 워크플로를 마지막으로 확인하세요.
ms.date: 01/30/2020
ms.openlocfilehash: c58ea2436027968143777a19286a1a0a72107717
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401510"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="3e18b-104">Docker 앱에 대한 개발 워크플로</span><span class="sxs-lookup"><span data-stu-id="3e18b-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="3e18b-105">애플리케이션 개발 수명 주기는 개발자의 컴퓨터에서 시작되며, 여기서 개발자는 선호하는 언어를 사용하여 로컬로 애플리케이션 코드를 작성하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-105">The application development life cycle starts at your computer, as a developer, where you code the application using your preferred language and test it locally.</span></span> <span data-ttu-id="3e18b-106">개발자가 어떤 언어, 프레임워크, 플랫폼을 선택하든 이 워크플로를 사용하면 개발자는 항상 Docker 컨테이너를 로컬에서 개발하고 테스트하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-106">With this workflow, no matter which language, framework, and platform you choose, you're always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="3e18b-107">각 컨테이너(Docker 이미지의 인스턴스)는 다음 구성 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-107">Each container (an instance of a Docker image) includes the following components:</span></span>

- <span data-ttu-id="3e18b-108">운영 체제 선택(예: Linux 배포판, Windows Nano Server 또는 Windows Server Core).</span><span class="sxs-lookup"><span data-stu-id="3e18b-108">An operating system selection, for example, a Linux distribution, Windows Nano Server, or Windows Server Core.</span></span>

- <span data-ttu-id="3e18b-109">개발 중에 추가된 파일(예: 소스 코드 및 애플리케이션 바이너리).</span><span class="sxs-lookup"><span data-stu-id="3e18b-109">Files added during development, for example, source code and application binaries.</span></span>

- <span data-ttu-id="3e18b-110">구성 정보(예: 환경 설정 및 종속성).</span><span class="sxs-lookup"><span data-stu-id="3e18b-110">Configuration information, such as environment settings and dependencies.</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="3e18b-111">Docker 컨테이너 기반 애플리케이션을 개발하기 위한 워크플로</span><span class="sxs-lookup"><span data-stu-id="3e18b-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="3e18b-112">이 섹션에서는 Docker 컨테이너 기반 애플리케이션에 대한 *내부 루프* 개발 워크플로를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="3e18b-113">내부 루프 워크플로란 프로덕션 배포까지 포함되는 광범위한 DevOps 워크플로를 고려하지 않고 개발자의 컴퓨터에서 수행되는 개발 작업에만 집중한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-113">The inner-loop workflow means it's not considering the broader DevOps workflow, which can include up to production deployment, and just focuses on the development work done on the developer's computer.</span></span> <span data-ttu-id="3e18b-114">환경을 설정하는 초기 단계는 한 번만 수행되므로 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-114">The initial steps to set up the environment aren't included, since those steps are done only once.</span></span>

<span data-ttu-id="3e18b-115">애플리케이션은 개발자 고유의 서비스와 추가 라이브러리(종속성)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="3e18b-116">다음은 그림 5-1처럼 일반적으로 Docker 애플리케이션을 빌드할 때 수행하는 기본 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

:::image type="complex" source="./media/docker-app-development-workflow/life-cycle-containerized-apps-docker-cli.png" alt-text="컨테이너화된 앱을 만드는 데 필요한 7가지 단계를 보여 주는 다이어그램":::
<span data-ttu-id="3e18b-118">Docker 앱 개발 프로세스: 1 - 앱 코딩, 2 - Dockerfile 작성, 3 - Dockerfile에 정의된 이미지 만들기, 4 - (선택 사항) docker-compose.yml 파일에 서비스 작성, 5 - container 또는 docker-compose 앱 실행, 6 - 앱 또는 마이크로 서비스 테스트, 7 - 리포지토리에 푸시하고 반복.</span><span class="sxs-lookup"><span data-stu-id="3e18b-118">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span>
:::image-end:::

<span data-ttu-id="3e18b-119">**그림 5-1.**</span><span class="sxs-lookup"><span data-stu-id="3e18b-119">**Figure 5-1.**</span></span> <span data-ttu-id="3e18b-120">Docker 컨테이너화된 앱 개발을 위한 단계별 워크플로</span><span class="sxs-lookup"><span data-stu-id="3e18b-120">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="3e18b-121">이 섹션에서는 전체 프로세스를 자세히 설명하고 모든 주요 단계는 Visual Studio 환경을 중심으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-121">In this section, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="3e18b-122">편집기/CLI 개발 접근 방식을 사용하는 경우(예: macOS 또는 Windows에서 Visual Studio Code와 Docker CLI 사용) 일반적으로 Visual Studio를 사용할 때보다 모든 단계를 더 자세히 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-122">When you're using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you're using Visual Studio.</span></span> <span data-ttu-id="3e18b-123">CLI 환경에서 작업하는 방법에 대한 자세한 내용은 eBook [컨테이너화된 Docker 애플리케이션 수명 주기와 Microsoft 플랫폼 및 도구](https://aka.ms/dockerlifecycleebook/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e18b-123">For more information about working in a CLI environment, see the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="3e18b-124">Visual Studio 2019를 사용하는 경우 이러한 단계의 상당 부분이 자동으로 처리되므로 생산성이 대폭 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-124">When you're using Visual Studio 2019, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="3e18b-125">Visual Studio 2019를 사용하고 다중 컨테이너 애플리케이션을 대상으로 하는 경우에 특히 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-125">This is especially true when you're using Visual Studio 2019 and targeting multi-container applications.</span></span> <span data-ttu-id="3e18b-126">예를 들어 마우스 클릭 한 번이면 Visual Studio가 애플리케이션의 구성을 사용하여 `Dockerfile` 및 `docker-compose.yml` 파일을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-126">For instance, with just one mouse click, Visual Studio adds the `Dockerfile` and `docker-compose.yml` file to your projects with the configuration for your application.</span></span> <span data-ttu-id="3e18b-127">Visual Studio에서 애플리케이션을 실행하면 Visual Studio가 Docker 이미지를 작성하고 Docker에서 바로 다중 컨테이너 애플리케이션을 실행하며, 심지어 여러 컨테이너를 한꺼번에 디버깅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-127">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="3e18b-128">이러한 기능은 개발 속도를 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-128">These features will boost your development speed.</span></span>

<span data-ttu-id="3e18b-129">그러나 Visual Studio가 이러한 단계를 자동으로 처리한다고 해서 Docker 내부에서 발생하는 일에 대해 전혀 몰라도 된다는 뜻은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-129">However, just because Visual Studio makes those steps automatic doesn't mean that you don't need to know what's going on underneath with Docker.</span></span> <span data-ttu-id="3e18b-130">따라서 다음 지침에서는 각 단계를 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-130">Therefore, the following guidance details every step.</span></span>

![1단계의 이미지입니다.](./media/docker-app-development-workflow/step-1-code-your-app.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="3e18b-132">1단계:</span><span class="sxs-lookup"><span data-stu-id="3e18b-132">Step 1.</span></span> <span data-ttu-id="3e18b-133">코딩을 시작하고 초기 애플리케이션 또는 서비스 기준 만들기</span><span class="sxs-lookup"><span data-stu-id="3e18b-133">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="3e18b-134">Docker 애플리케이션 개발은 Docker 없이 애플리케이션을 개발하는 방법과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-134">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="3e18b-135">다른 점은 Docker를 개발하는 동안 로컬 환경의 Docker 컨테이너 내에서 실행되는 애플리케이션을 배포하고 테스트한다는 점입니다(Docker를 사용하는 Linux VM 환경 또는 Windows 컨테이너를 사용하는 Windows 환경).</span><span class="sxs-lookup"><span data-stu-id="3e18b-135">The difference is that while developing for Docker, you're deploying and testing your application or services running within Docker containers in your local environment (either a Linux VM setup by Docker or directly Windows if using Windows Containers).</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="3e18b-136">Visual Studio를 사용하여 로컬 환경 설정</span><span class="sxs-lookup"><span data-stu-id="3e18b-136">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="3e18b-137">시작하려면 다음 지침에 설명된 대로 Windows용 [Docker CE(Community Edition)](https://docs.docker.com/docker-for-windows/)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-137">To begin, make sure you have [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="3e18b-138">Windows용 Docker CE 시작</span><span class="sxs-lookup"><span data-stu-id="3e18b-138">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="3e18b-139">또한 그림 5-2에서 표시된 대로 **.NET Core 플랫폼 간 개발** 워크로드가 설치된 Visual Studio 2019 버전 16.4 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-139">In addition, you need Visual Studio 2019 version 16.4 or later, with the **.NET Core cross-platform development** workload installed, as shown in Figure 5-2.</span></span>

![.NET Core 플랫폼 간 개발 선택의 스크린샷](./media/docker-app-development-workflow/dotnet-core-cross-platform-development.png)

<span data-ttu-id="3e18b-141">**그림 5-2**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-141">**Figure 5-2**.</span></span> <span data-ttu-id="3e18b-142">Visual Studio 2019 설정 중 **.NET Core 플랫폼 간 개발** 워크로드 선택</span><span class="sxs-lookup"><span data-stu-id="3e18b-142">Selecting the **.NET Core cross-platform development** workload during Visual Studio 2019 setup</span></span>

<span data-ttu-id="3e18b-143">심지어 애플리케이션에서 Docker를 사용하도록 설정하고 Docker에 배포 및 테스트하기 전에도 일반 .NET에서 애플리케이션 코딩을 시작할 수 있습니다(컨테이너를 사용하려는 경우 일반적으로 .NET Core).</span><span class="sxs-lookup"><span data-stu-id="3e18b-143">You can start coding your application in plain .NET (usually in .NET Core if you're planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="3e18b-144">하지만 되도록이면 빨리 Docker에서 작업을 시작하는 것이 좋습니다. 실제로 사용하게 될 환경이고 문제를 최대한 신속하게 검색할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-144">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="3e18b-145">이렇게 하도록 권장하는 이유는 Visual Studio를 사용하면 거의 투명한 것처럼 느껴지는 Docker를 손쉽게 작업할 수 있기 때문입니다. 가장 대표적인 예로 Visual Studio에서 다중 컨테이너 애플리케이션을 디버깅하는 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-145">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3e18b-146">추가 자료</span><span class="sxs-lookup"><span data-stu-id="3e18b-146">Additional resources</span></span>

- <span data-ttu-id="3e18b-147">**Windows용 Docker CE 시작** </span><span class="sxs-lookup"><span data-stu-id="3e18b-147">**Get started with Docker CE for Windows** </span></span>\
  <https://docs.docker.com/docker-for-windows/>

- <span data-ttu-id="3e18b-148">**Visual Studio 2019** </span><span class="sxs-lookup"><span data-stu-id="3e18b-148">**Visual Studio 2019** </span></span>\
  [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

![2단계의 이미지입니다.](./media/docker-app-development-workflow/step-2-write-dockerfile.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="3e18b-150">2단계.</span><span class="sxs-lookup"><span data-stu-id="3e18b-150">Step 2.</span></span> <span data-ttu-id="3e18b-151">기존 .NET 기본 이미지와 관련된 Dockerfile 만들기</span><span class="sxs-lookup"><span data-stu-id="3e18b-151">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="3e18b-152">Visual Studio에서 자동으로 배포하든 아니면 Docker CLI(docker run 및 docker-compose 명령)를 사용하여 수동으로 배포하든, 빌드하려는 각 사용자 지정 이미지에 대한 Dockerfile과 배포할 각 컨테이너에 대한 Dockerfile이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-152">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="3e18b-153">애플리케이션이 단일 사용자 지정 서비스를 포함하는 경우 단일 Dockerfile이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-153">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="3e18b-154">애플리케이션이 여러 서비스를 포함하는 경우(마이크로 서비스 아키텍처처럼) 서비스마다 하나의 Dockerfile이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-154">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="3e18b-155">Dockerfile은 애플리케이션 또는 서비스의 루트 폴더에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-155">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="3e18b-156">컨테이너의 애플리케이션 또는 서비스를 설정하고 실행하는 방법을 Docker에 알려주는 명령을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-156">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="3e18b-157">코드를 사용하여 수동으로 Dockerfile을 만들어서 .NET 종속성과 함께 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-157">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="3e18b-158">Visual Studio와 Docker용 도구를 사용하면 마우스 클릭 몇 번으로 이 작업을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-158">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="3e18b-159">Visual Studio 2019에서 새 프로젝트를 만들 때 그림 5-3에서 표시된 대로 **Docker 지원 사용**이라는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-159">When you create a new project in Visual Studio 2019, there's an option named **Enable Docker Support**, as shown in Figure 5-3.</span></span>

![Docker 지원 사용 확인란을 보여 주는 스크린샷](./media/docker-app-development-workflow/enable-docker-support-check-box.png)

<span data-ttu-id="3e18b-161">**그림 5-3**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-161">**Figure 5-3**.</span></span> <span data-ttu-id="3e18b-162">Visual Studio 2019에서 새 ASP.NET Core 프로젝트를 만들 때 Docker 지원 활성화</span><span class="sxs-lookup"><span data-stu-id="3e18b-162">Enabling Docker Support when creating a new ASP.NET Core project in Visual Studio 2019</span></span>

<span data-ttu-id="3e18b-163">그림 5-4에 표시된 대로 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고, **추가** > **Docker 지원...** 을 선택하여 기존 ASP.NET Core 웹앱 프로젝트에서 Docker 지원을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-163">You can also enable Docker support on an existing ASP.NET Core web app project by right-clicking the project in **Solution Explorer** and selecting **Add** > **Docker Support...**, as shown in Figure 5-4.</span></span>

![추가 메뉴의 Docker 지원 옵션을 보여 주는 스크린샷](./media/docker-app-development-workflow/add-docker-support-option.png)

<span data-ttu-id="3e18b-165">**그림 5-4**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-165">**Figure 5-4**.</span></span> <span data-ttu-id="3e18b-166">기존 Visual Studio 2019 프로젝트에서 Docker 지원을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="3e18b-166">Enabling Docker support in an existing Visual Studio 2019 project</span></span>

<span data-ttu-id="3e18b-167">이 작업은 필수 구성을 포함한 프로젝트에 *Dockerfile*을 추가하고 ASP.NET Core 프로젝트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-167">This action adds a *Dockerfile* to the project with the required configuration, and is only available on ASP.NET Core projects.</span></span>

<span data-ttu-id="3e18b-168">마찬가지로 Visual Studio는 **추가 > 컨테이너 오케스트레이터 지원...** 옵션을 사용하여 전체 솔루션용 `docker-compose.yml` 파일을 추가할 수도 있습니다. 4단계에서 이 옵션을 더 자세히 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-168">In a similar fashion, Visual Studio can also add a `docker-compose.yml` file for the whole solution with the option **Add > Container Orchestrator Support...**. In step 4, we'll explore this option in greater detail.</span></span>

### <a name="using-an-existing-official-net-docker-image"></a><span data-ttu-id="3e18b-169">기존의 공식 .NET Docker 이미지 사용</span><span class="sxs-lookup"><span data-stu-id="3e18b-169">Using an existing official .NET Docker image</span></span>

<span data-ttu-id="3e18b-170">일반적으로 [Docker Hub](https://hub.docker.com/) 레지스트리 같은 공식 리포지토리에서 얻을 수 있는 기본 이미지를 기반으로 컨테이너에 대한 사용자 지정 이미지를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-170">You usually build a custom image for your container on top of a base image you get from an official repository like the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="3e18b-171">Visual Studio에서 Docker 지원을 사용하도록 설정하면 내부에서 이와 같은 일이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-171">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="3e18b-172">Dockerfile은 기존 `dotnet/core/aspnet` 이미지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-172">Your Dockerfile will use an existing `dotnet/core/aspnet` image.</span></span>

<span data-ttu-id="3e18b-173">앞에서 선택하는 프레임워크 및 운영 체제에 따라 어떤 Docker 이미지와 리포지토리를 사용할 수 있는지 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-173">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="3e18b-174">예를 들어 ASP.NET Core(Linux 또는 Windows)를 사용하려는 경우 사용할 이미지는 `mcr.microsoft.com/dotnet/core/aspnet:3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-174">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is `mcr.microsoft.com/dotnet/core/aspnet:3.1`.</span></span> <span data-ttu-id="3e18b-175">따라서 컨테이너에 사용할 기본 Docker 이미지만 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-175">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="3e18b-176">이렇게 하려면 `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1`을 Dockerfile에 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="3e18b-176">You do that by adding `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1` to your Dockerfile.</span></span> <span data-ttu-id="3e18b-177">이 작업은 Visual Studio가 자동으로 수행하지만, 버전을 업데이트하려면 직접 이 값을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-177">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="3e18b-178">버전 번호가 있는 Docker Hub의 공식 .NET 이미지 리포지토리를 사용하면 모든 컴퓨터에서(개발, 테스트 및 프로덕션 포함) 동일한 언어 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-178">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="3e18b-179">다음 예제에서는 ASP.NET Core 컨테이너에 대한 샘플 Dockerfile을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-179">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
ARG source
WORKDIR /app
EXPOSE 80
COPY ${source:-obj/Docker/publish} .
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="3e18b-180">이 예에서 이미지는 공식 ASP.NET Core Docker 버전 3.1 이미지(Linux 및 Windows용 다중 아키텍처)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-180">In this case, the image is based on version 3.1 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="3e18b-181">이것은 설정 `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-181">This is the setting `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1`.</span></span> <span data-ttu-id="3e18b-182">(이 기본 이미지에 대한 자세한 내용은 [.NET Core Docker 이미지](https://hub.docker.com/_/microsoft-dotnet-core/) 페이지를 참조하세요.) 또한 Dockerfile에서, 런타임에 사용할 TCP 포트(이 예에서는 EXPOSE 설정을 사용하여 구성한 대로 포트 80)에서 수신 대기하라고 Docker에 지시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-182">(For more information about this base image, see the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="3e18b-183">사용하는 언어 및 프레임워크에 따라 Dockerfile에서 추가 구성 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-183">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="3e18b-184">예를 들어 `["dotnet", "MySingleContainerWebApp.dll"]`이 포함된 ENTRYPOINT 줄은 Docker에 .NET Core 애플리케이션을 실행하라고 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-184">For instance, the ENTRYPOINT line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="3e18b-185">SDK 및 .NET Core CLI(dotnet CLI)를 사용하여 .NET 애플리케이션을 빌드하고 실행하는 경우 이 설정이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-185">If you're using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="3e18b-186">결론적으로 ENTRYPOINT 줄 및 기타 설정은 개발자가 애플리케이션에 대해 선택하는 언어 및 플랫폼에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-186">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3e18b-187">추가 자료</span><span class="sxs-lookup"><span data-stu-id="3e18b-187">Additional resources</span></span>

- <span data-ttu-id="3e18b-188">**.NET Core 애플리케이션에 대한 Docker 이미지 작성** </span><span class="sxs-lookup"><span data-stu-id="3e18b-188">**Building Docker Images for .NET Core Applications** </span></span>\
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)

- <span data-ttu-id="3e18b-189">**고유의 이미지 빌드**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-189">**Build your own image**.</span></span> <span data-ttu-id="3e18b-190">공식 Docker 설명서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-190">In the official Docker documentation.</span></span>\
  <https://docs.docker.com/engine/tutorials/dockerimages/>

- <span data-ttu-id="3e18b-191">**Staying up-to-date with .NET Container Images(.NET 컨테이너 이미지를 최신 상태로 유지)**  </span><span class="sxs-lookup"><span data-stu-id="3e18b-191">**Staying up-to-date with .NET Container Images** </span></span>\
  <https://devblogs.microsoft.com/dotnet/staying-up-to-date-with-net-container-images/>

- <span data-ttu-id="3e18b-192">**Using .NET and Docker Together(.NET 및 Docker 함께 사용) - DockerCon 2018 업데이트** </span><span class="sxs-lookup"><span data-stu-id="3e18b-192">**Using .NET and Docker Together - DockerCon 2018 Update** </span></span>\
  <https://devblogs.microsoft.com/dotnet/using-net-and-docker-together-dockercon-2018-update/>

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="3e18b-193">다중 아키텍처 이미지 리포지토리 사용</span><span class="sxs-lookup"><span data-stu-id="3e18b-193">Using multi-arch image repositories</span></span>

<span data-ttu-id="3e18b-194">단일 리포지토리는 Linux 이미지 및 Windows 이미지 같은 플랫폼 변형을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-194">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="3e18b-195">이 기능을 통해 Microsoft 같은 공급업체(기본 이미지 작성자)는 여러 플랫폼(즉, Linux 및 Windows)을 처리하는 단일 리포지토리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-195">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="3e18b-196">예를 들어 Docker Hub 레지스트리에서 제공되는 [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) 리포지토리는 동일한 리포지토리 이름을 사용하여 Linux 및 Windows Nano Server에 대한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-196">For example, the [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="3e18b-197">태그를 지정하는 경우 다음과 같이 명시적인 플랫폼을 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-197">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

- `mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim` \
  <span data-ttu-id="3e18b-198">대상: Linux의 .NET Core 3.1 런타임 전용</span><span class="sxs-lookup"><span data-stu-id="3e18b-198">Targets: .NET Core 3.1 runtime-only on Linux</span></span>

- `mcr.microsoft.com/dotnet/core/aspnet:3.1-nanoserver-1909` \
  <span data-ttu-id="3e18b-199">대상: Windows Nano Server의 .NET Core 3.1 런타임 전용</span><span class="sxs-lookup"><span data-stu-id="3e18b-199">Targets: .NET Core 3.1 runtime-only on Windows Nano Server</span></span>

<span data-ttu-id="3e18b-200">그러나 동일한 이미지 이름을 지정하고 동일한 태그를 지정하는 경우 다중 아키텍처 이미지(예: `aspnet` 이미지)는 다음 예제와 같이 사용자가 배포하는 Docker 호스트 OS에 따라 Linux 또는 Windows 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-200">But, if you specify the same image name, even with the same tag, the multi-arch images (like the `aspnet` image) will use the Linux or Windows version depending on the Docker host OS you're deploying, as shown in the following example:</span></span>

- `mcr.microsoft.com/dotnet/core/aspnet:3.1` \
  <span data-ttu-id="3e18b-201">다중 아키텍처: Docker 호스트OS에 따라 Linux 또는 Windows Nano Server의 .NET Core 3.1 런타임 전용</span><span class="sxs-lookup"><span data-stu-id="3e18b-201">Multi-arch: .NET Core 3.1 runtime-only on Linux or Windows Nano Server depending on the Docker host OS</span></span>

<span data-ttu-id="3e18b-202">이와 같이, Windows 호스트에서 이미지를 끌어오면 Windows 변형을 끌어오고, Linux 호스트에서 동일한 이미지 이름을 끌어오면 Linux 변형을 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-202">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="multi-stage-builds-in-dockerfile"></a><span data-ttu-id="3e18b-203">Dockerfile의 다단계 빌드</span><span class="sxs-lookup"><span data-stu-id="3e18b-203">Multi-stage builds in Dockerfile</span></span>

<span data-ttu-id="3e18b-204">Dockerfile은 배치 스크립트와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-204">The Dockerfile is similar to a batch script.</span></span> <span data-ttu-id="3e18b-205">명령줄에서 머신을 설정해야 하는 경우에 수행하는 작업과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-205">Similar to what you would do if you had to set up the machine from the command line.</span></span>

<span data-ttu-id="3e18b-206">초기 컨텍스트를 설정하는 기본 이미지로 시작되고, 호스트 OS를 기반으로 하는 시작 파일 시스템과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-206">It starts with a base image that sets up the initial context, it's like the startup filesystem, that sits on top of the host OS.</span></span> <span data-ttu-id="3e18b-207">OS는 아니지만 컨테이너 내 “OS”처럼 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-207">It's not an OS, but you can think of it like "the" OS inside the container.</span></span>

<span data-ttu-id="3e18b-208">각 명령줄을 실행하면 파일 시스템에 이전 레이어에서 변경된 새 레이어가 생성되므로 이를 결합하면 결과 파일 시스템이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-208">The execution of every command line creates a new layer on the filesystem with the changes from the previous one, so that, when combined, produce the resulting filesystem.</span></span>

<span data-ttu-id="3e18b-209">모든 새 레이어가 이전 레이어를 "기반"으로 생성되는 것은 아니며 각 명령이 실행될 때마다 결과 이미지 크기가 증가하므로 애플리케이션을 빌드하고 게시하는 데 필요한 SDK 등을 포함해야 할 경우 이미지가 매우 커질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-209">Since every new layer "rests" on top of the previous one and the resulting image size increases with every command, images can get very large if they have to include, for example, the SDK needed to build and publish an application.</span></span>

<span data-ttu-id="3e18b-210">그래서 다단계 빌드가 들어가면(Docker 17.05 이상) 엄청난 효과를 발휘하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-210">This is where multi-stage builds get into the plot (from Docker 17.05 and higher) to do their magic.</span></span>

<span data-ttu-id="3e18b-211">핵심 개념은 단계에서 Dockerfile 실행 프로세스를 구분할 수 있다는 것입니다. 단계는 하나 이상의 명령이 실행되기 전 초기 이미지이며, 마지막 단계에서 최종 이미지 크기가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-211">The core idea is that you can separate the Dockerfile execution process in stages, where a stage is an initial image followed by one or more commands, and the last stage determines the final image size.</span></span>

<span data-ttu-id="3e18b-212">즉, 다단계 빌드는 생성 과정을 여러 "단계"로 분할한 후 최종 이미지를 어셈블하여 중간 단계에서 관련 디렉터리만 취할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-212">In short, multi-stage builds allow splitting the creation in different "phases" and then assemble the final image taking only the relevant directories from the intermediate stages.</span></span> <span data-ttu-id="3e18b-213">이 기능을 사용할 때의 일반적인 전략은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-213">The general strategy to use this feature is:</span></span>

1. <span data-ttu-id="3e18b-214">애플리케이션을 빌드하고 폴더에 게시하는 데 필요한 모든 것이 들어 있는 기본 SDK 이미지(크기는 중요하지 않음)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-214">Use a base SDK image (doesn't matter how large), with everything needed to build and publish the application to a folder and then</span></span>

2. <span data-ttu-id="3e18b-215">작은 런타임 전용의 기본 이미지를 사용하고 이전 단계의 게시 폴더를 복사하여 작은 최종 이미지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-215">Use a base, small, runtime-only image and copy the publishing folder from the previous stage to produce a small final image.</span></span>

<span data-ttu-id="3e18b-216">다단계 과정을 이해하는 가장 좋은 방법은 Dockerfile을 한 줄씩 자세히 살펴보는 것이므로 프로젝트에 Docker 지원을 추가할 때 Visual Studio에서 만든 초기 Dockerfile부터 살펴보고 나중에 몇 가지 최적화를 알아보도록 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-216">Probably the best way to understand multi-stage is going through a Dockerfile in detail, line by line, so let's begin with the initial Dockerfile created by Visual Studio when adding Docker support to a project and will get into some optimizations later.</span></span>

<span data-ttu-id="3e18b-217">초기 Dockerfile의 모습은 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-217">The initial Dockerfile might look something like this:</span></span>

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
 6  WORKDIR /src
 7  COPY src/Services/Catalog/Catalog.API/Catalog.API.csproj …
 8  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.AspNetCore.HealthChecks …
 9  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions.HealthChecks …
10  COPY src/BuildingBlocks/EventBus/IntegrationEventLogEF/ …
11  COPY src/BuildingBlocks/EventBus/EventBus/EventBus.csproj …
12  COPY src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.csproj …
13  COPY src/BuildingBlocks/EventBus/EventBusServiceBus/EventBusServiceBus.csproj …
14  COPY src/BuildingBlocks/WebHostCustomization/WebHost.Customization …
15  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
16  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
17  RUN dotnet restore src/Services/Catalog/Catalog.API/Catalog.API.csproj
18  COPY . .
19  WORKDIR /src/src/Services/Catalog/Catalog.API
20  RUN dotnet build Catalog.API.csproj -c Release -o /app
21
22  FROM build AS publish
23  RUN dotnet publish Catalog.API.csproj -c Release -o /app
24
25  FROM base AS final
26  WORKDIR /app
27  COPY --from=publish /app .
28  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

<span data-ttu-id="3e18b-218">이를 한 줄씩 자세히 설명하면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-218">And these are the details, line by line:</span></span>

- <span data-ttu-id="3e18b-219">**줄 #1:** "작은" 런타임 전용 기본 이미지로 단계를 시작하고 참조를 위해 이를 **base**라고 명명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-219">**Line #1:** Begin a stage with a "small" runtime-only base image, call it **base** for reference.</span></span>

- <span data-ttu-id="3e18b-220">**줄 #2:** 이미지에 **/app** 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-220">**Line #2:** Create the **/app** directory in the image.</span></span>

- <span data-ttu-id="3e18b-221">**줄 #3:** 포트 **80**을 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-221">**Line #3:** Expose port **80**.</span></span>

- <span data-ttu-id="3e18b-222">**줄 #5:** 빌드/게시를 위해 "큰" 이미지를 사용하여 새 단계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-222">**Line #5:** Begin a new stage with the "large" image for building/publishing.</span></span> <span data-ttu-id="3e18b-223">참조를 위해 이를 **build**라고 명명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-223">Call it **build** for reference.</span></span>

- <span data-ttu-id="3e18b-224">**줄 #6:** 이미지에 **/src** 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-224">**Line #6:** Create directory **/src** in the image.</span></span>

- <span data-ttu-id="3e18b-225">**줄 #7:** 패키지를 나중에 복원할 수 있도록 16번째 줄까지 참조된 **.csproj** 프로젝트 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-225">**Line #7:** Up to line 16, copy referenced **.csproj** project files to be able to restore packages later.</span></span>

- <span data-ttu-id="3e18b-226">**줄 #17:** **Catalog.API** 프로젝트 및 참조된 프로젝트의 패키지를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-226">**Line #17:** Restore packages for the **Catalog.API** project and the referenced projects.</span></span>

- <span data-ttu-id="3e18b-227">**줄 #18:** **솔루션의 모든 디렉터리 트리**( **.dockerignore** 파일에 포함된 파일/디렉터리는 예외)를 이미지의 **/src** 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-227">**Line #18:** Copy **all directory tree for the solution** (except the files/directories included in the **.dockerignore** file) to the **/src** directory in the image.</span></span>

- <span data-ttu-id="3e18b-228">**줄 #19:** 현재 폴더를 **Catalog.API** 프로젝트로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-228">**Line #19:** Change the current folder to the **Catalog.API** project.</span></span>

- <span data-ttu-id="3e18b-229">**줄 #20:** 프로젝트(및 기타 프로젝트 종속성)를 빌드하고 이미지의 **/app** 디렉터리에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-229">**Line #20:** Build the project (and other project dependencies) and output to the **/app** directory in the image.</span></span>

- <span data-ttu-id="3e18b-230">**줄 #22:** build에서 이어지는 새 단계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-230">**Line #22:** Begin a new stage continuing from the build.</span></span> <span data-ttu-id="3e18b-231">참조를 위해 이를 **publish**라고 명명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-231">Call it **publish** for reference.</span></span>

- <span data-ttu-id="3e18b-232">**줄 #23:** 프로젝트(및 종속성)를 게시하고 이미지의 **/app** 디렉터리에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-232">**Line #23:** Publish the project (and dependencies) and output to the **/app** directory in the image.</span></span>

- <span data-ttu-id="3e18b-233">**줄 #25:** **base**에서 이어지는 새 단계를 시작하고 이를 **final**이라고 명명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-233">**Line #25:** Begin a new stage continuing from **base** and call it **final**.</span></span>

- <span data-ttu-id="3e18b-234">**줄 #26:** 현재 디렉터리를 **/app**으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-234">**Line #26:** Change the current directory to **/app**.</span></span>

- <span data-ttu-id="3e18b-235">**줄 #27:** **publish** 단계에서 현재 디렉터리로 **/app** 디렉터리를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-235">**Line #27:** Copy the **/app** directory from stage **publish** to the current directory.</span></span>

- <span data-ttu-id="3e18b-236">**줄 #28:** 컨테이너가 시작될 때 실행할 명령을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-236">**Line #28:** Define the command to run when the container is started.</span></span>

<span data-ttu-id="3e18b-237">이제 전체 프로세스 성능을 높이는 몇 가지 최적화를 살펴보겠습니다. eShopOnContainers의 경우 Linux 컨테이너의 전체 솔루션을 빌드하는 데 약 22분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-237">Now let's explore some optimizations to improve the whole process performance that, in the case of eShopOnContainers, means about 22 minutes or more to build the complete solution in Linux containers.</span></span>

<span data-ttu-id="3e18b-238">상당히 간단한 Docker의 레이어 캐시 기능을 활용할 것인데, 기본 이미지와 명령이 이전에 실행된 것과 동일한 경우 명령을 실행할 필요 없이 결과 레이어만 사용하므로 시간이 절약됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-238">You'll take advantage of Docker's layer cache feature, which is quite simple: if the base image and the commands are the same as some previously executed, it can just use the resulting layer without the need to execute the commands, thus saving some time.</span></span>

<span data-ttu-id="3e18b-239">그러면 **build** 단계를 중점적으로 살펴보겠습니다. 5-6줄은 거의 동일하지만 7-17줄은 eShopOnContainers의 각 서비스마다 다르므로 매번 실행해야 합니다. 하지만 7-16줄을 다음과 같이 변경할 경우</span><span class="sxs-lookup"><span data-stu-id="3e18b-239">So, let's focus on the **build** stage, lines 5-6 are mostly the same, but lines 7-17 are different for every service from eShopOnContainers, so they have to execute every single time, however if you changed lines 7-16 to:</span></span>

```Dockerfile
COPY . .
```

<span data-ttu-id="3e18b-240">모든 서비스에 동일해집니다. 전체 솔루션이 복사되고 더 큰 레이어가 생성됩니다. 단,</span><span class="sxs-lookup"><span data-stu-id="3e18b-240">Then it would be just the same for every service, it would copy the whole solution and would create a larger layer but:</span></span>

1. <span data-ttu-id="3e18b-241">복사 프로세스는 처음에만 실행되고(그리고 파일이 변경되어 다시 빌드하는 경우) 다른 모든 서비스에 캐시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-241">The copy process would only be executed the first time (and when rebuilding if a file is changed) and would use the cache for all other services and</span></span>

2. <span data-ttu-id="3e18b-242">중간 단계에서 더 큰 이미지가 생성되므로 최종 이미지 크기는 달라지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-242">Since the larger image occurs in an intermediate stage it, doesn't affect the final image size.</span></span>

<span data-ttu-id="3e18b-243">다음으로 중요한 최적화는 17줄에서 실행된 `restore` 명령과 관련이 있습니다. 이 명령도 역시 eShopOnContainers의 각 서비스마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-243">The next significant optimization involves the `restore` command executed in line 17, which is also different for every service of eShopOnContainers.</span></span> <span data-ttu-id="3e18b-244">이 줄을 다음과 같이 변경할 경우</span><span class="sxs-lookup"><span data-stu-id="3e18b-244">If you change that line to just:</span></span>

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="3e18b-245">현재 전략으로 전체 솔루션의 패키지를 복원하려면 15번을 반복해야 하는 것과는 달리 단 한 번에 패키지를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-245">It would restore the packages for the whole solution, but then again, it would do it just once, instead of the 15 times with the current strategy.</span></span>

<span data-ttu-id="3e18b-246">하지만 `dotnet restore`는 폴더에 단일 프로젝트나 솔루션 파일이 있을 경우에만 실행되므로 이 방법은 약간 복잡하며 너무 세세한 부분까지 접근하지 않고 이 작업을 처리하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-246">However, `dotnet restore` only runs if there's a single project or solution file in the folder, so achieving this is a bit more complicated and the way to solve it, without getting into too many details, is this:</span></span>

1. <span data-ttu-id="3e18b-247">**.dockerignore**에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-247">Add the following lines to **.dockerignore**:</span></span>

   - <span data-ttu-id="3e18b-248">`*.sln` - 기본 폴더 트리의 모든 솔루션 파일 무시</span><span class="sxs-lookup"><span data-stu-id="3e18b-248">`*.sln`, to ignore all solution files in the main folder tree</span></span>

   - <span data-ttu-id="3e18b-249">`!eShopOnContainers-ServicesAndWebApps.sln` - 이 솔루션 파일만 포함</span><span class="sxs-lookup"><span data-stu-id="3e18b-249">`!eShopOnContainers-ServicesAndWebApps.sln`, to include only this solution file.</span></span>

2. <span data-ttu-id="3e18b-250">`dotnet restore`에 `/ignoreprojectextensions:.dcproj` 인수를 포함하여 docker-compose 프로젝트를 무시하고 eShopOnContainers-ServicesAndWebApps 솔루션의 패키지만 복원하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-250">Include the `/ignoreprojectextensions:.dcproj` argument to `dotnet restore`, so it also ignores the docker-compose project and only restores the packages for the eShopOnContainers-ServicesAndWebApps solution.</span></span>

<span data-ttu-id="3e18b-251">마지막 최적화를 보겠습니다. 20줄 바로 다음에 오는 23줄에서 애플리케이션을 빌드하므로 20줄은 불필요하며 시간이 오래 걸리는 명령을 또 한 번 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-251">For the final optimization, it just happens that line 20 is redundant, as line 23 also builds the application and comes, in essence, right after line 20, so there goes another time-consuming command.</span></span>

<span data-ttu-id="3e18b-252">결과 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-252">The resulting file is then:</span></span>

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS publish
 6  WORKDIR /src
 7  COPY . .
 8  RUN dotnet restore /ignoreprojectextensions:.dcproj
 9  WORKDIR /src/src/Services/Catalog/Catalog.API
10  RUN dotnet publish Catalog.API.csproj -c Release -0 /app
11
12  FROM base AS final
13  WORKDIR /app
14  COPY --from=publish /app
15  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

### <a name="creating-your-base-image-from-scratch"></a><span data-ttu-id="3e18b-253">기본 이미지를 처음부터 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="3e18b-253">Creating your base image from scratch</span></span>

<span data-ttu-id="3e18b-254">개발자 고유의 Docker 기본 이미지를 처음부터 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-254">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="3e18b-255">이 시나리오는 Docker를 시작하는 분들에게는 권장하지 않지만, 자신만의 고유한 기본 이미지 비트를 설정하고 싶은 분들은 그렇게 하셔도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-255">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3e18b-256">추가 자료</span><span class="sxs-lookup"><span data-stu-id="3e18b-256">Additional resources</span></span>

- <span data-ttu-id="3e18b-257">**다중 아키텍처 .NET Core 이미지**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-257">**Multi-arch .NET Core images**.</span></span>\
  <https://github.com/dotnet/announcements/issues/14>

- <span data-ttu-id="3e18b-258">**기본 이미지 만들기**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-258">**Create a base image**.</span></span> <span data-ttu-id="3e18b-259">공식 Docker 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-259">Official Docker documentation.</span></span>\
  <https://docs.docker.com/develop/develop-images/baseimages/>

![3단계의 이미지입니다.](./media/docker-app-development-workflow/step-3-create-dockerfile-defined-images.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="3e18b-261">3단계.</span><span class="sxs-lookup"><span data-stu-id="3e18b-261">Step 3.</span></span> <span data-ttu-id="3e18b-262">고유의 사용자 지정 Docker 이미지를 만들고 그 안에 애플리케이션 또는 서비스 포함</span><span class="sxs-lookup"><span data-stu-id="3e18b-262">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="3e18b-263">애플리케이션의 서비스마다 관련 이미지를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-263">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="3e18b-264">애플리케이션이 단일 서비스 또는 웹 애플리케이션으로 구성된 경우 단일 이미지만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-264">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="3e18b-265">Docker 이미지는 Visual Studio에서 자동으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-265">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="3e18b-266">다음 단계는 편집기/CLI 워크플로에만 필요하며 내부적으로 발생하는 동작에 대한 이해를 돕기 위해 설명되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-266">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="3e18b-267">개발자는 완료된 기능 또는 변경 내용을 소스 제어 시스템(예: GitHub)으로 푸시할 때까지 로컬로 개발 및 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-267">You, as a developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="3e18b-268">즉, Docker 이미지를 만들고 로컬 Docker 호스트(Windows 또는 Linux VM)에 컨테이너를 배포한 후 로컬 컨테이너에 대해 실행, 테스트 및 디버그해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-268">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="3e18b-269">로컬 환경에서 Docker CLI 및 Dockerfile을 사용하여 사용자 지정 이미지를 만들려면 그림 5-5처럼 docker build 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-269">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![docker build 명령의 콘솔 출력을 보여 주는 스크린샷입니다.](./media/docker-app-development-workflow/run-docker-build-command.png)

<span data-ttu-id="3e18b-271">**그림 5-5**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-271">**Figure 5-5**.</span></span> <span data-ttu-id="3e18b-272">사용자 지정 Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="3e18b-272">Creating a custom Docker image</span></span>

<span data-ttu-id="3e18b-273">필요에 따라 프로젝트 폴더에서 직접 docker 빌드를 실행하는 대신, 먼저 `dotnet publish`를 실행하여 필수 .NET 라이브러리와 이진 파일로 배포 가능 폴더를 생성한 다음, `docker build` 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-273">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running `dotnet publish`, and then use the `docker build` command.</span></span>

<span data-ttu-id="3e18b-274">그러면 이름이 `cesardl/netcore-webapi-microservice-docker:first`인 Docker 이미지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-274">This will create a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first`.</span></span> <span data-ttu-id="3e18b-275">이 경우 첫 번째는 특정 버전을 나타내는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-275">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="3e18b-276">구성된 Docker 애플리케이션에 대해 만들어야 하는 사용자 지정 이미지마다 이 단계를 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-276">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="3e18b-277">또한 애플리케이션이 여러 컨테이너로 구성된 경우(즉, 다중 컨테이너 애플리케이션인 경우) `docker-compose up --build` 명령을 사용하여 관련 docker-compose.yml 파일에 노출된 메타데이터를 통해 단일 명령으로 모든 관련 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-277">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the `docker-compose up --build` command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="3e18b-278">그림 5-6처럼 docker images 명령을 사용하여 로컬 리포지토리에서 기존 이미지를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-278">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![기존 이미지를 보여주는 docker images 명령의 콘솔 출력](./media/docker-app-development-workflow/view-existing-images-with-docker-images.png)

<span data-ttu-id="3e18b-280">**그림 5-6.**</span><span class="sxs-lookup"><span data-stu-id="3e18b-280">**Figure 5-6.**</span></span> <span data-ttu-id="3e18b-281">docker images 명령을 사용하여 기존 이미지 보기</span><span class="sxs-lookup"><span data-stu-id="3e18b-281">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="3e18b-282">Visual Studio로 Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="3e18b-282">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="3e18b-283">Visual Studio를 사용하여 Docker가 지원되는 프로젝트를 만드는 경우 이미지를 명시적으로 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3e18b-283">When you use Visual Studio to create a project with Docker support, you don't explicitly create an image.</span></span> <span data-ttu-id="3e18b-284">대신 **F5**(또는 **Ctrl-F5**) 키를 눌러 Docker화된 애플리케이션 또는 서비스를 실행하면 자동으로 이미지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-284">Instead, the image is created for you when you press **F5** (or **Ctrl-F5**) to run the dockerized application or service.</span></span> <span data-ttu-id="3e18b-285">이 단계는 Visual Studio에서 자동으로 실행되며 사용자에게는 보이지 않지만 내부적으로 어떤 일이 발생하는지 알아두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-285">This step is automatic in Visual Studio and you won't see it happen, but it's important that you know what's going on underneath.</span></span>

![선택 사항인 4단계의 이미지입니다.](./media/docker-app-development-workflow/step-4-define-services-docker-compose-yml.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="3e18b-287">4단계.</span><span class="sxs-lookup"><span data-stu-id="3e18b-287">Step 4.</span></span> <span data-ttu-id="3e18b-288">다중 컨테이너 Docker 애플리케이션을 빌드할 때 docker compose.yml 파일에서 서비스 정의</span><span class="sxs-lookup"><span data-stu-id="3e18b-288">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="3e18b-289">[docker compose.yml](https://docs.docker.com/compose/compose-file/) 파일을 사용하여 배포 명령을 통해 구성된 애플리케이션으로 배포할 관련 서비스 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-289">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span> <span data-ttu-id="3e18b-290">또한 해당 종속성 관계 및 런타임 구성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-290">It also configures its dependency relations and run-time configuration.</span></span>

<span data-ttu-id="3e18b-291">docker-compose.yml 파일을 사용하려면 기본 또는 루트 솔루션 폴더에 다음 예제와 비슷한 콘텐츠가 있는 파일을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-291">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3.4'

services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog-api
      - OrderingUrl=http://ordering-api
    ports:
      - "80:80"
    depends_on:
      - catalog-api
      - ordering-api

  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Port=1433;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sqldata

  ordering-api:
    image: eshop/ordering-api
    environment:
      - ConnectionString=Server=sqldata;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sqldata

  sqldata:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

<span data-ttu-id="3e18b-292">이 docker-compose.yml 파일은 단순화되고 병합된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-292">This docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="3e18b-293">항상 필요한 각 컨테이너에 대한 정적인 구성 데이터(사용자 지정 이미지처럼)와 연결 문자열처럼 배포 환경에 종속된 구성 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-293">It contains static configuration data for each container (like the name of the custom image), which is always required, and configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="3e18b-294">이후 섹션에서는 환경 및 실행 유형(디버그 또는 릴리스)에 따라 docker-compose.yml 구성을 여러 docker-compose 파일로 분할하고 값을 재정의하는 방법을 알아보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-294">In later sections, you will learn how to split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="3e18b-295">docker-compose.yml 파일 예제에서는 컨테이너로 실행되는 SQL Server for Linux를 기반으로 `webmvc` 서비스(웹 애플리케이션), 2개의 마이크로 서비스(`ordering-api` 및 `basket-api`), 1개의 데이터 원본 컨테이너, `sqldata`의 총 4개 서비스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-295">The docker-compose.yml file example defines four services: the `webmvc` service (a web application), two microservices (`ordering-api` and `basket-api`), and one data source container, `sqldata`, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="3e18b-296">각 서비스는 컨테이너로 배포되므로 각 서비스에 Docker 이미지가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-296">Each service will be deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="3e18b-297">docker-compose.yml 파일은 사용되는 컨테이너뿐 아니라 개별적으로 구성되는 방법까지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-297">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="3e18b-298">예를 들어 .yml 파일의 `webmvc` 컨테이너 정의는 다음과 같은 일을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-298">For instance, the `webmvc` container definition in the .yml file:</span></span>

- <span data-ttu-id="3e18b-299">미리 빌드된 `eshop/web:latest` 이미지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-299">Uses a pre-built `eshop/web:latest` image.</span></span> <span data-ttu-id="3e18b-300">그러나 docker-compose 파일의 빌드: 섹션을 기반으로 한 추가 구성을 사용하여 docker-compose 실행의 일부로 빌드되도록 이미지를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-300">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

- <span data-ttu-id="3e18b-301">두 환경 변수(CatalogUrl 및 OrderingUrl)를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-301">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

- <span data-ttu-id="3e18b-302">컨테이너에 노출된 포트 80을 호스트 컴퓨터의 포트 80으로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-302">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

- <span data-ttu-id="3e18b-303">depends_on 설정을 사용하여 웹앱을 카탈로그 및 주문 서비스와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-303">Links the web app to the catalog and ordering service with the depends_on setting.</span></span> <span data-ttu-id="3e18b-304">이렇게 하면 서비스는 이러한 서비스가 시작될 때까지 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-304">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="3e18b-305">이후 섹션에서 마이크로 서비스 및 다중 컨테이너 앱을 구현하는 방법을 알아볼 때 docker-compose.yml 파일을 다시 한 번 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-305">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2019"></a><span data-ttu-id="3e18b-306">Visual Studio 2019에서 docker-compose.yml 파일 작업</span><span class="sxs-lookup"><span data-stu-id="3e18b-306">Working with docker-compose.yml in Visual Studio 2019</span></span>

<span data-ttu-id="3e18b-307">앞서 말한 것처럼 Visual Studio 2017(15.8 버전부터)은 프로젝트에 Dockerfile을 추가하는 것 외에도 Docker Compose에 대한 오케스트레이터 지원을 솔루션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-307">Besides adding a Dockerfile to a project, as we mentioned before, Visual Studio 2017 (from version 15.8 on) can add orchestrator support for Docker Compose to a solution.</span></span>

<span data-ttu-id="3e18b-308">그림 5-7에 나와 있는 것처럼 컨테이너 오케스트레이터 지원을 처음으로 추가하면 Visual Studio가 프로젝트용 Dockerfile을 만들고 몇 가지 글로벌 `docker-compose*.yml` 파일을 사용하여 솔루션에 새로운(서비스 섹션) 프로젝트를 만든 후 이러한 파일에 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-308">When you add container orchestrator support, as shown in Figure 5-7, for the first time, Visual Studio creates the Dockerfile for the project and creates a new (service section) project in your solution with several global `docker-compose*.yml` files, and then adds the project to those files.</span></span> <span data-ttu-id="3e18b-309">그런 다음, docker-compose.yml 파일을 열고 추가 기능을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-309">You can then open the docker-compose.yml files and update them with additional features.</span></span>

<span data-ttu-id="3e18b-310">docker-compose.yml 파일에 포함할 각 프로젝트에서 이 작업을 반복해서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-310">You have to repeat this operation form every project you want to include in the docker-compose.yml file.</span></span>

<span data-ttu-id="3e18b-311">이러한 작성 과정에서 Visual Studio는 **Docker Compose** 및 **Kubernetes/Helm** 오케스트레이터를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-311">At the time of this writing, Visual Studio supports **Docker Compose** and **Kubernetes/Helm** orchestrators.</span></span>

![프로젝트 상황에 맞는 메뉴의 컨테이너 오케스트레이터 지원 옵션을 보여 주는 스크린샷](./media/docker-app-development-workflow/add-container-orchestrator-support-option.png)

<span data-ttu-id="3e18b-313">**그림 5-7**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-313">**Figure 5-7**.</span></span> <span data-ttu-id="3e18b-314">ASP.NET Core 프로젝트를 마우스 오른쪽 단추로 클릭하여 Visual Studio 2019에 Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="3e18b-314">Adding Docker support in Visual Studio 2019 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="3e18b-315">Visual Studio에서 솔루션에 오케스트레이터 지원을 추가하면 그림 5-8처럼 추가된 docker-compose.yml 파일을 포함하는 새 노드(`docker-compose.dcproj` 프로젝트 파일에 있는)가 솔루션 탐색기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-315">After you add orchestrator support to your solution in Visual Studio, you will also see a new node (in the `docker-compose.dcproj` project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![솔루션 탐색기의 docker-compose 노드를 보여 주는 스크린샷](./media/docker-app-development-workflow/docker-compose-tree-node.png)

<span data-ttu-id="3e18b-317">**그림 5-8**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-317">**Figure 5-8**.</span></span> <span data-ttu-id="3e18b-318">Visual Studio 2019 솔루션 탐색기에 추가된 **docker-compose** 트리 노드</span><span class="sxs-lookup"><span data-stu-id="3e18b-318">The **docker-compose** tree node added in Visual Studio 2019 Solution Explorer</span></span>

<span data-ttu-id="3e18b-319">`docker-compose up` 명령을 사용하여 단일 docker-compose.yml 파일이 있는 다중 컨테이너 애플리케이션을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-319">You could deploy a multi-container application with a single docker-compose.yml file by using the `docker-compose up` command.</span></span> <span data-ttu-id="3e18b-320">그러나 Visual Studio에서 그룹으로 추가하므로 개발자는 환경(개발 또는 프로덕션) 및 실행 형식(릴리스 또는 디버그)에 따라 값을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-320">However, Visual Studio adds a group of them so you can override values depending on the environment (development or production) and execution type (release or debug).</span></span> <span data-ttu-id="3e18b-321">이 기능에 대한 내용은 이후 섹션에서 설명하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-321">This capability will be explained in later sections.</span></span>

![5단계의 이미지입니다.](./media/docker-app-development-workflow/step-5-run-containers-compose-app.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="3e18b-323">5단계.</span><span class="sxs-lookup"><span data-stu-id="3e18b-323">Step 5.</span></span> <span data-ttu-id="3e18b-324">Docker 애플리케이션을 빌드하고 실행</span><span class="sxs-lookup"><span data-stu-id="3e18b-324">Build and run your Docker application</span></span>

<span data-ttu-id="3e18b-325">애플리케이션에 단일 컨테이너만 있는 경우 애플리케이션을 Docker 호스트(VM 또는 실제 서버)에 배포하여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-325">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="3e18b-326">그러나 애플리케이션에 여러 서비스가 있는 경우에는 단일 CLI 명령(`docker-compose up)`) 또는 이 명령을 내부적으로 실행하는 Visual Studio를 사용하여 이를 구성된 애플리케이션으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-326">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (`docker-compose up)`, or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="3e18b-327">다양한 옵션을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-327">Let's look at the different options.</span></span>

### <a name="option-a-running-a-single-container-application"></a><span data-ttu-id="3e18b-328">옵션 A: 단일 컨테이너 애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="3e18b-328">Option A: Running a single-container application</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="3e18b-329">Docker CLI 사용</span><span class="sxs-lookup"><span data-stu-id="3e18b-329">Using Docker CLI</span></span>

<span data-ttu-id="3e18b-330">그림 5-9처럼 `docker run` 명령을 사용하여 Docker 컨테이너를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-330">You can run a Docker container using the `docker run` command, as shown in Figure 5-9:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="3e18b-331">위의 명령이 실행될 때마다 지정된 이미지에서 새 컨테이너 인스턴스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-331">The above command will create a new container instance from the specified image, every time it's run.</span></span> <span data-ttu-id="3e18b-332">`--name` 매개 변수를 사용하여 컨테이너에 이름을 지정한 다음, `docker start {name}`(또는 컨테이너 ID나 자동 이름)을 사용하여 기존의 컨테이너 인스턴스를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-332">You can use the `--name` parameter to give a name to the container and then use `docker start {name}` (or use the container ID or automatic name) to run an existing container instance.</span></span>

![Docker run 명령을 사용하여 Docker 컨테이너를 실행하는 스크린샷](./media/docker-app-development-workflow/use-docker-run-command.png)

<span data-ttu-id="3e18b-334">**그림 5-9**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-334">**Figure 5-9**.</span></span> <span data-ttu-id="3e18b-335">docker run 명령을 사용하여 Docker 컨테이너 실행</span><span class="sxs-lookup"><span data-stu-id="3e18b-335">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="3e18b-336">이 경우 이 명령은 컨테이너의 내부 포트 5000을 호스트 컴퓨터의 포트 80에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-336">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="3e18b-337">즉, 호스트가 포트 80에서 수신 대기하고 컨테이너의 포트 5000에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-337">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

<span data-ttu-id="3e18b-338">표시된 해시는 컨테이너 ID이며, `--name` 옵션이 사용되지 않은 경우 임의의 가독성 있는 이름도 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-338">The hash shown is the container ID and it’s also assigned a random readable name if the `--name` option is not used.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="3e18b-339">Visual Studio 사용</span><span class="sxs-lookup"><span data-stu-id="3e18b-339">Using Visual Studio</span></span>

<span data-ttu-id="3e18b-340">컨테이너 오케스트레이터 지원을 추가하지 않은 경우 Visual Studio에서 **Ctrl-F5**를 눌러 단일 컨테이너 앱을 실행할 수도 있고, **F5** 키를 사용하여 컨테이너 내에서 애플리케이션을 디버깅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-340">If you haven't added container orchestrator support, you can also run a single container app in Visual Studio by pressing **Ctrl-F5** and you can also use **F5** to debug the application within the container.</span></span> <span data-ttu-id="3e18b-341">컨테이너는 docker run을 사용하여 로컬로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-341">The container runs locally using docker run.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="3e18b-342">옵션 B: 다중 컨테이너 애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="3e18b-342">Option B: Running a multi-container application</span></span>

<span data-ttu-id="3e18b-343">대부분의 엔터프라이즈 시나리오에서 Docker 애플리케이션은 여러 서비스로 구성되며, 따라서 그림 5-10처럼 다중 컨테이너 애플리케이션을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-343">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![여러 Docker 컨테이너가 있는 VM](./media/docker-app-development-workflow/vm-with-docker-containers-deployed.png)

<span data-ttu-id="3e18b-345">**그림 5-10**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-345">**Figure 5-10**.</span></span> <span data-ttu-id="3e18b-346">Docker 컨테이너가 배포된 VM</span><span class="sxs-lookup"><span data-stu-id="3e18b-346">VM with Docker containers deployed</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="3e18b-347">Docker CLI 사용</span><span class="sxs-lookup"><span data-stu-id="3e18b-347">Using Docker CLI</span></span>

<span data-ttu-id="3e18b-348">Docker CLI를 사용하여 다중 컨테이너 애플리케이션을 실행하려면 `docker-compose up` 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="3e18b-348">To run a multi-container application with the Docker CLI, you use the `docker-compose up` command.</span></span> <span data-ttu-id="3e18b-349">이 명령은 솔루션 수준에서 **docker-compose.yml** 파일을 사용하여 다중 컨테이너 애플리케이션을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-349">This command uses the **docker-compose.yml** file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="3e18b-350">그림 5-11은 기본 솔루션 디렉터리에서 명령을 실행할 때의 결과를 보여주며, docker-compose.yml 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-350">Figure 5-11 shows the results when running the command from your main solution directory, which contains the docker-compose.yml file.</span></span>

![docker-compose up 명령을 실행할 때의 화면 보기](./media/docker-app-development-workflow/results-docker-compose-up.png)

<span data-ttu-id="3e18b-352">**그림 5-11**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-352">**Figure 5-11**.</span></span> <span data-ttu-id="3e18b-353">docker-compose up 명령을 실행할 때의 결과 예제</span><span class="sxs-lookup"><span data-stu-id="3e18b-353">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="3e18b-354">docker-compose up 명령을 실행하면 그림 5-10에 나와 있는 것처럼 애플리케이션 및 관련 컨테이너가 Docker 호스트에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-354">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as depicted in Figure 5-10.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="3e18b-355">Visual Studio 사용</span><span class="sxs-lookup"><span data-stu-id="3e18b-355">Using Visual Studio</span></span>

<span data-ttu-id="3e18b-356">Visual Studio 2019를 사용하여 다중 컨테이너 애플리케이션을 실행하는 방법이 더 이상 간단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-356">Running a multi-container application using Visual Studio 2019 can't get any simpler.</span></span> <span data-ttu-id="3e18b-357">평상시처럼 **Ctrl-F5**를 눌러 실행하거나 **F5** 키를 눌러 디버깅하여 **docker-compose** 프로젝트를 시작 프로젝트로 설정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-357">You just press **Ctrl-F5** to run or **F5** to debug, as usual, setting up the **docker-compose** project as the startup project.</span></span>  <span data-ttu-id="3e18b-358">Visual Studio가 필요한 모든 설정을 처리하므로 평상시처럼 중단점을 만들고 최종적으로 "원격 서버"에서 실행되는 독립 프로세스를 마찬가지로 디버거가 이미 연결된 상태에서 디버깅할 수</span><span class="sxs-lookup"><span data-stu-id="3e18b-358">Visual Studio handles all needed setup, so you can create breakpoints as usual and debug what finally become independent processes running in "remote servers", with the debugger already attached.</span></span> <span data-ttu-id="3e18b-359">있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-359">just like that.</span></span>

<span data-ttu-id="3e18b-360">앞서 언급했듯이, 솔루션 내의 프로젝트에 Docker 솔루션 지원을 추가할 때마다 해당 프로젝트가 전역(솔루션 수준) docker-compose.yml 파일에서 구성되며, 따라서 전체 솔루션을 한꺼번에 실행 또는 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-360">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="3e18b-361">Visual Studio는 Docker 솔루션 지원이 사용되는 각 프로젝트에 대해 하나의 컨테이너를 시작하고, 모든 내부 단계(dotnet 게시, dotnet 빌드 등)를 자동으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-361">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="3e18b-362">모든 단조로운 작업을 엿보려면 파일을 살펴보세요</span><span class="sxs-lookup"><span data-stu-id="3e18b-362">If you want to take a peek at all the drudgery, take a look at the file:</span></span>

`{root solution folder}\obj\Docker\docker-compose.vs.debug.g.yml`

<span data-ttu-id="3e18b-363">여기서 중요한 점은, 그림 5-12처럼 Visual Studio 2019에는 F5 키 작업에 대한 추가 **Docker** 명령이 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-363">The important point here is that, as shown in Figure 5-12, in Visual Studio 2019 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="3e18b-364">이 옵션을 통해 솔루션 수준에서 docker-compose.yml 파일에 정의된 모든 컨테이너를 실행하여 다중 컨테이너 애플리케이션을 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-364">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="3e18b-365">다중 컨테이너 솔루션을 디버그하는 기능이 있다는 것은 서로 다른 프로젝트(컨테이너)마다 하나씩 여러 중단점을 지정할 수 있으며, Visual Studio에서 디버깅할 때 여러 프로젝트에서 정의되어 여러 컨테이너에서 실행되는 중단점에서 중지된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-365">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![Docker 작성 프로젝트를 실행하는 디버그 도구 모음의 스크린샷](./media/docker-app-development-workflow/debug-toolbar-docker-compose-project.png)

<span data-ttu-id="3e18b-367">**그림 5-12**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-367">**Figure 5-12**.</span></span> <span data-ttu-id="3e18b-368">Visual Studio 2019에서 다중 컨테이너 앱 실행</span><span class="sxs-lookup"><span data-stu-id="3e18b-368">Running multi-container apps in Visual Studio 2019</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3e18b-369">추가 자료</span><span class="sxs-lookup"><span data-stu-id="3e18b-369">Additional resources</span></span>

- <span data-ttu-id="3e18b-370">**원격 Docker 호스트에 ASP.NET 컨테이너 배포** </span><span class="sxs-lookup"><span data-stu-id="3e18b-370">**Deploy an ASP.NET container to a remote Docker host** </span></span>\
  <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="3e18b-371">오케스트레이터를 사용하여 테스트 및 배포하는 내용에 대한 메모</span><span class="sxs-lookup"><span data-stu-id="3e18b-371">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="3e18b-372">docker-compose up 및 docker run 명령(또는 Visual Studio에서 컨테이너를 실행하고 디버깅)은 개발 환경에서 컨테이너를 테스트하기에 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-372">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="3e18b-373">하지만 프로덕션 배포의 경우에는 이 접근법을 사용하지 말고 [Kubernetes](https://kubernetes.io/) 또는 [Service Fabric](https://azure.microsoft.com/services/service-fabric/) 같은 오케스트레이터를 대상으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-373">But you should not use this approach for production deployments, where you should target orchestrators like [Kubernetes](https://kubernetes.io/) or [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span></span> <span data-ttu-id="3e18b-374">Kubernetes를 사용 중인 경우 [pod](https://kubernetes.io/docs/concepts/workloads/pods/pod/)로 컨테이너와 [서비스](https://kubernetes.io/docs/concepts/services-networking/service/)를 정리하여 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-374">If you're using Kubernetes, you have to use [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) to organize containers and [services](https://kubernetes.io/docs/concepts/services-networking/service/) to network them.</span></span> <span data-ttu-id="3e18b-375">또한 [배포](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)를 사용하여 pod 생성 및 수정을 정리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-375">You also use [deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) to organize pod creation and modification.</span></span>

![6단계의 이미지입니다.](./media/docker-app-development-workflow/step-6-test-app-microservices.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="3e18b-377">6단계.</span><span class="sxs-lookup"><span data-stu-id="3e18b-377">Step 6.</span></span> <span data-ttu-id="3e18b-378">로컬 Docker 호스트를 사용하여 Docker 애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="3e18b-378">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="3e18b-379">이 단계는 애플리케이션에서 하는 일에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-379">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="3e18b-380">단일 컨테이너 또는 서비스로 배포되는 간단한 .NET Core 웹 애플리케이션에서는 그림 5-13처럼 Docker 호스트에서 브라우저를 열고 해당 사이트로 이동하여 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-380">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site, as shown in Figure 5-13.</span></span> <span data-ttu-id="3e18b-381">(Dockerfile의 구성이 컨테이너를 호스트에 있는 80 이외의 포트로 매핑하는 경우 호스트 포트를 URL에 포함합니다.)</span><span class="sxs-lookup"><span data-stu-id="3e18b-381">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![Localhost/API/값에서 오는 응답의 스크린샷](./media/docker-app-development-workflow/test-docker-app-locally-localhost.png)

<span data-ttu-id="3e18b-383">**그림 5-13**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-383">**Figure 5-13**.</span></span> <span data-ttu-id="3e18b-384">localhost를 사용하여 로컬로 Docker 애플리케이션을 테스트하는 예제</span><span class="sxs-lookup"><span data-stu-id="3e18b-384">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="3e18b-385">localhost가 Docker 호스트 IP를 가리키지 않는 경우(Docker CE를 사용하는 경우 기본적으로 Docker 호스트 IP를 가리켜야 함) 서비스를 탐색하려면 머신 네트워크 카드의 IP 주소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-385">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine's network card.</span></span>

<span data-ttu-id="3e18b-386">브라우저에서 이 URL은 우리가 살펴보고 있는 특정 컨테이너 예제에 대한 포트 80을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-386">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="3e18b-387">그러나 내부적으로는 요청이 포트 5000으로 리디렉션됩니다. 왜냐하면 이전 단계에서 설명했듯이 docker run 명령을 사용하여 이와 같은 방법으로 배포되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-387">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="3e18b-388">그림 5-14처럼 터미널에서 curl을 사용하여 애플리케이션을 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-388">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="3e18b-389">Windows에 설치된 Docker에서 기본 Docker 호스트 IP는 머신의 실제 IP 주소와는 별개로 항상 10.0.75.1입니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-389">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine's actual IP address.</span></span>

![CURL을 사용하여 http://10.0.75.1/API/values 에서 가져온 콘솔 출력](./media/docker-app-development-workflow/test-docker-app-locally-curl.png)

<span data-ttu-id="3e18b-391">**그림 5-14**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-391">**Figure 5-14**.</span></span> <span data-ttu-id="3e18b-392">curl을 사용하여 로컬로 Docker 애플리케이션을 테스트하는 예제</span><span class="sxs-lookup"><span data-stu-id="3e18b-392">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2019"></a><span data-ttu-id="3e18b-393">Visual Studio 2019를 사용하여 컨테이너 테스트 및 디버깅</span><span class="sxs-lookup"><span data-stu-id="3e18b-393">Testing and debugging containers with Visual Studio 2019</span></span>

<span data-ttu-id="3e18b-394">Visual Studio 2019를 사용하여 컨테이너를 실행하고 디버깅할 때 컨테이너 없이 실행할 때와 거의 동일한 방법으로 .NET 애플리케이션을 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-394">When running and debugging the containers with Visual Studio 2019, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="3e18b-395">Visual Studio 없이 디버깅 및 테스트</span><span class="sxs-lookup"><span data-stu-id="3e18b-395">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="3e18b-396">편집기/CLI 방식을 사용하여 개발하는 경우 컨테이너를 디버깅하기가 더 어려우며 추적을 생성하여 디버그하는 것이 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-396">If you're developing using the editor/CLI approach, debugging containers is more difficult and you'll probably want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3e18b-397">추가 자료</span><span class="sxs-lookup"><span data-stu-id="3e18b-397">Additional resources</span></span>

- <span data-ttu-id="3e18b-398">**로컬 Docker 컨테이너에서 앱 디버그** </span><span class="sxs-lookup"><span data-stu-id="3e18b-398">**Debugging apps in a local Docker container** </span></span>\
  [https://docs.microsoft.com/visualstudio/containers/edit-and-refresh](/visualstudio/containers/edit-and-refresh)

- <span data-ttu-id="3e18b-399">**Steve Lasker. Docker를 사용하여 ASP.NET Core 앱 빌드, 디버그, 배포.**</span><span class="sxs-lookup"><span data-stu-id="3e18b-399">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="3e18b-400">비디오.</span><span class="sxs-lookup"><span data-stu-id="3e18b-400">Video.</span></span> \
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115>

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="3e18b-401">Visual Studio를 사용하여 컨테이너를 개발할 때의 간소화된 워크플로</span><span class="sxs-lookup"><span data-stu-id="3e18b-401">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="3e18b-402">Visual Studio를 사용하면 편집기/CLI 방식을 사용할 때보다 워크플로가 훨씬 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-402">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="3e18b-403">Dockerfile 및 docker-compose.yml 파일과 관련하여 Docker에 필요한 대부분의 단계는 그림 5-15처럼 숨겨져 있거나 Visual Studio를 통해 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-403">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

:::image type="complex" source="./media/docker-app-development-workflow/simplified-life-cycle-containerized-apps-docker-cli.png" alt-text="앱을 만드는 데 걸리는 5가지 간단한 단계를 보여 주는 다이어그램":::
<span data-ttu-id="3e18b-405">Docker 앱 개발 프로세스: 1 - 앱 코딩, 2 - Dockerfile 작성, 3 - Dockerfile에 정의된 이미지 만들기, 4 - (선택 사항) docker-compose.yml 파일에 서비스 작성, 5 - container 또는 docker-compose 앱 실행, 6 - 앱 또는 마이크로 서비스 테스트, 7 - 리포지토리에 푸시하고 반복.</span><span class="sxs-lookup"><span data-stu-id="3e18b-405">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span>
:::image-end:::

<span data-ttu-id="3e18b-406">**그림 5-15**.</span><span class="sxs-lookup"><span data-stu-id="3e18b-406">**Figure 5-15**.</span></span> <span data-ttu-id="3e18b-407">Visual Studio를 사용하여 배포할 때의 간소화된 워크플로</span><span class="sxs-lookup"><span data-stu-id="3e18b-407">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="3e18b-408">또한 2단계(프로젝트에 Docker 지원 추가)를 한 번만 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-408">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="3e18b-409">따라서 다른 개발에서 .NET을 사용하여 수행하는 일반적인 개발 작업과 워크플로가 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-409">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="3e18b-410">내부에서 어떤 동작이 발생하는지(이미지 빌드 프로세스, 사용하는 기본 이미지, 컨테이너 배포 등) 알아야 하며, 때로는 Dockerfile 또는 docker-compose.yml 파일을 편집하여 동작을 사용자 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-410">You need to know what is going on under the covers (the image build process, what base images you're using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="3e18b-411">하지만 Visual Studio를 사용하여 대부분의 작업이 대폭 간소화되므로 개발자의 생산성이 크게 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-411">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3e18b-412">추가 자료</span><span class="sxs-lookup"><span data-stu-id="3e18b-412">Additional resources</span></span>

- <span data-ttu-id="3e18b-413">**Steve Lasker. Visual Studio(2017)를 사용한 .NET Docker 개발** </span><span class="sxs-lookup"><span data-stu-id="3e18b-413">**Steve Lasker. .NET Docker Development with Visual Studio (2017)** </span></span>\
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="3e18b-414">DockerFile에서 PowerShell 명령을 사용하여 Windows 컨테이너 설정</span><span class="sxs-lookup"><span data-stu-id="3e18b-414">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span>

<span data-ttu-id="3e18b-415">[Windows 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/about/index)를 사용하면 Docker 생태계의 나머지 부분과 동일한 도구로 기존 Windows 애플리케이션을 Docker 이미지로 변환하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-415">[Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/index) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="3e18b-416">Windows 컨테이너를 사용하려면 다음 예제와 같이 Dockerfile에서 PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-416">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM mcr.microsoft.com/windows/servercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="3e18b-417">이 예에서는 PowerShell 명령(RUN 설정)을 통해 Windows Server Core 기본 이미지(FROM 설정)를 사용하고 IIS를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-417">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="3e18b-418">비슷한 방법으로 PowerShell 명령을 사용하여 ASP.NET 4.x, .NET 4.6 또는 다른 Windows 소프트웨어 같은 추가 구성 요소를 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-418">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="3e18b-419">예를 들어 Dockerfile의 다음 명령은 ASP.NET 4.5를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3e18b-419">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="3e18b-420">추가 자료</span><span class="sxs-lookup"><span data-stu-id="3e18b-420">Additional resources</span></span>

- <span data-ttu-id="3e18b-421">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="3e18b-421">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="3e18b-422">Windows 기능을 포함하도록 dockerfile에서 실행되는 PowerShell 명령 예제.</span><span class="sxs-lookup"><span data-stu-id="3e18b-422">Example PowerShell commands to run from dockerfiles to include Windows features.</span></span>\
  <https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile>

>[!div class="step-by-step"]
><span data-ttu-id="3e18b-423">[이전](index.md)
>[다음](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="3e18b-423">[Previous](index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
