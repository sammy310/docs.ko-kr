---
title: <services>의 <add>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: dc769097a3aede2522c1fa7a4cf8e36c2d8fdfe8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398285"
---
# <a name="add-of-services"></a><span data-ttu-id="2ba3b-102">\<서비스의 \<> 추가 ></span><span class="sxs-lookup"><span data-stu-id="2ba3b-102">\<add> of \<services></span></span>
<span data-ttu-id="2ba3b-103">WCF (워크플로 기반 Windows Communication Foundation) <xref:System.Workflow.Runtime.WorkflowRuntime> 서비스를 호스팅하기 위한의 인스턴스에 대 한 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="2ba3b-104">이 요소는 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
<span data-ttu-id="2ba3b-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2ba3b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2ba3b-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2ba3b-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2ba3b-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2ba3b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2ba3b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2ba3b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="2ba3b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2ba3b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="2ba3b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowRuntime >** ](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="2ba3b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="2ba3b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<서비스 >** ](services-of-workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="2ba3b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services-of-workflowruntime.md)</span></span>\
<span data-ttu-id="2ba3b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="2ba3b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba3b-113">구문</span><span class="sxs-lookup"><span data-stu-id="2ba3b-113">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ba3b-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2ba3b-114">Attributes and Elements</span></span>  
 <span data-ttu-id="2ba3b-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ba3b-116">특성</span><span class="sxs-lookup"><span data-stu-id="2ba3b-116">Attributes</span></span>  
  
|<span data-ttu-id="2ba3b-117">특성</span><span class="sxs-lookup"><span data-stu-id="2ba3b-117">Attribute</span></span>|<span data-ttu-id="2ba3b-118">Description</span><span class="sxs-lookup"><span data-stu-id="2ba3b-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ba3b-119">type</span><span class="sxs-lookup"><span data-stu-id="2ba3b-119">type</span></span>|<span data-ttu-id="2ba3b-120">초기화할 서비스의 정규화된 어셈블리 형식 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-120">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="2ba3b-121">지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-121">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="2ba3b-122">자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-122">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ba3b-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2ba3b-123">Child Elements</span></span>  
 <span data-ttu-id="2ba3b-124">없음</span><span class="sxs-lookup"><span data-stu-id="2ba3b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ba3b-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2ba3b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2ba3b-126">요소</span><span class="sxs-lookup"><span data-stu-id="2ba3b-126">Element</span></span>|<span data-ttu-id="2ba3b-127">Description</span><span class="sxs-lookup"><span data-stu-id="2ba3b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ba3b-128">\<services></span><span class="sxs-lookup"><span data-stu-id="2ba3b-128">\<services></span></span>](services-of-workflowruntime.md)|<span data-ttu-id="2ba3b-129"><xref:System.Workflow.Runtime.WorkflowRuntime> 엔진에 추가할 서비스 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-129">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="2ba3b-130">요소는 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-130">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="2ba3b-131">컬렉션에 지정된 서비스는 워크플로 런타임 엔진에 의해 초기화되며 해당 <xref:System.Workflow.Runtime.WorkflowRuntime> 생성자를 호출할 때 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-131">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="2ba3b-132">따라서 컬렉션에 지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-132">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="2ba3b-133">자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-133">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ba3b-134">설명</span><span class="sxs-lookup"><span data-stu-id="2ba3b-134">Remarks</span></span>  
 <span data-ttu-id="2ba3b-135">이 요소에 지정된 서비스는 워크플로 런타임 엔진에 의해 초기화되며 해당 <xref:System.Workflow.Runtime.WorkflowRuntime> 생성자를 호출할 때 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-135">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="2ba3b-136">따라서 지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-136">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="2ba3b-137">자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-137">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ba3b-138">예제</span><span class="sxs-lookup"><span data-stu-id="2ba3b-138">Example</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="ServiceBehavior">
    <workflowRuntime name="WorkflowServiceHostRuntime"
                     validateOnCreate="true"
                     enablePerformanceCounters="true">
      <services>
        <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common" />
      </services>
    </workflowRuntime>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="2ba3b-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="2ba3b-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="2ba3b-140">[워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2ba3b-140">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
