---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 6901244009956a499458858bf73f8fd83ec52e13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152263"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="83e70-101">\<사용자 지정 추적쿼리></span><span class="sxs-lookup"><span data-stu-id="83e70-101">\<customTrackingQueries></span></span>
<span data-ttu-id="83e70-102">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="83e70-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="83e70-103">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83e70-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="83e70-104">프로필 쿼리 추적에 대한 자세한 내용은 [프로필 추적을](../../../windows-workflow-foundation/tracking-profiles.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="83e70-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="83e70-105">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="83e70-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="83e70-106">&nbsp;&nbsp;[**\<시스템. 서비스 모델>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="83e70-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="83e70-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="83e70-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="83e70-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적프로필>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="83e70-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="83e70-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<워크플로>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="83e70-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="83e70-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<사용자 지정 추적쿼리>**</span><span class="sxs-lookup"><span data-stu-id="83e70-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83e70-111">구문</span><span class="sxs-lookup"><span data-stu-id="83e70-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String"
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83e70-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="83e70-112">Attributes and Elements</span></span>  
 <span data-ttu-id="83e70-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83e70-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83e70-114">특성</span><span class="sxs-lookup"><span data-stu-id="83e70-114">Attributes</span></span>  
 <span data-ttu-id="83e70-115">없음</span><span class="sxs-lookup"><span data-stu-id="83e70-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="83e70-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="83e70-116">Child Elements</span></span>  
  
|<span data-ttu-id="83e70-117">요소</span><span class="sxs-lookup"><span data-stu-id="83e70-117">Element</span></span>|<span data-ttu-id="83e70-118">Description</span><span class="sxs-lookup"><span data-stu-id="83e70-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83e70-119">\<사용자 지정 추적 쿼리></span><span class="sxs-lookup"><span data-stu-id="83e70-119">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="83e70-120">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="83e70-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="83e70-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="83e70-121">Parent Elements</span></span>  
  
|<span data-ttu-id="83e70-122">요소</span><span class="sxs-lookup"><span data-stu-id="83e70-122">Element</span></span>|<span data-ttu-id="83e70-123">Description</span><span class="sxs-lookup"><span data-stu-id="83e70-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83e70-124">\<워크플로></span><span class="sxs-lookup"><span data-stu-id="83e70-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="83e70-125">**activityDefinitionId** 속성으로 식별 된 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="83e70-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83e70-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83e70-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="83e70-127">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="83e70-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="83e70-128">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="83e70-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
