---
description: '다음에 대 한 자세한 정보: <states> WCF, <workflowInstanceQuery>'
title: <states> WCF의 <workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: 66b3008b352d1f76c30aab9a0ec038836f33d408
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786644"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="beade-103">\<states> WCF의 \<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="beade-103">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="beade-104">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="beade-104">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="beade-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="beade-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="beade-106">구문</span><span class="sxs-lookup"><span data-stu-id="beade-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="beade-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="beade-107">Attributes and elements</span></span>

<span data-ttu-id="beade-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="beade-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="beade-109">특성</span><span class="sxs-lookup"><span data-stu-id="beade-109">Attributes</span></span>  

<span data-ttu-id="beade-110">없음</span><span class="sxs-lookup"><span data-stu-id="beade-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="beade-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="beade-111">Child elements</span></span>
  
|<span data-ttu-id="beade-112">요소</span><span class="sxs-lookup"><span data-stu-id="beade-112">Element</span></span>|<span data-ttu-id="beade-113">설명</span><span class="sxs-lookup"><span data-stu-id="beade-113">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="beade-114">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="beade-114">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="beade-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="beade-115">Parent elements</span></span>  
  
|<span data-ttu-id="beade-116">요소</span><span class="sxs-lookup"><span data-stu-id="beade-116">Element</span></span>|<span data-ttu-id="beade-117">설명</span><span class="sxs-lookup"><span data-stu-id="beade-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="beade-118">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="beade-118">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beade-119">설명</span><span class="sxs-lookup"><span data-stu-id="beade-119">Remarks</span></span>

<span data-ttu-id="beade-120">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="beade-120">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="beade-121">가능한 상태 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beade-121">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="beade-122">시스템 상태</span><span class="sxs-lookup"><span data-stu-id="beade-122">State</span></span>|<span data-ttu-id="beade-123">Description</span><span class="sxs-lookup"><span data-stu-id="beade-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="beade-124">중단됨</span><span class="sxs-lookup"><span data-stu-id="beade-124">Aborted</span></span>|<span data-ttu-id="beade-125">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="beade-125">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="beade-126">완료됨</span><span class="sxs-lookup"><span data-stu-id="beade-126">Completed</span></span>|<span data-ttu-id="beade-127">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="beade-127">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="beade-128">삭제됨</span><span class="sxs-lookup"><span data-stu-id="beade-128">Deleted</span></span>|<span data-ttu-id="beade-129">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="beade-129">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="beade-130">유휴 상태</span><span class="sxs-lookup"><span data-stu-id="beade-130">Idle</span></span>|<span data-ttu-id="beade-131">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="beade-131">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="beade-132">지속됨</span><span class="sxs-lookup"><span data-stu-id="beade-132">Persisted</span></span>|<span data-ttu-id="beade-133">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="beade-133">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="beade-134">다시 시작됨</span><span class="sxs-lookup"><span data-stu-id="beade-134">Resumed</span></span>|<span data-ttu-id="beade-135">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="beade-135">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="beade-136">시작됨</span><span class="sxs-lookup"><span data-stu-id="beade-136">Started</span></span>|<span data-ttu-id="beade-137">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="beade-137">The workflow instance is started.</span></span>|  
|<span data-ttu-id="beade-138">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="beade-138">UnhandledException</span></span>|<span data-ttu-id="beade-139">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="beade-139">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="beade-140">언로드됨</span><span class="sxs-lookup"><span data-stu-id="beade-140">Unloaded</span></span>|<span data-ttu-id="beade-141">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="beade-141">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="beade-142">취소됨</span><span class="sxs-lookup"><span data-stu-id="beade-142">Canceled</span></span>|<span data-ttu-id="beade-143">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="beade-143">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="beade-144">일시 중단</span><span class="sxs-lookup"><span data-stu-id="beade-144">Suspended</span></span>|<span data-ttu-id="beade-145">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="beade-145">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="beade-146">종료됨</span><span class="sxs-lookup"><span data-stu-id="beade-146">Terminated</span></span>|<span data-ttu-id="beade-147">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="beade-147">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="beade-148">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="beade-148">Unsuspended</span></span>|<span data-ttu-id="beade-149">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="beade-149">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="beade-150">예제</span><span class="sxs-lookup"><span data-stu-id="beade-150">Example</span></span>

<span data-ttu-id="beade-151">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="beade-151">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="beade-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="beade-152">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="beade-153">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="beade-153">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="beade-154">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="beade-154">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
