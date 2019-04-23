---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 663dda571990a86dc71ea927c4e97241e0ed3fc1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120083"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="84456-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="84456-101">\<customTrackingQueries></span></span>
<span data-ttu-id="84456-102">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84456-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="84456-103">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="84456-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="84456-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="84456-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="84456-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="84456-105">\<system.serviceModel></span></span>  
<span data-ttu-id="84456-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="84456-106">\<tracking></span></span>  
<span data-ttu-id="84456-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="84456-107">\<trackingProfile></span></span>  
<span data-ttu-id="84456-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="84456-108">\<workflow></span></span>  
<span data-ttu-id="84456-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="84456-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84456-110">구문</span><span class="sxs-lookup"><span data-stu-id="84456-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84456-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="84456-111">Attributes and Elements</span></span>  
 <span data-ttu-id="84456-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84456-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84456-113">특성</span><span class="sxs-lookup"><span data-stu-id="84456-113">Attributes</span></span>  
 <span data-ttu-id="84456-114">없음</span><span class="sxs-lookup"><span data-stu-id="84456-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="84456-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="84456-115">Child Elements</span></span>  
  
|<span data-ttu-id="84456-116">요소</span><span class="sxs-lookup"><span data-stu-id="84456-116">Element</span></span>|<span data-ttu-id="84456-117">설명</span><span class="sxs-lookup"><span data-stu-id="84456-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84456-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="84456-118">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="84456-119">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="84456-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="84456-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="84456-120">Parent Elements</span></span>  
  
|<span data-ttu-id="84456-121">요소</span><span class="sxs-lookup"><span data-stu-id="84456-121">Element</span></span>|<span data-ttu-id="84456-122">설명</span><span class="sxs-lookup"><span data-stu-id="84456-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84456-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="84456-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="84456-124">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소를 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="84456-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84456-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="84456-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="84456-126">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="84456-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="84456-127">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="84456-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
