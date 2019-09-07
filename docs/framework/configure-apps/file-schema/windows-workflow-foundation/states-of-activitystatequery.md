---
title: <activityStateQuery>의 <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: 0c8bf5b793684d3e6076114ce9eda7ffe1ef7a81
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398626"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="02210-102">\<activitystatequery \<>의 상태 ></span><span class="sxs-lookup"><span data-stu-id="02210-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="02210-103">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="02210-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="02210-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="02210-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="02210-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="02210-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="02210-106">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="02210-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="02210-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="02210-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="02210-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="02210-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="02210-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="02210-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="02210-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQueries >** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="02210-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="02210-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQuery >** ](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="02210-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="02210-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<상태 >**</span><span class="sxs-lookup"><span data-stu-id="02210-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02210-113">구문</span><span class="sxs-lookup"><span data-stu-id="02210-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02210-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="02210-114">Attributes and Elements</span></span>  
 <span data-ttu-id="02210-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="02210-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02210-116">특성</span><span class="sxs-lookup"><span data-stu-id="02210-116">Attributes</span></span>  
 <span data-ttu-id="02210-117">없음</span><span class="sxs-lookup"><span data-stu-id="02210-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="02210-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="02210-118">Child Elements</span></span>  
  
|<span data-ttu-id="02210-119">요소</span><span class="sxs-lookup"><span data-stu-id="02210-119">Element</span></span>|<span data-ttu-id="02210-120">Description</span><span class="sxs-lookup"><span data-stu-id="02210-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02210-121">\<state></span><span class="sxs-lookup"><span data-stu-id="02210-121">\<state></span></span>](state-of-states.md)|<span data-ttu-id="02210-122">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="02210-122">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02210-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="02210-123">Parent Elements</span></span>  
  
|<span data-ttu-id="02210-124">요소</span><span class="sxs-lookup"><span data-stu-id="02210-124">Element</span></span>|<span data-ttu-id="02210-125">설명</span><span class="sxs-lookup"><span data-stu-id="02210-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02210-126">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="02210-126">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="02210-127">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="02210-127">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="02210-128">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="02210-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02210-129">설명</span><span class="sxs-lookup"><span data-stu-id="02210-129">Remarks</span></span>  
 <span data-ttu-id="02210-130">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="02210-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="02210-131">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="02210-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="02210-132">인수 >, [ \<](arguments.md) [ 상태\<>](states.md) 및 [ 상태>요소를사용하\<](states.md) 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02210-132">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="02210-133">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="02210-133">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="02210-134">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로 [ \<activitystatequery >](activitystatequery.md)를 사용 하 여 추적 프로필 내에서 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="02210-134">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02210-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="02210-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="02210-136">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="02210-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="02210-137">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="02210-137">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
