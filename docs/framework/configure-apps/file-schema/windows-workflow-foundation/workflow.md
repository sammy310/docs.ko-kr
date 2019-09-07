---
title: <workflow>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: 5205f9ab89297c0e55c3e5e0c03b9e3fef36963a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397577"
---
# <a name="workflow"></a><span data-ttu-id="467f2-101">\<workflow></span><span class="sxs-lookup"><span data-stu-id="467f2-101">\<workflow></span></span>
<span data-ttu-id="467f2-102"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-102">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="467f2-103">워크플로 추적 및 해당 구성에 대 한 자세한 내용은 [워크플로 추적 및](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) 추적 및 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="467f2-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="467f2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="467f2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="467f2-105">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="467f2-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="467f2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="467f2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="467f2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="467f2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="467f2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<워크플로 >**</span><span class="sxs-lookup"><span data-stu-id="467f2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflow>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="467f2-109">구문</span><span class="sxs-lookup"><span data-stu-id="467f2-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String" 
             profileName="String" 
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String" 
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String" 
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String" 
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String" 
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="467f2-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="467f2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="467f2-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="467f2-112">특성</span><span class="sxs-lookup"><span data-stu-id="467f2-112">Attributes</span></span>  
  
|<span data-ttu-id="467f2-113">특성</span><span class="sxs-lookup"><span data-stu-id="467f2-113">Attribute</span></span>|<span data-ttu-id="467f2-114">Description</span><span class="sxs-lookup"><span data-stu-id="467f2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="467f2-115">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="467f2-115">activityDefinitionId</span></span>|<span data-ttu-id="467f2-116">추적되는 워크플로의 활동 정의 ID를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-116">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="467f2-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="467f2-117">Child Elements</span></span>  
  
|<span data-ttu-id="467f2-118">요소</span><span class="sxs-lookup"><span data-stu-id="467f2-118">Element</span></span>|<span data-ttu-id="467f2-119">Description</span><span class="sxs-lookup"><span data-stu-id="467f2-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="467f2-120">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="467f2-120">\<activityScheduledQueries></span></span>](activityscheduledqueries.md)|<span data-ttu-id="467f2-121">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-121">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="467f2-122">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-122">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="467f2-123">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="467f2-123">\<activityStateQueries></span></span>](activitystatequeries.md)|<span data-ttu-id="467f2-124">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-124">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="467f2-125">예를 들어, 워크플로 인스턴스 내에서 "전자 메일 보내기" 작업이 완료 될 때마다 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-125">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="467f2-126">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-126">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="467f2-127">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-127">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="467f2-128">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="467f2-128">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="467f2-129">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-129">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="467f2-130">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-130">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="467f2-131">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="467f2-131">\<cancelRequestedQueries></span></span>](cancelrequestedqueries.md)|<span data-ttu-id="467f2-132">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-132">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="467f2-133">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-133">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="467f2-134">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="467f2-134">\<customTrackingQueries></span></span>](customtrackingqueries.md)|<span data-ttu-id="467f2-135">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-135">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="467f2-136">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-136">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="467f2-137">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="467f2-137">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="467f2-138">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-138">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="467f2-139">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-139">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="467f2-140">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-140">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="467f2-141">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-141">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="467f2-142">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="467f2-142">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="467f2-143">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 구성 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-143">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="467f2-144">부모 요소</span><span class="sxs-lookup"><span data-stu-id="467f2-144">Parent Elements</span></span>  
  
|<span data-ttu-id="467f2-145">요소</span><span class="sxs-lookup"><span data-stu-id="467f2-145">Element</span></span>|<span data-ttu-id="467f2-146">설명</span><span class="sxs-lookup"><span data-stu-id="467f2-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="467f2-147">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="467f2-147">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="467f2-148">추적 참가자에서 워크플로 추적 레코드에 대 한 구독을 만들기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-148">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="467f2-149">추적 프로필에는 추적 참가자가 런타임에 워크플로 인스턴스 상태가 변경될 때 발생하는 워크플로 이벤트를 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-149">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="467f2-150">추적 프로필 섹션 내에서 정의되는 쿼리는 구독에서 반환되는 이벤트의 종류를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-150">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="467f2-151">설명</span><span class="sxs-lookup"><span data-stu-id="467f2-151">Remarks</span></span>  
 <span data-ttu-id="467f2-152">추적 프로필에는 추적 참가자가 런타임에 특정 워크플로 인스턴스 상태가 변경될 때 발생하는 워크플로 이벤트를 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-152">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="467f2-153">추적되는 워크플로 인스턴스는 이 구성 요소에 의해 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-153">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="467f2-154">모니터링 요구 사항에 따라 워크플로에서 상위 수준의 상태 변경 내용 중 작은 부분만 구독하는 매우 개괄적인 프로필을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-154">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="467f2-155">이와 반대로 이후에 세부 실행 흐름을 다시 작성할 수 있을 정도로 상세한 결과 이벤트를 포함하는 매우 구체적인 프로필을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-155">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="467f2-156">추적 프로필은 특정 추적 레코드에 대한 워크플로 런타임을 쿼리할 수 있는 추적 레코드에 대한 선언적 구독으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-156">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="467f2-157">다양 한 추적 레코드 클래스를 구독할 수 있는 몇 가지 쿼리 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-157">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="467f2-158">쿼리의 전체 목록은이 항목의 자식 요소 목록 및 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="467f2-158">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="467f2-159">다음 예제에서는 추적 참가자가 `Started` 및 `Completed` 워크플로 이벤트를 구독할 수 있도록 하는 구성 파일의 추적 프로필을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="467f2-159">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>    
    <trackingProfile name="Sample Tracking Profile">  
      <workflow activityDefinitionId="*">  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
            <states>  
              <state name="Started"/>  
              <state name="Completed"/>  
            </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="467f2-160">참고자료</span><span class="sxs-lookup"><span data-stu-id="467f2-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="467f2-161">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="467f2-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="467f2-162">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="467f2-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
