---
title: <ThrowUnobservedTaskExceptions> 요소
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 876452a0a56d10f169526138cdbbbd153572f457
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658845"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="bff60-102">\<ThrowUnobservedTaskExceptions > 요소</span><span class="sxs-lookup"><span data-stu-id="bff60-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="bff60-103">작업 예외가 처리되지 않으면 실행 중인 프로세스를 종료할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="bff60-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bff60-104">\<configuration></span></span>  
<span data-ttu-id="bff60-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="bff60-105">\<runtime></span></span>  
<span data-ttu-id="bff60-106">\<ThrowUnobservedTaskExceptions></span><span class="sxs-lookup"><span data-stu-id="bff60-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bff60-107">구문</span><span class="sxs-lookup"><span data-stu-id="bff60-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bff60-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bff60-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bff60-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bff60-110">특성</span><span class="sxs-lookup"><span data-stu-id="bff60-110">Attributes</span></span>  
  
|<span data-ttu-id="bff60-111">특성</span><span class="sxs-lookup"><span data-stu-id="bff60-111">Attribute</span></span>|<span data-ttu-id="bff60-112">설명</span><span class="sxs-lookup"><span data-stu-id="bff60-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="bff60-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="bff60-114">처리 되지 않은 태스크 예외가 실행 중인 프로세스를 종료할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bff60-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="bff60-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="bff60-116">값</span><span class="sxs-lookup"><span data-stu-id="bff60-116">Value</span></span>|<span data-ttu-id="bff60-117">설명</span><span class="sxs-lookup"><span data-stu-id="bff60-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="bff60-118">처리 되지 않은 작업 예외에 대 한 실행 중인 프로세스를 종료 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="bff60-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="bff60-120">처리 되지 않은 작업 예외에 대 한 실행 중인 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bff60-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bff60-121">Child Elements</span></span>  
 <span data-ttu-id="bff60-122">없음</span><span class="sxs-lookup"><span data-stu-id="bff60-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bff60-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bff60-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bff60-124">요소</span><span class="sxs-lookup"><span data-stu-id="bff60-124">Element</span></span>|<span data-ttu-id="bff60-125">설명</span><span class="sxs-lookup"><span data-stu-id="bff60-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bff60-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bff60-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="bff60-128">설명</span><span class="sxs-lookup"><span data-stu-id="bff60-128">Remarks</span></span>  
 <span data-ttu-id="bff60-129">와 <xref:System.Threading.Tasks.Task> 연결 된 예외가 관찰 되지 않은 경우에는 작업이 없으며 <xref:System.Threading.Tasks.Task.Wait%2A> , 부모가 연결 <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> 되지 않으며, 속성을 읽지 않은 경우 태스크 예외가 관찰 되지 않은으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="bff60-130">.NET Framework 4에서는 기본적으로 관찰 되지 않은 예외가 있는이 가비지 <xref:System.Threading.Tasks.Task> 수집 되는 경우 종료자는 예외를 throw 하 고 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-130">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="bff60-131">프로세스 종료는 가비지 수집 및 종료 시간에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="bff60-132">개발자가 작업을 기반으로 비동기 코드를 보다 쉽게 작성할 수 있도록 .NET Framework 4.5은 관찰 되지 않은 예외에 대 한이 기본 동작을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-132">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="bff60-133">관찰 되지 않은 예외는 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> 여전히 이벤트를 발생 시킵니다. 하지만 기본적으로이 프로세스는 종료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="bff60-134">대신, 이벤트 처리기가 예외를 준수 하는지 여부에 관계 없이 이벤트가 발생 한 후 예외가 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="bff60-135">.NET Framework 4.5에서는 응용 프로그램 구성 파일에서 [ \<ThrowUnobservedTaskExceptions > 요소](throwunobservedtaskexceptions-element.md) 를 사용 하 여 예외를 throw 하는 .NET Framework 4 동작을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-135">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="bff60-136">다음 방법 중 하나로 예외 동작을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="bff60-137">환경 변수 `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`)를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="bff60-138">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\에서 레지스트리 DWORD 값 ThrowUnobservedTaskExceptions = 1을 설정 합니다. NETFramework 키입니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bff60-139">예제</span><span class="sxs-lookup"><span data-stu-id="bff60-139">Example</span></span>  
 <span data-ttu-id="bff60-140">다음 예제에서는 응용 프로그램 구성 파일을 사용 하 여 작업에서 예외를 throw 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="bff60-141">예제</span><span class="sxs-lookup"><span data-stu-id="bff60-141">Example</span></span>  
 <span data-ttu-id="bff60-142">다음 예제에서는 작업에서 관찰 되지 않은 예외가 throw 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="bff60-143">제대로 작동 하려면 코드가 릴리스 된 프로그램으로 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bff60-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="bff60-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="bff60-144">See also</span></span>

- [<span data-ttu-id="bff60-145">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="bff60-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bff60-146">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="bff60-146">Configuration File Schema</span></span>](../index.md)
