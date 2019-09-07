---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: b2a81a42a17474bdb0124bec6d3c3eeefa514411
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398854"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="a028d-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="a028d-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="a028d-102">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a028d-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="a028d-103">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a028d-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="a028d-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a028d-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a028d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a028d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a028d-106">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a028d-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="a028d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="a028d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="a028d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="a028d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="a028d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a028d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="a028d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bookmarkResumptionQueries >** ](bookmarkresumptionqueries.md)</span><span class="sxs-lookup"><span data-stu-id="a028d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)</span></span>\
<span data-ttu-id="a028d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y >**</span><span class="sxs-lookup"><span data-stu-id="a028d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a028d-112">구문</span><span class="sxs-lookup"><span data-stu-id="a028d-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a028d-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a028d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a028d-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a028d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a028d-115">특성</span><span class="sxs-lookup"><span data-stu-id="a028d-115">Attributes</span></span>  
  
|<span data-ttu-id="a028d-116">특성</span><span class="sxs-lookup"><span data-stu-id="a028d-116">Attribute</span></span>|<span data-ttu-id="a028d-117">Description</span><span class="sxs-lookup"><span data-stu-id="a028d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a028d-118">name</span><span class="sxs-lookup"><span data-stu-id="a028d-118">name</span></span>|<span data-ttu-id="a028d-119">구독할 책갈피 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a028d-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a028d-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a028d-120">Child Elements</span></span>  
 <span data-ttu-id="a028d-121">없음</span><span class="sxs-lookup"><span data-stu-id="a028d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a028d-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a028d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a028d-123">요소</span><span class="sxs-lookup"><span data-stu-id="a028d-123">Element</span></span>|<span data-ttu-id="a028d-124">설명</span><span class="sxs-lookup"><span data-stu-id="a028d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a028d-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="a028d-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="a028d-126">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a028d-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a028d-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="a028d-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a028d-128">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="a028d-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a028d-129">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="a028d-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
