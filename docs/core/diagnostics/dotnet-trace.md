---
title: dotnet-trace 진단 도구 - .NET CLI
description: .NET EventPipe를 사용하여 네이티브 프로파일러 없이 실행 중인 프로세스의 .NET 추적을 수집하기 위해 dotnet-trace CLI 도구를 설치하고 사용하는 방법을 알아봅니다.
ms.date: 11/17/2020
ms.openlocfilehash: 6bc5ad449f62ed0080ff6b1f401f1871d90cf5ec
ms.sourcegitcommit: c6de55556add9f92af17e0f8d1da8f356a19a03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "96549334"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="699dd-103">dotnet-trace 성능 분석 유틸리티</span><span class="sxs-lookup"><span data-stu-id="699dd-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="699dd-104">**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="699dd-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="699dd-105">설치</span><span class="sxs-lookup"><span data-stu-id="699dd-105">Install</span></span>

<span data-ttu-id="699dd-106">다음 두 가지 방법으로 `dotnet-trace`를 다운로드하고 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-106">There are two ways to download and install `dotnet-trace`:</span></span>

- <span data-ttu-id="699dd-107">**dotnet 전역 도구:**</span><span class="sxs-lookup"><span data-stu-id="699dd-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="699dd-108">`dotnet-trace` [NuGet 패키지](https://www.nuget.org/packages/dotnet-trace)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-108">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-trace
  ```

- <span data-ttu-id="699dd-109">**직접 다운로드:**</span><span class="sxs-lookup"><span data-stu-id="699dd-109">**Direct download:**</span></span>

  <span data-ttu-id="699dd-110">플랫폼에 맞는 도구 실행 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="699dd-111">OS</span><span class="sxs-lookup"><span data-stu-id="699dd-111">OS</span></span>  | <span data-ttu-id="699dd-112">플랫폼</span><span class="sxs-lookup"><span data-stu-id="699dd-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="699dd-113">Windows</span><span class="sxs-lookup"><span data-stu-id="699dd-113">Windows</span></span> | <span data-ttu-id="699dd-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="699dd-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span></span> |
  | <span data-ttu-id="699dd-115">macOS</span><span class="sxs-lookup"><span data-stu-id="699dd-115">macOS</span></span>   | [<span data-ttu-id="699dd-116">x64</span><span class="sxs-lookup"><span data-stu-id="699dd-116">x64</span></span>](https://aka.ms/dotnet-trace/osx-x64) |
  | <span data-ttu-id="699dd-117">Linux</span><span class="sxs-lookup"><span data-stu-id="699dd-117">Linux</span></span>   | <span data-ttu-id="699dd-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="699dd-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="699dd-119">개요</span><span class="sxs-lookup"><span data-stu-id="699dd-119">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="699dd-120">설명</span><span class="sxs-lookup"><span data-stu-id="699dd-120">Description</span></span>

<span data-ttu-id="699dd-121">`dotnet-trace` 도구:</span><span class="sxs-lookup"><span data-stu-id="699dd-121">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="699dd-122">크로스 플랫폼 .NET Core 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-122">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="699dd-123">네이티브 프로파일러 없이 실행 중인 프로세스의 .NET Core 추적을 수집할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-123">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="699dd-124">.NET Core 런타임의 [`EventPipe`](./eventpipe.md)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-124">Is built on [`EventPipe`](./eventpipe.md) of the .NET Core runtime.</span></span>
* <span data-ttu-id="699dd-125">Windows, Linux 또는 macOS에서 동일한 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-125">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="699dd-126">옵션</span><span class="sxs-lookup"><span data-stu-id="699dd-126">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="699dd-127">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-127">Shows command-line help.</span></span>

- **`--version`**

  <span data-ttu-id="699dd-128">dotnet-trace 유틸리티의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-128">Displays the version of the dotnet-trace utility.</span></span>

## <a name="commands"></a><span data-ttu-id="699dd-129">명령</span><span class="sxs-lookup"><span data-stu-id="699dd-129">Commands</span></span>

| <span data-ttu-id="699dd-130">명령</span><span class="sxs-lookup"><span data-stu-id="699dd-130">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="699dd-131">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="699dd-131">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="699dd-132">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="699dd-132">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="699dd-133">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="699dd-133">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="699dd-134">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="699dd-134">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="699dd-135">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="699dd-135">dotnet-trace collect</span></span>

<span data-ttu-id="699dd-136">실행 중인 프로세스에서 진단 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-136">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="699dd-137">개요</span><span class="sxs-lookup"><span data-stu-id="699dd-137">Synopsis</span></span>

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>]  [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a><span data-ttu-id="699dd-138">옵션</span><span class="sxs-lookup"><span data-stu-id="699dd-138">Options</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="699dd-139">메모리 내 순환 버퍼의 크기를 MB(메가바이트) 단위로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-139">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="699dd-140">기본값은 256MB입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-140">Default 256 MB.</span></span>

- **`--clreventlevel <clreventlevel>`**

  <span data-ttu-id="699dd-141">내보낼 CLR 이벤트의 자세한 정도입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-141">Verbosity of CLR events to be emitted.</span></span>

- **`--clrevents <clrevents>`**

  <span data-ttu-id="699dd-142">내보낼 CLR 런타임 이벤트의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-142">List of CLR runtime events to emit.</span></span>

- **`--format {Chromium|NetTrace|Speedscope}`**

  <span data-ttu-id="699dd-143">추적 파일 변환에 대한 출력 형식을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-143">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="699dd-144">기본값은 `NetTrace`입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-144">The default is `NetTrace`.</span></span>

- **`-n, --name <name>`**

  <span data-ttu-id="699dd-145">추적을 수집할 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-145">The name of the process to collect the trace from.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="699dd-146">수집된 추적 데이터의 출력 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-146">The output path for the collected trace data.</span></span> <span data-ttu-id="699dd-147">지정하지 않으면 기본값인 `trace.nettrace`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-147">If not specified, it defaults to `trace.nettrace`.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="699dd-148">추적을 수집할 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-148">The process ID to collect the trace from.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="699dd-149">일반적인 추적 시나리오를 간략하게 지정할 수 있는 미리 정의되어 명명된 공급자 구성 세트입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-149">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span> <span data-ttu-id="699dd-150">다음 프로필을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-150">The following profiles are available:</span></span>

 | <span data-ttu-id="699dd-151">프로필</span><span class="sxs-lookup"><span data-stu-id="699dd-151">Profile</span></span> | <span data-ttu-id="699dd-152">설명</span><span class="sxs-lookup"><span data-stu-id="699dd-152">Description</span></span> |
 |---------|-------------|
 |`cpu-sampling`|<span data-ttu-id="699dd-153">CPU 사용량 및 일반 .NET 런타임 정보를 추적하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-153">Useful for tracking CPU usage and general .NET runtime information.</span></span> <span data-ttu-id="699dd-154">이 옵션은 프로필 또는 공급자가 지정되지 않은 경우 기본 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-154">This is the default option if no profile or providers are specified.</span></span>|
 |`gc-verbose`|<span data-ttu-id="699dd-155">GC 컬렉션을 추적하고 개체 할당을 샘플링합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-155">Tracks GC collections and samples object allocations.</span></span>|
 |`gc-collect`|<span data-ttu-id="699dd-156">매우 낮은 오버헤드로 GC 컬렉션을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-156">Tracks GC collections only at very low overhead.</span></span>|

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="699dd-157">사용하도록 설정할 `EventPipe` 공급자에 대한 쉼표로 구분된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-157">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="699dd-158">이러한 공급자는 `--profile <profile-name>`에서 암시하는 모든 공급자를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-158">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="699dd-159">특정 공급자에 대한 불일치 항목이 있는 경우 이 구성이 프로필의 암시적 구성보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-159">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="699dd-160">이 공급자 목록의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-160">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="699dd-161">`Provider`의 형식: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`</span><span class="sxs-lookup"><span data-stu-id="699dd-161">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="699dd-162">`KeyValueArgs`의 형식: `[key1=value1][;key2=value2]`</span><span class="sxs-lookup"><span data-stu-id="699dd-162">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- <span data-ttu-id="699dd-163">**`-- <command>`(.NET 5.0을 실행하는 대상 애플리케이션만 해당)**</span><span class="sxs-lookup"><span data-stu-id="699dd-163">**`-- <command>` (for target applications running .NET 5.0 only)**</span></span>

  <span data-ttu-id="699dd-164">사용자는 컬렉션 구성 매개 변수 다음에 `--`와 명령을 차례로 추가하여 5.0 런타임 이상에서 .NET 애플리케이션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-164">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="699dd-165">이 옵션은 시작 성능 문제 또는 어셈블리 로더 및 바인더 오류와 같이 프로세스 초기에 발생하는 문제를 진단할 때 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-165">This may be helpful when diagnosing issues that happen early in the process, such as startup performance issue or assembly loader and binder errors.</span></span>

  > [!NOTE]
  > <span data-ttu-id="699dd-166">이 옵션을 사용하면 도구에 다시 전달되는 첫 번째 .NET 5.0 프로세스가 모니터링됩니다. 즉, 명령에서 여러 .NET 애플리케이션을 시작하는 경우 첫 번째 앱만 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-166">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="699dd-167">따라서 자체 포함 애플리케이션에서 이 옵션을 사용하거나 `dotnet exec <app.dll>` 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-167">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="699dd-168">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="699dd-168">dotnet-trace convert</span></span>

