---
title: 높은 CPU 사용량 디버그 - .NET 코어
description: .NET Core의 높은 CPU 사용량을 디버깅하는 과정을 안내하는 자습서입니다.
ms.topic: tutorial
ms.date: 07/20/2020
ms.openlocfilehash: 3ba07f0bb40f8128c091fa427b957d824c07bcd5
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105364"
---
# <a name="debug-high-cpu-usage-in-net-core"></a><span data-ttu-id="2b90a-103">.NET 코어에서 높은 CPU 사용량 디버그</span><span class="sxs-lookup"><span data-stu-id="2b90a-103">Debug high CPU usage in .NET Core</span></span>

<span data-ttu-id="2b90a-104">**이 문서의 적용 대상: ✔️** .NET Core 3.1. SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="2b90a-104">**This article applies to: ✔️** .NET Core 3.1 SDK and later versions</span></span>

<span data-ttu-id="2b90a-105">이 자습서에서는 과도한 CPU 사용량 시나리오를 디버그하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-105">In this tutorial, you'll learn how to debug an excessive CPU usage scenario.</span></span> <span data-ttu-id="2b90a-106">제공된 예제 [ASP.NET Core 웹앱](/samples/dotnet/samples/diagnostic-scenarios) 소스 코드 리포지토리를 사용하면 교착 상태를 의도적으로 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-106">Using the provided example [ASP.NET Core web app](/samples/dotnet/samples/diagnostic-scenarios) source code repository, you can cause a deadlock intentionally.</span></span> <span data-ttu-id="2b90a-107">엔드포인트에서 중단 및 스레드 누적이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-107">The endpoint will experience a hang and thread accumulation.</span></span> <span data-ttu-id="2b90a-108">다양한 도구를 사용하여 진단 데이터의 몇 가지 주요 부분으로 이 시나리오를 진단하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-108">You'll learn how you can use various tools to diagnose this scenario with several key pieces of diagnostics data.</span></span>

<span data-ttu-id="2b90a-109">이 자습서에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-109">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="2b90a-110">높은 CPU 사용량 조사</span><span class="sxs-lookup"><span data-stu-id="2b90a-110">Investigate high CPU usage</span></span>
> - <span data-ttu-id="2b90a-111">[dotnet-counters](dotnet-counters.md)를 사용하여 CPU 사용량 확인</span><span class="sxs-lookup"><span data-stu-id="2b90a-111">Determine CPU usage with [dotnet-counters](dotnet-counters.md)</span></span>
> - <span data-ttu-id="2b90a-112">추적 생성을 위해 [dotnet-trace](dotnet-trace.md) 사용</span><span class="sxs-lookup"><span data-stu-id="2b90a-112">Use [dotnet-trace](dotnet-trace.md) for trace generation</span></span>
> - <span data-ttu-id="2b90a-113">PerfView에서 성능 프로파일링</span><span class="sxs-lookup"><span data-stu-id="2b90a-113">Profile performance in PerfView</span></span>
> - <span data-ttu-id="2b90a-114">과도한 CPU 사용량 진단 및 해결</span><span class="sxs-lookup"><span data-stu-id="2b90a-114">Diagnose and solve excessive CPU usage</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2b90a-115">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b90a-115">Prerequisites</span></span>

<span data-ttu-id="2b90a-116">이 자습서에서는 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-116">The tutorial uses:</span></span>

