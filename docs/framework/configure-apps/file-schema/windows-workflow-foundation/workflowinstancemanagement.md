---
description: 다음에 대해 자세히 알아보세요. <workflowInstanceManagement>
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 528c0c923be93d9581b8e3bfccc382eab11c5da1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697922"
---
# \<workflowInstanceManagement>

<span data-ttu-id="2ba2c-102">지속성 예외, 처리되지 않은 예외 동작 및 유휴 동작을 비롯하여 워크플로 인스턴스 실행 방법을 제어하는 설정을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**  
  
## <a name="syntax"></a><span data-ttu-id="2ba2c-103">구문</span><span class="sxs-lookup"><span data-stu-id="2ba2c-103">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ba2c-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2ba2c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="2ba2c-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ba2c-106">특성</span><span class="sxs-lookup"><span data-stu-id="2ba2c-106">Attributes</span></span>  
  
|<span data-ttu-id="2ba2c-107">attribute</span><span class="sxs-lookup"><span data-stu-id="2ba2c-107">Attribute</span></span>|<span data-ttu-id="2ba2c-108">설명</span><span class="sxs-lookup"><span data-stu-id="2ba2c-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ba2c-109">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="2ba2c-109">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="2ba2c-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2ba2c-110">Child Elements</span></span>  

 <span data-ttu-id="2ba2c-111">없음</span><span class="sxs-lookup"><span data-stu-id="2ba2c-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ba2c-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2ba2c-112">Parent Elements</span></span>  
  
|<span data-ttu-id="2ba2c-113">요소</span><span class="sxs-lookup"><span data-stu-id="2ba2c-113">Element</span></span>|<span data-ttu-id="2ba2c-114">설명</span><span class="sxs-lookup"><span data-stu-id="2ba2c-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ba2c-115">\<serviceBehaviors>의 \<behavior></span><span class="sxs-lookup"><span data-stu-id="2ba2c-115">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="2ba2c-116">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ba2c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ba2c-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
