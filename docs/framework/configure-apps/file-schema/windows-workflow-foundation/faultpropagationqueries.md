---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 3d6d03638ec5806448a16cc32b37e630d6198624
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152133"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="160e8-101">\<오류 전파쿼리></span><span class="sxs-lookup"><span data-stu-id="160e8-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="160e8-102">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="160e8-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="160e8-103">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="160e8-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="160e8-104">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="160e8-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="160e8-105">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="160e8-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="160e8-106">프로필 쿼리 추적에 대한 자세한 내용은 [프로필 추적](../../../windows-workflow-foundation/tracking-profiles.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="160e8-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="160e8-107">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="160e8-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="160e8-108">&nbsp;&nbsp;[**\<시스템. 서비스 모델>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="160e8-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="160e8-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="160e8-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="160e8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적프로필>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="160e8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="160e8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<워크플로>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="160e8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="160e8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<오류 전파쿼리>**</span><span class="sxs-lookup"><span data-stu-id="160e8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="160e8-113">구문</span><span class="sxs-lookup"><span data-stu-id="160e8-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="160e8-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="160e8-114">Attributes and Elements</span></span>  
 <span data-ttu-id="160e8-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="160e8-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="160e8-116">특성</span><span class="sxs-lookup"><span data-stu-id="160e8-116">Attributes</span></span>  
 <span data-ttu-id="160e8-117">없음</span><span class="sxs-lookup"><span data-stu-id="160e8-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="160e8-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="160e8-118">Child Elements</span></span>  
  
|<span data-ttu-id="160e8-119">요소</span><span class="sxs-lookup"><span data-stu-id="160e8-119">Element</span></span>|<span data-ttu-id="160e8-120">Description</span><span class="sxs-lookup"><span data-stu-id="160e8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="160e8-121">\<오류 전파쿼리></span><span class="sxs-lookup"><span data-stu-id="160e8-121">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="160e8-122">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="160e8-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="160e8-123">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="160e8-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="160e8-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="160e8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="160e8-125">요소</span><span class="sxs-lookup"><span data-stu-id="160e8-125">Element</span></span>|<span data-ttu-id="160e8-126">Description</span><span class="sxs-lookup"><span data-stu-id="160e8-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="160e8-127">\<워크플로></span><span class="sxs-lookup"><span data-stu-id="160e8-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="160e8-128">**activityDefinitionId** 속성으로 식별 된 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="160e8-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="160e8-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="160e8-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="160e8-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="160e8-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="160e8-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="160e8-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
