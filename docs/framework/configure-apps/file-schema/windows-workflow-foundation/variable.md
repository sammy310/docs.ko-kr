---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 5878720f51f4b5cfe3163abf316a867ccda31342
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397775"
---
# <a name="variable"></a><span data-ttu-id="b139e-101">\<variable></span><span class="sxs-lookup"><span data-stu-id="b139e-101">\<variable></span></span>
<span data-ttu-id="b139e-102">이 활동 쿼리와 연결된 변수의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b139e-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="b139e-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b139e-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b139e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b139e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b139e-105">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b139e-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="b139e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="b139e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="b139e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="b139e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="b139e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b139e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="b139e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQueries >** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="b139e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="b139e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQuery >** ](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="b139e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="b139e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<변수 >** ](variables.md)</span><span class="sxs-lookup"><span data-stu-id="b139e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<variables>**](variables.md)</span></span>\
<span data-ttu-id="b139e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<변수 >**</span><span class="sxs-lookup"><span data-stu-id="b139e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b139e-113">구문</span><span class="sxs-lookup"><span data-stu-id="b139e-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b139e-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b139e-114">Attributes and Elements</span></span>  
 <span data-ttu-id="b139e-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b139e-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b139e-116">특성</span><span class="sxs-lookup"><span data-stu-id="b139e-116">Attributes</span></span>  
  
|<span data-ttu-id="b139e-117">특성</span><span class="sxs-lookup"><span data-stu-id="b139e-117">Attribute</span></span>|<span data-ttu-id="b139e-118">설명</span><span class="sxs-lookup"><span data-stu-id="b139e-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b139e-119">name</span><span class="sxs-lookup"><span data-stu-id="b139e-119">name</span></span>|<span data-ttu-id="b139e-120">변수의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b139e-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b139e-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b139e-121">Child Elements</span></span>  
 <span data-ttu-id="b139e-122">없음</span><span class="sxs-lookup"><span data-stu-id="b139e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b139e-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b139e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b139e-124">요소</span><span class="sxs-lookup"><span data-stu-id="b139e-124">Element</span></span>|<span data-ttu-id="b139e-125">Description</span><span class="sxs-lookup"><span data-stu-id="b139e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b139e-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="b139e-126">\<variable></span></span>](variable.md)|<span data-ttu-id="b139e-127">활동 상태 쿼리와 연결되는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b139e-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b139e-128">설명</span><span class="sxs-lookup"><span data-stu-id="b139e-128">Remarks</span></span>  
 <span data-ttu-id="b139e-129">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b139e-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="b139e-130">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b139e-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="b139e-131">인수 >, [ \<](arguments.md) [ 상태\<>](states.md) 및 [ 상태>요소를사용하\<](states.md) 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b139e-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="b139e-132">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b139e-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="b139e-133">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로 [ \<activitystatequery >](activitystatequery.md)를 사용 하 여 추적 프로필 내에서 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="b139e-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b139e-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="b139e-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b139e-135">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="b139e-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b139e-136">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="b139e-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
