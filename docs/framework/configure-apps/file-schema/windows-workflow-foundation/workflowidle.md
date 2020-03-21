---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: d9eb182ef9c35d2e4c6f5d434e6b200ae2e7ca26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151847"
---
# <a name="workflowidle"></a><span data-ttu-id="81c53-101">\<워크플로우유></span><span class="sxs-lookup"><span data-stu-id="81c53-101">\<workflowIdle></span></span>
<span data-ttu-id="81c53-102">유휴 워크플로 인스턴스가 언로드되고 유지되는 시간을 제어하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="81c53-103">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="81c53-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="81c53-104">&nbsp;&nbsp;[**\<시스템. 서비스 모델>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="81c53-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="81c53-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>동작**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="81c53-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="81c53-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<서비스 행동>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="81c53-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="81c53-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<행동>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="81c53-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="81c53-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<워크플로유유>**</span><span class="sxs-lookup"><span data-stu-id="81c53-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c53-109">구문</span><span class="sxs-lookup"><span data-stu-id="81c53-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81c53-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="81c53-110">Attributes and Elements</span></span>  
 <span data-ttu-id="81c53-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81c53-112">특성</span><span class="sxs-lookup"><span data-stu-id="81c53-112">Attributes</span></span>  
  
|<span data-ttu-id="81c53-113">attribute</span><span class="sxs-lookup"><span data-stu-id="81c53-113">Attribute</span></span>|<span data-ttu-id="81c53-114">Description</span><span class="sxs-lookup"><span data-stu-id="81c53-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81c53-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="81c53-115">timeToPersist</span></span>|<span data-ttu-id="81c53-116">워크플로가 유휴 상태가 되고 유지되는 시간 간의 기간을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="81c53-117">기본값은 TimeSpan.MaxValue입니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="81c53-118">워크플로 인스턴스가 유휴 상태가 되면 기간이 경과되기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="81c53-119">이 특성은 인스턴스를 가능하면 오랫동안 메모리에 보관하면서 워크플로 인스턴스를 적극적으로 유지하려는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="81c53-120">이 특성은 해당 값이 **timeToUnload** 특성보다 적은 경우에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="81c53-121">이보다 크면 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="81c53-122">**timeToUnload** 특성에 의해 지정된 값 앞에 이 특성이 경과하는 경우 워크플로를 언로드하기 전에 지속성이 완료되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="81c53-123">이것은 워크플로가 유지될 때까지 언로드 작업이 지연될 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="81c53-124">지속성 계층은 일시적인 오류가 발생할 경우 재시도를 처리하고 복구할 수 없는 오류가 발생하는 경우에만 예외를 throw하는 역할을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="81c53-125">따라서 유지 중에 throw되는 예외는 심각한 예외로 간주되며 워크플로 인스턴스가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="81c53-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="81c53-126">timeToUnload</span></span>|<span data-ttu-id="81c53-127">워크플로가 유휴 상태가 되고 언로드되는 시간 간의 기간을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="81c53-128">기본값은 1분입니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="81c53-129">워크플로를 언로드한다는 것은 이를 유지한다는 의미이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="81c53-130">이 특성이 0으로 설정되면 워크플로가 유휴 상태가 되는 즉시 워크플로 인스턴스가 유지되고 언로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="81c53-131">이 특성을 TimeSpan.MaxValue로 설정하면 언로드 작업이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="81c53-132">즉, 유휴 워크플로 인스턴스가 언로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81c53-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="81c53-133">Child Elements</span></span>  
 <span data-ttu-id="81c53-134">없음</span><span class="sxs-lookup"><span data-stu-id="81c53-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81c53-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="81c53-135">Parent Elements</span></span>  
  
|<span data-ttu-id="81c53-136">요소</span><span class="sxs-lookup"><span data-stu-id="81c53-136">Element</span></span>|<span data-ttu-id="81c53-137">Description</span><span class="sxs-lookup"><span data-stu-id="81c53-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81c53-138">\<\<행동> 서비스 행동></span><span class="sxs-lookup"><span data-stu-id="81c53-138">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="81c53-139">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81c53-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81c53-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81c53-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
