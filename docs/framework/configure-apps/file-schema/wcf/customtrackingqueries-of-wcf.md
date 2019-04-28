---
title: <customTrackingQueries> WCF의
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 8b317cc289853902592e145e34b6e7bf5f84763b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704170"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="4c481-102">\<customTrackingQueries> of WCF</span><span class="sxs-lookup"><span data-stu-id="4c481-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="4c481-103">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4c481-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="4c481-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4c481-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="4c481-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4c481-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="4c481-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4c481-106">\<system.serviceModel></span></span>  
<span data-ttu-id="4c481-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="4c481-107">\<tracking></span></span>  
<span data-ttu-id="4c481-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="4c481-108">\<profiles></span></span>  
<span data-ttu-id="4c481-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4c481-109">\<trackingProfile></span></span>  
<span data-ttu-id="4c481-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4c481-110">\<workflow></span></span>  
<span data-ttu-id="4c481-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="4c481-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c481-112">구문</span><span class="sxs-lookup"><span data-stu-id="4c481-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c481-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4c481-113">Attributes and elements</span></span>

<span data-ttu-id="4c481-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c481-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c481-115">특성</span><span class="sxs-lookup"><span data-stu-id="4c481-115">Attributes</span></span>

<span data-ttu-id="4c481-116">없음</span><span class="sxs-lookup"><span data-stu-id="4c481-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="4c481-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4c481-117">Child elements</span></span>
  
|<span data-ttu-id="4c481-118">요소</span><span class="sxs-lookup"><span data-stu-id="4c481-118">Element</span></span>|<span data-ttu-id="4c481-119">설명</span><span class="sxs-lookup"><span data-stu-id="4c481-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c481-120">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="4c481-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="4c481-121">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="4c481-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c481-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4c481-122">Parent elements</span></span>  
  
|<span data-ttu-id="4c481-123">요소</span><span class="sxs-lookup"><span data-stu-id="4c481-123">Element</span></span>|<span data-ttu-id="4c481-124">설명</span><span class="sxs-lookup"><span data-stu-id="4c481-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c481-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4c481-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="4c481-126">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4c481-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c481-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="4c481-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4c481-128">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="4c481-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4c481-129">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="4c481-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
