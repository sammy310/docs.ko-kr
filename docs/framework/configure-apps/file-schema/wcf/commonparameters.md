---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: ab21be7b5e2738ac6a7c9bea676d8180c69d1afd
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968561"
---
# <a name="commonparameters"></a><span data-ttu-id="158e5-101">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="158e5-101">\<commonParameters></span></span>
<span data-ttu-id="158e5-102">여러 서비스에서 전역적으로 사용되는 매개 변수의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="158e5-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="158e5-103">이 컬렉션에는 일반적으로 영 속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="158e5-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
<span data-ttu-id="158e5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="158e5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="158e5-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="158e5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="158e5-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**동작**](behaviors.md) ></span><span class="sxs-lookup"><span data-stu-id="158e5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\</span></span>
<span data-ttu-id="158e5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors**](servicebehaviors.md) ></span><span class="sxs-lookup"><span data-stu-id="158e5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="158e5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="158e5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="158e5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**workflowRuntime >** ](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="158e5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="158e5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**commonParameters >**</span><span class="sxs-lookup"><span data-stu-id="158e5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<commonParameters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="158e5-111">구문</span><span class="sxs-lookup"><span data-stu-id="158e5-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="158e5-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="158e5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="158e5-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="158e5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="158e5-114">특성</span><span class="sxs-lookup"><span data-stu-id="158e5-114">Attributes</span></span>  
 <span data-ttu-id="158e5-115">없음.</span><span class="sxs-lookup"><span data-stu-id="158e5-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="158e5-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="158e5-116">Child Elements</span></span>  
  
|<span data-ttu-id="158e5-117">요소</span><span class="sxs-lookup"><span data-stu-id="158e5-117">Element</span></span>|<span data-ttu-id="158e5-118">설명</span><span class="sxs-lookup"><span data-stu-id="158e5-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="158e5-119">\<add></span><span class="sxs-lookup"><span data-stu-id="158e5-119">\<add></span></span>](add-of-commonparameters.md)|<span data-ttu-id="158e5-120">서비스에서 사용되는 일반 매개 변수의 이름-값 쌍을 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="158e5-120">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="158e5-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="158e5-121">Parent Elements</span></span>  
  
|<span data-ttu-id="158e5-122">요소</span><span class="sxs-lookup"><span data-stu-id="158e5-122">Element</span></span>|<span data-ttu-id="158e5-123">설명</span><span class="sxs-lookup"><span data-stu-id="158e5-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="158e5-124">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="158e5-124">\<workflowRuntime></span></span>](workflowruntime.md)|<span data-ttu-id="158e5-125">WCF (워크플로 기반 Windows Communication Foundation) 서비스를 호스팅하기 위한 <xref:System.Workflow.Runtime.WorkflowRuntime>의 인스턴스에 대 한 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="158e5-125">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="158e5-126">주의</span><span class="sxs-lookup"><span data-stu-id="158e5-126">Remarks</span></span>  
 <span data-ttu-id="158e5-127">`<commonParameters>` 요소는 여러 서비스에서 전역적으로 사용되는 모든 매개 변수를 정의합니다. 예를 들어 `ConnectionString`를 사용하는 경우 <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="158e5-127">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="158e5-128">SQL 추적 서비스에서는 `ConnectionString` 값이 `<commonParameters>` 섹션에 지정된 경우 해당 값을 일관성 있게 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="158e5-128">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="158e5-129">`StateMachineWorkflowInstance.StateHistory` 속성을 검색하는 것과 같은 일부 작업이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158e5-129">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="158e5-130">이 문제를 해결하려면 다음 예제와 같이 추적 공급자에 대한 구성 섹션에 `ConnectionString` 특성을 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="158e5-130">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  

```xml  
<add
type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" 
ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />
```  
  
 <span data-ttu-id="158e5-131">작업 일괄 처리를 지속성 저장소에 커밋하는 서비스(예: <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 및 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>)의 경우 다음 예제와 같이 `EnableRetries` 매개 변수를 사용하여 트랜잭션을 다시 시도하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158e5-131">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="158e5-132">`EnableRetries` 매개 변수는 *CommonParameters* 섹션과 같이 전역 수준에서 설정 하거나 `EnableRetries`를 지 원하는 개별 서비스 ( *서비스* 섹션에서 볼 수 있음)에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158e5-132">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="158e5-133">다음 샘플 코드는 일반 매개 변수를 프로그래밍 방식으로 변경 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="158e5-133">The following sample code shows how to change the common parameters programmatically:</span></span>
  
```csharp  
Configuration config = WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");
var wfruntime = config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters = wfruntime.CommonParameters;
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="158e5-134">구성 파일을 사용 하 여 Windows Workflow Foundation 호스트 응용 프로그램의 <xref:System.Workflow.Runtime.WorkflowRuntime> 개체 동작을 제어 하는 방법에 대 한 자세한 내용은 [워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="158e5-134">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="158e5-135">예제</span><span class="sxs-lookup"><span data-stu-id="158e5-135">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="158e5-136">참조</span><span class="sxs-lookup"><span data-stu-id="158e5-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="158e5-137">[워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="158e5-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="158e5-138">\<add></span><span class="sxs-lookup"><span data-stu-id="158e5-138">\<add></span></span>](add-of-commonparameters.md)
