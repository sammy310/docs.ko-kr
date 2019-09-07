---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: bc0cc5fd027da45994269b149b72496fa03becef
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398739"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="ad3ce-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="ad3ce-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="ad3ce-102">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ce-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="ad3ce-103">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ce-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="ad3ce-104">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ce-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="ad3ce-105">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ce-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="ad3ce-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad3ce-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ad3ce-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ad3ce-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ad3ce-108">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ad3ce-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="ad3ce-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="ad3ce-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="ad3ce-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="ad3ce-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="ad3ce-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ad3ce-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="ad3ce-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<faultPropagationQueries >**</span><span class="sxs-lookup"><span data-stu-id="ad3ce-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="ad3ce-113">구문</span><span class="sxs-lookup"><span data-stu-id="ad3ce-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String" 
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad3ce-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ad3ce-114">Attributes and Elements</span></span>  
 <span data-ttu-id="ad3ce-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ce-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad3ce-116">특성</span><span class="sxs-lookup"><span data-stu-id="ad3ce-116">Attributes</span></span>  
 <span data-ttu-id="ad3ce-117">없음</span><span class="sxs-lookup"><span data-stu-id="ad3ce-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad3ce-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ad3ce-118">Child Elements</span></span>  
  
|<span data-ttu-id="ad3ce-119">요소</span><span class="sxs-lookup"><span data-stu-id="ad3ce-119">Element</span></span>|<span data-ttu-id="ad3ce-120">설명</span><span class="sxs-lookup"><span data-stu-id="ad3ce-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad3ce-121">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="ad3ce-121">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="ad3ce-122">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ce-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="ad3ce-123">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ce-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad3ce-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ad3ce-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ad3ce-125">요소</span><span class="sxs-lookup"><span data-stu-id="ad3ce-125">Element</span></span>|<span data-ttu-id="ad3ce-126">설명</span><span class="sxs-lookup"><span data-stu-id="ad3ce-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad3ce-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ad3ce-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="ad3ce-128">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ce-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad3ce-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad3ce-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ad3ce-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="ad3ce-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ad3ce-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="ad3ce-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
