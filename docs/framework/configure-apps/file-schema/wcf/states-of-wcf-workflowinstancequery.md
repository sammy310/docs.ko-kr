---
title: <states>WCF의<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: 5b779cf1074687dbd648b23d04f7cf3a354a2014
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855034"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="f967d-102">\<states>WCF의\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="f967d-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="f967d-103">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="f967d-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f967d-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="f967d-105">구문</span><span class="sxs-lookup"><span data-stu-id="f967d-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f967d-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f967d-106">Attributes and elements</span></span>

<span data-ttu-id="f967d-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f967d-108">특성</span><span class="sxs-lookup"><span data-stu-id="f967d-108">Attributes</span></span>  

<span data-ttu-id="f967d-109">없음</span><span class="sxs-lookup"><span data-stu-id="f967d-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f967d-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f967d-110">Child elements</span></span>
  
|<span data-ttu-id="f967d-111">요소</span><span class="sxs-lookup"><span data-stu-id="f967d-111">Element</span></span>|<span data-ttu-id="f967d-112">Description</span><span class="sxs-lookup"><span data-stu-id="f967d-112">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="f967d-113">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-113">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f967d-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f967d-114">Parent elements</span></span>  
  
|<span data-ttu-id="f967d-115">요소</span><span class="sxs-lookup"><span data-stu-id="f967d-115">Element</span></span>|<span data-ttu-id="f967d-116">Description</span><span class="sxs-lookup"><span data-stu-id="f967d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="f967d-117">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-117">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f967d-118">설명</span><span class="sxs-lookup"><span data-stu-id="f967d-118">Remarks</span></span>

<span data-ttu-id="f967d-119">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-119">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="f967d-120">가능한 상태 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-120">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="f967d-121">시스템 상태</span><span class="sxs-lookup"><span data-stu-id="f967d-121">State</span></span>|<span data-ttu-id="f967d-122">Description</span><span class="sxs-lookup"><span data-stu-id="f967d-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f967d-123">중단됨</span><span class="sxs-lookup"><span data-stu-id="f967d-123">Aborted</span></span>|<span data-ttu-id="f967d-124">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-124">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="f967d-125">완료됨</span><span class="sxs-lookup"><span data-stu-id="f967d-125">Completed</span></span>|<span data-ttu-id="f967d-126">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-126">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="f967d-127">삭제됨</span><span class="sxs-lookup"><span data-stu-id="f967d-127">Deleted</span></span>|<span data-ttu-id="f967d-128">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-128">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="f967d-129">유휴 상태</span><span class="sxs-lookup"><span data-stu-id="f967d-129">Idle</span></span>|<span data-ttu-id="f967d-130">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-130">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="f967d-131">지속됨</span><span class="sxs-lookup"><span data-stu-id="f967d-131">Persisted</span></span>|<span data-ttu-id="f967d-132">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-132">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="f967d-133">다시 시작됨</span><span class="sxs-lookup"><span data-stu-id="f967d-133">Resumed</span></span>|<span data-ttu-id="f967d-134">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-134">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="f967d-135">시작됨</span><span class="sxs-lookup"><span data-stu-id="f967d-135">Started</span></span>|<span data-ttu-id="f967d-136">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-136">The workflow instance is started.</span></span>|  
|<span data-ttu-id="f967d-137">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="f967d-137">UnhandledException</span></span>|<span data-ttu-id="f967d-138">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-138">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="f967d-139">언로드됨</span><span class="sxs-lookup"><span data-stu-id="f967d-139">Unloaded</span></span>|<span data-ttu-id="f967d-140">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-140">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="f967d-141">취소됨</span><span class="sxs-lookup"><span data-stu-id="f967d-141">Canceled</span></span>|<span data-ttu-id="f967d-142">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-142">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="f967d-143">일시 중단</span><span class="sxs-lookup"><span data-stu-id="f967d-143">Suspended</span></span>|<span data-ttu-id="f967d-144">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="f967d-144">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="f967d-145">종료됨</span><span class="sxs-lookup"><span data-stu-id="f967d-145">Terminated</span></span>|<span data-ttu-id="f967d-146">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-146">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="f967d-147">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="f967d-147">Unsuspended</span></span>|<span data-ttu-id="f967d-148">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-148">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f967d-149">예제</span><span class="sxs-lookup"><span data-stu-id="f967d-149">Example</span></span>

<span data-ttu-id="f967d-150">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="f967d-150">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="f967d-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f967d-151">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f967d-152">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="f967d-152">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f967d-153">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="f967d-153">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
