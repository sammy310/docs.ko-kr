---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 695fccf88ac0d8a672e710ccc632ea58dd2fc693
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398777"
---
# <a name="customtrackingquery"></a><span data-ttu-id="8ef41-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="8ef41-101">\<customTrackingQuery></span></span>
<span data-ttu-id="8ef41-102">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ef41-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="8ef41-103">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8ef41-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="8ef41-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ef41-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8ef41-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8ef41-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8ef41-106">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8ef41-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="8ef41-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="8ef41-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="8ef41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="8ef41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="8ef41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8ef41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="8ef41-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customTrackingQueries >** ](customtrackingqueries.md)</span><span class="sxs-lookup"><span data-stu-id="8ef41-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span></span>\
<span data-ttu-id="8ef41-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customTrackingQuery >**</span><span class="sxs-lookup"><span data-stu-id="8ef41-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ef41-112">구문</span><span class="sxs-lookup"><span data-stu-id="8ef41-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ef41-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8ef41-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8ef41-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ef41-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ef41-115">특성</span><span class="sxs-lookup"><span data-stu-id="8ef41-115">Attributes</span></span>  
  
|<span data-ttu-id="8ef41-116">특성</span><span class="sxs-lookup"><span data-stu-id="8ef41-116">Attribute</span></span>|<span data-ttu-id="8ef41-117">Description</span><span class="sxs-lookup"><span data-stu-id="8ef41-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ef41-118">activityName</span><span class="sxs-lookup"><span data-stu-id="8ef41-118">activityName</span></span>|<span data-ttu-id="8ef41-119">추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8ef41-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="8ef41-120">name</span><span class="sxs-lookup"><span data-stu-id="8ef41-120">name</span></span>|<span data-ttu-id="8ef41-121">내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8ef41-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ef41-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8ef41-122">Child Elements</span></span>  
 <span data-ttu-id="8ef41-123">없음</span><span class="sxs-lookup"><span data-stu-id="8ef41-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ef41-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8ef41-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8ef41-125">요소</span><span class="sxs-lookup"><span data-stu-id="8ef41-125">Element</span></span>|<span data-ttu-id="8ef41-126">Description</span><span class="sxs-lookup"><span data-stu-id="8ef41-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ef41-127">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="8ef41-127">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="8ef41-128">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="8ef41-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ef41-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="8ef41-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8ef41-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="8ef41-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8ef41-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="8ef41-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
