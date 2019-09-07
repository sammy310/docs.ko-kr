---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: a43242e2f22c48a57c11f6f03657d7d3de27ff48
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398984"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="ffc0c-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="ffc0c-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="ffc0c-102">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0c-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="ffc0c-103">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0c-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="ffc0c-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ffc0c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ffc0c-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ffc0c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ffc0c-106">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ffc0c-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="ffc0c-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="ffc0c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="ffc0c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="ffc0c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="ffc0c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ffc0c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="ffc0c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityScheduledQueries >**</span><span class="sxs-lookup"><span data-stu-id="ffc0c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffc0c-111">구문</span><span class="sxs-lookup"><span data-stu-id="ffc0c-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffc0c-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ffc0c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ffc0c-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffc0c-114">특성</span><span class="sxs-lookup"><span data-stu-id="ffc0c-114">Attributes</span></span>  
 <span data-ttu-id="ffc0c-115">없음</span><span class="sxs-lookup"><span data-stu-id="ffc0c-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ffc0c-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ffc0c-116">Child Elements</span></span>  
  
|<span data-ttu-id="ffc0c-117">요소</span><span class="sxs-lookup"><span data-stu-id="ffc0c-117">Element</span></span>|<span data-ttu-id="ffc0c-118">설명</span><span class="sxs-lookup"><span data-stu-id="ffc0c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ffc0c-119">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="ffc0c-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="ffc0c-120">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0c-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ffc0c-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ffc0c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ffc0c-122">요소</span><span class="sxs-lookup"><span data-stu-id="ffc0c-122">Element</span></span>|<span data-ttu-id="ffc0c-123">Description</span><span class="sxs-lookup"><span data-stu-id="ffc0c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ffc0c-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ffc0c-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="ffc0c-125">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0c-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ffc0c-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="ffc0c-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ffc0c-127">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="ffc0c-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ffc0c-128">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="ffc0c-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
