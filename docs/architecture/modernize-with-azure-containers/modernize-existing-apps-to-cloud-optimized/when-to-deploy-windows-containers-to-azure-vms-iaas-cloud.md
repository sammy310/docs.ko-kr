---
title: Azure VM에 Windows 컨테이너를 배포해야 하는 경우(IaaS 클라우드)
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | Azure VM(IaaS 클라우드)에 Windows 컨테이너를 배포하는 경우
ms.date: 04/28/2018
ms.openlocfilehash: e9a2903662306b607977a7751018e24161ab80ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "69577906"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a><span data-ttu-id="9b5d5-103">Azure VM에 Windows 컨테이너를 배포해야 하는 경우(IaaS 클라우드)</span><span class="sxs-lookup"><span data-stu-id="9b5d5-103">When to deploy Windows Containers to Azure VMs (IaaS cloud)</span></span>

<span data-ttu-id="9b5d5-104">조직에서 Azure VM을 사용하는 경우 Windows 컨테이너도 사용하더라도 여전히 IaaS를 처리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b5d5-104">If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS.</span></span> <span data-ttu-id="9b5d5-105">즉, 부하 분산된 인프라에서 여러 VM에 배포하는 경우 확장성이 뛰어난 애플리케이션에 대한 인프라 작업, VM OS 패치 및 인프라 복잡성을 처리한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="9b5d5-105">That means that dealing with infrastructure operations, VM OS patches, and infrastructure complexity for highly scalable applications when you need to deploy to multiple VMs in a load balanced infrastructure.</span></span> <span data-ttu-id="9b5d5-106">Azure VM에서 Windows 컨테이너를 사용하는 주요 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5d5-106">The main scenarios for using Windows Containers in an Azure VM are:</span></span>

- <span data-ttu-id="9b5d5-107">**개발/테스트 환경**: 클라우드의 VM은 클라우드에서 개발하고 테스트하는 데 매우 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5d5-107">**Dev/test environment**: A VM in the cloud is perfect for development and testing in the cloud.</span></span> <span data-ttu-id="9b5d5-108">요구 사항에 따라 신속하게 환경을 만들거나 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5d5-108">You can rapidly create or stop the environment depending on your needs.</span></span>

- <span data-ttu-id="9b5d5-109">**중소 규모의 확장성 요구 사항**: 프로덕션 환경에 두 개의 VM만 필요할 수 있는 시나리오에서는 오케스트레이터 같은 고급 PaaS 환경으로 전환할 수 있을 때까지 소수의 VM을 관리하는 것이 경제적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5d5-109">**Small and medium scalability needs**: In scenarios where you might need just a couple of VMs for your production environment, managing a small number of VMs might be affordable until you can move to more advanced PaaS environments, like orchestrators.</span></span>

- <span data-ttu-id="9b5d5-110">**기존 배포 도구를 사용하는 프로덕션 환경**: VM 또는 운영 체제 미설치 서버(예: Puppet 또는 유사한 도구)에 대한 복잡 한 배포를 수행하기 위해 도구에 투자한 온-프레미스 환경에서 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5d5-110">**Production environment with existing deployment tools**: You might be moving from an on-premises environment in which you have invested in tools to make complex deployments to VMs or bare-metal servers (like Puppet or similar tools).</span></span> <span data-ttu-id="9b5d5-111">프로덕션 환경 배포 절차를 최소한으로 변경하여 클라우드로 이동하려면 이러한 도구를 계속 사용하여 Azure VM에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5d5-111">To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs.</span></span> <span data-ttu-id="9b5d5-112">그러나 배포 단위로 Windows 컨테이너를 사용하여 배포 환경을 개선하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5d5-112">However, you'll want to use Windows Containers as the unit of deployment to improve the deployment experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9b5d5-113">[이전](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[다음](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span><span class="sxs-lookup"><span data-stu-id="9b5d5-113">[Previous](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Next](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span></span>
