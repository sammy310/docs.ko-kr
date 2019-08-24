---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: b8052138a729fcba7cb158d81a63126f59e0c4fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69988733"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="a40ac-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="a40ac-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="a40ac-102">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a40ac-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a40ac-103">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a40ac-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="a40ac-104">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40ac-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="a40ac-105">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a40ac-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="a40ac-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a40ac-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a40ac-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a40ac-107">\<system.serviceModel></span></span>  
<span data-ttu-id="a40ac-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="a40ac-108">\<tracking></span></span>  
<span data-ttu-id="a40ac-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a40ac-109">\<trackingProfile></span></span>  
<span data-ttu-id="a40ac-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a40ac-110">\<workflow></span></span>  
<span data-ttu-id="a40ac-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="a40ac-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a40ac-112">구문</span><span class="sxs-lookup"><span data-stu-id="a40ac-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a40ac-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a40ac-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a40ac-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a40ac-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a40ac-115">특성</span><span class="sxs-lookup"><span data-stu-id="a40ac-115">Attributes</span></span>  
 <span data-ttu-id="a40ac-116">없음</span><span class="sxs-lookup"><span data-stu-id="a40ac-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a40ac-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a40ac-117">Child Elements</span></span>  
  
|<span data-ttu-id="a40ac-118">요소</span><span class="sxs-lookup"><span data-stu-id="a40ac-118">Element</span></span>|<span data-ttu-id="a40ac-119">설명</span><span class="sxs-lookup"><span data-stu-id="a40ac-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a40ac-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="a40ac-120">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="a40ac-121">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="a40ac-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a40ac-122">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a40ac-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a40ac-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a40ac-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a40ac-124">요소</span><span class="sxs-lookup"><span data-stu-id="a40ac-124">Element</span></span>|<span data-ttu-id="a40ac-125">Description</span><span class="sxs-lookup"><span data-stu-id="a40ac-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a40ac-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a40ac-126">\<workflow></span></span>](workflow.md)|<span data-ttu-id="a40ac-127">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a40ac-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a40ac-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="a40ac-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a40ac-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="a40ac-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a40ac-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="a40ac-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
