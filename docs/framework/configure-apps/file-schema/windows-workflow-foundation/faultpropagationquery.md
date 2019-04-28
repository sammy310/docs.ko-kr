---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: f3e281ff8a9de9be41dd6ad9d01ab52798d8e89e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794552"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="06753-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="06753-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="06753-102">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06753-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="06753-103">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="06753-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="06753-104">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06753-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="06753-105">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06753-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="06753-106">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06753-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="06753-107">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="06753-107">\<system.serviceModel>\\</span></span>
<span data-ttu-id="06753-108">\<tracking>\\</span><span class="sxs-lookup"><span data-stu-id="06753-108">\<tracking>\\</span></span>
<span data-ttu-id="06753-109">\<trackingProfile>\\</span><span class="sxs-lookup"><span data-stu-id="06753-109">\<trackingProfile>\\</span></span>
<span data-ttu-id="06753-110">\<workflow>\\</span><span class="sxs-lookup"><span data-stu-id="06753-110">\<workflow>\\</span></span>
<span data-ttu-id="06753-111">\<faultPropagationQueries>\\</span><span class="sxs-lookup"><span data-stu-id="06753-111">\<faultPropagationQueries>\\</span></span>
<span data-ttu-id="06753-112">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="06753-112">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="06753-113">구문</span><span class="sxs-lookup"><span data-stu-id="06753-113">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="06753-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="06753-114">Attributes and Elements</span></span>

<span data-ttu-id="06753-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="06753-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="06753-116">특성</span><span class="sxs-lookup"><span data-stu-id="06753-116">Attributes</span></span>

|<span data-ttu-id="06753-117">특성</span><span class="sxs-lookup"><span data-stu-id="06753-117">Attribute</span></span>|<span data-ttu-id="06753-118">설명</span><span class="sxs-lookup"><span data-stu-id="06753-118">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="06753-119">activityName</span><span class="sxs-lookup"><span data-stu-id="06753-119">activityName</span></span>|<span data-ttu-id="06753-120">오류를 전파 하는 오류 처리기 활동의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="06753-120">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="06753-121">기본값은 \*이며, 이는 모든 활동에 대해 오류 전파 레코드가 반환된다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06753-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="06753-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="06753-122">faultHandlerActivityName</span></span>|<span data-ttu-id="06753-123">오류의 출처인 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="06753-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="06753-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="06753-124">Child Elements</span></span>

<span data-ttu-id="06753-125">없음</span><span class="sxs-lookup"><span data-stu-id="06753-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="06753-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="06753-126">Parent Elements</span></span>

|<span data-ttu-id="06753-127">요소</span><span class="sxs-lookup"><span data-stu-id="06753-127">Element</span></span>|<span data-ttu-id="06753-128">설명</span><span class="sxs-lookup"><span data-stu-id="06753-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="06753-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="06753-129">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="06753-130">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 구성 요소 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06753-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="06753-131">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="06753-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="06753-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="06753-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="06753-133">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="06753-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="06753-134">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="06753-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
