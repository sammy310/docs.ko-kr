---
title: dotnet-trace 진단 도구 - .NET CLI
description: .NET EventPipe를 사용하여 네이티브 프로파일러 없이 실행 중인 프로세스의 .NET 추적을 수집하기 위해 dotnet-trace CLI 도구를 설치하고 사용하는 방법을 알아봅니다.
ms.date: 11/17/2020
ms.openlocfilehash: 93698882e94f58eda84abebc277e1eacfe22a3da
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189705"
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

> [!NOTE]
> x86 앱에서 `dotnet-trace`를 사용하려면 해당하는 x86 버전의 도구가 필요합니다.

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
    [-n, --name <name>] [--diagnostic-port] [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a>옵션

- **`--buffersize <size>`**

  메모리 내 순환 버퍼의 크기를 MB(메가바이트) 단위로 설정합니다. 기본값은 256MB입니다.

- **`--clreventlevel <clreventlevel>`**

  내보낼 CLR 이벤트의 자세한 정도입니다.

- **`--clrevents <clrevents>`**

  `+` 서명으로 구분할 수 있는 CLR 런타임 공급자 키워드 목록입니다. 16진수 값이 아닌 문자열 별칭을 통해 이벤트 키워드를 지정할 수 있도록 하는 간단한 매핑입니다. 예를 들어 `dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:3:4`는 `dotnet-trace collect --clrevents gc+gchandle --clreventlevel informational`과 동일한 이벤트 세트를 요청합니다. 다음 표에서는 사용 가능한 키워드의 목록을 보여 줍니다.

  | 키워드 문자열 별칭 | 키워드 16진수 값 |
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

  [.NET 런타임 공급자 참조 설명서](../../fundamentals/diagnostics/runtime-events.md)에서 CLR 공급자에 관해 자세히 알아볼 수 있습니다.

- **`--format {Chromium|NetTrace|Speedscope}`**

  추적 파일 변환에 대한 출력 형식을 설정합니다. 기본값은 `NetTrace`입니다.

- **`-n, --name <name>`**

  추적을 수집할 프로세스의 이름입니다.

- **`--diagnostic-port <path-to-port>`**

  만들 진단 포트의 이름입니다. 이 옵션을 사용하여 앱 시작부터 추적을 수집하는 방법을 알아보려면 [진단 포트를 사용하여 앱 시작부터 추적 수집](#use-diagnostic-port-to-collect-a-trace-from-app-startup)을 참조하세요.

- **`-o|--output <trace-file-path>`**

  수집된 추적 데이터의 출력 경로입니다. 지정하지 않으면 기본값인 `trace.nettrace`로 설정됩니다.

- **`-p|--process-id <PID>`**

  추적을 수집할 프로세스 ID입니다.

- **`--profile <profile-name>`**

  일반적인 추적 시나리오를 간략하게 지정할 수 있는 미리 정의되어 명명된 공급자 구성 세트입니다. 다음 프로필을 사용할 수 있습니다.

 | 프로필 | 설명 |
 |---------|-------------|
 |`cpu-sampling`|CPU 사용량 및 일반 .NET 런타임 정보를 추적하는 데 유용합니다. 이 옵션은 프로필 또는 공급자가 지정되지 않은 경우 기본 옵션입니다.|
 |`gc-verbose`|GC 컬렉션을 추적하고 개체 할당을 샘플링합니다.|
 |`gc-collect`|매우 낮은 오버헤드로 GC 컬렉션을 추적합니다.|

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

> [!NOTE]
> 대규모 애플리케이션에서는 추적을 중지하는 데 오래 걸릴 수 있습니다(최대 몇 분). 런타임에서는 추적에 캡처된 모든 관리 코드의 형식 캐시를 전송해야 합니다.

> [!NOTE]
> Linux 및 macOS에서 해당 명령은 대상 애플리케이션 및 `dotnet-trace`가 동일한 `TMPDIR` 환경 변수를 공유할 것으로 예상합니다. 그러지 않으면 명령 시간이 초과됩니다.

> [!NOTE]
> `dotnet-trace`를 사용하여 추적을 수집하려면 대상 프로세스를 실행하는 사용자와 동일한 사용자 또는 루트로 실행해야 합니다. 그러지 않으면 도구는 대상 프로세스와 연결을 설정하지 못합니다.

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

> [!NOTE]
> `nettrace` 파일을 `chromium` 또는 `speedscope` 파일로 변환하면 되돌릴 수 없습니다. `speedscope` 및 `chromium` 파일에는 `nettrace` 파일을 다시 생성하는 데 필요한 정보가 일부 포함되어 있지 않습니다. 그러나 `convert` 명령은 원래 `nettrace` 파일을 유지하므로 나중에 파일을 열 계획인 경우 삭제하지 마세요.

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

## <a name="use-diagnostic-port-to-collect-a-trace-from-app-startup"></a>진단 포트를 사용하여 앱 시작부터 추적 수집

  > [!IMPORTANT]
  > .NET 5.0 이상을 실행하는 앱에만 적용됩니다.

진단 포트는 .NET 5에서 추가된 새로운 런타임 기능으로, 앱 시작부터 추적을 시작하는 데 사용할 수 있습니다. `dotnet-trace`를 사용하여 이렇게 하려면 위의 예제에 설명된 대로 `dotnet-trace collect -- <command>`를 사용하거나 `--diagnostic-port` 옵션을 사용할 수 있습니다.

`dotnet-trace <collect|monitor> -- <command>`를 사용하여 애플리케이션을 자식 프로세스로 실행하는 것이 시작부터 빠르게 추적하는 가장 간단한 방법입니다.

하지만 추적되는 앱의 수명을 더 세부적으로 제어하거나(예: 처음 10분간만 앱을 모니터링하고 실행 계속) CLI를 사용하여 앱을 조작해야 하는 경우에는 `--diagnostic-port` 옵션을 사용하여 모니터링되는 대상 앱과 `dotnet-trace`를 모두 제어할 수 있습니다.

1. 아래 명령은 `dotnet-trace`에서 `myport.sock`라는 진단 소켓을 만들고 연결을 대기하게 합니다.

    > ```dotnet-cli
    > dotnet-trace collect --diagnostic-port myport.sock
    > ```

    출력:

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. 별도의 콘솔에서 `DOTNET_DiagnosticPorts` 환경 변수를 `dotnet-trace` 출력의 값으로 설정하고 대상 애플리케이션을 시작합니다.

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    그러면 `dotnet-trace`에서 `my-dotnet-app` 추적을 시작할 수 있습니다.

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > `dotnet run`을 사용하여 앱을 시작하면 문제가 될 수 있는데, dotnet CLI가 앱이 아닌 여러 자식 프로세스를 생성할 수 있고 해당 프로세스가 앱보다 먼저 `dotnet-trace`에 연결하여 앱이 런타임에 일시 중단될 수 있기 때문입니다. 앱의 자체 포함 버전을 직접 사용하거나 `dotnet exec`를 사용하여 애플리케이션을 시작하는 것이 좋습니다.

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

## <a name="use-rsp-file-to-avoid-typing-long-commands"></a>긴 명령을 입력하지 않기 위해 .rsp 파일 사용

전달할 인수를 포함하는 `.rsp` 파일을 사용하여 `dotnet-trace`를 시작할 수 있습니다. 이렇게 하면 긴 인수가 필요한 공급자를 사용하도록 설정하거나 문자를 없애는 셸 환경을 사용할 때 유용할 수 있습니다.

예를 들어 다음 공급자는 추적할 때마다 입력하는 일이 번거로울 수 있습니다.

```cmd
dotnet-trace collect --providers Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

또한 이전 예제에서는 `"`가 인수의 일부로 포함되어 있습니다. 따옴표는 각 셸에서 동일하게 처리되지 않으므로 여러 셸을 사용할 때 다양한 문제가 발생할 수 있습니다. 예를 들어 `zsh`에서 입력하는 명령과 `cmd`의 명령이 다릅니다.

해당 명령을 매번 입력하는 대신 다음 텍스트를 `myprofile.rsp`라는 파일에 저장할 수 있습니다.

```txt
--providers
Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

`myprofile.rsp`를 저장했으면 다음 명령을 통해 이 구성을 사용하여 `dotnet-trace`를 시작할 수 있습니다.

```bash
dotnet-trace @myprofile.rsp
```

## <a name="see-also"></a>참조

- [.NET의 잘 알려진 이벤트 공급자](well-known-event-providers.md)
