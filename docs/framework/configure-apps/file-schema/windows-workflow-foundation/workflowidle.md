---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 1dc186f5899935dab43c0d33894e659c4b19748c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201119"
---
# <a name="workflowidle"></a><span data-ttu-id="0b36b-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="0b36b-101">\<workflowIdle></span></span>
<span data-ttu-id="0b36b-102">유휴 워크플로 인스턴스가 언로드되고 유지되는 시간을 제어하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="0b36b-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0b36b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0b36b-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0b36b-104">\<behaviors></span></span>  
<span data-ttu-id="0b36b-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="0b36b-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="0b36b-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0b36b-106">\<behavior></span></span>  
<span data-ttu-id="0b36b-107">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="0b36b-107">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b36b-108">구문</span><span class="sxs-lookup"><span data-stu-id="0b36b-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b36b-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0b36b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0b36b-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b36b-111">특성</span><span class="sxs-lookup"><span data-stu-id="0b36b-111">Attributes</span></span>  
  
|<span data-ttu-id="0b36b-112">특성</span><span class="sxs-lookup"><span data-stu-id="0b36b-112">Attribute</span></span>|<span data-ttu-id="0b36b-113">설명</span><span class="sxs-lookup"><span data-stu-id="0b36b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b36b-114">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="0b36b-114">timeToPersist</span></span>|<span data-ttu-id="0b36b-115">워크플로가 유휴 상태가 되 고 유지 되는 시간 사이의 기간을 지정 하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-115">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="0b36b-116">기본값은 TimeSpan.MaxValue입니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-116">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="0b36b-117">워크플로 인스턴스가 유휴 상태가 되면 기간이 경과되기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-117">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="0b36b-118">이 특성은 인스턴스를 그대로 유지 하면서 최대한 오랫동안 메모리에서 워크플로 인스턴스를 더 적극적으로 유지 하려는 경우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-118">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="0b36b-119">이 특성은 해당 값이 유효한만 보다 작은 **timeToUnload** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-119">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="0b36b-120">이보다 크면 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-120">If it is greater, it is ignored.</span></span> <span data-ttu-id="0b36b-121">이 특성에 지정 된 값 전에 경과 된 경우는 **timeToUnload** 특성인 워크플로가 언로드되기 전에 지 속성이 완료 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-121">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="0b36b-122">이것은 워크플로가 유지될 때까지 언로드 작업이 지연될 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-122">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="0b36b-123">지속성 계층은 일시적인 오류가 발생할 경우 재시도를 처리하고 복구할 수 없는 오류가 발생하는 경우에만 예외를 throw하는 역할을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-123">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="0b36b-124">따라서 유지 중에 throw되는 예외는 심각한 예외로 간주되며 워크플로 인스턴스가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-124">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="0b36b-125">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="0b36b-125">timeToUnload</span></span>|<span data-ttu-id="0b36b-126">워크플로가 유휴 상태가 되고 언로드되는 시간 간의 기간을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-126">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="0b36b-127">기본값은 1분입니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-127">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="0b36b-128">워크플로를 언로드한다는 것은 이를 유지한다는 의미이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-128">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="0b36b-129">이 특성은 워크플로 인스턴스가 유지 되 고 언로드된 후 즉시 0으로 설정 된 경우 워크플로가 유휴 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-129">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="0b36b-130">이 특성을 TimeSpan.MaxValue로 효과적으로 설정 하면 언로드 작업이 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-130">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="0b36b-131">즉, 유휴 워크플로 인스턴스가 언로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-131">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b36b-132">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0b36b-132">Child Elements</span></span>  
 <span data-ttu-id="0b36b-133">없음</span><span class="sxs-lookup"><span data-stu-id="0b36b-133">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b36b-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0b36b-134">Parent Elements</span></span>  
  
|<span data-ttu-id="0b36b-135">요소</span><span class="sxs-lookup"><span data-stu-id="0b36b-135">Element</span></span>|<span data-ttu-id="0b36b-136">설명</span><span class="sxs-lookup"><span data-stu-id="0b36b-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b36b-137">\<동작 >의 \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0b36b-137">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="0b36b-138">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b36b-138">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b36b-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="0b36b-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
