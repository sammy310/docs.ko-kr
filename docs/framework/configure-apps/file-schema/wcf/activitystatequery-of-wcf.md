---
description: '다음에 대 한 자세한 정보: <activityStateQuery> WCF'
title: <activityStateQuery> WCF의
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: fff8f6ac793df9b0a355dfbed859b3a88178002a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725924"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="d4d68-103">\<activityStateQuery> WCF의</span><span class="sxs-lookup"><span data-stu-id="d4d68-103">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="d4d68-104">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-104">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="d4d68-105">예를 들어, 워크플로 인스턴스 내에서 "전자 메일 보내기" 작업이 완료 될 때마다 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-105">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="d4d68-106">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-106">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="d4d68-107">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-107">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="d4d68-108">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4d68-108">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="d4d68-109">구문</span><span class="sxs-lookup"><span data-stu-id="d4d68-109">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4d68-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d4d68-110">Attributes and elements</span></span>  

<span data-ttu-id="d4d68-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4d68-112">특성</span><span class="sxs-lookup"><span data-stu-id="d4d68-112">Attributes</span></span>  
  
|<span data-ttu-id="d4d68-113">attribute</span><span class="sxs-lookup"><span data-stu-id="d4d68-113">Attribute</span></span>|<span data-ttu-id="d4d68-114">설명</span><span class="sxs-lookup"><span data-stu-id="d4d68-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4d68-115">activityName</span><span class="sxs-lookup"><span data-stu-id="d4d68-115">activityName</span></span>|<span data-ttu-id="d4d68-116"><xref:System.Activities.Tracking.ActivityStateRecord> 인스턴스를 필터링할 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-116">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4d68-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d4d68-117">Child elements</span></span>  
  
|<span data-ttu-id="d4d68-118">요소</span><span class="sxs-lookup"><span data-stu-id="d4d68-118">Element</span></span>|<span data-ttu-id="d4d68-119">설명</span><span class="sxs-lookup"><span data-stu-id="d4d68-119">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="d4d68-120">이 활동 쿼리와 연결되는 인수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-120">A collection of arguments associated with this activity query.</span></span>|  
|[\<states>](../windows-workflow-foundation/states.md)|<span data-ttu-id="d4d68-121">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-121">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[\<states>](../windows-workflow-foundation/states.md)|<span data-ttu-id="d4d68-122">이 활동 쿼리와 연결되는 변수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-122">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4d68-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d4d68-123">Parent elements</span></span>  
  
|<span data-ttu-id="d4d68-124">요소</span><span class="sxs-lookup"><span data-stu-id="d4d68-124">Element</span></span>|<span data-ttu-id="d4d68-125">설명</span><span class="sxs-lookup"><span data-stu-id="d4d68-125">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="d4d68-126">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-126">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d4d68-127">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4d68-128">설명</span><span class="sxs-lookup"><span data-stu-id="d4d68-128">Remarks</span></span>

<span data-ttu-id="d4d68-129">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="d4d68-130">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="d4d68-131">[\<arguments>](../windows-workflow-foundation/arguments.md), 및 요소를 사용 [\<states>](../windows-workflow-foundation/states.md) [\<states>](../windows-workflow-foundation/states.md) 하 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-131">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="d4d68-132">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="d4d68-133">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로를 사용 하 여 추적 프로필 내에서 구독 [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d68-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a><span data-ttu-id="d4d68-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4d68-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="d4d68-135">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="d4d68-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d4d68-136">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d4d68-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
