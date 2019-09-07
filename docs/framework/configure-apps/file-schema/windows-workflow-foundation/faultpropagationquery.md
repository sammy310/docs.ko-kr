---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 6b43a570b4d4534adce1ef5ab394849651e3ac0e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398724"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="2451f-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="2451f-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="2451f-102">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2451f-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2451f-103">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2451f-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="2451f-104">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2451f-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="2451f-105">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2451f-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="2451f-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2451f-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="2451f-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2451f-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2451f-108">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2451f-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="2451f-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="2451f-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="2451f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="2451f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="2451f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2451f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="2451f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<faultPropagationQueries >** ](faultpropagationqueries.md)</span><span class="sxs-lookup"><span data-stu-id="2451f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)</span></span>\
<span data-ttu-id="2451f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y >**</span><span class="sxs-lookup"><span data-stu-id="2451f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2451f-114">구문</span><span class="sxs-lookup"><span data-stu-id="2451f-114">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="2451f-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2451f-115">Attributes and Elements</span></span>

<span data-ttu-id="2451f-116">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2451f-116">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2451f-117">특성</span><span class="sxs-lookup"><span data-stu-id="2451f-117">Attributes</span></span>

|<span data-ttu-id="2451f-118">특성</span><span class="sxs-lookup"><span data-stu-id="2451f-118">Attribute</span></span>|<span data-ttu-id="2451f-119">설명</span><span class="sxs-lookup"><span data-stu-id="2451f-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="2451f-120">activityName</span><span class="sxs-lookup"><span data-stu-id="2451f-120">activityName</span></span>|<span data-ttu-id="2451f-121">오류를 전파 한 오류 처리기 작업의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2451f-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="2451f-122">기본값은 \*이며, 이는 모든 활동에 대해 오류 전파 레코드가 반환된다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2451f-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="2451f-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="2451f-123">faultHandlerActivityName</span></span>|<span data-ttu-id="2451f-124">오류의 출처인 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2451f-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2451f-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2451f-125">Child Elements</span></span>

<span data-ttu-id="2451f-126">없음</span><span class="sxs-lookup"><span data-stu-id="2451f-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2451f-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2451f-127">Parent Elements</span></span>

|<span data-ttu-id="2451f-128">요소</span><span class="sxs-lookup"><span data-stu-id="2451f-128">Element</span></span>|<span data-ttu-id="2451f-129">설명</span><span class="sxs-lookup"><span data-stu-id="2451f-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2451f-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="2451f-130">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="2451f-131">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 구성 요소 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2451f-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2451f-132">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2451f-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="2451f-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="2451f-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2451f-134">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="2451f-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2451f-135">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="2451f-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
