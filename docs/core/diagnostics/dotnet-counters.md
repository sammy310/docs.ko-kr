---
title: dotnet-counters - .NET Core
description: dotnet-counter 명령줄 도구를 설치하고 사용하는 방법에 대해 알아봅니다.
ms.date: 02/26/2020
ms.openlocfilehash: 7ff29ad91ad271afd35e3d38a4d748bc79ad6c03
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507256"
---
# <a name="dotnet-counters"></a><span data-ttu-id="319a6-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="319a6-103">dotnet-counters</span></span>

<span data-ttu-id="319a6-104">**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="319a6-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="319a6-105">dotnet-counters 설치</span><span class="sxs-lookup"><span data-stu-id="319a6-105">Install dotnet-counters</span></span>

<span data-ttu-id="319a6-106">`dotnet-counters` [NuGet 패키지](https://www.nuget.org/packages/dotnet-counters)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="319a6-107">개요</span><span class="sxs-lookup"><span data-stu-id="319a6-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="319a6-108">설명</span><span class="sxs-lookup"><span data-stu-id="319a6-108">Description</span></span>

<span data-ttu-id="319a6-109">`dotnet-counters`는 임시 상태 모니터링 및 1단계 수준 성능 조사를 위한 성능 모니터링 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="319a6-110"><xref:System.Diagnostics.Tracing.EventCounter> API를 통해 게시된 성능 카운터 값을 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="319a6-111">예를 들어, `PerfView` 또는 `dotnet-trace`를 사용하여 보다 심각한 성능 조사를 살펴보기 전에 의심스러운 내용이 있는지 확인하기 위해 .NET Core 애플리케이션에서 throw되는 CPU 사용량 또는 예외 비율과 같은 항목을 신속하게 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="319a6-112">옵션</span><span class="sxs-lookup"><span data-stu-id="319a6-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="319a6-113">dotnet-counters 유틸리티의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="319a6-114">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="319a6-115">명령</span><span class="sxs-lookup"><span data-stu-id="319a6-115">Commands</span></span>

| <span data-ttu-id="319a6-116">명령</span><span class="sxs-lookup"><span data-stu-id="319a6-116">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="319a6-117">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="319a6-117">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="319a6-118">dotnet-counters 목록</span><span class="sxs-lookup"><span data-stu-id="319a6-118">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="319a6-119">dotnet-counters 모니터</span><span class="sxs-lookup"><span data-stu-id="319a6-119">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="319a6-120">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="319a6-120">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="319a6-121">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="319a6-121">dotnet-counters collect</span></span>

<span data-ttu-id="319a6-122">선택한 카운터 값을 주기적으로 수집하고 후처리를 위해 지정된 파일 형식으로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-122">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="319a6-123">개요</span><span class="sxs-lookup"><span data-stu-id="319a6-123">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="319a6-124">옵션</span><span class="sxs-lookup"><span data-stu-id="319a6-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="319a6-125">모니터링할 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-125">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="319a6-126">표시된 카운터 업데이트 사이의 지연 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-126">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="319a6-127">쉼표로 구분된 카운터 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-127">A comma-separated list of counters.</span></span> <span data-ttu-id="319a6-128">카운터는 `provider_name[:counter_name]`을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-128">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="319a6-129">적격 카운터 목록 없이 `provider_name`이 사용되는 경우 공급자의 모든 카운터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-129">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="319a6-130">공급자 및 카운터 이름을 검색하려면 [dotnet-counters 목록](#dotnet-counters-list) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-130">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="319a6-131">내보낼 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-131">The format to be exported.</span></span> <span data-ttu-id="319a6-132">현재 csv와 json을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-132">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="319a6-133">출력 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-133">The name of the output file.</span></span>

- <span data-ttu-id="319a6-134">**`-- <command>`(.NET 5.0 이상을 실행하는 대상 애플리케이션만 해당)**</span><span class="sxs-lookup"><span data-stu-id="319a6-134">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="319a6-135">사용자는 컬렉션 구성 매개 변수 다음에 `--`와 명령을 차례로 추가하여 5.0 런타임 이상에서 .NET 애플리케이션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-135">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="319a6-136">`dotnet-counters`는 제공된 명령을 사용하여 프로세스를 시작하고 요청된 메트릭을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-136">`dotnet-counters` will launch a process with the provided command and collect the requested metrics.</span></span> <span data-ttu-id="319a6-137">이 옵션은 애플리케이션의 시작 경로에 대한 메트릭을 수집하는 데 유용하며, 주요 진입점 이전이나 바로 다음에 발생하는 문제를 진단하거나 모니터링하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-137">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

> [!NOTE]
> <span data-ttu-id="319a6-138">이 옵션을 사용하면 도구에 다시 전달되는 첫 번째 .NET 5.0 프로세스가 모니터링됩니다. 즉, 명령에서 여러 .NET 애플리케이션을 시작하는 경우 첫 번째 앱만 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-138">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="319a6-139">따라서 자체 포함 애플리케이션에서 이 옵션을 사용하거나 `dotnet exec <app.dll>` 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-139">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

### <a name="examples"></a><span data-ttu-id="319a6-140">예</span><span class="sxs-lookup"><span data-stu-id="319a6-140">Examples</span></span>

- <span data-ttu-id="319a6-141">3초의 새로 고침 간격으로 모든 카운터를 수집하고 csv를 출력으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-141">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- <span data-ttu-id="319a6-142">`dotnet mvc.dll`을 자식 프로세스로 시작하고 시작에서 런타임 카운터 및 ASP.NET Core 호스팅 카운터 수집을 시작하여 JSON 출력으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-142">Start `dotnet mvc.dll` as a child process and start collecting runtime counters and ASP.NET Core Hosting counters from startup and save it as a JSON output:</span></span>

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="319a6-143">dotnet-counters 목록</span><span class="sxs-lookup"><span data-stu-id="319a6-143">dotnet-counters list</span></span>

<span data-ttu-id="319a6-144">공급자별로 그룹화된 카운터 이름 및 설명 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-144">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="319a6-145">개요</span><span class="sxs-lookup"><span data-stu-id="319a6-145">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="319a6-146">예제</span><span class="sxs-lookup"><span data-stu-id="319a6-146">Example</span></span>

```console
> dotnet-counters list
Showing well-known counters only. Specific processes may support additional counters.

System.Runtime
    cpu-usage                                    Amount of time the process has utilized the CPU (ms)
    working-set                                  Amount of working set used by the process (MB)
    gc-heap-size                                 Total heap size reported by the GC (MB)
    gen-0-gc-count                               Number of Gen 0 GCs / min
    gen-1-gc-count                               Number of Gen 1 GCs / min
    gen-2-gc-count                               Number of Gen 2 GCs / min
    time-in-gc                                   % time in GC since the last GC
    gen-0-size                                   Gen 0 Heap Size
    gen-1-size                                   Gen 1 Heap Size
    gen-2-size                                   Gen 2 Heap Size
    loh-size                                     LOH Heap Size
    alloc-rate                                   Allocation Rate
    assembly-count                               Number of Assemblies Loaded
    exception-count                              Number of Exceptions / sec
    threadpool-thread-count                      Number of ThreadPool Threads
    monitor-lock-contention-count                Monitor Lock Contention Count
    threadpool-queue-length                      ThreadPool Work Items Queue Length
    threadpool-completed-items-count             ThreadPool Completed Work Items Count
    active-timer-count                           Active Timers Count

Microsoft.AspNetCore.Hosting
    requests-per-second                  Request rate
    total-requests                       Total number of requests
    current-requests                     Current number of requests
    failed-requests                      Failed number of requests
```

> [!NOTE]
> <span data-ttu-id="319a6-147">이러한 카운터를 지원하는 프로세스를 식별한 경우, 예를 들어 호스트 머신에서 ASP.NET Core 애플리케이션이 실행되고 있는 경우 `Microsoft.AspNetCore.Hosting` 카운터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-147">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="319a6-148">dotnet-counters 모니터</span><span class="sxs-lookup"><span data-stu-id="319a6-148">dotnet-counters monitor</span></span>

<span data-ttu-id="319a6-149">선택한 카운터의 값을 주기적으로 새로 고치는 방법을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-149">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="319a6-150">개요</span><span class="sxs-lookup"><span data-stu-id="319a6-150">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [--counters] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="319a6-151">옵션</span><span class="sxs-lookup"><span data-stu-id="319a6-151">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="319a6-152">모니터링할 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-152">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="319a6-153">표시된 카운터 업데이트 사이의 지연 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-153">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="319a6-154">쉼표로 구분된 카운터 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-154">A comma-separated list of counters.</span></span> <span data-ttu-id="319a6-155">카운터는 `provider_name[:counter_name]`을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-155">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="319a6-156">적격 카운터 목록 없이 `provider_name`이 사용되는 경우 공급자의 모든 카운터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-156">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="319a6-157">공급자 및 카운터 이름을 검색하려면 [dotnet-counters 목록](#dotnet-counters-list) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-157">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

 <span data-ttu-id="319a6-158">**`-- <command>`(.NET 5.0 이상을 실행하는 대상 애플리케이션만 해당)**</span><span class="sxs-lookup"><span data-stu-id="319a6-158">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="319a6-159">사용자는 컬렉션 구성 매개 변수 다음에 `--`와 명령을 차례로 추가하여 5.0 런타임 이상에서 .NET 애플리케이션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-159">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="319a6-160">`dotnet-counters`는 제공된 명령을 사용하여 프로세스를 시작하고 요청된 메트릭을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-160">`dotnet-counters` will launch a process with the provided command and monitor the requested metrics.</span></span> <span data-ttu-id="319a6-161">이 옵션은 애플리케이션의 시작 경로에 대한 메트릭을 수집하는 데 유용하며, 주요 진입점 이전이나 바로 다음에 발생하는 문제를 진단하거나 모니터링하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-161">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="319a6-162">이 옵션을 사용하면 도구에 다시 전달되는 첫 번째 .NET 5.0 프로세스가 모니터링됩니다. 즉, 명령에서 여러 .NET 애플리케이션을 시작하는 경우 첫 번째 앱만 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-162">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="319a6-163">따라서 자체 포함 애플리케이션에서 이 옵션을 사용하거나 `dotnet exec <app.dll>` 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-163">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

### <a name="examples"></a><span data-ttu-id="319a6-164">예</span><span class="sxs-lookup"><span data-stu-id="319a6-164">Examples</span></span>

- <span data-ttu-id="319a6-165">3초의 새로 고침 간격으로 `System.Runtime`의 모든 카운터를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-165">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 --counters System.Runtime
  Press p to pause, r to resume, q to quit.
      Status: Running

  [System.Runtime]
      % Time in GC since last GC (%)                                 0
      Allocation Rate (B / 1 sec)                                5,376
      CPU Usage (%)                                                  0
      Exception Count (Count / 1 sec)                                0
      GC Fragmentation (%)                                          48.467
      GC Heap Size (MB)                                              0
      Gen 0 GC Count (Count / 1 sec)                                 1
      Gen 0 Size (B)                                                24
      Gen 1 GC Count (Count / 1 sec)                                 1
      Gen 1 Size (B)                                                24
      Gen 2 GC Count (Count / 1 sec)                                 1
      Gen 2 Size (B)                                           272,000
      IL Bytes Jitted (B)                                       19,449
      LOH Size (B)                                              19,640
      Monitor Lock Contention Count (Count / 1 sec)                  0
      Number of Active Timers                                        0
      Number of Assemblies Loaded                                    7
      Number of Methods Jitted                                     166
      POH (Pinned Object Heap) Size (B)                             24
      ThreadPool Completed Work Item Count (Count / 1 sec)           0
      ThreadPool Queue Length                                        0
      ThreadPool Thread Count                                        2
      Working Set (MB)                                              19
  ```

- <span data-ttu-id="319a6-166">`System.Runtime`에서 CPU 사용량 및 GC 힙 크기만 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-166">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="319a6-167">사용자 정의 `EventSource`에서 `EventCounter` 값을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-167">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="319a6-168">자세한 내용은 [자습서: .NET Core에서 EventCounters를 사용하여 성능 측정](event-counter-perf.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="319a6-168">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- <span data-ttu-id="319a6-169">`my-aspnet-server.exe`를 시작하고 시작에서 로드된 어셈블리 수를 모니터링합니다(.NET 5.0 이상만 해당).</span><span class="sxs-lookup"><span data-stu-id="319a6-169">Launch `my-aspnet-server.exe` and monitor the # of assemblies loaded from its startup (.NET 5.0 or later only):</span></span>

  <span data-ttu-id="319a6-170">참고:  .NET 5.0 이상을 실행하는 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-170">NOTE: This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- <span data-ttu-id="319a6-171">`arg1` 및 `arg2`를 명령줄 인수로 사용하여 `my-aspnet-server.exe`를 시작하고 시작에서 작업 집합 및 GC 힙 크기를 모니터링합니다(.NET 5.0 이상만 해당).</span><span class="sxs-lookup"><span data-stu-id="319a6-171">Launch `my-aspnet-server.exe` with `arg1` and `arg2` as command-line arguments and monitor its working set and GC heap size from its startup (.NET 5.0 or later only):</span></span>

  <span data-ttu-id="319a6-172">참고:  .NET 5.0 이상을 실행하는 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-172">NOTE: This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[working-set,gc-heap-size] -- my-aspnet-server.exe arg1 arg2
  ```

  ```console
  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      GC Heap Size (MB)                                 39
      Working Set (MB)                                  59
  ```

## <a name="dotnet-counters-ps"></a><span data-ttu-id="319a6-173">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="319a6-173">dotnet-counters ps</span></span>

<span data-ttu-id="319a6-174">모니터링할 수 있는 dotnet 프로세스의 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="319a6-174">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="319a6-175">개요</span><span class="sxs-lookup"><span data-stu-id="319a6-175">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="319a6-176">예제</span><span class="sxs-lookup"><span data-stu-id="319a6-176">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
