---
description: '다음에 대 한 자세한 정보: <faultPropagationQuery> WCF'
title: <faultPropagationQuery> WCF의
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: cd26bf76fec54371ef0455b93c98650bdab19068
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782067"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="be607-103">\<faultPropagationQuery> WCF의</span><span class="sxs-lookup"><span data-stu-id="be607-103">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="be607-104">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be607-104">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="be607-105">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="be607-105">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="be607-106">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be607-106">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="be607-107">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="be607-107">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="be607-108">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be607-108">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**  

## <a name="syntax"></a><span data-ttu-id="be607-109">구문</span><span class="sxs-lookup"><span data-stu-id="be607-109">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="be607-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="be607-110">Attributes and elements</span></span>

<span data-ttu-id="be607-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be607-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="be607-112">특성</span><span class="sxs-lookup"><span data-stu-id="be607-112">Attributes</span></span>

|<span data-ttu-id="be607-113">attribute</span><span class="sxs-lookup"><span data-stu-id="be607-113">Attribute</span></span>|<span data-ttu-id="be607-114">설명</span><span class="sxs-lookup"><span data-stu-id="be607-114">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="be607-115">오류를 전파 한 오류 처리기 작업의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="be607-115">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="be607-116">기본값은 \* 로, 모든 작업에 대해 오류 전파 레코드가 반환 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be607-116">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="be607-117">오류의 출처인 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="be607-117">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="be607-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="be607-118">Child elements</span></span>

<span data-ttu-id="be607-119">없음</span><span class="sxs-lookup"><span data-stu-id="be607-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="be607-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="be607-120">Parent elements</span></span>

|<span data-ttu-id="be607-121">요소</span><span class="sxs-lookup"><span data-stu-id="be607-121">Element</span></span>|<span data-ttu-id="be607-122">설명</span><span class="sxs-lookup"><span data-stu-id="be607-122">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="be607-123">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 구성 요소 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be607-123">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="be607-124">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="be607-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="be607-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be607-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="be607-126">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="be607-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="be607-127">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="be607-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
