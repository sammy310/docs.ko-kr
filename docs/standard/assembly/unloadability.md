---
title: .NET Core에서 어셈블리 언로드 기능을 사용하고 디버그하는 방법
description: 수집 가능한 AssemblyLoadContext를 사용하여 관리형 어셈블리를 로드하고 언로드하는 방법과 언로드를 성공하지 못하게 하는 문제를 디버그하는 방법을 알아봅니다.
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: 9d1f604816dcbd7a84a3692b3cfd24481532789a
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865348"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="5078c-103">.NET Core에서 어셈블리 언로드 기능을 사용하고 디버그하는 방법</span><span class="sxs-lookup"><span data-stu-id="5078c-103">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="5078c-104">.NET Core 3.0부터 어셈블리 집합을 로드하고 나중에 언로드하는 기능이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-104">Starting with .NET Core 3.0, the ability to load and later unload a set of assemblies is supported.</span></span> <span data-ttu-id="5078c-105">.NET Framework에서 사용자 지정 앱 도메인은 이러한 용도로 사용되지만 .NET Core에서는 단일 기본 앱 도메인만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-105">In .NET Framework, custom app domains were used for this purpose, but .NET Core only supports a single default app domain.</span></span>

<span data-ttu-id="5078c-106">.NET Core 3.0 이상 버전에서는 <xref:System.Runtime.Loader.AssemblyLoadContext>를 통해 언로드 가능성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-106">.NET Core 3.0 and later versions support unloadability through <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="5078c-107">어셈블리 집합을 수집 가능한 `AssemblyLoadContext`에 로드하고, 해당 어셈블리에서 메서드를 실행하거나 리플렉션을 사용하여 검사만 한 다음, 마지막으로 `AssemblyLoadContext`를 언로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-107">You can load a set of assemblies into a collectible `AssemblyLoadContext`, execute methods in them or just inspect them using reflection, and finally unload the `AssemblyLoadContext`.</span></span> <span data-ttu-id="5078c-108">그러면 `AssemblyLoadContext`에 로드된 어셈블리를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-108">That unloads the assemblies loaded into the `AssemblyLoadContext`.</span></span>

<span data-ttu-id="5078c-109">`AssemblyLoadContext`를 사용하여 언로드하는 것과 AppDomain을 사용하여 언로드하는 데는 중요한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-109">There's one noteworthy difference between the unloading using `AssemblyLoadContext` and using AppDomains.</span></span> <span data-ttu-id="5078c-110">AppDomain을 사용하면 언로드가 강제로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-110">With AppDomains, the unloading is forced.</span></span> <span data-ttu-id="5078c-111">언로드 시 대상 AppDomain에서 실행 중인 모든 스레드가 중단되고 대상 AppDomain에서 만들어진 관리형 COM 개체가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-111">At unload time, all threads running in the target AppDomain are aborted, managed COM objects created in the target AppDomain are destroyed, and so on.</span></span> <span data-ttu-id="5078c-112">`AssemblyLoadContext`에서 언로드는 “협조적”입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-112">With `AssemblyLoadContext`, the unload is "cooperative".</span></span> <span data-ttu-id="5078c-113"><xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> 메서드를 호출하면 언로드를 시작하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-113">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> method just initiates the unloading.</span></span> <span data-ttu-id="5078c-114">다음과 같은 경우 언로드가 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-114">The unloading finishes after:</span></span>

- <span data-ttu-id="5078c-115">호출 스택에서 `AssemblyLoadContext`에 로드된 어셈블리의 메서드가 있는 스레드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-115">No threads have methods from the assemblies loaded into the `AssemblyLoadContext` on their call stacks.</span></span>
- <span data-ttu-id="5078c-116">`AssemblyLoadContext`에 로드된 어셈블리의 유형, 해당 유형의 인스턴스 및 어셈블리 자체는 다음에서 참조하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-116">None of the types from the assemblies loaded into the `AssemblyLoadContext`, instances of those types, and the assemblies themselves are referenced by:</span></span>
  - <span data-ttu-id="5078c-117">약한 참조(<xref:System.WeakReference> 또는 <xref:System.WeakReference%601>)를 제외한 `AssemblyLoadContext` 외부의 참조.</span><span class="sxs-lookup"><span data-stu-id="5078c-117">References outside of the `AssemblyLoadContext`, except of weak references (<xref:System.WeakReference> or <xref:System.WeakReference%601>).</span></span>
  - <span data-ttu-id="5078c-118">`AssemblyLoadContext` 내부 및 외부로부터의 강력한 GC(가비지 수집기) 핸들([GCHandleType.Normal](xref:System.Runtime.InteropServices.GCHandleType.Normal) 또는 [GCHandleType.Pinned](xref:System.Runtime.InteropServices.GCHandleType.Pinned)).</span><span class="sxs-lookup"><span data-stu-id="5078c-118">Strong garbage collector (GC) handles ([GCHandleType.Normal](xref:System.Runtime.InteropServices.GCHandleType.Normal) or [GCHandleType.Pinned](xref:System.Runtime.InteropServices.GCHandleType.Pinned)) from both inside and outside of the `AssemblyLoadContext`.</span></span>

