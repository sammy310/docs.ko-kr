---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 29b6d8982e712a0fa595b3103803f1795adea892
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398563"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="8020b-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="8020b-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="8020b-102">워크플로 서비스 내에서 처리되지 않은 예외가 발생할 때 수행할 동작을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="8020b-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="8020b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8020b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8020b-104">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8020b-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="8020b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8020b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="8020b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8020b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="8020b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8020b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="8020b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowUnhandledException >**</span><span class="sxs-lookup"><span data-stu-id="8020b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8020b-109">구문</span><span class="sxs-lookup"><span data-stu-id="8020b-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8020b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8020b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8020b-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8020b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8020b-112">특성</span><span class="sxs-lookup"><span data-stu-id="8020b-112">Attributes</span></span>  
  
|<span data-ttu-id="8020b-113">특성</span><span class="sxs-lookup"><span data-stu-id="8020b-113">Attribute</span></span>|<span data-ttu-id="8020b-114">설명</span><span class="sxs-lookup"><span data-stu-id="8020b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8020b-115">action</span><span class="sxs-lookup"><span data-stu-id="8020b-115">action</span></span>|<span data-ttu-id="8020b-116">처리되지 않은 예외가 발생했을 때 수행할 동작을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8020b-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="8020b-117">이 특성은 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8020b-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8020b-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8020b-118">Child Elements</span></span>  
 <span data-ttu-id="8020b-119">없음</span><span class="sxs-lookup"><span data-stu-id="8020b-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8020b-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8020b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8020b-121">요소</span><span class="sxs-lookup"><span data-stu-id="8020b-121">Element</span></span>|<span data-ttu-id="8020b-122">Description</span><span class="sxs-lookup"><span data-stu-id="8020b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8020b-123">\<servicebehaviors의 \<동작 > ></span><span class="sxs-lookup"><span data-stu-id="8020b-123">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="8020b-124">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8020b-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8020b-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="8020b-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
