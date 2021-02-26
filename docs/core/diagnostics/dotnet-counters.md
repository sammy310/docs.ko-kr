---
title: dotnet-counters 진단 도구 - .NET CLI
description: 임시 상태 모니터링 및 1단계 수준 성능을 위해 dotnet-counter CLI 도구를 설치하고 사용하는 방법을 알아봅니다.
ms.date: 11/17/2020
ms.openlocfilehash: 1c802e33602c2d8f18600b9771a1f68e722d8fdf
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "100583302"
---
# <a name="investigate-performance-counters-dotnet-counters"></a><span data-ttu-id="08f57-103">성능 카운터 조사(dotnet-counters)</span><span class="sxs-lookup"><span data-stu-id="08f57-103">Investigate performance counters (dotnet-counters)</span></span>

<span data-ttu-id="08f57-104">**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="08f57-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="08f57-105">설치</span><span class="sxs-lookup"><span data-stu-id="08f57-105">Install</span></span>

<span data-ttu-id="08f57-106">다음 두 가지 방법으로 `dotnet-counters`를 다운로드하고 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-106">There are two ways to download and install `dotnet-counters`:</span></span>

- <span data-ttu-id="08f57-107">**dotnet 전역 도구:**</span><span class="sxs-lookup"><span data-stu-id="08f57-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="08f57-108">`dotnet-counters` [NuGet 패키지](https://www.nuget.org/packages/dotnet-counters)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-108">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-counters
  ```

- <span data-ttu-id="08f57-109">**직접 다운로드:**</span><span class="sxs-lookup"><span data-stu-id="08f57-109">**Direct download:**</span></span>

  <span data-ttu-id="08f57-110">플랫폼에 맞는 도구 실행 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="08f57-111">OS</span><span class="sxs-lookup"><span data-stu-id="08f57-111">OS</span></span>  | <span data-ttu-id="08f57-112">플랫폼</span><span class="sxs-lookup"><span data-stu-id="08f57-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="08f57-113">Windows</span><span class="sxs-lookup"><span data-stu-id="08f57-113">Windows</span></span> | <span data-ttu-id="08f57-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="08f57-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span></span> |
  | <span data-ttu-id="08f57-115">macOS</span><span class="sxs-lookup"><span data-stu-id="08f57-115">macOS</span></span>   | [<span data-ttu-id="08f57-116">x64</span><span class="sxs-lookup"><span data-stu-id="08f57-116">x64</span></span>](https://aka.ms/dotnet-counters/osx-x64) |
  | <span data-ttu-id="08f57-117">Linux</span><span class="sxs-lookup"><span data-stu-id="08f57-117">Linux</span></span>   | <span data-ttu-id="08f57-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="08f57-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span></span> |

> [!NOTE]
> <span data-ttu-id="08f57-119">x86 앱에서 `dotnet-counters`를 사용하려면 해당하는 x86 버전의 도구가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-119">To use `dotnet-counters` on an x86 app, you need a corresponding x86 version of the tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="08f57-120">개요</span><span class="sxs-lookup"><span data-stu-id="08f57-120">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="08f57-121">설명</span><span class="sxs-lookup"><span data-stu-id="08f57-121">Description</span></span>

<span data-ttu-id="08f57-122">`dotnet-counters`는 임시 상태 모니터링 및 1단계 수준 성능 조사를 위한 성능 모니터링 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-122">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="08f57-123"><xref:System.Diagnostics.Tracing.EventCounter> API를 통해 게시된 성능 카운터 값을 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-123">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="08f57-124">예를 들어, `PerfView` 또는 `dotnet-trace`를 사용하여 보다 심각한 성능 조사를 살펴보기 전에 의심스러운 내용이 있는지 확인하기 위해 .NET Core 애플리케이션에서 throw되는 CPU 사용량 또는 예외 비율과 같은 항목을 신속하게 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-124">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="08f57-125">옵션</span><span class="sxs-lookup"><span data-stu-id="08f57-125">Options</span></span>

- **`--version`**

  <span data-ttu-id="08f57-126">dotnet-counters 유틸리티의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-126">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="08f57-127">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-127">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="08f57-128">명령</span><span class="sxs-lookup"><span data-stu-id="08f57-128">Commands</span></span>

| <span data-ttu-id="08f57-129">명령</span><span class="sxs-lookup"><span data-stu-id="08f57-129">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="08f57-130">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="08f57-130">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="08f57-131">dotnet-counters 목록</span><span class="sxs-lookup"><span data-stu-id="08f57-131">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="08f57-132">dotnet-counters 모니터</span><span class="sxs-lookup"><span data-stu-id="08f57-132">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="08f57-133">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="08f57-133">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="08f57-134">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="08f57-134">dotnet-counters collect</span></span>

<span data-ttu-id="08f57-135">선택한 카운터 값을 주기적으로 수집하고 후처리를 위해 지정된 파일 형식으로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-135">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="08f57-136">개요</span><span class="sxs-lookup"><span data-stu-id="08f57-136">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="08f57-137">옵션</span><span class="sxs-lookup"><span data-stu-id="08f57-137">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="08f57-138">카운터 데이터를 수집할 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-138">The ID of the process to be collect counter data from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="08f57-139">카운터 데이터를 수집할 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-139">The name of the process to be collect counter data from.</span></span>

- **`--diagnostic-port`**

  <span data-ttu-id="08f57-140">만들 진단 포트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-140">The name of the diagnostic port to create.</span></span> <span data-ttu-id="08f57-141">이 옵션을 사용하여 앱 시작부터 카운터 모니터링을 시작하는 방법은 [진단 포트 사용](#using-diagnostic-port)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08f57-141">See [using diagnostic port](#using-diagnostic-port) for how to use this option to start monitoring counters from app startup.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="08f57-142">표시된 카운터 업데이트 사이의 지연 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-142">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="08f57-143">쉼표로 구분된 카운터 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-143">A comma-separated list of counters.</span></span> <span data-ttu-id="08f57-144">카운터는 `provider_name[:counter_name]`을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-144">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="08f57-145">적격 카운터 목록 없이 `provider_name`이 사용되는 경우 공급자의 모든 카운터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-145">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="08f57-146">공급자 및 카운터 이름을 검색하려면 [dotnet-counters 목록](#dotnet-counters-list) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-146">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="08f57-147">내보낼 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-147">The format to be exported.</span></span> <span data-ttu-id="08f57-148">현재 csv와 json을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-148">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="08f57-149">출력 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-149">The name of the output file.</span></span>

- <span data-ttu-id="08f57-150">**`-- <command>`(.NET 5.0 이상을 실행하는 대상 애플리케이션만 해당)**</span><span class="sxs-lookup"><span data-stu-id="08f57-150">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="08f57-151">사용자는 컬렉션 구성 매개 변수 다음에 `--`와 명령을 차례로 추가하여 5.0 런타임 이상에서 .NET 애플리케이션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-151">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="08f57-152">`dotnet-counters`는 제공된 명령을 사용하여 프로세스를 시작하고 요청된 메트릭을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-152">`dotnet-counters` will launch a process with the provided command and collect the requested metrics.</span></span> <span data-ttu-id="08f57-153">이 옵션은 애플리케이션의 시작 경로에 대한 메트릭을 수집하는 데 유용하며, 주요 진입점 이전이나 바로 다음에 발생하는 문제를 진단하거나 모니터링하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-153">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="08f57-154">이 옵션을 사용하면 도구에 다시 전달되는 첫 번째 .NET 5.0 프로세스가 모니터링됩니다. 즉, 명령에서 여러 .NET 애플리케이션을 시작하는 경우 첫 번째 앱만 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-154">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="08f57-155">따라서 자체 포함 애플리케이션에서 이 옵션을 사용하거나 `dotnet exec <app.dll>` 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-155">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

  > [!NOTE]
  > <span data-ttu-id="08f57-156">dotnet-counters를 통해 .NET 실행 파일을 시작하면 해당 입출력이 리디렉션되어 stdin/stdout과 상호 작용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-156">Launching a .NET executable via dotnet-counters will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span> <span data-ttu-id="08f57-157">Ctrl+C 또는 SIGTERM을 통해 도구를 종료하면 도구와 자식 프로세스가 모두 안전하게 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-157">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span> <span data-ttu-id="08f57-158">자식 프로세스가 도구보다 먼저 종료되면 도구도 종료되고 추적을 안전하게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-158">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span> <span data-ttu-id="08f57-159">Stdin/stdout을 사용해야 하는 경우 `--diagnostic-port` 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-159">If you need to use stdin/stdout, you can use the `--diagnostic-port` option.</span></span> <span data-ttu-id="08f57-160">자세한 내용은 [진단 포트 사용](#using-diagnostic-port)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08f57-160">See [Using diagnostic port](#using-diagnostic-port) for more information.</span></span>

> [!NOTE]
> <span data-ttu-id="08f57-161">Linux 및 macOS에서 해당 명령은 대상 애플리케이션 및 `dotnet-counters`가 동일한 `TMPDIR` 환경 변수를 공유할 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-161">On Linux and macOS, this command expects the target application and `dotnet-counters` to share the same `TMPDIR` environment variable.</span></span> <span data-ttu-id="08f57-162">그러지 않으면 명령 시간이 초과됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-162">Otherwise, the command will time out.</span></span>

> [!NOTE]
> <span data-ttu-id="08f57-163">`dotnet-counters`를 사용하여 메트릭을 수집하려면 대상 프로세스를 실행하는 사용자와 동일한 사용자 또는 루트로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-163">To collect metrics using `dotnet-counters`, it needs to be run as the same user as the user running target process or as root.</span></span> <span data-ttu-id="08f57-164">그러지 않으면 도구는 대상 프로세스와 연결을 설정하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-164">Otherwise, the tool will fail to establish a connection with the target process.</span></span>

### <a name="examples"></a><span data-ttu-id="08f57-165">예</span><span class="sxs-lookup"><span data-stu-id="08f57-165">Examples</span></span>

- <span data-ttu-id="08f57-166">3초의 새로 고침 간격으로 모든 카운터를 수집하고 csv를 출력으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-166">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- <span data-ttu-id="08f57-167">`dotnet mvc.dll`을 자식 프로세스로 시작하고 시작에서 런타임 카운터 및 ASP.NET Core 호스팅 카운터 수집을 시작하여 JSON 출력으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-167">Start `dotnet mvc.dll` as a child process and start collecting runtime counters and ASP.NET Core Hosting counters from startup and save it as a JSON output:</span></span>

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="08f57-168">dotnet-counters 목록</span><span class="sxs-lookup"><span data-stu-id="08f57-168">dotnet-counters list</span></span>

<span data-ttu-id="08f57-169">공급자별로 그룹화된 카운터 이름 및 설명 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-169">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="08f57-170">개요</span><span class="sxs-lookup"><span data-stu-id="08f57-170">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="08f57-171">예제</span><span class="sxs-lookup"><span data-stu-id="08f57-171">Example</span></span>

```console
> dotnet-counters list
Showing well-known counters only. Specific processes may support additional counters.

