---
title: 기타 컨테이너 배포 옵션
description: Azure를 사용 하는 다른 컨테이너 배포 옵션
ms.date: 05/13/2020
ms.openlocfilehash: 2eac822b74af636e0ab0ed24b58eb7139526f4a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163624"
---
# <a name="other-container-deployment-options"></a><span data-ttu-id="77b0b-103">기타 컨테이너 배포 옵션</span><span class="sxs-lookup"><span data-stu-id="77b0b-103">Other container deployment options</span></span>

<span data-ttu-id="77b0b-104">Azure Kubernetes 서비스 (AKS) 외에도 컨테이너 및 Azure Container Instances에 대 한 Azure App Service 컨테이너를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-104">Aside from Azure Kubernetes Service (AKS), you can also deploy containers to Azure App Service for Containers and Azure Container Instances.</span></span>

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a><span data-ttu-id="77b0b-105">컨테이너의 App Service에 배포 하는 것이 적합 한가요?</span><span class="sxs-lookup"><span data-stu-id="77b0b-105">When does it make sense to deploy to App Service for Containers?</span></span>

<span data-ttu-id="77b0b-106">오케스트레이션을 필요로 하지 않는 간단한 프로덕션 응용 프로그램은 컨테이너의 Azure App Service에 매우 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-106">Simple production applications that don't require orchestration are well suited to Azure App Service for Containers.</span></span>

## <a name="how-to-deploy-to-app-service-for-containers"></a><span data-ttu-id="77b0b-107">컨테이너의 App Service에 배포 하는 방법</span><span class="sxs-lookup"><span data-stu-id="77b0b-107">How to deploy to App Service for Containers</span></span>

