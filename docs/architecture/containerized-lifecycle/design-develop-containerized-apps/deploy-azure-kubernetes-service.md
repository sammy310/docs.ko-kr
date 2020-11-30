---
title: 높은 확장성 및 가용성을 위한 마이크로 서비스 및 다중 컨테이너 애플리케이션 오케스트레이션
description: Azure Kubernetes Service를 사용하여 앱을 배포하는 방법을 알아봅니다.
ms.date: 08/06/2020
ms.openlocfilehash: ba9887c0a4837c16a60ebeb006416c0fa8c105e0
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032205"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="9d7e3-103">AKS(Azure Kubernetes Service)에 배포</span><span class="sxs-lookup"><span data-stu-id="9d7e3-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="9d7e3-104">Azure CLI(Azure 명령줄 인터페이스)가 설치된 기본 클라이언트 운영 체제(Windows, macOS 또는 Linux)를 사용하여 AKS와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-104">You can interact with AKS using your preferred client operating system (Windows, macOS, or Linux) with Azure command-line interface(Azure CLI) installed.</span></span> <span data-ttu-id="9d7e3-105">자세한 내용은 [Azure CLI 설명서](/cli/azure/?view=azure-cli-latest) 및 사용 가능한 환경에 대한 [설치 가이드](/cli/azure/install-azure-cli?view=azure-cli-latest)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-105">For more details, refer [Azure CLI documentation](/cli/azure/?view=azure-cli-latest) and [Installation guide](/cli/azure/install-azure-cli?view=azure-cli-latest) for the available environments.</span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="9d7e3-106">Azure에서 AKS 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="9d7e3-106">Create the AKS environment in Azure</span></span>

<span data-ttu-id="9d7e3-107">AKS 환경을 만드는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-107">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="9d7e3-108">Azure CLI 명령을 사용하는 방법도 있고 Azure Portal을 사용하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-108">It can be done by using Azure CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="9d7e3-109">여기서는 Azure CLI를 사용하여 클러스터를 만들고 Azure Portal에서 결과를 검토하는 예제를 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-109">Here you can explore some examples using the Azure CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="9d7e3-110">개발 머신에 Kubectl 및 Docker도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-110">You also need to have Kubectl and Docker in your development machine.</span></span>

## <a name="create-the-aks-cluster"></a><span data-ttu-id="9d7e3-111">AKS 클러스터 만들기</span><span class="sxs-lookup"><span data-stu-id="9d7e3-111">Create the AKS cluster</span></span>

<span data-ttu-id="9d7e3-112">이 명령을 사용하여 AKS 클러스터를 만듭니다(리소스 그룹이 있어야 함).</span><span class="sxs-lookup"><span data-stu-id="9d7e3-112">Create the AKS cluster using this command (the resource group must exist):</span></span>

```console
az aks create --resource-group explore-docker-aks-rg --name explore-docker-aks --node-vm-size Standard_B2s --node-count 1 --generate-ssh-keys --location westeurope
```

> [!NOTE]
> <span data-ttu-id="9d7e3-113">`--node-vm-size` 및 `--node-count` 매개 변수 값은 샘플/개발 애플리케이션에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-113">The `--node-vm-size` and `--node-count` parameter values are good enough for a sample/dev application.</span></span>

<span data-ttu-id="9d7e3-114">만들기 작업이 완료되면 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-114">After the creation job finishes, you can see:</span></span>

- <span data-ttu-id="9d7e3-115">초기 리소스 그룹에서 만든 AKS 클러스터</span><span class="sxs-lookup"><span data-stu-id="9d7e3-115">The AKS cluster created in the initial resource group</span></span>
- <span data-ttu-id="9d7e3-116">다음 이미지에 표시된 것처럼 AKS 클러스터와 관련된 리소스를 포함하는 새로운 관련 리소스 그룹</span><span class="sxs-lookup"><span data-stu-id="9d7e3-116">A new, related resource group, containing the resources related to the AKS cluster, as show in the following images.</span></span>

<span data-ttu-id="9d7e3-117">AKS 클러스터를 포함하는 초기 리소스 그룹:</span><span class="sxs-lookup"><span data-stu-id="9d7e3-117">The initial resource group, with the AKS cluster:</span></span>

![AKS 리소스 그룹의 브라우저 보기.](media/deploy-azure-kubernetes-service/aks-cluster-view.png)

<span data-ttu-id="9d7e3-119">**그림 4-17**.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-119">**Figure 4-17**.</span></span> <span data-ttu-id="9d7e3-120">Azure의 AKS 리소스 그룹 보기.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-120">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="9d7e3-121">AKS 클러스터 리소스 그룹:</span><span class="sxs-lookup"><span data-stu-id="9d7e3-121">The AKS cluster resource group:</span></span>

![Azure AKS 리소스 그룹의 브라우저 보기.](media/deploy-azure-kubernetes-service/aks-resource-group-view.png)

<span data-ttu-id="9d7e3-123">**그림 4-18**.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-123">**Figure 4-18**.</span></span> <span data-ttu-id="9d7e3-124">Azure의 AKS 보기.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-124">AKS view from Azure.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d7e3-125">일반적으로 AKS 클러스터 리소스 그룹에서는 리소스를 수정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-125">In general, you shouldn't need to modify the resources in the AKS cluster resource group.</span></span> <span data-ttu-id="9d7e3-126">예를 들어 AKS 클러스터를 삭제하면 리소스 그룹이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-126">For example, the resource group is deleted when you delete the AKS cluster.</span></span>

<span data-ttu-id="9d7e3-127">`Azure CLI` 및 `Kubectl`을 사용하여 만든 노드를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-127">You can also view the node created using `Azure CLI` and `Kubectl`.</span></span>

<span data-ttu-id="9d7e3-128">먼저, 자격 증명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-128">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![위 명령의 콘솔 출력: /home/miguel/.kube/config에서 “explore-docker-aks”가 현재 컨텍스트로 병합됩니다.](media/deploy-azure-kubernetes-service/get-credentials-command-result.png)

<span data-ttu-id="9d7e3-130">**그림 4-19**.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-130">**Figure 4-19**.</span></span> <span data-ttu-id="9d7e3-131">`aks get-credentials` 명령 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-131">`aks get-credentials` command result.</span></span>

<span data-ttu-id="9d7e3-132">다음과 같이 Kubectl에서 노드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-132">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![위 명령의 콘솔 출력: 상태, 기간(실행된 시간) 및 버전이 있는 노드 목록](media/deploy-azure-kubernetes-service/kubectl-get-nodes-command-result.png)

<span data-ttu-id="9d7e3-134">**그림 4-20**.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-134">**Figure 4-20**.</span></span> <span data-ttu-id="9d7e3-135">`kubectl get nodes` 명령 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="9d7e3-135">`kubectl get nodes` command result.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="9d7e3-136">[이전](orchestrate-high-scalability-availability.md)
> [다음](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="9d7e3-136">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
