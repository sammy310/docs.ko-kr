---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 32a37fb3cc2b93046bea133f351185638b0d7545
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163165"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="d2323-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="d2323-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="d2323-102">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d2323-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d2323-103">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d2323-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="d2323-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d2323-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d2323-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d2323-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d2323-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d2323-106">\<tracking></span></span>  
<span data-ttu-id="d2323-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d2323-107">\<trackingProfile></span></span>  
<span data-ttu-id="d2323-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d2323-108">\<workflow></span></span>  
<span data-ttu-id="d2323-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="d2323-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2323-110">구문</span><span class="sxs-lookup"><span data-stu-id="d2323-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2323-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d2323-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d2323-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2323-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2323-113">특성</span><span class="sxs-lookup"><span data-stu-id="d2323-113">Attributes</span></span>  
 <span data-ttu-id="d2323-114">없음</span><span class="sxs-lookup"><span data-stu-id="d2323-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d2323-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d2323-115">Child Elements</span></span>  
  
|<span data-ttu-id="d2323-116">요소</span><span class="sxs-lookup"><span data-stu-id="d2323-116">Element</span></span>|<span data-ttu-id="d2323-117">설명</span><span class="sxs-lookup"><span data-stu-id="d2323-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2323-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="d2323-118">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="d2323-119">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="d2323-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2323-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d2323-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d2323-121">요소</span><span class="sxs-lookup"><span data-stu-id="d2323-121">Element</span></span>|<span data-ttu-id="d2323-122">설명</span><span class="sxs-lookup"><span data-stu-id="d2323-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2323-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d2323-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="d2323-124">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소를 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d2323-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2323-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="d2323-125">See also</span></span>

- [<span data-ttu-id="d2323-126">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="d2323-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d2323-127">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d2323-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
