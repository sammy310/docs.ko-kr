---
description: '다음에 대 한 자세한 정보: <ThrowUnobservedTaskExceptions> 요소'
title: <ThrowUnobservedTaskExceptions> 요소
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
ms.openlocfilehash: 53f3f1275ea8419bed52fd73726c043e1c49eed7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802400"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="c7be7-103">\<ThrowUnobservedTaskExceptions> 요소</span><span class="sxs-lookup"><span data-stu-id="c7be7-103">\<ThrowUnobservedTaskExceptions> Element</span></span>

<span data-ttu-id="c7be7-104">작업 예외가 처리되지 않으면 실행 중인 프로세스를 종료할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-104">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**  
  
## <a name="syntax"></a><span data-ttu-id="c7be7-105">구문</span><span class="sxs-lookup"><span data-stu-id="c7be7-105">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7be7-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c7be7-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c7be7-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7be7-108">특성</span><span class="sxs-lookup"><span data-stu-id="c7be7-108">Attributes</span></span>  
  
|<span data-ttu-id="c7be7-109">attribute</span><span class="sxs-lookup"><span data-stu-id="c7be7-109">Attribute</span></span>|<span data-ttu-id="c7be7-110">설명</span><span class="sxs-lookup"><span data-stu-id="c7be7-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c7be7-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="c7be7-112">처리 되지 않은 태스크 예외가 실행 중인 프로세스를 종료할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-112">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c7be7-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="c7be7-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="c7be7-114">값</span><span class="sxs-lookup"><span data-stu-id="c7be7-114">Value</span></span>|<span data-ttu-id="c7be7-115">설명</span><span class="sxs-lookup"><span data-stu-id="c7be7-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c7be7-116">처리 되지 않은 작업 예외에 대 한 실행 중인 프로세스를 종료 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-116">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="c7be7-117">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-117">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c7be7-118">처리 되지 않은 작업 예외에 대 한 실행 중인 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-118">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7be7-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c7be7-119">Child Elements</span></span>  

 <span data-ttu-id="c7be7-120">없음</span><span class="sxs-lookup"><span data-stu-id="c7be7-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7be7-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c7be7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c7be7-122">요소</span><span class="sxs-lookup"><span data-stu-id="c7be7-122">Element</span></span>|<span data-ttu-id="c7be7-123">설명</span><span class="sxs-lookup"><span data-stu-id="c7be7-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c7be7-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c7be7-125">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-125">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="c7be7-126">설명</span><span class="sxs-lookup"><span data-stu-id="c7be7-126">Remarks</span></span>  

 <span data-ttu-id="c7be7-127">와 연결 된 예외가 관찰 되지 않은 경우에는 <xref:System.Threading.Tasks.Task> <xref:System.Threading.Tasks.Task.Wait%2A> 작업이 없으며, 부모가 연결 되지 않으며, 속성을 읽지 않은 경우 <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> 태스크 예외가 관찰 되지 않은으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-127">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="c7be7-128">.NET Framework 4에서는 기본적으로 <xref:System.Threading.Tasks.Task> 관찰 되지 않은 예외가 있는이 가비지 수집 되는 경우 종료자는 예외를 throw 하 고 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-128">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="c7be7-129">프로세스 종료는 가비지 수집 및 종료 시간에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-129">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="c7be7-130">개발자가 작업을 기반으로 비동기 코드를 보다 쉽게 작성할 수 있도록 .NET Framework 4.5은 관찰 되지 않은 예외에 대 한이 기본 동작을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-130">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="c7be7-131">관찰 되지 않은 예외는 여전히 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> 이벤트를 발생 시킵니다. 하지만 기본적으로이 프로세스는 종료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-131">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="c7be7-132">대신, 이벤트 처리기가 예외를 준수 하는지 여부에 관계 없이 이벤트가 발생 한 후 예외가 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-132">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="c7be7-133">.NET Framework 4.5에서는 응용 프로그램 구성 파일의 [ \<ThrowUnobservedTaskExceptions> 요소](throwunobservedtaskexceptions-element.md) 를 사용 하 여 예외를 throw 하는 .NET Framework 4 동작을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-133">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="c7be7-134">다음 방법 중 하나로 예외 동작을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-134">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="c7be7-135">환경 변수 `COMPlus_ThrowUnobservedTaskExceptions` ()를 설정 `set COMPlus_ThrowUnobservedTaskExceptions=1` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-135">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="c7be7-136">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft에서 레지스트리 DWORD 값 ThrowUnobservedTaskExceptions = 1을 설정 \\ 합니다. NETFramework 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-136">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7be7-137">예제</span><span class="sxs-lookup"><span data-stu-id="c7be7-137">Example</span></span>  

 <span data-ttu-id="c7be7-138">다음 예제에서는 응용 프로그램 구성 파일을 사용 하 여 작업에서 예외를 throw 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-138">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="c7be7-139">예제</span><span class="sxs-lookup"><span data-stu-id="c7be7-139">Example</span></span>  

 <span data-ttu-id="c7be7-140">다음 예제에서는 작업에서 관찰 되지 않은 예외가 throw 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-140">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="c7be7-141">제대로 작동 하려면 코드가 릴리스 된 프로그램으로 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7be7-141">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c7be7-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7be7-142">See also</span></span>

- [<span data-ttu-id="c7be7-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c7be7-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c7be7-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c7be7-144">Configuration File Schema</span></span>](../index.md)
