---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: aa6ee435c66303b5089b459ecc4ed3023297636d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398966"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="107cf-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="107cf-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="107cf-102">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="107cf-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="107cf-103">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="107cf-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="107cf-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="107cf-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="107cf-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="107cf-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="107cf-106">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="107cf-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="107cf-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="107cf-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="107cf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="107cf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="107cf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="107cf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="107cf-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityScheduledQueries >** ](activityscheduledqueries.md)</span><span class="sxs-lookup"><span data-stu-id="107cf-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)</span></span>\
<span data-ttu-id="107cf-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y >**</span><span class="sxs-lookup"><span data-stu-id="107cf-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="107cf-112">구문</span><span class="sxs-lookup"><span data-stu-id="107cf-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="107cf-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="107cf-113">Attributes and Elements</span></span>  
 <span data-ttu-id="107cf-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="107cf-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="107cf-115">특성</span><span class="sxs-lookup"><span data-stu-id="107cf-115">Attributes</span></span>  
  
|<span data-ttu-id="107cf-116">특성</span><span class="sxs-lookup"><span data-stu-id="107cf-116">Attribute</span></span>|<span data-ttu-id="107cf-117">Description</span><span class="sxs-lookup"><span data-stu-id="107cf-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="107cf-118">activityName</span><span class="sxs-lookup"><span data-stu-id="107cf-118">activityName</span></span>|<span data-ttu-id="107cf-119">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="107cf-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="107cf-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="107cf-120">childActivityName</span></span>|<span data-ttu-id="107cf-121">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="107cf-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="107cf-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="107cf-122">Child Elements</span></span>  
 <span data-ttu-id="107cf-123">없음</span><span class="sxs-lookup"><span data-stu-id="107cf-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="107cf-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="107cf-124">Parent Elements</span></span>  
  
|<span data-ttu-id="107cf-125">요소</span><span class="sxs-lookup"><span data-stu-id="107cf-125">Element</span></span>|<span data-ttu-id="107cf-126">설명</span><span class="sxs-lookup"><span data-stu-id="107cf-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="107cf-127">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="107cf-127">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="107cf-128">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="107cf-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="107cf-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="107cf-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="107cf-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="107cf-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="107cf-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="107cf-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
