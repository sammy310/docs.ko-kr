---
description: '자세한 정보: 57398-MaxInstancesExceeded'
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: 104c466cb2e0ee8156e2b268caf5e757353dfb09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720230"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="41034-103">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="41034-103">57398 - MaxInstancesExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="41034-104">속성</span><span class="sxs-lookup"><span data-stu-id="41034-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41034-105">ID</span><span class="sxs-lookup"><span data-stu-id="41034-105">ID</span></span>|<span data-ttu-id="41034-106">57398</span><span class="sxs-lookup"><span data-stu-id="41034-106">57398</span></span>|  
|<span data-ttu-id="41034-107">키워드</span><span class="sxs-lookup"><span data-stu-id="41034-107">Keywords</span></span>|<span data-ttu-id="41034-108">WFServices</span><span class="sxs-lookup"><span data-stu-id="41034-108">WFServices</span></span>|  
|<span data-ttu-id="41034-109">Level</span><span class="sxs-lookup"><span data-stu-id="41034-109">Level</span></span>|<span data-ttu-id="41034-110">경고</span><span class="sxs-lookup"><span data-stu-id="41034-110">Warning</span></span>|  
|<span data-ttu-id="41034-111">채널</span><span class="sxs-lookup"><span data-stu-id="41034-111">Channel</span></span>|<span data-ttu-id="41034-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="41034-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="41034-113">설명</span><span class="sxs-lookup"><span data-stu-id="41034-113">Description</span></span>  

 <span data-ttu-id="41034-114">시스템이 스로틀 'MaxConcurrentInstances'에 대해 설정된 한도에 도달했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="41034-114">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="41034-115">메시지</span><span class="sxs-lookup"><span data-stu-id="41034-115">Message</span></span>  

 <span data-ttu-id="41034-116">시스템이 'MaxConcurrentInstances' 스로틀에 대해 설정된 한계에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="41034-116">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="41034-117">이 스로틀에 대한 제한은 %1(으)로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41034-117">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="41034-118">serviceThrottle 요소에서 'maxConcurrentInstances' 특성을 수정하거나 ServiceThrottlingBehavior 동작에서 'MaxConcurrentInstances' 속성을 수정하여 스로틀 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41034-118">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="41034-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="41034-119">Details</span></span>  
  
|<span data-ttu-id="41034-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="41034-120">Data Item Name</span></span>|<span data-ttu-id="41034-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="41034-121">Data Item Type</span></span>|<span data-ttu-id="41034-122">설명</span><span class="sxs-lookup"><span data-stu-id="41034-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="41034-123">Name</span><span class="sxs-lookup"><span data-stu-id="41034-123">Name</span></span>|<span data-ttu-id="41034-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="41034-124">xs:string</span></span>|<span data-ttu-id="41034-125">항목의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="41034-125">The name of the item.</span></span>|  
|<span data-ttu-id="41034-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="41034-126">AppDomain</span></span>|<span data-ttu-id="41034-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="41034-127">xs:string</span></span>|<span data-ttu-id="41034-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="41034-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
