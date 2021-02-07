---
description: 다음에 대해 자세히 알아보세요. <workflowUnhandledException>
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: b9258c986ffa154e490f80bead1dc53d8f7ef44d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697779"
---
# \<workflowUnhandledException>

<span data-ttu-id="8ddf0-102">워크플로 서비스 내에서 처리되지 않은 예외가 발생할 때 수행할 동작을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="8ddf0-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="8ddf0-103">구문</span><span class="sxs-lookup"><span data-stu-id="8ddf0-103">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ddf0-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8ddf0-104">Attributes and Elements</span></span>  

 <span data-ttu-id="8ddf0-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ddf0-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ddf0-106">특성</span><span class="sxs-lookup"><span data-stu-id="8ddf0-106">Attributes</span></span>  
  
|<span data-ttu-id="8ddf0-107">attribute</span><span class="sxs-lookup"><span data-stu-id="8ddf0-107">Attribute</span></span>|<span data-ttu-id="8ddf0-108">설명</span><span class="sxs-lookup"><span data-stu-id="8ddf0-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ddf0-109">작업</span><span class="sxs-lookup"><span data-stu-id="8ddf0-109">action</span></span>|<span data-ttu-id="8ddf0-110">처리되지 않은 예외가 발생했을 때 수행할 동작을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8ddf0-110">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="8ddf0-111">이 특성은 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8ddf0-111">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ddf0-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8ddf0-112">Child Elements</span></span>  

 <span data-ttu-id="8ddf0-113">없음</span><span class="sxs-lookup"><span data-stu-id="8ddf0-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ddf0-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8ddf0-114">Parent Elements</span></span>  
  
|<span data-ttu-id="8ddf0-115">요소</span><span class="sxs-lookup"><span data-stu-id="8ddf0-115">Element</span></span>|<span data-ttu-id="8ddf0-116">설명</span><span class="sxs-lookup"><span data-stu-id="8ddf0-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ddf0-117">\<serviceBehaviors>의 \<behavior></span><span class="sxs-lookup"><span data-stu-id="8ddf0-117">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="8ddf0-118">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ddf0-118">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ddf0-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ddf0-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
