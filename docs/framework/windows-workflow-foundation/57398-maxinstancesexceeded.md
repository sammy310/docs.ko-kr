---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: d644c25ec2dee06eea4a5fb66c30792bb650f252
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945966"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="8ab4c-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="8ab4c-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="8ab4c-103">속성</span><span class="sxs-lookup"><span data-stu-id="8ab4c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ab4c-104">ID</span><span class="sxs-lookup"><span data-stu-id="8ab4c-104">ID</span></span>|<span data-ttu-id="8ab4c-105">57398</span><span class="sxs-lookup"><span data-stu-id="8ab4c-105">57398</span></span>|  
|<span data-ttu-id="8ab4c-106">키워드</span><span class="sxs-lookup"><span data-stu-id="8ab4c-106">Keywords</span></span>|<span data-ttu-id="8ab4c-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="8ab4c-107">WFServices</span></span>|  
|<span data-ttu-id="8ab4c-108">수준</span><span class="sxs-lookup"><span data-stu-id="8ab4c-108">Level</span></span>|<span data-ttu-id="8ab4c-109">경고</span><span class="sxs-lookup"><span data-stu-id="8ab4c-109">Warning</span></span>|  
|<span data-ttu-id="8ab4c-110">채널</span><span class="sxs-lookup"><span data-stu-id="8ab4c-110">Channel</span></span>|<span data-ttu-id="8ab4c-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="8ab4c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8ab4c-112">설명</span><span class="sxs-lookup"><span data-stu-id="8ab4c-112">Description</span></span>  
 <span data-ttu-id="8ab4c-113">시스템이 스로틀 'MaxConcurrentInstances'에 대해 설정된 한도에 도달했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ab4c-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8ab4c-114">메시지</span><span class="sxs-lookup"><span data-stu-id="8ab4c-114">Message</span></span>  
 <span data-ttu-id="8ab4c-115">시스템이 'MaxConcurrentInstances' 스로틀에 대해 설정된 한계에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab4c-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="8ab4c-116">이 스로틀에 대한 제한은 %1(으)로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab4c-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="8ab4c-117">serviceThrottle 요소에서 'maxConcurrentInstances' 특성을 수정하거나 ServiceThrottlingBehavior 동작에서 'MaxConcurrentInstances' 속성을 수정하여 스로틀 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab4c-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8ab4c-118">설명</span><span class="sxs-lookup"><span data-stu-id="8ab4c-118">Details</span></span>  
  
|<span data-ttu-id="8ab4c-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="8ab4c-119">Data Item Name</span></span>|<span data-ttu-id="8ab4c-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="8ab4c-120">Data Item Type</span></span>|<span data-ttu-id="8ab4c-121">설명</span><span class="sxs-lookup"><span data-stu-id="8ab4c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8ab4c-122">이름</span><span class="sxs-lookup"><span data-stu-id="8ab4c-122">Name</span></span>|<span data-ttu-id="8ab4c-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="8ab4c-123">xs:string</span></span>|<span data-ttu-id="8ab4c-124">항목의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab4c-124">The name of the item.</span></span>|  
|<span data-ttu-id="8ab4c-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8ab4c-125">AppDomain</span></span>|<span data-ttu-id="8ab4c-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="8ab4c-126">xs:string</span></span>|<span data-ttu-id="8ab4c-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab4c-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
