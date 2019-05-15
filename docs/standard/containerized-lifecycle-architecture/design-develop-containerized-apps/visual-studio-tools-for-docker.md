---
title: Visual Studio Tools for Windows의 Docker
description: Visual Studio 2017 버전 15.7 이상에서 사용할 수 있는 Docker 도구를 가져옵니다.
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 2b6fdc33f9cf850cf9e52fca4a1a9754cd412567
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644683"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a><span data-ttu-id="ba3d2-103">Windows의 Visual Studio 2017에서 사용 하 여 Docker 도구</span><span class="sxs-lookup"><span data-stu-id="ba3d2-103">Use Docker Tools in Visual Studio 2017 on Windows</span></span>

<span data-ttu-id="ba3d2-104">Visual Studio 2017 버전 15.7 이상에 포함 된 Docker 도구를 사용 하는 경우 개발자 워크플로 Visual Studio Code 및 Docker CLI를 사용 하 여 비슷합니다 (실제로 동일한 Docker CLI)를 기반 하지만 더 쉽게 시작 하는 것에 프로세스를 간소화 하 고 향상 된 생산성을 제공 합니다. 빌드를 실행 하 고 작업을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-104">The developer workflow when using the Docker Tools included in Visual Studio 2017 version 15.7 and later, is similar to using Visual Studio Code and Docker CLI (in fact, it's based on the same Docker CLI), but it's easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="ba3d2-105">또한 실행 및 디버그 하 여 컨테이너를 통해 일반적인 `F5` 고 `Ctrl+F5` Visual Studio에서 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-105">It can also run and debug your containers via the usual `F5` and `Ctrl+F5` keys from Visual Studio.</span></span> <span data-ttu-id="ba3d2-106">해당 컨테이너에서 동일한 정의 된 경우에 전체 솔루션을 디버깅할 수 있습니다 `docker-compose.yml` 솔루션 수준 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-106">You can even debug a whole solution if its containers are defined in the same `docker-compose.yml` file at the solution level.</span></span>

## <a name="configure-your-local-environment"></a><span data-ttu-id="ba3d2-107">로컬 환경 구성</span><span class="sxs-lookup"><span data-stu-id="ba3d2-107">Configure your local environment</span></span>

<span data-ttu-id="ba3d2-108">Docker에 대 한 Windows의 최신 버전을 계속 하려면 Docker 응용 프로그램 설치 프로그램은 다음 참조에 설명 된 대로 간단 하기 때문에 개발 보다 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-108">With the latest versions of Docker for Windows, it's easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

