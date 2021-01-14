---
title: AKS/Kubernetes 클러스터에 Linux 컨테이너로 배포된 ASP.NET Core 애플리케이션 빌드
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기
ms.date: 01/06/2021
ms.openlocfilehash: 7a8f8272ab2faabd0398aeeb2039b6f034b4dedb
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970643"
---
# <a name="build-aspnet-core-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="2e0a4-103">AKS/Kubernetes 오케스트레이터에 Linux 컨테이너로 배포된 ASP.NET Core 애플리케이션 빌드</span><span class="sxs-lookup"><span data-stu-id="2e0a4-103">Build ASP.NET Core applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="2e0a4-104">AKS(Azure Kubernetes Service)는 컨테이너 배포 및 관리를 간소화하는 Azure의 관리형 Kubernetes 오케스트레이션 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="2e0a4-105">AKS의 주요 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-105">AKS main features are:</span></span>

- <span data-ttu-id="2e0a4-106">Azure에서 호스팅하는 제어 평면</span><span class="sxs-lookup"><span data-stu-id="2e0a4-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="2e0a4-107">자동화된 업그레이드</span><span class="sxs-lookup"><span data-stu-id="2e0a4-107">Automated upgrades</span></span>
- <span data-ttu-id="2e0a4-108">자동 복구</span><span class="sxs-lookup"><span data-stu-id="2e0a4-108">Self-healing</span></span>
- <span data-ttu-id="2e0a4-109">사용자 구성 가능 크기 조정</span><span class="sxs-lookup"><span data-stu-id="2e0a4-109">User-configurable scaling</span></span>
- <span data-ttu-id="2e0a4-110">개발자와 클러스터 운영자 모두에게 더 간단한 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="2e0a4-110">Simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="2e0a4-111">다음 예제에서는 Visual Studio 2019 버전 16.8을 사용하여 개발이 수행되는 동안 Linux에서 실행하고 Azure의 AKS 클러스터에 배포되는 ASP.NET Core 5.0 애플리케이션을 만들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-111">The following examples explore the creation of an ASP.NET Core 5.0 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2019 version 16.8.</span></span>

## <a name="creating-the-aspnet-core-project-using-visual-studio-2019"></a><span data-ttu-id="2e0a4-112">Visual Studio 2019를 사용하여 ASP.NET Core 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2e0a4-112">Creating the ASP.NET Core Project using Visual Studio 2019</span></span>

<span data-ttu-id="2e0a4-113">ASP.NET Core는 Microsoft 및 GitHub의 .NET 커뮤니티에서 유지 관리하는 범용 개발 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="2e0a4-114">Windows, macOS 및 Linux 플랫폼 간 교차 사용을 지원하며 디바이스, 클라우드 및 포함/IoT 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="2e0a4-115">이 예제에서는 Visual Studio 템플릿을 기준으로 하는 몇 가지 간단한 프로젝트를 사용하므로 샘플을 만들기 위한 추가 지식은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-115">This example uses a couple of simple projects based on Visual Studio templates, so you don't need much additional knowledge to create the sample.</span></span> <span data-ttu-id="2e0a4-116">표준 템플릿을 사용하여 프로젝트를 만들기만 하면 됩니다. 표준 템플릿에는 ASP.NET Core 5.0 기술을 사용하여 REST API 및 Razor 페이지가 있는 웹앱을 포함하는 소규모 프로젝트를 실행하기 위한 모든 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API and a Web App with Razor pages, using ASP.NET Core 5.0 technology.</span></span>

![Visual Studio에서 ASP.NET Core 웹 애플리케이션을 선택하는 새 프로젝트 창을 추가합니다.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-aspnet-core-application.png)

<span data-ttu-id="2e0a4-118">**그림 4-35**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-118">**Figure 4-35**.</span></span> <span data-ttu-id="2e0a4-119">Visual Studio 2019에서 ASP.NET Core 웹 애플리케이션 만들기.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-119">Creating an ASP.NET Core Web Application in Visual Studio 2019.</span></span>

<span data-ttu-id="2e0a4-120">Visual Studio에서 샘플 프로젝트를 만들려면 **파일** > **새로 만들기** > **프로젝트** 를 선택하고 **웹** 프로젝트 형식을 선택한 후 **ASP.NET Core 웹 애플리케이션** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project type and then the **ASP.NET Core Web Application** template.</span></span> <span data-ttu-id="2e0a4-121">필요한 경우 템플릿을 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-121">You can also search for the template if you need it.</span></span>

