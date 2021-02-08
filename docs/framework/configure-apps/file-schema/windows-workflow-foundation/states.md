---
description: 다음에 대해 자세히 알아보세요. <states>
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 9a66a1ce460db1f5f55fb99a191368635220f32f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781976"
---
# \<states>

<span data-ttu-id="55602-102">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="55602-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="55602-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55602-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="55602-104">구문</span><span class="sxs-lookup"><span data-stu-id="55602-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55602-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="55602-105">Attributes and Elements</span></span>  

 <span data-ttu-id="55602-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="55602-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55602-107">특성</span><span class="sxs-lookup"><span data-stu-id="55602-107">Attributes</span></span>  

 <span data-ttu-id="55602-108">없음</span><span class="sxs-lookup"><span data-stu-id="55602-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="55602-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="55602-109">Child Elements</span></span>  
  
|<span data-ttu-id="55602-110">요소</span><span class="sxs-lookup"><span data-stu-id="55602-110">Element</span></span>|<span data-ttu-id="55602-111">설명</span><span class="sxs-lookup"><span data-stu-id="55602-111">Description</span></span>|  
|-------------|-----------------|  
|[\<state>](states.md)|<span data-ttu-id="55602-112">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="55602-112">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="55602-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="55602-113">Parent Elements</span></span>  
  
|<span data-ttu-id="55602-114">요소</span><span class="sxs-lookup"><span data-stu-id="55602-114">Element</span></span>|<span data-ttu-id="55602-115">설명</span><span class="sxs-lookup"><span data-stu-id="55602-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|<span data-ttu-id="55602-116">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="55602-116">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55602-117">설명</span><span class="sxs-lookup"><span data-stu-id="55602-117">Remarks</span></span>  

 <span data-ttu-id="55602-118">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="55602-118">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="55602-119">가능한 상태 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55602-119">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="55602-120">시스템 상태</span><span class="sxs-lookup"><span data-stu-id="55602-120">State</span></span>|<span data-ttu-id="55602-121">Description</span><span class="sxs-lookup"><span data-stu-id="55602-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="55602-122">중단됨</span><span class="sxs-lookup"><span data-stu-id="55602-122">Aborted</span></span>|<span data-ttu-id="55602-123">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55602-123">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="55602-124">완료됨</span><span class="sxs-lookup"><span data-stu-id="55602-124">Completed</span></span>|<span data-ttu-id="55602-125">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55602-125">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="55602-126">삭제됨</span><span class="sxs-lookup"><span data-stu-id="55602-126">Deleted</span></span>|<span data-ttu-id="55602-127">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55602-127">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="55602-128">유휴 상태</span><span class="sxs-lookup"><span data-stu-id="55602-128">Idle</span></span>|<span data-ttu-id="55602-129">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="55602-129">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="55602-130">지속됨</span><span class="sxs-lookup"><span data-stu-id="55602-130">Persisted</span></span>|<span data-ttu-id="55602-131">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55602-131">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="55602-132">다시 시작됨</span><span class="sxs-lookup"><span data-stu-id="55602-132">Resumed</span></span>|<span data-ttu-id="55602-133">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55602-133">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="55602-134">시작됨</span><span class="sxs-lookup"><span data-stu-id="55602-134">Started</span></span>|<span data-ttu-id="55602-135">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55602-135">The workflow instance is started.</span></span>|  
|<span data-ttu-id="55602-136">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="55602-136">UnhandledException</span></span>|<span data-ttu-id="55602-137">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="55602-137">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="55602-138">언로드됨</span><span class="sxs-lookup"><span data-stu-id="55602-138">Unloaded</span></span>|<span data-ttu-id="55602-139">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55602-139">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="55602-140">취소됨</span><span class="sxs-lookup"><span data-stu-id="55602-140">Canceled</span></span>|<span data-ttu-id="55602-141">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55602-141">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="55602-142">일시 중단</span><span class="sxs-lookup"><span data-stu-id="55602-142">Suspended</span></span>|<span data-ttu-id="55602-143">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="55602-143">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="55602-144">종료됨</span><span class="sxs-lookup"><span data-stu-id="55602-144">Terminated</span></span>|<span data-ttu-id="55602-145">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="55602-145">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="55602-146">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="55602-146">Unsuspended</span></span>|<span data-ttu-id="55602-147">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="55602-147">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="55602-148">예제</span><span class="sxs-lookup"><span data-stu-id="55602-148">Example</span></span>  

 <span data-ttu-id="55602-149">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="55602-149">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="55602-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55602-150">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="55602-151">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="55602-151">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="55602-152">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="55602-152">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
