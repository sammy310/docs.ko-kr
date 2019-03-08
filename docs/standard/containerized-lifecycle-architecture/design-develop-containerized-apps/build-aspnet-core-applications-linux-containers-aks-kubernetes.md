---
title: Linux 컨테이너와 AKS/Kubernetes 클러스터에 배포 하는 ASP.NET Core 2.1 응용 프로그램 빌드
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/25/2019
ms.openlocfilehash: c6d778d345466b1b852d06bc01ce40ccfdebf964
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676657"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="ac4e5-103">Linux 컨테이너와 AKS/Kubernetes 오 케 스트레이 터에 배포 하는 ASP.NET Core 2.1 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="ac4e5-103">Build ASP.NET Core 2.1 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="ac4e5-104">Azure Kubernetes 서비스 (AKS)는 Azure의 관리 되는 Kubernetes 오케스트레이션 서비스 컨테이너 배포 및 관리를 간소화 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="ac4e5-105">AKS 주요 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-105">AKS main features are:</span></span>

- <span data-ttu-id="ac4e5-106">Azure 호스팅된 컨트롤 평면</span><span class="sxs-lookup"><span data-stu-id="ac4e5-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="ac4e5-107">자동된 업그레이드</span><span class="sxs-lookup"><span data-stu-id="ac4e5-107">Automated upgrades</span></span>
- <span data-ttu-id="ac4e5-108">자동 복구</span><span class="sxs-lookup"><span data-stu-id="ac4e5-108">Self-healing</span></span>
- <span data-ttu-id="ac4e5-109">사용자 구성 가능한 크기 조정</span><span class="sxs-lookup"><span data-stu-id="ac4e5-109">User configurable scaling</span></span>
- <span data-ttu-id="ac4e5-110">개발자와 클러스터 운영자 모두에 대 한 간단한 사용자 환경.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="ac4e5-111">Linux에서 실행 되 고 개발은 수행 하는 동안 Azure에서 AKS 클러스터를 배포 하는 ASP.NET Core 2.1 응용 프로그램 만들기를 탐색 하는 다음 예제에서는 Visual Studio 2017을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-111">The following examples explore the creation of an ASP.NET Core 2.1 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a><span data-ttu-id="ac4e5-112">Visual Studio 2017을 사용 하 여 ASP.NET Core 2.1 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="ac4e5-112">Creating the ASP.NET Core 2.1 Project using Visual Studio 2017</span></span>

<span data-ttu-id="ac4e5-113">ASP.NET Core는 Microsoft 및 GitHub의.NET 커뮤니티에서 유지 관리 하는 범용 개발 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="ac4e5-114">플랫폼 간, Windows, macOS 및 Linux를 지원 하며 장치, 클라우드 및 포함 된 IoT 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="ac4e5-115">이 예제에서는 샘플을 만드는 모든 추가 정보를 표시 하지 않아도 되므로 Visual Studio Web API 템플릿을 기반으로 하는 간단한 프로젝트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-115">This example uses a simple project that's based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="ac4e5-116">ASP.NET Core 2.1 기술을 사용 하 여 REST API를 사용 하 여 작은 프로젝트를 실행 하려면 모든 요소를 포함 하는 표준 템플릿을 사용 하 여 프로젝트를 만들려면 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.1 technology.</span></span>

![ASP.NET Core 웹 응용 프로그램을 선택 하면 Visual Studio에서 새 프로젝트 창을 추가 합니다.](media/create-aspnet-core-application.png)

<span data-ttu-id="ac4e5-118">**그림 4-36**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-118">**Figure 4-36**.</span></span> <span data-ttu-id="ac4e5-119">ASP.NET Core 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="ac4e5-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="ac4e5-120">Visual Studio에서 샘플 프로젝트를 만들려면 **파일** > **새로 만들기** > **프로젝트**을 선택 합니다 **웹**프로젝트 형식 뒤에 왼쪽된 창에서 **ASP.NET Core 웹 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="ac4e5-121">Visual Studio 웹 프로젝트에 대 한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="ac4e5-122">예를 들어 선택 **API** ASP.NET 웹 API 응용 프로그램을 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="ac4e5-123">ASP.NET Core 2.1 프레임 워크로 선택 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-123">Verify that you've selected ASP.NET Core 2.1 as the framework.</span></span> <span data-ttu-id="ac4e5-124">.NET core 2.1 Visual Studio 2017의 마지막 버전에 포함 되어 및 자동으로 설치 되며 Visual Studio 2017을 설치할 때 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-124">.NET Core 2.1 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![Visual Studio 대화 상자 API 옵션이 선택 된 ASP.NET Core 웹 응용 프로그램의 유형을 선택 합니다.](media/create-web-api-application.png)

