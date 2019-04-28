---
title: <faultPropagationQuery> WCF의
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: e5793852d49a052d05f6cb2f4efbe166d67afc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701049"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="12288-102">\<faultPropagationQuery> of WCF</span><span class="sxs-lookup"><span data-stu-id="12288-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="12288-103">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12288-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="12288-104">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="12288-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="12288-105">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12288-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="12288-106">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="12288-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="12288-107">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="12288-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="12288-108">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="12288-108">\<system.serviceModel>\\</span></span>
<span data-ttu-id="12288-109">\<tracking>\\</span><span class="sxs-lookup"><span data-stu-id="12288-109">\<tracking>\\</span></span>
<span data-ttu-id="12288-110">\<profiles>\\</span><span class="sxs-lookup"><span data-stu-id="12288-110">\<profiles>\\</span></span>
<span data-ttu-id="12288-111">\<trackingProfile>\\</span><span class="sxs-lookup"><span data-stu-id="12288-111">\<trackingProfile>\\</span></span>
<span data-ttu-id="12288-112">\<workflow>\\</span><span class="sxs-lookup"><span data-stu-id="12288-112">\<workflow>\\</span></span>
<span data-ttu-id="12288-113">\<faultPropagationQueries>\\</span><span class="sxs-lookup"><span data-stu-id="12288-113">\<faultPropagationQueries>\\</span></span>
<span data-ttu-id="12288-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="12288-114">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="12288-115">구문</span><span class="sxs-lookup"><span data-stu-id="12288-115">Syntax</span></span>

```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String" />
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="12288-116">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="12288-116">Attributes and elements</span></span>

<span data-ttu-id="12288-117">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12288-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="12288-118">특성</span><span class="sxs-lookup"><span data-stu-id="12288-118">Attributes</span></span>

|<span data-ttu-id="12288-119">특성</span><span class="sxs-lookup"><span data-stu-id="12288-119">Attribute</span></span>|<span data-ttu-id="12288-120">설명</span><span class="sxs-lookup"><span data-stu-id="12288-120">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="12288-121">오류를 전파 하는 오류 처리기 활동의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="12288-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="12288-122">기본값은 \*에 모든 활동에 대해 오류 전파 레코드가 반환 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12288-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="12288-123">오류의 출처인 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="12288-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="12288-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="12288-124">Child elements</span></span>

<span data-ttu-id="12288-125">없음</span><span class="sxs-lookup"><span data-stu-id="12288-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="12288-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="12288-126">Parent elements</span></span>

|<span data-ttu-id="12288-127">요소</span><span class="sxs-lookup"><span data-stu-id="12288-127">Element</span></span>|<span data-ttu-id="12288-128">설명</span><span class="sxs-lookup"><span data-stu-id="12288-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="12288-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="12288-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="12288-130">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 구성 요소 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12288-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="12288-131">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="12288-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="12288-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="12288-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="12288-133">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="12288-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="12288-134">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="12288-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
