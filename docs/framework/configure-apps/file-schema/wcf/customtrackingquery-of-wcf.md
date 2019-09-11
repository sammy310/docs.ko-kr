---
title: <customTrackingQuery>WCF의
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855425"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="44b8e-102">\<WCF의 customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="44b8e-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="44b8e-103">코드 활동에서 정의 하는 이벤트를 추적 하는 데 사용 되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44b8e-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="44b8e-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="44b8e-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="44b8e-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44b8e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="44b8e-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="44b8e-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="44b8e-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="44b8e-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="44b8e-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="44b8e-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="44b8e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="44b8e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="44b8e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="44b8e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="44b8e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="44b8e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="44b8e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customTrackingQueries >** ](customtrackingqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="44b8e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)</span></span>\
<span data-ttu-id="44b8e-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customTrackingQuery >**</span><span class="sxs-lookup"><span data-stu-id="44b8e-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44b8e-114">구문</span><span class="sxs-lookup"><span data-stu-id="44b8e-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44b8e-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="44b8e-115">Attributes and elements</span></span>  

<span data-ttu-id="44b8e-116">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="44b8e-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44b8e-117">특성</span><span class="sxs-lookup"><span data-stu-id="44b8e-117">Attributes</span></span>  
  
|<span data-ttu-id="44b8e-118">특성</span><span class="sxs-lookup"><span data-stu-id="44b8e-118">Attribute</span></span>|<span data-ttu-id="44b8e-119">설명</span><span class="sxs-lookup"><span data-stu-id="44b8e-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="44b8e-120">추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="44b8e-120">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="44b8e-121">내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="44b8e-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44b8e-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="44b8e-122">Child elements</span></span>

<span data-ttu-id="44b8e-123">없음</span><span class="sxs-lookup"><span data-stu-id="44b8e-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="44b8e-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="44b8e-124">Parent elements</span></span>

|<span data-ttu-id="44b8e-125">요소</span><span class="sxs-lookup"><span data-stu-id="44b8e-125">Element</span></span>|<span data-ttu-id="44b8e-126">Description</span><span class="sxs-lookup"><span data-stu-id="44b8e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44b8e-127">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="44b8e-127">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="44b8e-128">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44b8e-128">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="44b8e-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="44b8e-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="44b8e-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="44b8e-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="44b8e-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="44b8e-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
