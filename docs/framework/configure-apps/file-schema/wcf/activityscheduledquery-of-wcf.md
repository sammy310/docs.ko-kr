---
title: <activityScheduledQuery> WCF의
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 5087d56092296f8c68b719ec0945993adeb3de0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704721"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="8cfc7-102">\<activityScheduledQuery > WCF의</span><span class="sxs-lookup"><span data-stu-id="8cfc7-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="8cfc7-103">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8cfc7-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="8cfc7-104">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8cfc7-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="8cfc7-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8cfc7-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8cfc7-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8cfc7-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8cfc7-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="8cfc7-107">\<tracking></span></span>  
<span data-ttu-id="8cfc7-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="8cfc7-108">\<profiles></span></span>  
<span data-ttu-id="8cfc7-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8cfc7-109">\<trackingProfile></span></span>  
<span data-ttu-id="8cfc7-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8cfc7-110">\<workflow></span></span>  
<span data-ttu-id="8cfc7-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="8cfc7-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="8cfc7-112">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="8cfc7-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cfc7-113">구문</span><span class="sxs-lookup"><span data-stu-id="8cfc7-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8cfc7-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8cfc7-114">Attributes and elements</span></span>  

<span data-ttu-id="8cfc7-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8cfc7-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8cfc7-116">특성</span><span class="sxs-lookup"><span data-stu-id="8cfc7-116">Attributes</span></span>  
  
|<span data-ttu-id="8cfc7-117">특성</span><span class="sxs-lookup"><span data-stu-id="8cfc7-117">Attribute</span></span>|<span data-ttu-id="8cfc7-118">설명</span><span class="sxs-lookup"><span data-stu-id="8cfc7-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="8cfc7-119">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8cfc7-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="8cfc7-120">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8cfc7-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8cfc7-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8cfc7-121">Child elements</span></span>

<span data-ttu-id="8cfc7-122">없음</span><span class="sxs-lookup"><span data-stu-id="8cfc7-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="8cfc7-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8cfc7-123">Parent elements</span></span>  
  
|<span data-ttu-id="8cfc7-124">요소</span><span class="sxs-lookup"><span data-stu-id="8cfc7-124">Element</span></span>|<span data-ttu-id="8cfc7-125">설명</span><span class="sxs-lookup"><span data-stu-id="8cfc7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8cfc7-126">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="8cfc7-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="8cfc7-127">부모 활동에 의해 실행이 예약 된 활동을 추적 하는 데 사용 되는 쿼리의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8cfc7-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8cfc7-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="8cfc7-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="8cfc7-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="8cfc7-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8cfc7-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="8cfc7-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
