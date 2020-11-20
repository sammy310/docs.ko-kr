---
title: PerfCollect를 사용하여 .NET 애플리케이션 추적
description: .NET에서 perfcollect를 사용하여 추적을 수집하는 과정을 안내하는 자습서입니다.
ms.topic: tutorial
ms.date: 10/23/2020
ms.openlocfilehash: 376c957833924a9991e574557671ea3c8503d7c2
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507243"
---
# <a name="trace-net-applications-with-perfcollect"></a><span data-ttu-id="508d3-103">PerfCollect를 사용하여 .NET 애플리케이션 추적</span><span class="sxs-lookup"><span data-stu-id="508d3-103">Trace .NET applications with PerfCollect</span></span>

<span data-ttu-id="508d3-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="508d3-104">**This article applies to: ✔️** .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="508d3-105">Linux에서 성능 문제가 발생하는 경우 `perfcollect`로 추적을 수집하면 성능 문제 발생 시 머신에서 발생한 상황에 대한 자세한 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-105">When performance problems are encountered on Linux, collecting a trace with `perfcollect` can be used to gather detailed information about what was happening on the machine at the time of the performance problem.</span></span>

<span data-ttu-id="508d3-106">`perfcollect`는 [LTTng(Linux Tracing Tookit-Next Generation)](https://lttng.org)를 활용하여 런타임이나 모든 [EventSource](xref:System.Diagnostics.Tracing.EventListener)에서 기록된 이벤트를 수집할 뿐만 아니라 [perf](https://perf.wiki.kernel.org/)를 활용하여 대상 프로세스의 CPU 샘플을 수집하는 bash 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-106">`perfcollect` is a bash script that leverages [Linux Tracing Tookit-Next Generation (LTTng)](https://lttng.org) to collect events written from the runtime or any [EventSource](xref:System.Diagnostics.Tracing.EventListener), as well as [perf](https://perf.wiki.kernel.org/) to collect CPU samples of the target process.</span></span>

## <a name="prepare-your-machine"></a><span data-ttu-id="508d3-107">머신 준비</span><span class="sxs-lookup"><span data-stu-id="508d3-107">Prepare your machine</span></span>

<span data-ttu-id="508d3-108">`perfcollect`로 성능 추적을 수집할 머신을 준비하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-108">Follow these steps to prepare your machine to collect a performance trace with `perfcollect`.</span></span>

> [!NOTE]
> <span data-ttu-id="508d3-109">컨테이너 환경에 있는 경우 컨테이너에 `SYS_ADMIN` 기능이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-109">If you are in a container environment, your container needs to have `SYS_ADMIN` capability.</span></span> <span data-ttu-id="508d3-110">PerfCollect를 사용하여 컨테이너 내 애플리케이션 추적에 대한 자세한 내용은 [컨테이너에서 진단 수집](./diagnostics-in-containers.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="508d3-110">For more information on tracing applications inside containers using PerfCollect, see [Collect diagnostics in containers](./diagnostics-in-containers.md).</span></span>

1. <span data-ttu-id="508d3-111">`perfcollect`를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-111">Download `perfcollect`.</span></span>

    > ```bash
    > curl -OL https://aka.ms/perfcollect
    > ```

2. <span data-ttu-id="508d3-112">스크립트를 실행 가능하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-112">Make the script executable.</span></span>

    > ```bash
    > chmod +x perfcollect
    > ```

3. <span data-ttu-id="508d3-113">추적 필수 구성 요소인 실제 추적 라이브러리를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-113">Install tracing prerequisites - these are the actual tracing libraries.</span></span>

    > ```bash
    > sudo ./perfcollect install
    > ```

    <span data-ttu-id="508d3-114">그러면 다음과 같은 필수 구성 요소가 머신에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-114">This will install the following prerequisites on your machine:</span></span>

    1. <span data-ttu-id="508d3-115">`perf`: Linux 성능 이벤트 하위 시스템과 수반되는 사용자 모드 컬렉션/뷰어 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-115">`perf`: the Linux Performance Events subsystem and companion user-mode collection/viewer application.</span></span> <span data-ttu-id="508d3-116">`perf`는 Linux 커널 소스의 일부이지만 보통 기본적으로 설치되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-116">`perf` is part of the Linux kernel source, but is not usually installed by default.</span></span>

    2. <span data-ttu-id="508d3-117">`LTTng`: CoreCLR에서 런타임에 내보낸 이벤트 데이터를 캡처하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-117">`LTTng`: Used to capture event data emitted at runtime by CoreCLR.</span></span> <span data-ttu-id="508d3-118">그런 다음, 이 데이터를 사용하여 GC, JIT, 스레드 풀과 같은 다양한 런타임 구성 요소의 동작을 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-118">This data is then used to analyze the behavior of various runtime components such as the GC, JIT, and thread pool.</span></span>

<span data-ttu-id="508d3-119">최신 버전의 .NET Core 및 Linux perf 도구는 프레임워크 코드의 메서드 이름 자동 확인을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-119">Recent versions of .NET Core and the Linux perf tool support automatic resolution of method names for framework code.</span></span> <span data-ttu-id="508d3-120">.NET Core 3.1 이전 버전을 사용하는 경우 추가 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-120">If you are working with .NET Core version 3.1 or less, an extra step is necessary.</span></span> <span data-ttu-id="508d3-121">자세한 내용은 [프레임워크 기호 확인](#resolve-framework-symbols)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="508d3-121">See [Resolving Framework Symbols](#resolve-framework-symbols) for details.</span></span>

<span data-ttu-id="508d3-122">네이티브 런타임 DLL(예: libcoreclr.so)의 메서드 이름을 확인하기 위해 `perfcollect`는 데이터를 변환할 때 기호를 확인하지만 이러한 이진에 대한 기호가 있는 경우에만 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-122">For resolving method names of native runtime DLLs (such as libcoreclr.so), `perfcollect` will resolve symbols for them when it converts the data, but only if the symbols for these binaries are present.</span></span> <span data-ttu-id="508d3-123">자세한 내용은 [네이티브 런타임에 대한 기호 가져오기](#get-symbols-for-the-native-runtime) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="508d3-123">See [Getting Symbols for the Native Runtime](#get-symbols-for-the-native-runtime) section for details.</span></span>

## <a name="collect-a-trace"></a><span data-ttu-id="508d3-124">추적 수집</span><span class="sxs-lookup"><span data-stu-id="508d3-124">Collect a trace</span></span>

1. <span data-ttu-id="508d3-125">두 개의 셸을 사용할 수 있습니다. 하나는 추적을 제어하는 데 사용되어 **[Trace]** 라고 하고 하나는 애플리케이션을 실행하는 데 사용되어 **[App]** 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-125">Have two shells available - one for controlling tracing, referred to as **[Trace]**, and one for running the application, referred to as **[App]**.</span></span>

2. <span data-ttu-id="508d3-126">**[Trace]** 컬렉션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-126">**[Trace]** Start collection.</span></span>

    > ```bash
    > sudo ./perfcollect collect sampleTrace
    > ```

    <span data-ttu-id="508d3-127">예상 출력:</span><span class="sxs-lookup"><span data-stu-id="508d3-127">Expected Output:</span></span>

    > ```bash
    > Collection started.  Press CTRL+C to stop.
    > ```

3. <span data-ttu-id="508d3-128">**[App]** 다음 환경 변수를 사용하여 애플리케이션 셸을 설정합니다. 따라서 CoreCLR의 구성 추적을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-128">**[App]** Set up the application shell with the following environment variables - this enables tracing configuration of CoreCLR.</span></span>

    > ```bash
    > export COMPlus_PerfMapEnabled=1
    > export COMPlus_EnableEventLog=1
    > ```

4. <span data-ttu-id="508d3-129">**[App]** 앱을 실행합니다. 성능 문제를 캡처하기 위해 실행해야 하는 한 앱이 실행되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-129">**[App]** Run the app - let it run as long as you need to in order to capture the performance problem.</span></span> <span data-ttu-id="508d3-130">조사하려는 성능 문제가 발생하는 기간을 충분히 캡처할 수 있다면 정확한 길이는 짧을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-130">The exact length can be as short as you need as long as it sufficiently captures the window of time where the performance problem you want to investigate occurs.</span></span>

    > ```bash
    > dotnet run
    > ```

5. <span data-ttu-id="508d3-131">**[Trace]** 컬렉션을 중지합니다. Ctrl+C를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-131">**[Trace]** Stop collection - hit CTRL+C.</span></span>

    > ```bash
    > ^C
    > ...STOPPED.
    >
    > Starting post-processing. This may take some time.
    >
    > Generating native image symbol files
    > ...SKIPPED
    > Saving native symbols
    > ...FINISHED
    > Exporting perf.data file
    > ...FINISHED
    > Compressing trace files
    > ...FINISHED
    > Cleaning up artifacts
    > ...FINISHED
    >
    > Trace saved to sampleTrace.trace.zip
    > ```

    <span data-ttu-id="508d3-132">이제 압축된 추적 파일이 현재 작업 디렉터리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-132">The compressed trace file is now stored in the current working directory.</span></span>

## <a name="view-a-trace"></a><span data-ttu-id="508d3-133">추적 보기</span><span class="sxs-lookup"><span data-stu-id="508d3-133">View a trace</span></span>

<span data-ttu-id="508d3-134">수집된 추적을 볼 수 있는 여러 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-134">There are a number of options for viewing the trace that was collected.</span></span> <span data-ttu-id="508d3-135">추적은 Windows에서 [PerfView](https://aka.ms/perfview)를 사용하여 가장 잘 볼 수 있지만 `PerfCollect` 자체나 `TraceCompass`를 사용하여 Linux에서 직접 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-135">Traces are best viewed using [PerfView](https://aka.ms/perfview) on Windows, but they can be viewed directly on Linux using `PerfCollect` itself or `TraceCompass`.</span></span>

### <a name="use-perfcollect-to-view-the-trace-file"></a><span data-ttu-id="508d3-136">PerfCollect를 사용하여 추적 파일 보기</span><span class="sxs-lookup"><span data-stu-id="508d3-136">Use PerfCollect to view the trace file</span></span>

<span data-ttu-id="508d3-137">PerfCollect 자체를 사용하여 수집한 추적을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-137">You can use perfcollect itself to view the trace that you collected.</span></span> <span data-ttu-id="508d3-138">이렇게 하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-138">To do this, use the following command:</span></span>

```bash
./perfcollect view sampleTrace.trace.zip
```

<span data-ttu-id="508d3-139">기본적으로 `perf`를 사용하여 애플리케이션의 CPU 추적을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-139">By default, this will show the CPU trace of the application using `perf`.</span></span>

<span data-ttu-id="508d3-140">`LTTng`를 통해 수집된 이벤트를 확인하려면 `-viewer lttng` 플래그를 전달하여 개별 이벤트를 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-140">To look at the events that were collected via `LTTng`, you can pass in the flag `-viewer lttng` to see the individual events:</span></span>

```bash
./perfcollect view sampleTrace.trace.zip -viewer lttng
```

<span data-ttu-id="508d3-141">그러면 `babeltrace` 뷰어를 사용하여 이벤트 페이로드를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-141">This will use `babeltrace` viewer to print the events payload:</span></span>

```bash
# [01:02:18.189217659] (+0.020132603) ubuntu-xenial DotNETRuntime:ExceptionThrown_V1: { cpu_id = 0 }, { ExceptionType = "System.Exception", ExceptionMessage = "An exception happened", ExceptionEIP = 139875671834775, ExceptionHRESULT = 2148734208, ExceptionFlags = 16, ClrInstanceID = 0 }
# [01:02:18.189250227] (+0.020165171) ubuntu-xenial DotNETRuntime:ExceptionCatchStart: { cpu_id = 0 }, { EntryEIP = 139873639728404, MethodID = 139873626968120, MethodName = "void [helloworld] helloworld.Program::Main(string[])", ClrInstanceID = 0 }
```

### <a name="use-perfview-to-open-the-trace-file"></a><span data-ttu-id="508d3-142">PerfView를 사용하여 추적 파일 열기</span><span class="sxs-lookup"><span data-stu-id="508d3-142">Use PerfView to open the trace file</span></span>

<span data-ttu-id="508d3-143">CPU 샘플과 이벤트의 집계 뷰를 보려면 Windows 머신에서 `PerfView`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-143">To see an aggregate view of both the CPU sample and the events, you can use `PerfView` on a Windows machine.</span></span>

1. <span data-ttu-id="508d3-144">Linux에서 Windows 머신으로 trace.zip 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-144">Copy the trace.zip file from Linux to a Windows machine.</span></span>

2. <span data-ttu-id="508d3-145"><https://aka.ms/perfview>에서 PerfView를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-145">Download PerfView from <https://aka.ms/perfview>.</span></span>

3. <span data-ttu-id="508d3-146">PerfView.exe 실행</span><span class="sxs-lookup"><span data-stu-id="508d3-146">Run PerfView.exe</span></span>

    > ```cmd
    > PerfView.exe <path to trace.zip file>
    > ```

<span data-ttu-id="508d3-147">PerfView는 추적 파일에 포함된 데이터에 따라 지원되는 보기 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-147">PerfView will display the list of views that are supported based on the data contained in the trace file.</span></span>

- <span data-ttu-id="508d3-148">CPU를 조사하려면 **CPU 스택** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-148">For CPU investigations, choose **CPU stacks**.</span></span>

- <span data-ttu-id="508d3-149">자세한 GC 정보를 보려면 **GCStats** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-149">For detailed GC information, choose **GCStats**.</span></span>

- <span data-ttu-id="508d3-150">프로세스/모듈/메서드별 JIT 정보를 보려면 **JITStats** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-150">For per-process/module/method JIT information, choose **JITStats**.</span></span>

- <span data-ttu-id="508d3-151">필요한 정보에 대한 보기가 없는 경우 원시 이벤트 보기에서 이벤트를 검색해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-151">If there is not a view for the information you need, you can try looking for the events in the raw events view.</span></span>  <span data-ttu-id="508d3-152">**이벤트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-152">Choose **Events**.</span></span>

<span data-ttu-id="508d3-153">PerfView에서 보기를 해석하는 방법에 대한 자세한 내용은 보기 자체의 도움말 링크를 참조하거나 PerfView의 주 창에서 **도움말-> 사용자 가이드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-153">For more information on how to interpret views in PerfView, see help links in the view itself, or from the main window in PerfView, choose **Help->Users Guide**.</span></span>

### <a name="use-tracecompass-to-open-the-trace-file"></a><span data-ttu-id="508d3-154">TraceCompass를 사용하여 추적 파일 열기</span><span class="sxs-lookup"><span data-stu-id="508d3-154">Use TraceCompass to open the trace file</span></span>

<span data-ttu-id="508d3-155">[Eclipse TraceCompass](https://www.eclipse.org/tracecompass/)는 추적을 보는 데 사용할 수 있는 또 다른 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-155">[Eclipse TraceCompass](https://www.eclipse.org/tracecompass/) is another option you can use to view the traces.</span></span> <span data-ttu-id="508d3-156">`TraceCompass`는 Linux 머신에서도 작동하므로 추적을 Windows 머신으로 이동할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-156">`TraceCompass` works on Linux machines as well, so you don't need to move your trace over to a Windows machine.</span></span> <span data-ttu-id="508d3-157">`TraceCompass`를 사용하여 추적 파일을 열려면 파일의 압축을 풀어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-157">To use `TraceCompass` to open your trace file, you will need to unzip the file.</span></span>

```bash
unzip myTrace.trace.zip
```

<span data-ttu-id="508d3-158">`perfcollect`는 수집된 LTTng 추적을 CTF 파일 형식으로 `lttngTrace`의 하위 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-158">`perfcollect` will save the LTTng trace it collected into a CTF file format in a subdirectory in the `lttngTrace`.</span></span> <span data-ttu-id="508d3-159">특히 CTF 파일은 `lttngTrace/auto-20201025-101230\ust\uid\1000\64-bit\` 같은 디렉터리에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-159">Specifically, the CTF file will be located in a directory that looks like `lttngTrace/auto-20201025-101230\ust\uid\1000\64-bit\`.</span></span>

<span data-ttu-id="508d3-160">`TraceCompass`에서 `File -> Open Trace`를 선택하고 `metadata` 파일을 선택하여 CTF 추적 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-160">You can open the CTF trace file in `TraceCompass` by selecting `File -> Open Trace` and select the `metadata` file.</span></span>

<span data-ttu-id="508d3-161">자세한 내용은 [`TraceCompass` 설명서](https://www.eclipse.org/tracecompass/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="508d3-161">For more details, please refer to [`TraceCompass` documentation](https://www.eclipse.org/tracecompass/).</span></span>

## <a name="resolve-framework-symbols"></a><span data-ttu-id="508d3-162">프레임워크 기호 확인</span><span class="sxs-lookup"><span data-stu-id="508d3-162">Resolve framework symbols</span></span>

<span data-ttu-id="508d3-163">프레임워크 기호는 추적이 수집될 때 수동으로 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-163">Framework symbols need to be manually generated at the time the trace is collected.</span></span> <span data-ttu-id="508d3-164">프레임워크는 앱 코드가 Just-In-Time 컴파일되는 동안 미리 컴파일되기 때문에 프레임워크 기호는 앱 수준 기호와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-164">They are different than app-level symbols because the framework is pre-compiled while app code is just-in-time-compiled.</span></span> <span data-ttu-id="508d3-165">네이티브 코드로 미리 컴파일된 프레임워크 코드의 경우 네이티브 코드에서 메서드 이름으로의 매핑을 생성하는 방법을 알고 있는 `crossgen`을 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-165">For framework code that was precompiled to native code, you need to call `crossgen` that knows how to generate the mapping from the native code to the name of the methods.</span></span>

<span data-ttu-id="508d3-166">`perfcollect`는 대부분의 세부 정보를 자동으로 처리할 수 있지만 `crossgen`을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-166">`perfcollect` can handle most of the details for you, but it needs to have `crossgen` available.</span></span> <span data-ttu-id="508d3-167">기본적으로 .NET 배포와 함께 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-167">By default it is not installed with .NET distribution.</span></span> <span data-ttu-id="508d3-168">`crossgen`이 없는 경우 `perfcollect`는 경고를 표시하고 이러한 지침을 참조하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-168">If `crossgen` is not there, `perfcollect` warns you and refers you to these instructions.</span></span> <span data-ttu-id="508d3-169">이러한 문제를 해결하려면 사용 중인 런타임에 올바른 버전의 crossgen을 정확하게 페치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-169">To fix things you need to fetch exactly the right version of crossgen for the runtime you are using.</span></span> <span data-ttu-id="508d3-170">crossgen 도구를 .NET 런타임 DLL과 같은 디렉터리(예: libcoreclr.so)에 배치하면 `perfcollect`에서 찾아 추적 파일에 프레임워크 기호를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-170">If you place the crossgen tool in the same directory as the .NET Runtime DLLs (for example, libcoreclr.so), then `perfcollect` can find it and add the framework symbols to the trace file for you.</span></span>

<span data-ttu-id="508d3-171">일반적으로 .NET 애플리케이션을 만들 때 직접 작성한 코드에 대한 DLL만 생성하고 나머지에는 런타임의 공유 복사본을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-171">Normally when you create a .NET application, it just generates the DLL for the code you wrote, using a shared copy of the runtime for the rest.</span></span>   <span data-ttu-id="508d3-172">그러나 애플리케이션의 ‘자체 포함’ 버전을 생성할 수도 있으며 여기에는 모든 런타임 DLL이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-172">However you can also generate what is called a 'self-contained' version of an application and this contains all runtime DLLs.</span></span> <span data-ttu-id="508d3-173">`crossgen`은 자체 포함 앱을 만드는 데 사용되는 NuGet 패키지의 일부이므로 애플리케이션의 자체 포함 패키지를 만들면 올바른 버전의 `crossgen`을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-173">`crossgen` is part of the NuGet package that is used to create self-contained apps, so one way of getting the right version of `crossgen` is to create a self-contained package of your application.</span></span>

<span data-ttu-id="508d3-174">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-174">For example:</span></span>

   >```bash
   > mkdir helloWorld
   > cd helloWorld
   > dotnet new console
   > dotnet publish --self-contained -r linux-x64
   >```

<span data-ttu-id="508d3-175">그러면 새 Hello World 애플리케이션이 만들어지고 자체 포함 앱으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-175">This creates a new Hello World application and builds it as a self-contained app.</span></span>

<span data-ttu-id="508d3-176">자체 포함 애플리케이션을 만드는 부작용으로 dotnet 도구는 runtime.linux-x64.microsoft.netcore.app이라는 NuGet 패키지를 다운로드하여 ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/VERSION 디렉터리에 저장합니다. 여기서 VERSION은 .NET Core 런타임의 버전 번호입니다(예: 2.1.0).</span><span class="sxs-lookup"><span data-stu-id="508d3-176">As a side effect of creating the self-contained application the dotnet tool will download a NuGet package called runtime.linux-x64.microsoft.netcore.app and place it in the directory ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/VERSION, where VERSION is the version number of your .NET Core runtime (for example, 2.1.0).</span></span> <span data-ttu-id="508d3-177">그 아래에 도구 디렉터리가 있고 이 디렉터리 내에 필요한 crossgen 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-177">Under that is a tools directory and inside there is the crossgen tool you need.</span></span> <span data-ttu-id="508d3-178">.NET Core 3.0부터는 패키지 위치가 ~/.nuget/packages/microsoft.netcore.app.runtime.linux-x64/VERSION입니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-178">Starting with .NET Core 3.0, the package location is ~/.nuget/packages/microsoft.netcore.app.runtime.linux-x64/VERSION.</span></span>

<span data-ttu-id="508d3-179">`crossgen` 도구는 실제로 애플리케이션에서 사용하는 런타임 옆에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-179">The `crossgen` tool needs to be put next to the runtime that is actually used by your application.</span></span> <span data-ttu-id="508d3-180">일반적으로 앱은 /usr/share/dotnet/shared/Microsoft.NETCore.App/VERSION에 설치되는 .NET Core의 공유 버전을 사용합니다. 여기서 VERSION은 .NET 런타임의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-180">Typically your app uses the shared version of .NET Core that is installed at /usr/share/dotnet/shared/Microsoft.NETCore.App/VERSION where VERSION is the version number of the .NET Runtime.</span></span> <span data-ttu-id="508d3-181">이 위치는 공유 위치이므로 수정하려면 슈퍼 사용자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-181">This is a shared location, so you need to be super-user to modify it.</span></span> <span data-ttu-id="508d3-182">VERSION이 2.1.0인 경우 `crossgen`을 업데이트하는 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-182">If the VERSION is 2.1.0 the commands to update `crossgen` would be:</span></span>

   >```bash
   > sudo bash
   > cp ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/2.1.0/tools/crossgen /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
   >```

<span data-ttu-id="508d3-183">작업이 완료되면 `perfcollect`에서 crossgen을 사용하여 프레임워크 기호를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-183">Once you have done this, `perfcollect` will use crossgen to include framework symbols.</span></span> <span data-ttu-id="508d3-184">`perfcollect`에서 발생하던 경고가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-184">The warning that `perfcollect` used to issue should go away.</span></span> <span data-ttu-id="508d3-185">런타임을 업데이트할 때까지 머신당 한 번만 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-185">This only has to be one once per machine (until you update your runtime).</span></span>

### <a name="alternative-turn-off-use-of-precompiled-code"></a><span data-ttu-id="508d3-186">다른 방법: 미리 컴파일된 코드 사용 해제</span><span class="sxs-lookup"><span data-stu-id="508d3-186">Alternative: Turn off use of precompiled code</span></span>

<span data-ttu-id="508d3-187">.NET 런타임을 업데이트하여 `crossgen`을 추가하는 기능이 없거나 여러 이유로 위의 절차가 작동하지 않는 경우 또 다른 방법으로 프레임워크 기호를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-187">If you don't have the ability to update the .NET Runtime (to add `crossgen`), or if the above procedure did not work for some reason, there is another approach to getting framework symbols.</span></span> <span data-ttu-id="508d3-188">미리 컴파일된 프레임워크 코드를 사용하지 않도록 런타임에 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-188">You can tell the runtime to simply not use the precompiled framework code.</span></span> <span data-ttu-id="508d3-189">그러면 코드가 Just-In-Time 컴파일되고 `crossgen`이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-189">The code will be Just-In-Time compiled and `crossgen` is not needed.</span></span>

> [!NOTE]
> <span data-ttu-id="508d3-190">이 방법을 선택하면 애플리케이션의 시작 시간이 길어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-190">Choosing this approach may increase the startup time for your application.</span></span>

<span data-ttu-id="508d3-191">이렇게 하려면 다음 환경 변수를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-191">To do this, you can add the following environment variable:</span></span>

```bash
export COMPlus_ZapDisable=1
```

<span data-ttu-id="508d3-192">이렇게 변경하면 모든 .NET 코드에 대한 기호를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-192">With this change, you should get the symbols for all .NET code.</span></span>

## <a name="get-symbols-for-the-native-runtime"></a><span data-ttu-id="508d3-193">네이티브 런타임에 대한 기호 가져오기</span><span class="sxs-lookup"><span data-stu-id="508d3-193">Get symbols for the native runtime</span></span>

<span data-ttu-id="508d3-194">대체로 개발자는 직접 작성한 코드에 관심이 있으며, 이러한 코드는 기본적으로 `perfcollect`에서 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-194">Most of the time you are interested in your own code, which `perfcollect` resolves by default.</span></span> <span data-ttu-id="508d3-195">경우에 따라 .NET DLL 내부의 진행 상황(마지막 섹션에서 다루는 내용)을 확인하는 것이 유용하지만, 경우에 따라서는 네이티브 런타임 DLL(일반적으로 libcoreclr.so)의 진행 상황이 흥미롭습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-195">Sometimes it is useful to see what is going on inside the .NET DLLs (which is what the last section was about), but sometimes what is going on in the native runtime dlls (typically libcoreclr.so), is interesting.</span></span>  <span data-ttu-id="508d3-196">`perfcollect`는 데이터를 변환할 때 이러한 기호를 확인하지만 이러한 네이티브 DLL에 대한 기호가 있고 대상 라이브러리 옆에 있을 때만 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-196">`perfcollect` will resolve the symbols for these when it converts its data, but only if the symbols for these native DLLs are present (and are beside the library they are for).</span></span>

<span data-ttu-id="508d3-197">[dotnet-symbol](https://github.com/dotnet/symstore/blob/master/src/dotnet-symbol/README.md#symbol-downloader-dotnet-cli-extension)이라는 전역 명령이 있어 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-197">There is a global command called [dotnet-symbol](https://github.com/dotnet/symstore/blob/master/src/dotnet-symbol/README.md#symbol-downloader-dotnet-cli-extension) that does this.</span></span> <span data-ttu-id="508d3-198">dotnet-symbol을 사용하여 네이티브 런타임 기호를 가져오려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-198">To use dotnet-symbol to get native runtime symbols:</span></span>

1. <span data-ttu-id="508d3-199">`dotnet-symbol` 설치:</span><span class="sxs-lookup"><span data-stu-id="508d3-199">Install `dotnet-symbol`:</span></span>

    ```bash
    dotnet tool install -g dotnet-symbol
    ```

2. <span data-ttu-id="508d3-200">기호를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-200">Download the symbols.</span></span> <span data-ttu-id="508d3-201">설치한 .NET Core 런타임 버전이 2.1.0인 경우 이 작업을 수행하는 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-201">If your installed version of the .NET Core runtime is 2.1.0, the command to do this is:</span></span>

    ```bash
    mkdir mySymbols
    dotnet symbol --symbols --output mySymbols  /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0/lib*.so
    ```

3. <span data-ttu-id="508d3-202">기호를 올바른 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-202">Copy the symbols to the correct place.</span></span>

    ```bash
    sudo cp mySymbols/* /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
    ```

    <span data-ttu-id="508d3-203">적절한 디렉터리에 대한 쓰기 권한이 없어 이 작업을 수행할 수 없는 경우 `perf buildid-cache`를 사용하여 기호를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-203">If this cannot be done because you do not have write access to the appropriate directory, you can use `perf buildid-cache` to add the symbols.</span></span>

<span data-ttu-id="508d3-204">그러면 `perfcollect`를 실행할 때 네이티브 dll의 기호 이름을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d3-204">After this, you should get symbolic names for the native dlls when you run `perfcollect`.</span></span>

## <a name="collect-in-a-docker-container"></a><span data-ttu-id="508d3-205">Docker 컨테이너에서 수집</span><span class="sxs-lookup"><span data-stu-id="508d3-205">Collect in a Docker container</span></span>

<span data-ttu-id="508d3-206">컨테이너 환경에서 `perfcollect`를 사용하는 방법에 대한 자세한 내용은 [컨테이너에서 진단 수집](./diagnostics-in-containers.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="508d3-206">For more information on how to use `perfcollect` in container environments, see [Collect diagnostics in containers](./diagnostics-in-containers.md).</span></span>
