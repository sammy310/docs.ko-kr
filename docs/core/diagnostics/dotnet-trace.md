---
title: dotnet-trace - .NET Core
description: dotnet-trace 명령줄 도구를 설치하고 사용합니다.
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.openlocfilehash: 6513cf63070bc1984006da75313e9912d76a6c95
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321533"
---
# <a name="trace-for-performance-analysis-utility-dotnet-trace"></a><span data-ttu-id="61faf-103">성능 분석 추적 유틸리티(`dotnet-trace`)</span><span class="sxs-lookup"><span data-stu-id="61faf-103">Trace for performance analysis utility (`dotnet-trace`)</span></span>

<span data-ttu-id="61faf-104">**이 문서의 적용 대상:** .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="61faf-104">**This article applies to:** .NET Core 3.0 SDK and later versions</span></span>

## <a name="installing-dotnet-trace"></a><span data-ttu-id="61faf-105">`dotnet-trace` 설치</span><span class="sxs-lookup"><span data-stu-id="61faf-105">Installing `dotnet-trace`</span></span>

<span data-ttu-id="61faf-106">`dotnet-trace` [NuGet 패키지](https://www.nuget.org/packages/dotnet-trace)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-106">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="61faf-107">개요</span><span class="sxs-lookup"><span data-stu-id="61faf-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="61faf-108">설명</span><span class="sxs-lookup"><span data-stu-id="61faf-108">Description</span></span>

<span data-ttu-id="61faf-109">`dotnet-trace` 도구는 네이티브 프로파일러 없이 실행 중인 프로세스의 .NET Core 추적을 수집할 수 있도록 지원하는 플랫폼 간 CLI 글로벌 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-109">The `dotnet-trace` tool is a cross-platform CLI global tool that enables the collection of .NET Core traces of a running process without any native profiler involved.</span></span> <span data-ttu-id="61faf-110">.NET Core 런타임의 플랫폼 간 `EventPipe` 기술을 기반으로 하여 빌드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-110">It's built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span> <span data-ttu-id="61faf-111">`dotnet-trace`는 Windows, Linux 또는 macOS에서 동일한 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-111">`dotnet-trace` delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="61faf-112">옵션</span><span class="sxs-lookup"><span data-stu-id="61faf-112">Options</span></span>

- **`--version`**

<span data-ttu-id="61faf-113">dotnet-counters 유틸리티의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-113">Display the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

<span data-ttu-id="61faf-114">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-114">Show command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="61faf-115">명령</span><span class="sxs-lookup"><span data-stu-id="61faf-115">Commands</span></span>

| <span data-ttu-id="61faf-116">명령</span><span class="sxs-lookup"><span data-stu-id="61faf-116">Command</span></span>                                                     |
| ----------------------------------------------------------- |
| [<span data-ttu-id="61faf-117">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="61faf-117">dotnet-trace collect</span></span>](#dotnet-trace-collect)               |
| [<span data-ttu-id="61faf-118">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="61faf-118">dotnet-trace convert</span></span>](#dotnet-trace-convert)               |
| [<span data-ttu-id="61faf-119">dotnet-trace list-processes</span><span class="sxs-lookup"><span data-stu-id="61faf-119">dotnet-trace list-processes</span></span>](#dotnet-trace-list-processes) |
| [<span data-ttu-id="61faf-120">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="61faf-120">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="61faf-121">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="61faf-121">dotnet-trace collect</span></span>

<span data-ttu-id="61faf-122">실행 중인 프로세스에서 진단 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-122">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="61faf-123">개요</span><span class="sxs-lookup"><span data-stu-id="61faf-123">Synopsis</span></span>

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a><span data-ttu-id="61faf-124">옵션</span><span class="sxs-lookup"><span data-stu-id="61faf-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="61faf-125">추적을 수집하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-125">The process to collect the trace from.</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="61faf-126">메모리 내 순환 버퍼의 크기를 MB(메가바이트) 단위로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-126">Sets the size of the in-memory circular buffer in megabytes.</span></span> <span data-ttu-id="61faf-127">기본값은 256MB입니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-127">Default 256 MB.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="61faf-128">수집된 추적 데이터의 출력 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-128">The output path for the collected trace data.</span></span> <span data-ttu-id="61faf-129">지정하지 않으면 기본값인 `trace.nettrace`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-129">If not specified it defaults to `trace.nettrace`.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="61faf-130">사용하도록 설정할 `EventPipe` 공급자에 대한 쉼표로 구분된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-130">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="61faf-131">이러한 공급자는 `--profile <profile-name>`에서 암시하는 모든 공급자를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-131">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="61faf-132">특정 공급자에 대한 불일치 항목이 있는 경우 여기의 구성이 프로필의 암시적 구성보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-132">If there's any inconsistency for a particular provider, the configuration here takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="61faf-133">이 공급자 목록의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-133">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="61faf-134">`Provider`의 형식: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`</span><span class="sxs-lookup"><span data-stu-id="61faf-134">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="61faf-135">`KeyValueArgs`의 형식: `[key1=value1][;key2=value2]`</span><span class="sxs-lookup"><span data-stu-id="61faf-135">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="61faf-136">일반적인 추적 시나리오를 간략하게 지정할 수 있는 미리 정의되어 명명된 공급자 구성 세트입니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-136">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="61faf-137">추적 파일 변환에 대한 출력 형식을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-137">Sets the output format for the trace file conversion.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="61faf-138">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="61faf-138">dotnet-trace convert</span></span>

<span data-ttu-id="61faf-139">`nettrace` 추적을 대체 추적 분석 도구와 함께 사용할 대체 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-139">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="61faf-140">개요</span><span class="sxs-lookup"><span data-stu-id="61faf-140">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a><span data-ttu-id="61faf-141">인수</span><span class="sxs-lookup"><span data-stu-id="61faf-141">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="61faf-142">변환할 입력 추적 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-142">Input trace file to be converted.</span></span> <span data-ttu-id="61faf-143">기본값은 *trace.nettrace*입니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-143">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="61faf-144">옵션</span><span class="sxs-lookup"><span data-stu-id="61faf-144">Options</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="61faf-145">추적 파일 변환에 대한 출력 형식을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-145">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="61faf-146">출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-146">Output filename.</span></span> <span data-ttu-id="61faf-147">대상 형식의 확장명이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-147">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-list-processes"></a><span data-ttu-id="61faf-148">dotnet-trace list-processes</span><span class="sxs-lookup"><span data-stu-id="61faf-148">dotnet-trace list-processes</span></span>

<span data-ttu-id="61faf-149">추적할 수 있는 dotnet 프로세스를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-149">Lists dotnet processes that can be traced.</span></span>

### <a name="synopsis"></a><span data-ttu-id="61faf-150">개요</span><span class="sxs-lookup"><span data-stu-id="61faf-150">Synopsis</span></span>

```console
dotnet-trace list-processes [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="61faf-151">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="61faf-151">dotnet-trace list-profiles</span></span>

<span data-ttu-id="61faf-152">각 프로필에 있는 공급자 및 필터에 대한 설명이 포함된 미리 작성된 추적 프로필을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-152">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="61faf-153">개요</span><span class="sxs-lookup"><span data-stu-id="61faf-153">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="61faf-154">`dotnet-trace`를 사용하여 추적 수집</span><span class="sxs-lookup"><span data-stu-id="61faf-154">Collect a trace with `dotnet-trace`</span></span>

- <span data-ttu-id="61faf-155">`dotnet-trace`를 사용하여 추적을 수집하려면 먼저 추적을 수집할 .NET Core 애플리케이션의 PID(프로세스 식별자)를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-155">To collect traces using `dotnet-trace`, you'll need to first, find out the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="61faf-156">Windows에는 작업 관리자 또는 `tasklist` 명령을 사용하는 것과 같은 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-156">On Windows, there are options such as using the task manager or the `tasklist` command.</span></span>
  - <span data-ttu-id="61faf-157">Linux에는 `ps` 명령을 사용하는 간단한 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-157">On Linux, the trivial option could be using `ps` command.</span></span>

<span data-ttu-id="61faf-158">또한 [dotnet-trace list-processes](#dotnet-trace-list-processes) 명령을 사용하여 실행 중인 .NET Core 프로세스와 해당 PID를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-158">You may also use the [dotnet-trace list-processes](#dotnet-trace-list-processes) command to find out what .NET Core processes are running, along with their PIDs.</span></span>

- <span data-ttu-id="61faf-159">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-159">Then, run the following command:</span></span>

```console
> dotnet-trace collect --process-id <PID>

Press <Enter> to exit...
Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
```

- <span data-ttu-id="61faf-160">마지막으로 `<Enter>` 키를 눌러 수집을 중지합니다. 그러면 `dotnet-trace`에서 `trace.nettrace` 파일에 대한 이벤트 로깅을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-160">Finally, stop collection by pressing the `<Enter>` key, and `dotnet-trace` will finish logging events to `trace.nettrace` file.</span></span>

## <a name="viewing-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="61faf-161">`dotnet-trace`에서 캡처한 추적 보기</span><span class="sxs-lookup"><span data-stu-id="61faf-161">Viewing the trace captured from `dotnet-trace`</span></span>

<span data-ttu-id="61faf-162">Windows에서는 ETW 또는 LTTng를 사용하여 수집된 추적과 마찬가지로 분석을 위해 [PerfView](https://github.com/microsoft/perfview)에서 `.nettrace` 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-162">On Windows, `.nettrace` files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis, just like traces collected with ETW or LTTng.</span></span> <span data-ttu-id="61faf-163">Linux에서 수집된 추적의 경우 추적을 Windows 머신으로 이동하여 PerfView에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-163">For traces collected on Linux, you can move the trace to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="61faf-164">또한 `dotnet-trace`의 출력 형식을 `speedscope`로 변경하여 Linux 머신에서 추적을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-164">You may also view the trace on a Linux machine by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="61faf-165">`-f|--format` 옵션을 사용하여 출력 파일 형식을 변경할 수 있습니다. 그러면 `-f speedscope`에서 `dotnet-trace`를 수행하여 `speedscope` 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-165">You can change the output file format using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` to produce a `speedscope` file.</span></span> <span data-ttu-id="61faf-166">현재 `nettrace`(기본 옵션) 및 `speedscope` 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-166">You can currently choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="61faf-167">`Speedscope` 파일은 <https://www.speedscope.app>에서 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-167">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="61faf-168">.NET Core 런타임은 추적을 `nettrace` 형식으로 생성하며, 추적이 완료된 후에는 speedscope로 변환됩니다(지정된 경우).</span><span class="sxs-lookup"><span data-stu-id="61faf-168">The .NET Core runtime generates traces in the `nettrace` format, and they're converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="61faf-169">일부 변환으로 인해 데이터가 손실될 수 있으므로 원본 `nettrace` 파일이 변환된 파일과 함께 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-169">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="using-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="61faf-170">`dotnet-trace`를 사용하여 시간 경과에 따른 카운터 값 수집</span><span class="sxs-lookup"><span data-stu-id="61faf-170">Using `dotnet-trace` to collect counter values over time</span></span>

<span data-ttu-id="61faf-171">프로덕션 환경과 같은 성능에 민감한 설정에서 `EventCounter`를 기본 상태 모니터링에 사용하려고 하고 추적을 실시간으로 감시하지 않고 수집하려는 경우에도 `dotnet-trace`를 사용하여 이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-171">If you're trying to use `EventCounter` for basic health monitoring in  performance-sensitive settings like production environments and you want to collect traces instead of watching them in real time, you can do that with `dotnet-trace` as well.</span></span>

<span data-ttu-id="61faf-172">예를 들어 런타임 성능 카운터 값을 수집하려면 다음 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-172">For example, if you want to collect runtime performance counter values, you can use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="61faf-173">이 명령은 간단한 상태 모니터링을 위해 런타임 카운터에서 초당 한 번씩 보고하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-173">This command tells the runtime counters to be reported once every second for lightweight health monitoring.</span></span> <span data-ttu-id="61faf-174">`EventCounterIntervalSec=1`을 더 높은 값(예: 60)으로 바꾸면 카운터 데이터에서 세분성이 낮은 추적을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-174">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows you to collect a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="61faf-175">오버헤드(및 추적 크기)를 더 줄이기 위해 런타임 이벤트를 사용하지 않도록 설정하려면 다음 명령을 사용하여 런타임 이벤트 및 관리형 스택 프로파일러를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-175">If you want to disable runtime events to reduce the overhead (and trace size) even further, you can use the following command to disable runtime events and managed stack profiler.</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

## <a name="net-providers"></a><span data-ttu-id="61faf-176">.NET 공급자</span><span class="sxs-lookup"><span data-stu-id="61faf-176">.NET Providers</span></span>

<span data-ttu-id="61faf-177">.NET Core 런타임은 다음과 같은 .NET 공급자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-177">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="61faf-178">.NET Core에서 동일한 키워드를 사용하여 `Event Tracing for Windows (ETW)` 및 `EventPipe` 추적을 모두 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-178">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="61faf-179">공급자 이름</span><span class="sxs-lookup"><span data-stu-id="61faf-179">Provider name</span></span>                            | <span data-ttu-id="61faf-180">정보</span><span class="sxs-lookup"><span data-stu-id="61faf-180">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="61faf-181">런타임 공급자</span><span class="sxs-lookup"><span data-stu-id="61faf-181">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="61faf-182">CLR 런타임 키워드</span><span class="sxs-lookup"><span data-stu-id="61faf-182">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="61faf-183">런다운 공급자</span><span class="sxs-lookup"><span data-stu-id="61faf-183">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="61faf-184">CLR 런다운 키워드</span><span class="sxs-lookup"><span data-stu-id="61faf-184">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="61faf-185">샘플 프로파일러를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="61faf-185">Enables the sample profiler.</span></span> |
