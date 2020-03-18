---
title: AKS/Kubernetes 클러스터에 Linux 컨테이너로 배포된 ASP.NET Core 2.2 애플리케이션 빌드
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기
ms.date: 02/25/2019
ms.openlocfilehash: ab64a0423ceceb8285c159af276d6d97e12379d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "70848746"
---
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="7fab5-103">AKS/Kubernetes 오케스트레이터에 Linux 컨테이너로 배포된 ASP.NET Core 2.2 애플리케이션 빌드</span><span class="sxs-lookup"><span data-stu-id="7fab5-103">Build ASP.NET Core 2.2 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="7fab5-104">AKS(Azure Kubernetes Service)는 컨테이너 배포 및 관리를 간소화하는 Azure의 관리형 Kubernetes 오케스트레이션 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="7fab5-105">AKS의 주요 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-105">AKS main features are:</span></span>

- <span data-ttu-id="7fab5-106">Azure에서 호스팅하는 제어 평면</span><span class="sxs-lookup"><span data-stu-id="7fab5-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="7fab5-107">자동화된 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7fab5-107">Automated upgrades</span></span>
- <span data-ttu-id="7fab5-108">자동 복구</span><span class="sxs-lookup"><span data-stu-id="7fab5-108">Self-healing</span></span>
- <span data-ttu-id="7fab5-109">사용자 구성 가능 크기 조정</span><span class="sxs-lookup"><span data-stu-id="7fab5-109">User configurable scaling</span></span>
- <span data-ttu-id="7fab5-110">개발자와 클러스터 운영자 모두에게 더 간단한 사용자 환경.</span><span class="sxs-lookup"><span data-stu-id="7fab5-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="7fab5-111">다음 예제에서는 Visual Studio 2017을 사용하여 개발이 수행되는 동안 Linux에서 실행하고 Azure의 AKS 클러스터에 배포되는 ASP.NET Core 2.2 애플리케이션을 만들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-111">The following examples explore the creation of an ASP.NET Core 2.2 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a><span data-ttu-id="7fab5-112">Visual Studio 2017을 사용하여 ASP.NET Core 2.2 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="7fab5-112">Creating the ASP.NET Core 2.2 Project using Visual Studio 2017</span></span>

<span data-ttu-id="7fab5-113">ASP.NET Core는 Microsoft 및 GitHub의 .NET 커뮤니티에서 유지 관리하는 범용 개발 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="7fab5-114">Windows, macOS 및 Linux 플랫폼 간 교차 사용을 지원하며 디바이스, 클라우드 및 포함/IoT 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="7fab5-115">이 예제에서는 Visual Studio 웹 API 템플릿 기반의 간단한 프로젝트를 사용하므로 샘플을 만들기 위한 추가 지식은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-115">This example uses a simple project that's based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="7fab5-116">ASP.NET Core 2.2 기술을 사용하여 REST API를 통해 작은 프로젝트를 실행하기 위한 모든 요소가 포함된 표준 템플릿을 사용하여 프로젝트를 만들기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.2 technology.</span></span>

![Visual Studio에서 ASP.NET Core 웹 애플리케이션을 선택하는 새 프로젝트 창을 추가합니다.](media/create-aspnet-core-application.png)

<span data-ttu-id="7fab5-118">**그림 4-36**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-118">**Figure 4-36**.</span></span> <span data-ttu-id="7fab5-119">ASP.NET Core 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="7fab5-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="7fab5-120">Visual Studio에서 샘플 프로젝트를 만들려면 **파일** > **새로 만들기** > **프로젝트**를 선택하고 왼쪽 창에서 **웹** 프로젝트 형식을 선택한 후 **ASP.NET Core 웹 애플리케이션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="7fab5-121">Visual Studio에 웹 프로젝트용 템플릿이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="7fab5-122">이 예제에서는 **API**를 선택하여 ASP.NET 웹 API 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="7fab5-123">ASP.NET Core 2.2를 프레임워크로 선택했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-123">Verify that you've selected ASP.NET Core 2.2 as the framework.</span></span> <span data-ttu-id="7fab5-124">.NET Core 2.2는 Visual Studio 2017의 최신 버전에 포함되어 Visual Studio 2017을 설치하면 자동으로 설치되고 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-124">.NET Core 2.2 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![API 옵션이 선택된 상태에서 ASP.NET Core 웹 애플리케이션 유형을 선택하기 위한 Visual Studio 대화 상자](media/create-web-api-application.png)

