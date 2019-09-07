---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: ed08f5533cd6b3839775d061452cb17110cc627e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398901"
---
# <a name="argument"></a><span data-ttu-id="30543-101">\<argument></span><span class="sxs-lookup"><span data-stu-id="30543-101">\<argument></span></span>
<span data-ttu-id="30543-102">활동 상태 쿼리와 연결된 인수를 나타내는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="30543-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="30543-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30543-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="30543-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="30543-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="30543-105">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="30543-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="30543-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="30543-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="30543-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="30543-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="30543-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="30543-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="30543-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQueries >** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="30543-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="30543-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQuery >** ](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="30543-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="30543-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<인수 >** ](arguments.md)</span><span class="sxs-lookup"><span data-stu-id="30543-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<arguments>**](arguments.md)</span></span>\
<span data-ttu-id="30543-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<인수 >**</span><span class="sxs-lookup"><span data-stu-id="30543-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<argument>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30543-113">구문</span><span class="sxs-lookup"><span data-stu-id="30543-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30543-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="30543-114">Attributes and Elements</span></span>  
 <span data-ttu-id="30543-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30543-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30543-116">특성</span><span class="sxs-lookup"><span data-stu-id="30543-116">Attributes</span></span>  
  
|<span data-ttu-id="30543-117">특성</span><span class="sxs-lookup"><span data-stu-id="30543-117">Attribute</span></span>|<span data-ttu-id="30543-118">Description</span><span class="sxs-lookup"><span data-stu-id="30543-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30543-119">name</span><span class="sxs-lookup"><span data-stu-id="30543-119">name</span></span>|<span data-ttu-id="30543-120">인수의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="30543-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30543-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="30543-121">Child Elements</span></span>  
 <span data-ttu-id="30543-122">없음</span><span class="sxs-lookup"><span data-stu-id="30543-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30543-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="30543-123">Parent Elements</span></span>  
  
|<span data-ttu-id="30543-124">요소</span><span class="sxs-lookup"><span data-stu-id="30543-124">Element</span></span>|<span data-ttu-id="30543-125">Description</span><span class="sxs-lookup"><span data-stu-id="30543-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30543-126">\<arguments></span><span class="sxs-lookup"><span data-stu-id="30543-126">\<arguments></span></span>](arguments.md)|<span data-ttu-id="30543-127">이 활동 쿼리와 연결되는 인수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="30543-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30543-128">설명</span><span class="sxs-lookup"><span data-stu-id="30543-128">Remarks</span></span>  
 <span data-ttu-id="30543-129">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="30543-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="30543-130">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30543-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="30543-131">인수 >, [ \<](arguments.md) [ 상태\<>](states.md) 및 [ 상태>요소를사용하\<](states.md) 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30543-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="30543-132">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30543-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="30543-133">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로 [ \<activitystatequery >](activitystatequery.md)를 사용 하 여 추적 프로필 내에서 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="30543-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="30543-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="30543-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="30543-135">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="30543-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="30543-136">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="30543-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
