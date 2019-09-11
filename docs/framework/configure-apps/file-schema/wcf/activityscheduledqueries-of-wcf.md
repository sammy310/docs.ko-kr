---
title: <activityScheduledQueries>WCF의
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: c2281a9027aabfc5255ef7b09176f60d1725b522
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850501"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="acfe5-102">\<WCF의 activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="acfe5-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="acfe5-103">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="acfe5-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="acfe5-104">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="acfe5-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="acfe5-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="acfe5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="acfe5-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="acfe5-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="acfe5-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="acfe5-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="acfe5-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="acfe5-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="acfe5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="acfe5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="acfe5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="acfe5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="acfe5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="acfe5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="acfe5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityScheduledQueries >**</span><span class="sxs-lookup"><span data-stu-id="acfe5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acfe5-113">구문</span><span class="sxs-lookup"><span data-stu-id="acfe5-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acfe5-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="acfe5-114">Attributes and elements</span></span>  

<span data-ttu-id="acfe5-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="acfe5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acfe5-116">특성</span><span class="sxs-lookup"><span data-stu-id="acfe5-116">Attributes</span></span>  

<span data-ttu-id="acfe5-117">없음</span><span class="sxs-lookup"><span data-stu-id="acfe5-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="acfe5-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="acfe5-118">Child elements</span></span>  
  
|<span data-ttu-id="acfe5-119">요소</span><span class="sxs-lookup"><span data-stu-id="acfe5-119">Element</span></span>|<span data-ttu-id="acfe5-120">Description</span><span class="sxs-lookup"><span data-stu-id="acfe5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acfe5-121">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="acfe5-121">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="acfe5-122">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="acfe5-122">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="acfe5-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="acfe5-123">Parent elements</span></span>  
  
|<span data-ttu-id="acfe5-124">요소</span><span class="sxs-lookup"><span data-stu-id="acfe5-124">Element</span></span>|<span data-ttu-id="acfe5-125">Description</span><span class="sxs-lookup"><span data-stu-id="acfe5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acfe5-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="acfe5-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="acfe5-127">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="acfe5-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acfe5-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="acfe5-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="acfe5-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="acfe5-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="acfe5-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="acfe5-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
