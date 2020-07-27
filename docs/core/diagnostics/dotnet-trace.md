---
title: dotnet-trace 도구 - .NET Core
description: dotnet-trace 명령줄 도구를 설치하고 사용합니다.
ms.date: 11/21/2019
ms.openlocfilehash: 6dd968dc49522229dca02c0dc6f3de898026dd82
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924853"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="35832-103">dotnet-trace 성능 분석 유틸리티</span><span class="sxs-lookup"><span data-stu-id="35832-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="35832-104">**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="35832-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-trace"></a><span data-ttu-id="35832-105">dotnet-trace 설치</span><span class="sxs-lookup"><span data-stu-id="35832-105">Install dotnet-trace</span></span>

<span data-ttu-id="35832-106">[dotnet tool install](../tools/dotnet-tool-install.md) 명령으로 `dotnet-trace`[NuGet 패키지](https://www.nuget.org/packages/dotnet-trace) 설치:</span><span class="sxs-lookup"><span data-stu-id="35832-106">Install `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace) with the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="35832-107">개요</span><span class="sxs-lookup"><span data-stu-id="35832-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="35832-108">설명</span><span class="sxs-lookup"><span data-stu-id="35832-108">Description</span></span>

<span data-ttu-id="35832-109">`dotnet-trace` 도구:</span><span class="sxs-lookup"><span data-stu-id="35832-109">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="35832-110">크로스 플랫폼 .NET Core 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="35832-110">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="35832-111">네이티브 프로파일러 없이 실행 중인 프로세스의 .NET Core 추적을 수집할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-111">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="35832-112">.NET Core 런타임의 크로스 플랫폼 `EventPipe` 기술을 기반으로 하여 빌드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35832-112">Is built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span>
* <span data-ttu-id="35832-113">Windows, Linux 또는 macOS에서 동일한 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-113">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="35832-114">옵션</span><span class="sxs-lookup"><span data-stu-id="35832-114">Options</span></span>

- **`--version`**

  <span data-ttu-id="35832-115">dotnet-trace 유틸리티의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-115">Displays the version of the dotnet-trace utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="35832-116">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-116">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="35832-117">명령</span><span class="sxs-lookup"><span data-stu-id="35832-117">Commands</span></span>

| <span data-ttu-id="35832-118">명령</span><span class="sxs-lookup"><span data-stu-id="35832-118">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="35832-119">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="35832-119">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="35832-120">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="35832-120">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="35832-121">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="35832-121">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="35832-122">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="35832-122">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="35832-123">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="35832-123">dotnet-trace collect</span></span>

<span data-ttu-id="35832-124">실행 중인 프로세스에서 진단 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-124">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="35832-125">개요</span><span class="sxs-lookup"><span data-stu-id="35832-125">Synopsis</span></span>

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a><span data-ttu-id="35832-126">옵션</span><span class="sxs-lookup"><span data-stu-id="35832-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="35832-127">추적을 수집하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="35832-127">The process to collect the trace from.</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="35832-128">메모리 내 순환 버퍼의 크기를 MB(메가바이트) 단위로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-128">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="35832-129">기본값은 256MB입니다.</span><span class="sxs-lookup"><span data-stu-id="35832-129">Default 256 MB.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="35832-130">수집된 추적 데이터의 출력 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="35832-130">The output path for the collected trace data.</span></span> <span data-ttu-id="35832-131">지정하지 않으면 기본값인 `trace.nettrace`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="35832-131">If not specified it defaults to `trace.nettrace`.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="35832-132">사용하도록 설정할 `EventPipe` 공급자에 대한 쉼표로 구분된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="35832-132">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="35832-133">이러한 공급자는 `--profile <profile-name>`에서 암시하는 모든 공급자를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-133">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="35832-134">특정 공급자에 대한 불일치 항목이 있는 경우 이 구성이 프로필의 암시적 구성보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-134">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="35832-135">이 공급자 목록의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="35832-135">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="35832-136">`Provider`의 형식: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`</span><span class="sxs-lookup"><span data-stu-id="35832-136">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="35832-137">`KeyValueArgs`의 형식: `[key1=value1][;key2=value2]`</span><span class="sxs-lookup"><span data-stu-id="35832-137">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="35832-138">일반적인 추적 시나리오를 간략하게 지정할 수 있는 미리 정의되어 명명된 공급자 구성 세트입니다.</span><span class="sxs-lookup"><span data-stu-id="35832-138">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--format {NetTrace|Speedscope}`**

  <span data-ttu-id="35832-139">추적 파일 변환에 대한 출력 형식을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-139">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="35832-140">기본값은 `NetTrace`입니다.</span><span class="sxs-lookup"><span data-stu-id="35832-140">The default is `NetTrace`.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="35832-141">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="35832-141">dotnet-trace convert</span></span>

<span data-ttu-id="35832-142">`nettrace` 추적을 대체 추적 분석 도구와 함께 사용할 대체 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-142">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="35832-143">개요</span><span class="sxs-lookup"><span data-stu-id="35832-143">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a><span data-ttu-id="35832-144">인수</span><span class="sxs-lookup"><span data-stu-id="35832-144">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="35832-145">변환할 입력 추적 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="35832-145">Input trace file to be converted.</span></span> <span data-ttu-id="35832-146">기본값은 *trace.nettrace*입니다.</span><span class="sxs-lookup"><span data-stu-id="35832-146">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="35832-147">옵션</span><span class="sxs-lookup"><span data-stu-id="35832-147">Options</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="35832-148">추적 파일 변환에 대한 출력 형식을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-148">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="35832-149">출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="35832-149">Output filename.</span></span> <span data-ttu-id="35832-150">대상 형식의 확장명이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="35832-150">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="35832-151">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="35832-151">dotnet-trace ps</span></span>

<span data-ttu-id="35832-152">첨부할 수 있는 dotnet 프로세스를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-152">Lists dotnet processes that can be attached to.</span></span>

### <a name="synopsis"></a><span data-ttu-id="35832-153">개요</span><span class="sxs-lookup"><span data-stu-id="35832-153">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="35832-154">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="35832-154">dotnet-trace list-profiles</span></span>

<span data-ttu-id="35832-155">각 프로필에 있는 공급자 및 필터에 대한 설명이 포함된 미리 작성된 추적 프로필을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-155">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="35832-156">개요</span><span class="sxs-lookup"><span data-stu-id="35832-156">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="35832-157">dotnet-trace로 추적 수집</span><span class="sxs-lookup"><span data-stu-id="35832-157">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="35832-158">`dotnet-trace`을(를) 사용하여 추적을 수집하는 방법:</span><span class="sxs-lookup"><span data-stu-id="35832-158">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="35832-159">추적을 수집할 .NET Core 애플리케이션의 PID(프로세스 식별자)를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-159">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="35832-160">예를 들어, Windows에서 작업 관리자 또는 `tasklist` 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35832-160">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="35832-161">예를 들어, Linux에서는 `ps` 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="35832-161">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="35832-162">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="35832-162">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="35832-163">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-163">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="35832-164">위의 명령은 다음과 유사한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-164">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="35832-165">`<Enter>` 키를 눌러 수집을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-165">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="35832-166">`dotnet-trace`을(를) 사용하면 *trace.nettrace* 파일의 이벤트 로깅이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="35832-166">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="35832-167">dotnet-trace에서 캡처된 추적 보기</span><span class="sxs-lookup"><span data-stu-id="35832-167">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="35832-168">Windows에서는 분석을 위해 [PerfView](https://github.com/microsoft/perfview)에서 *.nettrace* 파일을 볼 수 있습니다. 다른 플랫폼에서 수집된 추적의 경우, 추적 파일을 Windows 머신으로 이동하여 PerfView에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35832-168">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="35832-169">Linux에서는 `dotnet-trace`의 출력 형식을 `speedscope`(으)로 변경하여 추적을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35832-169">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="35832-170">출력 파일 형식은 `-f|--format` 옵션을 사용하여 변경할 수 있습니다. `-f speedscope`을(를) 사용하면 `dotnet-trace`에서 `speedscope` 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-170">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="35832-171">`nettrace`(기본 옵션) 및 `speedscope` 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35832-171">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="35832-172">`Speedscope` 파일은 <https://www.speedscope.app>에서 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35832-172">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="35832-173">.NET Core 런타임은 `nettrace` 형식으로 추적을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-173">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="35832-174">추적이 완료된 후 추적이 speedscope(지정 된 경우)로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="35832-174">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="35832-175">일부 변환으로 인해 데이터가 손실될 수 있으므로 원본 `nettrace` 파일이 변환된 파일과 함께 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="35832-175">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="35832-176">dotnet-trace를 사용하여 시간 경과에 따라 카운터 값 사용</span><span class="sxs-lookup"><span data-stu-id="35832-176">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="35832-177">`dotnet-trace` 기능:</span><span class="sxs-lookup"><span data-stu-id="35832-177">`dotnet-trace` can:</span></span>

* <span data-ttu-id="35832-178">성능에 민감한 환경에서 기본 상태 모니터링을 위해 `EventCounter`을(를) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-178">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="35832-179">예를 들어, 프로덕션 환경에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35832-179">For example, in production.</span></span>
* <span data-ttu-id="35832-180">실시간으로 볼 필요가 없는 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-180">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="35832-181">예를 들어, 런타임 성능 카운터 값을 수집하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-181">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="35832-182">앞의 명령은 간단한 상태 모니터링을 위해 런타임 카운터에서 초당 한 번씩 보고하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-182">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="35832-183">`EventCounterIntervalSec=1`을 더 높은 값(예: 60)으로 바꾸면 카운터 데이터에서 세분성이 낮은 추적을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35832-183">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="35832-184">다음 명령은 앞의 명령보다 오버 헤드 및 추적 크기를 더 크게 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="35832-184">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="35832-185">앞의 명령은 런타임 이벤트와 관리되는 스택 프로파일러를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-185">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="35832-186">.NET 공급자</span><span class="sxs-lookup"><span data-stu-id="35832-186">.NET Providers</span></span>

<span data-ttu-id="35832-187">.NET Core 런타임은 다음과 같은 .NET 공급자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-187">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="35832-188">.NET Core에서 동일한 키워드를 사용하여 `Event Tracing for Windows (ETW)` 및 `EventPipe` 추적을 모두 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-188">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="35832-189">공급자 이름</span><span class="sxs-lookup"><span data-stu-id="35832-189">Provider name</span></span>                            | <span data-ttu-id="35832-190">정보</span><span class="sxs-lookup"><span data-stu-id="35832-190">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="35832-191">런타임 공급자</span><span class="sxs-lookup"><span data-stu-id="35832-191">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="35832-192">CLR 런타임 키워드</span><span class="sxs-lookup"><span data-stu-id="35832-192">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="35832-193">런다운 공급자</span><span class="sxs-lookup"><span data-stu-id="35832-193">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="35832-194">CLR 런다운 키워드</span><span class="sxs-lookup"><span data-stu-id="35832-194">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="35832-195">샘플 프로파일러를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="35832-195">Enables the sample profiler.</span></span> |
