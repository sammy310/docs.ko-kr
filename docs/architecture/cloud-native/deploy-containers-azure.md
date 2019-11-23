---
title: Azure에서 컨테이너 배포
description: Azure Container Registry, Azure Kubernetes Service 및 Azure Dev Spaces를 사용 하 여 Azure에 컨테이너를 배포 합니다.
ms.date: 06/30/2019
ms.openlocfilehash: 6d95db26b6a45dd6825c88693308ffe90d1ed071
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840486"
---
# <a name="deploying-containers-in-azure"></a><span data-ttu-id="e36f1-103">Azure에서 컨테이너 배포</span><span class="sxs-lookup"><span data-stu-id="e36f1-103">Deploying containers in Azure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e36f1-104">컨테이너는 다양 한 이점을 제공 합니다. 그 중 하나는 이식성입니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-104">Containers provide many benefits, one of which is portability.</span></span> <span data-ttu-id="e36f1-105">로컬로 개발 하 고 테스트 한 동일한 컨테이너를 쉽게 사용 하 고 스테이징 및 프로덕션 환경에서 앱을 실행할 수 있는 Azure에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-105">You can easily take the same container you've developed and tested locally and deploy it to Azure where it can run your app in staging and production environments.</span></span> <span data-ttu-id="e36f1-106">Azure는 컨테이너 기반 응용 프로그램 호스팅에 대 한 다양 한 옵션을 제공 하며, 이와 같은 다양 한 배포 방법을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-106">Azure provides a number of options for container-based app hosting and likewise supports several different means of deployment.</span></span> <span data-ttu-id="e36f1-107">가장 일반적이 고 가장 유연한 방법은 컨테이너를 호스트 하는 데 사용할 서비스에서 액세스할 수 있는 ACR (Azure Container Registry)에 배포 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-107">The most common and most flexible approach is to deploy your containers to Azure Container Registry (ACR), where they're accessible by whatever services you wish to use to host them.</span></span> <span data-ttu-id="e36f1-108">Azure Web App for Containers, AKS (azure Kubernetes Services) 및 ACI (Azure Container Instance)는 모두 ACR로 푸시되는 컨테이너 이미지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-108">Azure Web App for Containers, Azure Kubernetes Services (AKS), and Azure Container Instance (ACI) all can access container images that have been pushed to ACR.</span></span>

## <a name="azure-container-registry"></a><span data-ttu-id="e36f1-109">Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="e36f1-109">Azure Container Registry</span></span>

<span data-ttu-id="e36f1-110">ACR (Azure Container Registry)를 사용 하 여 모든 컨테이너 배포에 대 한 이미지를 작성, 저장 및 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-110">Azure Container Registry (ACR) lets you build, store, and manage images for all of your container deployments.</span></span> <span data-ttu-id="e36f1-111">컨테이너를 배포할 수 있는 다른 컨테이너 레지스트리 (공용 및 개인)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-111">There are other container registries, both public and private, to which you can deploy containers.</span></span> <span data-ttu-id="e36f1-112">다른 옵션에 대 한 ACR의 장점으로, 이미지를 프로덕션 환경에 가깝게 유지 하 여 빌드 및 배포 시간을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-112">The benefit of ACR over other options is that you can keep your images close to your production environment, improving build and deployment times.</span></span> <span data-ttu-id="e36f1-113">또한 Azure 리소스의 나머지 부분에 사용 하는 것과 동일한 보안 절차를 사용 하 여 보안을 강화 하 고, 보안을 개선 하 고, 자산 관리 작업을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-113">You can also secure them using the same security procedures you use for the rest of your Azure resources, improving security and reducing asset management effort.</span></span>

<span data-ttu-id="e36f1-114">Azure Portal을 사용 하거나 [Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli) 또는 [PowerShell 도구](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell)를 사용 하 여 [컨테이너 레지스트리를 만듭니다](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal) .</span><span class="sxs-lookup"><span data-stu-id="e36f1-114">You [create a container registry using the Azure Portal](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal) or [using the Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli) or [PowerShell tools](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell).</span></span> <span data-ttu-id="e36f1-115">새 컨테이너 레지스트리를 만들려면 Azure 구독, 리소스 그룹 및 고유한 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-115">Creating a new container registry just requires an Azure subscription, a resource group, and a unique name.</span></span> <span data-ttu-id="e36f1-116">그림 3-11에서는 *registryname*. azurecr.io에서 호스트 되는 레지스트리를 만들기 위한 기본 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-116">Figure 3-11 shows the basic options for creating a registry, which will be hosted at *registryname*.azurecr.io.</span></span>

