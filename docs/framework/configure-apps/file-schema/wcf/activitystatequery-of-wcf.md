---
title: <activityStateQuery>WCF의
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 49c507424e813067e1dad9b08167d9661acef36f
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991223"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="82282-102">\<WCF의 activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="82282-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="82282-103">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82282-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="82282-104">예를 들어, 워크플로 인스턴스 내에서 "전자 메일 보내기" 작업이 완료 될 때마다 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82282-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="82282-105">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="82282-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="82282-106">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="82282-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="82282-107">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82282-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="82282-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="82282-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="82282-109">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="82282-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="82282-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="82282-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="82282-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="82282-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="82282-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="82282-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="82282-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="82282-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="82282-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQueries >** ](activitystatequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="82282-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries-of-wcf.md)</span></span>\
<span data-ttu-id="82282-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityStateQuery >**</span><span class="sxs-lookup"><span data-stu-id="82282-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82282-116">구문</span><span class="sxs-lookup"><span data-stu-id="82282-116">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82282-117">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="82282-117">Attributes and elements</span></span>  

<span data-ttu-id="82282-118">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82282-118">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82282-119">특성</span><span class="sxs-lookup"><span data-stu-id="82282-119">Attributes</span></span>  
  
|<span data-ttu-id="82282-120">특성</span><span class="sxs-lookup"><span data-stu-id="82282-120">Attribute</span></span>|<span data-ttu-id="82282-121">설명</span><span class="sxs-lookup"><span data-stu-id="82282-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82282-122">activityName</span><span class="sxs-lookup"><span data-stu-id="82282-122">activityName</span></span>|<span data-ttu-id="82282-123"><xref:System.Activities.Tracking.ActivityStateRecord> 인스턴스를 필터링할 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="82282-123">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82282-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="82282-124">Child elements</span></span>  
  
|<span data-ttu-id="82282-125">요소</span><span class="sxs-lookup"><span data-stu-id="82282-125">Element</span></span>|<span data-ttu-id="82282-126">Description</span><span class="sxs-lookup"><span data-stu-id="82282-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82282-127">\<arguments></span><span class="sxs-lookup"><span data-stu-id="82282-127">\<arguments></span></span>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="82282-128">이 활동 쿼리와 연결되는 인수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="82282-128">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="82282-129">\<states></span><span class="sxs-lookup"><span data-stu-id="82282-129">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="82282-130">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="82282-130">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="82282-131">\<states></span><span class="sxs-lookup"><span data-stu-id="82282-131">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="82282-132">이 활동 쿼리와 연결되는 변수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="82282-132">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82282-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="82282-133">Parent elements</span></span>  
  
|<span data-ttu-id="82282-134">요소</span><span class="sxs-lookup"><span data-stu-id="82282-134">Element</span></span>|<span data-ttu-id="82282-135">설명</span><span class="sxs-lookup"><span data-stu-id="82282-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82282-136">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="82282-136">\<faultPropagationQuery></span></span>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="82282-137">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82282-137">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="82282-138">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="82282-138">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82282-139">설명</span><span class="sxs-lookup"><span data-stu-id="82282-139">Remarks</span></span>

<span data-ttu-id="82282-140">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="82282-140">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="82282-141">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82282-141">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="82282-142">인수 >, [ \<](../windows-workflow-foundation/arguments.md) [ 상태\<>](../windows-workflow-foundation/states.md) 및 [ 상태>요소를사용하\<](../windows-workflow-foundation/states.md) 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82282-142">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="82282-143">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82282-143">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="82282-144">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로 [ \<activitystatequery >](../windows-workflow-foundation/activitystatequery.md)를 사용 하 여 추적 프로필 내에서 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="82282-144">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a><span data-ttu-id="82282-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="82282-145">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="82282-146">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="82282-146">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="82282-147">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="82282-147">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