<span data-ttu-id="2e0a4-122">다음 이미지에 표시된 것처럼 애플리케이션 이름 및 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-122">Then enter the application name and location as shown in the next image.</span></span>

![프로젝트 이름 및 위치를 입력합니다.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/enter-project-name-and-location.png)

<span data-ttu-id="2e0a4-124">**그림 4-36**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-124">**Figure 4-36**.</span></span> <span data-ttu-id="2e0a4-125">Visual Studio 2019에서 프로젝트 이름 및 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-125">Enter the project name and location in Visual Studio 2019.</span></span>

<span data-ttu-id="2e0a4-126">ASP.NET Core 5.0을 프레임워크로 선택했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-126">Verify that you've selected ASP.NET Core 5.0 as the framework.</span></span> <span data-ttu-id="2e0a4-127">.NET Core 5.0은 Visual Studio 2019의 최신 릴리스에 포함되어 있으며 Visual Studio를 설치하면 자동으로 설치 및 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-127">.NET 5.0 is included in the latest release of Visual Studio 2019 and is automatically installed and configured for you when you install Visual Studio.</span></span>

![API 옵션이 선택된 상태에서 ASP.NET Core 웹 애플리케이션 유형을 선택하기 위한 Visual Studio 대화 상자](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-web-api-application.png)

<span data-ttu-id="2e0a4-129">**그림 4-37**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-129">**Figure 4-37**.</span></span> <span data-ttu-id="2e0a4-130">ASP.NET CORE 5.0 및 Web API 프로젝트 형식 선택</span><span class="sxs-lookup"><span data-stu-id="2e0a4-130">Selecting ASP.NET CORE 5.0 and Web API project type</span></span>

<span data-ttu-id="2e0a4-131">지금은 Docker 지원이 사용하도록 설정되어 있지 않으므로 프로젝트를 만든 후에 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-131">Notice Docker support is not enabled now, just to show it can be done after project creation.</span></span>

<span data-ttu-id="2e0a4-132">이전 버전의 .NET Core가 있는 경우 <https://dotnet.microsoft.com/download>에서 3.1 버전을 다운로드하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-132">If you have any previous version of .NET Core, you can download and install the 3.1 version from <https://dotnet.microsoft.com/download>.</span></span>

<span data-ttu-id="2e0a4-133">언제든지 프로젝트를 “Docker화”할 수 있는지 확인하기 위해 지금 Docker 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-133">To show you can "Dockerize" your project at any time, you'll add Docker support now.</span></span> <span data-ttu-id="2e0a4-134">솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **추가** > **Docker 지원** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-134">So right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![기존 프로젝트에 Docker 지원을 추가하는 바로 가기 메뉴 옵션: (프로젝트에서) 마우스 오른쪽 단추를 클릭하고 추가 > Docker 지원을 클릭합니다.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-docker-support-to-project.png)

<span data-ttu-id="2e0a4-136">**그림 4-38**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-136">**Figure 4-38**.</span></span> <span data-ttu-id="2e0a4-137">기존 프로젝트에 Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="2e0a4-137">Adding Docker support to an existing project</span></span>

<span data-ttu-id="2e0a4-138">Docker 지원 추가를 완료하려면 Windows 또는 Linux를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-138">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="2e0a4-139">이 경우 **Linux** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-139">In this case, select **Linux**.</span></span>

![Dockerfile에 대한 대상 OS를 선택하는 옵션 대화 상자](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-linux-docker-support.png)

<span data-ttu-id="2e0a4-141">**그림 4-39**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-141">**Figure 4-39**.</span></span> <span data-ttu-id="2e0a4-142">Linux 컨테이너 선택</span><span class="sxs-lookup"><span data-stu-id="2e0a4-142">Selecting Linux containers.</span></span>

<span data-ttu-id="2e0a4-143">이 간단한 단계를 수행하면 Linux 컨테이너에서 실행하는 ASP.NET Core 5.0 애플리케이션이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-143">With these simple steps, you have your ASP.NET Core 5.0 application running on a Linux container.</span></span>

<span data-ttu-id="2e0a4-144">여기에서는 자세히 설명하지 않지만 이와 비슷한 방식으로 간단한 **WebApp** 프로젝트를 추가하여(그림 4-40) 웹 API 엔드포인트를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-144">In a similar way, you can also add a very simple **WebApp** project (Figure 4-40) to consume the web API endpoint, although the details are not discussed here.</span></span>