- <span data-ttu-id="2b90a-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet) 이상 버전.</span><span class="sxs-lookup"><span data-stu-id="2b90a-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet) or a later version.</span></span>
- <span data-ttu-id="2b90a-118">시나리오를 트리거하는 [샘플 디버그 대상](/samples/dotnet/samples/diagnostic-scenarios).</span><span class="sxs-lookup"><span data-stu-id="2b90a-118">[Sample debug target](/samples/dotnet/samples/diagnostic-scenarios) to trigger the scenario.</span></span>
- <span data-ttu-id="2b90a-119">프로세스를 나열하고 프로필을 생성하는 [dotnet-trace](dotnet-trace.md).</span><span class="sxs-lookup"><span data-stu-id="2b90a-119">[dotnet-trace](dotnet-trace.md) to list processes and generate a profile.</span></span>
- <span data-ttu-id="2b90a-120">CPU 사용량을 모니터링하는 [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="2b90a-120">[dotnet-counters](dotnet-counters.md) to monitor cpu usage.</span></span>

## <a name="cpu-counters"></a><span data-ttu-id="2b90a-121">CPU 카운터</span><span class="sxs-lookup"><span data-stu-id="2b90a-121">CPU counters</span></span>

<span data-ttu-id="2b90a-122">진단 데이터를 수집하기 전에 높은 CPU 판단 기준을 관찰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-122">Before attempting to collect diagnostics data, you need to observe a high CPU condition.</span></span> <span data-ttu-id="2b90a-123">프로젝트 루트 디렉터리에서 다음 명령을 사용하여 [샘플 애플리케이션](/samples/dotnet/samples/diagnostic-scenarios)을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-123">Run the [sample application](/samples/dotnet/samples/diagnostic-scenarios) using the following command from the project root directory.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="2b90a-124">프로세스 ID를 찾으려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-124">To find the process ID, use the following command:</span></span>

```dotnetcli
dotnet-trace ps
```

<span data-ttu-id="2b90a-125">명령 출력에서 프로세스 ID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-125">Take note of the process ID from your command output.</span></span> <span data-ttu-id="2b90a-126">기존 프로세스 ID는 `22884`였지만 사용자의 프로세스 ID는 다를 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-126">Our process ID was `22884`, but yours will be different.</span></span> <span data-ttu-id="2b90a-127">현재 CPU 사용량을 확인하려면 [dotnet-counters](dotnet-counters.md) 도구 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-127">To check the current CPU usage, use the [dotnet-counters](dotnet-counters.md) tool command:</span></span>

```dotnetcli
dotnet-counters monitor --refresh-interval 1 -p 22884
```

<span data-ttu-id="2b90a-128">`refresh-interval`은 카운터 폴링 CPU 값 사이의 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-128">The `refresh-interval` is the number of seconds between the counter polling CPU values.</span></span> <span data-ttu-id="2b90a-129">출력은 다음과 같은 형태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-129">The output should be similar to the following:</span></span>

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    % Time in GC since last GC (%)                         0
    Allocation Rate / 1 sec (B)                            0
    CPU Usage (%)                                          0
    Exception Count / 1 sec                                0
    GC Heap Size (MB)                                      4
    Gen 0 GC Count / 60 sec                                0
    Gen 0 Size (B)                                         0
    Gen 1 GC Count / 60 sec                                0
    Gen 1 Size (B)                                         0
    Gen 2 GC Count / 60 sec                                0
    Gen 2 Size (B)                                         0
    LOH Size (B)                                           0
    Monitor Lock Contention Count / 1 sec                  0
    Number of Active Timers                                1
    Number of Assemblies Loaded                          140
    ThreadPool Completed Work Item Count / 1 sec           3
    ThreadPool Queue Length                                0
    ThreadPool Thread Count                                7
    Working Set (MB)                                      63
```

<span data-ttu-id="2b90a-130">웹앱을 실행하면 시작 직후에 CPU가 전혀 소비되지 않고 `0%`에 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-130">With the web app running, immediately after startup, the CPU isn't being consumed at all and is reported at `0%`.</span></span> <span data-ttu-id="2b90a-131">경로 매개 변수로 `60000`을 사용하여 `api/diagscenario/highcpu` 경로로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-131">Navigate to the `api/diagscenario/highcpu` route with `60000` as the route parameter:</span></span>

`https://localhost:5001/api/diagscenario/highcpu/60000`

<span data-ttu-id="2b90a-132">이제 [dotnet-counters](dotnet-counters.md) 명령을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-132">Now, rerun the [dotnet-counters](dotnet-counters.md) command.</span></span> <span data-ttu-id="2b90a-133">`cpu-usage`만 모니터링하려면 `System.Runtime[cpu-usage]`을 명령의 일부로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-133">To monitor just the `cpu-usage`, specify `System.Runtime[cpu-usage]` as part of the command.</span></span>

```dotnetcli
dotnet-counters monitor --counters System.Runtime[cpu-usage] -p 22884 --refresh-interval 1
```

<span data-ttu-id="2b90a-134">아래와 같이 CPU 사용량이 증가하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-134">You should see an increase in CPU usage as shown below:</span></span>

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    CPU Usage (%)                                         25
```

<span data-ttu-id="2b90a-135">요청 기간 동안 CPU 사용량은 약 25%입니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-135">Throughout the duration of the request, the CPU usage will hover around 25% .</span></span> <span data-ttu-id="2b90a-136">호스트 컴퓨터에 따라 CPU 사용량은 다양할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-136">Depending on the host machine, expect varying CPU usage.</span></span>

> [!TIP]
> <span data-ttu-id="2b90a-137">더 높은 CPU 사용량을 시각화하기 위해 여러 브라우저 탭에서 이 엔드포인트를 동시에 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-137">To visualize an even higher CPU usage, you can exercise this endpoint in multiple browser tabs simultaneously.</span></span>

<span data-ttu-id="2b90a-138">이 시점에서는 CPU가 예상보다 높게 실행되고 있다고 봐도 무방합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-138">At this point, you can safely say the CPU is running higher than you expect.</span></span>

## <a name="trace-generation"></a><span data-ttu-id="2b90a-139">추적 생성</span><span class="sxs-lookup"><span data-stu-id="2b90a-139">Trace generation</span></span>

<span data-ttu-id="2b90a-140">저속 요청을 분석할 때 코드가 수행하는 작업에 대한 정보를 제공할 수 있는 진단 도구가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-140">When analyzing a slow request, you need a diagnostics tool that can provide insights into what the code is doing.</span></span> <span data-ttu-id="2b90a-141">일반적으로 프로파일러를 선택하며, 선택할 수 있는 다양한 프로파일러 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-141">The usual choice is a profiler, and there are different profiler options to choose from.</span></span>

### <a name="linux"></a>[<span data-ttu-id="2b90a-142">Linux</span><span class="sxs-lookup"><span data-stu-id="2b90a-142">Linux</span></span>](#tab/linux)

<span data-ttu-id="2b90a-143">`perf` 도구를 사용하여 .NET Core 앱 프로필을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-143">The `perf` tool can be used to generate .NET Core app profiles.</span></span> <span data-ttu-id="2b90a-144">[샘플 디버그 대상](/samples/dotnet/samples/diagnostic-scenarios)의 이전 인스턴스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-144">Exit the previous instance of the [sample debug target](/samples/dotnet/samples/diagnostic-scenarios).</span></span>

<span data-ttu-id="2b90a-145">`COMPlus_PerfMapEnabled` 환경 변수를 설정하여 .NET Core 앱이 `/tmp` 디렉터리에 `map` 파일을 만들도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-145">Set the `COMPlus_PerfMapEnabled` environment variable to cause the .NET Core app to create a `map` file in the `/tmp` directory.</span></span> <span data-ttu-id="2b90a-146">이 `map` 파일은 `perf`에서 CPU 주소를 이름별로 JIT 생성 함수에 매핑하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-146">This `map` file is used by `perf` to map CPU address to JIT-generated functions by name.</span></span> <span data-ttu-id="2b90a-147">자세한 내용은 [perf 맵 작성](../run-time-config/debugging-profiling.md#write-perf-map)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b90a-147">For more information, see [Write perf map](../run-time-config/debugging-profiling.md#write-perf-map).</span></span>

<span data-ttu-id="2b90a-148">동일한 터미널 세션에서 [샘플 디버그 대상](/samples/dotnet/samples/diagnostic-scenarios)을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-148">Run the [sample debug target](/samples/dotnet/samples/diagnostic-scenarios) in the same terminal session.</span></span>

```dotnetcli
export COMPlus_PerfMapEnabled=1
dotnet run
```

<span data-ttu-id="2b90a-149">높은 CPU API 엔드포인트(`https://localhost:5001/api/diagscenario/highcpu/60000`)를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-149">Exercise the high CPU API endpoint (`https://localhost:5001/api/diagscenario/highcpu/60000`) again.</span></span> <span data-ttu-id="2b90a-150">1분 요청 내에서 실행되는 동안 프로세스 ID를 사용하여 `perf` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-150">While it's running within the 1-minute request, run the `perf` command with your process ID:</span></span>

```bash
sudo perf record -p 2266 -g
```

<span data-ttu-id="2b90a-151">`perf` 명령이 성능 수집 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-151">The `perf` command starts the performance collection process.</span></span> <span data-ttu-id="2b90a-152">약 20-30초 동안 실행한 후 <kbd>Ctrl+C</kbd>를 눌러 수집 프로세스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-152">Let it run for about 20-30 seconds, then press <kbd>Ctrl+C</kbd> to exit the collection process.</span></span> <span data-ttu-id="2b90a-153">동일한 `perf` 명령을 사용하여 추적의 출력을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-153">You can use the same `perf` command to see the output of the trace.</span></span>

```bash
sudo perf report -f
```

<span data-ttu-id="2b90a-154">다음 명령을 사용하여 _flame-graph_ 를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-154">You can also generate a _flame-graph_ by using the following commands:</span></span>

```bash
git clone --depth=1 https://github.com/BrendanGregg/FlameGraph
sudo perf script | FlameGraph/stackcollapse-perf.pl | FlameGraph/flamegraph.pl > flamegraph.svg
```

<span data-ttu-id="2b90a-155">이 명령은 성능 문제를 조사하기 위해 브라우저에서 볼 수 있는 `flamegraph.svg`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-155">This command generates a `flamegraph.svg` that you can view in the browser to investigate the performance problem:</span></span>

<span data-ttu-id="2b90a-156">[![플레임 그래프 SVG 이미지](media/flamegraph.jpg)](media/flamegraph.jpg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2b90a-156">[![Flame graph SVG image](media/flamegraph.jpg)](media/flamegraph.jpg#lightbox)</span></span>

### <a name="windows"></a>[<span data-ttu-id="2b90a-157">Windows</span><span class="sxs-lookup"><span data-stu-id="2b90a-157">Windows</span></span>](#tab/windows)

<span data-ttu-id="2b90a-158">Windows에서는 [dotnet-trace](dotnet-trace.md) 도구를 프로파일러로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-158">On Windows, you can use the [dotnet-trace](dotnet-trace.md) tool as a profiler.</span></span> <span data-ttu-id="2b90a-159">이전 [샘플 디버그 대상](/samples/dotnet/samples/diagnostic-scenarios)을 사용하여 높은 CPU 엔드포인트(`https://localhost:5001/api/diagscenario/highcpu/60000`)를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-159">Using the previous [sample debug target](/samples/dotnet/samples/diagnostic-scenarios), exercise the high CPU endpoint (`https://localhost:5001/api/diagscenario/highcpu/60000`) again.</span></span> <span data-ttu-id="2b90a-160">1분 요청 내에서 실행되는 동안 다음과 같이 `collect` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-160">While it's running within the 1-minute request, use the `collect` command as follows:</span></span>

```dotnetcli
dotnet-trace collect -p 22884 --providers Microsoft-DotNETCore-SampleProfiler
```

<span data-ttu-id="2b90a-161">[dotnet-trace](dotnet-trace.md)를 약 20-30초 동안 실행한 후 <kbd>Enter</kbd>를 눌러 컬렉션을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-161">Let [dotnet-trace](dotnet-trace.md) run for about 20-30 seconds, and then press the <kbd>Enter</kbd> to exit the collection.</span></span> <span data-ttu-id="2b90a-162">그 결과, 동일한 폴더에 `nettrace` 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-162">The result is a `nettrace` file located in the same folder.</span></span> <span data-ttu-id="2b90a-163">`nettrace` 파일은 Windows에서 기존 분석 도구를 사용하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-163">The `nettrace` files are a great way to use existing analysis tools on Windows.</span></span>

<span data-ttu-id="2b90a-164">아래와 같이 [`PerfView`](https://github.com/microsoft/perfview/blob/master/documentation/Downloading.md)를 사용하여 `nettrace`를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2b90a-164">Open the `nettrace` with [`PerfView`](https://github.com/microsoft/perfview/blob/master/documentation/Downloading.md) as shown below.</span></span>

<span data-ttu-id="2b90a-165">[![PerfView 이미지](media/perfview.jpg)](media/perfview.jpg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2b90a-165">[![PerfView image](media/perfview.jpg)](media/perfview.jpg#lightbox)</span></span>

---

## <a name="see-also"></a><span data-ttu-id="2b90a-166">참조</span><span class="sxs-lookup"><span data-stu-id="2b90a-166">See also</span></span>

- <span data-ttu-id="2b90a-167">프로세스를 나열하는 [dotnet-trace](dotnet-trace.md)</span><span class="sxs-lookup"><span data-stu-id="2b90a-167">[dotnet-trace](dotnet-trace.md) to list processes</span></span>
- <span data-ttu-id="2b90a-168">관리되는 메모리 사용량을 검사하는 [dotnet-counters](dotnet-counters.md)</span><span class="sxs-lookup"><span data-stu-id="2b90a-168">[dotnet-counters](dotnet-counters.md) to check managed memory usage</span></span>
- <span data-ttu-id="2b90a-169">덤프 파일을 수집 및 분석하는 [dotnet-dump](dotnet-dump.md)</span><span class="sxs-lookup"><span data-stu-id="2b90a-169">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file</span></span>
- [<span data-ttu-id="2b90a-170">dotnet/diagnostics</span><span class="sxs-lookup"><span data-stu-id="2b90a-170">dotnet/diagnostics</span></span>](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a><span data-ttu-id="2b90a-171">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2b90a-171">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2b90a-172">.NET Core의 교착 상태 디버그</span><span class="sxs-lookup"><span data-stu-id="2b90a-172">Debug a deadlock in .NET Core</span></span>](debug-deadlock.md)