> [!TIP]
> <span data-ttu-id="ba3d2-109">로 Windows에 Docker를 설치 하는 방법에 대 한 자세한 내용은 (<https://docs.docker.com/docker-for-windows/>).</span><span class="sxs-lookup"><span data-stu-id="ba3d2-109">To learn more about installing Docker for Windows, go to (<https://docs.docker.com/docker-for-windows/>).</span></span>

## <a name="docker-support-in-visual-studio-2017"></a><span data-ttu-id="ba3d2-110">Visual Studio 2017에 docker 지원</span><span class="sxs-lookup"><span data-stu-id="ba3d2-110">Docker support in Visual Studio 2017</span></span>

<span data-ttu-id="ba3d2-111">두 가지 수준의 Docker 지원 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-111">There are two levels of Docker support you can add to a project.</span></span> <span data-ttu-id="ba3d2-112">ASP.NET Core 프로젝트에 추가 하기만 하면를 `Dockerfile` 파일을 프로젝트에 Docker 지원을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-112">In ASP.NET Core projects, you can just add a `Dockerfile` file to the project by enabling Docker support.</span></span> <span data-ttu-id="ba3d2-113">다음 수준이 추가 하는 컨테이너 오케스트레이션 지원 기능을 `Dockerfile` (이미 존재 하지 않는) 하는 경우 프로젝트에 및 `docker-compose.yml` 솔루션 수준 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-113">The next level is container orchestration support, which adds a `Dockerfile` to the project (if it doesn't already exist) and a `docker-compose.yml` file at the solution level.</span></span> <span data-ttu-id="ba3d2-114">Docker Compose를 통해 컨테이너 오케스트레이션을 지원, Visual Studio 2017 버전 15.0을 15.7에서에서 기본적으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-114">Container orchestration support, via Docker Compose, is added by default in Visual Studio 2017 versions 15.0 to 15.7.</span></span> <span data-ttu-id="ba3d2-115">컨테이너 오케스트레이션 지원은 Visual Studio 2017 버전 15.8 이상에 옵트인 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-115">Container orchestration support is an opt-in feature in Visual Studio 2017 versions 15.8 or later.</span></span> <span data-ttu-id="ba3d2-116">나중에는 버전 15.8 Docker Compose 및 Service Fabric을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-116">Version 15.8 an later support Docker Compose and Service Fabric.</span></span>

<span data-ttu-id="ba3d2-117">**추가 > Docker 지원** 하 고 **추가 > 컨테이너 오 케 스트레이 터 지원** 명령에는 ASP.NET Core 프로젝트에 대 한 프로젝트 노드의 오른쪽 클릭 메뉴 (또는 상황에 맞는 메뉴)에 위치한  **솔루션 탐색기**그림 4-31에서 표시 된 것 처럼:</span><span class="sxs-lookup"><span data-stu-id="ba3d2-117">The **Add > Docker Support** and **Add > Container Orchestrator Support** commands are located on the right-click menu (or context menu) of the project node for an ASP.NET Core project in **Solution Explorer**, as shown in Figure 4-31:</span></span>

![Visual Studio에서 Docker 지원 메뉴 옵션 추가](./media/add-docker-support-menu.png)

<span data-ttu-id="ba3d2-119">**그림 4-31**.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-119">**Figure 4-31**.</span></span> <span data-ttu-id="ba3d2-120">Visual Studio 2017 프로젝트에 Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="ba3d2-120">Adding Docker support to a Visual Studio 2017 project</span></span>

### <a name="add-docker-support"></a><span data-ttu-id="ba3d2-121">Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="ba3d2-121">Add Docker support</span></span>

<span data-ttu-id="ba3d2-122">선택 하 여 기존 ASP.NET Core 프로젝트에 Docker 지원을 추가할 수 있습니다 **추가** > **Docker 지원** 에서 **솔루션 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-122">You can add Docker support to an existing ASP.NET Core project by selecting **Add** > **Docker Support** in **Solution Explorer**.</span></span> <span data-ttu-id="ba3d2-123">또한 Docker 지원을 프로젝트를 만드는 동안 선택 하 여 사용할 수 있습니다 **Docker 지원 사용** 에 **새 ASP.NET Core 웹 응용 프로그램** 클릭 하면 열리는 대화 상자 **확인** 에 **새 프로젝트** 그림 4-32와 같이 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-123">You can also enable Docker support during project creation by selecting **Enable Docker Support** in the **New ASP.NET Core Web Application** dialog box that opens after you click **OK** in the **New Project** dialog box, as shown in Figure 4-32.</span></span>

![Visual Studio에서 새 ASP.NET Core 웹앱에 Docker 지원 사용](./media/enable-docker-support-visual-studio.png)

<span data-ttu-id="ba3d2-125">**그림 4-32**.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-125">**Figure 4-32**.</span></span> <span data-ttu-id="ba3d2-126">Visual Studio 2017에서 프로젝트를 만드는 동안 Docker 지원을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="ba3d2-126">Enable Docker support during project creation in Visual Studio 2017</span></span>

<span data-ttu-id="ba3d2-127">를 추가 하거나 Docker 지원을 사용 하도록 설정 하는 경우 Visual Studio 추가 된 *Dockerfile* 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-127">When you add or enable Docker support, Visual Studio adds a *Dockerfile* file to the project.</span></span>

> [!NOTE]
> <span data-ttu-id="ba3d2-128">그림 4-33과 같이 ASP.NET 프로젝트 (.NET Framework,.NET Core 프로젝트가 아니라)에 대 한 프로젝트를 만드는 동안 Docker Compose 지원을 사용 하면 컨테이너 오케스트레이션을 지원도 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-128">When you enable Docker Compose support during project creation for a ASP.NET project (.NET Framework, not a .NET Core project) as shown in Figure 4-33, container orchestration support is also added.</span></span>

![ASP.NET 프로젝트에 Docker Compose 지원 사용](media/enable-docker-compose-support.png)

<span data-ttu-id="ba3d2-130">**그림 4-33**.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-130">**Figure 4-33**.</span></span> <span data-ttu-id="ba3d2-131">Visual Studio 2017의 ASP.NET 프로젝트에 대 한 지원 Docker Compose를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="ba3d2-131">Enabling Docker Compose support for an ASP.NET project in Visual Studio 2017</span></span>

### <a name="add-container-orchestration-support"></a><span data-ttu-id="ba3d2-132">컨테이너 오케스트레이션을 지원 추가</span><span class="sxs-lookup"><span data-stu-id="ba3d2-132">Add container orchestration support</span></span>

<span data-ttu-id="ba3d2-133">다중 컨테이너 솔루션을 작성 하려는 경우 컨테이너 오케스트레이션을 지원 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-133">When you want to compose a multi-container solution, add container orchestration support to your projects.</span></span> <span data-ttu-id="ba3d2-134">이렇게 하면 실행 하 고 같은 정의 하는 경우 컨테이너 (전체 솔루션)의 그룹을 동시에 디버깅할 수 있습니다 *docker compose.yml* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-134">This lets you run and debug a group of containers (a whole solution) at the same time if they're defined in the same *docker-compose.yml* file.</span></span>

<span data-ttu-id="ba3d2-135">컨테이너 오케스트레이션을 지원 기능을 추가 하려면 마우스 오른쪽 단추로 클릭에서 솔루션 또는 프로젝트 노드 **솔루션 탐색기**, 선택한 **추가 > 컨테이너 오케스트레이션을 지원**합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-135">To add container orchestration support, right-click on the solution or project node in **Solution Explorer**, and choose **Add > Container Orchestration Support**.</span></span> <span data-ttu-id="ba3d2-136">선택한 **Docker Compose** 또는 **Service Fabric** 컨테이너를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-136">Then choose **Docker Compose** or **Service Fabric** to manage the containers.</span></span>

<span data-ttu-id="ba3d2-137">프로젝트에 추가 하는 Dockerfile 컨테이너 오케스트레이션을 지원 프로젝트에 추가한 후 표시와 **docker compose** 솔루션에 추가 하는 폴더 **솔루션 탐색기**그림 4-34와 같이:</span><span class="sxs-lookup"><span data-stu-id="ba3d2-137">After you add container orchestration support to your project, you see a Dockerfile added to the project and a **docker-compose** folder added to the solution in **Solution Explorer**, as shown in Figure 4-34:</span></span>

![Visual Studio의 솔루션 탐색기 내의 Docker 파일](media/docker-support-solution-explorer.png)

<span data-ttu-id="ba3d2-139">**그림 4-34**합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-139">**Figure 4-34**.</span></span> <span data-ttu-id="ba3d2-140">Visual Studio 2017의 솔루션 탐색기에서 docker 파일</span><span class="sxs-lookup"><span data-stu-id="ba3d2-140">Docker files in Solution Explorer in Visual Studio 2017</span></span>

<span data-ttu-id="ba3d2-141">*docker-compose.yml*이 이미 있는 경우에는 Visual Studio에서 이 파일에 필수 구성 코드 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-141">If *docker-compose.yml* already exists, Visual Studio just adds the required lines of configuration code to it.</span></span>

## <a name="configure-docker-tools"></a><span data-ttu-id="ba3d2-142">Docker 도구를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-142">Configure Docker tools</span></span>

<span data-ttu-id="ba3d2-143">주 메뉴에서 선택 **도구 > 옵션**를 확장 하 고 **컨테이너 도구 > 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-143">From the main menu, choose **Tools > Options**, and expand **Container Tools > Settings**.</span></span> <span data-ttu-id="ba3d2-144">컨테이너 도구 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-144">The container tools settings appear.</span></span>

![Visual Studio Docker 도구 옵션을 표시 합니다. 프로젝트 로드 시 필요한 Docker 이미지를 자동으로 풀, 자동으로 백그라운드에서 컨테이너를 시작, 솔루션 닫기, 컨테이너를 자동으로 종료 및 트러스팅 SSL 인증서에 대 한 메시지를 표시 하지 마십시오.](./media/visual-studio-docker-tools-options.png)

<span data-ttu-id="ba3d2-146">**그림 4-35**합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-146">**Figure 4-35**.</span></span> <span data-ttu-id="ba3d2-147">Docker 도구 옵션</span><span class="sxs-lookup"><span data-stu-id="ba3d2-147">Docker Tools Options</span></span>

<span data-ttu-id="ba3d2-148">다음 표에서 이러한 옵션을 설정 하는 방법을 결정 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-148">The following table might help you decide how to set these options.</span></span>

| <span data-ttu-id="ba3d2-149">이름</span><span class="sxs-lookup"><span data-stu-id="ba3d2-149">Name</span></span> | <span data-ttu-id="ba3d2-150">기본 설정</span><span class="sxs-lookup"><span data-stu-id="ba3d2-150">Default Setting</span></span> | <span data-ttu-id="ba3d2-151">적용 대상</span><span class="sxs-lookup"><span data-stu-id="ba3d2-151">Applies To</span></span> | <span data-ttu-id="ba3d2-152">설명</span><span class="sxs-lookup"><span data-stu-id="ba3d2-152">Description</span></span> |
| -----|:---------------:|:----------:| ----------- |
| <span data-ttu-id="ba3d2-153">프로젝트 로드 시 필요한 Docker 이미지를 자동으로 풀</span><span class="sxs-lookup"><span data-stu-id="ba3d2-153">Automatically pull required Docker images on project load</span></span> | <span data-ttu-id="ba3d2-154">켜기</span><span class="sxs-lookup"><span data-stu-id="ba3d2-154">On</span></span> | <span data-ttu-id="ba3d2-155">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="ba3d2-155">Docker Compose</span></span> | <span data-ttu-id="ba3d2-156">성능 향상된을 위한 프로젝트를 로드할 때 Visual Studio는 Docker 가져오기 작업을 백그라운드에서 시작 이미지가 이미 다운로드 될 때 코드를 실행할 준비가 되도록 또는 다운로드 프로세스.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-156">For increased performance when loading projects, Visual Studio will start a Docker pull operation in the background so that when you're ready to run your code, the image is already downloaded or in the process of downloading.</span></span> <span data-ttu-id="ba3d2-157">방금 프로젝트를 로드 하 고 코드를 검색, 경우 해제할 수 있습니다이 필요 하지 않습니다 하는 컨테이너 이미지 다운로드를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-157">If you're just loading projects and browsing code, you can turn this off to avoid downloading container images you don't need.</span></span> |
| <span data-ttu-id="ba3d2-158">백그라운드에서 컨테이너를 자동으로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-158">Automatically start containers in background</span></span> | <span data-ttu-id="ba3d2-159">켜기</span><span class="sxs-lookup"><span data-stu-id="ba3d2-159">On</span></span> | <span data-ttu-id="ba3d2-160">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="ba3d2-160">Docker Compose</span></span> | <span data-ttu-id="ba3d2-161">다시 성능 향상된을 위해 Visual Studio 컨테이너를 만듭니다 볼륨 탑재를 사용 하 여 빌드하고 컨테이너를 실행 하는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-161">Again for increased performance, Visual Studio creates a container with volume mounts ready for when you build and run your container.</span></span> <span data-ttu-id="ba3d2-162">컨테이너를 만들 때 제어 하려는 경우이 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-162">If you want to control when your container is created, turn this off.</span></span> |
| <span data-ttu-id="ba3d2-163">Kill 컨테이너 솔루션에 자동으로 닫기</span><span class="sxs-lookup"><span data-stu-id="ba3d2-163">Automatically kill containers on solution close</span></span> | <span data-ttu-id="ba3d2-164">켜기</span><span class="sxs-lookup"><span data-stu-id="ba3d2-164">On</span></span> | <span data-ttu-id="ba3d2-165">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="ba3d2-165">Docker Compose</span></span> | <span data-ttu-id="ba3d2-166">이 기능을 끌 솔루션을 닫기 또는 Visual Studio를 닫은 후에 계속 실행 하기 위해 솔루션에 대 한 컨테이너를 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-166">Turn this off if you would like containers for your solution to continue to run after closing the solution or closing Visual Studio.</span></span> |
| <span data-ttu-id="ba3d2-167">Localhost SSL 인증서 신뢰에 대 한 확인 안 함</span><span class="sxs-lookup"><span data-stu-id="ba3d2-167">Do not prompt for trusting localhost SSL certificate</span></span> | <span data-ttu-id="ba3d2-168">끄기</span><span class="sxs-lookup"><span data-stu-id="ba3d2-168">Off</span></span> | <span data-ttu-id="ba3d2-169">ASP.NET Core 2.2 프로젝트</span><span class="sxs-lookup"><span data-stu-id="ba3d2-169">ASP.NET Core 2.2 projects</span></span> | <span data-ttu-id="ba3d2-170">Localhost SSL 인증서를 신뢰할 수 없는 경우 Visual Studio 묻는 프로젝트를 실행할 때마다이 확인란을 선택 하지 않으면.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-170">If the localhost SSL certificate is not trusted, Visual Studio will prompt every time you run your project, unless this checkbox is checked.</span></span> |

> [!WARNING]
> <span data-ttu-id="ba3d2-171">Localhost SSL 인증서가 신뢰할 수 있는 메시지를 표시 하지 않으려면 확인란을 HTTPS 요청을 웹 앱 또는 서비스에서 런타임에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-171">If the localhost SSL certificate is not trusted, and you check the box to suppress prompting, then HTTPS web requests might fail at runtime in your app or service.</span></span> <span data-ttu-id="ba3d2-172">이런 경우의 선택을 취소 합니다 **표시 안 함** 확인란 프로젝트를 실행 하 고 신뢰 프롬프트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-172">In that case, uncheck the **Do not prompt** checkbox, run your project, and indicate trust at the prompt.</span></span>

> [!TIP]
> <span data-ttu-id="ba3d2-173">서비스 구현 및 Visual Studio Tools for Docker 사용에 자세한 내용은 다음 문서를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3d2-173">For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>
>
><span data-ttu-id="ba3d2-174">로컬 Docker 컨테이너에서 앱을 디버깅 합니다. <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh></span><span class="sxs-lookup"><span data-stu-id="ba3d2-174">Debugging apps in a local Docker container: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh></span></span>
>
><span data-ttu-id="ba3d2-175">Visual Studio를 사용 하 여 컨테이너 레지스트리에 ASP.NET 컨테이너를 배포 합니다. <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker></span><span class="sxs-lookup"><span data-stu-id="ba3d2-175">Deploy an ASP.NET container to a container registry using Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker></span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ba3d2-176">[이전](docker-apps-inner-loop-workflow.md)
>[다음](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="ba3d2-176">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>
