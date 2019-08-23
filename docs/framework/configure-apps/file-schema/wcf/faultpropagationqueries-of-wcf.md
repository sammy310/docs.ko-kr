---
title: <faultPropagationQueries>WCF의
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: aeb964fc8c96c8cb9aeb316bb95f9565fc4a7f18
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918951"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="11602-102">\<WCF의 faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="11602-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="11602-103">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11602-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="11602-104">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="11602-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="11602-105">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11602-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="11602-106">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="11602-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="11602-107">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="11602-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="11602-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="11602-108">\<system.serviceModel></span></span>  
<span data-ttu-id="11602-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="11602-109">\<tracking></span></span>  
<span data-ttu-id="11602-110">\<profiles></span><span class="sxs-lookup"><span data-stu-id="11602-110">\<profiles></span></span>  
<span data-ttu-id="11602-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="11602-111">\<trackingProfile></span></span>  
<span data-ttu-id="11602-112">\<workflow></span><span class="sxs-lookup"><span data-stu-id="11602-112">\<workflow></span></span>  
<span data-ttu-id="11602-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="11602-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11602-114">구문</span><span class="sxs-lookup"><span data-stu-id="11602-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11602-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="11602-115">Attributes and elements</span></span>

<span data-ttu-id="11602-116">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="11602-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="11602-117">특성</span><span class="sxs-lookup"><span data-stu-id="11602-117">Attributes</span></span>

<span data-ttu-id="11602-118">없음</span><span class="sxs-lookup"><span data-stu-id="11602-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="11602-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="11602-119">Child elements</span></span>

|<span data-ttu-id="11602-120">요소</span><span class="sxs-lookup"><span data-stu-id="11602-120">Element</span></span>|<span data-ttu-id="11602-121">설명</span><span class="sxs-lookup"><span data-stu-id="11602-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11602-122">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="11602-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="11602-123">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="11602-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="11602-124">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="11602-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="11602-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="11602-125">Parent elements</span></span>  
  
|<span data-ttu-id="11602-126">요소</span><span class="sxs-lookup"><span data-stu-id="11602-126">Element</span></span>|<span data-ttu-id="11602-127">Description</span><span class="sxs-lookup"><span data-stu-id="11602-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11602-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="11602-128">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="11602-129">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="11602-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11602-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="11602-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="11602-131">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="11602-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="11602-132">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="11602-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
