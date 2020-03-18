---
title: 높은 확장성 및 가용성을 위한 마이크로 서비스 및 다중 컨테이너 애플리케이션 오케스트레이션
description: Azure Kubernetes Service를 사용하여 앱을 배포하는 방법을 알아봅니다.
ms.date: 02/15/2019
ms.openlocfilehash: 0aa2f83fbf8f9a8815d65730002943cca748643d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "71182363"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="6844a-103">AKS(Azure Kubernetes Service)에 배포</span><span class="sxs-lookup"><span data-stu-id="6844a-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="6844a-104">원하는 클라이언트 운영 체제를 사용하여 AKS와 상호 작용할 수 있으며, 여기서는 Microsoft Windows 및 Windows의 Ubuntu Linux 임베디드 버전에서 Bash 명령을 사용하여 상호 작용하는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-104">You can interact with AKS using your preferred client operating system, here we show how to do it with Microsoft Windows and an embedded version of Ubuntu Linux in Windows, using Bash commands.</span></span>

<span data-ttu-id="6844a-105">AKS를 사용하기 전에 갖추어야 할 필수 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-105">Prerequisites to have before using AKS are:</span></span>

- <span data-ttu-id="6844a-106">Linux 또는 Mac 개발 머신</span><span class="sxs-lookup"><span data-stu-id="6844a-106">Linux or Mac development machine</span></span>
- <span data-ttu-id="6844a-107">Windows 개발 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="6844a-107">Windows development machine</span></span>
  - <span data-ttu-id="6844a-108">Windows에서 사용하도록 설정된 개발자 모드.</span><span class="sxs-lookup"><span data-stu-id="6844a-108">Developer Mode enabled on Windows</span></span>
  - <span data-ttu-id="6844a-109">Linux용 Windows 하위 시스템</span><span class="sxs-lookup"><span data-stu-id="6844a-109">Windows Subsystem for Linux</span></span>
- <span data-ttu-id="6844a-110">[Windows, Mac 또는 Linux](https://docs.microsoft.com/cli/azure/install-azure-cli)에 설치된 Azure CLI</span><span class="sxs-lookup"><span data-stu-id="6844a-110">Azure-CLI installed on [Windows, Mac or Linux](https://docs.microsoft.com/cli/azure/install-azure-cli)</span></span>

> [!NOTE]
> <span data-ttu-id="6844a-111">다음 항목에 대한 전체 정보를 찾으려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-111">To find complete information about:</span></span>
>
> <span data-ttu-id="6844a-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index></span><span class="sxs-lookup"><span data-stu-id="6844a-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index></span></span>
>
> <span data-ttu-id="6844a-113">Linux용 Windows 하위 시스템: <https://docs.microsoft.com/windows/wsl/about></span><span class="sxs-lookup"><span data-stu-id="6844a-113">Windows Subsystem for Linux: <https://docs.microsoft.com/windows/wsl/about></span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="6844a-114">Azure에서 AKS 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="6844a-114">Create the AKS environment in Azure</span></span>

<span data-ttu-id="6844a-115">AKS 환경을 만드는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-115">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="6844a-116">Azure CLI 명령을 사용하는 방법도 있고 Azure Portal을 사용하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-116">It can be done by using Azure-CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="6844a-117">여기서는 Azure CLI를 사용하여 클러스터를 만들고 Azure Portal에서 결과를 검토하는 예제를 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-117">Here you can explore some examples using the Azure-CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="6844a-118">개발 머신에 Kubectl 및 Docker도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-118">You also need to have Kubectl and Docker in your development machine.</span></span>  

## <a name="create-the-aks-cluster"></a><span data-ttu-id="6844a-119">AKS 클러스터 만들기</span><span class="sxs-lookup"><span data-stu-id="6844a-119">Create the AKS cluster</span></span>

<span data-ttu-id="6844a-120">이 명령을 사용하여 AKS 클러스터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-120">Create the AKS cluster using this command:</span></span>

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

<span data-ttu-id="6844a-121">만들기 작업이 완료되면 Azure Portal에서 AKS가 생성된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-121">After the creation job finishes, you can see the AKS created in the Azure portal:</span></span>

<span data-ttu-id="6844a-122">리소스 그룹:</span><span class="sxs-lookup"><span data-stu-id="6844a-122">The resource group:</span></span>

![Azure AKS 리소스 그룹의 브라우저 보기.](media/aks-resource-group-view.png)

<span data-ttu-id="6844a-124">**그림 4-17**.</span><span class="sxs-lookup"><span data-stu-id="6844a-124">**Figure 4-17**.</span></span> <span data-ttu-id="6844a-125">Azure의 AKS 리소스 그룹 보기.</span><span class="sxs-lookup"><span data-stu-id="6844a-125">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="6844a-126">AKS 클러스터:</span><span class="sxs-lookup"><span data-stu-id="6844a-126">The AKS cluster:</span></span>

![AKS 리소스 그룹의 브라우저 보기.](media/aks-cluster-view.png)

<span data-ttu-id="6844a-128">**그림 4-18**.</span><span class="sxs-lookup"><span data-stu-id="6844a-128">**Figure 4-18**.</span></span> <span data-ttu-id="6844a-129">Azure의 AKS 보기.</span><span class="sxs-lookup"><span data-stu-id="6844a-129">AKS view from Azure.</span></span>

<span data-ttu-id="6844a-130">`Azure-CLI` 및 `Kubectl`을 사용하여 만든 노드를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-130">You can also view the node created using `Azure-CLI` and `Kubectl`.</span></span>

<span data-ttu-id="6844a-131">먼저, 자격 증명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-131">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![위 명령의 콘솔 출력: /root/.kube/config의 현재 컨텍스트로 병합된 "MsSampleK8Cluster"](media/get-credentials-command-result.png)

<span data-ttu-id="6844a-133">**그림 4-19**.</span><span class="sxs-lookup"><span data-stu-id="6844a-133">**Figure 4-19**.</span></span> <span data-ttu-id="6844a-134">`aks get-credentials` 명령 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-134">`aks get-credentials` command result.</span></span>

<span data-ttu-id="6844a-135">다음과 같이 Kubectl에서 노드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-135">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![위 명령의 콘솔 출력: 상태, 기간(실행된 시간) 및 버전이 있는 노드 목록](media/kubectl-get-nodes-command-result.png)

<span data-ttu-id="6844a-137">**그림 4-20**.</span><span class="sxs-lookup"><span data-stu-id="6844a-137">**Figure 4-20**.</span></span> <span data-ttu-id="6844a-138">`kubectl get nodes` 명령 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="6844a-138">`kubectl get nodes` command result.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6844a-139">[이전](orchestrate-high-scalability-availability.md)
>[다음](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="6844a-139">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
