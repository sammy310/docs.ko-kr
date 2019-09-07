---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 0d08612ce5d74f4f7f505c538187ddecea610132
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398822"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="df0d9-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="df0d9-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="df0d9-102">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df0d9-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="df0d9-103">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="df0d9-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="df0d9-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df0d9-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="df0d9-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="df0d9-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="df0d9-106">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="df0d9-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="df0d9-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="df0d9-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="df0d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="df0d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="df0d9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="df0d9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="df0d9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cancelRequestedQueries >**</span><span class="sxs-lookup"><span data-stu-id="df0d9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df0d9-111">구문</span><span class="sxs-lookup"><span data-stu-id="df0d9-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df0d9-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="df0d9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="df0d9-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df0d9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df0d9-114">특성</span><span class="sxs-lookup"><span data-stu-id="df0d9-114">Attributes</span></span>  
 <span data-ttu-id="df0d9-115">없음</span><span class="sxs-lookup"><span data-stu-id="df0d9-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="df0d9-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="df0d9-116">Child Elements</span></span>  
  
|<span data-ttu-id="df0d9-117">요소</span><span class="sxs-lookup"><span data-stu-id="df0d9-117">Element</span></span>|<span data-ttu-id="df0d9-118">Description</span><span class="sxs-lookup"><span data-stu-id="df0d9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df0d9-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="df0d9-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="df0d9-120">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="df0d9-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df0d9-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="df0d9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="df0d9-122">요소</span><span class="sxs-lookup"><span data-stu-id="df0d9-122">Element</span></span>|<span data-ttu-id="df0d9-123">설명</span><span class="sxs-lookup"><span data-stu-id="df0d9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df0d9-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="df0d9-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="df0d9-125">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="df0d9-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df0d9-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="df0d9-126">See also</span></span>

- [<span data-ttu-id="df0d9-127">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="df0d9-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="df0d9-128">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="df0d9-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