<span data-ttu-id="699dd-169">`nettrace` 추적을 대체 추적 분석 도구와 함께 사용할 대체 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-169">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="699dd-170">개요</span><span class="sxs-lookup"><span data-stu-id="699dd-170">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a><span data-ttu-id="699dd-171">인수</span><span class="sxs-lookup"><span data-stu-id="699dd-171">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="699dd-172">변환할 입력 추적 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-172">Input trace file to be converted.</span></span> <span data-ttu-id="699dd-173">기본값은 *trace.nettrace* 입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-173">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="699dd-174">옵션</span><span class="sxs-lookup"><span data-stu-id="699dd-174">Options</span></span>

- **`--format <Chromium|NetTrace|Speedscope>`**

  <span data-ttu-id="699dd-175">추적 파일 변환에 대한 출력 형식을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-175">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="699dd-176">출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-176">Output filename.</span></span> <span data-ttu-id="699dd-177">대상 형식의 확장명이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-177">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="699dd-178">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="699dd-178">dotnet-trace ps</span></span>

 <span data-ttu-id="699dd-179">추적을 수집할 수 있는 dotnet 프로세스를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-179">Lists the dotnet processes that traces can be collected from.</span></span>

### <a name="synopsis"></a><span data-ttu-id="699dd-180">개요</span><span class="sxs-lookup"><span data-stu-id="699dd-180">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="699dd-181">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="699dd-181">dotnet-trace list-profiles</span></span>