## <a name="use-collectible-assemblyloadcontext"></a><span data-ttu-id="5078c-119">수집 가능한 AssemblyLoadContext 사용</span><span class="sxs-lookup"><span data-stu-id="5078c-119">Use collectible AssemblyLoadContext</span></span>

<span data-ttu-id="5078c-120">이 섹션에는 .NET Core 애플리케이션을 수집 가능한 `AssemblyLoadContext`에 로드하고, 진입점을 실행한 다음, 언로드하는 간단한 방법을 보여주는 자세한 단계별 자습서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-120">This section contains a detailed step-by-step tutorial that shows a simple way to load a .NET Core application into a collectible `AssemblyLoadContext`, execute its entry point, and then unload it.</span></span> <span data-ttu-id="5078c-121">[https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading)에서 전체 샘플을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-121">You can find a complete sample at [https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading).</span></span>

### <a name="create-a-collectible-assemblyloadcontext"></a><span data-ttu-id="5078c-122">수집 가능한 AssemblyLoadContext 만들기</span><span class="sxs-lookup"><span data-stu-id="5078c-122">Create a collectible AssemblyLoadContext</span></span>

<span data-ttu-id="5078c-123"><xref:System.Runtime.Loader.AssemblyLoadContext>에서 클래스를 파생시키고 <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-123">You need to derive your class from the <xref:System.Runtime.Loader.AssemblyLoadContext> and override its <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5078c-124">이 메서드는 해당 `AssemblyLoadContext`에 로드된 어셈블리의 종속 항목인 모든 어셈블리의 참조를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-124">That method resolves references to all assemblies that are dependencies of assemblies loaded into that `AssemblyLoadContext`.</span></span>

<span data-ttu-id="5078c-125">다음 코드는 가장 간단한 사용자 지정 `AssemblyLoadContext`의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-125">The following code is an example of the simplest custom `AssemblyLoadContext`:</span></span>

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

<span data-ttu-id="5078c-126">여기에서 볼 수 있듯이 `Load` 메서드는 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-126">As you can see, the `Load` method returns `null`.</span></span> <span data-ttu-id="5078c-127">즉, 모든 종속성 어셈블리가 기본 컨텍스트에 로드되고 새 컨텍스트에는 명시적으로 로드된 어셈블리만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-127">That means that all the dependency assemblies are loaded into the default context, and the new context contains only the assemblies explicitly loaded into it.</span></span>

<span data-ttu-id="5078c-128">종속 항목의 일부 또는 전체를 `AssemblyLoadContext`에 로드하려는 경우 `Load` 메서드에서 `AssemblyDependencyResolver`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-128">If you want to load some or all of the dependencies into the `AssemblyLoadContext` too, you can use the `AssemblyDependencyResolver` in the `Load` method.</span></span> <span data-ttu-id="5078c-129">`AssemblyDependencyResolver`는 어셈블리 이름을 절대 어셈블리 파일 경로로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-129">The `AssemblyDependencyResolver` resolves the assembly names to absolute assembly file paths.</span></span> <span data-ttu-id="5078c-130">확인자는 컨텍스트에 로드된 주 어셈블리의 디렉터리에 있는 *.deps.json* 파일 및 어셈블리 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-130">The resolver uses the *.deps.json* file and assembly files in the directory of the main assembly loaded into the context.</span></span>

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a><span data-ttu-id="5078c-131">수집 가능한 사용자 지정 AssemblyLoadContext 사용</span><span class="sxs-lookup"><span data-stu-id="5078c-131">Use a custom collectible AssemblyLoadContext</span></span>

