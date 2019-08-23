---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: dc04405204be7c5484d47b4a3767f846b11abf9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945496"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="78208-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="78208-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="78208-102">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78208-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="78208-103">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="78208-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="78208-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78208-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="78208-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="78208-105">\<system.serviceModel></span></span>  
<span data-ttu-id="78208-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="78208-106">\<tracking></span></span>  
<span data-ttu-id="78208-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="78208-107">\<trackingProfile></span></span>  
<span data-ttu-id="78208-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="78208-108">\<workflow></span></span>  
<span data-ttu-id="78208-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="78208-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="78208-110">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="78208-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78208-111">구문</span><span class="sxs-lookup"><span data-stu-id="78208-111">Syntax</span></span>  
  
```xml 
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78208-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="78208-112">Attributes and Elements</span></span>  
 <span data-ttu-id="78208-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="78208-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78208-114">특성</span><span class="sxs-lookup"><span data-stu-id="78208-114">Attributes</span></span>  
  
|<span data-ttu-id="78208-115">특성</span><span class="sxs-lookup"><span data-stu-id="78208-115">Attribute</span></span>|<span data-ttu-id="78208-116">설명</span><span class="sxs-lookup"><span data-stu-id="78208-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78208-117">activityName</span><span class="sxs-lookup"><span data-stu-id="78208-117">activityName</span></span>|<span data-ttu-id="78208-118">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="78208-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="78208-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="78208-119">childActivityName</span></span>|<span data-ttu-id="78208-120">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="78208-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78208-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="78208-121">Child Elements</span></span>  
 <span data-ttu-id="78208-122">없음</span><span class="sxs-lookup"><span data-stu-id="78208-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78208-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="78208-123">Parent Elements</span></span>  
  
|<span data-ttu-id="78208-124">요소</span><span class="sxs-lookup"><span data-stu-id="78208-124">Element</span></span>|<span data-ttu-id="78208-125">Description</span><span class="sxs-lookup"><span data-stu-id="78208-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78208-126">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="78208-126">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="78208-127">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="78208-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78208-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="78208-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="78208-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="78208-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="78208-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="78208-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