<span data-ttu-id="ac4e5-126">**그림 4-37**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-126">**Figure 4-37**.</span></span> <span data-ttu-id="ac4e5-127">ASP.NET CORE 2.1을 선택 하 고 Web API 프로젝트 형식</span><span class="sxs-lookup"><span data-stu-id="ac4e5-127">Selecting ASP.NET CORE 2.1 and Web API project type</span></span>

<span data-ttu-id="ac4e5-128">이전 버전의.NET Core를 사용 하는 경우 다운로드 하 고에서 2.1 버전을 설치할 수 <https://www.microsoft.com/net/download/core#/sdk>입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-128">If you have any previous version of .NET Core, you can download and install the 2.1 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="ac4e5-129">프로젝트를 만들 때 Docker 지원을 추가할 수 있습니다 하거나 나중에 따라서 있습니다 수 "docker 화" 프로젝트가 언제 든 지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="ac4e5-130">프로젝트를 만든 후에 Docker 지원을 추가 하려면 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가** > **Docker 지원** 상황에 맞는 메뉴입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![기존 프로젝트에 Docker 지원을 추가 하려면 상황에 맞는 메뉴 옵션: 마우스 오른쪽 단추로 클릭 (프로젝트) > 추가 > Docker 지원 합니다.](media/add-docker-support-to-project.png)

<span data-ttu-id="ac4e5-132">**그림 4-38**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-132">**Figure 4-38**.</span></span> <span data-ttu-id="ac4e5-133">기존 프로젝트에 Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="ac4e5-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="ac4e5-134">Docker 지원 추가 완료 하려면 Windows 또는 Linux를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="ac4e5-135">이 경우 선택 **Linux**이므로 AKS (런타임에 2018)로 Windows 컨테이너를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![옵션 대화 상자를 Dockerfile에 대 한 대상 OS를 선택 합니다.](media/select-linux-docker-support.png)

<span data-ttu-id="ac4e5-137">**그림 4-39**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-137">**Figure 4-39**.</span></span> <span data-ttu-id="ac4e5-138">Linux 컨테이너를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-138">Selecting Linux containers.</span></span>

<span data-ttu-id="ac4e5-139">이러한 간단한 단계를 사용 하 여 ASP.NET Core 2.1 응용 프로그램을 Linux 컨테이너에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-139">With these simple steps, you have your ASP.NET Core 2.1 application running on a Linux container.</span></span>

<span data-ttu-id="ac4e5-140">알 수 있듯이 Visual Studio 2017 및 Docker 간의 통합은 개발자의 생산성을 완전히 방향인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="ac4e5-141">이제 응용 프로그램을 실행할 수 있습니다 합니다 **F5** 키 또는 사용 하 여 합니다 **재생** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="ac4e5-142">프로젝트를 실행 한 후 사용 하 여 이미지를 나열할 수 있습니다는 `docker images` 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="ac4e5-143">표시 된 `mssampleapplication` Visual Studio 2017을 사용 하 여 프로젝트의 자동 배포를 통해 생성 되는 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![콘솔 출력에서 docker images 명령을 사용 하 여 목록을 보여 줍니다. 리포지토리, 태그, 이미지 ID, Created (날짜) 및 크기입니다.](media/docker-images-command.png)

<span data-ttu-id="ac4e5-145">**그림 4 ~ 40**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-145">**Figure 4-40**.</span></span> <span data-ttu-id="ac4e5-146">Docker 이미지 보기</span><span class="sxs-lookup"><span data-stu-id="ac4e5-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="ac4e5-147">Azure Container Registry에 솔루션 등록</span><span class="sxs-lookup"><span data-stu-id="ac4e5-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="ac4e5-148">예: 모든 Docker 레지스트리로 이미지를 업로드 [ACR Azure Container Registry ()](https://azure.microsoft.com/services/container-registry/) 또는 Docker Hub 이미지는 레지스트리에서 AKS 클러스터에 배포할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="ac4e5-149">이 경우 Azure Container Registry에 이미지를 업로드 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="ac4e5-150">릴리스 모드에서 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="ac4e5-150">Create the image in Release mode</span></span>

