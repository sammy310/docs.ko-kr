---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 61a786efc67f4e9afa585864e1f62b966b5cdff8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105380"
---
# <a name="variables"></a><span data-ttu-id="4e8ac-101">\<variables></span><span class="sxs-lookup"><span data-stu-id="4e8ac-101">\<variables></span></span>
<span data-ttu-id="4e8ac-102">이 활동 쿼리와 연결된 변수의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4e8ac-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="4e8ac-103">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8ac-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="4e8ac-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4e8ac-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4e8ac-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="4e8ac-105">\<tracking></span></span>  
<span data-ttu-id="4e8ac-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4e8ac-106">\<trackingProfile></span></span>  
<span data-ttu-id="4e8ac-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4e8ac-107">\<workflow></span></span>  
<span data-ttu-id="4e8ac-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="4e8ac-108">\<activityStateQueries></span></span>  
<span data-ttu-id="4e8ac-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="4e8ac-109">\<activityStateQuery></span></span>  
<span data-ttu-id="4e8ac-110">\<variables></span><span class="sxs-lookup"><span data-stu-id="4e8ac-110">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e8ac-111">구문</span><span class="sxs-lookup"><span data-stu-id="4e8ac-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e8ac-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4e8ac-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4e8ac-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8ac-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e8ac-114">특성</span><span class="sxs-lookup"><span data-stu-id="4e8ac-114">Attributes</span></span>  
 <span data-ttu-id="4e8ac-115">없음</span><span class="sxs-lookup"><span data-stu-id="4e8ac-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4e8ac-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4e8ac-116">Child Elements</span></span>  
  
|<span data-ttu-id="4e8ac-117">요소</span><span class="sxs-lookup"><span data-stu-id="4e8ac-117">Element</span></span>|<span data-ttu-id="4e8ac-118">설명</span><span class="sxs-lookup"><span data-stu-id="4e8ac-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e8ac-119">\<variable></span><span class="sxs-lookup"><span data-stu-id="4e8ac-119">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="4e8ac-120">활동 상태 쿼리와 연결되는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e8ac-120">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e8ac-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4e8ac-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4e8ac-122">요소</span><span class="sxs-lookup"><span data-stu-id="4e8ac-122">Element</span></span>|<span data-ttu-id="4e8ac-123">설명</span><span class="sxs-lookup"><span data-stu-id="4e8ac-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e8ac-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="4e8ac-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="4e8ac-125">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4e8ac-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="4e8ac-126">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8ac-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e8ac-127">설명</span><span class="sxs-lookup"><span data-stu-id="4e8ac-127">Remarks</span></span>  
 <span data-ttu-id="4e8ac-128">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="4e8ac-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="4e8ac-129">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8ac-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="4e8ac-130">사용할 수는 [ \<인수 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)를 [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 고 [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 변수 또는 인수를 추출 하는 요소 워크플로의 모든 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="4e8ac-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="4e8ac-131">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e8ac-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="4e8ac-132">ActivityStateRecord 사용해 서만 추출할 수 있으므로 구독 하는 추적 내에서 변수 및 인수를 사용 하 여 프로 파일링 [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8ac-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4e8ac-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="4e8ac-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4e8ac-134">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="4e8ac-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4e8ac-135">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="4e8ac-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
