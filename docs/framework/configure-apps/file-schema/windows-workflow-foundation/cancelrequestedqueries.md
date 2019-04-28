---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 32a37fb3cc2b93046bea133f351185638b0d7545
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790249"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="9a81f-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="9a81f-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="9a81f-102">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a81f-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="9a81f-103">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9a81f-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="9a81f-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9a81f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9a81f-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9a81f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9a81f-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="9a81f-106">\<tracking></span></span>  
<span data-ttu-id="9a81f-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9a81f-107">\<trackingProfile></span></span>  
<span data-ttu-id="9a81f-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="9a81f-108">\<workflow></span></span>  
<span data-ttu-id="9a81f-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="9a81f-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a81f-110">구문</span><span class="sxs-lookup"><span data-stu-id="9a81f-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a81f-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9a81f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9a81f-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a81f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a81f-113">특성</span><span class="sxs-lookup"><span data-stu-id="9a81f-113">Attributes</span></span>  
 <span data-ttu-id="9a81f-114">없음</span><span class="sxs-lookup"><span data-stu-id="9a81f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9a81f-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9a81f-115">Child Elements</span></span>  
  
|<span data-ttu-id="9a81f-116">요소</span><span class="sxs-lookup"><span data-stu-id="9a81f-116">Element</span></span>|<span data-ttu-id="9a81f-117">설명</span><span class="sxs-lookup"><span data-stu-id="9a81f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a81f-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="9a81f-118">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="9a81f-119">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="9a81f-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a81f-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9a81f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9a81f-121">요소</span><span class="sxs-lookup"><span data-stu-id="9a81f-121">Element</span></span>|<span data-ttu-id="9a81f-122">설명</span><span class="sxs-lookup"><span data-stu-id="9a81f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a81f-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="9a81f-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9a81f-124">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소를 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9a81f-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a81f-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="9a81f-125">See also</span></span>

- [<span data-ttu-id="9a81f-126">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="9a81f-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9a81f-127">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="9a81f-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
