---
title: Azure VM(IaaS 클라우드)에 Windows 컨테이너를 배포하는 경우
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | Azure VM(IaaS 클라우드)에 Windows 컨테이너를 배포하는 경우
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 8bff4297f99b6549b80604860985568445bbdc0b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625653"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a><span data-ttu-id="6c890-103">Azure VM(IaaS 클라우드)에 Windows 컨테이너를 배포하는 경우</span><span class="sxs-lookup"><span data-stu-id="6c890-103">When to deploy Windows Containers to Azure VMs (IaaS cloud)</span></span>

<span data-ttu-id="6c890-104">조직에서 Azure VM을 사용한다면, Windows 컨테이너 또한 사용한다 해도 IaaS 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6c890-104">If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS.</span></span> <span data-ttu-id="6c890-105">이는 부하 분산 인프라에 있는 여러 VM에 배포가 필요한 경우, 확장성이 뛰어난 응용 프로그램에 대한 인프라 운영과 VM OS 패치, 인프라 복잡성을 처리한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="6c890-105">That means that dealing with infrastructure operations, VM OS patches, and infrastructure complexity for highly scalable applications when you need to deploy to multiple VMs in a load balanced infrastructure.</span></span> <span data-ttu-id="6c890-106">Azure VM에서 Windows 컨테이너를 사용하는 주요 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c890-106">The main scenarios for using Windows Containers in an Azure VM are:</span></span>

- <span data-ttu-id="6c890-107">**개발/테스트 환경**: 클라우드의 VM은 클라우드에서의 개발과 테스트에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="6c890-107">**Dev/test environment**: A VM in the cloud is perfect for development and testing in the cloud.</span></span> <span data-ttu-id="6c890-108">필요에 따라 환경을 신속하게 만들고 중지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c890-108">You can rapidly create or stop the environment depending on your needs.</span></span>

- <span data-ttu-id="6c890-109">**소규모 및 중간 규모의 확장성 요구**: 프로덕션 환경에 몇 개의 VM만 필요한 시나리오에서는 오케스트레이터와 같은 고급 PaaS 환경으로 옮기기 전까지 적은 수의 VM을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c890-109">**Small and medium scalability needs**: In scenarios where you might need just a couple of VMs for your production environment, managing a small number of VMs might be affordable until you can move to more advanced PaaS environments, like orchestrators.</span></span>

- <span data-ttu-id="6c890-110">**기존 배포 도구의 프로덕션 환경**: 복잡한 배포를 위해 도구에 투자한 온-프레미스 환경에서 VM이나 베어 메탈 서버(예 : 퍼핏 또는 유사한 도구)로 넘어갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c890-110">**Production environment with existing deployment tools**: You might be moving from an on-premises environment in which you have invested in tools to make complex deployments to VMs or bare-metal servers (like Puppet or similar tools).</span></span> <span data-ttu-id="6c890-111">프로덕션 환경의 배포 절차의 변경을 최소화하면서 클라우드로 넘어가려면 해당 도구를 계속 사용하여 Azure VM에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c890-111">To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs.</span></span> <span data-ttu-id="6c890-112">하지만 Windows 컨테이너를 배포 단위로 사용하여 배포 환경을 개선하고자 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6c890-112">However, you'll want to use Windows Containers as the unit of deployment to improve the deployment experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6c890-113">[이전](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[다음](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span><span class="sxs-lookup"><span data-stu-id="6c890-113">[Previous](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Next](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span></span>