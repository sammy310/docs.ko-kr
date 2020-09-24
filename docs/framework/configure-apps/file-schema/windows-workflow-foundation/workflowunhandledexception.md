---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 6e3993e43aac746f380a30341fe4ebffcd257c5f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148518"
---
# \<workflowUnhandledException>

<span data-ttu-id="8cb39-101">워크플로 서비스 내에서 처리되지 않은 예외가 발생할 때 수행할 동작을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb39-101">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="8cb39-102">구문</span><span class="sxs-lookup"><span data-stu-id="8cb39-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8cb39-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8cb39-103">Attributes and Elements</span></span>  

 <span data-ttu-id="8cb39-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb39-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8cb39-105">특성</span><span class="sxs-lookup"><span data-stu-id="8cb39-105">Attributes</span></span>  
  
|<span data-ttu-id="8cb39-106">attribute</span><span class="sxs-lookup"><span data-stu-id="8cb39-106">Attribute</span></span>|<span data-ttu-id="8cb39-107">설명</span><span class="sxs-lookup"><span data-stu-id="8cb39-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8cb39-108">action</span><span class="sxs-lookup"><span data-stu-id="8cb39-108">action</span></span>|<span data-ttu-id="8cb39-109">처리되지 않은 예외가 발생했을 때 수행할 동작을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb39-109">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="8cb39-110">이 특성은 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb39-110">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8cb39-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8cb39-111">Child Elements</span></span>  

 <span data-ttu-id="8cb39-112">없음</span><span class="sxs-lookup"><span data-stu-id="8cb39-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8cb39-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8cb39-113">Parent Elements</span></span>  
  
|<span data-ttu-id="8cb39-114">요소</span><span class="sxs-lookup"><span data-stu-id="8cb39-114">Element</span></span>|<span data-ttu-id="8cb39-115">설명</span><span class="sxs-lookup"><span data-stu-id="8cb39-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8cb39-116">\<serviceBehaviors>의 \<behavior></span><span class="sxs-lookup"><span data-stu-id="8cb39-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="8cb39-117">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb39-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8cb39-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cb39-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