<span data-ttu-id="7fab5-126">**그림 4-37**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-126">**Figure 4-37**.</span></span> <span data-ttu-id="7fab5-127">ASP.NET CORE 2.2 및 웹 API 프로젝트 형식 선택</span><span class="sxs-lookup"><span data-stu-id="7fab5-127">Selecting ASP.NET CORE 2.2 and Web API project type</span></span>

<span data-ttu-id="7fab5-128">이전 버전의 .NET Core를 보유한 경우 <https://dotnet.microsoft.com/download>에서 2.2 버전을 다운로드하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-128">If you have any previous version of .NET Core, you can download and install the 2.2 version from <https://dotnet.microsoft.com/download>.</span></span>

<span data-ttu-id="7fab5-129">프로젝트를 만들 때 또는 그 후에 Docker 지원을 추가할 수 있으므로 언제든지 프로젝트를 "Docker화"할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="7fab5-130">프로젝트를 만든 후 Docker 지원을 추가하려면 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **추가** > **Docker 지원**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![기존 프로젝트에 Docker 지원을 추가하는 바로 가기 메뉴 옵션: (프로젝트에서)마우스 오른쪽 단추를 클릭 > 추가 > Docker 지원](media/add-docker-support-to-project.png)

<span data-ttu-id="7fab5-132">**그림 4-38**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-132">**Figure 4-38**.</span></span> <span data-ttu-id="7fab5-133">기존 프로젝트에 Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="7fab5-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="7fab5-134">Docker 지원 추가를 완료하려면 Windows 또는 Linux를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="7fab5-135">AKS는 Windows 컨테이너를 지원하지 않으므로(2018년 말 현재) 이 경우 **Linux**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![Dockerfile에 대한 대상 OS를 선택하는 옵션 대화 상자](media/select-linux-docker-support.png)

<span data-ttu-id="7fab5-137">**그림 4-39**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-137">**Figure 4-39**.</span></span> <span data-ttu-id="7fab5-138">Linux 컨테이너 선택</span><span class="sxs-lookup"><span data-stu-id="7fab5-138">Selecting Linux containers.</span></span>

<span data-ttu-id="7fab5-139">이 간단한 단계를 수행하면 Linux 컨테이너에서 실행하는 ASP.NET Core 2.2 애플리케이션을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-139">With these simple steps, you have your ASP.NET Core 2.2 application running on a Linux container.</span></span>

<span data-ttu-id="7fab5-140">보다시피 Visual Studio 2017과 Docker는 개발자의 생산성을 최대한 높이는 방법으로 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="7fab5-141">이제 **F5** 키를 누르거나 **재생** 단추를 사용하여 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="7fab5-142">프로젝트를 실행한 후 `docker images` 명령을 사용하여 이미지를 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="7fab5-143">Visual Studio 2017을 통해 프로젝트를 자동 배포하여 만든 `mssampleapplication` 이미지가 보일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![Docker 이미지 명령의 콘솔 출력에 다음 정보를 포함하는 목록이 표시됩니다. 리포지토리, 태그, 이미지 ID, 만든 날짜 및 크기](media/docker-images-command.png)

<span data-ttu-id="7fab5-145">**그림 4-40**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-145">**Figure 4-40**.</span></span> <span data-ttu-id="7fab5-146">Docker 이미지 보기</span><span class="sxs-lookup"><span data-stu-id="7fab5-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="7fab5-147">Azure Container Registry에 솔루션 등록</span><span class="sxs-lookup"><span data-stu-id="7fab5-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="7fab5-148">이미지를 [ACR(Azure Container Registry)](https://azure.microsoft.com/services/container-registry/) 또는 Docker Hub와 같은 Docker 레지스트리에 업로드하여 해당 레지스트리에서 이미지를 AKS 클러스터에 배포할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="7fab5-149">이 경우 이미지를 Azure Container Registry에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="7fab5-150">릴리스 모드에서 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="7fab5-150">Create the image in Release mode</span></span>

