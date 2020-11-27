---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 04c5e0f4fbf3b95485e5bf4aae53aa2e4912d893
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294497"
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="9d291-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="9d291-102">225 - TraceCorrelationKeys</span></span>

## <a name="properties"></a><span data-ttu-id="9d291-103">속성</span><span class="sxs-lookup"><span data-stu-id="9d291-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9d291-104">ID</span><span class="sxs-lookup"><span data-stu-id="9d291-104">ID</span></span>|<span data-ttu-id="9d291-105">225</span><span class="sxs-lookup"><span data-stu-id="9d291-105">225</span></span>|  
|<span data-ttu-id="9d291-106">키워드</span><span class="sxs-lookup"><span data-stu-id="9d291-106">Keywords</span></span>|<span data-ttu-id="9d291-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9d291-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9d291-108">Level</span><span class="sxs-lookup"><span data-stu-id="9d291-108">Level</span></span>|<span data-ttu-id="9d291-109">정보</span><span class="sxs-lookup"><span data-stu-id="9d291-109">Information</span></span>|  
|<span data-ttu-id="9d291-110">채널</span><span class="sxs-lookup"><span data-stu-id="9d291-110">Channel</span></span>|<span data-ttu-id="9d291-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="9d291-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9d291-112">Description</span><span class="sxs-lookup"><span data-stu-id="9d291-112">Description</span></span>  

 <span data-ttu-id="9d291-113">이 이벤트는 워크플로 서비스에 내용 기반 상관 관계가 사용될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="9d291-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="9d291-114">여기에는 메시지를 인스턴스에 연결하기 위해 적용되는 상관 관계 키가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d291-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9d291-115">메시지</span><span class="sxs-lookup"><span data-stu-id="9d291-115">Message</span></span>  

 <span data-ttu-id="9d291-116">'%3' 부모 범위에서 '%2' 값을 사용하여 '%1' 상관 관계 키를 계산했습니다.</span><span class="sxs-lookup"><span data-stu-id="9d291-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9d291-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="9d291-117">Details</span></span>  
  
|<span data-ttu-id="9d291-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="9d291-118">Data Item Name</span></span>|<span data-ttu-id="9d291-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="9d291-119">Data Item Type</span></span>|<span data-ttu-id="9d291-120">Description</span><span class="sxs-lookup"><span data-stu-id="9d291-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9d291-121">Instance Key</span><span class="sxs-lookup"><span data-stu-id="9d291-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="9d291-122">상관 관계 값에서 생성된 키입니다.</span><span class="sxs-lookup"><span data-stu-id="9d291-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="9d291-123">값</span><span class="sxs-lookup"><span data-stu-id="9d291-123">Values</span></span>|`xs:string`|<span data-ttu-id="9d291-124">상관 관계 인스턴스 키를 컴퓨팅하는 데 사용된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d291-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="9d291-125">Parent Scope</span><span class="sxs-lookup"><span data-stu-id="9d291-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="9d291-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="9d291-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="9d291-127">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="9d291-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9d291-128">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d291-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9d291-129">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="9d291-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9d291-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9d291-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9d291-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9d291-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
