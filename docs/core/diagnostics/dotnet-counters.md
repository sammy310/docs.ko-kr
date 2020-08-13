---
title: dotnet-counters - .NET Core
description: dotnet-counter 명령줄 도구를 설치하고 사용하는 방법에 대해 알아봅니다.
ms.date: 02/26/2020
ms.openlocfilehash: 71e3c4f0a60960c4e672b95000bc0d67bd427514
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024630"
---
# <a name="dotnet-counters"></a><span data-ttu-id="cba8d-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="cba8d-103">dotnet-counters</span></span>

<span data-ttu-id="cba8d-104">**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="cba8d-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="cba8d-105">dotnet-counters 설치</span><span class="sxs-lookup"><span data-stu-id="cba8d-105">Install dotnet-counters</span></span>

<span data-ttu-id="cba8d-106">`dotnet-counters` [NuGet 패키지](https://www.nuget.org/packages/dotnet-counters)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="cba8d-107">개요</span><span class="sxs-lookup"><span data-stu-id="cba8d-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="cba8d-108">설명</span><span class="sxs-lookup"><span data-stu-id="cba8d-108">Description</span></span>

<span data-ttu-id="cba8d-109">`dotnet-counters`는 임시 상태 모니터링 및 1단계 수준 성능 조사를 위한 성능 모니터링 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="cba8d-110"><xref:System.Diagnostics.Tracing.EventCounter> API를 통해 게시된 성능 카운터 값을 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="cba8d-111">예를 들어, `PerfView` 또는 `dotnet-trace`를 사용하여 보다 심각한 성능 조사를 살펴보기 전에 의심스러운 내용이 있는지 확인하기 위해 .NET Core 애플리케이션에서 throw되는 CPU 사용량 또는 예외 비율과 같은 항목을 신속하게 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="cba8d-112">옵션</span><span class="sxs-lookup"><span data-stu-id="cba8d-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="cba8d-113">dotnet-counters 유틸리티의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="cba8d-114">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="cba8d-115">명령</span><span class="sxs-lookup"><span data-stu-id="cba8d-115">Commands</span></span>

| <span data-ttu-id="cba8d-116">명령</span><span class="sxs-lookup"><span data-stu-id="cba8d-116">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="cba8d-117">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="cba8d-117">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="cba8d-118">dotnet-counters 목록</span><span class="sxs-lookup"><span data-stu-id="cba8d-118">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="cba8d-119">dotnet-counters 모니터</span><span class="sxs-lookup"><span data-stu-id="cba8d-119">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="cba8d-120">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="cba8d-120">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="cba8d-121">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="cba8d-121">dotnet-counters collect</span></span>

<span data-ttu-id="cba8d-122">선택한 카운터 값을 주기적으로 수집하고 후처리를 위해 지정된 파일 형식으로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-122">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="cba8d-123">개요</span><span class="sxs-lookup"><span data-stu-id="cba8d-123">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a><span data-ttu-id="cba8d-124">옵션</span><span class="sxs-lookup"><span data-stu-id="cba8d-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="cba8d-125">모니터링할 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-125">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="cba8d-126">표시된 카운터 업데이트 사이의 지연 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-126">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="cba8d-127">공백으로 구분된 카운터의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-127">A space separated list of counters.</span></span> <span data-ttu-id="cba8d-128">카운터는 `provider_name[:counter_name]`을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-128">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="cba8d-129">한정된 `counter_name` 없이 `provider_name`을 사용하면 모든 카운터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-129">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="cba8d-130">공급자 및 카운터 이름을 검색하려면 [dotnet-counters 목록](#dotnet-counters-list) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-130">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="cba8d-131">내보낼 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-131">TThe format to be exported.</span></span> <span data-ttu-id="cba8d-132">현재 csv와 json을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-132">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="cba8d-133">출력 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-133">The name of the output file.</span></span>

### <a name="examples"></a><span data-ttu-id="cba8d-134">예</span><span class="sxs-lookup"><span data-stu-id="cba8d-134">Examples</span></span>

- <span data-ttu-id="cba8d-135">3초의 새로 고침 간격으로 모든 카운터를 수집하고 csv를 출력으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-135">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="cba8d-136">dotnet-counters 목록</span><span class="sxs-lookup"><span data-stu-id="cba8d-136">dotnet-counters list</span></span>

<span data-ttu-id="cba8d-137">공급자별로 그룹화된 카운터 이름 및 설명 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-137">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="cba8d-138">개요</span><span class="sxs-lookup"><span data-stu-id="cba8d-138">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="cba8d-139">예제</span><span class="sxs-lookup"><span data-stu-id="cba8d-139">Example</span></span>

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
> <span data-ttu-id="cba8d-140">이러한 카운터를 지원하는 프로세스를 식별한 경우, 예를 들어 호스트 머신에서 ASP.NET Core 애플리케이션이 실행되고 있는 경우 `Microsoft.AspNetCore.Hosting` 카운터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-140">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="cba8d-141">dotnet-counters 모니터</span><span class="sxs-lookup"><span data-stu-id="cba8d-141">dotnet-counters monitor</span></span>

<span data-ttu-id="cba8d-142">선택한 카운터의 값을 주기적으로 새로 고치는 방법을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-142">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="cba8d-143">개요</span><span class="sxs-lookup"><span data-stu-id="cba8d-143">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="cba8d-144">옵션</span><span class="sxs-lookup"><span data-stu-id="cba8d-144">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="cba8d-145">모니터링할 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-145">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="cba8d-146">표시된 카운터 업데이트 사이의 지연 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-146">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="cba8d-147">공백으로 구분된 카운터의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-147">A space separated list of counters.</span></span> <span data-ttu-id="cba8d-148">카운터는 `provider_name[:counter_name]`을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-148">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="cba8d-149">한정된 `counter_name` 없이 `provider_name`을 사용하면 모든 카운터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-149">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="cba8d-150">공급자 및 카운터 이름을 검색하려면 [dotnet-counters 목록](#dotnet-counters-list) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-150">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="cba8d-151">예</span><span class="sxs-lookup"><span data-stu-id="cba8d-151">Examples</span></span>

- <span data-ttu-id="cba8d-152">3초의 새로 고침 간격으로 `System.Runtime`의 모든 카운터를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-152">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- <span data-ttu-id="cba8d-153">`System.Runtime`에서 CPU 사용량 및 GC 힙 크기만 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-153">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="cba8d-154">사용자 정의 `EventSource`에서 `EventCounter` 값을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-154">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="cba8d-155">자세한 내용은 [자습서: .NET Core에서 EventCounters를 사용하여 성능 측정](event-counter-perf.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cba8d-155">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
  
## <a name="dotnet-counters-ps"></a><span data-ttu-id="cba8d-156">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="cba8d-156">dotnet-counters ps</span></span>

<span data-ttu-id="cba8d-157">모니터링할 수 있는 dotnet 프로세스의 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cba8d-157">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="cba8d-158">개요</span><span class="sxs-lookup"><span data-stu-id="cba8d-158">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="cba8d-159">예제</span><span class="sxs-lookup"><span data-stu-id="cba8d-159">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
