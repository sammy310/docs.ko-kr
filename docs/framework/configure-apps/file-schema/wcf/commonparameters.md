---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: b9ab4e8ca5a71d54a80d17322b61c83d41af2b40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673591"
---
# <a name="commonparameters"></a><span data-ttu-id="3b03c-101">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="3b03c-101">\<commonParameters></span></span>
<span data-ttu-id="3b03c-102">여러 서비스에서 전역적으로 사용되는 매개 변수의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3b03c-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="3b03c-103">일반적으로 이 컬렉션에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b03c-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="3b03c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3b03c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3b03c-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3b03c-105">\<behaviors></span></span>  
<span data-ttu-id="3b03c-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="3b03c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="3b03c-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3b03c-107">\<behavior></span></span>  
<span data-ttu-id="3b03c-108">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="3b03c-108">\<workflowRuntime></span></span>  
<span data-ttu-id="3b03c-109">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="3b03c-109">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b03c-110">구문</span><span class="sxs-lookup"><span data-stu-id="3b03c-110">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b03c-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3b03c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3b03c-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b03c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b03c-113">특성</span><span class="sxs-lookup"><span data-stu-id="3b03c-113">Attributes</span></span>  
 <span data-ttu-id="3b03c-114">없음</span><span class="sxs-lookup"><span data-stu-id="3b03c-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3b03c-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3b03c-115">Child Elements</span></span>  
  
|<span data-ttu-id="3b03c-116">요소</span><span class="sxs-lookup"><span data-stu-id="3b03c-116">Element</span></span>|<span data-ttu-id="3b03c-117">설명</span><span class="sxs-lookup"><span data-stu-id="3b03c-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b03c-118">\<add></span><span class="sxs-lookup"><span data-stu-id="3b03c-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|<span data-ttu-id="3b03c-119">서비스에서 사용되는 일반 매개 변수의 이름-값 쌍을 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3b03c-119">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b03c-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3b03c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3b03c-121">요소</span><span class="sxs-lookup"><span data-stu-id="3b03c-121">Element</span></span>|<span data-ttu-id="3b03c-122">설명</span><span class="sxs-lookup"><span data-stu-id="3b03c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b03c-123">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="3b03c-123">\<workflowRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|<span data-ttu-id="3b03c-124">인스턴스에 대 한 설정을 지정 <xref:System.Workflow.Runtime.WorkflowRuntime> 호스팅 워크플로 기반 Windows Communication Foundation (WCF) 서비스에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b03c-124">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b03c-125">설명</span><span class="sxs-lookup"><span data-stu-id="3b03c-125">Remarks</span></span>  
 <span data-ttu-id="3b03c-126">`<commonParameters>` 요소는 여러 서비스에서 전역적으로 사용되는 모든 매개 변수를 정의합니다. 예를 들어 `ConnectionString`를 사용하는 경우 <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3b03c-126">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b03c-127">SQL 추적 서비스에서는 `ConnectionString` 값이 `<commonParameters>` 섹션에 지정된 경우 해당 값을 일관성 있게 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b03c-127">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="3b03c-128">`StateMachineWorkflowInstance.StateHistory` 속성을 검색하는 것과 같은 일부 작업이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b03c-128">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="3b03c-129">이 문제를 해결하려면 다음 예제와 같이 추적 공급자에 대한 구성 섹션에 `ConnectionString` 특성을 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="3b03c-129">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="3b03c-130">작업 일괄 처리를 지속성 저장소에 커밋하는 서비스(예: <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 및 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>)의 경우 다음 예제와 같이 `EnableRetries` 매개 변수를 사용하여 트랜잭션을 다시 시도하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b03c-130">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime,
               Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="3b03c-131">`EnableRetries` 전역 수준에서 매개 변수를 설정할 수 있습니다 (에 표시 된 대로 합니다 *CommonParameters* 섹션) 개인에 대 한 지 원하는 서비스 또는 `EnableRetries` (에서처럼는 *Services*섹션).</span><span class="sxs-lookup"><span data-stu-id="3b03c-131">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="3b03c-132">다음 샘플 코드에서는 일반 매개 변수를 프로그래밍 방식으로 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3b03c-132">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="3b03c-133">동작을 제어 하려면 구성 파일을 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Workflow.Runtime.WorkflowRuntime> 개체는 Windows Workflow Foundation 호스트 응용 프로그램의 참조 [워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))합니다.</span><span class="sxs-lookup"><span data-stu-id="3b03c-133">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b03c-134">예제</span><span class="sxs-lookup"><span data-stu-id="3b03c-134">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="3b03c-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="3b03c-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="3b03c-136">[워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3b03c-136">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="3b03c-137">\<add></span><span class="sxs-lookup"><span data-stu-id="3b03c-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)
