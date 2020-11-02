---
title: 어셈블리 로드 해결
description: 이 문서에서는 .NET AppDomain.AssemblyResolve 이벤트에 대해 설명합니다. 어셈블리 로드를 제어해야 하는 애플리케이션에 이 이벤트를 사용합니다.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET], resolving loads
- application domains, loading assemblies
- resolving assembly loads
- assemblies [.NET], loading
- application domains, resolving assembly loads
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 16f2f61a2a36e4189e98c85b3d3ce706a52e2938
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687273"
---
# <a name="resolve-assembly-loads"></a><span data-ttu-id="b94e6-104">어셈블리 로드 해결</span><span class="sxs-lookup"><span data-stu-id="b94e6-104">Resolve assembly loads</span></span>

<span data-ttu-id="b94e6-105">.NET에서는 어셈블리 로드를 보다 효율적으로 제어해야 하는 애플리케이션에 대해 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-105">.NET provides the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event for applications that require greater control over assembly loading.</span></span> <span data-ttu-id="b94e6-106">이 이벤트를 처리하면 애플리케이션이 정상적인 검색 경로 외부에서 로드 컨텍스트에 어셈블리를 로드하고, 여러 어셈블리 버전 중에서 로드할 버전을 선택하고, 동적 어셈블리를 내보내 반환하는 작업 등을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-106">By handling this event, your application can load an assembly into the load context from outside the normal probing paths, select which of several assembly versions to load, emit a dynamic assembly and return it, and so on.</span></span> <span data-ttu-id="b94e6-107">이 항목에서는 <xref:System.AppDomain.AssemblyResolve> 이벤트 처리 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-107">This topic provides guidance for handling the <xref:System.AppDomain.AssemblyResolve> event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b94e6-108">리플렉션 전용 컨텍스트에서 어셈블리 로드를 확인하려면 <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType> 이벤트를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-108">For resolving assembly loads in the reflection-only context, use the <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType> event instead.</span></span>  
  
## <a name="how-the-assemblyresolve-event-works"></a><span data-ttu-id="b94e6-109">AssemblyResolve 이벤트 작동 방식</span><span class="sxs-lookup"><span data-stu-id="b94e6-109">How the AssemblyResolve event works</span></span>  
 <span data-ttu-id="b94e6-110"><xref:System.AppDomain.AssemblyResolve> 이벤트 처리기를 등록하면 런타임에 이름으로 어셈블리에 바인딩하지 못할 때마다 처리기가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-110">When you register a handler for the <xref:System.AppDomain.AssemblyResolve> event, the handler is invoked whenever the runtime fails to bind to an assembly by name.</span></span> <span data-ttu-id="b94e6-111">예를 들어 사용자 코드에서 다음 메서드를 호출하면 <xref:System.AppDomain.AssemblyResolve> 이벤트가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-111">For example, calling the following methods from user code can cause the <xref:System.AppDomain.AssemblyResolve> event to be raised:</span></span>  
  
- <span data-ttu-id="b94e6-112">첫 번째 인수가 로드할 어셈블리의 표시 이름을 나타내는 문자열(즉, <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> 속성에서 반환되는 문자열)인 <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> 메서드 오버로드 또는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 메서드 오버로드</span><span class="sxs-lookup"><span data-stu-id="b94e6-112">An <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> method overload or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overload whose first argument is a string that represents the display name of the assembly to load (that is, the string returned by the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property).</span></span>  
  
- <span data-ttu-id="b94e6-113">첫 번째 인수가 로드할 어셈블리를 식별하는 <xref:System.Reflection.AssemblyName> 개체인 <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> 메서드 오버로드 또는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 메서드 오버로드</span><span class="sxs-lookup"><span data-stu-id="b94e6-113">An <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> method overload or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overload whose first argument is an <xref:System.Reflection.AssemblyName> object that identifies the assembly to load.</span></span>  
  
- <span data-ttu-id="b94e6-114"><xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> 메서드 오버로드</span><span class="sxs-lookup"><span data-stu-id="b94e6-114">An <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> method overload.</span></span>  
  
