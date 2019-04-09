---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: 6fe02cfea91633da41c8ebc7d8a78dd005ad3f4a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080906"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="4b98a-101">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="4b98a-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="4b98a-102">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b98a-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="4b98a-103">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4b98a-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4b98a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4b98a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4b98a-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="4b98a-105">\<tracking></span></span>  
<span data-ttu-id="4b98a-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4b98a-106">\<trackingProfile></span></span>  
<span data-ttu-id="4b98a-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4b98a-107">\<workflow></span></span>  
<span data-ttu-id="4b98a-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="4b98a-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="4b98a-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="4b98a-109">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b98a-110">구문</span><span class="sxs-lookup"><span data-stu-id="4b98a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b98a-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4b98a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4b98a-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4b98a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b98a-113">특성</span><span class="sxs-lookup"><span data-stu-id="4b98a-113">Attributes</span></span>  
 <span data-ttu-id="4b98a-114">없음</span><span class="sxs-lookup"><span data-stu-id="4b98a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4b98a-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4b98a-115">Child Elements</span></span>  
  
|<span data-ttu-id="4b98a-116">요소</span><span class="sxs-lookup"><span data-stu-id="4b98a-116">Element</span></span>|<span data-ttu-id="4b98a-117">설명</span><span class="sxs-lookup"><span data-stu-id="4b98a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b98a-118">\<states></span><span class="sxs-lookup"><span data-stu-id="4b98a-118">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="4b98a-119">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4b98a-119">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b98a-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4b98a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4b98a-121">요소</span><span class="sxs-lookup"><span data-stu-id="4b98a-121">Element</span></span>|<span data-ttu-id="4b98a-122">설명</span><span class="sxs-lookup"><span data-stu-id="4b98a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b98a-123">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="4b98a-123">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="4b98a-124">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 구성 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b98a-124">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b98a-125">설명</span><span class="sxs-lookup"><span data-stu-id="4b98a-125">Remarks</span></span>  
 <span data-ttu-id="4b98a-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery>는 다음 <xref:System.Activities.Tracking.TrackingRecord> 개체를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b98a-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="4b98a-127">예제</span><span class="sxs-lookup"><span data-stu-id="4b98a-127">Example</span></span>  
 <span data-ttu-id="4b98a-128">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="4b98a-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b98a-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="4b98a-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4b98a-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="4b98a-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4b98a-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="4b98a-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
