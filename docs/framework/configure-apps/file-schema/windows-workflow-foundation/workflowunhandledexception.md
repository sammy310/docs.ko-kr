---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 29b6d8982e712a0fa595b3103803f1795adea892
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398563"
---
# \<workflowUnhandledException>
<span data-ttu-id="ddf66-101">워크플로 서비스 내에서 처리되지 않은 예외가 발생할 때 수행할 동작을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="ddf66-101">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="ddf66-102">구문</span><span class="sxs-lookup"><span data-stu-id="ddf66-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddf66-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ddf66-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ddf66-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf66-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddf66-105">특성</span><span class="sxs-lookup"><span data-stu-id="ddf66-105">Attributes</span></span>  
  
|<span data-ttu-id="ddf66-106">attribute</span><span class="sxs-lookup"><span data-stu-id="ddf66-106">Attribute</span></span>|<span data-ttu-id="ddf66-107">Description</span><span class="sxs-lookup"><span data-stu-id="ddf66-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ddf66-108">action</span><span class="sxs-lookup"><span data-stu-id="ddf66-108">action</span></span>|<span data-ttu-id="ddf66-109">처리되지 않은 예외가 발생했을 때 수행할 동작을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ddf66-109">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="ddf66-110">이 특성은 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ddf66-110">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ddf66-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ddf66-111">Child Elements</span></span>  
 <span data-ttu-id="ddf66-112">없음</span><span class="sxs-lookup"><span data-stu-id="ddf66-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ddf66-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ddf66-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ddf66-114">요소</span><span class="sxs-lookup"><span data-stu-id="ddf66-114">Element</span></span>|<span data-ttu-id="ddf66-115">Description</span><span class="sxs-lookup"><span data-stu-id="ddf66-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ddf66-116">\<behavior>으로\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ddf66-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="ddf66-117">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf66-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ddf66-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ddf66-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
