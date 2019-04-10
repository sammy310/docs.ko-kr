---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: a920d60d703fe262bee96d75c420c526d54f88ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210648"
---
# <a name="argument"></a><span data-ttu-id="fc83c-101">\<argument></span><span class="sxs-lookup"><span data-stu-id="fc83c-101">\<argument></span></span>
<span data-ttu-id="fc83c-102">활동 상태 쿼리와 연결된 인수를 나타내는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fc83c-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="fc83c-103">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc83c-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="fc83c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fc83c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="fc83c-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="fc83c-105">\<tracking></span></span>  
<span data-ttu-id="fc83c-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="fc83c-106">\<trackingProfile></span></span>  
<span data-ttu-id="fc83c-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="fc83c-107">\<workflow></span></span>  
<span data-ttu-id="fc83c-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="fc83c-108">\<activityStateQueries></span></span>  
<span data-ttu-id="fc83c-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="fc83c-109">\<activityStateQuery></span></span>  
<span data-ttu-id="fc83c-110">\<arguments></span><span class="sxs-lookup"><span data-stu-id="fc83c-110">\<arguments></span></span>  
<span data-ttu-id="fc83c-111">\<argument></span><span class="sxs-lookup"><span data-stu-id="fc83c-111">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc83c-112">구문</span><span class="sxs-lookup"><span data-stu-id="fc83c-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc83c-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fc83c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="fc83c-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fc83c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc83c-115">특성</span><span class="sxs-lookup"><span data-stu-id="fc83c-115">Attributes</span></span>  
  
|<span data-ttu-id="fc83c-116">특성</span><span class="sxs-lookup"><span data-stu-id="fc83c-116">Attribute</span></span>|<span data-ttu-id="fc83c-117">설명</span><span class="sxs-lookup"><span data-stu-id="fc83c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc83c-118">name</span><span class="sxs-lookup"><span data-stu-id="fc83c-118">name</span></span>|<span data-ttu-id="fc83c-119">인수의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fc83c-119">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc83c-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fc83c-120">Child Elements</span></span>  
 <span data-ttu-id="fc83c-121">없음</span><span class="sxs-lookup"><span data-stu-id="fc83c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc83c-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fc83c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="fc83c-123">요소</span><span class="sxs-lookup"><span data-stu-id="fc83c-123">Element</span></span>|<span data-ttu-id="fc83c-124">설명</span><span class="sxs-lookup"><span data-stu-id="fc83c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc83c-125">\<arguments></span><span class="sxs-lookup"><span data-stu-id="fc83c-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="fc83c-126">이 활동 쿼리와 연결되는 인수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="fc83c-126">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc83c-127">설명</span><span class="sxs-lookup"><span data-stu-id="fc83c-127">Remarks</span></span>  
 <span data-ttu-id="fc83c-128">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fc83c-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="fc83c-129">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc83c-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="fc83c-130">사용할 수는 [ \<인수 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)를 [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 고 [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 변수 또는 인수를 추출 하는 요소 워크플로의 모든 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="fc83c-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="fc83c-131">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc83c-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="fc83c-132">ActivityStateRecord 사용해 서만 추출할 수 있으므로 구독 하는 추적 내에서 변수 및 인수를 사용 하 여 프로 파일링 [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc83c-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc83c-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="fc83c-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fc83c-134">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="fc83c-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fc83c-135">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="fc83c-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
