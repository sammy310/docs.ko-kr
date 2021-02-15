---
title: 자세한 어셈블리 로딩 정보 수집 - .NET Core
description: .NET Core에서 어셈블리 로딩 정보를 수집하는 방법에 대한 설명
author: elinor-fung
ms.author: elfung
ms.date: 11/17/2020
ms.openlocfilehash: b121982995b440ade6d72190f44f9b9d237c8af6
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506506"
---
# <a name="collect-detailed-assembly-loading-information"></a><span data-ttu-id="cb660-103">자세한 어셈블리 로딩 정보 수집</span><span class="sxs-lookup"><span data-stu-id="cb660-103">Collect detailed assembly loading information</span></span>

<span data-ttu-id="cb660-104">.NET 5.0부터 런타임은 어셈블리 로딩 문제를 진단하는 데 도움이 되도록 [관리되는 어셈블리 로딩](loading-managed.md)에 대한 자세한 정보와 함께 `EventPipe`를 통해 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-104">Starting with .NET 5.0, the runtime can emit events through `EventPipe` with detailed information about [managed assembly loading](loading-managed.md) to aid in diagnosing assembly loading issues.</span></span> <span data-ttu-id="cb660-105">이러한 [이벤트](../../fundamentals/diagnostics/runtime-loader-binder-events.md)는 `Microsoft-Windows-DotNETRuntime` 공급자가 `AssemblyLoader` 키워드(`0x4`)로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-105">These [events](../../fundamentals/diagnostics/runtime-loader-binder-events.md) are emitted by the `Microsoft-Windows-DotNETRuntime` provider under the `AssemblyLoader` keyword (`0x4`).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb660-106">사전 준비 사항</span><span class="sxs-lookup"><span data-stu-id="cb660-106">Prerequisites</span></span>