<span data-ttu-id="7fab5-151">이제 그림 4-41과 같이 **릴리스**로 변경하고 이전과 같은 방법으로 애플리케이션을 실행하여 **릴리스** 모드에서 (프로덕션 준비가 완료된) 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![릴리스 모드에서 빌드하기 위한 VS의 도구 모음 옵션](media/select-release-mode.png)

<span data-ttu-id="7fab5-153">**그림 4-41**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-153">**Figure 4-41**.</span></span> <span data-ttu-id="7fab5-154">릴리스 모드 선택</span><span class="sxs-lookup"><span data-stu-id="7fab5-154">Selecting Release Mode</span></span>

<span data-ttu-id="7fab5-155">`docker image` 명령을 실행하면 만들어진 이미지 두 개(`debug`에 대한 이미지와 `release` 모드에 대한 이미지)가 모두 보입니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="7fab5-156">이미지에 대한 새 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="7fab5-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="7fab5-157">각 컨테이너 이미지에 레지스트리의 `loginServer` 이름으로 태그를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="7fab5-158">이 태그는 컨테이너 이미지를 이미지 레지스트리에 밀어넣을 때 라우팅에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="7fab5-159">Azure Portal에서 `loginServer` 이름을 보고 Azure Container Registry에서 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![브라우저 오른쪽 위의 Azure 컨테이너 레지스트리 이름 보기](media/loginServer-name.png)

<span data-ttu-id="7fab5-161">**그림 4-42**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-161">**Figure 4-42**.</span></span> <span data-ttu-id="7fab5-162">레지스트리의 이름 보기</span><span class="sxs-lookup"><span data-stu-id="7fab5-162">View of the name of the Registry</span></span>

<span data-ttu-id="7fab5-163">또는 다음 명령을 실행하여 이름을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![위 명령의 콘솔 출력](media/az-cli-loginServer-name.png)

<span data-ttu-id="7fab5-165">**그림 4-43**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-165">**Figure 4-43**.</span></span> <span data-ttu-id="7fab5-166">PowerShell을 사용하여 레지스트리의 이름 가져오기</span><span class="sxs-lookup"><span data-stu-id="7fab5-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="7fab5-167">두 경우 모두 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="7fab5-168">이 예제의 경우 이름은 `mssampleacr.azurecr.io`입니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="7fab5-169">이제 다음 명령을 사용하여 이미지에 태그를 지정하고 최신 이미지를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="7fab5-170">`docker tag` 명령을 실행한 후 `docker images` 명령을 사용하여 이미지를 나열하면 새 태그가 지정된 이미지가 보일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Docker 이미지 명령의 콘솔 출력](media/tagged-docker-images-list.png)

<span data-ttu-id="7fab5-172">**그림 4-44**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-172">**Figure 4-44**.</span></span> <span data-ttu-id="7fab5-173">태그가 지정된 이미지 보기</span><span class="sxs-lookup"><span data-stu-id="7fab5-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="7fab5-174">Azure ACR에 이미지 푸시</span><span class="sxs-lookup"><span data-stu-id="7fab5-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="7fab5-175">Azure Container Registry에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-175">Log in to the Azure Container Registry</span></span>

```console
az acr login --name mssampleacr
```

<span data-ttu-id="7fab5-176">다음 명령을 사용하여 이미지를 Azure ACR에 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-176">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="7fab5-177">이 명령은 이미지를 업로드하는 동안 다소 시간이 걸리지만 프로세스와 관련된 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-177">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Docker 푸시 명령의 콘솔 출력: 각 레이어에 대한 문자 기반 진행률 표시줄을 보여줍니다.](media/uploading-image-to-acr.png)

