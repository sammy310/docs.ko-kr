---
title: <bookmarkResumptionQuery>WCF의
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 36d169b78e78692c7b45c75d5d375bddbba1c66f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850110"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="9ca7c-102">\<WCF의 y ></span><span class="sxs-lookup"><span data-stu-id="9ca7c-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="9ca7c-103">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ca7c-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="9ca7c-104">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca7c-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="9ca7c-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca7c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="9ca7c-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ca7c-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9ca7c-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9ca7c-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9ca7c-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9ca7c-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="9ca7c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="9ca7c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="9ca7c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9ca7c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="9ca7c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9ca7c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="9ca7c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bookmarkResumptionQueries >** ](bookmarkresumptionqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9ca7c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)</span></span>\
<span data-ttu-id="9ca7c-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y >**</span><span class="sxs-lookup"><span data-stu-id="9ca7c-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ca7c-114">구문</span><span class="sxs-lookup"><span data-stu-id="9ca7c-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ca7c-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9ca7c-115">Attributes and elements</span></span>

<span data-ttu-id="9ca7c-116">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca7c-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ca7c-117">특성</span><span class="sxs-lookup"><span data-stu-id="9ca7c-117">Attributes</span></span>  
  
|<span data-ttu-id="9ca7c-118">특성</span><span class="sxs-lookup"><span data-stu-id="9ca7c-118">Attribute</span></span>|<span data-ttu-id="9ca7c-119">Description</span><span class="sxs-lookup"><span data-stu-id="9ca7c-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="9ca7c-120">구독할 책갈피 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca7c-120">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ca7c-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9ca7c-121">Child elements</span></span>

<span data-ttu-id="9ca7c-122">없음</span><span class="sxs-lookup"><span data-stu-id="9ca7c-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="9ca7c-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9ca7c-123">Parent elements</span></span>  
  
|<span data-ttu-id="9ca7c-124">요소</span><span class="sxs-lookup"><span data-stu-id="9ca7c-124">Element</span></span>|<span data-ttu-id="9ca7c-125">Description</span><span class="sxs-lookup"><span data-stu-id="9ca7c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ca7c-126">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="9ca7c-126">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="9ca7c-127">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ca7c-127">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ca7c-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="9ca7c-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9ca7c-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="9ca7c-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9ca7c-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="9ca7c-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
