---
title: Azure에서 컨테이너 배포
description: Azure Container Registry, Azure Kubernetes Service 및 Azure Dev Spaces를 사용 하 여 Azure에 컨테이너를 배포 합니다.
ms.date: 04/13/2020
ms.openlocfilehash: 6238460c6129583c34e6b328c38ed9042f32f3d6
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199562"
---
# <a name="deploying-containers-in-azure"></a><span data-ttu-id="3d823-103">Azure에서 컨테이너 배포</span><span class="sxs-lookup"><span data-stu-id="3d823-103">Deploying containers in Azure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="3d823-104">이 장과 1 장에서는 컨테이너에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-104">We've discussed containers in this chapter and in chapter 1.</span></span> <span data-ttu-id="3d823-105">컨테이너는 이식성을 비롯 한 클라우드 네이티브 응용 프로그램에 많은 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-105">We've seen that containers provide many benefits to cloud-native applications, including portability.</span></span> <span data-ttu-id="3d823-106">Azure 클라우드에서는 스테이징 및 프로덕션 환경에서 동일한 컨테이너 화 된 서비스를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-106">In the Azure cloud, you can deploy the same containerized services across staging and production environments.</span></span> <span data-ttu-id="3d823-107">Azure는 이러한 컨테이너 화 된 워크 로드를 호스트 하기 위한 몇 가지 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-107">Azure provides several options for hosting these containerized workloads:</span></span>

- <span data-ttu-id="3d823-108">AKS(Azure Kubernetes Services)</span><span class="sxs-lookup"><span data-stu-id="3d823-108">Azure Kubernetes Services (AKS)</span></span>
- <span data-ttu-id="3d823-109">ACI(Azure Container Instance)</span><span class="sxs-lookup"><span data-stu-id="3d823-109">Azure Container Instance (ACI)</span></span>
- <span data-ttu-id="3d823-110">컨테이너에 대 한 Azure Web Apps</span><span class="sxs-lookup"><span data-stu-id="3d823-110">Azure Web Apps for Containers</span></span>

## <a name="azure-container-registry"></a><span data-ttu-id="3d823-111">Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="3d823-111">Azure Container Registry</span></span>

<span data-ttu-id="3d823-112">마이크로 서비스을 컨테이너 화 때 먼저 빌드 컨테이너 "이미지"를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-112">When containerizing a microservice, you first a build container "image."</span></span> <span data-ttu-id="3d823-113">이미지는 서비스 코드, 종속성 및 런타임의 이진 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-113">The image is a binary representation of the service code, dependencies, and runtime.</span></span> <span data-ttu-id="3d823-114">Docker API의 `Docker Build` 명령을 사용 하 여 이미지를 수동으로 만들 수 있지만, 자동화 된 빌드 프로세스의 일부로 생성 하는 것이 더 나은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-114">While you can manually create an image using the `Docker Build` command from the Docker API, a better approach is to create it as part of an automated build process.</span></span>

<span data-ttu-id="3d823-115">컨테이너 이미지를 만든 후에는 컨테이너 레지스트리에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-115">Once created, container images are stored in container registries.</span></span> <span data-ttu-id="3d823-116">컨테이너 이미지를 작성, 저장 및 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-116">They enable you to build, store, and manage container images.</span></span> <span data-ttu-id="3d823-117">공개 및 개인의 여러 레지스트리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-117">There are many registries available, both public and private.</span></span> <span data-ttu-id="3d823-118">ACR (Azure Container Registry)은 Azure 클라우드의 완전히 관리 되는 컨테이너 레지스트리 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-118">Azure Container Registry (ACR) is a fully managed container registry service in the Azure cloud.</span></span> <span data-ttu-id="3d823-119">Azure 네트워크 내에 이미지를 유지 하므로 Azure 컨테이너 호스트에 배포 하는 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-119">It persists your images inside the Azure network, reducing the time to deploy them to Azure container hosts.</span></span> <span data-ttu-id="3d823-120">다른 Azure 리소스에 사용 하는 것과 동일한 보안 및 id 절차를 사용 하 여 보안을 유지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-120">You can also secure them using the same security and identity procedures that you use for other Azure resources.</span></span>

