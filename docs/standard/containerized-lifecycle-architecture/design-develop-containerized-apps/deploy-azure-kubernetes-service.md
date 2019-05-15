---
title: 높은 확장성 및 가용성을 위한 마이크로 서비스 및 다중 컨테이너 애플리케이션 오케스트레이션
description: Azure Kubernetes Service를 사용 하 여 앱을 배포 하는 방법에 알아봅니다.
ms.date: 02/15/2019
ms.openlocfilehash: 88e76b4b0a3686f4227a6aee1b7fbd2bfe55fdcc
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644629"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="352a0-103">AKS(Azure Kubernetes Service)에 배포</span><span class="sxs-lookup"><span data-stu-id="352a0-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="352a0-104">원하는 클라이언트 운영 체제를 사용 하 여 AKS 상호 작용할 수 있습니다, 여기 살펴보겠습니다 Microsoft Windows 및 Windows, Ubuntu Linux의 포함 된 버전을 사용 하 여 수행 하는 방법을 Bash 명령을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-104">You can interact with AKS using your preferred client operating system, here we show how to do it with Microsoft Windows and an embedded version of Ubuntu Linux in Windows, using Bash commands.</span></span>

<span data-ttu-id="352a0-105">AKS를 사용 하기 전에 가지 필수 구성 요소가 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-105">Prerequisites to have before using AKS are:</span></span>

- <span data-ttu-id="352a0-106">Linux 또는 Mac 개발 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="352a0-106">Linux or Mac development machine</span></span>
- <span data-ttu-id="352a0-107">Windows 개발 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="352a0-107">Windows development machine</span></span>
  - <span data-ttu-id="352a0-108">Windows에서 사용 하도록 설정 하는 개발자 모드</span><span class="sxs-lookup"><span data-stu-id="352a0-108">Developer Mode enabled on Windows</span></span>
  - <span data-ttu-id="352a0-109">Linux 용 Windows 하위 시스템</span><span class="sxs-lookup"><span data-stu-id="352a0-109">Windows Subsystem for Linux</span></span>
- <span data-ttu-id="352a0-110">Azure CLI 설치 [Windows, Mac 또는 Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span><span class="sxs-lookup"><span data-stu-id="352a0-110">Azure-CLI installed on [Windows, Mac or Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span></span>

> [!NOTE]
> <span data-ttu-id="352a0-111">에 대 한 전체 정보를 찾으려면:</span><span class="sxs-lookup"><span data-stu-id="352a0-111">To find complete information about:</span></span>
>
> <span data-ttu-id="352a0-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span><span class="sxs-lookup"><span data-stu-id="352a0-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span></span>
>
> <span data-ttu-id="352a0-113">Linux 용 Windows 하위 시스템: <https://docs.microsoft.com/windows/wsl/about></span><span class="sxs-lookup"><span data-stu-id="352a0-113">Windows Subsystem for Linux: <https://docs.microsoft.com/windows/wsl/about></span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="352a0-114">Azure에서 AKS 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="352a0-114">Create the AKS environment in Azure</span></span>

<span data-ttu-id="352a0-115">AKS 환경을 만드는 방법은 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-115">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="352a0-116">Azure CLI 명령을 사용 하 여 또는 Azure portal을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-116">It can be done by using Azure-CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="352a0-117">여기 몇 가지 예제 클러스터를 만들고 결과 검토 하려면 Azure portal에서 Azure CLI를 사용 하 여 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-117">Here you can explore some examples using the Azure-CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="352a0-118">Kubectl 및 Docker 개발 컴퓨터에 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-118">You also need to have Kubectl and Docker in your development machine.</span></span>  

## <a name="create-the-aks-cluster"></a><span data-ttu-id="352a0-119">AKS 클러스터 만들기</span><span class="sxs-lookup"><span data-stu-id="352a0-119">Create the AKS cluster</span></span>

<span data-ttu-id="352a0-120">이 명령을 사용 하 여 AKS 클러스터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-120">Create the AKS cluster using this command:</span></span>

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

<span data-ttu-id="352a0-121">만들기 작업이 완료 되 면 Azure portal에서 만든 AKS를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-121">After the creation job finishes, you can see the AKS created in the Azure portal:</span></span>

<span data-ttu-id="352a0-122">리소스 그룹:</span><span class="sxs-lookup"><span data-stu-id="352a0-122">The resource group:</span></span>

![브라우저 보기 Azure AKS 리소스 그룹입니다.](media/aks-resource-group-view.png)

<span data-ttu-id="352a0-124">**그림 4-17**.</span><span class="sxs-lookup"><span data-stu-id="352a0-124">**Figure 4-17**.</span></span> <span data-ttu-id="352a0-125">Azure에서 AKS 리소스 그룹 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-125">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="352a0-126">AKS 클러스터의 경우:</span><span class="sxs-lookup"><span data-stu-id="352a0-126">The AKS cluster:</span></span>

![AKS 리소스 그룹의 브라우저 보기입니다.](media/aks-cluster-view.png)

<span data-ttu-id="352a0-128">**그림 4-18**.</span><span class="sxs-lookup"><span data-stu-id="352a0-128">**Figure 4-18**.</span></span> <span data-ttu-id="352a0-129">Azure에서 AKS 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-129">AKS view from Azure.</span></span>

<span data-ttu-id="352a0-130">사용 하 여 만든 노드를 볼 수도 있습니다 `Azure-CLI` 고 `Kubectl`입니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-130">You can also view the node created using `Azure-CLI` and `Kubectl`.</span></span>

<span data-ttu-id="352a0-131">먼저 자격 증명 가져오기:</span><span class="sxs-lookup"><span data-stu-id="352a0-131">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![위 명령의 출력을 콘솔: 병합 된 "/root/.kube/config에서 현재 컨텍스트로 MsSampleK8Cluster 합니다.](media/get-credentials-command-result.png)

<span data-ttu-id="352a0-133">**그림 4-19**.</span><span class="sxs-lookup"><span data-stu-id="352a0-133">**Figure 4-19**.</span></span> <span data-ttu-id="352a0-134">`aks get-credentials` 명령 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-134">`aks get-credentials` command result.</span></span>

<span data-ttu-id="352a0-135">그리고 Kubectl에서 노드를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-135">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![위 명령 출력을 콘솔: 노드 상태, 기간 (시간 실행) 및 버전을 사용 하 여 목록](media/kubectl-get-nodes-command-result.png)

<span data-ttu-id="352a0-137">**그림 4-20**.</span><span class="sxs-lookup"><span data-stu-id="352a0-137">**Figure 4-20**.</span></span> <span data-ttu-id="352a0-138">`kubectl get nodes` 명령 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="352a0-138">`kubectl get nodes` command result.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="352a0-139">[이전](orchestrate-high-scalability-availability.md)
>[다음](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="352a0-139">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