<span data-ttu-id="2e0a4-145">그 이후에는 다음 이미지 4-40에 표시되는 것처럼 **WebApi** 프로젝트에 대한 오케스트레이터 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-145">After that, you add orchestrator support for your **WebApi** project as shown next, in image 4-40.</span></span>

![WebApi 프로젝트에 오케스트레이터 지원 추가](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-orchestrator-support.png)

<span data-ttu-id="2e0a4-147">**그림 4-40**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-147">**Figure 4-40**.</span></span> <span data-ttu-id="2e0a4-148">*WebApi* 프로젝트에 오케스트레이터 지원 추가</span><span class="sxs-lookup"><span data-stu-id="2e0a4-148">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="2e0a4-149">로컬 개발에 적절한 `Docker Compose` 옵션을 선택하는 경우 Visual Studio는 이미지 4-41에 표시된 대로 docker-compose 파일을 사용하여 docker-compose 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-149">When you choose the `Docker Compose` option, which is fine for local development, Visual Studio adds the docker-compose project, with the docker-compose files as shown in image 4-41.</span></span>

![솔루션에 추가된 docker-compose](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-compose-project-in-visual-studio.png)

<span data-ttu-id="2e0a4-151">**그림 4-41**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-151">**Figure 4-41**.</span></span> <span data-ttu-id="2e0a4-152">*WebApi* 프로젝트에 오케스트레이터 지원 추가</span><span class="sxs-lookup"><span data-stu-id="2e0a4-152">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="2e0a4-153">추가된 초기 파일은 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-153">The initial files added are similar to these ones:</span></span>

`docker-compose.yml`

```yml
version: "3.4"

services:
  webapi:
    image: ${DOCKER_REGISTRY-}webapi
    build:
      context: .
      dockerfile: WebApi/Dockerfile

  webapp:
    image: ${DOCKER_REGISTRY-}webapp
    build:
      context: .
      dockerfile: WebApp/Dockerfile
```

`docker-compose.override.yml`

```yml
version: "3.4"

services:
  webapi:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
  webapp:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
```

<span data-ttu-id="2e0a4-154">Docker Compose를 사용하여 앱을 실행하려면 `docker-compose.override.yml`을 약간만 조정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-154">To have you app running with Docker Compose you just have to make a few tweaks to `docker-compose.override.yml`</span></span>

```yml
services:
  webapi:
    #...
    ports:
      - "51080:80"
      - "51443:443"
    #...
  webapp:
    environment:
      #...
      - WebApiBaseAddress=http://webapi
    ports:
      - "50080:80"
      - "50443:443"
    #...
```

<span data-ttu-id="2e0a4-155">이제 이미지 4-42에 나와 있는 것처럼 **F5** 키를 누르거나, **재생** 단추 또는 **Ctrl+F5** 키를 사용하고 docker-compose 프로젝트를 선택하여 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-155">Now you can run your application with the **F5** key, or by using the **Play** button, or the **Ctrl+F5** key, selecting the docker-compose project, as shown in image 4-42.</span></span>

![Visual Studio를 사용하여 docker-compose 프로젝트 실행](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/running-docker-compose-with-visual-studio.png)

<span data-ttu-id="2e0a4-157">**그림 4-42**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-157">**Figure 4-42**.</span></span> <span data-ttu-id="2e0a4-158">*WebApi* 프로젝트에 오케스트레이터 지원 추가</span><span class="sxs-lookup"><span data-stu-id="2e0a4-158">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="2e0a4-159">설명된 대로 docker-compose 애플리케이션을 실행하는 경우 다음과 같은 결과를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-159">When running the docker-compose application as explained, you get:</span></span>

1. <span data-ttu-id="2e0a4-160">docker-compose 파일별로 빌드된 이미지 및 생성된 컨테이너.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-160">The images built and containers created as per the docker-compose file.</span></span>
2. <span data-ttu-id="2e0a4-161">브라우저는 `docker-compose` 프로젝트의 “속성” 대화 상자에 구성된 주소에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-161">The browser open in the address configured in the "Properties" dialog for the `docker-compose` project.</span></span>
3. <span data-ttu-id="2e0a4-162">**컨테이너** 창이 열립니다(Visual Studio 2019 버전 16.4 이상).</span><span class="sxs-lookup"><span data-stu-id="2e0a4-162">The **Container** window open (in Visual Studio 2019 version 16.4 and later).</span></span>
4. <span data-ttu-id="2e0a4-163">다음 이미지에 표시된 것처럼 솔루션의 모든 프로젝트에 대한 디버거 지원.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-163">Debugger support for all projects in the solution, as shown in the following images.</span></span>