<span data-ttu-id="3d823-121">[Azure Portal](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal), [Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli)또는 [PowerShell 도구](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell)를 사용 하 여 Azure Container Registry를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-121">You create an Azure Container Registry using the [Azure portal](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal), [Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli), or [PowerShell tools](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell).</span></span> <span data-ttu-id="3d823-122">Azure에서 레지스트리를 만드는 방법은 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-122">Creating a registry in Azure is simple.</span></span> <span data-ttu-id="3d823-123">Azure 구독, 리소스 그룹 및 고유한 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-123">It requires an Azure subscription, resource group, and a unique name.</span></span> <span data-ttu-id="3d823-124">그림 3-11에서는에서 `registryname.azurecr.io`호스트 되는 레지스트리를 만들기 위한 기본 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-124">Figure 3-11 shows the basic options for creating a registry, which will be hosted at `registryname.azurecr.io`.</span></span>

![컨테이너 레지스트리 만들기](./media/create-container-registry.png)

<span data-ttu-id="3d823-126">**그림 3-11**.</span><span class="sxs-lookup"><span data-stu-id="3d823-126">**Figure 3-11**.</span></span> <span data-ttu-id="3d823-127">컨테이너 레지스트리 만들기</span><span class="sxs-lookup"><span data-stu-id="3d823-127">Create container registry</span></span>

<span data-ttu-id="3d823-128">레지스트리를 만든 후에는이를 사용 하기 전에 인증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-128">Once you've created the registry, you'll need to authenticate with it before you can use it.</span></span> <span data-ttu-id="3d823-129">일반적으로 Azure CLI 명령을 사용 하 여 레지스트리에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-129">Typically, you'll log into the registry using the Azure CLI command:</span></span>

```azurecli
az acr login --name *registryname*
```

<span data-ttu-id="3d823-130">인증 된 후에는 docker 명령을 사용 하 여 컨테이너 이미지를 푸시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-130">Once authenticated, you can use docker commands to push container images to it.</span></span> <span data-ttu-id="3d823-131">그러나 이렇게 하려면 먼저 ACR 로그인 서버의 정규화 된 이름 (URL)을 사용 하 여 이미지에 태그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-131">Before you can do so, however, you must tag your image with the fully qualified name (URL) of your ACR login server.</span></span> <span data-ttu-id="3d823-132">*Registryname*. azurecr.io 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-132">It will have the format *registryname*.azurecr.io.</span></span>

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="3d823-133">이미지에 태그를 지정한 후 `docker push` 명령을 사용 하 여 ACR 인스턴스로 이미지를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-133">After you've tagged the image, you use the `docker push` command to push the image to your ACR instance.</span></span>

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="3d823-134">이미지를 레지스트리에 푸시한 후에는 다음 명령을 사용 하 여 로컬 Docker 환경에서 이미지를 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-134">After you push an image to the registry, it's a good idea to remove the image from your local Docker environment, using this command:</span></span>

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="3d823-135">개발자는 컨테이너 레지스트리에 이미지를 수동으로 푸시하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-135">As a best practice, developers shouldn't manually push images to a container registry.</span></span> <span data-ttu-id="3d823-136">대신 GitHub 또는 Azure DevOps와 같은 도구에 정의 된 빌드 파이프라인이이 프로세스를 담당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-136">Instead, a build pipeline defined in a tool like GitHub or Azure DevOps should be responsible for this process.</span></span> <span data-ttu-id="3d823-137">[클라우드-기본 DevOps 챕터](devops.md)에서 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3d823-137">Learn more in the [Cloud-Native DevOps chapter](devops.md).</span></span>

## <a name="acr-tasks"></a><span data-ttu-id="3d823-138">ACR 작업</span><span class="sxs-lookup"><span data-stu-id="3d823-138">ACR Tasks</span></span>

