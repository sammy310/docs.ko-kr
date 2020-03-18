---
title: Windows의 Visual Studio Tools for Docker
description: Visual Studio 2017 버전 15.7 이상에서 사용할 수 있는 Docker 도구를 알아봅니다.
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 2b6fdc33f9cf850cf9e52fca4a1a9754cd412567
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "68673880"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a><span data-ttu-id="78581-103">Windows에서 Visual Studio 2017의 Docker 도구 사용</span><span class="sxs-lookup"><span data-stu-id="78581-103">Use Docker Tools in Visual Studio 2017 on Windows</span></span>

<span data-ttu-id="78581-104">Visual Studio 2017 버전 15.7 이상에 포함된 Docker 도구를 사용하는 경우 개발자 워크플로는 Visual Studio Code 및 Docker CLI를 사용할 때와 비슷하지만(실제로 동일한 Docker CLI 기반), 더 쉽게 시작할 수 있고, 프로세스가 더 간단하고, 빌드/실행/구성 작업의 생산성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="78581-104">The developer workflow when using the Docker Tools included in Visual Studio 2017 version 15.7 and later, is similar to using Visual Studio Code and Docker CLI (in fact, it's based on the same Docker CLI), but it's easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="78581-105">또한 Visual Studio의 일반적인 `F5` 및 `Ctrl+F5` 키를 통해 컨테이너를 실행하고 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78581-105">It can also run and debug your containers via the usual `F5` and `Ctrl+F5` keys from Visual Studio.</span></span> <span data-ttu-id="78581-106">컨테이너가 솔루션 수준에서 동일한 `docker-compose.yml` 파일에 정의된 경우 솔루션 전체를 디버그할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78581-106">You can even debug a whole solution if its containers are defined in the same `docker-compose.yml` file at the solution level.</span></span>

## <a name="configure-your-local-environment"></a><span data-ttu-id="78581-107">로컬 환경 구성</span><span class="sxs-lookup"><span data-stu-id="78581-107">Configure your local environment</span></span>

<span data-ttu-id="78581-108">최신 버전의 Windows용 Docker를 사용하면 다음 참고 자료에 설명된 것처럼 설정 방법이 간단하므로 이전보다 훨씬 쉽게 Docker 애플리케이션을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78581-108">With the latest versions of Docker for Windows, it's easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

> [!TIP]
> <span data-ttu-id="78581-109">Windows용 Docker 설치 방법에 대한 자세한 내용은 <https://docs.docker.com/docker-for-windows/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78581-109">To learn more about installing Docker for Windows, go to (<https://docs.docker.com/docker-for-windows/>).</span></span>

## <a name="docker-support-in-visual-studio-2017"></a><span data-ttu-id="78581-110">Visual Studio 2017의 Docker 지원</span><span class="sxs-lookup"><span data-stu-id="78581-110">Docker support in Visual Studio 2017</span></span>

<span data-ttu-id="78581-111">두 가지 수준의 Docker 지원을 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78581-111">There are two levels of Docker support you can add to a project.</span></span> <span data-ttu-id="78581-112">ASP.NET Core 프로젝트에서는 Docker 지원을 설정하여 `Dockerfile` 파일을 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78581-112">In ASP.NET Core projects, you can just add a `Dockerfile` file to the project by enabling Docker support.</span></span> <span data-ttu-id="78581-113">그 다음 수준은 솔루션 수준에서 `Dockerfile`을 프로젝트에 추가하고(없는 경우) `docker-compose.yml` 파일을 추가하는 컨테이너 오케스트레이션 지원입니다.</span><span class="sxs-lookup"><span data-stu-id="78581-113">The next level is container orchestration support, which adds a `Dockerfile` to the project (if it doesn't already exist) and a `docker-compose.yml` file at the solution level.</span></span> <span data-ttu-id="78581-114">Docker Compose를 통한 컨테이너 오케스트레이션 지원은 Visual Studio 2017 버전 15.0~15.7에서 기본적으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="78581-114">Container orchestration support, via Docker Compose, is added by default in Visual Studio 2017 versions 15.0 to 15.7.</span></span> <span data-ttu-id="78581-115">컨테이너 오케스트레이션 지원은 Visual Studio 2017 버전 15.8 이상에서 제공하는 옵트인 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="78581-115">Container orchestration support is an opt-in feature in Visual Studio 2017 versions 15.8 or later.</span></span> <span data-ttu-id="78581-116">버전 15.8 이상에서는 Docker Compose 및 Service Fabric을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="78581-116">Version 15.8 an later support Docker Compose and Service Fabric.</span></span>

<span data-ttu-id="78581-117">**추가 > Docker 지원** 및 **추가 > 컨테이너 오케스트레이터 지원** 명령은 그림 4-31처럼 **솔루션 탐색기**에서 ASP.NET Core 프로젝트의 프로젝트 노드를 오른쪽 단추로 클릭하면 나타나는 메뉴(또는 팝업 메뉴)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78581-117">The **Add > Docker Support** and **Add > Container Orchestrator Support** commands are located on the right-click menu (or context menu) of the project node for an ASP.NET Core project in **Solution Explorer**, as shown in Figure 4-31:</span></span>

![Visual Studio에서 Docker 지원 메뉴 옵션 추가](./media/add-docker-support-menu.png)

<span data-ttu-id="78581-119">**그림 4-31**.</span><span class="sxs-lookup"><span data-stu-id="78581-119">**Figure 4-31**.</span></span> <span data-ttu-id="78581-120">Visual Studio 2017 프로젝트에 Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="78581-120">Adding Docker support to a Visual Studio 2017 project</span></span>

### <a name="add-docker-support"></a><span data-ttu-id="78581-121">Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="78581-121">Add Docker support</span></span>

<span data-ttu-id="78581-122">**솔루션 탐색기**에서 **추가** > **Docker 지원**을 선택하여 기존 ASP.NET Core 프로젝트에 Docker 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78581-122">You can add Docker support to an existing ASP.NET Core project by selecting **Add** > **Docker Support** in **Solution Explorer**.</span></span> <span data-ttu-id="78581-123">프로젝트를 만드는 동안 그림 4-32처럼 **새 프로젝트**에서 **확인**을 클릭하면 열리는 **새 ASP.NET Core 웹 애플리케이션** 대화 상자에서 **Docker 지원 사용**을 선택하여 Docker를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78581-123">You can also enable Docker support during project creation by selecting **Enable Docker Support** in the **New ASP.NET Core Web Application** dialog box that opens after you click **OK** in the **New Project** dialog box, as shown in Figure 4-32.</span></span>

![Visual Studio에서 새 ASP.NET Core 웹앱에 Docker 지원 사용](./media/enable-docker-support-visual-studio.png)

<span data-ttu-id="78581-125">**그림 4-32**.</span><span class="sxs-lookup"><span data-stu-id="78581-125">**Figure 4-32**.</span></span> <span data-ttu-id="78581-126">Visual Studio 2017에서 프로젝트를 만드는 동안 Docker 지원을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="78581-126">Enable Docker support during project creation in Visual Studio 2017</span></span>

<span data-ttu-id="78581-127">Docker 지원을 추가하거나 사용하도록 설정하면 Visual Studio가 프로젝트에 *Dockerfile* 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="78581-127">When you add or enable Docker support, Visual Studio adds a *Dockerfile* file to the project.</span></span>

> [!NOTE]
> <span data-ttu-id="78581-128">그림 4-33처럼 ASP.NET 프로젝트(.NET Core가 아닌 .NET Framework 프로젝트)에 사용할 프로젝트를 만드는 동안 Docker Compose 지원을 사용하도록 설정하면 컨테이너 오케스트레이션 지원도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="78581-128">When you enable Docker Compose support during project creation for a ASP.NET project (.NET Framework, not a .NET Core project) as shown in Figure 4-33, container orchestration support is also added.</span></span>

![ASP.NET 프로젝트에 Docker Compose 지원 사용](media/enable-docker-compose-support.png)

<span data-ttu-id="78581-130">**그림 4-33**.</span><span class="sxs-lookup"><span data-stu-id="78581-130">**Figure 4-33**.</span></span> <span data-ttu-id="78581-131">Visual Studio 2017에서 ASP.NET 프로젝트에 Docker Compose 지원 사용</span><span class="sxs-lookup"><span data-stu-id="78581-131">Enabling Docker Compose support for an ASP.NET project in Visual Studio 2017</span></span>

### <a name="add-container-orchestration-support"></a><span data-ttu-id="78581-132">컨테이너 오케스트레이션 지원 추가</span><span class="sxs-lookup"><span data-stu-id="78581-132">Add container orchestration support</span></span>

<span data-ttu-id="78581-133">다중 컨테이너 솔루션을 작성하려면 프로젝트에 컨테이너 오케스트레이션 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="78581-133">When you want to compose a multi-container solution, add container orchestration support to your projects.</span></span> <span data-ttu-id="78581-134">이렇게 하면 동일한 *docker-compose.yml* 파일에 정의된 컨테이너 그룹(전체 솔루션)을 동시에 실행하고 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78581-134">This lets you run and debug a group of containers (a whole solution) at the same time if they're defined in the same *docker-compose.yml* file.</span></span>

<span data-ttu-id="78581-135">컨테이너 오케스트레이션 지원을 추가하려면 **솔루션 탐색기**에서 솔루션 또는 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **추가 > 컨테이너 오케스트레이션 지원**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78581-135">To add container orchestration support, right-click on the solution or project node in **Solution Explorer**, and choose **Add > Container Orchestration Support**.</span></span> <span data-ttu-id="78581-136">그런 다음, 컨테이너를 관리할 **Docker Compose** 또는 **Service Fabric**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78581-136">Then choose **Docker Compose** or **Service Fabric** to manage the containers.</span></span>

<span data-ttu-id="78581-137">프로젝트에 컨테이너 오케스트레이션 지원을 추가한 후에는 그림 4-34처럼 **솔루션 탐색기**에서 Dockerfile이 프로젝트에 추가되고 **docker-compose** 폴더가 솔루션에 추가된 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78581-137">After you add container orchestration support to your project, you see a Dockerfile added to the project and a **docker-compose** folder added to the solution in **Solution Explorer**, as shown in Figure 4-34:</span></span>

![Visual Studio의 솔루션 탐색기 내의 Docker 파일](media/docker-support-solution-explorer.png)

<span data-ttu-id="78581-139">**그림 4-34**.</span><span class="sxs-lookup"><span data-stu-id="78581-139">**Figure 4-34**.</span></span> <span data-ttu-id="78581-140">Visual Studio 2017 솔루션 탐색기의 Docker 파일</span><span class="sxs-lookup"><span data-stu-id="78581-140">Docker files in Solution Explorer in Visual Studio 2017</span></span>

<span data-ttu-id="78581-141">*docker-compose.yml*이 이미 있는 경우에는 Visual Studio에서 이 파일에 필수 구성 코드 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="78581-141">If *docker-compose.yml* already exists, Visual Studio just adds the required lines of configuration code to it.</span></span>

## <a name="configure-docker-tools"></a><span data-ttu-id="78581-142">Docker 도구 구성</span><span class="sxs-lookup"><span data-stu-id="78581-142">Configure Docker tools</span></span>

<span data-ttu-id="78581-143">주 메뉴에서 **도구 > 옵션**을 선택하고, **컨테이너 도구 > 설정**을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="78581-143">From the main menu, choose **Tools > Options**, and expand **Container Tools > Settings**.</span></span> <span data-ttu-id="78581-144">그러면 컨테이너 도구 설정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78581-144">The container tools settings appear.</span></span>

![다음을 보여주는 Visual Studio Docker 도구 옵션: 프로젝트 로드 시 필요한 Docker 이미지를 자동으로 끌어오기, 백그라운드에서 자동으로 컨테이너 시작, 솔루션이 닫히면 자동으로 컨테이너 종료, 신뢰할 수 있는 SSL 인증서에는 메시지를 표시하지 않기](./media/visual-studio-docker-tools-options.png)

<span data-ttu-id="78581-146">**그림 4-35**.</span><span class="sxs-lookup"><span data-stu-id="78581-146">**Figure 4-35**.</span></span> <span data-ttu-id="78581-147">Docker 도구 옵션</span><span class="sxs-lookup"><span data-stu-id="78581-147">Docker Tools Options</span></span>

<span data-ttu-id="78581-148">다음 표는 이러한 옵션을 설정하는 방법을 결정하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78581-148">The following table might help you decide how to set these options.</span></span>

| <span data-ttu-id="78581-149">이름</span><span class="sxs-lookup"><span data-stu-id="78581-149">Name</span></span> | <span data-ttu-id="78581-150">기본 설정</span><span class="sxs-lookup"><span data-stu-id="78581-150">Default Setting</span></span> | <span data-ttu-id="78581-151">적용 대상</span><span class="sxs-lookup"><span data-stu-id="78581-151">Applies To</span></span> | <span data-ttu-id="78581-152">설명</span><span class="sxs-lookup"><span data-stu-id="78581-152">Description</span></span> |
| -----|:---------------:|:----------:| ----------- |
| <span data-ttu-id="78581-153">프로젝트 로드 시 필요한 Docker 이미지를 자동으로 끌어오기</span><span class="sxs-lookup"><span data-stu-id="78581-153">Automatically pull required Docker images on project load</span></span> | <span data-ttu-id="78581-154">켜기</span><span class="sxs-lookup"><span data-stu-id="78581-154">On</span></span> | <span data-ttu-id="78581-155">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="78581-155">Docker Compose</span></span> | <span data-ttu-id="78581-156">프로젝트를 로드할 때 성능을 향상하기 위해 Visual Studio는 백그라운드에서 Docker 끌어오기 작업을 수행합니다. 이렇게 하면 코드를 실행할 준비가 되었을 때 이미지가 이미 다운로드되어 있거나 다운로드 중입니다.</span><span class="sxs-lookup"><span data-stu-id="78581-156">For increased performance when loading projects, Visual Studio will start a Docker pull operation in the background so that when you're ready to run your code, the image is already downloaded or in the process of downloading.</span></span> <span data-ttu-id="78581-157">단순히 프로젝트를 로드하고 코드를 검색하려는 경우에는 불필요한 컨테이너 이미지를 다운로드하지 않도록 이 기능을 끄면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78581-157">If you're just loading projects and browsing code, you can turn this off to avoid downloading container images you don't need.</span></span> |
| <span data-ttu-id="78581-158">백그라운드에서 자동으로 컨테이너 시작</span><span class="sxs-lookup"><span data-stu-id="78581-158">Automatically start containers in background</span></span> | <span data-ttu-id="78581-159">켜기</span><span class="sxs-lookup"><span data-stu-id="78581-159">On</span></span> | <span data-ttu-id="78581-160">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="78581-160">Docker Compose</span></span> | <span data-ttu-id="78581-161">마찬가지로 성능을 향상하기 위해 Visual Studio는 개발자가 컨테이너를 빌드하고 실행할 때 볼륨 탑재가 완료된 컨테이너를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="78581-161">Again for increased performance, Visual Studio creates a container with volume mounts ready for when you build and run your container.</span></span> <span data-ttu-id="78581-162">컨테이너를 만드는 시기를 제어하려면 이 기능을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="78581-162">If you want to control when your container is created, turn this off.</span></span> |
| <span data-ttu-id="78581-163">솔루션이 닫히면 자동으로 컨테이너 종료</span><span class="sxs-lookup"><span data-stu-id="78581-163">Automatically kill containers on solution close</span></span> | <span data-ttu-id="78581-164">켜기</span><span class="sxs-lookup"><span data-stu-id="78581-164">On</span></span> | <span data-ttu-id="78581-165">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="78581-165">Docker Compose</span></span> | <span data-ttu-id="78581-166">솔루션을 닫거나 Visual Studio를 닫은 후에도 솔루션의 컨테이너를 계속 실행하려면 이 기능을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="78581-166">Turn this off if you would like containers for your solution to continue to run after closing the solution or closing Visual Studio.</span></span> |
| <span data-ttu-id="78581-167">신뢰할 수 있는 localhost SSL 인증서에는 메시지를 표시하지 않기</span><span class="sxs-lookup"><span data-stu-id="78581-167">Do not prompt for trusting localhost SSL certificate</span></span> | <span data-ttu-id="78581-168">끄기</span><span class="sxs-lookup"><span data-stu-id="78581-168">Off</span></span> | <span data-ttu-id="78581-169">ASP.NET Core 2.2 프로젝트</span><span class="sxs-lookup"><span data-stu-id="78581-169">ASP.NET Core 2.2 projects</span></span> | <span data-ttu-id="78581-170">localhost SSL 인증서를 신뢰할 수 없는 경우 이 확인란을 선택하지 않으면 프로젝트를 실행할 때마다 Visual Studio가 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="78581-170">If the localhost SSL certificate is not trusted, Visual Studio will prompt every time you run your project, unless this checkbox is checked.</span></span> |

> [!WARNING]
> <span data-ttu-id="78581-171">localhost SSL 인증서를 신뢰할 수 없고 메시지를 표시하지 않는 확인란을 선택하면 런타임에 앱 또는 서비스에서 HTTPS 웹 요청이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78581-171">If the localhost SSL certificate is not trusted, and you check the box to suppress prompting, then HTTPS web requests might fail at runtime in your app or service.</span></span> <span data-ttu-id="78581-172">이 경우 **메시지 표시 안 함** 확인란을 선택 취소하고, 프롬프트에서 신뢰를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="78581-172">In that case, uncheck the **Do not prompt** checkbox, run your project, and indicate trust at the prompt.</span></span>

> [!TIP]
> <span data-ttu-id="78581-173">서비스 구현 및 Visual Studio Tools for Docker 사용에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78581-173">For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>
>
><span data-ttu-id="78581-174">로컬 Docker 컨테이너에서 앱 디버깅: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh></span><span class="sxs-lookup"><span data-stu-id="78581-174">Debugging apps in a local Docker container: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh></span></span>
>
><span data-ttu-id="78581-175">Visual Studio를 사용하여 컨테이너 레지스트리에 ASP.NET 컨테이너 배포: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker></span><span class="sxs-lookup"><span data-stu-id="78581-175">Deploy an ASP.NET container to a container registry using Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker></span></span>

>[!div class="step-by-step"]
><span data-ttu-id="78581-176">[이전](docker-apps-inner-loop-workflow.md)
>[다음](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="78581-176">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>
