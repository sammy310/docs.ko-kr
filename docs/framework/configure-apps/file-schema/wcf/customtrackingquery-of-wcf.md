---
title: <customTrackingQuery>WCF의
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: b034727dc89b58794ec2834cb0ff39cd7e5f1dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919355"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="2d232-102">\<WCF의 customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="2d232-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="2d232-103">코드 활동에서 정의 하는 이벤트를 추적 하는 데 사용 되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d232-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="2d232-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2d232-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="2d232-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d232-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2d232-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2d232-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2d232-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2d232-107">\<tracking></span></span>  
<span data-ttu-id="2d232-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="2d232-108">\<profiles></span></span>  
<span data-ttu-id="2d232-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2d232-109">\<trackingProfile></span></span>  
<span data-ttu-id="2d232-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2d232-110">\<workflow></span></span>  
<span data-ttu-id="2d232-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="2d232-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="2d232-112">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="2d232-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d232-113">구문</span><span class="sxs-lookup"><span data-stu-id="2d232-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d232-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2d232-114">Attributes and elements</span></span>  

<span data-ttu-id="2d232-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d232-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d232-116">특성</span><span class="sxs-lookup"><span data-stu-id="2d232-116">Attributes</span></span>  
  
|<span data-ttu-id="2d232-117">특성</span><span class="sxs-lookup"><span data-stu-id="2d232-117">Attribute</span></span>|<span data-ttu-id="2d232-118">Description</span><span class="sxs-lookup"><span data-stu-id="2d232-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="2d232-119">추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2d232-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="2d232-120">내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2d232-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d232-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2d232-121">Child elements</span></span>

<span data-ttu-id="2d232-122">없음</span><span class="sxs-lookup"><span data-stu-id="2d232-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2d232-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2d232-123">Parent elements</span></span>

|<span data-ttu-id="2d232-124">요소</span><span class="sxs-lookup"><span data-stu-id="2d232-124">Element</span></span>|<span data-ttu-id="2d232-125">설명</span><span class="sxs-lookup"><span data-stu-id="2d232-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d232-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="2d232-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="2d232-127">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d232-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="2d232-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="2d232-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2d232-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="2d232-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2d232-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="2d232-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