<span data-ttu-id="5078c-132">이 섹션에서는 `TestAssemblyLoadContext`의 간단한 버전을 사용한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-132">This section assumes the simpler version of the `TestAssemblyLoadContext` is being used.</span></span>

<span data-ttu-id="5078c-133">사용자 지정 `AssemblyLoadContext`의 인스턴스를 만들고 다음과 같이 어셈블리를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-133">You can create an instance of the custom `AssemblyLoadContext` and load an assembly into it as follows:</span></span>

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

<span data-ttu-id="5078c-134">로드된 어셈블리에서 참조하는 각 어셈블리에 대해 `TestAssemblyLoadContext.Load` 메서드를 호출하므로, `TestAssemblyLoadContext`에서 어셈블리를 가져올 위치를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-134">For each of the assemblies referenced by the loaded assembly, the `TestAssemblyLoadContext.Load` method is called so that the `TestAssemblyLoadContext` can decide where to get the assembly from.</span></span> <span data-ttu-id="5078c-135">이 경우 `null`을 반환하여, 런타임에서 기본적으로 어셈블리를 로드하는 데 사용하는 위치에서 기본 컨텍스트에 로드되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-135">In our case, it returns `null` to indicate that it should be loaded into the default context from locations that the runtime uses to load assemblies by default.</span></span>

<span data-ttu-id="5078c-136">이제 어셈블리가 로드되었으므로 여기에서 메서드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-136">Now that an assembly was loaded, you can execute a method from it.</span></span> <span data-ttu-id="5078c-137">다음과 같이 `Main` 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-137">Run the `Main` method:</span></span>

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

<span data-ttu-id="5078c-138">`Main` 메서드가 리턴하고 나면 사용자 지정 `AssemblyLoadContext`에서 `Unload` 메서드를 호출하거나 `AssemblyLoadContext`에 대한 참조를 제거하여 언로드를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-138">After the `Main` method returns, you can initiate unloading by either calling the `Unload` method on the custom `AssemblyLoadContext` or getting rid of the reference you have to the `AssemblyLoadContext`:</span></span>

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

<span data-ttu-id="5078c-139">그러면 테스트 어셈블리를 언로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-139">This is sufficient to unload the test assembly.</span></span> <span data-ttu-id="5078c-140">`TestAssemblyLoadContext`, `Assembly` 및 `MethodInfo`(`Assembly.EntryPoint`)가 스택 슬롯 참조를 통해 활성 상태를 유지할 수 없도록(real 또는 Jit 도입 로컬) 인라인화할 수 없는 개별 메서드로 이 모두를 통합해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-140">Let's actually put all of this into a separate non-inlineable method to ensure that the `TestAssemblyLoadContext`, `Assembly`, and `MethodInfo` (the `Assembly.EntryPoint`) can't be kept alive by stack slot references (real- or JIT-introduced locals).</span></span> <span data-ttu-id="5078c-141">그러면 `TestAssemblyLoadContext`를 활성 상태로 유지하고 언로드를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-141">That could keep the `TestAssemblyLoadContext` alive and prevent the unload.</span></span>

<span data-ttu-id="5078c-142">또한 나중에 언로드 완료를 검색하는 데 사용할 수 있도록 `AssemblyLoadContext`의 약한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-142">Also, return a weak reference to the `AssemblyLoadContext` so that you can use it later to detect unload completion.</span></span>

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

<span data-ttu-id="5078c-143">이제 이 함수를 실행하여 어셈블리를 로드, 실행 및 언로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-143">Now you can run this function to load, execute, and unload the assembly.</span></span>

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

