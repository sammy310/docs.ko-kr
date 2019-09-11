---
title: <bookmarkResumptionQueries>WCF의
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850131"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="8d756-102">\<WCF의 bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="8d756-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="8d756-103">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8d756-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="8d756-104">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8d756-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="8d756-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d756-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="8d756-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8d756-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8d756-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8d756-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8d756-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="8d756-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="8d756-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="8d756-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="8d756-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="8d756-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="8d756-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="8d756-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="8d756-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bookmarkResumptionQueries >**</span><span class="sxs-lookup"><span data-stu-id="8d756-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="8d756-113">구문</span><span class="sxs-lookup"><span data-stu-id="8d756-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d756-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8d756-114">Attributes and elements</span></span>  
  
<span data-ttu-id="8d756-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d756-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d756-116">특성</span><span class="sxs-lookup"><span data-stu-id="8d756-116">Attributes</span></span>  
  
<span data-ttu-id="8d756-117">없음</span><span class="sxs-lookup"><span data-stu-id="8d756-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8d756-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8d756-118">Child elements</span></span>  
  
|<span data-ttu-id="8d756-119">요소</span><span class="sxs-lookup"><span data-stu-id="8d756-119">Element</span></span>|<span data-ttu-id="8d756-120">Description</span><span class="sxs-lookup"><span data-stu-id="8d756-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d756-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="8d756-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="8d756-122">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="8d756-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="8d756-123">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8d756-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8d756-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8d756-124">Parent elements</span></span>  
  
|<span data-ttu-id="8d756-125">요소</span><span class="sxs-lookup"><span data-stu-id="8d756-125">Element</span></span>|<span data-ttu-id="8d756-126">Description</span><span class="sxs-lookup"><span data-stu-id="8d756-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d756-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8d756-127">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="8d756-128">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8d756-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d756-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="8d756-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8d756-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="8d756-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8d756-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="8d756-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
