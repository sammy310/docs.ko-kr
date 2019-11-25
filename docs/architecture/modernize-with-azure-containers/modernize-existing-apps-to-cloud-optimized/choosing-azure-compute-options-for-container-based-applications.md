---
title: 컨테이너 기반 애플리케이션의 Azure 컴퓨팅 플랫폼 선택
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 컨테이너 기반 애플리케이션용 Azure 컴퓨팅 플랫폼 선택
ms.date: 05/04/2018
ms.openlocfilehash: 079c9c5ca02b6dc75214d63cb59afdead03d3190
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2019
ms.locfileid: "73737007"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="a67b8-103">컨테이너 기반 애플리케이션의 Azure 컴퓨팅 플랫폼 선택</span><span class="sxs-lookup"><span data-stu-id="a67b8-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="a67b8-104">이전 섹션을 읽으면서 알았듯이 Azure는 여러 선택 항목을 제공하는 개방 클라우드입니다.</span><span class="sxs-lookup"><span data-stu-id="a67b8-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="a67b8-105">사용자 요구에 가장 적합한 기능을 사용할 수 있지만, 컨테이너화된 애플리케이션에 어떤 제품/기술을 사용해야 하는지 결정하는 문제도 대두됩니다.</span><span class="sxs-lookup"><span data-stu-id="a67b8-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="a67b8-106">*기본* 권장 사항으로 이 지침에서 권장하는 기본 기준은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a67b8-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="a67b8-107">**단일 모놀리식 앱:** Azure App Service 선택</span><span class="sxs-lookup"><span data-stu-id="a67b8-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="a67b8-108">**N 계층 앱:** 하나 이상의 백 엔드 서비스가 있는 경우 Azure Kubernetes Service(AKS) 또는 App Service와 같은 오케스트레이터를 선택</span><span class="sxs-lookup"><span data-stu-id="a67b8-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS) or App Service if you have a single or a few back-end services</span></span>
- <span data-ttu-id="a67b8-109">**마이크로 서비스:** AKS 또는 Azure Web Apps for Containers를 선택</span><span class="sxs-lookup"><span data-stu-id="a67b8-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="a67b8-110">**서버리스 함수 및 이벤트 처리기:** Azure Functions를 선택</span><span class="sxs-lookup"><span data-stu-id="a67b8-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="a67b8-111">**대규모 일괄 처리:** Azure Batch를 선택</span><span class="sxs-lookup"><span data-stu-id="a67b8-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="a67b8-112">그러나 제품 선택은 특정 애플리케이션의 요구 사항 및 특성에 따라 달라지므로 이러한 권장 사항은 참고만 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67b8-112">However, this recommendation should be taken with a pinch of salt, as the product's selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="a67b8-113">처음에는 비슷한 유형으로 보일 수 있어도 애플리케이션은 다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a67b8-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="a67b8-114">애플리케이션의 요구 사항을 심층적으로 분석한 후에는 제품 선택이 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67b8-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="a67b8-115">하지만 시작점으로, 특정 우선 순위에 따라 평가 및 테스트를 시작할 수 있는 초기 지침을 마련하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a67b8-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="a67b8-116">그림 1에서 다양한 종류의 앱과 이상적인 Azure 호스팅 시나리오에 대한 분석을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67b8-116">In Figure 1, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![다양한 앱에 가장 적합한 Azure 호스팅 시나리오의 표](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> <span data-ttu-id="a67b8-118">[이전](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [다음](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="a67b8-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