System.Runtime
    cpu-usage                                    Amount of time the process has utilized the CPU (ms)
    working-set                                  Amount of working set used by the process (MB)
    gc-heap-size                                 Total heap size reported by the GC (MB)
    gen-0-gc-count                               Number of Gen 0 GCs per interval
    gen-1-gc-count                               Number of Gen 1 GCs per interval
    gen-2-gc-count                               Number of Gen 2 GCs per interval
    time-in-gc                                   % time in GC since the last GC
    gen-0-size                                   Gen 0 Heap Size
    gen-1-size                                   Gen 1 Heap Size
    gen-2-size                                   Gen 2 Heap Size
    loh-size                                     LOH Heap Size
    alloc-rate                                   Allocation Rate
    assembly-count                               Number of Assemblies Loaded
    exception-count                              Number of Exceptions per interval
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
> <span data-ttu-id="08f57-172">이러한 카운터를 지원하는 프로세스를 식별한 경우, 예를 들어 호스트 머신에서 ASP.NET Core 애플리케이션이 실행되고 있는 경우 `Microsoft.AspNetCore.Hosting` 카운터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-172">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="08f57-173">dotnet-counters 모니터</span><span class="sxs-lookup"><span data-stu-id="08f57-173">dotnet-counters monitor</span></span>

