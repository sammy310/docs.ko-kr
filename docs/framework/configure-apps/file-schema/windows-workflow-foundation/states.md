---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: e759f86e7746eaf3fdd72ed923612b24ef9b0c23
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150819"
---
# \<states>

<span data-ttu-id="81405-101">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81405-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="81405-102">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81405-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="81405-103">구문</span><span class="sxs-lookup"><span data-stu-id="81405-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81405-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="81405-104">Attributes and Elements</span></span>  

 <span data-ttu-id="81405-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="81405-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81405-106">특성</span><span class="sxs-lookup"><span data-stu-id="81405-106">Attributes</span></span>  

 <span data-ttu-id="81405-107">없음</span><span class="sxs-lookup"><span data-stu-id="81405-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="81405-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="81405-108">Child Elements</span></span>  
  
|<span data-ttu-id="81405-109">요소</span><span class="sxs-lookup"><span data-stu-id="81405-109">Element</span></span>|<span data-ttu-id="81405-110">설명</span><span class="sxs-lookup"><span data-stu-id="81405-110">Description</span></span>|  
|-------------|-----------------|  
|[\<state>](states.md)|<span data-ttu-id="81405-111">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="81405-111">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="81405-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="81405-112">Parent Elements</span></span>  
  
|<span data-ttu-id="81405-113">요소</span><span class="sxs-lookup"><span data-stu-id="81405-113">Element</span></span>|<span data-ttu-id="81405-114">설명</span><span class="sxs-lookup"><span data-stu-id="81405-114">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|<span data-ttu-id="81405-115">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="81405-115">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81405-116">설명</span><span class="sxs-lookup"><span data-stu-id="81405-116">Remarks</span></span>  

 <span data-ttu-id="81405-117">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="81405-117">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="81405-118">가능한 상태 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81405-118">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="81405-119">시스템 상태</span><span class="sxs-lookup"><span data-stu-id="81405-119">State</span></span>|<span data-ttu-id="81405-120">Description</span><span class="sxs-lookup"><span data-stu-id="81405-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="81405-121">중단됨</span><span class="sxs-lookup"><span data-stu-id="81405-121">Aborted</span></span>|<span data-ttu-id="81405-122">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81405-122">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="81405-123">완료됨</span><span class="sxs-lookup"><span data-stu-id="81405-123">Completed</span></span>|<span data-ttu-id="81405-124">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81405-124">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="81405-125">삭제됨</span><span class="sxs-lookup"><span data-stu-id="81405-125">Deleted</span></span>|<span data-ttu-id="81405-126">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81405-126">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="81405-127">유휴 상태</span><span class="sxs-lookup"><span data-stu-id="81405-127">Idle</span></span>|<span data-ttu-id="81405-128">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="81405-128">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="81405-129">지속됨</span><span class="sxs-lookup"><span data-stu-id="81405-129">Persisted</span></span>|<span data-ttu-id="81405-130">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81405-130">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="81405-131">다시 시작됨</span><span class="sxs-lookup"><span data-stu-id="81405-131">Resumed</span></span>|<span data-ttu-id="81405-132">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81405-132">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="81405-133">시작됨</span><span class="sxs-lookup"><span data-stu-id="81405-133">Started</span></span>|<span data-ttu-id="81405-134">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81405-134">The workflow instance is started.</span></span>|  
|<span data-ttu-id="81405-135">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="81405-135">UnhandledException</span></span>|<span data-ttu-id="81405-136">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="81405-136">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="81405-137">언로드됨</span><span class="sxs-lookup"><span data-stu-id="81405-137">Unloaded</span></span>|<span data-ttu-id="81405-138">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81405-138">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="81405-139">취소됨</span><span class="sxs-lookup"><span data-stu-id="81405-139">Canceled</span></span>|<span data-ttu-id="81405-140">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81405-140">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="81405-141">일시 중단</span><span class="sxs-lookup"><span data-stu-id="81405-141">Suspended</span></span>|<span data-ttu-id="81405-142">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="81405-142">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="81405-143">종료됨</span><span class="sxs-lookup"><span data-stu-id="81405-143">Terminated</span></span>|<span data-ttu-id="81405-144">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="81405-144">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="81405-145">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="81405-145">Unsuspended</span></span>|<span data-ttu-id="81405-146">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="81405-146">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="81405-147">예제</span><span class="sxs-lookup"><span data-stu-id="81405-147">Example</span></span>  

 <span data-ttu-id="81405-148">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="81405-148">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="81405-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81405-149">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="81405-150">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="81405-150">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="81405-151">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="81405-151">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