<span data-ttu-id="5078c-144">그러나 언로드는 즉시 완료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-144">However, the unload doesn't complete immediately.</span></span> <span data-ttu-id="5078c-145">앞에서 설명한 것처럼 가비지 수집기를 사용하여 테스트 어셈블리에서 모든 개체를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-145">As previously mentioned, it relies on the garbage collector to collect all the objects from the test assembly.</span></span> <span data-ttu-id="5078c-146">대부분의 경우 언로드가 완료될 때까지 기다릴 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-146">In many cases, it isn't necessary to wait for the unload completion.</span></span> <span data-ttu-id="5078c-147">그러나 언로드가 완료되었음을 확인하는 것이 유용한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-147">However, there are cases where it's useful to know that the unload has finished.</span></span> <span data-ttu-id="5078c-148">예를 들어, 디스크에서 사용자 지정 `AssemblyLoadContext`로 로드된 어셈블리 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-148">For example, you may want to delete the assembly file that was loaded into the custom `AssemblyLoadContext` from disk.</span></span> <span data-ttu-id="5078c-149">이 경우 다음 코드 조각을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-149">In such a case, the following code snippet can be used.</span></span> <span data-ttu-id="5078c-150">이 코드 조각은 가비지 수집을 트리거하고 사용자 지정 `AssemblyLoadContext`에 대한 약한 참조가 `null`로 설정되어 대상 개체가 수집되었음을 나타낼 때까지 루프에서 보류 중인 종료자를 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-150">It triggers garbage collection and waits for pending finalizers in a loop until the weak reference to the custom `AssemblyLoadContext` is set to `null`, indicating the target object was collected.</span></span> <span data-ttu-id="5078c-151">대부분의 경우 루프를 한 번만 통과하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-151">In most cases, just one pass through the loop is required.</span></span> <span data-ttu-id="5078c-152">그러나 `AssemblyLoadContext`에서 실행 중인 코드를 통해 만든 개체에 종료자가 있는 복잡한 경우에는 추가 통과가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-152">However, for more complex cases where objects created by the code running in the `AssemblyLoadContext` have finalizers, more passes may be needed.</span></span>

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a><span data-ttu-id="5078c-153">언로딩 이벤트</span><span class="sxs-lookup"><span data-stu-id="5078c-153">The Unloading event</span></span>

<span data-ttu-id="5078c-154">이 이벤트는 경우에 따라 언로드를 시작할 때 일부 정리를 수행하기 위해 사용자 지정 `AssemblyLoadContext`에 로드된 코드에 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-154">In some cases, it may be necessary for the code loaded into a custom `AssemblyLoadContext` to perform some cleanup when the unloading is initiated.</span></span> <span data-ttu-id="5078c-155">예를 들어 스레드를 중지하고, 강력한 GC 핸들을 정리해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-155">For example, it may need to stop threads or clean up strong GC handles.</span></span> <span data-ttu-id="5078c-156">이 경우 `Unloading` 이벤트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-156">The `Unloading` event can be used in such cases.</span></span> <span data-ttu-id="5078c-157">필요한 정리를 수행하는 처리기를 이 이벤트에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-157">A handler that performs the necessary cleanup can be hooked to this event.</span></span>

### <a name="troubleshoot-unloadability-issues"></a><span data-ttu-id="5078c-158">로드 불가능 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5078c-158">Troubleshoot unloadability issues</span></span>

<span data-ttu-id="5078c-159">언로드의 협조적 특성 때문에 수집 가능한 `AssemblyLoadContext`의 요소가 활성 상태를 유지하게 하고 언로드를 방지할 수 있는 참조를 잊기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-159">Due to the cooperative nature of the unloading, it's easy to forget about references that may be keeping the stuff in a collectible `AssemblyLoadContext` alive and preventing unload.</span></span> <span data-ttu-id="5078c-160">다음은 참조를 보유할 수 있는 엔터티(일부는 명확하지 않음)의 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-160">Here is a summary of entities (some of them non-obvious) that can hold the references:</span></span>

- <span data-ttu-id="5078c-161">수집 가능한 `AssemblyLoadContext`의 외부에서 보유하며, 스택 슬롯 또는 프로세서 레지스터(사용자 코드를 사용하여 명시적으로 만들거나 JIT(Just-In-Time) 컴파일러에서 내재적으로 생성하는 메서드 로컬), 정적 변수 또는 강력한/고정 GC 핸들에 저장되며 다음을 가리키는 일반 참조.</span><span class="sxs-lookup"><span data-stu-id="5078c-161">Regular references held from outside of the collectible `AssemblyLoadContext` that are stored in a stack slot or a processor register (method locals, either explicitly created by the user code or implicitly by the just-in-time (JIT) compiler), a static variable, or a strong (pinning) GC handle, and transitively pointing to:</span></span>
  - <span data-ttu-id="5078c-162">수집 가능한 `AssemblyLoadContext`에 로드된 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="5078c-162">An assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
  - <span data-ttu-id="5078c-163">이러한 어셈블리의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-163">A type from such an assembly.</span></span>
  - <span data-ttu-id="5078c-164">이러한 어셈블리에 있는 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-164">An instance of a type from such an assembly.</span></span>
