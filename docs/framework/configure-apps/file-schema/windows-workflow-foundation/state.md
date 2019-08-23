---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 9ffe9f9f69f68b6f47cbc3a75200b2867aae2384
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947447"
---
# <a name="state"></a><span data-ttu-id="b809b-101">\<state></span><span class="sxs-lookup"><span data-stu-id="b809b-101">\<state></span></span>
<span data-ttu-id="b809b-102">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="b809b-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b809b-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b809b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b809b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b809b-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="b809b-105">\<tracking></span></span>  
<span data-ttu-id="b809b-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b809b-106">\<trackingProfile></span></span>  
<span data-ttu-id="b809b-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b809b-107">\<workflow></span></span>  
<span data-ttu-id="b809b-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="b809b-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="b809b-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="b809b-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="b809b-110">\<states></span><span class="sxs-lookup"><span data-stu-id="b809b-110">\<states></span></span>  
<span data-ttu-id="b809b-111">\<state></span><span class="sxs-lookup"><span data-stu-id="b809b-111">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b809b-112">구문</span><span class="sxs-lookup"><span data-stu-id="b809b-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b809b-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b809b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b809b-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b809b-115">특성</span><span class="sxs-lookup"><span data-stu-id="b809b-115">Attributes</span></span>  
  
|<span data-ttu-id="b809b-116">특성</span><span class="sxs-lookup"><span data-stu-id="b809b-116">Attribute</span></span>|<span data-ttu-id="b809b-117">Description</span><span class="sxs-lookup"><span data-stu-id="b809b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b809b-118">name</span><span class="sxs-lookup"><span data-stu-id="b809b-118">name</span></span>|<span data-ttu-id="b809b-119">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-119">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b809b-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b809b-120">Child Elements</span></span>  
 <span data-ttu-id="b809b-121">없음</span><span class="sxs-lookup"><span data-stu-id="b809b-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b809b-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b809b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b809b-123">요소</span><span class="sxs-lookup"><span data-stu-id="b809b-123">Element</span></span>|<span data-ttu-id="b809b-124">설명</span><span class="sxs-lookup"><span data-stu-id="b809b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b809b-125">\<states></span><span class="sxs-lookup"><span data-stu-id="b809b-125">\<states></span></span>](states.md)|<span data-ttu-id="b809b-126">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-126">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b809b-127">설명</span><span class="sxs-lookup"><span data-stu-id="b809b-127">Remarks</span></span>  
 <span data-ttu-id="b809b-128">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="b809b-129">가능한 상태 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="b809b-130">상태</span><span class="sxs-lookup"><span data-stu-id="b809b-130">State</span></span>|<span data-ttu-id="b809b-131">설명</span><span class="sxs-lookup"><span data-stu-id="b809b-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b809b-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="b809b-132">Aborted</span></span>|<span data-ttu-id="b809b-133">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="b809b-134">Completed</span><span class="sxs-lookup"><span data-stu-id="b809b-134">Completed</span></span>|<span data-ttu-id="b809b-135">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="b809b-136">삭제됨</span><span class="sxs-lookup"><span data-stu-id="b809b-136">Deleted</span></span>|<span data-ttu-id="b809b-137">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="b809b-138">Idle</span><span class="sxs-lookup"><span data-stu-id="b809b-138">Idle</span></span>|<span data-ttu-id="b809b-139">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="b809b-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="b809b-140">Persisted</span></span>|<span data-ttu-id="b809b-141">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="b809b-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="b809b-142">Resumed</span></span>|<span data-ttu-id="b809b-143">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="b809b-144">Started</span><span class="sxs-lookup"><span data-stu-id="b809b-144">Started</span></span>|<span data-ttu-id="b809b-145">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="b809b-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="b809b-146">UnhandledException</span></span>|<span data-ttu-id="b809b-147">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="b809b-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="b809b-148">Unloaded</span></span>|<span data-ttu-id="b809b-149">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="b809b-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="b809b-150">Canceled</span></span>|<span data-ttu-id="b809b-151">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="b809b-152">Suspended</span><span class="sxs-lookup"><span data-stu-id="b809b-152">Suspended</span></span>|<span data-ttu-id="b809b-153">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="b809b-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="b809b-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="b809b-154">Terminated</span></span>|<span data-ttu-id="b809b-155">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="b809b-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="b809b-156">Unsuspended</span></span>|<span data-ttu-id="b809b-157">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b809b-158">예제</span><span class="sxs-lookup"><span data-stu-id="b809b-158">Example</span></span>  
 <span data-ttu-id="b809b-159">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b809b-160">참고자료</span><span class="sxs-lookup"><span data-stu-id="b809b-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b809b-161">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="b809b-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b809b-162">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="b809b-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
