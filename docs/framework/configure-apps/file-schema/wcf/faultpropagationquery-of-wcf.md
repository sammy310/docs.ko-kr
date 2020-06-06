---
title: <faultPropagationQuery>WCF의
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: a6ef4e198caec4a1f21cedf2ff46d390aeaa2d3b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855336"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="9498e-102">\<faultPropagationQuery>WCF의</span><span class="sxs-lookup"><span data-stu-id="9498e-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="9498e-103">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9498e-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="9498e-104">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9498e-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="9498e-105">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9498e-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="9498e-106">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9498e-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="9498e-107">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9498e-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**  

## <a name="syntax"></a><span data-ttu-id="9498e-108">구문</span><span class="sxs-lookup"><span data-stu-id="9498e-108">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="9498e-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9498e-109">Attributes and elements</span></span>

<span data-ttu-id="9498e-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9498e-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9498e-111">특성</span><span class="sxs-lookup"><span data-stu-id="9498e-111">Attributes</span></span>

|<span data-ttu-id="9498e-112">attribute</span><span class="sxs-lookup"><span data-stu-id="9498e-112">Attribute</span></span>|<span data-ttu-id="9498e-113">Description</span><span class="sxs-lookup"><span data-stu-id="9498e-113">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="9498e-114">오류를 전파 한 오류 처리기 작업의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9498e-114">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="9498e-115">기본값은 \* 로, 모든 작업에 대해 오류 전파 레코드가 반환 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9498e-115">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="9498e-116">오류의 출처인 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9498e-116">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9498e-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9498e-117">Child elements</span></span>

<span data-ttu-id="9498e-118">없음</span><span class="sxs-lookup"><span data-stu-id="9498e-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9498e-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9498e-119">Parent elements</span></span>

|<span data-ttu-id="9498e-120">요소</span><span class="sxs-lookup"><span data-stu-id="9498e-120">Element</span></span>|<span data-ttu-id="9498e-121">Description</span><span class="sxs-lookup"><span data-stu-id="9498e-121">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="9498e-122">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 구성 요소 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9498e-122">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="9498e-123">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9498e-123">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="9498e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9498e-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9498e-125">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="9498e-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9498e-126">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="9498e-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
