---
title: <commonParameters>의 <add>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: d682acd7fff6bab2c66660a028f8a75b780e21d2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400676"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="5d3a0-102">\<\<commonParameters > > 추가</span><span class="sxs-lookup"><span data-stu-id="5d3a0-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="5d3a0-103">여러 서비스에서 전역적으로 사용되는 매개 변수의 이름-값 쌍을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3a0-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="5d3a0-104">일반적으로 이 매개 변수에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3a0-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
<span data-ttu-id="5d3a0-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d3a0-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5d3a0-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5d3a0-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5d3a0-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5d3a0-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="5d3a0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5d3a0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="5d3a0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5d3a0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="5d3a0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowRuntime >** ](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="5d3a0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="5d3a0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<commonParameters >** ](commonparameters.md)</span><span class="sxs-lookup"><span data-stu-id="5d3a0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<commonParameters>**](commonparameters.md)</span></span>\
<span data-ttu-id="5d3a0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="5d3a0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d3a0-113">구문</span><span class="sxs-lookup"><span data-stu-id="5d3a0-113">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d3a0-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5d3a0-114">Attributes and Elements</span></span>  
 <span data-ttu-id="5d3a0-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3a0-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d3a0-116">특성</span><span class="sxs-lookup"><span data-stu-id="5d3a0-116">Attributes</span></span>  
  
|<span data-ttu-id="5d3a0-117">특성</span><span class="sxs-lookup"><span data-stu-id="5d3a0-117">Attribute</span></span>|<span data-ttu-id="5d3a0-118">Description</span><span class="sxs-lookup"><span data-stu-id="5d3a0-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d3a0-119">name</span><span class="sxs-lookup"><span data-stu-id="5d3a0-119">name</span></span>|<span data-ttu-id="5d3a0-120">서비스에 지정한 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5d3a0-120">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="5d3a0-121">value</span><span class="sxs-lookup"><span data-stu-id="5d3a0-121">value</span></span>|<span data-ttu-id="5d3a0-122">서비스에 지정한 매개 변수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5d3a0-122">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d3a0-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5d3a0-123">Child Elements</span></span>  
 <span data-ttu-id="5d3a0-124">없음</span><span class="sxs-lookup"><span data-stu-id="5d3a0-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d3a0-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5d3a0-125">Parent Elements</span></span>  
  
|<span data-ttu-id="5d3a0-126">요소</span><span class="sxs-lookup"><span data-stu-id="5d3a0-126">Element</span></span>|<span data-ttu-id="5d3a0-127">Description</span><span class="sxs-lookup"><span data-stu-id="5d3a0-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d3a0-128">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="5d3a0-128">\<commonParameters></span></span>](commonparameters.md)|<span data-ttu-id="5d3a0-129">서비스에서 사용하는 일반 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5d3a0-129">A collection of common parameters used by services.</span></span> <span data-ttu-id="5d3a0-130">일반적으로 이 컬렉션에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3a0-130">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d3a0-131">설명</span><span class="sxs-lookup"><span data-stu-id="5d3a0-131">Remarks</span></span>  
 <span data-ttu-id="5d3a0-132">`<commonParameters>` 요소는 여러 서비스에서 전역적으로 사용되는 모든 매개 변수를 정의합니다. 예를 들어 `ConnectionString`를 사용하는 경우 <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3a0-132">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="5d3a0-133">작업 일괄 처리를 지속성 저장소에 커밋하는 서비스(예: <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 및 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>)의 경우 다음 예제와 같이 `EnableRetries` 매개 변수를 사용하여 트랜잭션을 다시 시도하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3a0-133">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<workflowRuntime name="SampleApplication"
                 unloadOnIdle="false">
  <commonParameters>
    <add name="ConnectionString"
         value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
    <add name="EnableRetries"
         value="True" />
  </commonParameters>
  <services>
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="5d3a0-134">매개 변수는 `EnableRetries` 전역 수준 ( *CommonParameters* 섹션에 표시) 또는을 지 원하는 `EnableRetries` 개별 서비스 ( *서비스* 섹션에 표시 된 대로)에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3a0-134">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="5d3a0-135">구성 파일을 사용 하 여 Windows Workflow Foundation 호스트 응용 프로그램 <xref:System.Workflow.Runtime.WorkflowRuntime> 개체의 동작을 제어 하는 방법에 대 한 자세한 내용은 [워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d3a0-135">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d3a0-136">예제</span><span class="sxs-lookup"><span data-stu-id="5d3a0-136">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="5d3a0-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d3a0-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="5d3a0-138">[워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5d3a0-138">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="5d3a0-139">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="5d3a0-139">\<commonParameters></span></span>](commonparameters.md)