<span data-ttu-id="ac4e5-151">그림과 같이 이제 만들겠습니다 **릴리스** 으로 변경 하 여 (프로덕션에 대 한 준비 됨) 모드 **릴리스**그림 4-41 및 이전과 같이 응용 프로그램을 실행 합니다. 표시 된 것 처럼, 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![릴리스 모드에서 빌드를 VS에서 도구 모음 옵션입니다.](media/select-release-mode.png)

<span data-ttu-id="ac4e5-153">**그림 4-41**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-153">**Figure 4-41**.</span></span> <span data-ttu-id="ac4e5-154">릴리스 모드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-154">Selecting Release Mode</span></span>

<span data-ttu-id="ac4e5-155">실행 하는 경우는 `docker image` 명령에 대 한 두 이미지를 만든 표시 됩니다 `debug` 에 대 한 다른 `release` 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="ac4e5-156">이미지에 대 한 새 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="ac4e5-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="ac4e5-157">각 컨테이너 이미지를 사용 하 여 태그를 지정 해야 합니다.는 `loginServer` 레지스트리 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="ac4e5-158">이 태그는 컨테이너 이미지를 이미지 레지스트리에 밀어넣을 때 라우팅에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="ac4e5-159">볼 수는 `loginServer` Azure Container Registry에서 정보를 얻고, Azure portal에서 이름</span><span class="sxs-lookup"><span data-stu-id="ac4e5-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![브라우저 보기는 Azure 컨테이너 레지스트리 이름의 오른쪽 상단의입니다.](media/loginServer-name.png)

<span data-ttu-id="ac4e5-161">**그림 4-42**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-161">**Figure 4-42**.</span></span> <span data-ttu-id="ac4e5-162">레지스트리 이름 보기</span><span class="sxs-lookup"><span data-stu-id="ac4e5-162">View of the name of the Registry</span></span>

<span data-ttu-id="ac4e5-163">또는 다음 명령을 실행 하 여:</span><span class="sxs-lookup"><span data-stu-id="ac4e5-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![위 명령의 출력을 콘솔입니다.](media/az-cli-loginServer-name.png)

<span data-ttu-id="ac4e5-165">**그림 4-43**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-165">**Figure 4-43**.</span></span> <span data-ttu-id="ac4e5-166">PowerShell을 사용 하 여 레지스트리의 이름으로 가져오기</span><span class="sxs-lookup"><span data-stu-id="ac4e5-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="ac4e5-167">두 경우 모두 이름을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="ac4e5-168">예에서 `mssampleacr.azurecr.io`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="ac4e5-169">이제 태그를 지정할 수 이미지 (릴리스 이미지)는 최신 이미지 명령을 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="ac4e5-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="ac4e5-170">실행 한 후 합니다 `docker tag` 명령에 사용 하 여 이미지를 나열 합니다 `docker images` 명령을 새 태그를 사용 하 여 이미지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![콘솔 출력에서 docker images 명령을 합니다.](media/tagged-docker-images-list.png)

<span data-ttu-id="ac4e5-172">**그림 4-44**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-172">**Figure 4-44**.</span></span> <span data-ttu-id="ac4e5-173">태그가 지정 된 이미지의 보기</span><span class="sxs-lookup"><span data-stu-id="ac4e5-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="ac4e5-174">Azure ACR에 이미지 푸시</span><span class="sxs-lookup"><span data-stu-id="ac4e5-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="ac4e5-175">다음 명령을 사용 하 여 Azure ACR에 이미지를 푸시하십시오.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-175">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="ac4e5-176">이 명령을 걸립니다 이미지 업로드 되지만 프로세스의 피드백을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-176">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![콘솔 출력에서 docker push 명령은: 각 계층에 대 한 문자 기반 진행률 표시줄을 보여 줍니다.](media/uploading-image-to-acr.png)

<span data-ttu-id="ac4e5-178">**그림 4-45**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-178">**Figure 4-45**.</span></span> <span data-ttu-id="ac4e5-179">ACR에 이미지 업로드</span><span class="sxs-lookup"><span data-stu-id="ac4e5-179">Uploading the image to the ACR</span></span>

<span data-ttu-id="ac4e5-180">프로세스가 완료 되는 경우 얻게 결과 아래 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-180">You can see below the result you should get when the process completes:</span></span>

