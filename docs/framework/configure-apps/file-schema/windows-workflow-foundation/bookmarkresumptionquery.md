---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 9043deb66e1a4314df97f4da41103e74676a270c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945954"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="6fb65-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="6fb65-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="6fb65-102">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fb65-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="6fb65-103">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb65-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="6fb65-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6fb65-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6fb65-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6fb65-105">\<system.serviceModel></span></span>  
<span data-ttu-id="6fb65-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6fb65-106">\<tracking></span></span>  
<span data-ttu-id="6fb65-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6fb65-107">\<trackingProfile></span></span>  
<span data-ttu-id="6fb65-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6fb65-108">\<workflow></span></span>  
<span data-ttu-id="6fb65-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="6fb65-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="6fb65-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="6fb65-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fb65-111">구문</span><span class="sxs-lookup"><span data-stu-id="6fb65-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6fb65-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6fb65-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6fb65-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb65-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6fb65-114">특성</span><span class="sxs-lookup"><span data-stu-id="6fb65-114">Attributes</span></span>  
  
|<span data-ttu-id="6fb65-115">특성</span><span class="sxs-lookup"><span data-stu-id="6fb65-115">Attribute</span></span>|<span data-ttu-id="6fb65-116">Description</span><span class="sxs-lookup"><span data-stu-id="6fb65-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6fb65-117">name</span><span class="sxs-lookup"><span data-stu-id="6fb65-117">name</span></span>|<span data-ttu-id="6fb65-118">구독할 책갈피 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb65-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6fb65-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6fb65-119">Child Elements</span></span>  
 <span data-ttu-id="6fb65-120">없음</span><span class="sxs-lookup"><span data-stu-id="6fb65-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6fb65-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6fb65-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6fb65-122">요소</span><span class="sxs-lookup"><span data-stu-id="6fb65-122">Element</span></span>|<span data-ttu-id="6fb65-123">설명</span><span class="sxs-lookup"><span data-stu-id="6fb65-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6fb65-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="6fb65-124">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="6fb65-125">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fb65-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6fb65-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="6fb65-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6fb65-127">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="6fb65-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6fb65-128">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="6fb65-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
