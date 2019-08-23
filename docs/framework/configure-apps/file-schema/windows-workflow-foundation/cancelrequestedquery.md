---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: d9c3f91edb41bd034bcd978b075d62f74b6e308d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945877"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="571f6-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="571f6-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="571f6-102">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="571f6-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="571f6-103">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="571f6-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="571f6-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="571f6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="571f6-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="571f6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="571f6-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="571f6-106">\<tracking></span></span>  
<span data-ttu-id="571f6-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="571f6-107">\<trackingProfile></span></span>  
<span data-ttu-id="571f6-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="571f6-108">\<workflow></span></span>  
<span data-ttu-id="571f6-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="571f6-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="571f6-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="571f6-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="571f6-111">구문</span><span class="sxs-lookup"><span data-stu-id="571f6-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="571f6-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="571f6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="571f6-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="571f6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="571f6-114">특성</span><span class="sxs-lookup"><span data-stu-id="571f6-114">Attributes</span></span>  
  
|<span data-ttu-id="571f6-115">특성</span><span class="sxs-lookup"><span data-stu-id="571f6-115">Attribute</span></span>|<span data-ttu-id="571f6-116">Description</span><span class="sxs-lookup"><span data-stu-id="571f6-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="571f6-117">activityName</span><span class="sxs-lookup"><span data-stu-id="571f6-117">activityName</span></span>|<span data-ttu-id="571f6-118">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="571f6-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="571f6-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="571f6-119">childActivityName</span></span>|<span data-ttu-id="571f6-120">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="571f6-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="571f6-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="571f6-121">Child Elements</span></span>  
 <span data-ttu-id="571f6-122">없음</span><span class="sxs-lookup"><span data-stu-id="571f6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="571f6-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="571f6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="571f6-124">요소</span><span class="sxs-lookup"><span data-stu-id="571f6-124">Element</span></span>|<span data-ttu-id="571f6-125">설명</span><span class="sxs-lookup"><span data-stu-id="571f6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="571f6-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="571f6-126">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="571f6-127">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="571f6-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="571f6-128">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="571f6-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="571f6-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="571f6-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="571f6-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="571f6-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="571f6-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="571f6-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
