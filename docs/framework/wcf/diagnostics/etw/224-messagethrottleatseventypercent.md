---
description: '자세한 정보: 224-MessageThrottleAtSeventyPercent'
title: 224 - MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: 14c08371c5db7e6f7deb0a5851a1d24dfc94475e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794275"
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="d3acd-103">224 - MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="d3acd-103">224 - MessageThrottleAtSeventyPercent</span></span>

## <a name="properties"></a><span data-ttu-id="d3acd-104">속성</span><span class="sxs-lookup"><span data-stu-id="d3acd-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d3acd-105">ID</span><span class="sxs-lookup"><span data-stu-id="d3acd-105">ID</span></span>|<span data-ttu-id="d3acd-106">224</span><span class="sxs-lookup"><span data-stu-id="d3acd-106">224</span></span>|  
|<span data-ttu-id="d3acd-107">키워드</span><span class="sxs-lookup"><span data-stu-id="d3acd-107">Keywords</span></span>|<span data-ttu-id="d3acd-108">EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d3acd-108">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d3acd-109">Level</span><span class="sxs-lookup"><span data-stu-id="d3acd-109">Level</span></span>|<span data-ttu-id="d3acd-110">경고</span><span class="sxs-lookup"><span data-stu-id="d3acd-110">Warning</span></span>|  
|<span data-ttu-id="d3acd-111">채널</span><span class="sxs-lookup"><span data-stu-id="d3acd-111">Channel</span></span>|<span data-ttu-id="d3acd-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="d3acd-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d3acd-113">설명</span><span class="sxs-lookup"><span data-stu-id="d3acd-113">Description</span></span>  

 <span data-ttu-id="d3acd-114">기본 서비스 스로틀 중 하나가 초과되면 `MessageThrottleExceeded` 이벤트가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d3acd-114">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="d3acd-115">작업 스파이크가 느려지고 스로틀의 현재 값이 현재 한계의 70%이면 이 이벤트가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d3acd-115">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="d3acd-116">이 이벤트는 작업이 느려지므로 한 번만 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d3acd-116">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="d3acd-117">예를 들어 현재 값이 70% 표시 지점을 넘나들면(예: 70,69,70,71,70,69) 처음으로 70%가 될 때만 이 이벤트가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d3acd-117">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="d3acd-118">이 이벤트가 내보내진 후에 현재 값이 스로틀 한계를 다시 초과하면 `MessageThrottleExceeded` 이벤트가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d3acd-118">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d3acd-119">메시지</span><span class="sxs-lookup"><span data-stu-id="d3acd-119">Message</span></span>  

 <span data-ttu-id="d3acd-120">'%2'의 스로틀 제한 '%1'이(가) 70퍼센트입니다.</span><span class="sxs-lookup"><span data-stu-id="d3acd-120">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d3acd-121">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d3acd-121">Details</span></span>  
  
|<span data-ttu-id="d3acd-122">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d3acd-122">Data Item Name</span></span>|<span data-ttu-id="d3acd-123">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d3acd-123">Data Item Type</span></span>|<span data-ttu-id="d3acd-124">설명</span><span class="sxs-lookup"><span data-stu-id="d3acd-124">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d3acd-125">Throttle Name</span><span class="sxs-lookup"><span data-stu-id="d3acd-125">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="d3acd-126">초과한 스로틀의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d3acd-126">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="d3acd-127">`MaxConcurrentCalls`, `MaxConcurrentInstances` 또는 `MaxConcurrentSessions` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d3acd-127">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="d3acd-128">제한</span><span class="sxs-lookup"><span data-stu-id="d3acd-128">Limit</span></span>|`xs:long`|<span data-ttu-id="d3acd-129">현재 구성된 스로틀 한계입니다.</span><span class="sxs-lookup"><span data-stu-id="d3acd-129">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="d3acd-130">HostReference</span><span class="sxs-lookup"><span data-stu-id="d3acd-130">HostReference</span></span>|`xs:string`|<span data-ttu-id="d3acd-131">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d3acd-131">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d3acd-132">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3acd-132">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d3acd-133">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="d3acd-133">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d3acd-134">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d3acd-134">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d3acd-135">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d3acd-135">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