- <span data-ttu-id="5078c-165">수집 가능한 `AssemblyLoadContext`에 로드된 어셈블리의 스레드 실행 코드.</span><span class="sxs-lookup"><span data-stu-id="5078c-165">Threads running code from an assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
- <span data-ttu-id="5078c-166">수집 가능한 `AssemblyLoadContext` 내부에서 만들어진 수집 불가능한 사용자 지정 `AssemblyLoadContext` 형식의 인스턴스</span><span class="sxs-lookup"><span data-stu-id="5078c-166">Instances of custom, non-collectible `AssemblyLoadContext` types created inside of the collectible `AssemblyLoadContext`.</span></span>
- <span data-ttu-id="5078c-167">콜백이 사용자 지정 `AssemblyLoadContext`의 메서드로 설정된 보류 중인 <xref:System.Threading.RegisteredWaitHandle> 인스턴스</span><span class="sxs-lookup"><span data-stu-id="5078c-167">Pending <xref:System.Threading.RegisteredWaitHandle> instances with callbacks set to methods in the custom `AssemblyLoadContext`.</span></span>

> [!TIP]
> <span data-ttu-id="5078c-168">스택 슬롯 또는 프로세서 레지스터에 저장되고 다음과 같은 상황에서 `AssemblyLoadContext` 언로드를 금지할 수 있는 개체 참조</span><span class="sxs-lookup"><span data-stu-id="5078c-168">Object references that are stored in stack slots or processor registers and that could prevent unloading of an `AssemblyLoadContext` can occur in the following situations:</span></span>
>
> - <span data-ttu-id="5078c-169">사용자가 만든 로컬 변수가 없더라도 함수 호출 결과를 다른 함수에 직접 전달하는 경우</span><span class="sxs-lookup"><span data-stu-id="5078c-169">When function call results are passed directly to another function, even though there is no user-created local variable.</span></span>
> - <span data-ttu-id="5078c-170">JIT 컴파일러가 메서드의 특정 지점에서 사용할 수 있었던 개체에 대한 참조를 유지하는 경우</span><span class="sxs-lookup"><span data-stu-id="5078c-170">When the JIT compiler keeps a reference to an object that was available at some point in a method.</span></span>

## <a name="debug-unloading-issues"></a><span data-ttu-id="5078c-171">디버그 언로드 문제</span><span class="sxs-lookup"><span data-stu-id="5078c-171">Debug unloading issues</span></span>

<span data-ttu-id="5078c-172">언로드 관련 문제를 디버깅하는 것이 지루한 작업이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-172">Debugging issues with unloading can be tedious.</span></span> <span data-ttu-id="5078c-173">`AssemblyLoadContext`를 활성 상태로 유지할 수 있는 항목을 알 수 없지만 언로드가 실패하는 상황이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-173">You can get into situations where you don't know what can be holding an `AssemblyLoadContext` alive, but the unload fails.</span></span> <span data-ttu-id="5078c-174">이 문제를 해결하는 가장 좋은 방법은 SOS 플러그 인을 사용하는 WinDbg(Unix의 LLDB)입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-174">The best weapon to help with that is WinDbg (LLDB on Unix) with the SOS plugin.</span></span> <span data-ttu-id="5078c-175">특정 `AssemblyLoadContext`에 속한 `LoaderAllocator`를 활성 상태로 유지하는 사항을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-175">You need to find what's keeping a `LoaderAllocator` belonging to the specific `AssemblyLoadContext` alive.</span></span> <span data-ttu-id="5078c-176">SOS 플러그 인을 사용하면 GC 힙 개체, 해당 계층 구조 및 루트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-176">The SOS plugin allows you to look at GC heap objects, their hierarchies, and roots.</span></span>

<span data-ttu-id="5078c-177">플러그 인을 디버거로 로드하려면 디버거 명령줄에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-177">To load the plugin into the debugger, enter the following command in the debugger command line:</span></span>