<span data-ttu-id="699dd-182">각 프로필에 있는 공급자 및 필터에 대한 설명이 포함된 미리 작성된 추적 프로필을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-182">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="699dd-183">개요</span><span class="sxs-lookup"><span data-stu-id="699dd-183">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="699dd-184">dotnet-trace로 추적 수집</span><span class="sxs-lookup"><span data-stu-id="699dd-184">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="699dd-185">`dotnet-trace`을(를) 사용하여 추적을 수집하는 방법:</span><span class="sxs-lookup"><span data-stu-id="699dd-185">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="699dd-186">추적을 수집할 .NET Core 애플리케이션의 PID(프로세스 식별자)를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-186">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="699dd-187">예를 들어, Windows에서 작업 관리자 또는 `tasklist` 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-187">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="699dd-188">예를 들어, Linux에서는 `ps` 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-188">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="699dd-189">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="699dd-189">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="699dd-190">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-190">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="699dd-191">위의 명령은 다음과 유사한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-191">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="699dd-192">`<Enter>` 키를 눌러 수집을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-192">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="699dd-193">`dotnet-trace`을(를) 사용하면 *trace.nettrace* 파일의 이벤트 로깅이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-193">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a><span data-ttu-id="699dd-194">dotnet-trace를 사용하여 자식 애플리케이션을 시작하고 시작에서 추적 수집</span><span class="sxs-lookup"><span data-stu-id="699dd-194">Launch a child application and collect a trace from its startup using dotnet-trace</span></span>

> [!IMPORTANT]
> <span data-ttu-id="699dd-195">.NET 5.0 이상을 실행하는 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-195">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="699dd-196">경우에 따라 시작에서 프로세스의 추적을 수집하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-196">Sometimes it may be useful to collect a trace of a process from its startup.</span></span> <span data-ttu-id="699dd-197">.NET 5.0 이상을 실행하는 앱의 경우 dotnet-trace를 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-197">For apps running .NET 5.0 or later, it is possible to do this by using dotnet-trace.</span></span>

<span data-ttu-id="699dd-198">그러면 `arg1` 및 `arg2`를 명령줄 인수로 사용하여 `hello.exe`가 시작되고 런타임 시작에서 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-198">This will launch `hello.exe` with `arg1` and `arg2` as its command-line arguments and collect a trace from its runtime startup:</span></span>

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

<span data-ttu-id="699dd-199">위의 명령은 다음과 유사한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-199">The preceding command generates output similar to the following:</span></span>

```console
No profile or providers specified, defaulting to trace profile 'cpu-sampling'

Provider Name                           Keywords            Level               Enabled By
Microsoft-DotNETCore-SampleProfiler     0x0000F00000000000  Informational(4)    --profile
Microsoft-Windows-DotNETRuntime         0x00000014C14FCCBD  Informational(4)    --profile

Process        : E:\temp\gcperfsim\bin\Debug\net5.0\gcperfsim.exe
Output File    : E:\temp\gcperfsim\trace.nettrace


[00:00:00:05]   Recording trace 122.244  (KB)
Press <Enter> or <Ctrl+C> to exit...
```