<span data-ttu-id="08f57-174">선택한 카운터의 값을 주기적으로 새로 고치는 방법을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-174">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="08f57-175">개요</span><span class="sxs-lookup"><span data-stu-id="08f57-175">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="08f57-176">옵션</span><span class="sxs-lookup"><span data-stu-id="08f57-176">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="08f57-177">모니터링할 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-177">The ID of the process to be monitored.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="08f57-178">모니터링할 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-178">The name of the process to be monitored.</span></span>

- **`--diagnostic-port`**

  <span data-ttu-id="08f57-179">만들 진단 포트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-179">The name of the diagnostic port to create.</span></span> <span data-ttu-id="08f57-180">이 옵션을 사용하여 앱 시작부터 카운터 모니터링을 시작하는 방법은 [진단 포트 사용](#using-diagnostic-port)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08f57-180">See [using diagnostic port](#using-diagnostic-port) for how to use this option to start monitoring counters from app startup.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="08f57-181">표시된 카운터 업데이트 사이의 지연 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-181">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="08f57-182">쉼표로 구분된 카운터 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-182">A comma-separated list of counters.</span></span> <span data-ttu-id="08f57-183">카운터는 `provider_name[:counter_name]`을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-183">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="08f57-184">적격 카운터 목록 없이 `provider_name`이 사용되는 경우 공급자의 모든 카운터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-184">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="08f57-185">공급자 및 카운터 이름을 검색하려면 [dotnet-counters 목록](#dotnet-counters-list) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-185">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

 <span data-ttu-id="08f57-186">**`-- <command>`(.NET 5.0 이상을 실행하는 대상 애플리케이션만 해당)**</span><span class="sxs-lookup"><span data-stu-id="08f57-186">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="08f57-187">사용자는 컬렉션 구성 매개 변수 다음에 `--`와 명령을 차례로 추가하여 5.0 런타임 이상에서 .NET 애플리케이션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-187">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="08f57-188">`dotnet-counters`는 제공된 명령을 사용하여 프로세스를 시작하고 요청된 메트릭을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-188">`dotnet-counters` will launch a process with the provided command and monitor the requested metrics.</span></span> <span data-ttu-id="08f57-189">이 옵션은 애플리케이션의 시작 경로에 대한 메트릭을 수집하는 데 유용하며, 주요 진입점 이전이나 바로 다음에 발생하는 문제를 진단하거나 모니터링하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-189">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="08f57-190">이 옵션을 사용하면 도구에 다시 전달되는 첫 번째 .NET 5.0 프로세스가 모니터링됩니다. 즉, 명령에서 여러 .NET 애플리케이션을 시작하는 경우 첫 번째 앱만 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-190">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="08f57-191">따라서 자체 포함 애플리케이션에서 이 옵션을 사용하거나 `dotnet exec <app.dll>` 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-191">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

  > [!NOTE]
  > <span data-ttu-id="08f57-192">dotnet-counters를 통해 .NET 실행 파일을 시작하면 해당 입출력이 리디렉션되어 stdin/stdout과 상호 작용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-192">Launching a .NET executable via dotnet-counters will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span> <span data-ttu-id="08f57-193">Ctrl+C 또는 SIGTERM을 통해 도구를 종료하면 도구와 자식 프로세스가 모두 안전하게 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-193">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span> <span data-ttu-id="08f57-194">자식 프로세스가 도구보다 먼저 종료되면 도구도 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-194">If the child process exits before the tool, the tool will exit as well.</span></span> <span data-ttu-id="08f57-195">Stdin/stdout을 사용해야 하는 경우 `--diagnostic-port` 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-195">If you need to use stdin/stdout, you can use the `--diagnostic-port` option.</span></span> <span data-ttu-id="08f57-196">자세한 내용은 [진단 포트 사용](#using-diagnostic-port)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08f57-196">See [Using diagnostic port](#using-diagnostic-port) for more information.</span></span>

> [!NOTE]
> <span data-ttu-id="08f57-197">Linux 및 macOS에서 해당 명령은 대상 애플리케이션 및 `dotnet-counters`가 동일한 `TMPDIR` 환경 변수를 공유할 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-197">On Linux and macOS, this command expects the target application and `dotnet-counters` to share the same `TMPDIR` environment variable.</span></span>

> [!NOTE]
> <span data-ttu-id="08f57-198">`dotnet-counters`를 사용하여 메트릭을 모니터링하려면 대상 프로세스를 실행하는 사용자와 동일한 사용자 또는 루트로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-198">To monitor metrics using `dotnet-counters`, it needs to be run as the same user as the user running target process or as root.</span></span>

> [!NOTE]
> <span data-ttu-id="08f57-199">`[ERROR] System.ComponentModel.Win32Exception (299): A 32 bit processes cannot access modules of a 64 bit process.`와 유사한 오류 메시지가 표시되는 경우, 대상 프로세스와 비트 수가 일치하지 않는 `dotnet-counters`를 사용하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-199">If you see an error message similar to the following one: `[ERROR] System.ComponentModel.Win32Exception (299): A 32 bit processes cannot access modules of a 64 bit process.`, you are trying to use `dotnet-counters` that has mismatched bitness against the target process.</span></span> <span data-ttu-id="08f57-200">[설치](#install) 링크에서 도구의 올바른 비트 수를 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-200">Make sure to download the correct bitness of the tool in the [install](#install) link.</span></span>

### <a name="examples"></a><span data-ttu-id="08f57-201">예</span><span class="sxs-lookup"><span data-stu-id="08f57-201">Examples</span></span>

- <span data-ttu-id="08f57-202">3초의 새로 고침 간격으로 `System.Runtime`의 모든 카운터를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-202">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

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

- <span data-ttu-id="08f57-203">`System.Runtime`에서 CPU 사용량 및 GC 힙 크기만 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-203">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="08f57-204">사용자 정의 `EventSource`에서 `EventCounter` 값을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-204">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="08f57-205">자세한 내용은 [자습서: .NET Core에서 EventCounters를 사용하여 성능 측정](event-counter-perf.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08f57-205">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- <span data-ttu-id="08f57-206">`dotnet-counters`에서 사용할 수 있는 잘 알려진 카운터를 모두 봅니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-206">View all well-known counters that are available in `dotnet-counters`:</span></span>

  ```console
  > dotnet-counters list

  Showing well-known counters for .NET (Core) version 3.1 only. Specific processes may support additional counters.
  System.Runtime
      cpu-usage                          The percent of process' CPU usage relative to all of the system CPU resources [0-100]
      working-set                        Amount of working set used by the process (MB)
      gc-heap-size                       Total heap size reported by the GC (MB)
      gen-0-gc-count                     Number of Gen 0 GCs between update intervals
      gen-1-gc-count                     Number of Gen 1 GCs between update intervals
      gen-2-gc-count                     Number of Gen 2 GCs between update intervals
      time-in-gc                         % time in GC since the last GC
      gen-0-size                         Gen 0 Heap Size
      gen-1-size                         Gen 1 Heap Size
      gen-2-size                         Gen 2 Heap Size
      loh-size                           LOH Size
      alloc-rate                         Number of bytes allocated in the managed heap between update intervals
      assembly-count                     Number of Assemblies Loaded
      exception-count                    Number of Exceptions / sec
      threadpool-thread-count            Number of ThreadPool Threads
      monitor-lock-contention-count      Number of times there were contention when trying to take the monitor lock between update intervals
      threadpool-queue-length            ThreadPool Work Items Queue Length
      threadpool-completed-items-count   ThreadPool Completed Work Items Count
      active-timer-count                 Number of timers that are currently active

  Microsoft.AspNetCore.Hosting
      requests-per-second                Number of requests between update intervals
      total-requests                     Total number of requests
      current-requests                   Current number of requests
      failed-requests                    Failed number of requests
  ```

- <span data-ttu-id="08f57-207">.NET 5 앱용 `dotnet-counters` 에서 사용할 수 있는 잘 알려진 카운터를 모두 봅니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-207">View all well-known counters that are available in `dotnet-counters` for .NET 5 apps:</span></span>

  ```console
  > dotnet-counters list --runtime-version 5.0

  Showing well-known counters for .NET (Core) version 5.0 only. Specific processes may support additional counters.
  System.Runtime
      cpu-usage                          The percent of process' CPU usage relative to all of the system CPU resources [0-100]
      working-set                        Amount of working set used by the process (MB)
      gc-heap-size                       Total heap size reported by the GC (MB)
      gen-0-gc-count                     Number of Gen 0 GCs between update intervals
      gen-1-gc-count                     Number of Gen 1 GCs between update intervals
      gen-2-gc-count                     Number of Gen 2 GCs between update intervals
      time-in-gc                         % time in GC since the last GC
      gen-0-size                         Gen 0 Heap Size
      gen-1-size                         Gen 1 Heap Size
      gen-2-size                         Gen 2 Heap Size
      loh-size                           LOH Size
      poh-size                           POH (Pinned Object Heap) Size
      alloc-rate                         Number of bytes allocated in the managed heap between update intervals
      gc-fragmentation                   GC Heap Fragmentation
      assembly-count                     Number of Assemblies Loaded
      exception-count                    Number of Exceptions / sec
      threadpool-thread-count            Number of ThreadPool Threads
      monitor-lock-contention-count      Number of times there were contention when trying to take the monitor lock between update intervals
      threadpool-queue-length            ThreadPool Work Items Queue Length
      threadpool-completed-items-count   ThreadPool Completed Work Items Count
      active-timer-count                 Number of timers that are currently active
      il-bytes-jitted                    Total IL bytes jitted
      methods-jitted-count               Number of methods jitted

  Microsoft.AspNetCore.Hosting
      requests-per-second   Number of requests between update intervals
      total-requests        Total number of requests
      current-requests      Current number of requests
      failed-requests       Failed number of requests

  Microsoft-AspNetCore-Server-Kestrel
      connections-per-second      Number of connections between update intervals
      total-connections           Total Connections
      tls-handshakes-per-second   Number of TLS Handshakes made between update intervals
      total-tls-handshakes        Total number of TLS handshakes made
      current-tls-handshakes      Number of currently active TLS handshakes
      failed-tls-handshakes       Total number of failed TLS handshakes
      current-connections         Number of current connections
      connection-queue-length     Length of Kestrel Connection Queue
      request-queue-length        Length total HTTP request queue

  System.Net.Http
      requests-started        Total Requests Started
      requests-started-rate   Number of Requests Started between update intervals
      requests-aborted        Total Requests Aborted
      requests-aborted-rate   Number of Requests Aborted between update intervals
      current-requests        Current Requests
  ```

- <span data-ttu-id="08f57-208">`my-aspnet-server.exe`를 시작하고 시작에서 로드된 어셈블리 수를 모니터링합니다(.NET 5.0 이상만 해당).</span><span class="sxs-lookup"><span data-stu-id="08f57-208">Launch `my-aspnet-server.exe` and monitor the # of assemblies loaded from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="08f57-209">.NET 5.0 이상을 실행하는 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-209">This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- <span data-ttu-id="08f57-210">`arg1` 및 `arg2`를 명령줄 인수로 사용하여 `my-aspnet-server.exe`를 시작하고 시작에서 작업 집합 및 GC 힙 크기를 모니터링합니다(.NET 5.0 이상만 해당).</span><span class="sxs-lookup"><span data-stu-id="08f57-210">Launch `my-aspnet-server.exe` with `arg1` and `arg2` as command-line arguments and monitor its working set and GC heap size from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="08f57-211">.NET 5.0 이상을 실행하는 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-211">This works for apps running .NET 5.0 or later only.</span></span>

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

## <a name="dotnet-counters-ps"></a><span data-ttu-id="08f57-212">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="08f57-212">dotnet-counters ps</span></span>

<span data-ttu-id="08f57-213">모니터링할 수 있는 dotnet 프로세스의 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-213">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="08f57-214">개요</span><span class="sxs-lookup"><span data-stu-id="08f57-214">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="08f57-215">예제</span><span class="sxs-lookup"><span data-stu-id="08f57-215">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/user/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```

## <a name="using-diagnostic-port"></a><span data-ttu-id="08f57-216">진단 포트 사용</span><span class="sxs-lookup"><span data-stu-id="08f57-216">Using diagnostic port</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="08f57-217">.NET 5.0 이상을 실행하는 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-217">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="08f57-218">진단 포트는 .NET 5에서 추가된 새로운 런타임 기능으로, 앱 시작부터 카운터 모니터링과 수집을 시작하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-218">Diagnostic port is a new runtime feature that was added in .NET 5 that allows you to start monitoring or collecting counters from app startup.</span></span> <span data-ttu-id="08f57-219">`dotnet-counters`를 사용하여 이렇게 하려면 위의 예제에 설명된 대로 `dotnet-counters <collect|monitor> -- <command>`를 사용하거나 `--diagnostic-port` 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-219">To do this using `dotnet-counters`, you can either use `dotnet-counters <collect|monitor> -- <command>` as described in the examples above, or use the `--diagnostic-port` option.</span></span>

<span data-ttu-id="08f57-220">`dotnet-counters <collect|monitor> -- <command>`를 사용하여 애플리케이션을 자식 프로세스로 실행하는 것이 시작부터 빠르게 모니터링하는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-220">Using `dotnet-counters <collect|monitor> -- <command>` to launch the application as a child process is the simplest way to quickly monitor it from its startup.</span></span>

<span data-ttu-id="08f57-221">하지만 모니터링되는 앱의 수명을 더 세부적으로 제어하거나(예: 처음 10분간만 앱을 모니터링하고 실행 계속) CLI를 사용하여 앱을 조작해야 하는 경우에는 `--diagnostic-port` 옵션을 사용하여 모니터링되는 대상 앱과 `dotnet-counters`를 모두 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-221">However, when you want to gain a finer control over the lifetime of the app being monitored (for example, monitor the app for the first 10 minutes only and continue executing) or if you need to interact with the app using the CLI, using `--diagnostic-port` option allows you to control both the target app being monitored and `dotnet-counters`.</span></span>

1. <span data-ttu-id="08f57-222">아래 명령은 dotnet-counters에서 `myport.sock`라는 진단 소켓을 만들고 연결을 대기하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-222">The command below makes dotnet-counters create a diagnostics socket named `myport.sock` and wait for a connection.</span></span>

    > ```dotnet-cli
    > dotnet-counters collect --diagnostic-port myport.sock
    > ```

    <span data-ttu-id="08f57-223">출력:</span><span class="sxs-lookup"><span data-stu-id="08f57-223">Output:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. <span data-ttu-id="08f57-224">별도의 콘솔에서 `DOTNET_DiagnosticPorts` 환경 변수를 `dotnet-counters` 출력의 값으로 설정하고 대상 애플리케이션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-224">In a separate console, launch the target application with the environment variable `DOTNET_DiagnosticPorts` set to the value in the `dotnet-counters` output.</span></span>

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    <span data-ttu-id="08f57-225">그러면 `dotnet-counters`가 `my-dotnet-app`에서 카운터 수집을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-225">This should then enable `dotnet-counters` to start collecting counters on `my-dotnet-app`:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > <span data-ttu-id="08f57-226">`dotnet run`을 사용하여 앱을 시작하면 문제가 될 수 있는데, dotnet CLI가 앱이 아닌 여러 자식 프로세스를 생성할 수 있고 해당 프로세스가 앱보다 먼저 `dotnet-counters`에 연결하여 앱이 런타임에 일시 중단될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-226">Launching your app with `dotnet run` can be problematic because the dotnet CLI may spawn many child processes that are not your app and they can connect to `dotnet-counters` before your app, leaving your app to be suspended at runtime.</span></span> <span data-ttu-id="08f57-227">앱의 자체 포함 버전을 직접 사용하거나 `dotnet exec`를 사용하여 애플리케이션을 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="08f57-227">It is recommended you directly use a self-contained version of the app or use `dotnet exec` to launch the application.</span></span>
