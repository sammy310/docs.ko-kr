---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 7217fb886cc96e1ad19f96e2c6542277cfc7979e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790431"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="f2685-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="f2685-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="f2685-102">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2685-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="f2685-103">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f2685-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="f2685-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f2685-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f2685-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f2685-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f2685-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="f2685-106">\<tracking></span></span>  
<span data-ttu-id="f2685-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f2685-107">\<trackingProfile></span></span>  
<span data-ttu-id="f2685-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="f2685-108">\<workflow></span></span>  
<span data-ttu-id="f2685-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="f2685-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2685-110">구문</span><span class="sxs-lookup"><span data-stu-id="f2685-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2685-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f2685-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f2685-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f2685-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2685-113">특성</span><span class="sxs-lookup"><span data-stu-id="f2685-113">Attributes</span></span>  
 <span data-ttu-id="f2685-114">없음</span><span class="sxs-lookup"><span data-stu-id="f2685-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f2685-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f2685-115">Child Elements</span></span>  
  
|<span data-ttu-id="f2685-116">요소</span><span class="sxs-lookup"><span data-stu-id="f2685-116">Element</span></span>|<span data-ttu-id="f2685-117">설명</span><span class="sxs-lookup"><span data-stu-id="f2685-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2685-118">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="f2685-118">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="f2685-119">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="f2685-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f2685-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f2685-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f2685-121">요소</span><span class="sxs-lookup"><span data-stu-id="f2685-121">Element</span></span>|<span data-ttu-id="f2685-122">설명</span><span class="sxs-lookup"><span data-stu-id="f2685-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2685-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="f2685-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="f2685-124">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소를 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f2685-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2685-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="f2685-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f2685-126">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="f2685-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f2685-127">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="f2685-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