<span data-ttu-id="699dd-200">`<Enter>` 또는 `<Ctrl + C>` 키를 눌러 추적 수집을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-200">You can stop collecting the trace by pressing `<Enter>` or `<Ctrl + C>` key.</span></span> <span data-ttu-id="699dd-201">그러면 `hello.exe`도 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-201">Doing this will also exit `hello.exe`.</span></span>

> [!NOTE]
> <span data-ttu-id="699dd-202">dotnet-trace를 통해 `hello.exe`를 시작하면 해당 입출력이 리디렉션되어 stdin/stdout과 상호 작용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-202">Launching `hello.exe` via dotnet-trace will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span>
> <span data-ttu-id="699dd-203">Ctrl+C 또는 SIGTERM을 통해 도구를 종료하면 도구와 자식 프로세스가 모두 안전하게 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-203">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span>
> <span data-ttu-id="699dd-204">자식 프로세스가 도구보다 먼저 종료되면 도구도 종료되고 추적을 안전하게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-204">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="699dd-205">dotnet-trace에서 캡처된 추적 보기</span><span class="sxs-lookup"><span data-stu-id="699dd-205">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="699dd-206">Windows에서는 분석을 위해 [PerfView](https://github.com/microsoft/perfview)에서 *.nettrace* 파일을 볼 수 있습니다. 다른 플랫폼에서 수집된 추적의 경우, 추적 파일을 Windows 머신으로 이동하여 PerfView에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-206">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="699dd-207">Linux에서는 `dotnet-trace`의 출력 형식을 `speedscope`(으)로 변경하여 추적을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-207">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="699dd-208">출력 파일 형식은 `-f|--format` 옵션을 사용하여 변경할 수 있습니다. `-f speedscope`을(를) 사용하면 `dotnet-trace`에서 `speedscope` 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-208">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="699dd-209">`nettrace`(기본 옵션) 및 `speedscope` 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-209">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="699dd-210">`Speedscope` 파일은 <https://www.speedscope.app>에서 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-210">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="699dd-211">.NET Core 런타임은 `nettrace` 형식으로 추적을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-211">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="699dd-212">추적이 완료된 후 추적이 speedscope(지정 된 경우)로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-212">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="699dd-213">일부 변환으로 인해 데이터가 손실될 수 있으므로 원본 `nettrace` 파일이 변환된 파일과 함께 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-213">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="699dd-214">dotnet-trace를 사용하여 시간 경과에 따라 카운터 값 사용</span><span class="sxs-lookup"><span data-stu-id="699dd-214">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="699dd-215">`dotnet-trace` 기능:</span><span class="sxs-lookup"><span data-stu-id="699dd-215">`dotnet-trace` can:</span></span>

* <span data-ttu-id="699dd-216">성능에 민감한 환경에서 기본 상태 모니터링을 위해 `EventCounter`을(를) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-216">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="699dd-217">예를 들어, 프로덕션 환경에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-217">For example, in production.</span></span>
* <span data-ttu-id="699dd-218">실시간으로 볼 필요가 없는 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-218">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="699dd-219">예를 들어, 런타임 성능 카운터 값을 수집하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-219">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="699dd-220">앞의 명령은 간단한 상태 모니터링을 위해 런타임 카운터에서 초당 한 번씩 보고하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-220">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="699dd-221">`EventCounterIntervalSec=1`을 더 높은 값(예: 60)으로 바꾸면 카운터 데이터에서 세분성이 낮은 추적을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-221">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="699dd-222">다음 명령은 앞의 명령보다 오버 헤드 및 추적 크기를 더 크게 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-222">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="699dd-223">앞의 명령은 런타임 이벤트와 관리되는 스택 프로파일러를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-223">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="699dd-224">.NET 공급자</span><span class="sxs-lookup"><span data-stu-id="699dd-224">.NET Providers</span></span>

<span data-ttu-id="699dd-225">.NET Core 런타임은 다음과 같은 .NET 공급자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-225">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="699dd-226">.NET Core에서 동일한 키워드를 사용하여 `Event Tracing for Windows (ETW)` 및 `EventPipe` 추적을 모두 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-226">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="699dd-227">공급자 이름</span><span class="sxs-lookup"><span data-stu-id="699dd-227">Provider name</span></span>                            | <span data-ttu-id="699dd-228">정보</span><span class="sxs-lookup"><span data-stu-id="699dd-228">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="699dd-229">런타임 공급자</span><span class="sxs-lookup"><span data-stu-id="699dd-229">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="699dd-230">CLR 런타임 키워드</span><span class="sxs-lookup"><span data-stu-id="699dd-230">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="699dd-231">런다운 공급자</span><span class="sxs-lookup"><span data-stu-id="699dd-231">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="699dd-232">CLR 런다운 키워드</span><span class="sxs-lookup"><span data-stu-id="699dd-232">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="699dd-233">샘플 프로파일러를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="699dd-233">Enables the sample profiler.</span></span> |
