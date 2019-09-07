---
title: <states>의 <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 391e552bce34d637a324c78702cb0e7121f2c999
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398660"
---
# <a name="state-of-states"></a><span data-ttu-id="3ac16-102">\<상태 > \<상태 ></span><span class="sxs-lookup"><span data-stu-id="3ac16-102">\<state> of \<states></span></span>
<span data-ttu-id="3ac16-103">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3ac16-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="3ac16-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ac16-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3ac16-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3ac16-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3ac16-106">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3ac16-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="3ac16-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="3ac16-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="3ac16-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="3ac16-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="3ac16-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3ac16-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="3ac16-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQueries >** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="3ac16-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="3ac16-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQuery >** ](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="3ac16-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="3ac16-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<상태 >** ](states-of-activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="3ac16-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-activitystatequery.md)</span></span>\
<span data-ttu-id="3ac16-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<상태 >**</span><span class="sxs-lookup"><span data-stu-id="3ac16-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ac16-114">구문</span><span class="sxs-lookup"><span data-stu-id="3ac16-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ac16-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3ac16-115">Attributes and Elements</span></span>  
 <span data-ttu-id="3ac16-116">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3ac16-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ac16-117">특성</span><span class="sxs-lookup"><span data-stu-id="3ac16-117">Attributes</span></span>  
  
|<span data-ttu-id="3ac16-118">특성</span><span class="sxs-lookup"><span data-stu-id="3ac16-118">Attribute</span></span>|<span data-ttu-id="3ac16-119">Description</span><span class="sxs-lookup"><span data-stu-id="3ac16-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ac16-120">name</span><span class="sxs-lookup"><span data-stu-id="3ac16-120">name</span></span>|<span data-ttu-id="3ac16-121">추적 레코드를 내보내야 할 구독된 활동의 상태를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3ac16-121">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ac16-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3ac16-122">Child Elements</span></span>  
 <span data-ttu-id="3ac16-123">없음</span><span class="sxs-lookup"><span data-stu-id="3ac16-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ac16-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3ac16-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3ac16-125">요소</span><span class="sxs-lookup"><span data-stu-id="3ac16-125">Element</span></span>|<span data-ttu-id="3ac16-126">Description</span><span class="sxs-lookup"><span data-stu-id="3ac16-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ac16-127">\<states></span><span class="sxs-lookup"><span data-stu-id="3ac16-127">\<states></span></span>](states-of-activitystatequery.md)|<span data-ttu-id="3ac16-128">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3ac16-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ac16-129">설명</span><span class="sxs-lookup"><span data-stu-id="3ac16-129">Remarks</span></span>  
 <span data-ttu-id="3ac16-130">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3ac16-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="3ac16-131">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3ac16-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="3ac16-132">인수 >, [ \<](arguments.md) [ 상태\<>](states.md) 및 [ 상태>요소를사용하\<](states.md) 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ac16-132">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="3ac16-133">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ac16-133">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="3ac16-134">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로 [ \<activitystatequery >](activitystatequery.md)를 사용 하 여 추적 프로필 내에서 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ac16-134">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ac16-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="3ac16-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3ac16-136">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="3ac16-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3ac16-137">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="3ac16-137">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
