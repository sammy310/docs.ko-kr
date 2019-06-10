---
title: 컨테이너 기반 응용 프로그램용 Azure 계산 플랫폼 선택
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | 컨테이너 기반 응용 프로그램용 Azure 계산 플랫폼 선택
ms.date: 05/04/2018
ms.openlocfilehash: d91cd279402dc24beb5f766c06cb85ac8d74f482
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758817"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="39160-103">컨테이너 기반 응용 프로그램용 Azure 계산 플랫폼 선택</span><span class="sxs-lookup"><span data-stu-id="39160-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="39160-104">앞선 절에서 Azure는 여러 가지를 선택할 수 있는 개방형 클라우드라는 것을 알 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="39160-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="39160-105">요구 사항에 맞는 적합한 선택은 가능하더라도 컨테이너화된 응용 프로그램에 어떤 제품이나 기술을 사용해야 할 것인지 의문이 생길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39160-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="39160-106">*기본적인* 권장 사항으로, 이 설명서에서 권장하는 주요 기준은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="39160-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="39160-107">**단일 모놀리식 앱:** Azure App Service를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39160-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="39160-108">**N 계층 앱:** 단일 또는 몇 백 엔드 서비스에 있는 경우 App Service 또는 Azure Kubernetes Service (AKS) 같은 오 케 스트레이 터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39160-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="39160-109">**Linux 마이크로 서비스:** AKS/Kubernetes를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39160-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
- <span data-ttu-id="39160-110">**Windows 마이크로 서비스:** 컨테이너용 Azure Web Apps 선택</span><span class="sxs-lookup"><span data-stu-id="39160-110">**Windows microservices:** Choose Azure Web Apps for Containers</span></span>
- <span data-ttu-id="39160-111">**서버리스 functions 및 이벤트 처리기:** Azure 함수를 선택합니다</span><span class="sxs-lookup"><span data-stu-id="39160-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="39160-112">**대규모 일괄 처리:** Azure Batch를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39160-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="39160-113">특정 응용 프로그램의 요구 사항과 특징에 따라 제품의 선택이 달라질 수 있으므로 이러한 권장 사항을 액면 그대로 받아들여서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="39160-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="39160-114">처음에는 비슷한 형식으로 보일지라도 모든 응용 프로그램이 동일하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39160-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="39160-115">응용 프로그램의 요구사항을 심층적으로 분석한 후에 선택한 제품이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39160-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="39160-116">그러나 출발점으로 특정 우선 순위에 따라 테스트하거나 측청할 수 있는 초기 지침을 갖는 것은 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39160-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="39160-117">다음 그림에서는 다른 종류의 앱 및 이상적인 Azure 호스팅 시나리오에 대 한 분석을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39160-117">In the next figure, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="39160-118">[이전](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [다음](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="39160-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
