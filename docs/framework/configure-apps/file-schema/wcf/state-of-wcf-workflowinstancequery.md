---
title: <state>WCF의<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 99387a8f60e96beb2ec7706d9abf4bb6ae84b868
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938217"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="104b2-102">\<WCF, \<workflowInstanceQuery >의 상태 ></span><span class="sxs-lookup"><span data-stu-id="104b2-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="104b2-103">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="104b2-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="104b2-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="104b2-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="104b2-105">\<system.serviceModel></span></span>  
<span data-ttu-id="104b2-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="104b2-106">\<tracking></span></span>  
<span data-ttu-id="104b2-107">\<profiles></span><span class="sxs-lookup"><span data-stu-id="104b2-107">\<profiles></span></span>  
<span data-ttu-id="104b2-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="104b2-108">\<trackingProfile></span></span>  
<span data-ttu-id="104b2-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="104b2-109">\<workflow></span></span>  
<span data-ttu-id="104b2-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="104b2-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="104b2-111">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="104b2-111">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="104b2-112">\<states></span><span class="sxs-lookup"><span data-stu-id="104b2-112">\<states></span></span>  
<span data-ttu-id="104b2-113">\<state></span><span class="sxs-lookup"><span data-stu-id="104b2-113">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="104b2-114">구문</span><span class="sxs-lookup"><span data-stu-id="104b2-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="104b2-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="104b2-115">Attributes and elements</span></span>

<span data-ttu-id="104b2-116">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="104b2-117">특성</span><span class="sxs-lookup"><span data-stu-id="104b2-117">Attributes</span></span>

|<span data-ttu-id="104b2-118">특성</span><span class="sxs-lookup"><span data-stu-id="104b2-118">Attribute</span></span>|<span data-ttu-id="104b2-119">설명</span><span class="sxs-lookup"><span data-stu-id="104b2-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="104b2-120">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="104b2-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="104b2-121">Child elements</span></span>

<span data-ttu-id="104b2-122">없음</span><span class="sxs-lookup"><span data-stu-id="104b2-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="104b2-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="104b2-123">Parent elements</span></span>

|<span data-ttu-id="104b2-124">요소</span><span class="sxs-lookup"><span data-stu-id="104b2-124">Element</span></span>|<span data-ttu-id="104b2-125">Description</span><span class="sxs-lookup"><span data-stu-id="104b2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="104b2-126">\<states></span><span class="sxs-lookup"><span data-stu-id="104b2-126">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="104b2-127">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="104b2-128">설명</span><span class="sxs-lookup"><span data-stu-id="104b2-128">Remarks</span></span>  

<span data-ttu-id="104b2-129">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-129">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="104b2-130">가능한 상태 값은 다음 표에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-130">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="104b2-131">State</span><span class="sxs-lookup"><span data-stu-id="104b2-131">State</span></span>|<span data-ttu-id="104b2-132">설명</span><span class="sxs-lookup"><span data-stu-id="104b2-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="104b2-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="104b2-133">Aborted</span></span>|<span data-ttu-id="104b2-134">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="104b2-135">Completed</span><span class="sxs-lookup"><span data-stu-id="104b2-135">Completed</span></span>|<span data-ttu-id="104b2-136">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="104b2-137">삭제됨</span><span class="sxs-lookup"><span data-stu-id="104b2-137">Deleted</span></span>|<span data-ttu-id="104b2-138">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="104b2-139">Idle</span><span class="sxs-lookup"><span data-stu-id="104b2-139">Idle</span></span>|<span data-ttu-id="104b2-140">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="104b2-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="104b2-141">Persisted</span></span>|<span data-ttu-id="104b2-142">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="104b2-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="104b2-143">Resumed</span></span>|<span data-ttu-id="104b2-144">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="104b2-145">Started</span><span class="sxs-lookup"><span data-stu-id="104b2-145">Started</span></span>|<span data-ttu-id="104b2-146">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="104b2-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="104b2-147">UnhandledException</span></span>|<span data-ttu-id="104b2-148">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="104b2-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="104b2-149">Unloaded</span></span>|<span data-ttu-id="104b2-150">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="104b2-151">Canceled</span><span class="sxs-lookup"><span data-stu-id="104b2-151">Canceled</span></span>|<span data-ttu-id="104b2-152">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="104b2-153">Suspended</span><span class="sxs-lookup"><span data-stu-id="104b2-153">Suspended</span></span>|<span data-ttu-id="104b2-154">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="104b2-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="104b2-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="104b2-155">Terminated</span></span>|<span data-ttu-id="104b2-156">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="104b2-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="104b2-157">Unsuspended</span></span>|<span data-ttu-id="104b2-158">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="104b2-159">예제</span><span class="sxs-lookup"><span data-stu-id="104b2-159">Example</span></span>

<span data-ttu-id="104b2-160">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="104b2-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="104b2-161">참고자료</span><span class="sxs-lookup"><span data-stu-id="104b2-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="104b2-162">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="104b2-162">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="104b2-163">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="104b2-163">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