<span data-ttu-id="5078c-178">WinDbg의 경우(.NET Core 애플리케이션으로 분리될 때 WinDbg가 자동으로 수행함):</span><span class="sxs-lookup"><span data-stu-id="5078c-178">In WinDbg (it seems WinDbg does that automatically when breaking into .NET Core application):</span></span>

```console
.loadby sos coreclr
```

<span data-ttu-id="5078c-179">LLDB에서:</span><span class="sxs-lookup"><span data-stu-id="5078c-179">In LLDB:</span></span>

```console
plugin load /path/to/libsosplugin.so
```

<span data-ttu-id="5078c-180">언로드에 문제가 있는 예제 프로그램을 디버깅해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-180">Let's debug an example program that has problems with unloading.</span></span> <span data-ttu-id="5078c-181">소스 코드는 아래 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-181">Source code is included below.</span></span> <span data-ttu-id="5078c-182">WinDbg에서 실행하면 언로드 성공 여부를 확인한 후 즉시 프로그램이 디버거를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-182">When you run it under WinDbg, the program breaks into the debugger right after attempting to check for the unload success.</span></span> <span data-ttu-id="5078c-183">그런 다음 원인을 검색하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-183">You can then start looking for the culprits.</span></span>

> [!TIP]
> <span data-ttu-id="5078c-184">Unix에서 LLDB를 사용하여 디버깅하는 경우 다음 예제의 SOS 명령 앞에 `!`가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-184">If you debug using LLDB on Unix, the SOS commands in the following examples don't have the `!` in front of them.</span></span>

```console
!dumpheap -type LoaderAllocator
```

<span data-ttu-id="5078c-185">이 명령은 GC 힙에 있는 `LoaderAllocator`를 포함하는 형식 이름을 사용하는 모든 개체를 덤프합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-185">This command dumps all objects with a type name containing `LoaderAllocator` that are in the GC heap.</span></span> <span data-ttu-id="5078c-186">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-186">Here is an example:</span></span>

```console
         Address               MT     Size
000002b78000ce40 00007ffadc93a288       48
000002b78000ceb0 00007ffadc93a218       24

Statistics:
              MT    Count    TotalSize Class Name
00007ffadc93a218        1           24 System.Reflection.LoaderAllocatorScout
00007ffadc93a288        1           48 System.Reflection.LoaderAllocator
Total 2 objects
```

<span data-ttu-id="5078c-187">아래 “통계” 파트에서 주의해야 할 개체인 `System.Reflection.LoaderAllocator`에 속한 `MT`(`MethodTable`)을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-187">In the "Statistics:" part below, check the `MT` (`MethodTable`) belonging to the `System.Reflection.LoaderAllocator`, which is the object we care about.</span></span> <span data-ttu-id="5078c-188">그런 다음 시작 부분에 있는 목록에서 해당 항목과 일치하는 `MT`가 있는 항목을 찾아 개체 자체의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-188">Then, in the list at the beginning, find the entry with `MT` matching that one and get the address of the object itself.</span></span> <span data-ttu-id="5078c-189">이 경우 "000002b78000ce40"입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-189">In our case, it is "000002b78000ce40".</span></span>

<span data-ttu-id="5078c-190">이제 `LoaderAllocator` 개체의 주소를 알고 있으므로 다른 명령을 사용하여 GC 루트를 찾을 수 있음</span><span class="sxs-lookup"><span data-stu-id="5078c-190">Now that we know the address of the `LoaderAllocator` object, we can use another command to find its GC roots:</span></span>

```console
!gcroot -all 0x000002b78000ce40
```

<span data-ttu-id="5078c-191">이 명령은 `LoaderAllocator` 인스턴스를 초래하는 개체 참조의 체인을 덤프합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-191">This command dumps the chain of object references that lead to the `LoaderAllocator` instance.</span></span> <span data-ttu-id="5078c-192">이 목록은 `LoaderAllocator`를 활성 상태로 유지하므로 문제의 핵심이 되는 엔터티인 루트로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-192">The list starts with the root, which is the entity that keeps our `LoaderAllocator` alive and thus is the core of the problem.</span></span> <span data-ttu-id="5078c-193">루트는 스택 슬롯, 프로세서 레지스터, GC 핸들 또는 정적 변수일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-193">The root can be a stack slot, a processor register, a GC handle, or a static variable.</span></span>

