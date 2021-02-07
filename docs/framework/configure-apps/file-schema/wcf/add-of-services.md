---
description: '다음에 대 한 자세한 정보:: <add><services>'
title: <services>의 <add>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 868a4ef9fafcc42ca4620880b2c6f1cb499cab4a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750028"
---
# <a name="add-of-services"></a><span data-ttu-id="e33aa-103">\<services>의 \<add></span><span class="sxs-lookup"><span data-stu-id="e33aa-103">\<add> of \<services></span></span>

<span data-ttu-id="e33aa-104"><xref:System.Workflow.Runtime.WorkflowRuntime>WCF (워크플로 기반 Windows Communication Foundation) 서비스를 호스팅하기 위한의 인스턴스에 대 한 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e33aa-104">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="e33aa-105">이 요소는 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e33aa-105">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services-of-workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="e33aa-106">구문</span><span class="sxs-lookup"><span data-stu-id="e33aa-106">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e33aa-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e33aa-107">Attributes and Elements</span></span>  

 <span data-ttu-id="e33aa-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e33aa-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e33aa-109">특성</span><span class="sxs-lookup"><span data-stu-id="e33aa-109">Attributes</span></span>  
  
|<span data-ttu-id="e33aa-110">attribute</span><span class="sxs-lookup"><span data-stu-id="e33aa-110">Attribute</span></span>|<span data-ttu-id="e33aa-111">Description</span><span class="sxs-lookup"><span data-stu-id="e33aa-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e33aa-112">type</span><span class="sxs-lookup"><span data-stu-id="e33aa-112">type</span></span>|<span data-ttu-id="e33aa-113">초기화할 서비스의 정규화된 어셈블리 형식 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e33aa-113">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="e33aa-114">지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e33aa-114">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="e33aa-115">자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e33aa-115">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e33aa-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e33aa-116">Child Elements</span></span>  

 <span data-ttu-id="e33aa-117">없음</span><span class="sxs-lookup"><span data-stu-id="e33aa-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e33aa-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e33aa-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e33aa-119">요소</span><span class="sxs-lookup"><span data-stu-id="e33aa-119">Element</span></span>|<span data-ttu-id="e33aa-120">설명</span><span class="sxs-lookup"><span data-stu-id="e33aa-120">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services-of-workflowruntime.md)|<span data-ttu-id="e33aa-121"><xref:System.Workflow.Runtime.WorkflowRuntime> 엔진에 추가할 서비스 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e33aa-121">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="e33aa-122">요소는 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e33aa-122">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="e33aa-123">컬렉션에 지정된 서비스는 워크플로 런타임 엔진에 의해 초기화되며 해당 <xref:System.Workflow.Runtime.WorkflowRuntime> 생성자를 호출할 때 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e33aa-123">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="e33aa-124">따라서 컬렉션에 지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e33aa-124">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="e33aa-125">자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e33aa-125">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e33aa-126">설명</span><span class="sxs-lookup"><span data-stu-id="e33aa-126">Remarks</span></span>  

 <span data-ttu-id="e33aa-127">이 요소에 지정된 서비스는 워크플로 런타임 엔진에 의해 초기화되며 해당 <xref:System.Workflow.Runtime.WorkflowRuntime> 생성자를 호출할 때 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e33aa-127">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="e33aa-128">따라서 지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e33aa-128">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="e33aa-129">자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e33aa-129">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e33aa-130">예제</span><span class="sxs-lookup"><span data-stu-id="e33aa-130">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e33aa-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e33aa-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="e33aa-132">[워크플로 구성 파일](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e33aa-132">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
