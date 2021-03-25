---
title: dotnet-trace 진단 도구 - .NET CLI
description: .NET EventPipe를 사용하여 네이티브 프로파일러 없이 실행 중인 프로세스의 .NET 추적을 수집하기 위해 dotnet-trace CLI 도구를 설치하고 사용하는 방법을 알아봅니다.
ms.date: 11/17/2020
ms.openlocfilehash: e4e5bf91a7e6a9bf98e8cb006864b4cbc5ca17a2
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103624190"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="014e4-103">dotnet-trace 성능 분석 유틸리티</span><span class="sxs-lookup"><span data-stu-id="014e4-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="014e4-104">**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="014e4-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="014e4-105">설치</span><span class="sxs-lookup"><span data-stu-id="014e4-105">Install</span></span>

<span data-ttu-id="014e4-106">다음 두 가지 방법으로 `dotnet-trace`를 다운로드하고 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-106">There are two ways to download and install `dotnet-trace`:</span></span>

- <span data-ttu-id="014e4-107">**dotnet 전역 도구:**</span><span class="sxs-lookup"><span data-stu-id="014e4-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="014e4-108">`dotnet-trace` [NuGet 패키지](https://www.nuget.org/packages/dotnet-trace)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-108">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-trace
  ```

- <span data-ttu-id="014e4-109">**직접 다운로드:**</span><span class="sxs-lookup"><span data-stu-id="014e4-109">**Direct download:**</span></span>

  <span data-ttu-id="014e4-110">플랫폼에 맞는 도구 실행 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="014e4-111">OS</span><span class="sxs-lookup"><span data-stu-id="014e4-111">OS</span></span>  | <span data-ttu-id="014e4-112">플랫폼</span><span class="sxs-lookup"><span data-stu-id="014e4-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="014e4-113">Windows</span><span class="sxs-lookup"><span data-stu-id="014e4-113">Windows</span></span> | <span data-ttu-id="014e4-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="014e4-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span></span> |
  | <span data-ttu-id="014e4-115">macOS</span><span class="sxs-lookup"><span data-stu-id="014e4-115">macOS</span></span>   | [<span data-ttu-id="014e4-116">x64</span><span class="sxs-lookup"><span data-stu-id="014e4-116">x64</span></span>](https://aka.ms/dotnet-trace/osx-x64) |
  | <span data-ttu-id="014e4-117">Linux</span><span class="sxs-lookup"><span data-stu-id="014e4-117">Linux</span></span>   | <span data-ttu-id="014e4-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="014e4-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span></span> |

> [!NOTE]
> <span data-ttu-id="014e4-119">x86 앱에서 `dotnet-trace`를 사용하려면 해당하는 x86 버전의 도구가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-119">To use `dotnet-trace` on an x86 app, you need a corresponding x86 version of the tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="014e4-120">개요</span><span class="sxs-lookup"><span data-stu-id="014e4-120">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="014e4-121">설명</span><span class="sxs-lookup"><span data-stu-id="014e4-121">Description</span></span>

<span data-ttu-id="014e4-122">`dotnet-trace` 도구:</span><span class="sxs-lookup"><span data-stu-id="014e4-122">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="014e4-123">크로스 플랫폼 .NET Core 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-123">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="014e4-124">네이티브 프로파일러 없이 실행 중인 프로세스의 .NET Core 추적을 수집할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-124">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="014e4-125">.NET Core 런타임의 [`EventPipe`](./eventpipe.md)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-125">Is built on [`EventPipe`](./eventpipe.md) of the .NET Core runtime.</span></span>
* <span data-ttu-id="014e4-126">Windows, Linux 또는 macOS에서 동일한 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-126">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="014e4-127">옵션</span><span class="sxs-lookup"><span data-stu-id="014e4-127">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="014e4-128">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-128">Shows command-line help.</span></span>

- **`--version`**

  <span data-ttu-id="014e4-129">dotnet-trace 유틸리티의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-129">Displays the version of the dotnet-trace utility.</span></span>

## <a name="commands"></a><span data-ttu-id="014e4-130">명령</span><span class="sxs-lookup"><span data-stu-id="014e4-130">Commands</span></span>

| <span data-ttu-id="014e4-131">명령</span><span class="sxs-lookup"><span data-stu-id="014e4-131">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="014e4-132">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="014e4-132">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="014e4-133">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="014e4-133">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="014e4-134">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="014e4-134">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="014e4-135">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="014e4-135">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="014e4-136">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="014e4-136">dotnet-trace collect</span></span>

<span data-ttu-id="014e4-137">실행 중인 프로세스에서 진단 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-137">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="014e4-138">개요</span><span class="sxs-lookup"><span data-stu-id="014e4-138">Synopsis</span></span>

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>] [--diagnostic-port] [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a><span data-ttu-id="014e4-139">옵션</span><span class="sxs-lookup"><span data-stu-id="014e4-139">Options</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="014e4-140">메모리 내 순환 버퍼의 크기를 MB(메가바이트) 단위로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-140">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="014e4-141">기본값은 256MB입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-141">Default 256 MB.</span></span>

  > [!NOTE]
  > <span data-ttu-id="014e4-142">대상 프로세스가 이벤트를 너무 자주 기록하는 경우 이 버퍼가 오버플로되고 일부 이벤트가 삭제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-142">If the target process writes events too frequently, it can overflow this buffer and some events might be dropped.</span></span> <span data-ttu-id="014e4-143">너무 많은 이벤트가 삭제되는 경우에는 버퍼 크기를 늘려 삭제된 이벤트 수가 감소하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="014e4-143">If too many events are getting dropped, increase the buffer size to see if the number of dropped events reduces.</span></span> <span data-ttu-id="014e4-144">버퍼 크기를 늘려도 삭제된 이벤트 수가 감소하지 않는다면 이는 느린 판독기로 인해 대상 프로세스의 버퍼가 플러시되지 않기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-144">If the number of dropped events does not decrease with a larger buffer size, it may be due to a slow reader preventing the target process' buffers from being flushed.</span></span>

- **`--clreventlevel <clreventlevel>`**

  <span data-ttu-id="014e4-145">내보낼 CLR 이벤트의 자세한 정도입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-145">Verbosity of CLR events to be emitted.</span></span>

- **`--clrevents <clrevents>`**

  <span data-ttu-id="014e4-146">`+` 서명으로 구분할 수 있는 CLR 런타임 공급자 키워드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-146">A list of CLR runtime provider keywords to enable separated by `+` signs.</span></span> <span data-ttu-id="014e4-147">16진수 값이 아닌 문자열 별칭을 통해 이벤트 키워드를 지정할 수 있도록 하는 간단한 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-147">This is a simple mapping that lets you specify event keywords via string aliases rather than their hex values.</span></span> <span data-ttu-id="014e4-148">예를 들어 `dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:3:4`는 `dotnet-trace collect --clrevents gc+gchandle --clreventlevel informational`과 동일한 이벤트 세트를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-148">For example, `dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:3:4` requests the same set of events as `dotnet-trace collect --clrevents gc+gchandle --clreventlevel informational`.</span></span> <span data-ttu-id="014e4-149">다음 표에서는 사용 가능한 키워드의 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-149">The table below shows the list of available keywords:</span></span>

  | <span data-ttu-id="014e4-150">키워드 문자열 별칭</span><span class="sxs-lookup"><span data-stu-id="014e4-150">Keyword String Alias</span></span> | <span data-ttu-id="014e4-151">키워드 16진수 값</span><span class="sxs-lookup"><span data-stu-id="014e4-151">Keyword Hex Value</span></span> |
  | ------------ | ------------------- |
  | `gc` | `0x1` |
  | `gchandle` | `0x2` |
  | `fusion` | `0x4` |
  | `loader` | `0x8` |
  | `jit` | `0x10` |
  | `ngen` | `0x20` |
  | `startenumeration` | `0x40` |
  | `endenumeration` | `0x80` |
  | `security` | `0x400` |
  | `appdomainresourcemanagement` | `0x800` |
  | `jittracing` | `0x1000` |
  | `interop` | `0x2000` |
  | `contention` | `0x4000` |
  | `exception` | `0x8000` |
  | `threading` | `0x10000` |
  | `jittedmethodiltonativemap` | `0x20000` |
  | `overrideandsuppressngenevents` | `0x40000` |
  | `type` | `0x80000` |
  | `gcheapdump` | `0x100000` |
  | `gcsampledobjectallocationhigh` | `0x200000` |
  | `gcheapsurvivalandmovement` | `0x400000` |
  | `gcheapcollect` | `0x800000` |
  | `gcheapandtypenames` | `0x1000000` |
  | `gcsampledobjectallocationlow` | `0x2000000` |
  | `perftrack` | `0x20000000` |
  | `stack` | `0x40000000` |
  | `threadtransfer` | `0x80000000` |
  | `debugger` | `0x100000000` |
  | `monitoring` | `0x200000000` |
  | `codesymbols` | `0x400000000` |
  | `eventsource` | `0x800000000` |
  | `compilation` | `0x1000000000` |
  | `compilationdiagnostic` | `0x2000000000` |
  | `methoddiagnostic` | `0x4000000000` |
  | `typediagnostic` | `0x8000000000` |

  <span data-ttu-id="014e4-152">[.NET 런타임 공급자 참조 설명서](../../fundamentals/diagnostics/runtime-events.md)에서 CLR 공급자에 관해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-152">You can read about the CLR provider more in detail on the [.NET runtime provider reference documentation](../../fundamentals/diagnostics/runtime-events.md).</span></span>

- **`--format {Chromium|NetTrace|Speedscope}`**

  <span data-ttu-id="014e4-153">추적 파일 변환에 대한 출력 형식을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-153">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="014e4-154">기본값은 `NetTrace`입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-154">The default is `NetTrace`.</span></span>

- **`-n, --name <name>`**

  <span data-ttu-id="014e4-155">추적을 수집할 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-155">The name of the process to collect the trace from.</span></span>

- **`--diagnostic-port <path-to-port>`**

  <span data-ttu-id="014e4-156">만들 진단 포트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-156">The name of the diagnostic port to create.</span></span> <span data-ttu-id="014e4-157">이 옵션을 사용하여 앱 시작부터 추적을 수집하는 방법을 알아보려면 [진단 포트를 사용하여 앱 시작부터 추적 수집](#use-diagnostic-port-to-collect-a-trace-from-app-startup)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="014e4-157">See [Use diagnostic port to collect a trace from app startup](#use-diagnostic-port-to-collect-a-trace-from-app-startup) to learn how to use this option to collect a trace from app startup.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="014e4-158">수집된 추적 데이터의 출력 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-158">The output path for the collected trace data.</span></span> <span data-ttu-id="014e4-159">지정하지 않으면 기본값인 `trace.nettrace`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-159">If not specified, it defaults to `trace.nettrace`.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="014e4-160">추적을 수집할 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-160">The process ID to collect the trace from.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="014e4-161">일반적인 추적 시나리오를 간략하게 지정할 수 있는 미리 정의되어 명명된 공급자 구성 세트입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-161">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span> <span data-ttu-id="014e4-162">다음 프로필을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-162">The following profiles are available:</span></span>

 | <span data-ttu-id="014e4-163">프로필</span><span class="sxs-lookup"><span data-stu-id="014e4-163">Profile</span></span> | <span data-ttu-id="014e4-164">설명</span><span class="sxs-lookup"><span data-stu-id="014e4-164">Description</span></span> |
 |---------|-------------|
 |`cpu-sampling`|<span data-ttu-id="014e4-165">CPU 사용량 및 일반 .NET 런타임 정보를 추적하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-165">Useful for tracking CPU usage and general .NET runtime information.</span></span> <span data-ttu-id="014e4-166">이 옵션은 프로필 또는 공급자가 지정되지 않은 경우 기본 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-166">This is the default option if no profile or providers are specified.</span></span>|
 |`gc-verbose`|<span data-ttu-id="014e4-167">GC 컬렉션을 추적하고 개체 할당을 샘플링합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-167">Tracks GC collections and samples object allocations.</span></span>|
 |`gc-collect`|<span data-ttu-id="014e4-168">매우 낮은 오버헤드로 GC 컬렉션을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-168">Tracks GC collections only at very low overhead.</span></span>|

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="014e4-169">사용하도록 설정할 `EventPipe` 공급자에 대한 쉼표로 구분된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-169">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="014e4-170">이러한 공급자는 `--profile <profile-name>`에서 암시하는 모든 공급자를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-170">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="014e4-171">특정 공급자에 대한 불일치 항목이 있는 경우 이 구성이 프로필의 암시적 구성보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-171">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="014e4-172">이 공급자 목록의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-172">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="014e4-173">`Provider`의 형식: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`</span><span class="sxs-lookup"><span data-stu-id="014e4-173">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="014e4-174">`KeyValueArgs`의 형식: `[key1=value1][;key2=value2]`</span><span class="sxs-lookup"><span data-stu-id="014e4-174">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

  <span data-ttu-id="014e4-175">.NET의 잘 알려진 몇 가지 공급자에 대해 자세히 알아보려면 [잘 알려진 이벤트 공급자](./well-known-event-providers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="014e4-175">To learn more about some of the well-known providers in .NET, refer to [Well-known Event Providers](./well-known-event-providers.md).</span></span>

- <span data-ttu-id="014e4-176">**`-- <command>`(.NET 5.0을 실행하는 대상 애플리케이션만 해당)**</span><span class="sxs-lookup"><span data-stu-id="014e4-176">**`-- <command>` (for target applications running .NET 5.0 only)**</span></span>

  <span data-ttu-id="014e4-177">사용자는 컬렉션 구성 매개 변수 다음에 `--`와 명령을 차례로 추가하여 5.0 런타임 이상에서 .NET 애플리케이션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-177">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="014e4-178">이 옵션은 시작 성능 문제 또는 어셈블리 로더 및 바인더 오류와 같이 프로세스 초기에 발생하는 문제를 진단할 때 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-178">This may be helpful when diagnosing issues that happen early in the process, such as startup performance issue or assembly loader and binder errors.</span></span>

  > [!NOTE]
  > <span data-ttu-id="014e4-179">이 옵션을 사용하면 도구에 다시 전달되는 첫 번째 .NET 5.0 프로세스가 모니터링됩니다. 즉, 명령에서 여러 .NET 애플리케이션을 시작하는 경우 첫 번째 앱만 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-179">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="014e4-180">따라서 자체 포함 애플리케이션에서 이 옵션을 사용하거나 `dotnet exec <app.dll>` 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-180">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

> [!NOTE]
> <span data-ttu-id="014e4-181">대규모 애플리케이션에서는 추적을 중지하는 데 오래 걸릴 수 있습니다(최대 몇 분).</span><span class="sxs-lookup"><span data-stu-id="014e4-181">Stopping the trace may take a long time (up to minutes) for large applications.</span></span> <span data-ttu-id="014e4-182">런타임에서는 추적에 캡처된 모든 관리 코드의 형식 캐시를 전송해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-182">The runtime needs to send over the type cache for all managed code that was captured in the trace.</span></span>

> [!NOTE]
> <span data-ttu-id="014e4-183">Linux 및 macOS에서 해당 명령은 대상 애플리케이션 및 `dotnet-trace`가 동일한 `TMPDIR` 환경 변수를 공유할 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-183">On Linux and macOS, this command expects the target application and `dotnet-trace` to share the same `TMPDIR` environment variable.</span></span> <span data-ttu-id="014e4-184">그러지 않으면 명령 시간이 초과됩니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-184">Otherwise, the command will time out.</span></span>

> [!NOTE]
> <span data-ttu-id="014e4-185">`dotnet-trace`를 사용하여 추적을 수집하려면 대상 프로세스를 실행하는 사용자와 동일한 사용자 또는 루트로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-185">To collect a trace using `dotnet-trace`, it needs to be run as the same user as the user running target process or as root.</span></span> <span data-ttu-id="014e4-186">그러지 않으면 도구는 대상 프로세스와 연결을 설정하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-186">Otherwise, the tool will fail to establish a connection with the target process.</span></span>

> [!NOTE]
> <span data-ttu-id="014e4-187">`[ERROR] System.ComponentModel.Win32Exception (299): A 32 bit processes cannot access modules of a 64 bit process.`와 유사한 오류 메시지가 표시되는 경우, 대상 프로세스와 비트 수가 일치하지 않는 `dotnet-trace`를 사용하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-187">If you see an error message similar to the following one: `[ERROR] System.ComponentModel.Win32Exception (299): A 32 bit processes cannot access modules of a 64 bit process.`, you are trying to use `dotnet-trace` that has mismatched bitness against the target process.</span></span> <span data-ttu-id="014e4-188">[설치](#install) 링크에서 도구의 올바른 비트 수를 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-188">Make sure to download the correct bitness of the tool in the [install](#install) link.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="014e4-189">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="014e4-189">dotnet-trace convert</span></span>

<span data-ttu-id="014e4-190">`nettrace` 추적을 대체 추적 분석 도구와 함께 사용할 대체 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-190">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="014e4-191">개요</span><span class="sxs-lookup"><span data-stu-id="014e4-191">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a><span data-ttu-id="014e4-192">인수</span><span class="sxs-lookup"><span data-stu-id="014e4-192">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="014e4-193">변환할 입력 추적 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-193">Input trace file to be converted.</span></span> <span data-ttu-id="014e4-194">기본값은 *trace.nettrace* 입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-194">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="014e4-195">옵션</span><span class="sxs-lookup"><span data-stu-id="014e4-195">Options</span></span>

- **`--format <Chromium|NetTrace|Speedscope>`**

  <span data-ttu-id="014e4-196">추적 파일 변환에 대한 출력 형식을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-196">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="014e4-197">출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-197">Output filename.</span></span> <span data-ttu-id="014e4-198">대상 형식의 확장명이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-198">Extension of target format will be added.</span></span>

> [!NOTE]
> <span data-ttu-id="014e4-199">`nettrace` 파일을 `chromium` 또는 `speedscope` 파일로 변환하면 되돌릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-199">Converting `nettrace` files to `chromium` or `speedscope` files is irreversible.</span></span> <span data-ttu-id="014e4-200">`speedscope` 및 `chromium` 파일에는 `nettrace` 파일을 다시 생성하는 데 필요한 정보가 일부 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-200">`speedscope` and `chromium` files don't have all the information necessary to reconstruct `nettrace` files.</span></span> <span data-ttu-id="014e4-201">그러나 `convert` 명령은 원래 `nettrace` 파일을 유지하므로 나중에 파일을 열 계획인 경우 삭제하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="014e4-201">However, the `convert` command preserves the original `nettrace` file, so don't delete this file if you plan to open it in the future.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="014e4-202">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="014e4-202">dotnet-trace ps</span></span>

 <span data-ttu-id="014e4-203">추적을 수집할 수 있는 dotnet 프로세스를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-203">Lists the dotnet processes that traces can be collected from.</span></span>

### <a name="synopsis"></a><span data-ttu-id="014e4-204">개요</span><span class="sxs-lookup"><span data-stu-id="014e4-204">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="014e4-205">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="014e4-205">dotnet-trace list-profiles</span></span>

<span data-ttu-id="014e4-206">각 프로필에 있는 공급자 및 필터에 대한 설명이 포함된 미리 작성된 추적 프로필을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-206">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="014e4-207">개요</span><span class="sxs-lookup"><span data-stu-id="014e4-207">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="014e4-208">dotnet-trace로 추적 수집</span><span class="sxs-lookup"><span data-stu-id="014e4-208">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="014e4-209">`dotnet-trace`을(를) 사용하여 추적을 수집하는 방법:</span><span class="sxs-lookup"><span data-stu-id="014e4-209">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="014e4-210">추적을 수집할 .NET Core 애플리케이션의 PID(프로세스 식별자)를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-210">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="014e4-211">예를 들어, Windows에서 작업 관리자 또는 `tasklist` 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-211">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="014e4-212">예를 들어, Linux에서는 `ps` 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-212">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="014e4-213">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="014e4-213">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="014e4-214">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-214">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="014e4-215">위의 명령은 다음과 유사한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-215">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="014e4-216">`<Enter>` 키를 눌러 수집을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-216">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="014e4-217">`dotnet-trace`을(를) 사용하면 *trace.nettrace* 파일의 이벤트 로깅이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-217">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a><span data-ttu-id="014e4-218">dotnet-trace를 사용하여 자식 애플리케이션을 시작하고 시작에서 추적 수집</span><span class="sxs-lookup"><span data-stu-id="014e4-218">Launch a child application and collect a trace from its startup using dotnet-trace</span></span>

> [!IMPORTANT]
> <span data-ttu-id="014e4-219">.NET 5.0 이상을 실행하는 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-219">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="014e4-220">경우에 따라 시작에서 프로세스의 추적을 수집하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-220">Sometimes it may be useful to collect a trace of a process from its startup.</span></span> <span data-ttu-id="014e4-221">.NET 5.0 이상을 실행하는 앱의 경우 dotnet-trace를 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-221">For apps running .NET 5.0 or later, it is possible to do this by using dotnet-trace.</span></span>

<span data-ttu-id="014e4-222">그러면 `arg1` 및 `arg2`를 명령줄 인수로 사용하여 `hello.exe`가 시작되고 런타임 시작에서 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-222">This will launch `hello.exe` with `arg1` and `arg2` as its command-line arguments and collect a trace from its runtime startup:</span></span>

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

<span data-ttu-id="014e4-223">위의 명령은 다음과 유사한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-223">The preceding command generates output similar to the following:</span></span>

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

<span data-ttu-id="014e4-224">`<Enter>` 또는 `<Ctrl + C>` 키를 눌러 추적 수집을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-224">You can stop collecting the trace by pressing `<Enter>` or `<Ctrl + C>` key.</span></span> <span data-ttu-id="014e4-225">그러면 `hello.exe`도 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-225">Doing this will also exit `hello.exe`.</span></span>

> [!NOTE]
> <span data-ttu-id="014e4-226">dotnet-trace를 통해 `hello.exe`를 시작하면 해당 입출력이 리디렉션되어 stdin/stdout과 상호 작용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-226">Launching `hello.exe` via dotnet-trace will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span>
> <span data-ttu-id="014e4-227">Ctrl+C 또는 SIGTERM을 통해 도구를 종료하면 도구와 자식 프로세스가 모두 안전하게 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-227">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span>
> <span data-ttu-id="014e4-228">자식 프로세스가 도구보다 먼저 종료되면 도구도 종료되고 추적을 안전하게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-228">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span>

## <a name="use-diagnostic-port-to-collect-a-trace-from-app-startup"></a><span data-ttu-id="014e4-229">진단 포트를 사용하여 앱 시작부터 추적 수집</span><span class="sxs-lookup"><span data-stu-id="014e4-229">Use diagnostic port to collect a trace from app startup</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="014e4-230">.NET 5.0 이상을 실행하는 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-230">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="014e4-231">진단 포트는 .NET 5에서 추가된 새로운 런타임 기능으로, 앱 시작부터 추적을 시작하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-231">Diagnostic port is a new runtime feature that was added in .NET 5 that allows you to start tracing from app startup.</span></span> <span data-ttu-id="014e4-232">`dotnet-trace`를 사용하여 이렇게 하려면 위의 예제에 설명된 대로 `dotnet-trace collect -- <command>`를 사용하거나 `--diagnostic-port` 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-232">To do this using `dotnet-trace`, you can either use `dotnet-trace collect -- <command>` as described in the examples above, or use the `--diagnostic-port` option.</span></span>

<span data-ttu-id="014e4-233">`dotnet-trace <collect|monitor> -- <command>`를 사용하여 애플리케이션을 자식 프로세스로 실행하는 것이 시작부터 빠르게 추적하는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-233">Using `dotnet-trace <collect|monitor> -- <command>` to launch the application as a child process is the simplest way to quickly trace it from its startup.</span></span>

<span data-ttu-id="014e4-234">하지만 추적되는 앱의 수명을 더 세부적으로 제어하거나(예: 처음 10분간만 앱을 모니터링하고 실행 계속) CLI를 사용하여 앱을 조작해야 하는 경우에는 `--diagnostic-port` 옵션을 사용하여 모니터링되는 대상 앱과 `dotnet-trace`를 모두 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-234">However, when you want to gain a finer control over the lifetime of the app being traced (for example, monitor the app for the first 10 minutes only and continue executing) or if you need to interact with the app using the CLI, using `--diagnostic-port` option allows you to control both the target app being monitored and `dotnet-trace`.</span></span>

1. <span data-ttu-id="014e4-235">아래 명령은 `dotnet-trace`에서 `myport.sock`라는 진단 소켓을 만들고 연결을 대기하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-235">The command below makes `dotnet-trace` create a diagnostics socket named `myport.sock` and wait for a connection.</span></span>

    > ```dotnet-cli
    > dotnet-trace collect --diagnostic-port myport.sock
    > ```

    <span data-ttu-id="014e4-236">출력:</span><span class="sxs-lookup"><span data-stu-id="014e4-236">Output:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. <span data-ttu-id="014e4-237">별도의 콘솔에서 `DOTNET_DiagnosticPorts` 환경 변수를 `dotnet-trace` 출력의 값으로 설정하고 대상 애플리케이션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-237">In a separate console, launch the target application with the environment variable `DOTNET_DiagnosticPorts` set to the value in the `dotnet-trace` output.</span></span>

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    <span data-ttu-id="014e4-238">그러면 `dotnet-trace`에서 `my-dotnet-app` 추적을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-238">This should then enable `dotnet-trace` to start tracing `my-dotnet-app`:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > <span data-ttu-id="014e4-239">`dotnet run`을 사용하여 앱을 시작하면 문제가 될 수 있는데, dotnet CLI가 앱이 아닌 여러 자식 프로세스를 생성할 수 있고 해당 프로세스가 앱보다 먼저 `dotnet-trace`에 연결하여 앱이 런타임에 일시 중단될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-239">Launching your app with `dotnet run` can be problematic because the dotnet CLI may spawn many child processes that are not your app and they can connect to `dotnet-trace` before your app, leaving your app to be suspended at runtime.</span></span> <span data-ttu-id="014e4-240">앱의 자체 포함 버전을 직접 사용하거나 `dotnet exec`를 사용하여 애플리케이션을 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-240">It is recommended you directly use a self-contained version of the app or use `dotnet exec` to launch the application.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="014e4-241">dotnet-trace에서 캡처된 추적 보기</span><span class="sxs-lookup"><span data-stu-id="014e4-241">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="014e4-242">Windows에서는 분석을 위해 [PerfView](https://github.com/microsoft/perfview)에서 *.nettrace* 파일을 볼 수 있습니다. 다른 플랫폼에서 수집된 추적의 경우, 추적 파일을 Windows 머신으로 이동하여 PerfView에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-242">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="014e4-243">Linux에서는 `dotnet-trace`의 출력 형식을 `speedscope`(으)로 변경하여 추적을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-243">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="014e4-244">출력 파일 형식은 `-f|--format` 옵션을 사용하여 변경할 수 있습니다. `-f speedscope`을(를) 사용하면 `dotnet-trace`에서 `speedscope` 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-244">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="014e4-245">`nettrace`(기본 옵션) 및 `speedscope` 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-245">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="014e4-246">`Speedscope` 파일은 <https://www.speedscope.app>에서 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-246">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="014e4-247">.NET Core 런타임은 `nettrace` 형식으로 추적을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-247">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="014e4-248">추적이 완료된 후 추적이 speedscope(지정 된 경우)로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-248">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="014e4-249">일부 변환으로 인해 데이터가 손실될 수 있으므로 원본 `nettrace` 파일이 변환된 파일과 함께 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-249">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="014e4-250">dotnet-trace를 사용하여 시간 경과에 따라 카운터 값 사용</span><span class="sxs-lookup"><span data-stu-id="014e4-250">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="014e4-251">`dotnet-trace` 기능:</span><span class="sxs-lookup"><span data-stu-id="014e4-251">`dotnet-trace` can:</span></span>

* <span data-ttu-id="014e4-252">성능에 민감한 환경에서 기본 상태 모니터링을 위해 `EventCounter`을(를) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-252">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="014e4-253">예를 들어, 프로덕션 환경에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-253">For example, in production.</span></span>
* <span data-ttu-id="014e4-254">실시간으로 볼 필요가 없는 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-254">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="014e4-255">예를 들어, 런타임 성능 카운터 값을 수집하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-255">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="014e4-256">앞의 명령은 간단한 상태 모니터링을 위해 런타임 카운터에서 초당 한 번씩 보고하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-256">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="014e4-257">`EventCounterIntervalSec=1`을 더 높은 값(예: 60)으로 바꾸면 카운터 데이터에서 세분성이 낮은 추적을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-257">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="014e4-258">다음 명령은 앞의 명령보다 오버 헤드 및 추적 크기를 더 크게 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-258">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="014e4-259">앞의 명령은 런타임 이벤트와 관리되는 스택 프로파일러를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-259">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="use-rsp-file-to-avoid-typing-long-commands"></a><span data-ttu-id="014e4-260">긴 명령을 입력하지 않기 위해 .rsp 파일 사용</span><span class="sxs-lookup"><span data-stu-id="014e4-260">Use .rsp file to avoid typing long commands</span></span>

<span data-ttu-id="014e4-261">전달할 인수를 포함하는 `.rsp` 파일을 사용하여 `dotnet-trace`를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-261">You can launch `dotnet-trace` with an `.rsp` file that contains the arguments to pass.</span></span> <span data-ttu-id="014e4-262">이렇게 하면 긴 인수가 필요한 공급자를 사용하도록 설정하거나 문자를 없애는 셸 환경을 사용할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-262">This can be useful when enabling providers that expect lengthy arguments or when using a shell environment that strips characters.</span></span>

<span data-ttu-id="014e4-263">예를 들어 다음 공급자는 추적할 때마다 입력하는 일이 번거로울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-263">For example, the following provider can be cumbersome to type out each time you want to trace:</span></span>

```cmd
dotnet-trace collect --providers Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

<span data-ttu-id="014e4-264">또한 이전 예제에서는 `"`가 인수의 일부로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-264">In addition, the previous example contains `"` as part of the argument.</span></span> <span data-ttu-id="014e4-265">따옴표는 각 셸에서 동일하게 처리되지 않으므로 여러 셸을 사용할 때 다양한 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-265">Because quotes are not handled equally by each shell, you may experience various issues when using different shells.</span></span> <span data-ttu-id="014e4-266">예를 들어 `zsh`에서 입력하는 명령과 `cmd`의 명령이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-266">For example, the command to enter in `zsh` is different to the command in `cmd`.</span></span>

<span data-ttu-id="014e4-267">해당 명령을 매번 입력하는 대신 다음 텍스트를 `myprofile.rsp`라는 파일에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-267">Instead of typing this each time, you can save the following text into a file called `myprofile.rsp`.</span></span>

```txt
--providers
Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

<span data-ttu-id="014e4-268">`myprofile.rsp`를 저장했으면 다음 명령을 통해 이 구성을 사용하여 `dotnet-trace`를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="014e4-268">Once you've saved `myprofile.rsp`, you can launch `dotnet-trace` with this configuration using the following command:</span></span>

```bash
dotnet-trace @myprofile.rsp
```

## <a name="see-also"></a><span data-ttu-id="014e4-269">참조</span><span class="sxs-lookup"><span data-stu-id="014e4-269">See also</span></span>

- [<span data-ttu-id="014e4-270">.NET의 잘 알려진 이벤트 공급자</span><span class="sxs-lookup"><span data-stu-id="014e4-270">Well-known event providers from .NET</span></span>](well-known-event-providers.md)
