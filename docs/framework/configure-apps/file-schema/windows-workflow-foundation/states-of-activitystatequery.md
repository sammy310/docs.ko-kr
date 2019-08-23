---
title: <activityStateQuery>의 <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: 50827577374859133e6c673e8850e145b4ccab73
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947422"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="28595-102">\<activitystatequery \<>의 상태 ></span><span class="sxs-lookup"><span data-stu-id="28595-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="28595-103">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="28595-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="28595-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="28595-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="28595-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="28595-105">\<system.serviceModel></span></span>  
<span data-ttu-id="28595-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="28595-106">\<tracking></span></span>  
<span data-ttu-id="28595-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="28595-107">\<trackingProfile></span></span>  
<span data-ttu-id="28595-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="28595-108">\<workflow></span></span>  
<span data-ttu-id="28595-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="28595-109">\<activityStateQueries></span></span>  
<span data-ttu-id="28595-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="28595-110">\<activityStateQuery></span></span>  
<span data-ttu-id="28595-111">\<states></span><span class="sxs-lookup"><span data-stu-id="28595-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28595-112">구문</span><span class="sxs-lookup"><span data-stu-id="28595-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28595-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="28595-113">Attributes and Elements</span></span>  
 <span data-ttu-id="28595-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28595-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28595-115">특성</span><span class="sxs-lookup"><span data-stu-id="28595-115">Attributes</span></span>  
 <span data-ttu-id="28595-116">없음</span><span class="sxs-lookup"><span data-stu-id="28595-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="28595-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="28595-117">Child Elements</span></span>  
  
|<span data-ttu-id="28595-118">요소</span><span class="sxs-lookup"><span data-stu-id="28595-118">Element</span></span>|<span data-ttu-id="28595-119">설명</span><span class="sxs-lookup"><span data-stu-id="28595-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28595-120">\<state></span><span class="sxs-lookup"><span data-stu-id="28595-120">\<state></span></span>](state-of-states.md)|<span data-ttu-id="28595-121">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="28595-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28595-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="28595-122">Parent Elements</span></span>  
  
|<span data-ttu-id="28595-123">요소</span><span class="sxs-lookup"><span data-stu-id="28595-123">Element</span></span>|<span data-ttu-id="28595-124">설명</span><span class="sxs-lookup"><span data-stu-id="28595-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28595-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="28595-125">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="28595-126">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="28595-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="28595-127">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="28595-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28595-128">설명</span><span class="sxs-lookup"><span data-stu-id="28595-128">Remarks</span></span>  
 <span data-ttu-id="28595-129">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="28595-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="28595-130">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28595-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="28595-131">인수 >, [ \<](arguments.md) [ 상태\<>](states.md) 및 [ 상태>요소를사용하\<](states.md) 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28595-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="28595-132">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28595-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="28595-133">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로 [ \<activitystatequery >](activitystatequery.md)를 사용 하 여 추적 프로필 내에서 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="28595-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="28595-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="28595-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="28595-135">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="28595-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="28595-136">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="28595-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