![콘솔에서 완료 되 면 모든 레이어 또는 노드를 보여 주는 docker push 명령은 출력 합니다.](media/uploading-docker-images-complete.png)

<span data-ttu-id="ac4e5-182">**그림 4-46**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-182">**Figure 4-46**.</span></span> <span data-ttu-id="ac4e5-183">노드 보기</span><span class="sxs-lookup"><span data-stu-id="ac4e5-183">View of nodes</span></span>

<span data-ttu-id="ac4e5-184">다음 단계 AKS Kubernetes 클러스터에 컨테이너를 배포 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-184">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="ac4e5-185">이 위해 파일이 필요 (**.yml 파일 배포**) 다음을 포함 하는:</span><span class="sxs-lookup"><span data-stu-id="ac4e5-185">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

```yml
apiVersion: apps/v1beta1
kind: Deployment
metadata:
  name: mssamplesbook
spec:
  replicas: 1
  template:
    metadata:
      labels:
        app: mssample-kub-app
    spec:
      containers:
        - mane: mssample-services-app
          image: mssampleacr.azurecr.io/mssampleaksapplication:v1
          ports:
            - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
    name: mssample-kub-app
spec:
  ports:
    - name: http-port
      port: 80
      targetPort: 80
  selector:
    app: mssample-kub-app
  type: LoadBalancer
```

> [!NOTE]
> <span data-ttu-id="ac4e5-186">Kubernetes 사용 하 여 배포에 대 한 자세한 내용은 다음을 참조 하세요. <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="ac4e5-186">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="ac4e5-187">이제 사용 하 여 배포할 준비가 거의 **Kubectl**,이 명령 사용 하 여 AKS 클러스터에 자격 증명을 먼저 가져와야 하지만:</span><span class="sxs-lookup"><span data-stu-id="ac4e5-187">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![위 명령의 출력을 콘솔: 현재 컨텍스트에서 /root/.kube/config으로 병합 된 "MSSampleK8Cluster](media/getting-aks-credentials.png)

<span data-ttu-id="ac4e5-189">**그림 4-47**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-189">**Figure 4-47**.</span></span> <span data-ttu-id="ac4e5-190">자격 증명 가져오기</span><span class="sxs-lookup"><span data-stu-id="ac4e5-190">getting credentials</span></span>

<span data-ttu-id="ac4e5-191">사용 하 여는 `kubectl create` 배포를 시작 하는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-191">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![위 명령의 출력을 콘솔: 배포 "mssamplesbook"을 생성 합니다.](media/kubectl-create-command.png)

<span data-ttu-id="ac4e5-194">**그림 4-48**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-194">**Figure 4-48**.</span></span> <span data-ttu-id="ac4e5-195">Kubernetes에 배포</span><span class="sxs-lookup"><span data-stu-id="ac4e5-195">Deploy to Kubernetes</span></span>

<span data-ttu-id="ac4e5-196">배포가 완료 되 면이 명령을 사용 하 여 일시적으로 액세스할 수 있는 로컬 프록시를 사용 하 여 Kubernetes 콘솔을 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-196">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="ac4e5-197">Url에 액세스 하 고 `http://127.0.0.1:8001`입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-197">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Kubernetes 대시보드를 배포, Pod, 복제본 집합 및 서비스를 보여 주는의 브라우저 보기입니다.](media/kubernetes-cluster-information.png)

<span data-ttu-id="ac4e5-199">**그림 4-49**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-199">**Figure 4-49**.</span></span> <span data-ttu-id="ac4e5-200">Kubernetes 클러스터 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="ac4e5-200">View Kubernetes cluster information</span></span>

<span data-ttu-id="ac4e5-201">이제 azure에서 Linux 컨테이너와 AKS Kubernetes 클러스터를 사용 하 여 배포 된 응용 프로그램을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-201">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="ac4e5-202">Azure portal에서 가져올 수 있는 서비스의 공용 IP로 이동 하 여 앱에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-202">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="ac4e5-203">섹션에서이 샘플에 대 한 AKS 클러스터를 만드는 방법 보시 [ **Azure Kubernetes Service (AKS)를 배포** ](deploy-azure-kubernetes-service.md) 이 가이드에서.</span><span class="sxs-lookup"><span data-stu-id="ac4e5-203">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ac4e5-204">[이전](set-up-windows-containers-with-powershell.md)
>[다음](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="ac4e5-204">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
