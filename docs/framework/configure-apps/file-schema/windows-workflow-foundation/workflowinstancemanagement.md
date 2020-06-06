---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: aa2edafd9adc0317ed0023ad46688025dcecad67
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397530"
---
# \<workflowInstanceManagement>
<span data-ttu-id="f5aef-101">지속성 예외, 처리되지 않은 예외 동작 및 유휴 동작을 비롯하여 워크플로 인스턴스 실행 방법을 제어하는 설정을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="f5aef-101">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**  
  
## <a name="syntax"></a><span data-ttu-id="f5aef-102">구문</span><span class="sxs-lookup"><span data-stu-id="f5aef-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5aef-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f5aef-103">Attributes and Elements</span></span>  
 <span data-ttu-id="f5aef-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5aef-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5aef-105">특성</span><span class="sxs-lookup"><span data-stu-id="f5aef-105">Attributes</span></span>  
  
|<span data-ttu-id="f5aef-106">attribute</span><span class="sxs-lookup"><span data-stu-id="f5aef-106">Attribute</span></span>|<span data-ttu-id="f5aef-107">Description</span><span class="sxs-lookup"><span data-stu-id="f5aef-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5aef-108">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="f5aef-108">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="f5aef-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f5aef-109">Child Elements</span></span>  
 <span data-ttu-id="f5aef-110">없음</span><span class="sxs-lookup"><span data-stu-id="f5aef-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5aef-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f5aef-111">Parent Elements</span></span>  
  
|<span data-ttu-id="f5aef-112">요소</span><span class="sxs-lookup"><span data-stu-id="f5aef-112">Element</span></span>|<span data-ttu-id="f5aef-113">Description</span><span class="sxs-lookup"><span data-stu-id="f5aef-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5aef-114">\<behavior>으로\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f5aef-114">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="f5aef-115">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5aef-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5aef-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5aef-116">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