<span data-ttu-id="e36f1-117">![컨테이너 레지스트리](./media/create-container-registry.png)
**그림 3-11**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-117">![Create container registry](./media/create-container-registry.png)
**Figure 3-11**.</span></span> <span data-ttu-id="e36f1-118">컨테이너 레지스트리 만들기</span><span class="sxs-lookup"><span data-stu-id="e36f1-118">Create container registry</span></span>

<span data-ttu-id="e36f1-119">레지스트리를 만든 후에는 해당 레지스트리를 사용 하기 전에 인증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-119">Once you've created a registry, you'll need to authenticate with it before you can use it.</span></span> <span data-ttu-id="e36f1-120">일반적으로 Azure CLI 명령을 사용 하 여 레지스트리에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-120">Typically, you'll log into the registry using the Azure CLI command:</span></span>

```azurecli
az acr login --name *registryname*
```

<span data-ttu-id="e36f1-121">Azure Container Registry에서 레지스트리를 만든 후에는 docker 명령을 사용 하 여 컨테이너 이미지를 푸시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-121">Once you've created a registry in Azure Container Registry, you can use docker commands to push container images to it.</span></span> <span data-ttu-id="e36f1-122">그러나이 작업을 수행 하려면 먼저 ACR 로그인 서버의 정규화 된 이름 (URL)을 사용 하 여 이미지에 태그를 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-122">Before you can do so, however, you must first tag your image with the fully qualified name (URL) of your ACR login server.</span></span> <span data-ttu-id="e36f1-123">이는 *registryname*. azurecr.io 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-123">This will have the format *registryname*.azurecr.io.</span></span>

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="e36f1-124">이미지에 태그를 지정한 후에는 `docker push` 명령을 사용 하 여 ACR 인스턴스로 이미지를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-124">After you've tagged the image, you use the `docker push` command to push the image to your ACR instance.</span></span>

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="e36f1-125">이미지를 레지스트리에 푸시한 후에는 다음 명령을 사용 하 여 로컬 Docker 환경에서 이미지를 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-125">After you push an image to the registry, it's a good idea to remove the image from your local Docker environment, using this command:</span></span>

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="e36f1-126">개발자는 자신의 컴퓨터에서 컨테이너 레지스트리로 직접 푸시하는 경우가 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-126">Developers should rarely push directly from their machines to a container registry.</span></span> <span data-ttu-id="e36f1-127">대신 Azure DevOps와 같은 도구에 정의 된 빌드 파이프라인이이 프로세스를 담당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-127">Instead, a build pipeline defined in a tool like Azure DevOps should be responsible for this process.</span></span> <span data-ttu-id="e36f1-128">[클라우드-기본 DevOps 챕터](devops.md)에서 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="e36f1-128">Learn more in the [Cloud-Native DevOps chapter](devops.md).</span></span>

## <a name="azure-kubernetes-service"></a><span data-ttu-id="e36f1-129">Azure Kubernetes Service</span><span class="sxs-lookup"><span data-stu-id="e36f1-129">Azure Kubernetes Service</span></span>

