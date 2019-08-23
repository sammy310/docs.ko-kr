---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: f77a613f4eb0456a0085096aa478d37c78122217
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946311"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="5febb-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="5febb-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="5febb-102">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5febb-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="5febb-103">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5febb-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="5febb-104">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5febb-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="5febb-105">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5febb-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="5febb-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5febb-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="5febb-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5febb-107">\<system.serviceModel></span></span>\
<span data-ttu-id="5febb-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="5febb-108">\<tracking></span></span>\
<span data-ttu-id="5febb-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="5febb-109">\<trackingProfile></span></span>\
<span data-ttu-id="5febb-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5febb-110">\<workflow></span></span>\
<span data-ttu-id="5febb-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="5febb-111">\<faultPropagationQueries></span></span>\
<span data-ttu-id="5febb-112">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="5febb-112">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="5febb-113">구문</span><span class="sxs-lookup"><span data-stu-id="5febb-113">Syntax</span></span>

```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5febb-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5febb-114">Attributes and Elements</span></span>

<span data-ttu-id="5febb-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5febb-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5febb-116">특성</span><span class="sxs-lookup"><span data-stu-id="5febb-116">Attributes</span></span>

|<span data-ttu-id="5febb-117">특성</span><span class="sxs-lookup"><span data-stu-id="5febb-117">Attribute</span></span>|<span data-ttu-id="5febb-118">Description</span><span class="sxs-lookup"><span data-stu-id="5febb-118">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="5febb-119">activityName</span><span class="sxs-lookup"><span data-stu-id="5febb-119">activityName</span></span>|<span data-ttu-id="5febb-120">오류를 전파 한 오류 처리기 작업의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5febb-120">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="5febb-121">기본값은 \*이며, 이는 모든 활동에 대해 오류 전파 레코드가 반환된다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5febb-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="5febb-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="5febb-122">faultHandlerActivityName</span></span>|<span data-ttu-id="5febb-123">오류의 출처인 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5febb-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="5febb-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5febb-124">Child Elements</span></span>

<span data-ttu-id="5febb-125">없음</span><span class="sxs-lookup"><span data-stu-id="5febb-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5febb-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5febb-126">Parent Elements</span></span>

|<span data-ttu-id="5febb-127">요소</span><span class="sxs-lookup"><span data-stu-id="5febb-127">Element</span></span>|<span data-ttu-id="5febb-128">설명</span><span class="sxs-lookup"><span data-stu-id="5febb-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5febb-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="5febb-129">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="5febb-130">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 구성 요소 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5febb-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="5febb-131">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5febb-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="5febb-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="5febb-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5febb-133">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="5febb-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5febb-134">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="5febb-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
