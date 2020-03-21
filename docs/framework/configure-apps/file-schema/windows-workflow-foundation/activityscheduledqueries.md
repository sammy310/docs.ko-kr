---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 763754b95a7f39c7f35e05df28589b69352168e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152426"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="1dad1-101">\<활동일정쿼리></span><span class="sxs-lookup"><span data-stu-id="1dad1-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="1dad1-102">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1dad1-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="1dad1-103">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1dad1-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="1dad1-104">프로필 쿼리 추적에 대한 자세한 내용은 [프로필 추적을](../../../windows-workflow-foundation/tracking-profiles.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1dad1-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1dad1-105">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1dad1-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1dad1-106">&nbsp;&nbsp;[**\<시스템. 서비스 모델>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1dad1-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1dad1-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="1dad1-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="1dad1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적프로필>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="1dad1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="1dad1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<워크플로>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1dad1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="1dad1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<활동일정 쿼리>**</span><span class="sxs-lookup"><span data-stu-id="1dad1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dad1-111">구문</span><span class="sxs-lookup"><span data-stu-id="1dad1-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dad1-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1dad1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1dad1-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1dad1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dad1-114">특성</span><span class="sxs-lookup"><span data-stu-id="1dad1-114">Attributes</span></span>  
 <span data-ttu-id="1dad1-115">없음</span><span class="sxs-lookup"><span data-stu-id="1dad1-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1dad1-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1dad1-116">Child Elements</span></span>  
  
|<span data-ttu-id="1dad1-117">요소</span><span class="sxs-lookup"><span data-stu-id="1dad1-117">Element</span></span>|<span data-ttu-id="1dad1-118">Description</span><span class="sxs-lookup"><span data-stu-id="1dad1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dad1-119">\<활동일정쿼리></span><span class="sxs-lookup"><span data-stu-id="1dad1-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="1dad1-120">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="1dad1-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1dad1-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1dad1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1dad1-122">요소</span><span class="sxs-lookup"><span data-stu-id="1dad1-122">Element</span></span>|<span data-ttu-id="1dad1-123">Description</span><span class="sxs-lookup"><span data-stu-id="1dad1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dad1-124">\<워크플로></span><span class="sxs-lookup"><span data-stu-id="1dad1-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="1dad1-125">**activityDefinitionId** 속성으로 식별 된 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1dad1-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1dad1-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1dad1-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1dad1-127">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="1dad1-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1dad1-128">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="1dad1-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
