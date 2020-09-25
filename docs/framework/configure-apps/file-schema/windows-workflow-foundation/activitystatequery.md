---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: fdb173f6d16087e921fc7f2edbb30fa901545eac
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177763"
---
# \<activityStateQuery>

<span data-ttu-id="8bcf4-101">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-101">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="8bcf4-102">예를 들어, 워크플로 인스턴스 내에서 "전자 메일 보내기" 작업이 완료 될 때마다 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-102">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="8bcf4-103">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-103">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="8bcf4-104">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-104">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="8bcf4-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="8bcf4-106">구문</span><span class="sxs-lookup"><span data-stu-id="8bcf4-106">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bcf4-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8bcf4-107">Attributes and Elements</span></span>  

 <span data-ttu-id="8bcf4-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bcf4-109">특성</span><span class="sxs-lookup"><span data-stu-id="8bcf4-109">Attributes</span></span>  
  
|<span data-ttu-id="8bcf4-110">attribute</span><span class="sxs-lookup"><span data-stu-id="8bcf4-110">Attribute</span></span>|<span data-ttu-id="8bcf4-111">설명</span><span class="sxs-lookup"><span data-stu-id="8bcf4-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bcf4-112">activityName</span><span class="sxs-lookup"><span data-stu-id="8bcf4-112">activityName</span></span>|<span data-ttu-id="8bcf4-113"><xref:System.Activities.Tracking.ActivityStateRecord> 인스턴스를 필터링할 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-113">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8bcf4-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8bcf4-114">Child Elements</span></span>  
  
|<span data-ttu-id="8bcf4-115">요소</span><span class="sxs-lookup"><span data-stu-id="8bcf4-115">Element</span></span>|<span data-ttu-id="8bcf4-116">설명</span><span class="sxs-lookup"><span data-stu-id="8bcf4-116">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](arguments.md)|<span data-ttu-id="8bcf4-117">이 활동 쿼리와 연결되는 인수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-117">A collection of arguments associated with this activity query.</span></span>|  
|[\<states>](states.md)|<span data-ttu-id="8bcf4-118">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-118">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[\<states>](states.md)|<span data-ttu-id="8bcf4-119">이 활동 쿼리와 연결되는 변수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-119">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8bcf4-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8bcf4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8bcf4-121">요소</span><span class="sxs-lookup"><span data-stu-id="8bcf4-121">Element</span></span>|<span data-ttu-id="8bcf4-122">설명</span><span class="sxs-lookup"><span data-stu-id="8bcf4-122">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="8bcf4-123">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-123">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8bcf4-124">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-124">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bcf4-125">설명</span><span class="sxs-lookup"><span data-stu-id="8bcf4-125">Remarks</span></span>  

 <span data-ttu-id="8bcf4-126">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-126">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="8bcf4-127">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-127">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="8bcf4-128">[\<arguments>](arguments.md), 및 요소를 사용 [\<states>](states.md) [\<states>](states.md) 하 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-128">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="8bcf4-129">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-129">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="8bcf4-130">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로를 사용 하 여 추적 프로필 내에서 구독 [\<activityStateQuery>](activitystatequery.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bcf4-130">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8bcf4-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bcf4-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8bcf4-132">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="8bcf4-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8bcf4-133">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="8bcf4-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
