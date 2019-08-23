---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: c46d1fb9eb853e57c7ad1b97eb9a22556cdfb7d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913107"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="ec4dd-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="ec4dd-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="ec4dd-102">워크플로 서비스 내에서 처리되지 않은 예외가 발생할 때 수행할 동작을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4dd-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="ec4dd-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ec4dd-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ec4dd-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ec4dd-104">\<behaviors></span></span>  
<span data-ttu-id="ec4dd-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ec4dd-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="ec4dd-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ec4dd-106">\<behavior></span></span>  
<span data-ttu-id="ec4dd-107">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="ec4dd-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec4dd-108">구문</span><span class="sxs-lookup"><span data-stu-id="ec4dd-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec4dd-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ec4dd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ec4dd-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec4dd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec4dd-111">특성</span><span class="sxs-lookup"><span data-stu-id="ec4dd-111">Attributes</span></span>  
  
|<span data-ttu-id="ec4dd-112">특성</span><span class="sxs-lookup"><span data-stu-id="ec4dd-112">Attribute</span></span>|<span data-ttu-id="ec4dd-113">Description</span><span class="sxs-lookup"><span data-stu-id="ec4dd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec4dd-114">action</span><span class="sxs-lookup"><span data-stu-id="ec4dd-114">action</span></span>|<span data-ttu-id="ec4dd-115">처리되지 않은 예외가 발생했을 때 수행할 동작을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4dd-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="ec4dd-116">이 특성은 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4dd-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec4dd-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ec4dd-117">Child Elements</span></span>  
 <span data-ttu-id="ec4dd-118">없음</span><span class="sxs-lookup"><span data-stu-id="ec4dd-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec4dd-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ec4dd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ec4dd-120">요소</span><span class="sxs-lookup"><span data-stu-id="ec4dd-120">Element</span></span>|<span data-ttu-id="ec4dd-121">Description</span><span class="sxs-lookup"><span data-stu-id="ec4dd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec4dd-122">\<servicebehaviors의 \<동작 > ></span><span class="sxs-lookup"><span data-stu-id="ec4dd-122">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="ec4dd-123">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec4dd-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec4dd-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="ec4dd-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
