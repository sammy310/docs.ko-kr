---
title: <customTrackingQuery> WCF의
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 0a5e7c034ce1ef12a8d7d5b1753e2e441e48e293
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673175"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="36a8b-102">\<customTrackingQuery> of WCF</span><span class="sxs-lookup"><span data-stu-id="36a8b-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="36a8b-103">코드 활동에서 정의 하는 이벤트를 추적 하는 데 사용 되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36a8b-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="36a8b-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="36a8b-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="36a8b-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="36a8b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="36a8b-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="36a8b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="36a8b-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="36a8b-107">\<tracking></span></span>  
<span data-ttu-id="36a8b-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="36a8b-108">\<profiles></span></span>  
<span data-ttu-id="36a8b-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="36a8b-109">\<trackingProfile></span></span>  
<span data-ttu-id="36a8b-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="36a8b-110">\<workflow></span></span>  
<span data-ttu-id="36a8b-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="36a8b-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="36a8b-112">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="36a8b-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36a8b-113">구문</span><span class="sxs-lookup"><span data-stu-id="36a8b-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36a8b-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="36a8b-114">Attributes and elements</span></span>  

<span data-ttu-id="36a8b-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="36a8b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36a8b-116">특성</span><span class="sxs-lookup"><span data-stu-id="36a8b-116">Attributes</span></span>  
  
|<span data-ttu-id="36a8b-117">특성</span><span class="sxs-lookup"><span data-stu-id="36a8b-117">Attribute</span></span>|<span data-ttu-id="36a8b-118">설명</span><span class="sxs-lookup"><span data-stu-id="36a8b-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="36a8b-119">추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="36a8b-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="36a8b-120">내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="36a8b-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36a8b-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="36a8b-121">Child elements</span></span>

<span data-ttu-id="36a8b-122">없음</span><span class="sxs-lookup"><span data-stu-id="36a8b-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="36a8b-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="36a8b-123">Parent elements</span></span>

|<span data-ttu-id="36a8b-124">요소</span><span class="sxs-lookup"><span data-stu-id="36a8b-124">Element</span></span>|<span data-ttu-id="36a8b-125">설명</span><span class="sxs-lookup"><span data-stu-id="36a8b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36a8b-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="36a8b-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="36a8b-127">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36a8b-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="36a8b-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="36a8b-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="36a8b-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="36a8b-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="36a8b-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="36a8b-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