<span data-ttu-id="e36f1-130">컨테이너 기반 응용 프로그램에 여러 컨테이너가 포함 된 경우 Kubernetes와 같은 *orchestrator* 를 사용 하 여 컨테이너 간의 상호 작용을 정의 하 고 관리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-130">If your container-based application involves multiple containers, you'll most likely want to define and manage the interactions between the containers using an *orchestrator* like Kubernetes.</span></span> <span data-ttu-id="e36f1-131">ACR에 컨테이너 이미지를 배포한 후에는 Azure Kubernetes 서비스를 쉽게 구성 하 여 ACR에서 업데이트 된 이미지를 자동으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-131">Once you've deployed your container images to ACR, you can easily configure Azure Kubernetes Services to automatically deploy updated images from ACR.</span></span> <span data-ttu-id="e36f1-132">전체 CI/CD 파이프라인을 사용 하는 경우 업데이트를 신속 하 게 배포할 때 관련 된 위험을 최소화 하기 위해 [카나리아 릴리스](https://martinfowler.com/bliki/CanaryRelease.html) 전략을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-132">With a full CI/CD pipeline in place, you can configure a [canary release](https://martinfowler.com/bliki/CanaryRelease.html) strategy to minimize the risk involved when rapidly deploying updates.</span></span> <span data-ttu-id="e36f1-133">새 버전의 앱은 전송 된 트래픽이 없는 프로덕션 환경에서 초기에 구성 되며 소수의 사용자는 새로 배포 된 앱 버전으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-133">The new version of the app is initially configured in production with no traffic routed to it, and then a small number of users are routed to the newly-deployed version of the app.</span></span> <span data-ttu-id="e36f1-134">팀이 새 버전의 소프트웨어에서 확신을 얻게 되 면 새 버전의 인스턴스는 더 이상 사용 되지 않으며 이전 버전의 인스턴스는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-134">As the team gains confidence in the new version of the software, more instances of the new version are rolled out and the previous version's instances are retired.</span></span> <span data-ttu-id="e36f1-135">AKS는이 스타일의 배포를 쉽게 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-135">AKS easily supports this style of deployment.</span></span>

<span data-ttu-id="e36f1-136">Azure의 대부분 리소스와 마찬가지로 포털을 사용 하거나 명령줄 도구나 투구 또는 Terraform 같은 인프라 자동화 도구를 사용 하 여 Azure Kubernetes 클러스터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-136">As with most resources in Azure, you can create Azure Kubernetes clusters using the portal or using command line tools or infrastructure automation tools like Helm or Terraform.</span></span> <span data-ttu-id="e36f1-137">새 클러스터를 시작 하려면 다음 정보를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-137">To get started with a new cluster, you need to provide the following information:</span></span>

- <span data-ttu-id="e36f1-138">Azure 구독</span><span class="sxs-lookup"><span data-stu-id="e36f1-138">Azure subscription</span></span>
- <span data-ttu-id="e36f1-139">리소스 그룹</span><span class="sxs-lookup"><span data-stu-id="e36f1-139">Resource group</span></span>
- <span data-ttu-id="e36f1-140">Kubernetes 클러스터 이름</span><span class="sxs-lookup"><span data-stu-id="e36f1-140">Kubernetes cluster name</span></span>
- <span data-ttu-id="e36f1-141">Region</span><span class="sxs-lookup"><span data-stu-id="e36f1-141">Region</span></span>
- <span data-ttu-id="e36f1-142">Kubernetes 버전</span><span class="sxs-lookup"><span data-stu-id="e36f1-142">Kubernetes version</span></span>
- <span data-ttu-id="e36f1-143">DNS 이름 접두사</span><span class="sxs-lookup"><span data-stu-id="e36f1-143">DNS name prefix</span></span>
- <span data-ttu-id="e36f1-144">노드 크기</span><span class="sxs-lookup"><span data-stu-id="e36f1-144">Node size</span></span>
- <span data-ttu-id="e36f1-145">노드 수</span><span class="sxs-lookup"><span data-stu-id="e36f1-145">Node count</span></span>

<span data-ttu-id="e36f1-146">이 정보는 시작 하기에 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-146">This information is sufficient to get started.</span></span> <span data-ttu-id="e36f1-147">Azure Portal에서 생성 프로세스의 일부로 클러스터의 다음 기능에 대 한 옵션을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-147">As part of the creation process in the Azure Portal, you can also configure options for the following features of your cluster:</span></span>

- <span data-ttu-id="e36f1-148">소수 자릿수</span><span class="sxs-lookup"><span data-stu-id="e36f1-148">Scale</span></span>
- <span data-ttu-id="e36f1-149">인증</span><span class="sxs-lookup"><span data-stu-id="e36f1-149">Authentication</span></span>
- <span data-ttu-id="e36f1-150">네트워킹</span><span class="sxs-lookup"><span data-stu-id="e36f1-150">Networking</span></span>
- <span data-ttu-id="e36f1-151">모니터링</span><span class="sxs-lookup"><span data-stu-id="e36f1-151">Monitoring</span></span>
- <span data-ttu-id="e36f1-152">Tags</span><span class="sxs-lookup"><span data-stu-id="e36f1-152">Tags</span></span>

