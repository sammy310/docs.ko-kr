---
title: <cancelRequestedQuery>WCF의
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 0ac8b87afc44927ab6653dd6fcdc09cd61436a9b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850057"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="0fd57-102">\<WCF의 cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="0fd57-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="0fd57-103">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0fd57-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0fd57-104">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd57-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="0fd57-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0fd57-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="0fd57-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0fd57-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0fd57-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0fd57-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0fd57-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="0fd57-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="0fd57-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="0fd57-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="0fd57-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="0fd57-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="0fd57-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="0fd57-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="0fd57-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cancelRequestedQueries >** ](cancelrequestedqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="0fd57-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries-of-wcf.md)</span></span>\
<span data-ttu-id="0fd57-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cancelRequestedQuery >**</span><span class="sxs-lookup"><span data-stu-id="0fd57-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="0fd57-114">구문</span><span class="sxs-lookup"><span data-stu-id="0fd57-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0fd57-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0fd57-115">Attributes and elements</span></span>

<span data-ttu-id="0fd57-116">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd57-116">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0fd57-117">특성</span><span class="sxs-lookup"><span data-stu-id="0fd57-117">Attributes</span></span>  
  
|<span data-ttu-id="0fd57-118">특성</span><span class="sxs-lookup"><span data-stu-id="0fd57-118">Attribute</span></span>|<span data-ttu-id="0fd57-119">Description</span><span class="sxs-lookup"><span data-stu-id="0fd57-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="0fd57-120">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd57-120">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="0fd57-121">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd57-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0fd57-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0fd57-122">Child elements</span></span>

<span data-ttu-id="0fd57-123">없음</span><span class="sxs-lookup"><span data-stu-id="0fd57-123">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="0fd57-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0fd57-124">Parent elements</span></span>
  
|<span data-ttu-id="0fd57-125">요소</span><span class="sxs-lookup"><span data-stu-id="0fd57-125">Element</span></span>|<span data-ttu-id="0fd57-126">Description</span><span class="sxs-lookup"><span data-stu-id="0fd57-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0fd57-127">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="0fd57-127">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="0fd57-128">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0fd57-128">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0fd57-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="0fd57-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0fd57-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="0fd57-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0fd57-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="0fd57-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
