---
title: 컨테이너 기반 응용 프로그램에 대 한 Azure 계산 플랫폼 선택
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
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="2fd0b-103">컨테이너 기반 응용 프로그램에 대 한 Azure 계산 플랫폼 선택</span><span class="sxs-lookup"><span data-stu-id="2fd0b-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="2fd0b-104">앞선 절에서 Azure는 여러 가지를 선택할 수 있는 개방형 클라우드라는 것을 알 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="2fd0b-105">요구 사항에 맞는 적합한 선택은 가능하더라도 컨테이너화된 응용 프로그램에 어떤 제품이나 기술을 사용해야 할 것인지 의문이 생길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="2fd0b-106">*기본적인* 권장 사항으로, 이 설명서에서 권장하는 주요 기준은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="2fd0b-107">**단일 모놀리식 앱:** Azure App Service를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="2fd0b-108">**N 계층 앱:** 단일 또는 몇 백 엔드 서비스에 있는 경우 Azure Kubernetes Service (AKS), Service Fabric (SF) 또는 App Service와 같은 오 케 스트레이 터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="2fd0b-109">**Linux 마이크로 서비스:** AKS/Kubernetes를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
- <span data-ttu-id="2fd0b-110">**Windows 마이크로 서비스:** Service Fabric을 선택</span><span class="sxs-lookup"><span data-stu-id="2fd0b-110">**Windows microservices:** Choose Service Fabric</span></span>
- <span data-ttu-id="2fd0b-111">**서버 리스 functions 및 이벤트 처리기:** Azure 함수 선택</span><span class="sxs-lookup"><span data-stu-id="2fd0b-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="2fd0b-112">**대규모 일괄 처리:** Azure Batch를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="2fd0b-113">그러나이 권장 사항은 제품의 선택은 특정 응용 프로그램의 요구 사항 및 특징에 따라 달라 집니다으로 약간의 솔트를 사용 하 여 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="2fd0b-114">일부 응용 프로그램은 처음에 비슷한 형식이 계실 경우에 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="2fd0b-115">응용 프로그램의 요구를 심층적으로 분석 한 후 선택한 제품 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="2fd0b-116">그러나 시작 지점으로 개의 평가 시작 하는 데 수의 초기 지침 이며 특정 우선 순위에 따라 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="2fd0b-117">다음 그림에서는 자세한 의사 결정 테이블 하는 동안 더 전역을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="2fd0b-118">알림 방법 (Windows 및 OS 기본 일부 오 케 스트레이 터는 더 Linux 컨테이너에 대 한 완성 및 Windows 컨테이너에 대 한 기타 Linux)는 의사 결정 요소를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="2fd0b-119">예를 들어 Linux 컨테이너는 Service Fabric에서 더 새롭고 완성도 낮음 하지만 Kubernetes (AKS azure에서)에서 매우 완성도 높은입니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="2fd0b-120">반면에 Windows 컨테이너는 Service Fabric (2017 년 5 월에에서 릴리스됨)에 더 성숙 하 고 AKS에서 더 새롭고 완성도 낮음.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="2fd0b-121">그러나 OS 완성에서 이러한 차이 나중에 페이드 및 여러 플랫폼에는 비교할 수 있는 OS의 완성도 있고 결정 응용 프로그램에 필요할 수 또는 각 플랫폼의 에코 시스템에 따라 특정 기능을 기반으로 하는 기본 설정에 대 한 자세한 내용은 이었으며 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="2fd0b-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="2fd0b-122">[이전](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [다음](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="2fd0b-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