- <span data-ttu-id="cb660-107">[.NET 5.0 SDK](https://dotnet.microsoft.com/download) 이상 버전</span><span class="sxs-lookup"><span data-stu-id="cb660-107">[.NET 5.0 SDK](https://dotnet.microsoft.com/download) or later versions</span></span>
- <span data-ttu-id="cb660-108">[dotnet-trace](../diagnostics/dotnet-trace.md) 도구.</span><span class="sxs-lookup"><span data-stu-id="cb660-108">[dotnet-trace](../diagnostics/dotnet-trace.md) tool.</span></span>

## <a name="collect-a-trace-with-assembly-loading-events"></a><span data-ttu-id="cb660-109">어셈블리 로딩 이벤트를 사용하여 추적 수집</span><span class="sxs-lookup"><span data-stu-id="cb660-109">Collect a trace with assembly loading events</span></span>

<span data-ttu-id="cb660-110">런타임에 어셈블리 로딩 이벤트를 사용하도록 설정하고 그 추적을 수집하려면 `dotnet-trace`를 다음 명령과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-110">To enable assembly loading events in the runtime and collect a trace of them, use `dotnet-trace` with the following command:</span></span>

```console
dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:4 --process-id <pid>
```

<span data-ttu-id="cb660-111">그러면 지정된 `<pid>`의 추적이 수집되어 `Microsoft-Windows-DotNETRuntime` 공급자에서 `AssemblyLoader` 이벤트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-111">This will collect a trace of the specified `<pid>`, enabling the `AssemblyLoader` events in the `Microsoft-Windows-DotNETRuntime` provider.</span></span> <span data-ttu-id="cb660-112">결과는 `.nettrace` 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-112">The result is a `.nettrace` file.</span></span>

## <a name="view-a-trace"></a><span data-ttu-id="cb660-113">추적 보기</span><span class="sxs-lookup"><span data-stu-id="cb660-113">View a trace</span></span>

<span data-ttu-id="cb660-114">수집된 추적 파일은 Windows에서 [PerfView](https://github.com/microsoft/perfview)의 이벤트 보기를 사용하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-114">The collected trace file can be viewed on Windows using the Events view in [PerfView](https://github.com/microsoft/perfview).</span></span> <span data-ttu-id="cb660-115">모든 어셈블리 로딩 이벤트에는 접두사 `Microsoft-Windows-DotNETRuntime/AssemblyLoader`가 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-115">All the assembly loading events will be prefixed with `Microsoft-Windows-DotNETRuntime/AssemblyLoader`.</span></span>

## <a name="example-on-windows"></a><span data-ttu-id="cb660-116">예제(Windows)</span><span class="sxs-lookup"><span data-stu-id="cb660-116">Example (on Windows)</span></span>

<span data-ttu-id="cb660-117">이 예제에서는 [어셈블리 로딩 확장 지점 샘플](https://github.com/dotnet/samples/tree/master/core/extensions/AssemblyLoading)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-117">This example uses the [assembly loading extension points sample](https://github.com/dotnet/samples/tree/master/core/extensions/AssemblyLoading).</span></span> <span data-ttu-id="cb660-118">애플리케이션에서 어셈블리 `MyLibrary`를 로드하려고 합니다. 이 어셈블리는 애플리케이션에서 참조하지 않으므로 성공적으로 로드하려면 어셈블리 로딩 확장 지점에서 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-118">The application attempts to load an assembly `MyLibrary` - an assembly that is not referenced by the application and thus requires handling in an assembly loading extension point to be successfully loaded.</span></span>

### <a name="collect-the-trace"></a><span data-ttu-id="cb660-119">추적 수집</span><span class="sxs-lookup"><span data-stu-id="cb660-119">Collect the trace</span></span>

01. <span data-ttu-id="cb660-120">다운로드한 샘플이 있는 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-120">Navigate to the directory with the downloaded sample.</span></span> <span data-ttu-id="cb660-121">다음을 사용하여 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-121">Build the application with:</span></span>

    ```console
    dotnet build
    ```

01. <span data-ttu-id="cb660-122">키를 누를 때까지 대기하며 일시 중지해야 함을 나타내는 인수를 사용하여 애플리케이션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-122">Launch the application with arguments indicating that it should pause, waiting for a key press.</span></span> <span data-ttu-id="cb660-123">다시 시작할 때 애플리케이션이 성공적인 로드에 필요한 처리 없이 기본 `AssemblyLoadContext`에서 어셈블리를 로드하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-123">On resuming, it will attempt to load the assembly in the default `AssemblyLoadContext` - without the handling necessary for a successful load.</span></span> <span data-ttu-id="cb660-124">출력 디렉터리로 이동하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-124">Navigate to the output directory and run:</span></span>

    ```console
    AssemblyLoading.exe /d default
    ```

01. <span data-ttu-id="cb660-125">애플리케이션의 프로세스 ID를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-125">Find the application's process ID.</span></span>

    ```console
    dotnet-trace ps
    ```

    <span data-ttu-id="cb660-126">출력에 사용 가능한 프로세스가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-126">The output will list the available processes.</span></span> <span data-ttu-id="cb660-127">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="cb660-127">For example:</span></span>

    ```console
    35832 AssemblyLoading C:\src\AssemblyLoading\bin\Debug\net5.0\AssemblyLoading.exe
    ```

01. <span data-ttu-id="cb660-128">실행 중인 애플리케이션에 `dotnet-trace`를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-128">Attach `dotnet-trace` to the running application.</span></span>

    ```console
    dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:4 --process-id 35832
    ```

01. <span data-ttu-id="cb660-129">애플리케이션을 실행하는 창에서 아무 키나 눌러 프로그램을 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-129">In the window running the application, press any key to let the program continue.</span></span> <span data-ttu-id="cb660-130">애플리케이션이 종료되면 추적이 자동으로 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-130">Tracing will automatically stop once the application exits.</span></span>

### <a name="view-the-trace"></a><span data-ttu-id="cb660-131">추적 보기</span><span class="sxs-lookup"><span data-stu-id="cb660-131">View the trace</span></span>

<span data-ttu-id="cb660-132">[PerfView](https://github.com/microsoft/perfview)에서 수집된 추적을 열고 이벤트 보기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-132">Open the collected trace in [PerfView](https://github.com/microsoft/perfview) and open the Events view.</span></span> <span data-ttu-id="cb660-133">이벤트 목록을 `Microsoft-Windows-DotNETRuntime/AssemblyLoader` 이벤트로 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-133">Filter the events list to `Microsoft-Windows-DotNETRuntime/AssemblyLoader` events.</span></span>

:::image type="content" source="media/collect-details/assembly-loader-filter.png" alt-text="PerfView 어셈블리 로더 필터 이미지":::

<span data-ttu-id="cb660-135">추적이 시작된 후 애플리케이션에서 발생한 모든 어셈블리 로드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-135">All assembly loads that occurred in the application after tracing started will be shown.</span></span> <span data-ttu-id="cb660-136">이 예제에 대한 원하는 어셈블리 로드 작업 `MyLibrary`를 검사하기 위해 몇 가지 추가 필터링을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-136">To inspect the load operation for the assembly of interest for this example - `MyLibrary`, we can do some more filtering.</span></span>

### <a name="assembly-loads"></a><span data-ttu-id="cb660-137">어셈블리 로드</span><span class="sxs-lookup"><span data-stu-id="cb660-137">Assembly loads</span></span>

<span data-ttu-id="cb660-138">왼쪽에 있는 이벤트 목록을 사용하여 `Microsoft-Windows-DotNETRuntime/AssemblyLoader` 아래의 [`Start`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#assemblyloadstart-event) 및 [`Stop`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#assemblyloadstop-event) 이벤트로 보기를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-138">Filter the view to the [`Start`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#assemblyloadstart-event) and [`Stop`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#assemblyloadstop-event) events under `Microsoft-Windows-DotNETRuntime/AssemblyLoader` using the event list on the left.</span></span> <span data-ttu-id="cb660-139">`AssemblyName`, `ActivityID` 및 `Success` 열을 보기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-139">Add the columns `AssemblyName`, `ActivityID`, and `Success` to the view.</span></span> <span data-ttu-id="cb660-140">`MyLibrary`를 포함하는 이벤트로 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-140">Filter to events containing `MyLibrary`.</span></span>

:::image type="content" source="media/collect-details/start-stop.png" alt-text="PerfView 시작 및 중지 이벤트 이미지":::

| <span data-ttu-id="cb660-142">이벤트 이름</span><span class="sxs-lookup"><span data-stu-id="cb660-142">Event Name</span></span>             | <span data-ttu-id="cb660-143">AssemblyName</span><span class="sxs-lookup"><span data-stu-id="cb660-143">AssemblyName</span></span>                                      | <span data-ttu-id="cb660-144">ActivityID</span><span class="sxs-lookup"><span data-stu-id="cb660-144">ActivityID</span></span> | <span data-ttu-id="cb660-145">Success</span><span class="sxs-lookup"><span data-stu-id="cb660-145">Success</span></span> |
| ---------------------- | ------------------------------------------------- | ---------- | ------- |
| `AssemblyLoader/Start` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | <span data-ttu-id="cb660-146">//1/2/</span><span class="sxs-lookup"><span data-stu-id="cb660-146">//1/2/</span></span>     |         |
| `AssemblyLoader/Stop`  | `MyLibrary, Culture=neutral, PublicKeyToken=null` | <span data-ttu-id="cb660-147">//1/2/</span><span class="sxs-lookup"><span data-stu-id="cb660-147">//1/2/</span></span>     | <span data-ttu-id="cb660-148">False</span><span class="sxs-lookup"><span data-stu-id="cb660-148">False</span></span>   |

<span data-ttu-id="cb660-149">`Stop` 이벤트에 하나의 `Start`/`Stop` 쌍과 `Success=False`가 표시되어 로드 작업이 실패했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-149">You should see one `Start`/`Stop` pair with `Success=False` on the `Stop` event, indicating the load operation failed.</span></span> <span data-ttu-id="cb660-150">두 이벤트의 활동 ID는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-150">Note that the two events have the same activity ID.</span></span> <span data-ttu-id="cb660-151">활동 ID를 사용하여 다른 모든 어셈블리 로더 이벤트를 이 로드 작업에 해당하는 이벤트로만 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-151">The activity ID can be used to filter all the other assembly loader events to just the ones corresponding to this load operation.</span></span>

### <a name="breakdown-of-attempt-to-load"></a><span data-ttu-id="cb660-152">로드 시도 분석</span><span class="sxs-lookup"><span data-stu-id="cb660-152">Breakdown of attempt to load</span></span>

<span data-ttu-id="cb660-153">로드 작업에 대한 자세한 분석을 보려면 왼쪽에 있는 이벤트 목록을 사용하여 `Microsoft-Windows-DotNETRuntime/AssemblyLoader` 아래의 [`ResolutionAttempted` 이벤트](../../fundamentals/diagnostics/runtime-loader-binder-events.md#resolutionattempted-event)로 보기를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-153">For a more detailed breakdown of the load operation, filter the view to the [`ResolutionAttempted` events](../../fundamentals/diagnostics/runtime-loader-binder-events.md#resolutionattempted-event) under `Microsoft-Windows-DotNETRuntime/AssemblyLoader` using the event list on the left.</span></span> <span data-ttu-id="cb660-154">`AssemblyName`, `Stage` 및 `Result` 열을 보기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-154">Add the columns `AssemblyName`, `Stage`, and `Result` to the view.</span></span> <span data-ttu-id="cb660-155">`Start`/`Stop` 쌍의 활동 ID를 갖는 이벤트로 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-155">Filter to events with the activity ID from the `Start`/`Stop` pair.</span></span>

:::image type="content" source="media/collect-details/resolution-attempted.png" alt-text="PerfView ResolutionAttempted 이벤트 이미지":::

| <span data-ttu-id="cb660-157">이벤트 이름</span><span class="sxs-lookup"><span data-stu-id="cb660-157">Event Name</span></span>                           | <span data-ttu-id="cb660-158">AssemblyName</span><span class="sxs-lookup"><span data-stu-id="cb660-158">AssemblyName</span></span>                                      | <span data-ttu-id="cb660-159">단계</span><span class="sxs-lookup"><span data-stu-id="cb660-159">Stage</span></span>                               | <span data-ttu-id="cb660-160">결과</span><span class="sxs-lookup"><span data-stu-id="cb660-160">Result</span></span>             |
| ------------------------------------ | ------------------------------------------------- | ----------------------------------- | ------------------ |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `FindInLoadContext`                 | `AssemblyNotFound` |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `ApplicationAssemblies`             | `AssemblyNotFound` |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `AssemblyLoadContextResolvingEvent` | `AssemblyNotFound` |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `AppDomainAssemblyResolveEvent`     | `AssemblyNotFound` |

<span data-ttu-id="cb660-161">위의 이벤트는 어셈블리 로더가 현재 로드 컨텍스트를 확인하고, 관리되는 애플리케이션 어셈블리에 대한 기본 검색 논리를 실행하고, <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> 이벤트에 대해 처리기를 호출하고, <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>에 대해 처리기를 호출하여 어셈블리를 확인하려고 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-161">The events above indicate that the assembly loader attempted to resolve the assembly by looking in the current load context, running the default probing logic for managed application assemblies, invoking handlers for the <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> event, and invoking handlers for the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cb660-162">이러한 모든 단계에 대해 어셈블리를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-162">For all of these steps, the assembly was not found.</span></span>

### <a name="extension-points"></a><span data-ttu-id="cb660-163">확장 지점</span><span class="sxs-lookup"><span data-stu-id="cb660-163">Extension points</span></span>

<span data-ttu-id="cb660-164">호출된 확장 지점을 확인하려면 왼쪽에 있는 이벤트 목록을 사용하여 `Microsoft-Windows-DotNETRuntime/AssemblyLoader` 아래의 [`AssemblyLoadContextResolvingHandlerInvoked`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#assemblyloadcontextresolvinghandlerinvoked-event) 및 [`AppDomainAssemblyResolveHandlerInvoked`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#appdomainassemblyresolvehandlerinvoked-event)로 보기를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-164">To see which extension points were invoked, filter the view to the [`AssemblyLoadContextResolvingHandlerInvoked`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#assemblyloadcontextresolvinghandlerinvoked-event) and [`AppDomainAssemblyResolveHandlerInvoked`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#appdomainassemblyresolvehandlerinvoked-event) under `Microsoft-Windows-DotNETRuntime/AssemblyLoader` using the event list on the left.</span></span> <span data-ttu-id="cb660-165">`AssemblyName` 및 `HandlerName` 열을 보기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-165">Add the columns `AssemblyName` and `HandlerName` to the view.</span></span> <span data-ttu-id="cb660-166">`Start`/`Stop` 쌍의 활동 ID를 갖는 이벤트로 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-166">Filter to events with the activity ID from the `Start`/`Stop` pair.</span></span>

:::image type="content" source="media/collect-details/extension-point.png" alt-text="PerfView 확장 지점 이벤트 이미지":::

| <span data-ttu-id="cb660-168">이벤트 이름</span><span class="sxs-lookup"><span data-stu-id="cb660-168">Event Name</span></span>                                                  | <span data-ttu-id="cb660-169">AssemblyName</span><span class="sxs-lookup"><span data-stu-id="cb660-169">AssemblyName</span></span>                                      | <span data-ttu-id="cb660-170">HandlerName</span><span class="sxs-lookup"><span data-stu-id="cb660-170">HandlerName</span></span>                      |
| ----------------------------------------------------------- | ------------------------------------------------- | -------------------------------- |
| `AssemblyLoader/AssemblyLoadContextResolvingHandlerInvoked` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `OnAssemblyLoadContextResolving` |
| `AssemblyLoader/AppDomainAssemblyResolveHandlerInvoked`     | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `OnAppDomainAssemblyResolve`     |

<span data-ttu-id="cb660-171">위의 이벤트는 <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> 이벤트에 대해 `OnAssemblyLoadContextResolving`이라는 처리기가 호출되고 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트에 대해 `OnAppDomainAssemblyResolve`이라는 처리기가 호출되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-171">The events above indicate that a handler named `OnAssemblyLoadContextResolving` was invoked for the <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> event and a handler named `OnAppDomainAssemblyResolve` was invoked for the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>

### <a name="collect-another-trace"></a><span data-ttu-id="cb660-172">다른 추적 수집</span><span class="sxs-lookup"><span data-stu-id="cb660-172">Collect another trace</span></span>

<span data-ttu-id="cb660-173"><xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> 이벤트에 대한 처리기가 `MyLibrary` 어셈블리를 로드하도록 인수를 사용하여 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-173">Run the application with arguments such that its handler for the <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> event will load the `MyLibrary` assembly.</span></span>

```console
AssemblyLoading /d default alc-resolving
```

<span data-ttu-id="cb660-174">[위의 단계](#collect-the-trace)를 사용하여 다른 `.nettrace` 파일을 수집하고 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-174">Collect and open another `.nettrace` file using the [steps from above](#collect-the-trace).</span></span>

<span data-ttu-id="cb660-175">다시 `MyLibrary`에 대한 `Start` 및 `Stop` 이벤트로 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-175">Filter to the `Start` and `Stop` events for `MyLibrary` again.</span></span> <span data-ttu-id="cb660-176">`Start`/`Stop` 쌍과 그 사이에 또 다른 `Start`/`Stop`이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-176">You should see a `Start`/`Stop` pair with another `Start`/`Stop` between them.</span></span> <span data-ttu-id="cb660-177">내부 로드 작업은 <xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyPath%2A?displayProperty=nameWithType>을 호출했을 때 <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType>에 대한 처리기를 통해 트리거된 로드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-177">The inner load operation represents the load triggered by the handler for <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> when it called <xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyPath%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cb660-178">이번에는 `Stop` 이벤트에 `Success=True`가 표시되어 로드 작업이 성공했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-178">This time, you should see `Success=True` on the `Stop` event, indicating the load operation succeeded.</span></span> <span data-ttu-id="cb660-179">`ResultAssemblyPath` 필드는 결과 어셈블리의 경로를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-179">The `ResultAssemblyPath` field shows the path of the resulting assembly.</span></span>

:::image type="content" source="media/collect-details/start-stop-success.png" alt-text="PerfView 성공한 이벤트 시작 및 중지 이벤트 이미지":::

| <span data-ttu-id="cb660-181">이벤트 이름</span><span class="sxs-lookup"><span data-stu-id="cb660-181">Event Name</span></span>             | <span data-ttu-id="cb660-182">AssemblyName</span><span class="sxs-lookup"><span data-stu-id="cb660-182">AssemblyName</span></span>                                                       | <span data-ttu-id="cb660-183">ActivityID</span><span class="sxs-lookup"><span data-stu-id="cb660-183">ActivityID</span></span> | <span data-ttu-id="cb660-184">Success</span><span class="sxs-lookup"><span data-stu-id="cb660-184">Success</span></span> | <span data-ttu-id="cb660-185">ResultAssemblyPath</span><span class="sxs-lookup"><span data-stu-id="cb660-185">ResultAssemblyPath</span></span>                                      |
| ---------------------- | ------------------------------------------------------------------ |------------|---------| ------------------------------------------------------- |
| `AssemblyLoader/Start` |                  `MyLibrary, Culture=neutral, PublicKeyToken=null` | <span data-ttu-id="cb660-186">//1/2/</span><span class="sxs-lookup"><span data-stu-id="cb660-186">//1/2/</span></span>     |         |                                                         |
| `AssemblyLoader/Start` | `MyLibrary, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null` | <span data-ttu-id="cb660-187">//1/2/1/</span><span class="sxs-lookup"><span data-stu-id="cb660-187">//1/2/1/</span></span>   |         |                                                         |
| `AssemblyLoader/Stop`  | `MyLibrary, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null` | <span data-ttu-id="cb660-188">//1/2/1/</span><span class="sxs-lookup"><span data-stu-id="cb660-188">//1/2/1/</span></span>   | <span data-ttu-id="cb660-189">True</span><span class="sxs-lookup"><span data-stu-id="cb660-189">True</span></span>    | <span data-ttu-id="cb660-190">*C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll*</span><span class="sxs-lookup"><span data-stu-id="cb660-190">*C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll*</span></span> |
| `AssemblyLoader/Stop`  |                  `MyLibrary, Culture=neutral, PublicKeyToken=null` | <span data-ttu-id="cb660-191">//1/2/</span><span class="sxs-lookup"><span data-stu-id="cb660-191">//1/2/</span></span>     | <span data-ttu-id="cb660-192">True</span><span class="sxs-lookup"><span data-stu-id="cb660-192">True</span></span>    | <span data-ttu-id="cb660-193">*C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll*</span><span class="sxs-lookup"><span data-stu-id="cb660-193">*C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll*</span></span> |

<span data-ttu-id="cb660-194">그런 다음 외부 로드의 활동 ID를 갖는 `ResolutionAttempted` 이벤트를 살펴보고 어셈블리가 성공적으로 확인된 단계를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-194">We can then look at the `ResolutionAttempted` events with the activity ID from the outer load to determine the step at which the assembly was successfully resolved.</span></span> <span data-ttu-id="cb660-195">이번에는 이벤트에 `AssemblyLoadContextResolvingEvent` 단계가 성공했다고 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-195">This time, the events will show that the `AssemblyLoadContextResolvingEvent` stage was successful.</span></span> <span data-ttu-id="cb660-196">`ResultAssemblyPath` 필드는 결과 어셈블리의 경로를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-196">The `ResultAssemblyPath` field shows the path of the resulting assembly.</span></span>

:::image type="content" source="media/collect-details/resolution-attempted-success.png" alt-text="PerfView 성공한 ResolutionAttempted 이벤트 이미지":::

| <span data-ttu-id="cb660-198">이벤트 이름</span><span class="sxs-lookup"><span data-stu-id="cb660-198">Event Name</span></span>                           | <span data-ttu-id="cb660-199">AssemblyName</span><span class="sxs-lookup"><span data-stu-id="cb660-199">AssemblyName</span></span>                                      | <span data-ttu-id="cb660-200">단계</span><span class="sxs-lookup"><span data-stu-id="cb660-200">Stage</span></span>                               | <span data-ttu-id="cb660-201">결과</span><span class="sxs-lookup"><span data-stu-id="cb660-201">Result</span></span>             | <span data-ttu-id="cb660-202">ResultAssemblyPath</span><span class="sxs-lookup"><span data-stu-id="cb660-202">ResultAssemblyPath</span></span> |
| ------------------------------------ | ------------------------------------------------- | ----------------------------------- | ------------------ | ------------------ |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `FindInLoadContext`                 | `AssemblyNotFound` |                    |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `ApplicationAssemblies`             | `AssemblyNotFound` |                    |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `AssemblyLoadContextResolvingEvent` | `Success`          | <span data-ttu-id="cb660-203">*C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll*</span><span class="sxs-lookup"><span data-stu-id="cb660-203">*C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll*</span></span> |

<span data-ttu-id="cb660-204">`AssemblyLoadContextResolvingHandlerInvoked` 이벤트를 살펴보면 `OnAssemblyLoadContextResolving`라는 처리기가 호출되었음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-204">Looking at `AssemblyLoadContextResolvingHandlerInvoked` events will show that the handler named `OnAssemblyLoadContextResolving` was invoked.</span></span> <span data-ttu-id="cb660-205">`ResultAssemblyPath` 필드는 처리기에서 반환된 어셈블리의 경로를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-205">The `ResultAssemblyPath` field shows the path of the assembly returned by the handler.</span></span>

:::image type="content" source="media/collect-details/extension-point-success.png" alt-text="PerfView 성공한 확장 지점 이벤트 이미지":::

| <span data-ttu-id="cb660-207">이벤트 이름</span><span class="sxs-lookup"><span data-stu-id="cb660-207">Event Name</span></span>                                                  | <span data-ttu-id="cb660-208">AssemblyName</span><span class="sxs-lookup"><span data-stu-id="cb660-208">AssemblyName</span></span>                                      | <span data-ttu-id="cb660-209">HandlerName</span><span class="sxs-lookup"><span data-stu-id="cb660-209">HandlerName</span></span>                      | <span data-ttu-id="cb660-210">ResultAssemblyPath</span><span class="sxs-lookup"><span data-stu-id="cb660-210">ResultAssemblyPath</span></span> |
| ----------------------------------------------------------- | ------------------------------------------------- | -------------------------------- | ------------------ |
| `AssemblyLoader/AssemblyLoadContextResolvingHandlerInvoked` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `OnAssemblyLoadContextResolving` | <span data-ttu-id="cb660-211">*C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll*</span><span class="sxs-lookup"><span data-stu-id="cb660-211">*C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll*</span></span> |

<span data-ttu-id="cb660-212">어셈블리가 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트를 발생시키는 로딩 알고리즘 단계에 도달하기 전에 성공적으로 로드되었으므로 `AppDomainAssemblyResolveEvent` 단계 또는 `AppDomainAssemblyResolveHandlerInvoked` 이벤트가 포함된 `ResolutionAttempted` 이벤트가 더 이상 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb660-212">Note that there is no longer a `ResolutionAttempted` event with the `AppDomainAssemblyResolveEvent` stage or any `AppDomainAssemblyResolveHandlerInvoked` events, as the assembly was successfully loaded before reaching the step of the loading algorithm that raises the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb660-213">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb660-213">See also</span></span>

- [<span data-ttu-id="cb660-214">어셈블리 로더 이벤트</span><span class="sxs-lookup"><span data-stu-id="cb660-214">Assembly loader events</span></span>](../../fundamentals/diagnostics/runtime-loader-binder-events.md)
- [<span data-ttu-id="cb660-215">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="cb660-215">dotnet-trace</span></span>](../diagnostics/dotnet-trace.md)
- [<span data-ttu-id="cb660-216">PerfView</span><span class="sxs-lookup"><span data-stu-id="cb660-216">PerfView</span></span>](https://github.com/microsoft/perfview)
