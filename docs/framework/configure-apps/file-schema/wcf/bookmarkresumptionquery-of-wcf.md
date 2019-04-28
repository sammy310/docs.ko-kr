---
title: <bookmarkResumptionQuery> WCF의
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 38c87cefc49821b03d119299ef60e3fbbad21d7e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704390"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="3751f-102">\<bookmarkResumptionQuery> of WCF</span><span class="sxs-lookup"><span data-stu-id="3751f-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="3751f-103">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3751f-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="3751f-104">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3751f-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="3751f-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3751f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="3751f-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3751f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3751f-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="3751f-107">\<tracking></span></span>  
<span data-ttu-id="3751f-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="3751f-108">\<profiles></span></span>  
<span data-ttu-id="3751f-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3751f-109">\<trackingProfile></span></span>  
<span data-ttu-id="3751f-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="3751f-110">\<workflow></span></span>  
<span data-ttu-id="3751f-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="3751f-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="3751f-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="3751f-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3751f-113">구문</span><span class="sxs-lookup"><span data-stu-id="3751f-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3751f-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3751f-114">Attributes and elements</span></span>

<span data-ttu-id="3751f-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3751f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3751f-116">특성</span><span class="sxs-lookup"><span data-stu-id="3751f-116">Attributes</span></span>  
  
|<span data-ttu-id="3751f-117">특성</span><span class="sxs-lookup"><span data-stu-id="3751f-117">Attribute</span></span>|<span data-ttu-id="3751f-118">설명</span><span class="sxs-lookup"><span data-stu-id="3751f-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="3751f-119">구독할 책갈피 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3751f-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3751f-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3751f-120">Child elements</span></span>

<span data-ttu-id="3751f-121">없음</span><span class="sxs-lookup"><span data-stu-id="3751f-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="3751f-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3751f-122">Parent elements</span></span>  
  
|<span data-ttu-id="3751f-123">요소</span><span class="sxs-lookup"><span data-stu-id="3751f-123">Element</span></span>|<span data-ttu-id="3751f-124">설명</span><span class="sxs-lookup"><span data-stu-id="3751f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3751f-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="3751f-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="3751f-126">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3751f-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3751f-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="3751f-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3751f-128">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="3751f-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3751f-129">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="3751f-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
