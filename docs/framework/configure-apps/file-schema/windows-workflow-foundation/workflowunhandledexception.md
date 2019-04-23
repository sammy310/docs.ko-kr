---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: cfe3350ac42d1e0e837b79f25753f62dc2051dd2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096253"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="55a25-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="55a25-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="55a25-102">워크플로 서비스 내에서 처리되지 않은 예외가 발생할 때 수행할 동작을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="55a25-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="55a25-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="55a25-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="55a25-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="55a25-104">\<behaviors></span></span>  
<span data-ttu-id="55a25-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="55a25-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="55a25-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="55a25-106">\<behavior></span></span>  
<span data-ttu-id="55a25-107">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="55a25-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55a25-108">구문</span><span class="sxs-lookup"><span data-stu-id="55a25-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55a25-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="55a25-109">Attributes and Elements</span></span>  
 <span data-ttu-id="55a25-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="55a25-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55a25-111">특성</span><span class="sxs-lookup"><span data-stu-id="55a25-111">Attributes</span></span>  
  
|<span data-ttu-id="55a25-112">특성</span><span class="sxs-lookup"><span data-stu-id="55a25-112">Attribute</span></span>|<span data-ttu-id="55a25-113">설명</span><span class="sxs-lookup"><span data-stu-id="55a25-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="55a25-114">action</span><span class="sxs-lookup"><span data-stu-id="55a25-114">action</span></span>|<span data-ttu-id="55a25-115">처리되지 않은 예외가 발생했을 때 수행할 동작을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="55a25-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="55a25-116">이 특성은 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="55a25-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55a25-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="55a25-117">Child Elements</span></span>  
 <span data-ttu-id="55a25-118">없음</span><span class="sxs-lookup"><span data-stu-id="55a25-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55a25-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="55a25-119">Parent Elements</span></span>  
  
|<span data-ttu-id="55a25-120">요소</span><span class="sxs-lookup"><span data-stu-id="55a25-120">Element</span></span>|<span data-ttu-id="55a25-121">설명</span><span class="sxs-lookup"><span data-stu-id="55a25-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55a25-122">\<동작 >의 \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="55a25-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="55a25-123">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="55a25-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55a25-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="55a25-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
