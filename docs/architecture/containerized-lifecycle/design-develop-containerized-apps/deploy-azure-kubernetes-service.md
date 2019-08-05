---
title: 높은 확장성 및 가용성을 위한 마이크로 서비스 및 다중 컨테이너 애플리케이션 오케스트레이션
description: Azure Kubernetes Service를 사용하여 앱을 배포하는 방법을 알아봅니다.
ms.date: 02/15/2019
ms.openlocfilehash: 88e76b4b0a3686f4227a6aee1b7fbd2bfe55fdcc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68672630"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="83e83-103">AKS(Azure Kubernetes Service)에 배포</span><span class="sxs-lookup"><span data-stu-id="83e83-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="83e83-104">원하는 클라이언트 운영 체제를 사용하여 AKS와 상호 작용할 수 있으며, 여기서는 Microsoft Windows 및 Windows의 Ubuntu Linux 임베디드 버전에서 Bash 명령을 사용하여 상호 작용하는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-104">You can interact with AKS using your preferred client operating system, here we show how to do it with Microsoft Windows and an embedded version of Ubuntu Linux in Windows, using Bash commands.</span></span>

<span data-ttu-id="83e83-105">AKS를 사용하기 전에 갖추어야 할 필수 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-105">Prerequisites to have before using AKS are:</span></span>

- <span data-ttu-id="83e83-106">Linux 또는 Mac 개발 머신</span><span class="sxs-lookup"><span data-stu-id="83e83-106">Linux or Mac development machine</span></span>
- <span data-ttu-id="83e83-107">Windows 개발 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="83e83-107">Windows development machine</span></span>
  - <span data-ttu-id="83e83-108">Windows에서 사용하도록 설정된 개발자 모드.</span><span class="sxs-lookup"><span data-stu-id="83e83-108">Developer Mode enabled on Windows</span></span>
  - <span data-ttu-id="83e83-109">Linux용 Windows 하위 시스템</span><span class="sxs-lookup"><span data-stu-id="83e83-109">Windows Subsystem for Linux</span></span>
- <span data-ttu-id="83e83-110">[Windows, Mac 또는 Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)에 설치된 Azure CLI</span><span class="sxs-lookup"><span data-stu-id="83e83-110">Azure-CLI installed on [Windows, Mac or Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span></span>

> [!NOTE]
> <span data-ttu-id="83e83-111">다음 항목에 대한 전체 정보를 찾으려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-111">To find complete information about:</span></span>
>
> <span data-ttu-id="83e83-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span><span class="sxs-lookup"><span data-stu-id="83e83-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span></span>
>
> <span data-ttu-id="83e83-113">Linux용 Windows 하위 시스템: <https://docs.microsoft.com/windows/wsl/about></span><span class="sxs-lookup"><span data-stu-id="83e83-113">Windows Subsystem for Linux: <https://docs.microsoft.com/windows/wsl/about></span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="83e83-114">Azure에서 AKS 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="83e83-114">Create the AKS environment in Azure</span></span>

<span data-ttu-id="83e83-115">AKS 환경을 만드는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-115">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="83e83-116">Azure CLI 명령을 사용하는 방법도 있고 Azure Portal을 사용하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-116">It can be done by using Azure-CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="83e83-117">여기서는 Azure CLI를 사용하여 클러스터를 만들고 Azure Portal에서 결과를 검토하는 예제를 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-117">Here you can explore some examples using the Azure-CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="83e83-118">개발 머신에 Kubectl 및 Docker도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-118">You also need to have Kubectl and Docker in your development machine.</span></span>  

## <a name="create-the-aks-cluster"></a><span data-ttu-id="83e83-119">AKS 클러스터 만들기</span><span class="sxs-lookup"><span data-stu-id="83e83-119">Create the AKS cluster</span></span>

<span data-ttu-id="83e83-120">이 명령을 사용하여 AKS 클러스터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-120">Create the AKS cluster using this command:</span></span>

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

<span data-ttu-id="83e83-121">만들기 작업이 완료되면 Azure Portal에서 AKS가 생성된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-121">After the creation job finishes, you can see the AKS created in the Azure portal:</span></span>

<span data-ttu-id="83e83-122">리소스 그룹:</span><span class="sxs-lookup"><span data-stu-id="83e83-122">The resource group:</span></span>

![Azure AKS 리소스 그룹의 브라우저 보기.](media/aks-resource-group-view.png)

<span data-ttu-id="83e83-124">**그림 4-17**.</span><span class="sxs-lookup"><span data-stu-id="83e83-124">**Figure 4-17**.</span></span> <span data-ttu-id="83e83-125">Azure의 AKS 리소스 그룹 보기.</span><span class="sxs-lookup"><span data-stu-id="83e83-125">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="83e83-126">AKS 클러스터:</span><span class="sxs-lookup"><span data-stu-id="83e83-126">The AKS cluster:</span></span>

![AKS 리소스 그룹의 브라우저 보기.](media/aks-cluster-view.png)

<span data-ttu-id="83e83-128">**그림 4-18**.</span><span class="sxs-lookup"><span data-stu-id="83e83-128">**Figure 4-18**.</span></span> <span data-ttu-id="83e83-129">Azure의 AKS 보기.</span><span class="sxs-lookup"><span data-stu-id="83e83-129">AKS view from Azure.</span></span>

<span data-ttu-id="83e83-130">`Azure-CLI` 및 `Kubectl`을 사용하여 만든 노드를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-130">You can also view the node created using `Azure-CLI` and `Kubectl`.</span></span>

<span data-ttu-id="83e83-131">먼저, 자격 증명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-131">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![위 명령의 콘솔 출력: /root/.kube/config의 현재 컨텍스트로 병합된 "MsSampleK8Cluster"](media/get-credentials-command-result.png)

<span data-ttu-id="83e83-133">**그림 4-19**.</span><span class="sxs-lookup"><span data-stu-id="83e83-133">**Figure 4-19**.</span></span> <span data-ttu-id="83e83-134">`aks get-credentials` 명령 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-134">`aks get-credentials` command result.</span></span>

<span data-ttu-id="83e83-135">다음과 같이 Kubectl에서 노드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-135">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![위 명령의 콘솔 출력: 상태, 기간(실행된 시간) 및 버전이 있는 노드 목록](media/kubectl-get-nodes-command-result.png)

<span data-ttu-id="83e83-137">**그림 4-20**.</span><span class="sxs-lookup"><span data-stu-id="83e83-137">**Figure 4-20**.</span></span> <span data-ttu-id="83e83-138">`kubectl get nodes` 명령 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="83e83-138">`kubectl get nodes` command result.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="83e83-139">[이전](orchestrate-high-scalability-availability.md)
>[다음](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="83e83-139">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
