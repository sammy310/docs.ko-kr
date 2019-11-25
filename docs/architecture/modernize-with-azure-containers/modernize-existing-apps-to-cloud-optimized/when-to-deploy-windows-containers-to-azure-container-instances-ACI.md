---
title: Azure Container Instances(ACI)에 Windows 컨테이너를 배포하는 경우
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | Azure Container Instances(ACI)에 Windows 컨테이너를 배포하는 경우
ms.date: 04/29/2018
ms.openlocfilehash: 3b6ae1ced9c4e01f5ab400e2575947a396064ebd
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577936"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="107d6-103">Azure Container Instances(ACI)에 Windows 컨테이너를 배포하는 경우</span><span class="sxs-lookup"><span data-stu-id="107d6-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="107d6-104">Azure Container Instances 기본 가치 제안은 사용자가 컨테이너를 바로 배포할 수 있으며 해당 환경을 유지 관리할 필요가 없고, 기본 운영 체제 또는 VM을 업그레이드/패치할 필요가 없고, 모든 것이 투명하고, 컨테이너를 즉시 사용 가능한 환경에 배포할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="107d6-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="107d6-105">ACI를 사용하려는 이유 및 시나리오는 컨테이너에서 Azure VM을 사용하는 경우의 주요 시나리오와 비슷합니다. 기본적으로 Azure Container Instances 사용에 대한 주요 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="107d6-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="107d6-106">**개발/테스트 시나리오**</span><span class="sxs-lookup"><span data-stu-id="107d6-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="107d6-107">**작업 자동화**</span><span class="sxs-lookup"><span data-stu-id="107d6-107">**Task automation**</span></span>
- <span data-ttu-id="107d6-108">**CI/CD 에이전트**</span><span class="sxs-lookup"><span data-stu-id="107d6-108">**CI/CD agents**</span></span>
- <span data-ttu-id="107d6-109">**소규모/대규모 일괄 처리**</span><span class="sxs-lookup"><span data-stu-id="107d6-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="107d6-110">**간단한 웹앱**</span><span class="sxs-lookup"><span data-stu-id="107d6-110">**Simple web apps**</span></span>

<span data-ttu-id="107d6-111">간단한 웹앱 시나리오는 ACI에 타당한 시나리오이지만 ACI에서는 컨테이너 이미지당 하나의 컨테이너 인스턴스만 가능하므로 고가용성이 확보되지 않고 확장성만 제한된다는 것을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="107d6-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="107d6-112">그러나 ACI가 단일 컨테이너 인스턴스만 제공하기 때문에 인프라로 고려되는 경우에도 Windows Server를 사용하는 일반 Azure VM에 비해 큰 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107d6-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="107d6-113">ACI를 사용하면 컨테이너를 자체 유지 관리 환경에 배포하고 해당 컨테이너에 대해서만 비용을 지불하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="107d6-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="107d6-114">VM을 유지 관리/업데이트/패치하지 않아도 되므로 컨테이너와 함께 VM을 사용할 수 있는 대부분의 시나리오에서 훨씬 더 나은 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="107d6-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="107d6-115">ACI 사용은 간단합니다. VM 환경은 만들 필요가 없이 컨테이너만 배포하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="107d6-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="107d6-116">Azure Container Instances(ACI)의 주요 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="107d6-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="107d6-117">서버를 관리하지 않고 컨테이너를 실행</span><span class="sxs-lookup"><span data-stu-id="107d6-117">Run containers without managing servers</span></span>
- <span data-ttu-id="107d6-118">주문형 컨테이너를 사용하여 민첩성을 향상</span><span class="sxs-lookup"><span data-stu-id="107d6-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="107d6-119">단일 명령을 사용하여 뛰어난 단순성과 속도로 클라우드에 컨테이너를 배포</span><span class="sxs-lookup"><span data-stu-id="107d6-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="107d6-120">하이퍼바이저 격리를 사용하여 애플리케이션을 보호</span><span class="sxs-lookup"><span data-stu-id="107d6-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="107d6-121">간단히 말해서, ACI를 사용하면 가상 머신을 관리하거나 새로운 도구를 배울 필요 없이 신속하게 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107d6-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="107d6-122">단지 클라우드에서 실행되는 컨테이너의 애플리케이션일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="107d6-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="107d6-123">[이전](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [다음](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="107d6-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span></span>
