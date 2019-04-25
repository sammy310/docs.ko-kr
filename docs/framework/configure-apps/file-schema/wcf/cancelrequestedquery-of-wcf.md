---
title: <cancelRequestedQuery> WCF의
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: bd6157e63761efa954744ab08ea6c66535def514
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673363"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="37e33-102">\<cancelRequestedQuery > WCF의</span><span class="sxs-lookup"><span data-stu-id="37e33-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="37e33-103">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37e33-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="37e33-104">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37e33-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="37e33-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="37e33-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="37e33-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="37e33-106">\<system.serviceModel></span></span>  
<span data-ttu-id="37e33-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="37e33-107">\<tracking></span></span>  
<span data-ttu-id="37e33-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="37e33-108">\<profiles></span></span>  
<span data-ttu-id="37e33-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="37e33-109">\<trackingProfile></span></span>  
<span data-ttu-id="37e33-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="37e33-110">\<workflow></span></span>  
<span data-ttu-id="37e33-111">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="37e33-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="37e33-112">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="37e33-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37e33-113">구문</span><span class="sxs-lookup"><span data-stu-id="37e33-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37e33-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="37e33-114">Attributes and elements</span></span>

<span data-ttu-id="37e33-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="37e33-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="37e33-116">특성</span><span class="sxs-lookup"><span data-stu-id="37e33-116">Attributes</span></span>  
  
|<span data-ttu-id="37e33-117">특성</span><span class="sxs-lookup"><span data-stu-id="37e33-117">Attribute</span></span>|<span data-ttu-id="37e33-118">설명</span><span class="sxs-lookup"><span data-stu-id="37e33-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="37e33-119">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="37e33-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="37e33-120">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="37e33-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37e33-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="37e33-121">Child elements</span></span>

<span data-ttu-id="37e33-122">없음</span><span class="sxs-lookup"><span data-stu-id="37e33-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="37e33-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="37e33-123">Parent elements</span></span>
  
|<span data-ttu-id="37e33-124">요소</span><span class="sxs-lookup"><span data-stu-id="37e33-124">Element</span></span>|<span data-ttu-id="37e33-125">설명</span><span class="sxs-lookup"><span data-stu-id="37e33-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37e33-126">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="37e33-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="37e33-127">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37e33-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37e33-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="37e33-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="37e33-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="37e33-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="37e33-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="37e33-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
