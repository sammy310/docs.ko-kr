---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 0a32e6ee22cdf984e64c1b8fa16836c4c56d0380
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932733"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="e35bd-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="e35bd-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="e35bd-102">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 구성 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e35bd-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="e35bd-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e35bd-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e35bd-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e35bd-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e35bd-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="e35bd-105">\<tracking></span></span>  
<span data-ttu-id="e35bd-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e35bd-106">\<trackingProfile></span></span>  
<span data-ttu-id="e35bd-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="e35bd-107">\<workflow></span></span>  
<span data-ttu-id="e35bd-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="e35bd-108">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e35bd-109">구문</span><span class="sxs-lookup"><span data-stu-id="e35bd-109">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e35bd-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e35bd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e35bd-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e35bd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e35bd-112">특성</span><span class="sxs-lookup"><span data-stu-id="e35bd-112">Attributes</span></span>  
 <span data-ttu-id="e35bd-113">없음</span><span class="sxs-lookup"><span data-stu-id="e35bd-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e35bd-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e35bd-114">Child Elements</span></span>  
  
|<span data-ttu-id="e35bd-115">요소</span><span class="sxs-lookup"><span data-stu-id="e35bd-115">Element</span></span>|<span data-ttu-id="e35bd-116">Description</span><span class="sxs-lookup"><span data-stu-id="e35bd-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e35bd-117">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="e35bd-117">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="e35bd-118">워크플로 인스턴스 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="e35bd-118">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e35bd-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e35bd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e35bd-120">요소</span><span class="sxs-lookup"><span data-stu-id="e35bd-120">Element</span></span>|<span data-ttu-id="e35bd-121">Description</span><span class="sxs-lookup"><span data-stu-id="e35bd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e35bd-122">\<workflow></span><span class="sxs-lookup"><span data-stu-id="e35bd-122">\<workflow></span></span>](workflow.md)|<span data-ttu-id="e35bd-123">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e35bd-123">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e35bd-124">설명</span><span class="sxs-lookup"><span data-stu-id="e35bd-124">Remarks</span></span>  
 <span data-ttu-id="e35bd-125"><xref:System.Activities.Tracking.WorkflowInstanceQuery>는 다음 <xref:System.Activities.Tracking.TrackingRecord> 개체를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e35bd-125">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="e35bd-126">예제</span><span class="sxs-lookup"><span data-stu-id="e35bd-126">Example</span></span>  
 <span data-ttu-id="e35bd-127">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="e35bd-127">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e35bd-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="e35bd-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e35bd-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="e35bd-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e35bd-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="e35bd-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
