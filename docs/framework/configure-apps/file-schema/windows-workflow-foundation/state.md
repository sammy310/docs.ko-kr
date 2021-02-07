---
description: 다음에 대해 자세히 알아보세요. <state>
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: c04ba8a791d08e65337ffc28cd86f5a4a6af150f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729760"
---
# \<state>

<span data-ttu-id="86c7c-102">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="86c7c-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86c7c-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="86c7c-104">구문</span><span class="sxs-lookup"><span data-stu-id="86c7c-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86c7c-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="86c7c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="86c7c-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86c7c-107">특성</span><span class="sxs-lookup"><span data-stu-id="86c7c-107">Attributes</span></span>  
  
|<span data-ttu-id="86c7c-108">attribute</span><span class="sxs-lookup"><span data-stu-id="86c7c-108">Attribute</span></span>|<span data-ttu-id="86c7c-109">설명</span><span class="sxs-lookup"><span data-stu-id="86c7c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="86c7c-110">name</span><span class="sxs-lookup"><span data-stu-id="86c7c-110">name</span></span>|<span data-ttu-id="86c7c-111">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-111">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86c7c-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="86c7c-112">Child Elements</span></span>  

 <span data-ttu-id="86c7c-113">없음</span><span class="sxs-lookup"><span data-stu-id="86c7c-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86c7c-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="86c7c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="86c7c-115">요소</span><span class="sxs-lookup"><span data-stu-id="86c7c-115">Element</span></span>|<span data-ttu-id="86c7c-116">설명</span><span class="sxs-lookup"><span data-stu-id="86c7c-116">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states.md)|<span data-ttu-id="86c7c-117">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-117">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86c7c-118">설명</span><span class="sxs-lookup"><span data-stu-id="86c7c-118">Remarks</span></span>  

 <span data-ttu-id="86c7c-119">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-119">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="86c7c-120">가능한 상태 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-120">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="86c7c-121">시스템 상태</span><span class="sxs-lookup"><span data-stu-id="86c7c-121">State</span></span>|<span data-ttu-id="86c7c-122">Description</span><span class="sxs-lookup"><span data-stu-id="86c7c-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="86c7c-123">중단됨</span><span class="sxs-lookup"><span data-stu-id="86c7c-123">Aborted</span></span>|<span data-ttu-id="86c7c-124">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-124">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="86c7c-125">완료됨</span><span class="sxs-lookup"><span data-stu-id="86c7c-125">Completed</span></span>|<span data-ttu-id="86c7c-126">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-126">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="86c7c-127">삭제됨</span><span class="sxs-lookup"><span data-stu-id="86c7c-127">Deleted</span></span>|<span data-ttu-id="86c7c-128">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-128">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="86c7c-129">유휴 상태</span><span class="sxs-lookup"><span data-stu-id="86c7c-129">Idle</span></span>|<span data-ttu-id="86c7c-130">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-130">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="86c7c-131">지속됨</span><span class="sxs-lookup"><span data-stu-id="86c7c-131">Persisted</span></span>|<span data-ttu-id="86c7c-132">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-132">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="86c7c-133">다시 시작됨</span><span class="sxs-lookup"><span data-stu-id="86c7c-133">Resumed</span></span>|<span data-ttu-id="86c7c-134">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-134">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="86c7c-135">시작됨</span><span class="sxs-lookup"><span data-stu-id="86c7c-135">Started</span></span>|<span data-ttu-id="86c7c-136">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-136">The workflow instance is started.</span></span>|  
|<span data-ttu-id="86c7c-137">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="86c7c-137">UnhandledException</span></span>|<span data-ttu-id="86c7c-138">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-138">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="86c7c-139">언로드됨</span><span class="sxs-lookup"><span data-stu-id="86c7c-139">Unloaded</span></span>|<span data-ttu-id="86c7c-140">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-140">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="86c7c-141">취소됨</span><span class="sxs-lookup"><span data-stu-id="86c7c-141">Canceled</span></span>|<span data-ttu-id="86c7c-142">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-142">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="86c7c-143">일시 중단</span><span class="sxs-lookup"><span data-stu-id="86c7c-143">Suspended</span></span>|<span data-ttu-id="86c7c-144">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="86c7c-144">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="86c7c-145">종료됨</span><span class="sxs-lookup"><span data-stu-id="86c7c-145">Terminated</span></span>|<span data-ttu-id="86c7c-146">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-146">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="86c7c-147">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="86c7c-147">Unsuspended</span></span>|<span data-ttu-id="86c7c-148">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-148">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="86c7c-149">예제</span><span class="sxs-lookup"><span data-stu-id="86c7c-149">Example</span></span>  

 <span data-ttu-id="86c7c-150">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="86c7c-150">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="86c7c-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86c7c-151">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="86c7c-152">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="86c7c-152">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="86c7c-153">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="86c7c-153">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
