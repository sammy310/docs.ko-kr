---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 560df771b44fc8ba8d192657677bf0496283b539
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945422"
---
# <a name="activitystatequery"></a><span data-ttu-id="f0e1b-101">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="f0e1b-101">\<activityStateQuery></span></span>
<span data-ttu-id="f0e1b-102">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-102">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="f0e1b-103">예를 들어, 워크플로 인스턴스 내에서 "전자 메일 보내기" 작업이 완료 될 때마다 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="f0e1b-104">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="f0e1b-105">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="f0e1b-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="f0e1b-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f0e1b-107">\<system.serviceModel></span></span>  
<span data-ttu-id="f0e1b-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="f0e1b-108">\<tracking></span></span>  
<span data-ttu-id="f0e1b-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f0e1b-109">\<trackingProfile></span></span>  
<span data-ttu-id="f0e1b-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="f0e1b-110">\<workflow></span></span>  
<span data-ttu-id="f0e1b-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="f0e1b-111">\<activityStateQueries></span></span>  
<span data-ttu-id="f0e1b-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="f0e1b-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0e1b-113">구문</span><span class="sxs-lookup"><span data-stu-id="f0e1b-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0e1b-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f0e1b-114">Attributes and Elements</span></span>  
 <span data-ttu-id="f0e1b-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0e1b-116">특성</span><span class="sxs-lookup"><span data-stu-id="f0e1b-116">Attributes</span></span>  
  
|<span data-ttu-id="f0e1b-117">특성</span><span class="sxs-lookup"><span data-stu-id="f0e1b-117">Attribute</span></span>|<span data-ttu-id="f0e1b-118">Description</span><span class="sxs-lookup"><span data-stu-id="f0e1b-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0e1b-119">activityName</span><span class="sxs-lookup"><span data-stu-id="f0e1b-119">activityName</span></span>|<span data-ttu-id="f0e1b-120"><xref:System.Activities.Tracking.ActivityStateRecord> 인스턴스를 필터링할 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0e1b-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f0e1b-121">Child Elements</span></span>  
  
|<span data-ttu-id="f0e1b-122">요소</span><span class="sxs-lookup"><span data-stu-id="f0e1b-122">Element</span></span>|<span data-ttu-id="f0e1b-123">설명</span><span class="sxs-lookup"><span data-stu-id="f0e1b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0e1b-124">\<arguments></span><span class="sxs-lookup"><span data-stu-id="f0e1b-124">\<arguments></span></span>](arguments.md)|<span data-ttu-id="f0e1b-125">이 활동 쿼리와 연결되는 인수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="f0e1b-126">\<states></span><span class="sxs-lookup"><span data-stu-id="f0e1b-126">\<states></span></span>](states.md)|<span data-ttu-id="f0e1b-127">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="f0e1b-128">\<states></span><span class="sxs-lookup"><span data-stu-id="f0e1b-128">\<states></span></span>](states.md)|<span data-ttu-id="f0e1b-129">이 활동 쿼리와 연결되는 변수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0e1b-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f0e1b-130">Parent Elements</span></span>  
  
|<span data-ttu-id="f0e1b-131">요소</span><span class="sxs-lookup"><span data-stu-id="f0e1b-131">Element</span></span>|<span data-ttu-id="f0e1b-132">Description</span><span class="sxs-lookup"><span data-stu-id="f0e1b-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0e1b-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="f0e1b-133">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="f0e1b-134">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="f0e1b-135">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0e1b-136">설명</span><span class="sxs-lookup"><span data-stu-id="f0e1b-136">Remarks</span></span>  
 <span data-ttu-id="f0e1b-137">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="f0e1b-138">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="f0e1b-139">인수 >, [ \<](arguments.md) [ 상태\<>](states.md) 및 [ 상태>요소를사용하\<](states.md) 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-139">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="f0e1b-140">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-140">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="f0e1b-141">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로 [ \<activitystatequery >](activitystatequery.md)를 사용 하 여 추적 프로필 내에서 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e1b-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f0e1b-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="f0e1b-142">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f0e1b-143">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="f0e1b-143">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f0e1b-144">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="f0e1b-144">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
