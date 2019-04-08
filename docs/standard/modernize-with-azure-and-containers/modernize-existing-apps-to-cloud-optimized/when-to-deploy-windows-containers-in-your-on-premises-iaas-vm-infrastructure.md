---
title: 온-프레미스 IaaS VM 인프라에 Windows 컨테이너를 배포하는 경우
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | 온-프레미스 IaaS VM 인프라에 Windows 컨테이너를 배포하는 경우
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: ed9b64927372837c3ecf9377261150d4ee29d323
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149252"
---
# <a name="when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure"></a><span data-ttu-id="abbbd-103">온-프레미스 IaaS VM 인프라에 Windows 컨테이너를 배포하는 경우</span><span class="sxs-lookup"><span data-stu-id="abbbd-103">When to deploy Windows Containers in your on-premises IaaS VM infrastructure</span></span>

-   <span data-ttu-id="abbbd-104">조직이 클라우드로 이동할 준비가 되지 않을 수 있습니다 또는 비즈니스 이유가 대 한 클라우드로 이동 하는 일을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbbd-104">Your organization might not be ready to move to the cloud, or it might not be able to move to the cloud for a business reason.</span></span> <span data-ttu-id="abbbd-105">그러나 사용자 고유의 데이터 센터에서 Windows 컨테이너를 사용 하는 이점은 접속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbbd-105">But, you can still get the benefits of using Windows Containers in your own datacenters.</span></span>

-   <span data-ttu-id="abbbd-106">온-프레미스에 사용되는 다른 아티팩트가 있을 수 있으며 클라우드로 옮기면 속도가 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbbd-106">You might have other artifacts that are being used on-premises, and which might slow you down when you try to move to the cloud.</span></span> <span data-ttu-id="abbbd-107">예를 들면 온-프레미스 Windows Server Active Directory나 그 밖에 온-프레미스 자산의 보안이나 인증 종속성이 이에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="abbbd-107">For example, security or authentication dependencies with on-premises Windows Server Active Directory, or any other on-premises asset.</span></span>

-   <span data-ttu-id="abbbd-108">지금 Windows 컨테이너 사용을 시작한다면 나중에 보다 유리한 위치에서 클라우드로 단계적 마이그레이션을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbbd-108">If you start using Windows Containers today, you can make a phased migration to the cloud tomorrow from a much better position.</span></span> <span data-ttu-id="abbbd-109">Windows 컨테이너는 제약이 없는 모든 클라우드로의 배포 단위가 되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbbd-109">Windows Containers is becoming a unit of deployment for any cloud, with no lock-in.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="abbbd-110">[이전](when-not-to-deploy-to-windows-containers.md)
>[다음](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="abbbd-110">[Previous](when-not-to-deploy-to-windows-containers.md)
[Next](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)</span></span>