<span data-ttu-id="5078c-194">다음은 `gcroot` 명령 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-194">Here is an example of the output of the `gcroot` command:</span></span>

```console
Thread 4ac:
    000000cf9499dd20 00007ffa7d0236bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
        rbp-20: 000000cf9499dd90
            ->  000002b78000d328 System.Reflection.RuntimeMethodInfo
            ->  000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
            ->  000002b78000d1d0 System.RuntimeType
            ->  000002b78000ce40 System.Reflection.LoaderAllocator

HandleTable:
    000002b7f8a81198 (strong handle)
    -> 000002b78000d948 test.Test
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

    000002b7f8a815f8 (pinned handle)
    -> 000002b790001038 System.Object[]
    -> 000002b78000d390 example.TestInfo
    -> 000002b78000d328 System.Reflection.RuntimeMethodInfo
    -> 000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
    -> 000002b78000d1d0 System.RuntimeType
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

Found 3 roots.
```

<span data-ttu-id="5078c-195">다음 단계는 문제를 해결할 수 있도록 루트의 위치를 파악하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-195">The next step is to figure out where the root is located so you can fix it.</span></span> <span data-ttu-id="5078c-196">가장 쉬운 사례는 루트가 스택 슬롯 또는 프로세서 레지스터인 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-196">The easiest case is when the root is a stack slot or a processor register.</span></span> <span data-ttu-id="5078c-197">이 경우 `gcroot`는 프레임에 해당 함수를 실행하는 루트 및 스레드가 포함된 함수의 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-197">In that case, the `gcroot` shows the name of the function whose frame contains the root and the thread executing that function.</span></span> <span data-ttu-id="5078c-198">루트가 정적 변수이거나 GC 핸들인 경우 해결하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-198">The difficult case is when the root is a static variable or a GC handle.</span></span>

<span data-ttu-id="5078c-199">이전 예제에서 첫 번째 루트는 `rbp-20` 주소(여기서 `rbp`는 프로세서 레지스터 `rbp`이고 -20은 해당 레지스터로부터의 16진수 오프셋임)에서 `example.Program.Main(System.String[])` 함수의 프레임에 저장된 `System.Reflection.RuntimeMethodInfo` 형식의 로컬입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-199">In the previous example, the first root is a local of type `System.Reflection.RuntimeMethodInfo` stored in the frame of the function `example.Program.Main(System.String[])` at address `rbp-20` (`rbp` is the processor register `rbp` and -20 is a hexadecimal offset from that register).</span></span>

<span data-ttu-id="5078c-200">두 번째 루트는 `test.Test` 클래스의 인스턴스에 대한 참조를 보유하는 기본 (강력) `GCHandle`입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-200">The second root is a normal (strong) `GCHandle` that holds a reference to an instance of the `test.Test` class.</span></span>

<span data-ttu-id="5078c-201">세 번째 루트는 고정된 `GCHandle`입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-201">The third root is a pinned `GCHandle`.</span></span> <span data-ttu-id="5078c-202">실제로는 정적 변수이지만 알 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-202">This one is actually a static variable, but unfortunately, there is no way to tell.</span></span> <span data-ttu-id="5078c-203">참조 형식의 정적은 내부 런타임 구조체의 관리형 개체 배열에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-203">Statics for reference types are stored in a managed object array in internal runtime structures.</span></span>

<span data-ttu-id="5078c-204">`AssemblyLoadContext`를 언로드하지 못하게 하는 또 다른 경우는 스레드에 스택의 `AssemblyLoadContext`에 로드된 어셈블리의 메서드 프레임이 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-204">Another case that can prevent unloading of an `AssemblyLoadContext` is when a thread has a frame of a method from an assembly loaded into the `AssemblyLoadContext` on its stack.</span></span> <span data-ttu-id="5078c-205">모든 스레드의 관리형 호출 스택을 덤프하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-205">You can check that by dumping managed call stacks of all threads:</span></span>

```console
~*e !clrstack
```