<span data-ttu-id="2e0a4-164">열리는 브라우저:</span><span class="sxs-lookup"><span data-stu-id="2e0a4-164">Browser opened:</span></span>

![웹앱이 실행되는 브라우저 보기](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/browser-opened.png)

<span data-ttu-id="2e0a4-166">**그림 4-43**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-166">**Figure 4-43**.</span></span> <span data-ttu-id="2e0a4-167">애플리케이션이 여러 컨테이너에서 실행되는 브라우저 창.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-167">Browser window with an application running on multiple containers.</span></span>

<span data-ttu-id="2e0a4-168">컨테이너 창:</span><span class="sxs-lookup"><span data-stu-id="2e0a4-168">Containers window:</span></span>

![Visual Studio “컨테이너” 창](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/visual-studio-containers-window.png)

<span data-ttu-id="2e0a4-170">**그림 4-44**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-170">**Figure 4-44**.</span></span> <span data-ttu-id="2e0a4-171">Visual Studio “컨테이너” 창</span><span class="sxs-lookup"><span data-stu-id="2e0a4-171">Visual Studio "Containers" window</span></span>

<span data-ttu-id="2e0a4-172">**컨테이너** 창에서는 실행 중인 컨테이너를 보고, 사용할 수 있는 이미지를 찾아보고, 환경 변수, 로그 및 포트 매핑을 보고, 파일 시스템을 검사하고, 디버거를 연결하거나, 컨테이너 환경 내에서 터미널 창을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-172">The **Containers** window lets you view running containers, browse available images, view environment variables, logs, and port mappings, inspect the filesystem, attach a debugger, or open a terminal window inside the container environment.</span></span>

<span data-ttu-id="2e0a4-173">보다시피 Visual Studio 2019와 Docker는 개발자의 생산성을 최대한 높이는 방법으로 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-173">As you can see, the integration between Visual Studio 2019 and Docker is completely oriented to the developer's productivity.</span></span>

<span data-ttu-id="2e0a4-174">물론 `docker images` 명령을 사용하여 이미지를 나열할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-174">Of course, you can also list the images using the `docker images` command.</span></span> <span data-ttu-id="2e0a4-175">Visual Studio 2019를 통해 프로젝트를 자동 배포하여 만든 `webapi` 및 `webapp` 이미지에 `dev` 태그가 지정된 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-175">You should see the `webapi` and `webapp` images with the `dev` tags created by the automatic deployment of our project with Visual Studio 2019.</span></span>

```console
docker images
```

![Docker 이미지 명령의 콘솔 출력에 다음 정보를 포함하는 목록이 표시됩니다. 리포지토리, 태그, 이미지 ID, 만든 날짜 및 크기](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-images-command.png)

<span data-ttu-id="2e0a4-177">**그림 4-45**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-177">**Figure 4-45**.</span></span> <span data-ttu-id="2e0a4-178">Docker 이미지 보기</span><span class="sxs-lookup"><span data-stu-id="2e0a4-178">View of Docker images</span></span>

## <a name="register-the-solution-in-an-azure-container-registry-acr"></a><span data-ttu-id="2e0a4-179">ACR(Azure Container Registry)에 솔루션 등록</span><span class="sxs-lookup"><span data-stu-id="2e0a4-179">Register the Solution in an Azure Container Registry (ACR)</span></span>