<span data-ttu-id="7fab5-179">**그림 4-45**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-179">**Figure 4-45**.</span></span> <span data-ttu-id="7fab5-180">ACR에 이미지 업로드</span><span class="sxs-lookup"><span data-stu-id="7fab5-180">Uploading the image to the ACR</span></span>

<span data-ttu-id="7fab5-181">프로세스가 완료될 때 얻는 결과를 아래에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-181">You can see below the result you should get when the process completes:</span></span>

![Docker 푸시 명령의 콘솔 출력, 완료된 상태이며 모든 레이어 또는 노드를 보여줍니다.](media/uploading-docker-images-complete.png)

<span data-ttu-id="7fab5-183">**그림 4-46**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-183">**Figure 4-46**.</span></span> <span data-ttu-id="7fab5-184">노드 보기</span><span class="sxs-lookup"><span data-stu-id="7fab5-184">View of nodes</span></span>

<span data-ttu-id="7fab5-185">다음으로 컨테이너를 AKS Kubernetes 클러스터에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-185">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="7fab5-186">이 단계를 위해 다음을 포함하는 파일( **.yml 배포 파일**)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-186">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

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
        - name: mssample-services-app
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
> <span data-ttu-id="7fab5-187">Kubernetes를 사용한 배포에 대한 자세한 내용은 <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7fab5-187">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="7fab5-188">이제 **Kubectl**을 사용하여 배포할 준비가 거의 완료되었지만 먼저 이 명령을 사용하여 자격 증명을 AKS 클러스터로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-188">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![위 명령의 콘솔 출력: /root/.kube/config의 현재 컨텍스트로 병합된 "MSSampleK8Cluster"](media/getting-aks-credentials.png)

<span data-ttu-id="7fab5-190">**그림 4-47**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-190">**Figure 4-47**.</span></span> <span data-ttu-id="7fab5-191">자격 증명 가져오기</span><span class="sxs-lookup"><span data-stu-id="7fab5-191">getting credentials</span></span>

<span data-ttu-id="7fab5-192">그런 다음, `kubectl create` 명령을 사용하여 배포를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-192">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![위 명령의 콘솔 출력: 배포 "mssamplesbook"이 만들어졌습니다.](media/kubectl-create-command.png)

<span data-ttu-id="7fab5-195">**그림 4-48**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-195">**Figure 4-48**.</span></span> <span data-ttu-id="7fab5-196">Kubernetes에 배포</span><span class="sxs-lookup"><span data-stu-id="7fab5-196">Deploy to Kubernetes</span></span>

<span data-ttu-id="7fab5-197">배포가 완료되면 이 명령을 사용하여 일시적으로 액세스할 수 있는 로컬 프록시를 통해 Kubernetes 콘솔에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-197">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="7fab5-198">그리고 URL `http://127.0.0.1:8001`에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-198">And accessing the url `http://127.0.0.1:8001`.</span></span>

![배포, Pod, 복제본 세트 및 서비스를 보여주는 Kubernetes 대시보드의 브라우저 보기](media/kubernetes-cluster-information.png)

<span data-ttu-id="7fab5-200">**그림 4-49**.</span><span class="sxs-lookup"><span data-stu-id="7fab5-200">**Figure 4-49**.</span></span> <span data-ttu-id="7fab5-201">Kubernetes 클러스터 정보 보기</span><span class="sxs-lookup"><span data-stu-id="7fab5-201">View Kubernetes cluster information</span></span>

<span data-ttu-id="7fab5-202">지금까지 Linux 컨테이너를 사용하여 Azure 및 AKS Kubernetes 클러스터에 애플리케이션을 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-202">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="7fab5-203">앱에 액세스하여 Azure Portal에서 가져올 수 있는 서비스의 공용 IP를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-203">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="7fab5-204">이 가이드의 [**AKS(Azure Kubernetes Service)에 배포**](deploy-azure-kubernetes-service.md) 섹션에서 이 샘플에 대한 AKS 클러스터를 만드는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab5-204">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7fab5-205">[이전](set-up-windows-containers-with-powershell.md)
>[다음](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="7fab5-205">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
