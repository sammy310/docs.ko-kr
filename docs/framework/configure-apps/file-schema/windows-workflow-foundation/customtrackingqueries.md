---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 429940b2ed69d8be497626f634a21adca540b529
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945845"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="2d6b8-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="2d6b8-101">\<customTrackingQueries></span></span>
<span data-ttu-id="2d6b8-102">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="2d6b8-103">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="2d6b8-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2d6b8-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2d6b8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="2d6b8-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2d6b8-106">\<tracking></span></span>  
<span data-ttu-id="2d6b8-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2d6b8-107">\<trackingProfile></span></span>  
<span data-ttu-id="2d6b8-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2d6b8-108">\<workflow></span></span>  
<span data-ttu-id="2d6b8-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="2d6b8-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d6b8-110">구문</span><span class="sxs-lookup"><span data-stu-id="2d6b8-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d6b8-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2d6b8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2d6b8-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d6b8-113">특성</span><span class="sxs-lookup"><span data-stu-id="2d6b8-113">Attributes</span></span>  
 <span data-ttu-id="2d6b8-114">없음</span><span class="sxs-lookup"><span data-stu-id="2d6b8-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2d6b8-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2d6b8-115">Child Elements</span></span>  
  
|<span data-ttu-id="2d6b8-116">요소</span><span class="sxs-lookup"><span data-stu-id="2d6b8-116">Element</span></span>|<span data-ttu-id="2d6b8-117">Description</span><span class="sxs-lookup"><span data-stu-id="2d6b8-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d6b8-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="2d6b8-118">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="2d6b8-119">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2d6b8-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2d6b8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2d6b8-121">요소</span><span class="sxs-lookup"><span data-stu-id="2d6b8-121">Element</span></span>|<span data-ttu-id="2d6b8-122">Description</span><span class="sxs-lookup"><span data-stu-id="2d6b8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d6b8-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2d6b8-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="2d6b8-124">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6b8-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d6b8-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="2d6b8-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2d6b8-126">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="2d6b8-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2d6b8-127">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="2d6b8-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
