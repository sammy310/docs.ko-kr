---
title: <states>의 <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: ff75895949c50cd369e4297ea77dc21106994067
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794411"
---
# <a name="state-of-states"></a><span data-ttu-id="b18b8-102">\<상태 >의 \<상태 ></span><span class="sxs-lookup"><span data-stu-id="b18b8-102">\<state> of \<states></span></span>
<span data-ttu-id="b18b8-103">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b18b8-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="b18b8-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b18b8-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b18b8-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b18b8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b18b8-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="b18b8-106">\<tracking></span></span>  
<span data-ttu-id="b18b8-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b18b8-107">\<trackingProfile></span></span>  
<span data-ttu-id="b18b8-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b18b8-108">\<workflow></span></span>  
<span data-ttu-id="b18b8-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="b18b8-109">\<activityStateQueries></span></span>  
<span data-ttu-id="b18b8-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="b18b8-110">\<activityStateQuery></span></span>  
<span data-ttu-id="b18b8-111">\<states></span><span class="sxs-lookup"><span data-stu-id="b18b8-111">\<states></span></span>  
<span data-ttu-id="b18b8-112">\<state></span><span class="sxs-lookup"><span data-stu-id="b18b8-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b18b8-113">구문</span><span class="sxs-lookup"><span data-stu-id="b18b8-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b18b8-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b18b8-114">Attributes and Elements</span></span>  
 <span data-ttu-id="b18b8-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b18b8-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b18b8-116">특성</span><span class="sxs-lookup"><span data-stu-id="b18b8-116">Attributes</span></span>  
  
|<span data-ttu-id="b18b8-117">특성</span><span class="sxs-lookup"><span data-stu-id="b18b8-117">Attribute</span></span>|<span data-ttu-id="b18b8-118">설명</span><span class="sxs-lookup"><span data-stu-id="b18b8-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b18b8-119">name</span><span class="sxs-lookup"><span data-stu-id="b18b8-119">name</span></span>|<span data-ttu-id="b18b8-120">추적 레코드를 내보내야 할 구독된 활동의 상태를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b18b8-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b18b8-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b18b8-121">Child Elements</span></span>  
 <span data-ttu-id="b18b8-122">없음</span><span class="sxs-lookup"><span data-stu-id="b18b8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b18b8-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b18b8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b18b8-124">요소</span><span class="sxs-lookup"><span data-stu-id="b18b8-124">Element</span></span>|<span data-ttu-id="b18b8-125">설명</span><span class="sxs-lookup"><span data-stu-id="b18b8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b18b8-126">\<states></span><span class="sxs-lookup"><span data-stu-id="b18b8-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="b18b8-127">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b18b8-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b18b8-128">설명</span><span class="sxs-lookup"><span data-stu-id="b18b8-128">Remarks</span></span>  
 <span data-ttu-id="b18b8-129">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b18b8-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="b18b8-130">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b18b8-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="b18b8-131">사용할 수는 [ \<인수 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)를 [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 고 [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 변수 또는 인수를 추출 하는 요소 워크플로의 모든 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="b18b8-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="b18b8-132">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b18b8-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="b18b8-133">ActivityStateRecord 사용해 서만 추출할 수 있으므로 구독 하는 추적 내에서 변수 및 인수를 사용 하 여 프로 파일링 [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b18b8-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b18b8-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="b18b8-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b18b8-135">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="b18b8-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b18b8-136">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="b18b8-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
