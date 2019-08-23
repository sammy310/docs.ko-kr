---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 628dbf801cae5f61dc7d518c27df3380dd2d3d23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945944"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="ad23e-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="ad23e-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="ad23e-102">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad23e-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ad23e-103">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ad23e-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="ad23e-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad23e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ad23e-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ad23e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ad23e-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ad23e-106">\<tracking></span></span>  
<span data-ttu-id="ad23e-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ad23e-107">\<trackingProfile></span></span>  
<span data-ttu-id="ad23e-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ad23e-108">\<workflow></span></span>  
<span data-ttu-id="ad23e-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="ad23e-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad23e-110">구문</span><span class="sxs-lookup"><span data-stu-id="ad23e-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad23e-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ad23e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ad23e-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ad23e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad23e-113">특성</span><span class="sxs-lookup"><span data-stu-id="ad23e-113">Attributes</span></span>  
 <span data-ttu-id="ad23e-114">없음</span><span class="sxs-lookup"><span data-stu-id="ad23e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad23e-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ad23e-115">Child Elements</span></span>  
  
|<span data-ttu-id="ad23e-116">요소</span><span class="sxs-lookup"><span data-stu-id="ad23e-116">Element</span></span>|<span data-ttu-id="ad23e-117">설명</span><span class="sxs-lookup"><span data-stu-id="ad23e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad23e-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="ad23e-118">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="ad23e-119">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="ad23e-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad23e-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ad23e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ad23e-121">요소</span><span class="sxs-lookup"><span data-stu-id="ad23e-121">Element</span></span>|<span data-ttu-id="ad23e-122">Description</span><span class="sxs-lookup"><span data-stu-id="ad23e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad23e-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ad23e-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="ad23e-124">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ad23e-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad23e-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad23e-125">See also</span></span>

- [<span data-ttu-id="ad23e-126">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="ad23e-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ad23e-127">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="ad23e-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
