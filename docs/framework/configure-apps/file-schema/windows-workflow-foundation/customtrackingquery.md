---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 92060260075017359d8a5f0500d52e52c2217d3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790184"
---
# <a name="customtrackingquery"></a><span data-ttu-id="ac568-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="ac568-101">\<customTrackingQuery></span></span>
<span data-ttu-id="ac568-102">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ac568-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="ac568-103">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ac568-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="ac568-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ac568-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ac568-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ac568-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ac568-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ac568-106">\<tracking></span></span>  
<span data-ttu-id="ac568-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ac568-107">\<trackingProfile></span></span>  
<span data-ttu-id="ac568-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ac568-108">\<workflow></span></span>  
<span data-ttu-id="ac568-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="ac568-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="ac568-110">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="ac568-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac568-111">구문</span><span class="sxs-lookup"><span data-stu-id="ac568-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac568-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ac568-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ac568-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac568-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac568-114">특성</span><span class="sxs-lookup"><span data-stu-id="ac568-114">Attributes</span></span>  
  
|<span data-ttu-id="ac568-115">특성</span><span class="sxs-lookup"><span data-stu-id="ac568-115">Attribute</span></span>|<span data-ttu-id="ac568-116">설명</span><span class="sxs-lookup"><span data-stu-id="ac568-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac568-117">activityName</span><span class="sxs-lookup"><span data-stu-id="ac568-117">activityName</span></span>|<span data-ttu-id="ac568-118">추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ac568-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="ac568-119">name</span><span class="sxs-lookup"><span data-stu-id="ac568-119">name</span></span>|<span data-ttu-id="ac568-120">내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ac568-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac568-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ac568-121">Child Elements</span></span>  
 <span data-ttu-id="ac568-122">없음</span><span class="sxs-lookup"><span data-stu-id="ac568-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac568-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ac568-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ac568-124">요소</span><span class="sxs-lookup"><span data-stu-id="ac568-124">Element</span></span>|<span data-ttu-id="ac568-125">설명</span><span class="sxs-lookup"><span data-stu-id="ac568-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac568-126">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="ac568-126">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="ac568-127">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="ac568-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac568-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac568-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ac568-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="ac568-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ac568-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="ac568-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
