---
title: dotnet-trace 진단 도구 - .NET CLI
description: .NET EventPipe를 사용하여 네이티브 프로파일러 없이 실행 중인 프로세스의 .NET 추적을 수집하기 위해 dotnet-trace CLI 도구를 설치하고 사용하는 방법을 알아봅니다.
ms.date: 11/17/2020
ms.openlocfilehash: d0798e4f703c18c48db47193ac24ec0d13b66ae5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829312"
---
# <a name="dotnet-trace-performance-analysis-utility"></a>dotnet-trace 성능 분석 유틸리티

**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전

## <a name="install"></a>설치

다음 두 가지 방법으로 `dotnet-trace`를 다운로드하고 설치할 수 있습니다.

- **dotnet 전역 도구:**

  `dotnet-trace` [NuGet 패키지](https://www.nuget.org/packages/dotnet-trace)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.

  ```dotnetcli
  dotnet tool install --global dotnet-trace
  ```

- **직접 다운로드:**

  플랫폼에 맞는 도구 실행 파일을 다운로드합니다.

  | OS  | 플랫폼 |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-trace/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64) |

## <a name="synopsis"></a>개요

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>설명

`dotnet-trace` 도구:

* 크로스 플랫폼 .NET Core 도구입니다.
* 네이티브 프로파일러 없이 실행 중인 프로세스의 .NET Core 추적을 수집할 수 있도록 합니다.
* .NET Core 런타임의 [`EventPipe`](./eventpipe.md)를 기반으로 합니다.
* Windows, Linux 또는 macOS에서 동일한 환경을 제공합니다.

## <a name="options"></a>옵션

- **`-h|--help`**

  명령줄 도움말을 표시합니다.

- **`--version`**

  dotnet-trace 유틸리티의 버전을 표시합니다.

## <a name="commands"></a>명령

