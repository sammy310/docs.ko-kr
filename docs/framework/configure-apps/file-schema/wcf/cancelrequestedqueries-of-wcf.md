---
title: <cancelRequestedQueries>WCF의
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 63cfc835ac7ce88bde56fd9243a2cf6652cbce6e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850087"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="f1d1e-102">\<WCF의 cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="f1d1e-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="f1d1e-103">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f1d1e-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="f1d1e-104">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d1e-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="f1d1e-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f1d1e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f1d1e-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f1d1e-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f1d1e-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f1d1e-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f1d1e-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f1d1e-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="f1d1e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="f1d1e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="f1d1e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f1d1e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="f1d1e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f1d1e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="f1d1e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cancelRequestedQueries >**</span><span class="sxs-lookup"><span data-stu-id="f1d1e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1d1e-113">구문</span><span class="sxs-lookup"><span data-stu-id="f1d1e-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1d1e-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f1d1e-114">Attributes and elements</span></span>  

<span data-ttu-id="f1d1e-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d1e-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1d1e-116">특성</span><span class="sxs-lookup"><span data-stu-id="f1d1e-116">Attributes</span></span>

<span data-ttu-id="f1d1e-117">없음</span><span class="sxs-lookup"><span data-stu-id="f1d1e-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f1d1e-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f1d1e-118">Child elements</span></span>
  
|<span data-ttu-id="f1d1e-119">요소</span><span class="sxs-lookup"><span data-stu-id="f1d1e-119">Element</span></span>|<span data-ttu-id="f1d1e-120">Description</span><span class="sxs-lookup"><span data-stu-id="f1d1e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1d1e-121">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="f1d1e-121">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="f1d1e-122">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="f1d1e-122">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1d1e-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f1d1e-123">Parent elements</span></span>  
  
|<span data-ttu-id="f1d1e-124">요소</span><span class="sxs-lookup"><span data-stu-id="f1d1e-124">Element</span></span>|<span data-ttu-id="f1d1e-125">Description</span><span class="sxs-lookup"><span data-stu-id="f1d1e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1d1e-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="f1d1e-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="f1d1e-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f1d1e-127">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1d1e-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="f1d1e-128">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="f1d1e-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="f1d1e-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f1d1e-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="f1d1e-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
