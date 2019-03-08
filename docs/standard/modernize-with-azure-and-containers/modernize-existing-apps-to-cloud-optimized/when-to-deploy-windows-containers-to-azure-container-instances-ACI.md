---
title: Windows 컨테이너를 Azure ACI (Container Instances)를 배포 하는 경우
description: Azure 클라우드 및 Windows 컨테이너를 사용 하 여 기존.NET 응용 프로그램 현대화 | Windows 컨테이너를 Azure ACI (Container Instances)를 배포 하는 경우
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 03ee7c8b65e1a92dcc7fd40b44e9ba081f571487
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674408"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="cad51-103">Windows 컨테이너를 Azure ACI (Container Instances)를 배포 하는 경우</span><span class="sxs-lookup"><span data-stu-id="cad51-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="cad51-104">Azure Container Instances에 컨테이너를 즉시 배포할 수 있습니다 하는 환경을 유지 관리할 필요가 없습니다 기본 가치는, 필요가 기본 운영 체제 또는 Vm에 투명 하는 모든 업그레이드/패치 및 배포 하기만 하면 됩니다. 즉시 사용 환경에 대 한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="cad51-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="cad51-105">이유와 ACI를 사용 하려는 경우 시나리오는 비슷합니다는 주요 시나리오는 기본적으로 컨테이너를 사용 하 여 Azure Vm을 사용 하는 경우, Azure Container Instances를 사용 하 여에 대 한 주요 시나리오는:</span><span class="sxs-lookup"><span data-stu-id="cad51-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="cad51-106">**개발/테스트 시나리오**</span><span class="sxs-lookup"><span data-stu-id="cad51-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="cad51-107">**작업 자동화**</span><span class="sxs-lookup"><span data-stu-id="cad51-107">**Task automation**</span></span>
- <span data-ttu-id="cad51-108">**CI/CD 에이전트**</span><span class="sxs-lookup"><span data-stu-id="cad51-108">**CI/CD agents**</span></span>
- <span data-ttu-id="cad51-109">**일괄 처리 작은/크기 조정**</span><span class="sxs-lookup"><span data-stu-id="cad51-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="cad51-110">**간단한 웹 앱**</span><span class="sxs-lookup"><span data-stu-id="cad51-110">**Simple web apps**</span></span>

<span data-ttu-id="cad51-111">간단한 웹 앱 시나리오를 ACI에 대 한 상당한 시나리오 이지만 ACI에서 컨테이너 이미지 당 하나의 컨테이너 인스턴스를 하나만 사용할 수 있습니다, 되므로 고가용성 없습니다 하는 확장성 제한 된 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad51-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="cad51-112">그러나 ACI 바로 단일 컨테이너 인스턴스를 제공 하기 때문에 인프라 것으로 간주 됩니다, 경우에 Windows Server를 사용 하 여 일반 Azure Vm에 비해 굉장한 이점이입니다.</span><span class="sxs-lookup"><span data-stu-id="cad51-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="cad51-113">ACI를 사용 하 여 자체 관리 되는 환경에 컨테이너를 배포 하기만 하면 됩니다 하 고 해당 컨테이너에 대 한 비용만 지불 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad51-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="cad51-114">위치를 사용 하 고 Vm 컨테이너를 사용 하 여 대부분의 시나리오에 대 한 훨씬 더 나은 플랫폼 이므로 유지 관리/업데이트/패치 Vm 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cad51-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="cad51-115">ACI를 사용 하는 간단 하 고, 컨테이너를 배포 하기만 하면 됩니다 하 고, 컨테이너를 배포한 VM 환경을 만들려면 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad51-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="cad51-116">Azure 컨테이너 인스턴스 (ACI)의 가장 큰 장점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cad51-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="cad51-117">서버를 관리할 필요 없이 컨테이너 실행</span><span class="sxs-lookup"><span data-stu-id="cad51-117">Run containers without managing servers</span></span>
- <span data-ttu-id="cad51-118">주문형 컨테이너로 민첩성 증가</span><span class="sxs-lookup"><span data-stu-id="cad51-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="cad51-119">최고의 간단 함 및 속도 사용 하 여 클라우드에 컨테이너에 배포-단일 명령으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad51-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="cad51-120">하이퍼바이저 격리를 사용 하 여 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="cad51-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="cad51-121">즉, ACI를 사용 하 여 가상 컴퓨터를 관리 하거나 새로운 도구를 배울 필요 없이 빠르게 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad51-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="cad51-122">응용 프로그램 일 뿐임 클라우드에서 실행 되는 컨테이너의 경우</span><span class="sxs-lookup"><span data-stu-id="cad51-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="cad51-123">[이전](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [다음](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="cad51-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
