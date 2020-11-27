---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: bd490aad24fba4550bc778799cd6f836dcfd466c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289180"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="f4dce-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="f4dce-102">57398 - MaxInstancesExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="f4dce-103">속성</span><span class="sxs-lookup"><span data-stu-id="f4dce-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4dce-104">ID</span><span class="sxs-lookup"><span data-stu-id="f4dce-104">ID</span></span>|<span data-ttu-id="f4dce-105">57398</span><span class="sxs-lookup"><span data-stu-id="f4dce-105">57398</span></span>|  
|<span data-ttu-id="f4dce-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f4dce-106">Keywords</span></span>|<span data-ttu-id="f4dce-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="f4dce-107">WFServices</span></span>|  
|<span data-ttu-id="f4dce-108">Level</span><span class="sxs-lookup"><span data-stu-id="f4dce-108">Level</span></span>|<span data-ttu-id="f4dce-109">경고</span><span class="sxs-lookup"><span data-stu-id="f4dce-109">Warning</span></span>|  
|<span data-ttu-id="f4dce-110">채널</span><span class="sxs-lookup"><span data-stu-id="f4dce-110">Channel</span></span>|<span data-ttu-id="f4dce-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="f4dce-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f4dce-112">Description</span><span class="sxs-lookup"><span data-stu-id="f4dce-112">Description</span></span>  

 <span data-ttu-id="f4dce-113">시스템이 스로틀 'MaxConcurrentInstances'에 대해 설정된 한도에 도달했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4dce-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f4dce-114">메시지</span><span class="sxs-lookup"><span data-stu-id="f4dce-114">Message</span></span>  

 <span data-ttu-id="f4dce-115">시스템이 'MaxConcurrentInstances' 스로틀에 대해 설정된 한계에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="f4dce-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="f4dce-116">이 스로틀에 대한 제한은 %1(으)로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f4dce-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="f4dce-117">serviceThrottle 요소에서 'maxConcurrentInstances' 특성을 수정하거나 ServiceThrottlingBehavior 동작에서 'MaxConcurrentInstances' 속성을 수정하여 스로틀 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4dce-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f4dce-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f4dce-118">Details</span></span>  
  
|<span data-ttu-id="f4dce-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f4dce-119">Data Item Name</span></span>|<span data-ttu-id="f4dce-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f4dce-120">Data Item Type</span></span>|<span data-ttu-id="f4dce-121">Description</span><span class="sxs-lookup"><span data-stu-id="f4dce-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f4dce-122">이름</span><span class="sxs-lookup"><span data-stu-id="f4dce-122">Name</span></span>|<span data-ttu-id="f4dce-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4dce-123">xs:string</span></span>|<span data-ttu-id="f4dce-124">항목의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f4dce-124">The name of the item.</span></span>|  
|<span data-ttu-id="f4dce-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f4dce-125">AppDomain</span></span>|<span data-ttu-id="f4dce-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4dce-126">xs:string</span></span>|<span data-ttu-id="f4dce-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f4dce-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
