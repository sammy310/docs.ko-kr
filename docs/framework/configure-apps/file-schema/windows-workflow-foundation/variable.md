---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: a8f66f950db1edf8cd6ec21400785fb7e01b878e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947270"
---
# <a name="variable"></a><span data-ttu-id="455e8-101">\<variable></span><span class="sxs-lookup"><span data-stu-id="455e8-101">\<variable></span></span>
<span data-ttu-id="455e8-102">이 활동 쿼리와 연결된 변수의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="455e8-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="455e8-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="455e8-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="455e8-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="455e8-104">\<system.serviceModel></span></span>  
<span data-ttu-id="455e8-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="455e8-105">\<tracking></span></span>  
<span data-ttu-id="455e8-106">\<profiles></span><span class="sxs-lookup"><span data-stu-id="455e8-106">\<profiles></span></span>  
<span data-ttu-id="455e8-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="455e8-107">\<trackingProfile></span></span>  
<span data-ttu-id="455e8-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="455e8-108">\<workflow></span></span>  
<span data-ttu-id="455e8-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="455e8-109">\<activityStateQueries></span></span>  
<span data-ttu-id="455e8-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="455e8-110">\<activityStateQuery></span></span>  
<span data-ttu-id="455e8-111">\<variables></span><span class="sxs-lookup"><span data-stu-id="455e8-111">\<variables></span></span>  
<span data-ttu-id="455e8-112">\<variable></span><span class="sxs-lookup"><span data-stu-id="455e8-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="455e8-113">구문</span><span class="sxs-lookup"><span data-stu-id="455e8-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="455e8-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="455e8-114">Attributes and Elements</span></span>  
 <span data-ttu-id="455e8-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="455e8-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="455e8-116">특성</span><span class="sxs-lookup"><span data-stu-id="455e8-116">Attributes</span></span>  
  
|<span data-ttu-id="455e8-117">특성</span><span class="sxs-lookup"><span data-stu-id="455e8-117">Attribute</span></span>|<span data-ttu-id="455e8-118">Description</span><span class="sxs-lookup"><span data-stu-id="455e8-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="455e8-119">name</span><span class="sxs-lookup"><span data-stu-id="455e8-119">name</span></span>|<span data-ttu-id="455e8-120">변수의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="455e8-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="455e8-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="455e8-121">Child Elements</span></span>  
 <span data-ttu-id="455e8-122">없음</span><span class="sxs-lookup"><span data-stu-id="455e8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="455e8-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="455e8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="455e8-124">요소</span><span class="sxs-lookup"><span data-stu-id="455e8-124">Element</span></span>|<span data-ttu-id="455e8-125">Description</span><span class="sxs-lookup"><span data-stu-id="455e8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="455e8-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="455e8-126">\<variable></span></span>](variable.md)|<span data-ttu-id="455e8-127">활동 상태 쿼리와 연결되는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="455e8-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="455e8-128">설명</span><span class="sxs-lookup"><span data-stu-id="455e8-128">Remarks</span></span>  
 <span data-ttu-id="455e8-129">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="455e8-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="455e8-130">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="455e8-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="455e8-131">인수 >, [ \<](arguments.md) [ 상태\<>](states.md) 및 [ 상태>요소를사용하\<](states.md) 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="455e8-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="455e8-132">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="455e8-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="455e8-133">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로 [ \<activitystatequery >](activitystatequery.md)를 사용 하 여 추적 프로필 내에서 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="455e8-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="455e8-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="455e8-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="455e8-135">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="455e8-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="455e8-136">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="455e8-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
