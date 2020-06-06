---
title: <commonParameters>의 <add>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: d682acd7fff6bab2c66660a028f8a75b780e21d2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400676"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="8ddcc-102">\<commonParameters>의 \<add></span><span class="sxs-lookup"><span data-stu-id="8ddcc-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="8ddcc-103">여러 서비스에서 전역적으로 사용되는 매개 변수의 이름-값 쌍을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ddcc-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="8ddcc-104">일반적으로 이 매개 변수에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ddcc-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<commonParameters>**](commonparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="8ddcc-105">구문</span><span class="sxs-lookup"><span data-stu-id="8ddcc-105">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ddcc-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8ddcc-106">Attributes and Elements</span></span>  
 <span data-ttu-id="8ddcc-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ddcc-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ddcc-108">특성</span><span class="sxs-lookup"><span data-stu-id="8ddcc-108">Attributes</span></span>  
  
|<span data-ttu-id="8ddcc-109">attribute</span><span class="sxs-lookup"><span data-stu-id="8ddcc-109">Attribute</span></span>|<span data-ttu-id="8ddcc-110">Description</span><span class="sxs-lookup"><span data-stu-id="8ddcc-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ddcc-111">name</span><span class="sxs-lookup"><span data-stu-id="8ddcc-111">name</span></span>|<span data-ttu-id="8ddcc-112">서비스에 지정한 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ddcc-112">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="8ddcc-113">값</span><span class="sxs-lookup"><span data-stu-id="8ddcc-113">value</span></span>|<span data-ttu-id="8ddcc-114">서비스에 지정한 매개 변수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ddcc-114">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ddcc-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8ddcc-115">Child Elements</span></span>  
 <span data-ttu-id="8ddcc-116">없음</span><span class="sxs-lookup"><span data-stu-id="8ddcc-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ddcc-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8ddcc-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8ddcc-118">요소</span><span class="sxs-lookup"><span data-stu-id="8ddcc-118">Element</span></span>|<span data-ttu-id="8ddcc-119">Description</span><span class="sxs-lookup"><span data-stu-id="8ddcc-119">Description</span></span>|  
|-------------|-----------------|  
|[\<commonParameters>](commonparameters.md)|<span data-ttu-id="8ddcc-120">서비스에서 사용하는 일반 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8ddcc-120">A collection of common parameters used by services.</span></span> <span data-ttu-id="8ddcc-121">일반적으로 이 컬렉션에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ddcc-121">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ddcc-122">설명</span><span class="sxs-lookup"><span data-stu-id="8ddcc-122">Remarks</span></span>  
 <span data-ttu-id="8ddcc-123">`<commonParameters>` 요소는 여러 서비스에서 전역적으로 사용되는 모든 매개 변수를 정의합니다. 예를 들어 `ConnectionString`를 사용하는 경우 <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8ddcc-123">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="8ddcc-124">작업 일괄 처리를 지속성 저장소에 커밋하는 서비스(예: <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 및 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>)의 경우 다음 예제와 같이 `EnableRetries` 매개 변수를 사용하여 트랜잭션을 다시 시도하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ddcc-124">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="8ddcc-125">`EnableRetries`매개 변수는 전역 수준 ( *CommonParameters* 섹션에 표시) 또는을 지 원하는 개별 서비스 `EnableRetries` ( *서비스* 섹션에 표시 된 대로)에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ddcc-125">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="8ddcc-126">구성 파일을 사용 하 여 Windows Workflow Foundation 호스트 응용 프로그램 개체의 동작을 제어 하는 방법에 대 한 자세한 내용은 <xref:System.Workflow.Runtime.WorkflowRuntime> [워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ddcc-126">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ddcc-127">예제</span><span class="sxs-lookup"><span data-stu-id="8ddcc-127">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="8ddcc-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ddcc-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="8ddcc-129">[워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8ddcc-129">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [\<commonParameters>](commonparameters.md)