- <span data-ttu-id="b94e6-115">다른 애플리케이션 도메인의 개체를 인스턴스화하는 <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> 또는 <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> 메서드 오버로드</span><span class="sxs-lookup"><span data-stu-id="b94e6-115">An <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> method overload that instantiates an object in another application domain.</span></span>  
  
### <a name="what-the-event-handler-does"></a><span data-ttu-id="b94e6-116">이벤트 처리기가 수행하는 작업</span><span class="sxs-lookup"><span data-stu-id="b94e6-116">What the event handler does</span></span>  
 <span data-ttu-id="b94e6-117"><xref:System.AppDomain.AssemblyResolve> 이벤트 처리기는 <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> 속성을 통해 로드할 어셈블리의 표시 이름을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-117">The handler for the <xref:System.AppDomain.AssemblyResolve> event receives the display name of the assembly to be loaded, in the <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="b94e6-118">처리기가 어셈블리 이름을 인식하지 못하는 경우 `null`(C#), `Nothing`(Visual Basic) 또는 `nullptr`(Visual C++)이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-118">If the handler does not recognize the assembly name, it returns `null` (C#), `Nothing` (Visual Basic), or `nullptr` (Visual C++).</span></span>  
  
 <span data-ttu-id="b94e6-119">처리기가 어셈블리 이름을 인식하면 요청을 충족하는 어셈블리를 로드하고 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-119">If the handler recognizes the assembly name, it can load and return an assembly that satisfies the request.</span></span> <span data-ttu-id="b94e6-120">다음 목록에서는 몇 가지 샘플 시나리오를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-120">The following list describes some sample scenarios.</span></span>  
  
- <span data-ttu-id="b94e6-121">처리기가 어셈블리 버전의 위치를 알고 있다면 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> 또는 <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> 메서드를 사용하여 어셈블리를 로드할 수 있으며, 성공할 경우 로드된 어셈블리를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-121">If the handler knows the location of a version of the assembly, it can load the assembly by using the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> method, and can return the loaded assembly if successful.</span></span>  
  
- <span data-ttu-id="b94e6-122">처리기가 바이트 배열로 저장된 어셈블리 데이터베이스에 액세스할 수 있는 경우 바이트 배열을 사용하는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 메서드 오버로드 중 하나를 사용하여 바이트 배열을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-122">If the handler has access to a database of assemblies stored as byte arrays, it can load a byte array by using one of the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overloads that take a byte array.</span></span>  
  
- <span data-ttu-id="b94e6-123">처리기는 동적 어셈블리를 생성하고 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-123">The handler can generate a dynamic assembly and return it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b94e6-124">처리기는 어셈블리를 로드 소스 컨텍스트에 로드하거나, 로드 컨텍스트에 로드하거나, 컨텍스트 없이 로드해야 합니다. 처리기가 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> 또는 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> 메서드를 사용하여 어셈블리를 리플렉션 전용 컨텍스트에 로드하는 경우 <xref:System.AppDomain.AssemblyResolve> 이벤트를 발생시킨 로드 시도가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-124">The handler must load the assembly into the load-from context, into the load context, or without context.If the handler loads the assembly into the reflection-only context by using the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> or the <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> method, the load attempt that raised the <xref:System.AppDomain.AssemblyResolve> event fails.</span></span>  
  
 <span data-ttu-id="b94e6-125">적합한 어셈블리를 반환하는 것은 이벤트 처리기의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-125">It is the responsibility of the event handler to return a suitable assembly.</span></span> <span data-ttu-id="b94e6-126">처리기는 <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> 속성 값을 <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29> 생성자에 전달하여 요청된 어셈블리의 표시 이름을 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-126">The handler can parse the display name of the requested assembly by passing the <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> property value to the <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29> constructor.</span></span> <span data-ttu-id="b94e6-127">.NET Framework 4부터 처리기는 <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> 속성을 사용하여 현재 요청이 다른 어셈블리의 종속성인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-127">Beginning with the .NET Framework 4, the handler can use the <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property to determine whether the current request is a dependency of another assembly.</span></span> <span data-ttu-id="b94e6-128">이 정보는 종속성을 충족하는 어셈블리를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-128">This information can help identify an assembly that will satisfy the dependency.</span></span>  
  
 <span data-ttu-id="b94e6-129">이벤트 처리기는 요청된 버전과 다른 어셈블리 버전을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-129">The event handler can return a different version of the assembly than the version that was requested.</span></span>  
  
 <span data-ttu-id="b94e6-130">대부분의 경우 처리기에서 반환되는 어셈블리는 처리기가 로드하는 컨텍스트에 관계없이 로드 컨텍스트에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-130">In most cases, the assembly that is returned by the handler appears in the load context, regardless of the context the handler loads it into.</span></span> <span data-ttu-id="b94e6-131">예를 들어 처리기가 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> 메서드를 사용하여 어셈블리를 로드 소스 컨텍스트에 로드하는 경우 처리기에서 반환되는 어셈블리는 로드 컨텍스트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-131">For example, if the handler uses the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method to load an assembly into the load-from context, the assembly appears in the load context when the handler returns it.</span></span> <span data-ttu-id="b94e6-132">그러나 다음과 같은 경우에는 처리기에서 반환되는 어셈블리가 컨텍스트 없이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-132">However, in the following case the assembly appears without context when the handler returns it:</span></span>  
  
- <span data-ttu-id="b94e6-133">즉, 처리기가 컨텍스트 없이 어셈블리를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-133">The handler loads an assembly without context.</span></span>  
  
- <span data-ttu-id="b94e6-134"><xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> 속성이 null이 아닌 경우.</span><span class="sxs-lookup"><span data-stu-id="b94e6-134">The <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property is not null.</span></span>  
  
- <span data-ttu-id="b94e6-135">요청하는 어셈블리(즉, <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> 속성에서 반환되는 어셈블리)가 컨텍스트 없이 로드된 경우.</span><span class="sxs-lookup"><span data-stu-id="b94e6-135">The requesting assembly (that is, the assembly that is returned by the <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property) was loaded without context.</span></span>  
  
 <span data-ttu-id="b94e6-136">컨텍스트에 대한 자세한 내용은 <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType> 메서드 오버로드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b94e6-136">For information about contexts, see the <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType> method overload.</span></span>  
  
 <span data-ttu-id="b94e6-137">동일한 어셈블리의 여러 버전을 동일한 애플리케이션 도메인에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-137">Multiple versions of the same assembly can be loaded into the same application domain.</span></span> <span data-ttu-id="b94e6-138">이 방법은 형식 할당 문제를 일으킬 수 있으므로 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-138">This practice is not recommended, because it can lead to type assignment problems.</span></span> <span data-ttu-id="b94e6-139">[최선의 어셈블리 로드 방법](../../framework/deployment/best-practices-for-assembly-loading.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b94e6-139">See [Best practices for assembly loading](../../framework/deployment/best-practices-for-assembly-loading.md).</span></span>  
  
### <a name="what-the-event-handler-should-not-do"></a><span data-ttu-id="b94e6-140">이벤트 처리기에서 수행하지 않아야 하는 작업</span><span class="sxs-lookup"><span data-stu-id="b94e6-140">What the event handler should not do</span></span>  
<span data-ttu-id="b94e6-141"><xref:System.AppDomain.AssemblyResolve> 이벤트 처리의 기본 규칙은 알 수 없는 어셈블리를 반환하지 않아야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-141">The primary rule for handling the <xref:System.AppDomain.AssemblyResolve> event is that you should not try to return an assembly you do not recognize.</span></span> <span data-ttu-id="b94e6-142">처리기를 작성할 때 이벤트를 발생시킬 수 있는 어셈블리를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-142">When you write the handler, you should know which assemblies might cause the event to be raised.</span></span> <span data-ttu-id="b94e6-143">처리기는 다른 어셈블리에 대해 null을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-143">Your handler should return null for other assemblies.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="b94e6-144">.NET Framework 4부터 위성 어셈블리에 대해 <xref:System.AppDomain.AssemblyResolve> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-144">Beginning with the .NET Framework 4, the <xref:System.AppDomain.AssemblyResolve> event is raised for satellite assemblies.</span></span> <span data-ttu-id="b94e6-145">이 변경 내용은 처리기가 모든 어셈블리 로드 요청을 확인하려는 경우 이전 버전의 .NET Framework에 대해 작성된 이벤트 처리기에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-145">This change affects an event handler that was written for an earlier version of the .NET Framework, if the handler tries to resolve all assembly load requests.</span></span> <span data-ttu-id="b94e6-146">인식되지 않는 어셈블리를 무시하는 이벤트 처리기는 이 변경 내용의 영향을 받지 않습니다. null을 반환하고 일반적인 대체 메커니즘을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-146">Event handlers that ignore assemblies they do not recognize are not affected by this change: They return null, and normal fallback mechanisms are followed.</span></span>  

<span data-ttu-id="b94e6-147">어셈블리를 로드할 때 이벤트 처리기는 <xref:System.AppDomain.AssemblyResolve> 이벤트가 재귀적으로 발생될 수 있게 하여 스택 오버플로가 발생할 수 있는 <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> 또는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 메서드 오버로드를 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-147">When loading an assembly, the event handler must not use any of the <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overloads that can cause the <xref:System.AppDomain.AssemblyResolve> event to be raised recursively, because this can lead to a stack overflow.</span></span> <span data-ttu-id="b94e6-148">이 항목의 앞부분에 제공된 목록을 참조하세요. 이 문제는 모든 이벤트 처리기가 반환될 때까지 예외가 throw되지 않기 때문에 로드 요청에 대한 예외 처리를 제공하는 경우에도 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-148">(See the list provided earlier in this topic.) This happens even if you provide exception handling for the load request, because no exception is thrown until all event handlers have returned.</span></span> <span data-ttu-id="b94e6-149">따라서 다음 코드는 `MyAssembly`를 찾을 수 없는 경우 스택 오버플로를 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b94e6-149">Thus, the following code results in a stack overflow if `MyAssembly` is not found:</span></span>  

```cpp
using namespace System;
using namespace System::Reflection;

ref class Example
{
internal:
    static Assembly^ MyHandler(Object^ source, ResolveEventArgs^ e)
    {
        Console::WriteLine("Resolving {0}", e->Name);
        return Assembly::Load(e->Name);
    }
};

void main()
{
    AppDomain^ ad = AppDomain::CreateDomain("Test");
    ad->AssemblyResolve += gcnew ResolveEventHandler(&Example::MyHandler);

    try
    {
        Object^ obj = ad->CreateInstanceAndUnwrap(
            "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
            "MyType");
    }
    catch (Exception^ ex)
    {
        Console::WriteLine(ex->Message);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```csharp
using System;
using System.Reflection;

class BadExample
{
    static void Main()
    {
        AppDomain ad = AppDomain.CreateDomain("Test");
        ad.AssemblyResolve += MyHandler;

        try
        {
            object obj = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType");
        }
        catch (Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
    }

    static Assembly MyHandler(object source, ResolveEventArgs e)
    {
        Console.WriteLine("Resolving {0}", e.Name);
        return Assembly.Load(e.Name);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```vb
Imports System.Reflection

Class BadExample

    Shared Sub Main()

        Dim ad As AppDomain = AppDomain.CreateDomain("Test")
        AddHandler ad.AssemblyResolve, AddressOf MyHandler

        Try
            Dim obj As object = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType")
        Catch ex As Exception
            Console.WriteLine(ex.Message)
        End Try
    End Sub

    Shared Function MyHandler(ByVal source As Object, _
                              ByVal e As ResolveEventArgs) As Assembly
        Console.WriteLine("Resolving {0}", e.Name)
        Return Assembly.Load(e.Name)
    End Function
End Class

' This example produces output similar to the following:
'
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'...
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'
'Process is terminated due to StackOverflowException.
```

## <a name="see-also"></a><span data-ttu-id="b94e6-150">참조</span><span class="sxs-lookup"><span data-stu-id="b94e6-150">See also</span></span>

- [<span data-ttu-id="b94e6-151">최선의 어셈블리 로드 방법</span><span class="sxs-lookup"><span data-stu-id="b94e6-151">Best practices for assembly loading</span></span>](../../framework/deployment/best-practices-for-assembly-loading.md)
- [<span data-ttu-id="b94e6-152">애플리케이션 도메인 사용</span><span class="sxs-lookup"><span data-stu-id="b94e6-152">Use application domains</span></span>](../../framework/app-domains/use.md)