<span data-ttu-id="3d823-139">[ACR 작업](https://docs.microsoft.com/azure/container-registry/container-registry-tasks-overview) 은 Azure Container Registry에서 사용할 수 있는 기능 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-139">[ACR Tasks](https://docs.microsoft.com/azure/container-registry/container-registry-tasks-overview) is a set of features available from the Azure Container Registry.</span></span> <span data-ttu-id="3d823-140">Azure 클라우드에서 컨테이너 이미지를 작성 하 고 관리 하 여 [내부 루프 개발 주기](https://docs.microsoft.com/dotnet/architecture/containerized-lifecycle/design-develop-containerized-apps/docker-apps-inner-loop-workflow) 를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-140">It extends your [inner-loop development cycle](https://docs.microsoft.com/dotnet/architecture/containerized-lifecycle/design-develop-containerized-apps/docker-apps-inner-loop-workflow) by building and managing container images in the Azure cloud.</span></span> <span data-ttu-id="3d823-141">개발 컴퓨터에서 및 `docker build` `docker push` 를 로컬로 호출 하는 대신 클라우드의 ACR 작업에 의해 자동으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-141">Instead of invoking a `docker build` and `docker push` locally on your development machine, they're automatically handled by ACR Tasks in the cloud.</span></span>

<span data-ttu-id="3d823-142">다음 AZ CLI 명령은 컨테이너 이미지를 빌드하고 ACR로 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-142">The following AZ CLI command both builds a container image and pushes it to ACR:</span></span>

```azurecli
# create a container registry
az acr create --resource-group myResourceGroup --name myContainerRegistry008 --sku Basic

# build container image in ACR and push it into your container regsitry
az acr build --image sample/hello-world:v1  --registry myContainerRegistry008 --file Dockerfile .
```

<span data-ttu-id="3d823-143">이전 명령 블록에서 볼 수 있듯이, 개발 컴퓨터에 Docker Desktop을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-143">As you can see from the previous command block, there's no need to install Docker Desktop on your development machine.</span></span> <span data-ttu-id="3d823-144">또한 소스 코드와 기본 이미지 업데이트 모두에서 컨테이너 이미지를 다시 작성 하도록 ACR 작업 트리거를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-144">Additionally, you can configure ACR Task triggers to rebuild containers images on both source code and base image updates.</span></span>

## <a name="azure-kubernetes-service"></a><span data-ttu-id="3d823-145">Azure Kubernetes Service</span><span class="sxs-lookup"><span data-stu-id="3d823-145">Azure Kubernetes Service</span></span>

<span data-ttu-id="3d823-146">이 장에서는 Azure Kubernetes Service (AKS)의 길이에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-146">We discussed Azure Kubernetes Service (AKS) at length in this chapter.</span></span> <span data-ttu-id="3d823-147">컨테이너 화 된 클라우드 네이티브 응용 프로그램을 관리 하는 사실상 컨테이너 오 케 스트레이 터입니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-147">We've seen that it's the de facto container orchestrator managing containerized cloud-native applications.</span></span>

<span data-ttu-id="3d823-148">ACR 같은 레지스트리에 이미지를 배포한 후에는 AKS를 자동으로 풀 및 배포 하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-148">Once you deploy an image to a registry, such as ACR, you can configure AKS to automatically pull and deploy it.</span></span> <span data-ttu-id="3d823-149">CI/CD 파이프라인이 준비 되 면 업데이트를 신속 하 게 배포할 때 관련 된 위험을 최소화 하기 위해 [카나리아 릴리스](https://martinfowler.com/bliki/CanaryRelease.html) 전략을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-149">With a CI/CD pipeline in place, you might configure a  [canary release](https://martinfowler.com/bliki/CanaryRelease.html) strategy to minimize the risk involved when rapidly deploying updates.</span></span> <span data-ttu-id="3d823-150">새 버전의 앱은 전송 된 트래픽이 없는 프로덕션 환경에서 초기에 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-150">The new version of the app is initially configured in production with no traffic routed to it.</span></span> <span data-ttu-id="3d823-151">그러면 시스템에서 사용자의 일부를 새로 배포 된 버전으로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-151">Then, the system will route a small percentage of users to the newly deployed version.</span></span> <span data-ttu-id="3d823-152">팀이 새 버전에서 자신감을 얻게 되 면 더 많은 인스턴스를 출시 하 고 이전을 사용 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-152">As the team gains confidence in the new version, it can roll out more instances and retire the old.</span></span> <span data-ttu-id="3d823-153">AKS는이 스타일의 배포를 쉽게 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-153">AKS easily supports this style of deployment.</span></span>

<span data-ttu-id="3d823-154">Azure의 대부분 리소스와 마찬가지로 포털, 명령줄 또는 투구 또는 Terraform 같은 자동화 도구를 사용 하 여 Azure Kubernetes Service 클러스터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-154">As with most resources in Azure, you can create an Azure Kubernetes Service cluster using the portal, command-line, or automation tools like Helm or Terraform.</span></span> <span data-ttu-id="3d823-155">새 클러스터를 시작 하려면 다음 정보를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-155">To get started with a new cluster, you need to provide the following information:</span></span>

- <span data-ttu-id="3d823-156">Azure 구독</span><span class="sxs-lookup"><span data-stu-id="3d823-156">Azure subscription</span></span>
- <span data-ttu-id="3d823-157">Resource group</span><span class="sxs-lookup"><span data-stu-id="3d823-157">Resource group</span></span>
- <span data-ttu-id="3d823-158">Kubernetes 클러스터 이름</span><span class="sxs-lookup"><span data-stu-id="3d823-158">Kubernetes cluster name</span></span>
- <span data-ttu-id="3d823-159">지역</span><span class="sxs-lookup"><span data-stu-id="3d823-159">Region</span></span>
- <span data-ttu-id="3d823-160">Kubernetes 버전</span><span class="sxs-lookup"><span data-stu-id="3d823-160">Kubernetes version</span></span>
- <span data-ttu-id="3d823-161">DNS 이름 접두사</span><span class="sxs-lookup"><span data-stu-id="3d823-161">DNS name prefix</span></span>
- <span data-ttu-id="3d823-162">노드 크기</span><span class="sxs-lookup"><span data-stu-id="3d823-162">Node size</span></span>
- <span data-ttu-id="3d823-163">노드 수</span><span class="sxs-lookup"><span data-stu-id="3d823-163">Node count</span></span>

<span data-ttu-id="3d823-164">이 정보는 시작 하기에 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-164">This information is sufficient to get started.</span></span> <span data-ttu-id="3d823-165">Azure Portal 만들기 프로세스의 일부로 클러스터의 다음 기능에 대 한 옵션을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-165">As part of the creation process in the Azure portal, you can also configure options for the following features of your cluster:</span></span>

- <span data-ttu-id="3d823-166">확장</span><span class="sxs-lookup"><span data-stu-id="3d823-166">Scale</span></span>
- <span data-ttu-id="3d823-167">인증</span><span class="sxs-lookup"><span data-stu-id="3d823-167">Authentication</span></span>
- <span data-ttu-id="3d823-168">네트워킹</span><span class="sxs-lookup"><span data-stu-id="3d823-168">Networking</span></span>
- <span data-ttu-id="3d823-169">모니터링</span><span class="sxs-lookup"><span data-stu-id="3d823-169">Monitoring</span></span>
- <span data-ttu-id="3d823-170">태그들</span><span class="sxs-lookup"><span data-stu-id="3d823-170">Tags</span></span>

<span data-ttu-id="3d823-171">이 [빠른 시작은 Azure Portal를 사용 하 여 AKS 클러스터를 배포 하는 과정](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal)을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-171">This [quickstart walks through deploying an AKS cluster using the Azure portal](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).</span></span>

## <a name="azure-dev-spaces"></a><span data-ttu-id="3d823-172">Azure Dev 공간</span><span class="sxs-lookup"><span data-stu-id="3d823-172">Azure Dev Spaces</span></span>

<span data-ttu-id="3d823-173">클라우드 네이티브 응용 프로그램을 신속 하 게 확장 하 여 큰 계산 리소스를 실행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-173">Cloud-native applications can quickly grow large and complex, requiring significant compute resources to run.</span></span> <span data-ttu-id="3d823-174">이러한 시나리오에서는 전체 응용 프로그램을 개발 컴퓨터 (특히 랩톱)에서 호스팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-174">In these scenarios, the entire application can't be hosted on a development machine (especially a laptop).</span></span> <span data-ttu-id="3d823-175">Azure Dev Spaces AKS를 사용 하 여이 문제를 해결 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-175">Azure Dev Spaces is designed to address this problem using AKS.</span></span> <span data-ttu-id="3d823-176">개발자는이를 통해 AKS development 클러스터에 응용 프로그램의 나머지 부분을 호스트 하는 동안 로컬 버전의 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-176">It enables developers to work with a local version of their services while hosting the rest of the application in an AKS development cluster.</span></span>

<span data-ttu-id="3d823-177">개발자는 전체 컨테이너 화 된 응용 프로그램을 포함 하는 AKS 클러스터에서 실행 중인 (개발) 인스턴스를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-177">Developers share a running (development) instance in an AKS cluster that contains the entire containerized application.</span></span> <span data-ttu-id="3d823-178">그러나 해당 컴퓨터에 설정 된 개인 공간을 사용 하 여 로컬에서 서비스를 개발 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-178">But they use personal spaces set up on their machine to locally develop their services.</span></span> <span data-ttu-id="3d823-179">준비가 되 면 종속성을 복제 하지 않고 AKS 클러스터에서 종단 간 테스트를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-179">When ready, they test from end-to-end in the AKS cluster - without replicating dependencies.</span></span> <span data-ttu-id="3d823-180">Azure Dev Spaces AKS의 서비스를 사용 하 여 로컬 컴퓨터의 코드를 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-180">Azure Dev Spaces merges code from the local machine with services in AKS.</span></span> <span data-ttu-id="3d823-181">개발자는 Visual Studio 또는 Visual Studio Code를 사용 하 여 Kubernetes에서 직접 코드를 신속 하 게 반복 하 고 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-181">Developers can rapidly iterate and debug code directly in Kubernetes using Visual Studio or Visual Studio Code.</span></span>

<span data-ttu-id="3d823-182">Azure Dev Spaces의 가치를 이해 하기 위해 Microsoft Azure에서 컨테이너의 오후 Gabe Monroy, PM에서이 따옴표를 공유 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-182">To understand the value of Azure Dev Spaces, let me share this quotation from Gabe Monroy, PM Lead of Containers at Microsoft Azure:</span></span>

> <span data-ttu-id="3d823-183">수십 개의 구성 요소로 구성 된 복잡 한 마이크로 서비스 응용 프로그램에서 버그를 수정 하려고 하는 새로운 직원이 있는데, 각각 자체 구성 및 지원 서비스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-183">Imagine you're a new employee trying to fix a bug in a complex microservices application consisting of dozens of components, each with their own configuration and backing services.</span></span> <span data-ttu-id="3d823-184">시작 하려면 IDE 설정, 도구 체인 빌드, 컨테이너 화 된 서비스 종속성, 로컬 Kubernetes 환경, 지원 서비스에 대 한 mock 등의 작업을 비롯 하 여 프로덕션을 모방 하도록 로컬 개발 환경을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-184">To get started, you must configure your local development environment so that it can mimic production including setting up your IDE, building tool chain, containerized service dependencies, a local Kubernetes environment, mocks for backing services, and more.</span></span> <span data-ttu-id="3d823-185">개발 환경을 설정 하는 데 소요 되는 모든 시간을 사용 하 여 첫 번째 버그를 수정 하는 데 며칠이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-185">With all the time involved setting up your development environment, fixing that first bug could take days.</span></span>
> <span data-ttu-id="3d823-186">또는 Dev Spaces 및 AKS를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-186">Or you could use Dev Spaces and AKS.</span></span>

<span data-ttu-id="3d823-187">Azure Dev Spaces 사용 하는 프로세스에는 다음 단계가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-187">The process for working with Azure Dev Spaces involves the following steps:</span></span>

1. <span data-ttu-id="3d823-188">개발 공간을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-188">Create the dev space.</span></span>
2. <span data-ttu-id="3d823-189">루트 개발 공간을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-189">Configure the root dev space.</span></span>
3. <span data-ttu-id="3d823-190">사용자 고유의 시스템 버전에 대 한 자식 개발 공간을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-190">Configure a child dev space (for your own version of the system).</span></span>
4. <span data-ttu-id="3d823-191">Dev 공간에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-191">Connect to the dev space.</span></span>

<span data-ttu-id="3d823-192">이러한 모든 단계는 Azure CLI 및 새로운 `azds` 명령줄 도구를 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-192">All of these steps can be performed using the Azure CLI and new  `azds` command-line tools.</span></span> <span data-ttu-id="3d823-193">예를 들어, 지정 된 Kubernetes 클러스터에 대 한 새 Azure Dev 공간을 만들려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-193">For example, to create a new Azure Dev Space for a given Kubernetes cluster, you would use a command like this one:</span></span>

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

<span data-ttu-id="3d823-194">그런 다음 `azds prep` 명령을 사용 하 여 응용 프로그램을 실행 하는 데 필요한 Docker 및 투구 차트 자산을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-194">Next, you can use the `azds prep` command to generate the necessary Docker and Helm chart assets for running the application.</span></span> <span data-ttu-id="3d823-195">그런 다음를 사용 하 여 `azds up`AKS에서 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-195">Then you run your code in AKS using `azds up`.</span></span> <span data-ttu-id="3d823-196">이 명령을 처음 실행 하면 투구 차트가 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-196">The first time you run this command, the Helm chart will be installed.</span></span> <span data-ttu-id="3d823-197">컨테이너는 사용자의 지침에 따라 빌드되고 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-197">The containers will be built and deployed according to your instructions.</span></span> <span data-ttu-id="3d823-198">이 작업은 처음 실행 될 때까지 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-198">This task may take a few minutes the first time it's run.</span></span> <span data-ttu-id="3d823-199">그러나를 변경한 후에는를 사용 하 여 `azds space select` 사용자 고유의 자식 개발 공간에 연결한 다음 격리 된 자식 개발 공간에서 업데이트를 배포 하 고 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-199">However, after you make changes, you can connect to your own child dev space using `azds space select` and then deploy and debug your updates in your isolated child dev space.</span></span> <span data-ttu-id="3d823-200">개발 공간이 준비 되 고 실행 되 면 `azds up` 명령을 다시 실행 하 여 업데이트를 보내거나 Visual Studio 또는 Visual Studio Code에서 기본 제공 되는 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-200">Once you have your dev space up and running, you can send updates to it by reissuing the `azds up` command or you can use built-in tooling in Visual Studio or Visual Studio Code.</span></span> <span data-ttu-id="3d823-201">VS Code를 사용 하 여 명령 팔레트를 사용 하 여 개발 공간에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-201">With VS Code, you use the command palette to connect to your dev space.</span></span> <span data-ttu-id="3d823-202">그림 3-12에서는 Visual Studio에서 Azure Dev Spaces를 사용 하 여 웹 응용 프로그램을 시작 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-202">Figure 3-12 shows how to launch your web application using Azure Dev Spaces in Visual Studio.</span></span>

<span data-ttu-id="3d823-203">![Visual Studio](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**그림 3-12**에서 Azure Dev Spaces에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d823-203">![Connect to Azure Dev Spaces in Visual Studio](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**Figure 3-12**.</span></span> <span data-ttu-id="3d823-204">Visual Studio에서 Azure Dev Spaces에 연결</span><span class="sxs-lookup"><span data-stu-id="3d823-204">Connect to Azure Dev Spaces in Visual Studio</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3d823-205">[이전](combine-containers-serverless-approaches.md)
>[다음](scale-containers-serverless.md)</span><span class="sxs-lookup"><span data-stu-id="3d823-205">[Previous](combine-containers-serverless-approaches.md)
[Next](scale-containers-serverless.md)</span></span>
