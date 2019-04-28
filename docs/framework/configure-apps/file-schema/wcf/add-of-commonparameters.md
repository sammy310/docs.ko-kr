---
title: <commonParameters>의 <add>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: 6aaba3f82966ad4496e6edaae06b5d7a8aef3863
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673656"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="81f79-102">\<추가 >의 \<일반 매개 변수 ></span><span class="sxs-lookup"><span data-stu-id="81f79-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="81f79-103">여러 서비스에서 전역적으로 사용되는 매개 변수의 이름-값 쌍을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f79-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="81f79-104">일반적으로 이 매개 변수에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f79-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="81f79-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="81f79-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="81f79-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="81f79-106">\<behaviors></span></span>  
<span data-ttu-id="81f79-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="81f79-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="81f79-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="81f79-108">\<behavior></span></span>  
<span data-ttu-id="81f79-109">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="81f79-109">\<workflowRuntime></span></span>  
<span data-ttu-id="81f79-110">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="81f79-110">\<commonParameters></span></span>  
<span data-ttu-id="81f79-111">\<add></span><span class="sxs-lookup"><span data-stu-id="81f79-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81f79-112">구문</span><span class="sxs-lookup"><span data-stu-id="81f79-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81f79-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="81f79-113">Attributes and Elements</span></span>  
 <span data-ttu-id="81f79-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="81f79-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81f79-115">특성</span><span class="sxs-lookup"><span data-stu-id="81f79-115">Attributes</span></span>  
  
|<span data-ttu-id="81f79-116">특성</span><span class="sxs-lookup"><span data-stu-id="81f79-116">Attribute</span></span>|<span data-ttu-id="81f79-117">설명</span><span class="sxs-lookup"><span data-stu-id="81f79-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81f79-118">name</span><span class="sxs-lookup"><span data-stu-id="81f79-118">name</span></span>|<span data-ttu-id="81f79-119">서비스에 지정한 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="81f79-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="81f79-120">값</span><span class="sxs-lookup"><span data-stu-id="81f79-120">value</span></span>|<span data-ttu-id="81f79-121">서비스에 지정한 매개 변수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="81f79-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81f79-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="81f79-122">Child Elements</span></span>  
 <span data-ttu-id="81f79-123">없음</span><span class="sxs-lookup"><span data-stu-id="81f79-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81f79-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="81f79-124">Parent Elements</span></span>  
  
|<span data-ttu-id="81f79-125">요소</span><span class="sxs-lookup"><span data-stu-id="81f79-125">Element</span></span>|<span data-ttu-id="81f79-126">설명</span><span class="sxs-lookup"><span data-stu-id="81f79-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81f79-127">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="81f79-127">\<commonParameters></span></span>](commonparameters.md)|<span data-ttu-id="81f79-128">서비스에서 사용하는 일반 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="81f79-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="81f79-129">일반적으로 이 컬렉션에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f79-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81f79-130">설명</span><span class="sxs-lookup"><span data-stu-id="81f79-130">Remarks</span></span>  
 <span data-ttu-id="81f79-131">`<commonParameters>` 요소는 여러 서비스에서 전역적으로 사용되는 모든 매개 변수를 정의합니다. 예를 들어 `ConnectionString`를 사용하는 경우 <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="81f79-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="81f79-132">작업 일괄 처리를 지속성 저장소에 커밋하는 서비스(예: <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 및 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>)의 경우 다음 예제와 같이 `EnableRetries` 매개 변수를 사용하여 트랜잭션을 다시 시도하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f79-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="81f79-133">`EnableRetries` 매개 변수에서 전역 수준을 설정할 수 있습니다 (에 표시 된 대로 합니다 *CommonParameters* 섹션) 개인에 대 한 지 원하는 서비스 또는 `EnableRetries` (에서처럼는 *Services*섹션).</span><span class="sxs-lookup"><span data-stu-id="81f79-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="81f79-134">동작을 제어 하려면 구성 파일을 사용 하는 방법은 <xref:System.Workflow.Runtime.WorkflowRuntime> 개체는 Windows Workflow Foundation 호스트 응용 프로그램의 참조 [워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))합니다.</span><span class="sxs-lookup"><span data-stu-id="81f79-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81f79-135">예제</span><span class="sxs-lookup"><span data-stu-id="81f79-135">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="81f79-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="81f79-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="81f79-137">[워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="81f79-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="81f79-138">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="81f79-138">\<commonParameters></span></span>](commonparameters.md)