<span data-ttu-id="77b0b-108">[컨테이너의 Azure App Service](https://azure.microsoft.com/services/app-service/containers/)에 배포 하려면 해당 인스턴스에 액세스 하는 데 필요한 AZURE CONTAINER REGISTRY (ACR) 인스턴스 및 자격 증명이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-108">To deploy to [Azure App Service for Containers](https://azure.microsoft.com/services/app-service/containers/), you'll need an Azure Container Registry (ACR) instance and credentials to access it.</span></span> <span data-ttu-id="77b0b-109">컨테이너 이미지를 ACR 리포지토리로 푸시하여 Azure App Service로 끌어올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-109">Push your container image to the ACR repository so it can pulled into your Azure App Service.</span></span> <span data-ttu-id="77b0b-110">완료 되 면 연속 배포에 대해 앱을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-110">Once complete, you can configure the app for Continuous Deployment.</span></span> <span data-ttu-id="77b0b-111">그렇게 하면 이미지가 ACR에서 변경 될 때마다 자동으로 업데이트를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-111">Doing so will automatically deploy updates whenever the image changes in ACR.</span></span>

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a><span data-ttu-id="77b0b-112">Azure Container Instances에 배포 하는 것이 적합 한가요?</span><span class="sxs-lookup"><span data-stu-id="77b0b-112">When does it make sense to deploy to Azure Container Instances?</span></span>

<span data-ttu-id="77b0b-113">[ACI (Azure Container Instances)](https://azure.microsoft.com/services/container-instances/) 를 사용 하면 가상 머신 또는 클러스터를 설정 하지 않고도 관리 되는 서버 리스 클라우드 환경에서 Docker 컨테이너를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-113">[Azure Container Instances (ACI)](https://azure.microsoft.com/services/container-instances/) enables you to run Docker containers in a managed, serverless cloud environment, without having to set up virtual machines or clusters.</span></span> <span data-ttu-id="77b0b-114">격리 된 컨테이너에서 실행할 수 있는 단기 실행 작업에 적합 한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-114">It's a great solution for short-running workloads that can run in an isolated container.</span></span> <span data-ttu-id="77b0b-115">간단한 서비스, 테스트 시나리오, 작업 자동화, 빌드 작업 등에 대해 ACI를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-115">Consider ACI for simple services, testing scenarios, task automation, and build jobs.</span></span> <span data-ttu-id="77b0b-116">ACI는 컨테이너 인스턴스를 회전 하 고 작업을 수행한 다음 아래로 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-116">ACI spins-up a container instance, performs the task, and then spins it down.</span></span>

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a><span data-ttu-id="77b0b-117">Azure Container Instances에 앱을 배포 하는 방법</span><span class="sxs-lookup"><span data-stu-id="77b0b-117">How to deploy an app to Azure Container Instances</span></span>

<span data-ttu-id="77b0b-118">[Azure Container Instances (ACI)](/azure/container-instances/)에 배포 하려면 AZURE CONTAINER REGISTRY (ACR) 및 액세스를 위한 자격 증명이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-118">To deploy to [Azure Container Instances (ACI)](/azure/container-instances/), you need an Azure Container Registry (ACR) and credentials for accessing it.</span></span> <span data-ttu-id="77b0b-119">컨테이너 이미지를 리포지토리에 푸시 하면 ACI로 끌어올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-119">Once you push your container image to the repository, it's available to pull into ACI.</span></span> <span data-ttu-id="77b0b-120">Azure Portal 또는 명령줄 인터페이스를 사용 하 여 ACI로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-120">You can work with ACI using the Azure portal or command-line interface.</span></span> <span data-ttu-id="77b0b-121">ACR은 ACI와 긴밀 하 게 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-121">ACR provides tight integration with ACI.</span></span> <span data-ttu-id="77b0b-122">그림 3-14에서는 ACR에 개별 컨테이너 이미지를 푸시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-122">Figure 3-14 shows how to push an individual container image to ACR.</span></span>

![Azure Container Registry 실행 인스턴스](./media/acr-runinstance-contextmenu.png)

<span data-ttu-id="77b0b-124">**그림 3-14**.</span><span class="sxs-lookup"><span data-stu-id="77b0b-124">**Figure 3-14**.</span></span> <span data-ttu-id="77b0b-125">Azure Container Registry 실행 인스턴스</span><span class="sxs-lookup"><span data-stu-id="77b0b-125">Azure Container Registry Run Instance</span></span>

<span data-ttu-id="77b0b-126">ACI에서 인스턴스를 만드는 작업은 신속 하 게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-126">Creating an instance in ACI can be done quickly.</span></span> <span data-ttu-id="77b0b-127">이미지 레지스트리, Azure 리소스 그룹 정보, 할당할 메모리 양 및 수신 대기할 포트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-127">Specify the image registry, Azure resource group information, the amount of memory to allocate, and the port on which to listen.</span></span> <span data-ttu-id="77b0b-128">이 [빠른 시작에서는 Azure Portal를 사용 하 여 ACI에 컨테이너 인스턴스를 배포 하는 방법을 보여 줍니다](/azure/container-instances/container-instances-quickstart-portal).</span><span class="sxs-lookup"><span data-stu-id="77b0b-128">This [quickstart shows how to deploy a container instance to ACI using the Azure portal](/azure/container-instances/container-instances-quickstart-portal).</span></span>

<span data-ttu-id="77b0b-129">배포가 완료 되 면 새로 배포 된 컨테이너의 IP 주소를 찾아 지정 된 포트를 통해 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-129">Once the deployment completes, find the newly deployed container's IP address and communicate with it over the port you specified.</span></span>

<span data-ttu-id="77b0b-130">Azure Container Instances는 Azure에서 간단한 컨테이너 워크 로드를 실행 하는 가장 빠른 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-130">Azure Container Instances offers the fastest way to run simple container workloads in Azure.</span></span> <span data-ttu-id="77b0b-131">App service, orchestrator 또는 virtual machine을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-131">You don't need to configure an app service, orchestrator, or virtual machine.</span></span> <span data-ttu-id="77b0b-132">전체 컨테이너 오케스트레이션, 서비스 검색, 자동 크기 조정 또는 조정 된 업그레이드가 필요한 시나리오의 경우 Azure Kubernetes 서비스 (AKS)를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b0b-132">For scenarios where you require full container orchestration, service discovery, automatic scaling, or coordinated upgrades, we recommend Azure Kubernetes Service (AKS).</span></span>

## <a name="references"></a><span data-ttu-id="77b0b-133">참조</span><span class="sxs-lookup"><span data-stu-id="77b0b-133">References</span></span>

- [<span data-ttu-id="77b0b-134">Kubernetes란?</span><span class="sxs-lookup"><span data-stu-id="77b0b-134">What is Kubernetes?</span></span>](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [<span data-ttu-id="77b0b-135">Minikube를 사용 하 여 Kubernetes 설치</span><span class="sxs-lookup"><span data-stu-id="77b0b-135">Installing Kubernetes with Minikube</span></span>](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [<span data-ttu-id="77b0b-136">MiniKube vs Docker Desktop</span><span class="sxs-lookup"><span data-stu-id="77b0b-136">MiniKube vs Docker Desktop</span></span>](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [<span data-ttu-id="77b0b-137">Docker용 Visual Studio Tools</span><span class="sxs-lookup"><span data-stu-id="77b0b-137">Visual Studio Tools for Docker</span></span>](/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)
- [<span data-ttu-id="77b0b-138">서버 리스 콜드 시작 이해</span><span class="sxs-lookup"><span data-stu-id="77b0b-138">Understanding serverless cold start</span></span>](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [<span data-ttu-id="77b0b-139">사전 준비 Azure Functions 인스턴스</span><span class="sxs-lookup"><span data-stu-id="77b0b-139">Pre-warmed Azure Functions instances</span></span>](/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [<span data-ttu-id="77b0b-140">사용자 지정 이미지를 사용하여 Linux에서 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="77b0b-140">Create a function on Linux using a custom image</span></span>](/azure/azure-functions/functions-create-function-linux-custom-image)
- [<span data-ttu-id="77b0b-141">Docker 컨테이너에서 Azure Functions 실행</span><span class="sxs-lookup"><span data-stu-id="77b0b-141">Run Azure Functions in a Docker Container</span></span>](https://markheath.net/post/azure-functions-docker)
- [<span data-ttu-id="77b0b-142">사용자 지정 이미지를 사용하여 Linux에서 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="77b0b-142">Create a function on Linux using a custom image</span></span>](/azure/azure-functions/functions-create-function-linux-custom-image)
- [<span data-ttu-id="77b0b-143">Kubernetes 이벤트 기반 자동 크기 조정을 사용 하는 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="77b0b-143">Azure Functions with Kubernetes Event Driven Autoscaling</span></span>](/azure/azure-functions/functions-kubernetes-keda)
- [<span data-ttu-id="77b0b-144">카나리아 릴리스</span><span class="sxs-lookup"><span data-stu-id="77b0b-144">Canary Release</span></span>](https://martinfowler.com/bliki/CanaryRelease.html)
- [<span data-ttu-id="77b0b-145">VS Code Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="77b0b-145">Azure Dev Spaces with VS Code</span></span>](/azure/dev-spaces/quickstart-netcore)
- [<span data-ttu-id="77b0b-146">Visual Studio를 사용 하 여 Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="77b0b-146">Azure Dev Spaces with Visual Studio</span></span>](/azure/dev-spaces/quickstart-netcore-visualstudio)
- [<span data-ttu-id="77b0b-147">여러 노드 풀 AKS</span><span class="sxs-lookup"><span data-stu-id="77b0b-147">AKS Multiple Node Pools</span></span>](/azure/aks/use-multiple-node-pools)
- [<span data-ttu-id="77b0b-148">AKS Cluster Autoscaler</span><span class="sxs-lookup"><span data-stu-id="77b0b-148">AKS Cluster Autoscaler</span></span>](/azure/aks/cluster-autoscaler)
- [<span data-ttu-id="77b0b-149">자습서: AKS에서 응용 프로그램 크기 조정</span><span class="sxs-lookup"><span data-stu-id="77b0b-149">Tutorial: Scale applications in AKS</span></span>](/azure/aks/tutorial-kubernetes-scale)
- [<span data-ttu-id="77b0b-150">Azure Functions 비율 크기 조정 및 호스팅</span><span class="sxs-lookup"><span data-stu-id="77b0b-150">Azure Functions scale and hosting</span></span>](/azure/azure-functions/functions-scale)
- [<span data-ttu-id="77b0b-151">문서 Azure Container Instances</span><span class="sxs-lookup"><span data-stu-id="77b0b-151">Azure Container Instances Docs</span></span>](/azure/container-instances/)
- [<span data-ttu-id="77b0b-152">ACR에서 컨테이너 인스턴스 배포</span><span class="sxs-lookup"><span data-stu-id="77b0b-152">Deploy Container Instance from ACR</span></span>](/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
><span data-ttu-id="77b0b-153">[이전](scale-containers-serverless.md)
>[다음](communication-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="77b0b-153">[Previous](scale-containers-serverless.md)
[Next](communication-patterns.md)</span></span>
