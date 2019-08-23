---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 89de9ef10449fbae78a8c5b558101a2cf6477b07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945531"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="d9e25-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="d9e25-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="d9e25-102">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9e25-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="d9e25-103">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e25-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="d9e25-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9e25-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d9e25-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d9e25-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d9e25-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d9e25-106">\<tracking></span></span>  
<span data-ttu-id="d9e25-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d9e25-107">\<trackingProfile></span></span>  
<span data-ttu-id="d9e25-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d9e25-108">\<workflow></span></span>  
<span data-ttu-id="d9e25-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="d9e25-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e25-110">구문</span><span class="sxs-lookup"><span data-stu-id="d9e25-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9e25-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d9e25-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d9e25-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e25-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9e25-113">특성</span><span class="sxs-lookup"><span data-stu-id="d9e25-113">Attributes</span></span>  
 <span data-ttu-id="d9e25-114">없음</span><span class="sxs-lookup"><span data-stu-id="d9e25-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d9e25-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d9e25-115">Child Elements</span></span>  
  
|<span data-ttu-id="d9e25-116">요소</span><span class="sxs-lookup"><span data-stu-id="d9e25-116">Element</span></span>|<span data-ttu-id="d9e25-117">설명</span><span class="sxs-lookup"><span data-stu-id="d9e25-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9e25-118">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="d9e25-118">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="d9e25-119">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="d9e25-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9e25-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d9e25-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d9e25-121">요소</span><span class="sxs-lookup"><span data-stu-id="d9e25-121">Element</span></span>|<span data-ttu-id="d9e25-122">Description</span><span class="sxs-lookup"><span data-stu-id="d9e25-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9e25-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d9e25-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="d9e25-124">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d9e25-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9e25-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="d9e25-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d9e25-126">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="d9e25-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d9e25-127">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d9e25-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
