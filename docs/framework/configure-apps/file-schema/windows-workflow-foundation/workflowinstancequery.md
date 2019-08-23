---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: f0a3c3a27b40000432b40b7008f81251fe771ca2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913135"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="aa7fe-101">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="aa7fe-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="aa7fe-102">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa7fe-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="aa7fe-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa7fe-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="aa7fe-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="aa7fe-104">\<system.serviceModel></span></span>  
<span data-ttu-id="aa7fe-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="aa7fe-105">\<tracking></span></span>  
<span data-ttu-id="aa7fe-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="aa7fe-106">\<trackingProfile></span></span>  
<span data-ttu-id="aa7fe-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="aa7fe-107">\<workflow></span></span>  
<span data-ttu-id="aa7fe-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="aa7fe-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="aa7fe-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="aa7fe-109">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa7fe-110">구문</span><span class="sxs-lookup"><span data-stu-id="aa7fe-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa7fe-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="aa7fe-111">Attributes and Elements</span></span>  
 <span data-ttu-id="aa7fe-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7fe-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa7fe-113">특성</span><span class="sxs-lookup"><span data-stu-id="aa7fe-113">Attributes</span></span>  
 <span data-ttu-id="aa7fe-114">없음</span><span class="sxs-lookup"><span data-stu-id="aa7fe-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aa7fe-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="aa7fe-115">Child Elements</span></span>  
  
|<span data-ttu-id="aa7fe-116">요소</span><span class="sxs-lookup"><span data-stu-id="aa7fe-116">Element</span></span>|<span data-ttu-id="aa7fe-117">설명</span><span class="sxs-lookup"><span data-stu-id="aa7fe-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa7fe-118">\<states></span><span class="sxs-lookup"><span data-stu-id="aa7fe-118">\<states></span></span>](states.md)|<span data-ttu-id="aa7fe-119">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="aa7fe-119">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa7fe-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="aa7fe-120">Parent Elements</span></span>  
  
|<span data-ttu-id="aa7fe-121">요소</span><span class="sxs-lookup"><span data-stu-id="aa7fe-121">Element</span></span>|<span data-ttu-id="aa7fe-122">Description</span><span class="sxs-lookup"><span data-stu-id="aa7fe-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa7fe-123">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="aa7fe-123">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="aa7fe-124">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 구성 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa7fe-124">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa7fe-125">설명</span><span class="sxs-lookup"><span data-stu-id="aa7fe-125">Remarks</span></span>  
 <span data-ttu-id="aa7fe-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery>는 다음 <xref:System.Activities.Tracking.TrackingRecord> 개체를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa7fe-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="aa7fe-127">예제</span><span class="sxs-lookup"><span data-stu-id="aa7fe-127">Example</span></span>  
 <span data-ttu-id="aa7fe-128">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7fe-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa7fe-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa7fe-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="aa7fe-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="aa7fe-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="aa7fe-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="aa7fe-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
