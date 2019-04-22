---
title: 컨테이너 기반 응용 프로그램용 Azure 계산 플랫폼 선택
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | 컨테이너 기반 응용 프로그램용 Azure 계산 플랫폼 선택
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: f251aecfeaf2421a5cecf218577369963bc736fb
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58186106"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="e9bef-103">컨테이너 기반 응용 프로그램용 Azure 계산 플랫폼 선택</span><span class="sxs-lookup"><span data-stu-id="e9bef-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="e9bef-104">앞선 절에서 Azure는 여러 가지를 선택할 수 있는 개방형 클라우드라는 것을 알 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="e9bef-105">요구 사항에 맞는 적합한 선택은 가능하더라도 컨테이너화된 응용 프로그램에 어떤 제품이나 기술을 사용해야 할 것인지 의문이 생길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="e9bef-106">*기본적인* 권장 사항으로, 이 설명서에서 권장하는 주요 기준은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="e9bef-107">**단일 모놀리식 앱:** Azure App Service를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="e9bef-108">**N 계층 앱:** 단일 또는 몇 개의 백 엔드 서비스가 있다면 Azure Kubernetes Service(AKS)나 Service Fabric(SF), App Service와 같은 오케스트레이터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="e9bef-109">**Linux 마이크로 서비스:** AKS/Kubernetes를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
- <span data-ttu-id="e9bef-110">**Windows 마이크로 서비스:** Service Fabric을 선택합니다</span><span class="sxs-lookup"><span data-stu-id="e9bef-110">**Windows microservices:** Choose Service Fabric</span></span>
- <span data-ttu-id="e9bef-111">**서버리스 functions 및 이벤트 처리기:** Azure 함수를 선택합니다</span><span class="sxs-lookup"><span data-stu-id="e9bef-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="e9bef-112">**대규모 일괄 처리:** Azure Batch를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="e9bef-113">특정 응용 프로그램의 요구 사항과 특징에 따라 제품의 선택이 달라질 수 있으므로 이러한 권장 사항을 액면 그대로 받아들여서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="e9bef-114">처음에는 비슷한 형식으로 보일지라도 모든 응용 프로그램이 동일하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="e9bef-115">응용 프로그램의 요구사항을 심층적으로 분석한 후에 선택한 제품이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="e9bef-116">그러나 출발점으로 특정 우선 순위에 따라 테스트하거나 측청할 수 있는 초기 지침을 갖는 것은 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="e9bef-117">다음 그림에서는 자세한 의사 결정 테이블을 통해 보다 전반적인 분석을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="e9bef-118">일부 오케스트레이터가 Linux 컨테이너와 Windows 컨테이너에서 더 완성도가 있으므로 기본 OS(Windows와 Linux)가 결정 요인이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="e9bef-119">예를 들어, Linux 컨테이너는 Kubernetes(Azure의 AKS)에서는 매우 완성도가 높지만 서비스 Fabric에서는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="e9bef-120">반면 Windows Container는 Service Fabric(2017 년 5월에 릴리스됨)에서 완성도가 있지만 AKS에서는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="e9bef-121">그러나 앞으로 OS에 따른 완성도의 차이는 사라지게 되고, 다양한 플랫폼의 OS 완성도는 비슷해지며, 의사 결정은 응용 프로그램에서 필요로 하는 특정 기능이나 각 플랫폼의 생태계에 따른 환경 설정에 기반한 선호도에 따라 결정하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e9bef-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="e9bef-122">[이전](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [다음](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="e9bef-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
