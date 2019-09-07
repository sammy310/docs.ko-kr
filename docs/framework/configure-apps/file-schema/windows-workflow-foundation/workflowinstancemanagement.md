---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: aa2edafd9adc0317ed0023ad46688025dcecad67
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397530"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="109d2-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="109d2-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="109d2-102">지속성 예외, 처리되지 않은 예외 동작 및 유휴 동작을 비롯하여 워크플로 인스턴스 실행 방법을 제어하는 설정을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="109d2-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="109d2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="109d2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="109d2-104">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="109d2-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="109d2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="109d2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="109d2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="109d2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="109d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="109d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="109d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowInstanceManagement >**</span><span class="sxs-lookup"><span data-stu-id="109d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="109d2-109">구문</span><span class="sxs-lookup"><span data-stu-id="109d2-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="109d2-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="109d2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="109d2-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="109d2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="109d2-112">특성</span><span class="sxs-lookup"><span data-stu-id="109d2-112">Attributes</span></span>  
  
|<span data-ttu-id="109d2-113">특성</span><span class="sxs-lookup"><span data-stu-id="109d2-113">Attribute</span></span>|<span data-ttu-id="109d2-114">Description</span><span class="sxs-lookup"><span data-stu-id="109d2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="109d2-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="109d2-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="109d2-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="109d2-116">Child Elements</span></span>  
 <span data-ttu-id="109d2-117">없음</span><span class="sxs-lookup"><span data-stu-id="109d2-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="109d2-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="109d2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="109d2-119">요소</span><span class="sxs-lookup"><span data-stu-id="109d2-119">Element</span></span>|<span data-ttu-id="109d2-120">설명</span><span class="sxs-lookup"><span data-stu-id="109d2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="109d2-121">\<servicebehaviors의 \<동작 > ></span><span class="sxs-lookup"><span data-stu-id="109d2-121">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="109d2-122">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="109d2-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="109d2-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="109d2-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
