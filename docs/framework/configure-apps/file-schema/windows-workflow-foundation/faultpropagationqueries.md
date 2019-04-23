---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 402b938913575adfa9125b981dc2913680f07b73
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204044"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="73cfb-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="73cfb-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="73cfb-102">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73cfb-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="73cfb-103">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="73cfb-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="73cfb-104">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cfb-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="73cfb-105">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="73cfb-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="73cfb-106">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73cfb-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="73cfb-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="73cfb-107">\<system.serviceModel></span></span>  
<span data-ttu-id="73cfb-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="73cfb-108">\<tracking></span></span>  
<span data-ttu-id="73cfb-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="73cfb-109">\<trackingProfile></span></span>  
<span data-ttu-id="73cfb-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="73cfb-110">\<workflow></span></span>  
<span data-ttu-id="73cfb-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="73cfb-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73cfb-112">구문</span><span class="sxs-lookup"><span data-stu-id="73cfb-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73cfb-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="73cfb-113">Attributes and Elements</span></span>  
 <span data-ttu-id="73cfb-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73cfb-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73cfb-115">특성</span><span class="sxs-lookup"><span data-stu-id="73cfb-115">Attributes</span></span>  
 <span data-ttu-id="73cfb-116">없음</span><span class="sxs-lookup"><span data-stu-id="73cfb-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73cfb-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="73cfb-117">Child Elements</span></span>  
  
|<span data-ttu-id="73cfb-118">요소</span><span class="sxs-lookup"><span data-stu-id="73cfb-118">Element</span></span>|<span data-ttu-id="73cfb-119">설명</span><span class="sxs-lookup"><span data-stu-id="73cfb-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73cfb-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="73cfb-120">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="73cfb-121">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="73cfb-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="73cfb-122">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="73cfb-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73cfb-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="73cfb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="73cfb-124">요소</span><span class="sxs-lookup"><span data-stu-id="73cfb-124">Element</span></span>|<span data-ttu-id="73cfb-125">설명</span><span class="sxs-lookup"><span data-stu-id="73cfb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73cfb-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="73cfb-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="73cfb-127">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소를 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="73cfb-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73cfb-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="73cfb-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="73cfb-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="73cfb-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="73cfb-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="73cfb-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
