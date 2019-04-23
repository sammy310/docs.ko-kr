---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: e54f98c980f60d02377e38d53d9d0eb48581eec0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132485"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="d5bf8-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="d5bf8-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="d5bf8-102">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 구성 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf8-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="d5bf8-103">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d5bf8-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d5bf8-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d5bf8-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d5bf8-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d5bf8-105">\<tracking></span></span>  
<span data-ttu-id="d5bf8-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d5bf8-106">\<trackingProfile></span></span>  
<span data-ttu-id="d5bf8-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d5bf8-107">\<workflow></span></span>  
<span data-ttu-id="d5bf8-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="d5bf8-108">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5bf8-109">구문</span><span class="sxs-lookup"><span data-stu-id="d5bf8-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5bf8-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d5bf8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d5bf8-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5bf8-112">특성</span><span class="sxs-lookup"><span data-stu-id="d5bf8-112">Attributes</span></span>  
 <span data-ttu-id="d5bf8-113">없음</span><span class="sxs-lookup"><span data-stu-id="d5bf8-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d5bf8-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d5bf8-114">Child Elements</span></span>  
  
|<span data-ttu-id="d5bf8-115">요소</span><span class="sxs-lookup"><span data-stu-id="d5bf8-115">Element</span></span>|<span data-ttu-id="d5bf8-116">설명</span><span class="sxs-lookup"><span data-stu-id="d5bf8-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5bf8-117">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="d5bf8-117">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="d5bf8-118">워크플로 인스턴스 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf8-118">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5bf8-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d5bf8-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d5bf8-120">요소</span><span class="sxs-lookup"><span data-stu-id="d5bf8-120">Element</span></span>|<span data-ttu-id="d5bf8-121">설명</span><span class="sxs-lookup"><span data-stu-id="d5bf8-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5bf8-122">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d5bf8-122">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="d5bf8-123">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소를 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf8-123">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5bf8-124">설명</span><span class="sxs-lookup"><span data-stu-id="d5bf8-124">Remarks</span></span>  
 <span data-ttu-id="d5bf8-125"><xref:System.Activities.Tracking.WorkflowInstanceQuery>는 다음 <xref:System.Activities.Tracking.TrackingRecord> 개체를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf8-125">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="d5bf8-126">예제</span><span class="sxs-lookup"><span data-stu-id="d5bf8-126">Example</span></span>  
 <span data-ttu-id="d5bf8-127">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf8-127">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5bf8-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5bf8-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d5bf8-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="d5bf8-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d5bf8-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d5bf8-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
