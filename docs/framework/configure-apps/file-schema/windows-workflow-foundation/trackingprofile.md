---
title: <trackingProfile>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: 8985da7e1223ac117cf1b68227140634f9c85d3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151891"
---
# <a name="trackingprofile"></a><span data-ttu-id="9d80c-101">\<추적프로필></span><span class="sxs-lookup"><span data-stu-id="9d80c-101">\<trackingProfile></span></span>
<span data-ttu-id="9d80c-102">추적 참가자에서 워크플로 추적 레코드에 대한 구독을 만들기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-102">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="9d80c-103">추적 프로필에는 추적 참가자가 런타임에 워크플로 인스턴스 상태가 변경될 때 발생하는 워크플로 이벤트를 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-103">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="9d80c-104">추적 프로필 섹션 내에서 정의되는 쿼리는 구독에서 반환되는 이벤트의 종류를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-104">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="9d80c-105">워크플로 추적 및 구성에 대한 자세한 내용은 [워크플로 추적 및 추적](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) [및 추적 프로필을](../../../windows-workflow-foundation/tracking-profiles.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9d80c-105">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="9d80c-106">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d80c-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9d80c-107">&nbsp;&nbsp;[**\<시스템. 서비스 모델>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9d80c-107">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="9d80c-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="9d80c-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="9d80c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<추적프로필>**</span><span class="sxs-lookup"><span data-stu-id="9d80c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trackingProfile>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d80c-110">구문</span><span class="sxs-lookup"><span data-stu-id="9d80c-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d80c-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9d80c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9d80c-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d80c-113">특성</span><span class="sxs-lookup"><span data-stu-id="9d80c-113">Attributes</span></span>  
  
|<span data-ttu-id="9d80c-114">attribute</span><span class="sxs-lookup"><span data-stu-id="9d80c-114">Attribute</span></span>|<span data-ttu-id="9d80c-115">Description</span><span class="sxs-lookup"><span data-stu-id="9d80c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d80c-116">name</span><span class="sxs-lookup"><span data-stu-id="9d80c-116">name</span></span>|<span data-ttu-id="9d80c-117">추적 프로필의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d80c-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9d80c-118">Child Elements</span></span>  
  
|<span data-ttu-id="9d80c-119">요소</span><span class="sxs-lookup"><span data-stu-id="9d80c-119">Element</span></span>|<span data-ttu-id="9d80c-120">Description</span><span class="sxs-lookup"><span data-stu-id="9d80c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d80c-121">\<참가자들은></span><span class="sxs-lookup"><span data-stu-id="9d80c-121">\<participants></span></span>](participants.md)|<span data-ttu-id="9d80c-122"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-122">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9d80c-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9d80c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9d80c-124">요소</span><span class="sxs-lookup"><span data-stu-id="9d80c-124">Element</span></span>|<span data-ttu-id="9d80c-125">Description</span><span class="sxs-lookup"><span data-stu-id="9d80c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d80c-126">\<추적></span><span class="sxs-lookup"><span data-stu-id="9d80c-126">\<tracking></span></span>](tracking.md)|<span data-ttu-id="9d80c-127">워크플로 서비스에 대한 추적 설정을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d80c-128">설명</span><span class="sxs-lookup"><span data-stu-id="9d80c-128">Remarks</span></span>  
 <span data-ttu-id="9d80c-129">추적 프로필에는 추적 참가자가 런타임에 워크플로 인스턴스 상태가 변경될 때 발생하는 워크플로 이벤트를 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="9d80c-130">모니터링 요구 사항에 따라 워크플로에서 상위 수준의 상태 변경 내용 중 작은 부분만 구독하는 매우 개괄적인 프로필을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="9d80c-131">이와 반대로 이후에 세부 실행 흐름을 다시 작성할 수 있을 정도로 상세한 결과 이벤트를 포함하는 매우 구체적인 프로필을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="9d80c-132">추적 프로필은 특정 추적 레코드에 대한 워크플로 런타임을 쿼리할 수 있는 추적 레코드에 대한 선언적 구독으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="9d80c-133">다양한 개체 클래스를 구독할 수 있는 몇 <xref:System.Activities.Tracking.TrackingRecord> 가지 쿼리 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="9d80c-134">전체 쿼리 목록은 [ \<참가자>](participants.md) 및 [프로필 추적을](../../../windows-workflow-foundation/tracking-profiles.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9d80c-134">For a complete list of queries, see [\<participants>](participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="9d80c-135">다음 예제에서는 추적 참가자가 `Started` 및 `Completed` 워크플로 이벤트를 구독할 수 있도록 하는 구성 파일의 추적 프로필을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d80c-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9d80c-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d80c-136">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="9d80c-137">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="9d80c-137">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9d80c-138">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="9d80c-138">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
