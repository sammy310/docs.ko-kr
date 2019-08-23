---
title: <faultPropagationQuery>WCF의
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: 6ba6478ca500c0a8ef150966a97898f8743ffdf8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925628"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="70e6d-102">\<WCF의 y ></span><span class="sxs-lookup"><span data-stu-id="70e6d-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="70e6d-103">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70e6d-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="70e6d-104">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="70e6d-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="70e6d-105">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e6d-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="70e6d-106">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="70e6d-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="70e6d-107">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70e6d-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="70e6d-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="70e6d-108">\<system.serviceModel></span></span>\
<span data-ttu-id="70e6d-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="70e6d-109">\<tracking></span></span>\
<span data-ttu-id="70e6d-110">\<profiles></span><span class="sxs-lookup"><span data-stu-id="70e6d-110">\<profiles></span></span>\
<span data-ttu-id="70e6d-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="70e6d-111">\<trackingProfile></span></span>\
<span data-ttu-id="70e6d-112">\<workflow></span><span class="sxs-lookup"><span data-stu-id="70e6d-112">\<workflow></span></span>\
<span data-ttu-id="70e6d-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="70e6d-113">\<faultPropagationQueries></span></span>\
<span data-ttu-id="70e6d-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="70e6d-114">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="70e6d-115">구문</span><span class="sxs-lookup"><span data-stu-id="70e6d-115">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="70e6d-116">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="70e6d-116">Attributes and elements</span></span>

<span data-ttu-id="70e6d-117">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70e6d-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="70e6d-118">특성</span><span class="sxs-lookup"><span data-stu-id="70e6d-118">Attributes</span></span>

|<span data-ttu-id="70e6d-119">특성</span><span class="sxs-lookup"><span data-stu-id="70e6d-119">Attribute</span></span>|<span data-ttu-id="70e6d-120">Description</span><span class="sxs-lookup"><span data-stu-id="70e6d-120">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="70e6d-121">오류를 전파 한 오류 처리기 작업의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="70e6d-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="70e6d-122">기본값은 \*에 모든 활동에 대해 오류 전파 레코드가 반환 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70e6d-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="70e6d-123">오류의 출처인 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="70e6d-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="70e6d-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="70e6d-124">Child elements</span></span>

<span data-ttu-id="70e6d-125">없음</span><span class="sxs-lookup"><span data-stu-id="70e6d-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="70e6d-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="70e6d-126">Parent elements</span></span>

|<span data-ttu-id="70e6d-127">요소</span><span class="sxs-lookup"><span data-stu-id="70e6d-127">Element</span></span>|<span data-ttu-id="70e6d-128">Description</span><span class="sxs-lookup"><span data-stu-id="70e6d-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="70e6d-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="70e6d-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="70e6d-130">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 구성 요소 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70e6d-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="70e6d-131">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="70e6d-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="70e6d-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="70e6d-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="70e6d-133">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="70e6d-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="70e6d-134">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="70e6d-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
