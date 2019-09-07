---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 563e0cbd3f50887e1c9e3d47a3c9502acc13b2c9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398862"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="ce7f9-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="ce7f9-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="ce7f9-102">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ce7f9-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ce7f9-103">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7f9-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="ce7f9-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce7f9-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ce7f9-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ce7f9-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ce7f9-106">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ce7f9-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="ce7f9-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="ce7f9-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="ce7f9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="ce7f9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="ce7f9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ce7f9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="ce7f9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bookmarkResumptionQueries >**</span><span class="sxs-lookup"><span data-stu-id="ce7f9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="ce7f9-111">구문</span><span class="sxs-lookup"><span data-stu-id="ce7f9-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce7f9-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ce7f9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ce7f9-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7f9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce7f9-114">특성</span><span class="sxs-lookup"><span data-stu-id="ce7f9-114">Attributes</span></span>  
 <span data-ttu-id="ce7f9-115">없음</span><span class="sxs-lookup"><span data-stu-id="ce7f9-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce7f9-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ce7f9-116">Child Elements</span></span>  
  
|<span data-ttu-id="ce7f9-117">요소</span><span class="sxs-lookup"><span data-stu-id="ce7f9-117">Element</span></span>|<span data-ttu-id="ce7f9-118">Description</span><span class="sxs-lookup"><span data-stu-id="ce7f9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce7f9-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="ce7f9-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="ce7f9-120">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="ce7f9-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ce7f9-121">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7f9-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce7f9-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ce7f9-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ce7f9-123">요소</span><span class="sxs-lookup"><span data-stu-id="ce7f9-123">Element</span></span>|<span data-ttu-id="ce7f9-124">설명</span><span class="sxs-lookup"><span data-stu-id="ce7f9-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce7f9-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ce7f9-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="ce7f9-126">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ce7f9-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce7f9-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="ce7f9-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ce7f9-128">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="ce7f9-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ce7f9-129">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="ce7f9-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