<span data-ttu-id="2e0a4-180">ACR([Azure Container Registry](https://azure.microsoft.com/services/container-registry/))에 이미지를 업로드할 수 있지만 Docker Hub 또는 다른 레지스트리를 사용할 수도 있으므로 해당 레지스트리에서 AKS 클러스터에 이미지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-180">You can upload the images to the [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/), but you could also use Docker Hub or any other registry, so the images can be deployed to the AKS cluster from that registry.</span></span>

### <a name="create-an-acr-instance"></a><span data-ttu-id="2e0a4-181">ACR 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="2e0a4-181">Create an ACR instance</span></span>

<span data-ttu-id="2e0a4-182">**az cli** 에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-182">Run the following command from the **az cli**:</span></span>

```powershell
az acr create --name exploredocker --resource-group explore-docker-aks-rg --sku basic --admin-enabled
```

> [!NOTE]
> <span data-ttu-id="2e0a4-183">컨테이너 레지스트리 이름(예: `exploredocker`)은 Azure 내에서 고유해야 하며, 5~50자의 영숫자를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-183">The container registry name (e.g `exploredocker`) must be unique within Azure, and contain 5-50 alphanumeric characters.</span></span> <span data-ttu-id="2e0a4-184">자세한 내용은 [컨테이너 레지스트리 만들기](/azure/container-registry/container-registry-get-started-azure-cli#create-a-container-registry)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-184">For more details, refer [Create a container registry](/azure/container-registry/container-registry-get-started-azure-cli#create-a-container-registry)</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="2e0a4-185">릴리스 모드에서 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="2e0a4-185">Create the image in Release mode</span></span>

<span data-ttu-id="2e0a4-186">이제 그림 4-46과 같이 **릴리스** 로 변경하고 이전과 같은 방법으로 애플리케이션을 실행하여 **릴리스** 모드에서 (프로덕션 준비가 완료된) 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-186">You'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-46, and running the application as you did before.</span></span>

![릴리스 모드에서 빌드하기 위한 VS의 도구 모음 옵션](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-release-mode.png)

<span data-ttu-id="2e0a4-188">**그림 4-46**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-188">**Figure 4-46**.</span></span> <span data-ttu-id="2e0a4-189">릴리스 모드 선택</span><span class="sxs-lookup"><span data-stu-id="2e0a4-189">Selecting Release Mode</span></span>

<span data-ttu-id="2e0a4-190">`docker images` 명령을 실행하면 `debug`용(**dev**) 이미지 1개와 `release`용(**latest**) 이미지 1개로 이루어진 2개의 이미지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-190">If you execute the `docker images` command, you'll see both images created, one for `debug` (**dev**) and the other for `release` (**latest**) mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="2e0a4-191">이미지에 대한 새 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="2e0a4-191">Create a new Tag for the Image</span></span>

<span data-ttu-id="2e0a4-192">각 컨테이너 이미지에 레지스트리의 `loginServer` 이름으로 태그를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-192">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="2e0a4-193">이 태그는 컨테이너 이미지를 이미지 레지스트리에 밀어넣을 때 라우팅에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-193">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="2e0a4-194">Azure Portal에서 `loginServer` 이름을 보고 Azure Container Registry에서 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-194">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![브라우저 오른쪽 위의 Azure 컨테이너 레지스트리 이름 보기](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/loginServer-name.png)

<span data-ttu-id="2e0a4-196">**그림 4-47**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-196">**Figure 4-47**.</span></span> <span data-ttu-id="2e0a4-197">레지스트리의 이름 보기</span><span class="sxs-lookup"><span data-stu-id="2e0a4-197">View of the name of the Registry</span></span>

<span data-ttu-id="2e0a4-198">또는 다음 명령을 실행하여 이름을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-198">Or by running the following command:</span></span>

```console
az acr list --resource-group <resource-group-name> --query "[].{acrLoginServer:loginServer}" --output table
```

![위 명령의 콘솔 출력](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/az-cli-loginServer-name.png)

<span data-ttu-id="2e0a4-200">**그림 4-48**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-200">**Figure 4-48**.</span></span> <span data-ttu-id="2e0a4-201">**az cli** 를 사용하여 레지스트리의 이름 가져오기</span><span class="sxs-lookup"><span data-stu-id="2e0a4-201">Get the name of the registry using **az cli**</span></span>

<span data-ttu-id="2e0a4-202">두 경우 모두 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-202">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="2e0a4-203">이 예제의 경우 이름은 `exploredocker.azurecr.io`입니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-203">In our example, `exploredocker.azurecr.io`.</span></span>

<span data-ttu-id="2e0a4-204">이제 다음 명령을 사용하여 이미지에 태그를 지정하고 최신 이미지를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-204">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag <image-name>:latest <login-server-name>/<image-name>:v1
```

<span data-ttu-id="2e0a4-205">`docker tag` 명령을 실행한 후 `docker images` 명령을 사용하여 이미지를 나열하면 새 태그가 지정된 이미지가 보일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-205">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Docker 이미지 명령의 콘솔 출력](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/tagged-docker-images-list.png)

<span data-ttu-id="2e0a4-207">**그림 4-49**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-207">**Figure 4-49**.</span></span> <span data-ttu-id="2e0a4-208">태그가 지정된 이미지 보기</span><span class="sxs-lookup"><span data-stu-id="2e0a4-208">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="2e0a4-209">Azure ACR에 이미지 푸시</span><span class="sxs-lookup"><span data-stu-id="2e0a4-209">Push the image into the Azure ACR</span></span>

<span data-ttu-id="2e0a4-210">Azure Container Registry에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-210">Log in to the Azure Container Registry</span></span>

```console
az acr login --name exploredocker
```

<span data-ttu-id="2e0a4-211">다음 명령을 사용하여 이미지를 Azure ACR에 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-211">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push <login-server-name>/<image-name>:v1
```

<span data-ttu-id="2e0a4-212">이 명령은 이미지를 업로드하는 동안 다소 시간이 걸리지만 프로세스와 관련된 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-212">This command takes a while uploading the images but gives you feedback in the process.</span></span> <span data-ttu-id="2e0a4-213">다음 이미지에서 한 이미지의 출력은 완료되고 다른 이미지의 출력은 진행 중인 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-213">In the following image, you can see the output from one image completed and another in progress.</span></span>

![docker push 명령의 콘솔 출력입니다.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/uploading-docker-images-complete.png)

<span data-ttu-id="2e0a4-215">**그림 4-50**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-215">**Figure 4-50**.</span></span> <span data-ttu-id="2e0a4-216">push 명령의 콘솔 출력.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-216">Console output from the push command.</span></span>

<span data-ttu-id="2e0a4-217">다중 컨테이너 앱을 AKS 클러스터에 배포하려면 대부분의 속성을 `docker-compose.yml` 및 `docker-compose.override.yml` 파일에서 가져오는 일부 매니페스트 `.yaml` 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-217">To deploy your multi-container app into your AKS cluster you need some manifest `.yaml` files that have, most of the properties taken from the `docker-compose.yml` and `docker-compose.override.yml` files.</span></span>

#### `deploy-webapi.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapi
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapi
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapi
    spec:
      containers:
        - name: webapi
          image: exploredocker.azurecr.io/webapi:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
---
apiVersion: v1
kind: Service
metadata:
  name: webapi
  labels:
    app: weather-forecast
    service: webapi
spec:
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapi
```

#### `deploy-webapp.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapp
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapp
    spec:
      containers:
        - name: webapp
          image: exploredocker.azurecr.io/webapp:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
            - name: WebApiBaseAddress
              value: http://webapi
---
apiVersion: v1
kind: Service
metadata:
  name: webapp
  labels:
    app: weather-forecast
    service: webapp
spec:
  type: LoadBalancer
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapp
```

> [!NOTE]
> <span data-ttu-id="2e0a4-218">이전 `.yml` 파일은 `ASPNETCORE_URLS` 매개 변수를 사용하여 `HTTP` 포트만 사용하도록 설정하여 샘플 앱에서 누락된 인증서와 관련된 문제가 발생하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-218">The previous `.yml` files only enable the `HTTP` ports, using the `ASPNETCORE_URLS` parameter, to avoid issues with the missing certificate in the sample app.</span></span>

> [!TIP]
> <span data-ttu-id="2e0a4-219">이 가이드의 [**AKS(Azure Kubernetes Service)에 배포**](deploy-azure-kubernetes-service.md) 섹션에서 이 샘플에 대한 AKS 클러스터를 만드는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-219">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

<span data-ttu-id="2e0a4-220">이제 **kubectl** 을 사용하여 배포할 준비가 거의 완료되었지만 먼저 이 명령을 사용하여 AKS 클러스터에서 자격 증명을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-220">Now you're almost ready to deploy using **kubectl**, but first you must get the credentials from the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![위 명령의 콘솔 출력: C:\Users\Miguel.kube\config에서 “explore-docker-aks”가 현재 컨텍스트로 병합됩니다.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/getting-aks-credentials.png)

<span data-ttu-id="2e0a4-222">**그림 4-51**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-222">**Figure 4-51**.</span></span> <span data-ttu-id="2e0a4-223">AKS에서 kubectl 환경으로 자격 증명 가져오기.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-223">Getting credentials from AKS into the kubectl environment.</span></span>

<span data-ttu-id="2e0a4-224">또한 다음 명령을 사용하여 AKS 클러스터가 ACR에서 이미지를 끌어올 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-224">You also have to allow the AKS cluster to pull images from the ACR, using this command:</span></span>

```console
az aks update --name explore-docker-aks --resource-group explore-docker-aks-rg --attach-acr exploredocker
```

<span data-ttu-id="2e0a4-225">이전 명령은 완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-225">The previous command might take a couple of minutes to complete.</span></span> <span data-ttu-id="2e0a4-226">그런 다음, `kubectl apply` 명령을 사용하여 배포를 시작한 다음, `kubectl get all` 명령을 사용하여 클러스터 개체 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-226">Then, use the `kubectl apply` command to launch the deployments, and then `kubectl get all` get list the cluster objects.</span></span>

```console
kubectl apply -f deploy-webapi.yml
kubectl apply -f deploy-webapp.yml

kubectl get all
```

![위 명령의 콘솔 출력: 배포를 적용함.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubectl-apply-command.png)

<span data-ttu-id="2e0a4-229">**그림 4-52**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-229">**Figure 4-52**.</span></span> <span data-ttu-id="2e0a4-230">Kubernetes에 배포</span><span class="sxs-lookup"><span data-stu-id="2e0a4-230">Deployment to Kubernetes</span></span>

<span data-ttu-id="2e0a4-231">다음 이미지에 표시된 것처럼 부하 분산 장치에서 외부 IP를 가져올 때까지 잠시 기다렸다가 `kubectl get services`를 사용하여 확인합니다. 그러면 해당 주소에서 애플리케이션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-231">You'll have to wait a while until the load balancer gets the external IP, checking with `kubectl get services`, and then the application should be available at that address, as shown in the next image:</span></span>

![AKS에 배포된 애플리케이션의 브라우저 보기](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/aks-deployed-application.png)

<span data-ttu-id="2e0a4-233">**그림 4-53**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-233">**Figure 4-53**.</span></span> <span data-ttu-id="2e0a4-234">Kubernetes에 배포</span><span class="sxs-lookup"><span data-stu-id="2e0a4-234">Deployment to Kubernetes</span></span>

<span data-ttu-id="2e0a4-235">배포가 완료되면 ssh 터널을 사용하여 로컬 프록시를 통해 [Kubernetes 웹 UI](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-235">When the deployment completes, you can access the [Kubernetes Web UI](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) with a local proxy, using an ssh tunnel.</span></span>

<span data-ttu-id="2e0a4-236">먼저 다음 명령을 사용하여 ClusterRoleBinding을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-236">First you must create a ClusterRoleBinding with the following command:</span></span>

```console
kubectl create clusterrolebinding kubernetes-dashboard --clusterrole=cluster-admin --serviceaccount=kube-system:kubernetes-dashboard
```

<span data-ttu-id="2e0a4-237">그런 다음, 이 명령을 실행하여 프록시를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-237">And then this command to start the proxy:</span></span>

```console
az aks browse --resource-group exploredocker-aks-rg --name explore-docker-aks
```

<span data-ttu-id="2e0a4-238">브라우저 창이 다음과 비슷한 보기로 `http://127.0.0.1:8001`에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-238">A browser window should open at `http://127.0.0.1:8001` with a view similar to this one:</span></span>

![배포, Pod, 복제본 세트 및 서비스를 보여주는 Kubernetes 대시보드의 브라우저 보기](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubernetes-cluster-information.png)

<span data-ttu-id="2e0a4-240">**그림 4-54**.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-240">**Figure 4-54**.</span></span> <span data-ttu-id="2e0a4-241">Kubernetes 클러스터 정보 보기</span><span class="sxs-lookup"><span data-stu-id="2e0a4-241">View Kubernetes cluster information</span></span>

<span data-ttu-id="2e0a4-242">이제 ASP.NET Core 애플리케이션이 Linux 컨테이너에서 실행되며, Azure의 AKS 클러스터에 배포되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-242">Now you have your ASP.NET Core application, running in Linux containers, and deployed to an AKS cluster on Azure.</span></span>

> [!NOTE]
> <span data-ttu-id="2e0a4-243">Kubernetes를 사용한 배포에 대한 자세한 내용은 <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e0a4-243">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="2e0a4-244">[이전](set-up-windows-containers-with-powershell.md)
> [다음](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="2e0a4-244">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