<span data-ttu-id="e36f1-153">이 [빠른 시작은 Azure Portal를 사용 하 여 AKS 클러스터를 배포 하는 과정](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal)을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-153">This [quickstart walks through deploying an AKS cluster using the Azure portal](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).</span></span>

## <a name="azure-dev-spaces"></a><span data-ttu-id="e36f1-154">Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="e36f1-154">Azure Dev Spaces</span></span>

<span data-ttu-id="e36f1-155">복잡 한 Kubernetes 클러스터는 호스트에 상당한 리소스를 요구할 수 있으므로 개발자가 단일 컴퓨터 (특히 랩톱)에서 전체 응용 프로그램을 실행 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-155">Complex Kubernetes clusters can require significant resources to host, which can make it difficult for developers to run the entire application on a single machine (especially a laptop).</span></span> <span data-ttu-id="e36f1-156">Azure Dev Spaces 개발자가 Azure에서 호스트 되는 Azure Kubernetes 클러스터의 고유한 버전으로 작업할 수 있도록 하 여이에 대 한 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-156">Azure Dev Spaces offers a solution to this by allowing developers to work with their own versions of Azure Kubernetes clusters hosted in Azure.</span></span> <span data-ttu-id="e36f1-157">Azure Dev Spaces는 AKS를 사용 하 여 마이크로 서비스 기반 응용 프로그램을 쉽게 개발할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-157">Azure Dev Spaces is designed to ease development of microservice-based applications using AKS.</span></span>

<span data-ttu-id="e36f1-158">Azure Dev Spaces의 가치를 이해 하기 위해 Microsoft Azure에서 컨테이너의 오후 Gabe Monroy, PM에서이 따옴표를 공유 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-158">To understand the value of Azure Dev Spaces, let me share this quotation from Gabe Monroy, PM Lead of Containers at Microsoft Azure:</span></span>

<span data-ttu-id="e36f1-159">"수십 개의 구성 요소로 구성 된 복잡 한 마이크로 서비스 응용 프로그램에서 버그를 수정 하려는 새 직원이 있으며 각각 자체 구성 및 지원 서비스가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-159">"Imagine you are a new employee trying to fix a bug in a complex microservices application consisting of dozens of components, each with their own configuration and backing services.</span></span> <span data-ttu-id="e36f1-160">시작 하려면 IDE 설정, 도구 체인 빌드, 컨테이너 화 된 서비스 종속성, 로컬 Kubernetes 환경, 지원 서비스에 대 한 mock 등의 작업을 비롯 하 여 프로덕션을 모방 하도록 로컬 개발 환경을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-160">To get started, you must configure your local development environment so that it can mimic production including setting up your IDE, building tool chain, containerized service dependencies, a local Kubernetes environment, mocks for backing services, and more.</span></span> <span data-ttu-id="e36f1-161">개발 환경을 설정 하는 데 소요 되는 모든 시간을 사용 하 여 첫 번째 버그를 수정 하는 데 며칠이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-161">With all the time involved setting up your development environment, fixing that first bug could take days.</span></span>

> <span data-ttu-id="e36f1-162">또는 Dev Spaces 및 AKS를 사용할 수 있습니다. "</span><span class="sxs-lookup"><span data-stu-id="e36f1-162">Or you could use Dev Spaces and AKS."</span></span>

<span data-ttu-id="e36f1-163">Azure Dev Spaces 사용 하는 프로세스에는 다음 단계가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-163">The process for working with Azure Dev Spaces involves the following steps:</span></span>

1. <span data-ttu-id="e36f1-164">개발 공간을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-164">Create the dev space.</span></span>
2. <span data-ttu-id="e36f1-165">루트 개발 공간을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-165">Configure the root dev space.</span></span>
3. <span data-ttu-id="e36f1-166">사용자 고유의 시스템 버전에 대 한 자식 개발 공간을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-166">Configure a child dev space (for your own version of the system).</span></span>
4. <span data-ttu-id="e36f1-167">Dev 공간에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-167">Connect to the dev space.</span></span>

