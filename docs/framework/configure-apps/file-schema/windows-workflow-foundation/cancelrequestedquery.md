---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e6840ce647625c36356cccd4651f17de32777e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152289"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="ce4e6-101">\<cancel요청쿼리></span><span class="sxs-lookup"><span data-stu-id="ce4e6-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="ce4e6-102">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ce4e6-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ce4e6-103">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ce4e6-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="ce4e6-104">프로필 쿼리 추적에 대한 자세한 내용은 [프로필 추적](../../../windows-workflow-foundation/tracking-profiles.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ce4e6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ce4e6-105">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ce4e6-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ce4e6-106">&nbsp;&nbsp;[**\<시스템. 서비스 모델>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ce4e6-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="ce4e6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="ce4e6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="ce4e6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적프로필>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="ce4e6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="ce4e6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<워크플로>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ce4e6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="ce4e6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<취소요청쿼리>**](cancelrequestedqueries.md)</span><span class="sxs-lookup"><span data-stu-id="ce4e6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span></span>\
<span data-ttu-id="ce4e6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancel요청쿼리>**</span><span class="sxs-lookup"><span data-stu-id="ce4e6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce4e6-112">구문</span><span class="sxs-lookup"><span data-stu-id="ce4e6-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce4e6-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ce4e6-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ce4e6-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce4e6-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce4e6-115">특성</span><span class="sxs-lookup"><span data-stu-id="ce4e6-115">Attributes</span></span>  
  
|<span data-ttu-id="ce4e6-116">attribute</span><span class="sxs-lookup"><span data-stu-id="ce4e6-116">Attribute</span></span>|<span data-ttu-id="ce4e6-117">Description</span><span class="sxs-lookup"><span data-stu-id="ce4e6-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce4e6-118">activityName</span><span class="sxs-lookup"><span data-stu-id="ce4e6-118">activityName</span></span>|<span data-ttu-id="ce4e6-119">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ce4e6-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="ce4e6-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="ce4e6-120">childActivityName</span></span>|<span data-ttu-id="ce4e6-121">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ce4e6-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce4e6-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ce4e6-122">Child Elements</span></span>  
 <span data-ttu-id="ce4e6-123">없음</span><span class="sxs-lookup"><span data-stu-id="ce4e6-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce4e6-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ce4e6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ce4e6-125">요소</span><span class="sxs-lookup"><span data-stu-id="ce4e6-125">Element</span></span>|<span data-ttu-id="ce4e6-126">Description</span><span class="sxs-lookup"><span data-stu-id="ce4e6-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce4e6-127">\<오류 전파쿼리></span><span class="sxs-lookup"><span data-stu-id="ce4e6-127">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="ce4e6-128">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ce4e6-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ce4e6-129">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ce4e6-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce4e6-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce4e6-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ce4e6-131">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="ce4e6-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ce4e6-132">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="ce4e6-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