<span data-ttu-id="5078c-206">명령은 “모든 스레드에 `!clrstack` 명령 적용”을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-206">The command means "apply to all threads the `!clrstack` command".</span></span> <span data-ttu-id="5078c-207">다음은 예제에 대한 해당 명령의 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-207">The following is the output of that command for the example.</span></span> <span data-ttu-id="5078c-208">안타깝게도 Unix의 LLDB에서는 모든 스레드에 명령을 적용할 수 있는 방법이 없으므로 수동으로 스레드를 전환하고 `clrstack` 명령을 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-208">Unfortunately, LLDB on Unix doesn't have any way to apply a command to all threads, so you must manually switch threads and repeat the `clrstack` command.</span></span> <span data-ttu-id="5078c-209">디버거가 "관리형 스택을 탐색할 수 없습니다"라고 표시하는 경우 모든 스레드를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-209">Ignore all threads where the debugger says "Unable to walk the managed stack".</span></span>

```console
OS Thread Id: 0x6ba8 (0)
        Child SP               IP Call Site
0000001fc697d5c8 00007ffb50d9de12 [HelperMethodFrame: 0000001fc697d5c8] System.Diagnostics.Debugger.BreakInternal()
0000001fc697d6d0 00007ffa864765fa System.Diagnostics.Debugger.Break()
0000001fc697d700 00007ffa864736bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
0000001fc697d998 00007ffae5fdc1e3 [GCFrame: 0000001fc697d998]
0000001fc697df28 00007ffae5fdc1e3 [GCFrame: 0000001fc697df28]
OS Thread Id: 0x2ae4 (1)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x61a4 (2)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x7fdc (3)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5390 (4)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5ec8 (5)
        Child SP               IP Call Site
0000001fc70ff6e0 00007ffb5437f6e4 [DebuggerU2MCatchHandlerFrame: 0000001fc70ff6e0]
OS Thread Id: 0x4624 (6)
        Child SP               IP Call Site
GetFrameContext failed: 1
0000000000000000 0000000000000000
OS Thread Id: 0x60bc (7)
        Child SP               IP Call Site
0000001fc727f158 00007ffb5437fce4 [HelperMethodFrame: 0000001fc727f158] System.Threading.Thread.SleepInternal(Int32)
0000001fc727f260 00007ffb37ea7c2b System.Threading.Thread.Sleep(Int32)
0000001fc727f290 00007ffa865005b3 test.Program.ThreadProc() [E:\unloadability\test\Program.cs @ 17]
0000001fc727f2c0 00007ffb37ea6a5b System.Threading.Thread.ThreadMain_ThreadStart()
0000001fc727f2f0 00007ffadbc4cbe3 System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object)
0000001fc727f568 00007ffae5fdc1e3 [GCFrame: 0000001fc727f568]
0000001fc727f7f0 00007ffae5fdc1e3 [DebuggerU2MCatchHandlerFrame: 0000001fc727f7f0]

```

<span data-ttu-id="5078c-210">여기에서 볼 수 있듯이 마지막 스레드에는 `test.Program.ThreadProc()`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-210">As you can see, the last thread has `test.Program.ThreadProc()`.</span></span> <span data-ttu-id="5078c-211">이 함수는 `AssemblyLoadContext`에 로드된 어셈블리의 함수이므로 `AssemblyLoadContext`를 활성 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-211">This is a function from the assembly loaded into the `AssemblyLoadContext`, and so it keeps the `AssemblyLoadContext` alive.</span></span>

## <a name="example-source-with-unloadability-issues"></a><span data-ttu-id="5078c-212">로드 불가능 문제가 있는 소스 예제</span><span class="sxs-lookup"><span data-stu-id="5078c-212">Example source with unloadability issues</span></span>

<span data-ttu-id="5078c-213">다음 코드는 이전 디버깅 예제에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-213">The following code is used in the previous debugging example.</span></span>

### <a name="main-testing-program"></a><span data-ttu-id="5078c-214">기본 테스트 프로그램</span><span class="sxs-lookup"><span data-stu-id="5078c-214">Main testing program</span></span>

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a><span data-ttu-id="5078c-215">TestAssemblyLoadContext에 로드된 프로그램</span><span class="sxs-lookup"><span data-stu-id="5078c-215">Program loaded into the TestAssemblyLoadContext</span></span>

<span data-ttu-id="5078c-216">다음 코드는 기본 테스트 프로그램의 `ExecuteAndUnload` 메서드에 전달되는 *test.dll*을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5078c-216">The following code represents the *test.dll* passed to the `ExecuteAndUnload` method in the main testing program.</span></span>

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
