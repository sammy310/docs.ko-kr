---
title: <states>WCF의<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: ef4ce4b6fa6e60ead10b196b10a7c1489e15ac25
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938974"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="26470-102">\<WCF, \<workflowInstanceQuery의 > 상태 ></span><span class="sxs-lookup"><span data-stu-id="26470-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="26470-103">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26470-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="26470-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26470-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="26470-105">\<system.serviceModel> \<tracking></span><span class="sxs-lookup"><span data-stu-id="26470-105">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="26470-106">\<profiles></span><span class="sxs-lookup"><span data-stu-id="26470-106">\<profiles></span></span>  
<span data-ttu-id="26470-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="26470-107">\<trackingProfile></span></span>  
<span data-ttu-id="26470-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="26470-108">\<workflow></span></span>  
<span data-ttu-id="26470-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="26470-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="26470-110">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="26470-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="26470-111">\<states></span><span class="sxs-lookup"><span data-stu-id="26470-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26470-112">구문</span><span class="sxs-lookup"><span data-stu-id="26470-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26470-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="26470-113">Attributes and elements</span></span>

<span data-ttu-id="26470-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26470-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26470-115">특성</span><span class="sxs-lookup"><span data-stu-id="26470-115">Attributes</span></span>  

<span data-ttu-id="26470-116">없음</span><span class="sxs-lookup"><span data-stu-id="26470-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="26470-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="26470-117">Child elements</span></span>
  
|<span data-ttu-id="26470-118">요소</span><span class="sxs-lookup"><span data-stu-id="26470-118">Element</span></span>|<span data-ttu-id="26470-119">Description</span><span class="sxs-lookup"><span data-stu-id="26470-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26470-120">\<states></span><span class="sxs-lookup"><span data-stu-id="26470-120">\<states></span></span>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="26470-121">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="26470-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="26470-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="26470-122">Parent elements</span></span>  
  
|<span data-ttu-id="26470-123">요소</span><span class="sxs-lookup"><span data-stu-id="26470-123">Element</span></span>|<span data-ttu-id="26470-124">Description</span><span class="sxs-lookup"><span data-stu-id="26470-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26470-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="26470-125">\<workflowInstanceQuery></span></span>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="26470-126">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="26470-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26470-127">설명</span><span class="sxs-lookup"><span data-stu-id="26470-127">Remarks</span></span>

<span data-ttu-id="26470-128">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="26470-128">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="26470-129">가능한 상태 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26470-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="26470-130">상태</span><span class="sxs-lookup"><span data-stu-id="26470-130">State</span></span>|<span data-ttu-id="26470-131">설명</span><span class="sxs-lookup"><span data-stu-id="26470-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="26470-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="26470-132">Aborted</span></span>|<span data-ttu-id="26470-133">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26470-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="26470-134">Completed</span><span class="sxs-lookup"><span data-stu-id="26470-134">Completed</span></span>|<span data-ttu-id="26470-135">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26470-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="26470-136">삭제됨</span><span class="sxs-lookup"><span data-stu-id="26470-136">Deleted</span></span>|<span data-ttu-id="26470-137">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26470-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="26470-138">Idle</span><span class="sxs-lookup"><span data-stu-id="26470-138">Idle</span></span>|<span data-ttu-id="26470-139">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="26470-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="26470-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="26470-140">Persisted</span></span>|<span data-ttu-id="26470-141">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26470-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="26470-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="26470-142">Resumed</span></span>|<span data-ttu-id="26470-143">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26470-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="26470-144">Started</span><span class="sxs-lookup"><span data-stu-id="26470-144">Started</span></span>|<span data-ttu-id="26470-145">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26470-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="26470-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="26470-146">UnhandledException</span></span>|<span data-ttu-id="26470-147">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="26470-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="26470-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="26470-148">Unloaded</span></span>|<span data-ttu-id="26470-149">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26470-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="26470-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="26470-150">Canceled</span></span>|<span data-ttu-id="26470-151">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26470-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="26470-152">Suspended</span><span class="sxs-lookup"><span data-stu-id="26470-152">Suspended</span></span>|<span data-ttu-id="26470-153">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="26470-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="26470-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="26470-154">Terminated</span></span>|<span data-ttu-id="26470-155">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="26470-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="26470-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="26470-156">Unsuspended</span></span>|<span data-ttu-id="26470-157">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="26470-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="26470-158">예제</span><span class="sxs-lookup"><span data-stu-id="26470-158">Example</span></span>

<span data-ttu-id="26470-159">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="26470-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="26470-160">참고자료</span><span class="sxs-lookup"><span data-stu-id="26470-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="26470-161">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="26470-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="26470-162">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="26470-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
