---
title: <bookmarkResumptionQueries>WCF의
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 5ec9827e9862866096265da576c91b10573012d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919735"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="90200-102">\<WCF의 bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="90200-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="90200-103">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="90200-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="90200-104">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="90200-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="90200-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90200-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="90200-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="90200-106">\<system.serviceModel></span></span>  
<span data-ttu-id="90200-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="90200-107">\<tracking></span></span>  
<span data-ttu-id="90200-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="90200-108">\<profiles></span></span>  
<span data-ttu-id="90200-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="90200-109">\<trackingProfile></span></span>  
<span data-ttu-id="90200-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="90200-110">\<workflow></span></span>  
<span data-ttu-id="90200-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="90200-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="90200-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="90200-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90200-113">구문</span><span class="sxs-lookup"><span data-stu-id="90200-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90200-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="90200-114">Attributes and elements</span></span>  
  
<span data-ttu-id="90200-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="90200-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90200-116">특성</span><span class="sxs-lookup"><span data-stu-id="90200-116">Attributes</span></span>  
  
<span data-ttu-id="90200-117">없음</span><span class="sxs-lookup"><span data-stu-id="90200-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="90200-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="90200-118">Child elements</span></span>  
  
|<span data-ttu-id="90200-119">요소</span><span class="sxs-lookup"><span data-stu-id="90200-119">Element</span></span>|<span data-ttu-id="90200-120">Description</span><span class="sxs-lookup"><span data-stu-id="90200-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90200-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="90200-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="90200-122">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="90200-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="90200-123">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="90200-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="90200-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="90200-124">Parent elements</span></span>  
  
|<span data-ttu-id="90200-125">요소</span><span class="sxs-lookup"><span data-stu-id="90200-125">Element</span></span>|<span data-ttu-id="90200-126">설명</span><span class="sxs-lookup"><span data-stu-id="90200-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90200-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="90200-127">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="90200-128">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="90200-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90200-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="90200-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="90200-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="90200-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="90200-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="90200-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
