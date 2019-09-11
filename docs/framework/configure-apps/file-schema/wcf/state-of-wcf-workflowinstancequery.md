---
title: <state>WCF의<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 80f7532f3c51680a2e34713b526dc43822db61b9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854957"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="1d890-102">\<WCF, \<workflowInstanceQuery >의 상태 ></span><span class="sxs-lookup"><span data-stu-id="1d890-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="1d890-103">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="1d890-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d890-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1d890-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1d890-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1d890-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1d890-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1d890-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1d890-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="1d890-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="1d890-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="1d890-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1d890-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="1d890-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1d890-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="1d890-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflowinstancequeries&gt >** ](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1d890-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="1d890-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQuery >** ](workflowinstancequery-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1d890-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)</span></span>\
<span data-ttu-id="1d890-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<상태 >** ](states-of-wcf-workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="1d890-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)</span></span>\
<span data-ttu-id="1d890-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<상태 >**</span><span class="sxs-lookup"><span data-stu-id="1d890-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d890-115">구문</span><span class="sxs-lookup"><span data-stu-id="1d890-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d890-116">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1d890-116">Attributes and elements</span></span>

<span data-ttu-id="1d890-117">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="1d890-118">특성</span><span class="sxs-lookup"><span data-stu-id="1d890-118">Attributes</span></span>

|<span data-ttu-id="1d890-119">특성</span><span class="sxs-lookup"><span data-stu-id="1d890-119">Attribute</span></span>|<span data-ttu-id="1d890-120">Description</span><span class="sxs-lookup"><span data-stu-id="1d890-120">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="1d890-121">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-121">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d890-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1d890-122">Child elements</span></span>

<span data-ttu-id="1d890-123">없음</span><span class="sxs-lookup"><span data-stu-id="1d890-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1d890-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1d890-124">Parent elements</span></span>

|<span data-ttu-id="1d890-125">요소</span><span class="sxs-lookup"><span data-stu-id="1d890-125">Element</span></span>|<span data-ttu-id="1d890-126">설명</span><span class="sxs-lookup"><span data-stu-id="1d890-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d890-127">\<states></span><span class="sxs-lookup"><span data-stu-id="1d890-127">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="1d890-128">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-128">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d890-129">설명</span><span class="sxs-lookup"><span data-stu-id="1d890-129">Remarks</span></span>  

<span data-ttu-id="1d890-130">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-130">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="1d890-131">가능한 상태 값은 다음 표에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-131">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="1d890-132">State</span><span class="sxs-lookup"><span data-stu-id="1d890-132">State</span></span>|<span data-ttu-id="1d890-133">설명</span><span class="sxs-lookup"><span data-stu-id="1d890-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1d890-134">Aborted</span><span class="sxs-lookup"><span data-stu-id="1d890-134">Aborted</span></span>|<span data-ttu-id="1d890-135">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-135">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="1d890-136">Completed</span><span class="sxs-lookup"><span data-stu-id="1d890-136">Completed</span></span>|<span data-ttu-id="1d890-137">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-137">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="1d890-138">삭제됨</span><span class="sxs-lookup"><span data-stu-id="1d890-138">Deleted</span></span>|<span data-ttu-id="1d890-139">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-139">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="1d890-140">Idle</span><span class="sxs-lookup"><span data-stu-id="1d890-140">Idle</span></span>|<span data-ttu-id="1d890-141">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-141">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="1d890-142">Persisted</span><span class="sxs-lookup"><span data-stu-id="1d890-142">Persisted</span></span>|<span data-ttu-id="1d890-143">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-143">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="1d890-144">Resumed</span><span class="sxs-lookup"><span data-stu-id="1d890-144">Resumed</span></span>|<span data-ttu-id="1d890-145">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-145">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="1d890-146">Started</span><span class="sxs-lookup"><span data-stu-id="1d890-146">Started</span></span>|<span data-ttu-id="1d890-147">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-147">The workflow instance is started.</span></span>|  
|<span data-ttu-id="1d890-148">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="1d890-148">UnhandledException</span></span>|<span data-ttu-id="1d890-149">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-149">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="1d890-150">Unloaded</span><span class="sxs-lookup"><span data-stu-id="1d890-150">Unloaded</span></span>|<span data-ttu-id="1d890-151">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-151">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="1d890-152">Canceled</span><span class="sxs-lookup"><span data-stu-id="1d890-152">Canceled</span></span>|<span data-ttu-id="1d890-153">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-153">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="1d890-154">Suspended</span><span class="sxs-lookup"><span data-stu-id="1d890-154">Suspended</span></span>|<span data-ttu-id="1d890-155">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="1d890-155">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="1d890-156">Terminated</span><span class="sxs-lookup"><span data-stu-id="1d890-156">Terminated</span></span>|<span data-ttu-id="1d890-157">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-157">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="1d890-158">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="1d890-158">Unsuspended</span></span>|<span data-ttu-id="1d890-159">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-159">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1d890-160">예제</span><span class="sxs-lookup"><span data-stu-id="1d890-160">Example</span></span>

<span data-ttu-id="1d890-161">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="1d890-161">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="1d890-162">참고자료</span><span class="sxs-lookup"><span data-stu-id="1d890-162">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1d890-163">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="1d890-163">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1d890-164">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="1d890-164">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