<span data-ttu-id="e36f1-168">이러한 모든 단계는 Azure CLI 및 새로운 `azds` 명령줄 도구를 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-168">All of these steps can be performed using the Azure CLI and new  `azds` command line tools.</span></span> <span data-ttu-id="e36f1-169">예를 들어, 지정 된 Kubernetes 클러스터에 대 한 새 Azure Dev 공간을 만들려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-169">For example, to create a new Azure Dev Space for a given Kubernetes cluster, you would use a command like this one:</span></span>

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

<span data-ttu-id="e36f1-170">그런 다음 `azds prep` 명령을 사용 하 여 응용 프로그램을 실행 하는 데 필요한 Docker 및 투구 차트 자산을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-170">Next, you can use the `azds prep` command to generate the necessary Docker and Helm chart assets for running the application.</span></span> <span data-ttu-id="e36f1-171">그런 다음 `azds up`를 사용 하 여 AKS에서 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-171">Then you run your code in AKS using `azds up`.</span></span> <span data-ttu-id="e36f1-172">이 명령을 처음 실행 하면 투구 차트가 설치 되 고 사용자의 지침에 따라 컨테이너가 빌드되고 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-172">The first time you run this command, the Helm chart will be installed, and the container(s) will be built and deployed according to your instructions.</span></span> <span data-ttu-id="e36f1-173">이를 처음 실행 하면 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-173">This may take a few minutes the first time it's run.</span></span> <span data-ttu-id="e36f1-174">그러나 변경을 수행한 후 `azds space select`를 사용 하 여 사용자 고유의 자식 개발 공간에 연결 하 고 격리 된 자식 개발 공간에 업데이트를 배포 하 고 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-174">However, after you make changes, you can connect to your own child dev space using `azds space select` and then deploy and debug your updates in your isolated child dev space.</span></span> <span data-ttu-id="e36f1-175">개발 공간이 준비 되 고 실행 되 면 `azds up` 명령을 다시 실행 하거나 Visual Studio 또는 Visual Studio Code에서 기본 제공 되는 도구를 사용 하 여 업데이트를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-175">Once you have your dev space up and running, you can send updates to it by re-issuing the `azds up` command or you can use built-in tooling in Visual Studio or Visual Studio Code.</span></span> <span data-ttu-id="e36f1-176">VS Code를 사용 하 여 명령 팔레트를 사용 하 여 개발 공간에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-176">With VS Code, you use the command palette to connect to your dev space.</span></span> <span data-ttu-id="e36f1-177">그림 3-12에서는 Visual Studio에서 Azure Dev Spaces를 사용 하 여 웹 응용 프로그램을 시작 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-177">Figure 3-12 shows how to launch your web application using Azure Dev Spaces in Visual Studio.</span></span>

<span data-ttu-id="e36f1-178">**그림 3-12**](./media/azure-dev-spaces-visual-studio-launchsettings.png)
Visual Studio에서 Azure Dev Spaces에 연결 ![합니다.</span><span class="sxs-lookup"><span data-stu-id="e36f1-178">![Connect to Azure Dev Spaces in Visual Studio](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**Figure 3-12**.</span></span> <span data-ttu-id="e36f1-179">Visual Studio에서 Azure Dev Spaces에 연결</span><span class="sxs-lookup"><span data-stu-id="e36f1-179">Connect to Azure Dev Spaces in Visual Studio</span></span>

## <a name="references"></a><span data-ttu-id="e36f1-180">참조</span><span class="sxs-lookup"><span data-stu-id="e36f1-180">References</span></span>

- [<span data-ttu-id="e36f1-181">카나리아 릴리스</span><span class="sxs-lookup"><span data-stu-id="e36f1-181">Canary Release</span></span>](https://martinfowler.com/bliki/CanaryRelease.html)
- [<span data-ttu-id="e36f1-182">VS Code Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="e36f1-182">Azure Dev Spaces with VS Code</span></span>](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [<span data-ttu-id="e36f1-183">Visual Studio를 사용 하 여 Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="e36f1-183">Azure Dev Spaces with Visual Studio</span></span>](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)

>[!div class="step-by-step"]
><span data-ttu-id="e36f1-184">[이전](combine-containers-serverless-approaches.md)
>[다음](scale-containers-serverless.md)</span><span class="sxs-lookup"><span data-stu-id="e36f1-184">[Previous](combine-containers-serverless-approaches.md)
[Next](scale-containers-serverless.md)</span></span>
