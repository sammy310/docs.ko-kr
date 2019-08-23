---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: bb7ae702209df3c0297ec2cfac6b09ee47ad9558
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946124"
---
# <a name="arguments"></a><span data-ttu-id="30320-101">\<arguments></span><span class="sxs-lookup"><span data-stu-id="30320-101">\<arguments></span></span>
<span data-ttu-id="30320-102">활동 상태 쿼리와 연결되는 인수의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30320-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="30320-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30320-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="30320-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="30320-104">\<system.serviceModel></span></span>  
<span data-ttu-id="30320-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="30320-105">\<tracking></span></span>  
<span data-ttu-id="30320-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="30320-106">\<trackingProfile></span></span>  
<span data-ttu-id="30320-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="30320-107">\<workflow></span></span>  
<span data-ttu-id="30320-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="30320-108">\<activityStateQueries></span></span>  
<span data-ttu-id="30320-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="30320-109">\<activityStateQuery></span></span>  
<span data-ttu-id="30320-110">\<arguments></span><span class="sxs-lookup"><span data-stu-id="30320-110">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30320-111">구문</span><span class="sxs-lookup"><span data-stu-id="30320-111">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30320-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="30320-112">Attributes and Elements</span></span>  
 <span data-ttu-id="30320-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30320-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30320-114">특성</span><span class="sxs-lookup"><span data-stu-id="30320-114">Attributes</span></span>  
 <span data-ttu-id="30320-115">없음</span><span class="sxs-lookup"><span data-stu-id="30320-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="30320-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="30320-116">Child Elements</span></span>  
  
|<span data-ttu-id="30320-117">요소</span><span class="sxs-lookup"><span data-stu-id="30320-117">Element</span></span>|<span data-ttu-id="30320-118">설명</span><span class="sxs-lookup"><span data-stu-id="30320-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30320-119">\<argument></span><span class="sxs-lookup"><span data-stu-id="30320-119">\<argument></span></span>](argument.md)|<span data-ttu-id="30320-120">활동 상태 쿼리와 연결되는 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="30320-120">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="30320-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="30320-121">Parent Elements</span></span>  
  
|<span data-ttu-id="30320-122">요소</span><span class="sxs-lookup"><span data-stu-id="30320-122">Element</span></span>|<span data-ttu-id="30320-123">Description</span><span class="sxs-lookup"><span data-stu-id="30320-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30320-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="30320-124">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="30320-125">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30320-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="30320-126">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="30320-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30320-127">설명</span><span class="sxs-lookup"><span data-stu-id="30320-127">Remarks</span></span>  
 <span data-ttu-id="30320-128">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="30320-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="30320-129">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30320-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="30320-130">인수 >, [ \<](arguments.md) [ 상태\<>](states.md) 및 [ 상태>요소를사용하\<](states.md) 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30320-130">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="30320-131">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30320-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="30320-132">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로 [ \<activitystatequery >](activitystatequery.md)를 사용 하 여 추적 프로필 내에서 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="30320-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="30320-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="30320-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="30320-134">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="30320-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="30320-135">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="30320-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