| 명령                                                   |
|-----------------------------------------------------------|
| [dotnet-trace collect](#dotnet-trace-collect)             |
| [dotnet-trace convert](#dotnet-trace-convert)             |
| [dotnet-trace ps](#dotnet-trace-ps)                       |
| [dotnet-trace list-profiles](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a>dotnet-trace collect

실행 중인 프로세스에서 진단 추적을 수집합니다.

### <a name="synopsis"></a>개요

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>]  [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a>옵션

- **`--buffersize <size>`**

  메모리 내 순환 버퍼의 크기를 MB(메가바이트) 단위로 설정합니다. 기본값은 256MB입니다.

- **`--clreventlevel <clreventlevel>`**

  내보낼 CLR 이벤트의 자세한 정도입니다.

- **`--clrevents <clrevents>`**

  내보낼 CLR 런타임 이벤트의 목록입니다.

- **`--format {Chromium|NetTrace|Speedscope}`**

  추적 파일 변환에 대한 출력 형식을 설정합니다. 기본값은 `NetTrace`입니다.

- **`-n, --name <name>`**

  추적을 수집할 프로세스의 이름입니다.

- **`-o|--output <trace-file-path>`**

  수집된 추적 데이터의 출력 경로입니다. 지정하지 않으면 기본값인 `trace.nettrace`로 설정됩니다.

- **`-p|--process-id <PID>`**

  추적을 수집할 프로세스 ID입니다.

- **`--profile <profile-name>`**

  일반적인 추적 시나리오를 간략하게 지정할 수 있는 미리 정의되어 명명된 공급자 구성 세트입니다.

- **`--providers <list-of-comma-separated-providers>`**

  사용하도록 설정할 `EventPipe` 공급자에 대한 쉼표로 구분된 목록입니다. 이러한 공급자는 `--profile <profile-name>`에서 암시하는 모든 공급자를 보완합니다. 특정 공급자에 대한 불일치 항목이 있는 경우 이 구성이 프로필의 암시적 구성보다 우선합니다.

  이 공급자 목록의 형식은 다음과 같습니다.

  - `Provider[,Provider]`
  - `Provider`의 형식: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`
  - `KeyValueArgs`의 형식: `[key1=value1][;key2=value2]`

- **`-- <command>`(.NET 5.0을 실행하는 대상 애플리케이션만 해당)**

  사용자는 컬렉션 구성 매개 변수 다음에 `--`와 명령을 차례로 추가하여 5.0 런타임 이상에서 .NET 애플리케이션을 시작할 수 있습니다. 이 옵션은 시작 성능 문제 또는 어셈블리 로더 및 바인더 오류와 같이 프로세스 초기에 발생하는 문제를 진단할 때 도움이 될 수 있습니다.

  > [!NOTE]
  > 이 옵션을 사용하면 도구에 다시 전달되는 첫 번째 .NET 5.0 프로세스가 모니터링됩니다. 즉, 명령에서 여러 .NET 애플리케이션을 시작하는 경우 첫 번째 앱만 수집합니다. 따라서 자체 포함 애플리케이션에서 이 옵션을 사용하거나 `dotnet exec <app.dll>` 옵션을 사용하는 것이 좋습니다.

## <a name="dotnet-trace-convert"></a>dotnet-trace convert

`nettrace` 추적을 대체 추적 분석 도구와 함께 사용할 대체 형식으로 변환합니다.

### <a name="synopsis"></a>개요

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a>인수

- **`<input-filename>`**

  변환할 입력 추적 파일입니다. 기본값은 *trace.nettrace* 입니다.

### <a name="options"></a>옵션

- **`--format <Chromium|NetTrace|Speedscope>`**

  추적 파일 변환에 대한 출력 형식을 설정합니다.

- **`-o|--output <output-filename>`**

  출력 파일 이름입니다. 대상 형식의 확장명이 추가됩니다.

## <a name="dotnet-trace-ps"></a>dotnet-trace ps

 추적을 수집할 수 있는 dotnet 프로세스를 나열합니다.

### <a name="synopsis"></a>개요

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>dotnet-trace list-profiles

각 프로필에 있는 공급자 및 필터에 대한 설명이 포함된 미리 작성된 추적 프로필을 나열합니다.

### <a name="synopsis"></a>개요

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>dotnet-trace로 추적 수집

`dotnet-trace`을(를) 사용하여 추적을 수집하는 방법:

- 추적을 수집할 .NET Core 애플리케이션의 PID(프로세스 식별자)를 확인해야 합니다.

  - 예를 들어, Windows에서 작업 관리자 또는 `tasklist` 명령을 사용할 수 있습니다.
  - 예를 들어, Linux에서는 `ps` 명령입니다.
  - [dotnet-trace ps](#dotnet-trace-ps)

- 다음 명령을 실행합니다.

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  위의 명령은 다음과 유사한 출력을 생성합니다.

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- `<Enter>` 키를 눌러 수집을 중지합니다. `dotnet-trace`을(를) 사용하면 *trace.nettrace* 파일의 이벤트 로깅이 종료됩니다.

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a>dotnet-trace를 사용하여 자식 애플리케이션을 시작하고 시작에서 추적 수집

> [!IMPORTANT]
> .NET 5.0 이상을 실행하는 앱에만 적용됩니다.

경우에 따라 시작에서 프로세스의 추적을 수집하는 것이 유용할 수 있습니다. .NET 5.0 이상을 실행하는 앱의 경우 dotnet-trace를 사용하여 이 작업을 수행할 수 있습니다.

그러면 `arg1` 및 `arg2`를 명령줄 인수로 사용하여 `hello.exe`가 시작되고 런타임 시작에서 추적을 수집합니다.

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

위의 명령은 다음과 유사한 출력을 생성합니다.

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

`<Enter>` 또는 `<Ctrl + C>` 키를 눌러 추적 수집을 중지할 수 있습니다. 그러면 `hello.exe`도 종료됩니다.

> [!NOTE]
> dotnet-trace를 통해 `hello.exe`를 시작하면 해당 입출력이 리디렉션되어 stdin/stdout과 상호 작용할 수 없습니다.
> Ctrl+C 또는 SIGTERM을 통해 도구를 종료하면 도구와 자식 프로세스가 모두 안전하게 종료됩니다.
> 자식 프로세스가 도구보다 먼저 종료되면 도구도 종료되고 추적을 안전하게 볼 수 있습니다.

## <a name="view-the-trace-captured-from-dotnet-trace"></a>dotnet-trace에서 캡처된 추적 보기

Windows에서는 분석을 위해 [PerfView](https://github.com/microsoft/perfview)에서 *.nettrace* 파일을 볼 수 있습니다. 다른 플랫폼에서 수집된 추적의 경우, 추적 파일을 Windows 머신으로 이동하여 PerfView에서 볼 수 있습니다.

Linux에서는 `dotnet-trace`의 출력 형식을 `speedscope`(으)로 변경하여 추적을 볼 수 있습니다. 출력 파일 형식은 `-f|--format` 옵션을 사용하여 변경할 수 있습니다. `-f speedscope`을(를) 사용하면 `dotnet-trace`에서 `speedscope` 파일을 생성합니다. `nettrace`(기본 옵션) 및 `speedscope` 중에서 선택할 수 있습니다. `Speedscope` 파일은 <https://www.speedscope.app>에서 열 수 있습니다.

> [!NOTE]
> .NET Core 런타임은 `nettrace` 형식으로 추적을 생성합니다. 추적이 완료된 후 추적이 speedscope(지정 된 경우)로 변환됩니다. 일부 변환으로 인해 데이터가 손실될 수 있으므로 원본 `nettrace` 파일이 변환된 파일과 함께 보존됩니다.

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a>dotnet-trace를 사용하여 시간 경과에 따라 카운터 값 사용

`dotnet-trace` 기능:

* 성능에 민감한 환경에서 기본 상태 모니터링을 위해 `EventCounter`을(를) 사용합니다. 예를 들어, 프로덕션 환경에 있습니다.
* 실시간으로 볼 필요가 없는 추적을 수집합니다.

예를 들어, 런타임 성능 카운터 값을 수집하려면 다음 명령을 사용합니다.

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

앞의 명령은 간단한 상태 모니터링을 위해 런타임 카운터에서 초당 한 번씩 보고하도록 지시합니다. `EventCounterIntervalSec=1`을 더 높은 값(예: 60)으로 바꾸면 카운터 데이터에서 세분성이 낮은 추적을 수집할 수 있습니다.

다음 명령은 앞의 명령보다 오버 헤드 및 추적 크기를 더 크게 줄입니다.

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

앞의 명령은 런타임 이벤트와 관리되는 스택 프로파일러를 사용하지 않도록 설정합니다.

## <a name="net-providers"></a>.NET 공급자

.NET Core 런타임은 다음과 같은 .NET 공급자를 지원합니다. .NET Core에서 동일한 키워드를 사용하여 `Event Tracing for Windows (ETW)` 및 `EventPipe` 추적을 모두 사용하도록 설정합니다.

| 공급자 이름                            | 정보 |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [런타임 공급자](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[CLR 런타임 키워드](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [런다운 공급자](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[CLR 런다운 키워드](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | 샘플 프로파일러를 사용하도록 설정합니다. |
