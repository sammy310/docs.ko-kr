---
title: <activityStateQuery>WCF의
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 233bd3a2fa161222977902cc1053f964e8171173
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850478"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="33fc9-102">\<WCF의 activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="33fc9-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="33fc9-103">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="33fc9-104">예를 들어, 워크플로 인스턴스 내에서 "전자 메일 보내기" 작업이 완료 될 때마다 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="33fc9-105">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="33fc9-106">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="33fc9-107">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="33fc9-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="33fc9-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33fc9-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33fc9-109">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="33fc9-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="33fc9-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="33fc9-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="33fc9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="33fc9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="33fc9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="33fc9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="33fc9-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="33fc9-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="33fc9-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQueries >** ](activitystatequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="33fc9-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries-of-wcf.md)</span></span>\
<span data-ttu-id="33fc9-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityStateQuery >**</span><span class="sxs-lookup"><span data-stu-id="33fc9-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33fc9-116">구문</span><span class="sxs-lookup"><span data-stu-id="33fc9-116">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33fc9-117">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="33fc9-117">Attributes and elements</span></span>  

<span data-ttu-id="33fc9-118">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-118">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33fc9-119">특성</span><span class="sxs-lookup"><span data-stu-id="33fc9-119">Attributes</span></span>  
  
|<span data-ttu-id="33fc9-120">특성</span><span class="sxs-lookup"><span data-stu-id="33fc9-120">Attribute</span></span>|<span data-ttu-id="33fc9-121">Description</span><span class="sxs-lookup"><span data-stu-id="33fc9-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33fc9-122">activityName</span><span class="sxs-lookup"><span data-stu-id="33fc9-122">activityName</span></span>|<span data-ttu-id="33fc9-123"><xref:System.Activities.Tracking.ActivityStateRecord> 인스턴스를 필터링할 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-123">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33fc9-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="33fc9-124">Child elements</span></span>  
  
|<span data-ttu-id="33fc9-125">요소</span><span class="sxs-lookup"><span data-stu-id="33fc9-125">Element</span></span>|<span data-ttu-id="33fc9-126">설명</span><span class="sxs-lookup"><span data-stu-id="33fc9-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33fc9-127">\<arguments></span><span class="sxs-lookup"><span data-stu-id="33fc9-127">\<arguments></span></span>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="33fc9-128">이 활동 쿼리와 연결되는 인수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-128">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="33fc9-129">\<states></span><span class="sxs-lookup"><span data-stu-id="33fc9-129">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="33fc9-130">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-130">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="33fc9-131">\<states></span><span class="sxs-lookup"><span data-stu-id="33fc9-131">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="33fc9-132">이 활동 쿼리와 연결되는 변수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-132">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33fc9-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="33fc9-133">Parent elements</span></span>  
  
|<span data-ttu-id="33fc9-134">요소</span><span class="sxs-lookup"><span data-stu-id="33fc9-134">Element</span></span>|<span data-ttu-id="33fc9-135">Description</span><span class="sxs-lookup"><span data-stu-id="33fc9-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33fc9-136">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="33fc9-136">\<faultPropagationQuery></span></span>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="33fc9-137">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-137">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="33fc9-138">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-138">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33fc9-139">설명</span><span class="sxs-lookup"><span data-stu-id="33fc9-139">Remarks</span></span>

<span data-ttu-id="33fc9-140">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-140">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="33fc9-141">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-141">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="33fc9-142">인수 >, [ \<](../windows-workflow-foundation/arguments.md) [ 상태\<>](../windows-workflow-foundation/states.md) 및 [ 상태>요소를사용하\<](../windows-workflow-foundation/states.md) 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다. 다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수 및 인수를 추출 하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-142">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="33fc9-143">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로 [ \<activitystatequery >](../windows-workflow-foundation/activitystatequery.md)를 사용 하 여 추적 프로필 내에서 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="33fc9-143">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="33fc9-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="33fc9-144">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="33fc9-145">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="33fc9-145">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="33fc9-146">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="33fc9-146">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
