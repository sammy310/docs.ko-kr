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
# <a name="trace-for-performance-analysis-utility-dotnet-trace"></a>성능 분석 추적 유틸리티(`dotnet-trace`)

**이 문서의 적용 대상:** .NET Core 3.0 SDK 이상 버전

## <a name="installing-dotnet-trace"></a>`dotnet-trace` 설치

`dotnet-trace` [NuGet 패키지](https://www.nuget.org/packages/dotnet-trace)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a>개요

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>설명

`dotnet-trace` 도구는 네이티브 프로파일러 없이 실행 중인 프로세스의 .NET Core 추적을 수집할 수 있도록 지원하는 플랫폼 간 CLI 글로벌 도구입니다. .NET Core 런타임의 플랫폼 간 `EventPipe` 기술을 기반으로 하여 빌드되었습니다. `dotnet-trace`는 Windows, Linux 또는 macOS에서 동일한 환경을 제공합니다.

## <a name="options"></a>옵션

- **`--version`**

dotnet-counters 유틸리티의 버전을 표시합니다.

- **`-h|--help`**

명령줄 도움말을 표시합니다.

## <a name="commands"></a>명령

| 명령                                                     |
| ----------------------------------------------------------- |
| [dotnet-trace collect](#dotnet-trace-collect)               |
| [dotnet-trace convert](#dotnet-trace-convert)               |
| [dotnet-trace list-processes](#dotnet-trace-list-processes) |
| [dotnet-trace list-profiles](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a>dotnet-trace collect

실행 중인 프로세스에서 진단 추적을 수집합니다.

### <a name="synopsis"></a>개요

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a>옵션

- **`-p|--process-id <PID>`**

  추적을 수집하는 프로세스입니다.

- **`--buffersize <size>`**

  메모리 내 순환 버퍼의 크기를 MB(메가바이트) 단위로 설정합니다. 기본값은 256MB입니다.

- **`-o|--output <trace-file-path>`**

  수집된 추적 데이터의 출력 경로입니다. 지정하지 않으면 기본값인 `trace.nettrace`로 지정됩니다.

- **`--providers <list-of-comma-separated-providers>`**

  사용하도록 설정할 `EventPipe` 공급자에 대한 쉼표로 구분된 목록입니다. 이러한 공급자는 `--profile <profile-name>`에서 암시하는 모든 공급자를 보완합니다. 특정 공급자에 대한 불일치 항목이 있는 경우 여기의 구성이 프로필의 암시적 구성보다 우선합니다.

  이 공급자 목록의 형식은 다음과 같습니다.

  - `Provider[,Provider]`
  - `Provider`의 형식: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`
  - `KeyValueArgs`의 형식: `[key1=value1][;key2=value2]`

- **`--profile <profile-name>`**

  일반적인 추적 시나리오를 간략하게 지정할 수 있는 미리 정의되어 명명된 공급자 구성 세트입니다.

- **`--format <NetTrace|Speedscope>`**

  추적 파일 변환에 대한 출력 형식을 설정합니다.

## <a name="dotnet-trace-convert"></a>dotnet-trace convert

`nettrace` 추적을 대체 추적 분석 도구와 함께 사용할 대체 형식으로 변환합니다.

### <a name="synopsis"></a>개요

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a>인수

- **`<input-filename>`**

  변환할 입력 추적 파일입니다. 기본값은 *trace.nettrace*입니다.

### <a name="options"></a>옵션

- **`--format <NetTrace|Speedscope>`**

  추적 파일 변환에 대한 출력 형식을 설정합니다.

- **`-o|--output <output-filename>`**

  출력 파일 이름입니다. 대상 형식의 확장명이 추가됩니다.

## <a name="dotnet-trace-list-processes"></a>dotnet-trace list-processes

추적할 수 있는 dotnet 프로세스를 나열합니다.

### <a name="synopsis"></a>개요

```console
dotnet-trace list-processes [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>dotnet-trace list-profiles

각 프로필에 있는 공급자 및 필터에 대한 설명이 포함된 미리 작성된 추적 프로필을 나열합니다.

### <a name="synopsis"></a>개요

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>`dotnet-trace`를 사용하여 추적 수집

- `dotnet-trace`를 사용하여 추적을 수집하려면 먼저 추적을 수집할 .NET Core 애플리케이션의 PID(프로세스 식별자)를 확인해야 합니다.

  - Windows에는 작업 관리자 또는 `tasklist` 명령을 사용하는 것과 같은 옵션이 있습니다.
  - Linux에는 `ps` 명령을 사용하는 간단한 옵션이 있을 수 있습니다.

또한 [dotnet-trace list-processes](#dotnet-trace-list-processes) 명령을 사용하여 실행 중인 .NET Core 프로세스와 해당 PID를 확인할 수도 있습니다.

- 다음 명령을 실행합니다.

```console
> dotnet-trace collect --process-id <PID>

Press <Enter> to exit...
Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
```

- 마지막으로 `<Enter>` 키를 눌러 수집을 중지합니다. 그러면 `dotnet-trace`에서 `trace.nettrace` 파일에 대한 이벤트 로깅을 완료합니다.

## <a name="viewing-the-trace-captured-from-dotnet-trace"></a>`dotnet-trace`에서 캡처한 추적 보기

Windows에서는 ETW 또는 LTTng를 사용하여 수집된 추적과 마찬가지로 분석을 위해 [PerfView](https://github.com/microsoft/perfview)에서 `.nettrace` 파일을 볼 수 있습니다. Linux에서 수집된 추적의 경우 추적을 Windows 머신으로 이동하여 PerfView에서 볼 수 있습니다.

또한 `dotnet-trace`의 출력 형식을 `speedscope`로 변경하여 Linux 머신에서 추적을 볼 수도 있습니다. `-f|--format` 옵션을 사용하여 출력 파일 형식을 변경할 수 있습니다. 그러면 `-f speedscope`에서 `dotnet-trace`를 수행하여 `speedscope` 파일을 생성합니다. 현재 `nettrace`(기본 옵션) 및 `speedscope` 중에서 선택할 수 있습니다. `Speedscope` 파일은 <https://www.speedscope.app>에서 열 수 있습니다.

> [!NOTE]
> .NET Core 런타임은 추적을 `nettrace` 형식으로 생성하며, 추적이 완료된 후에는 speedscope로 변환됩니다(지정된 경우). 일부 변환으로 인해 데이터가 손실될 수 있으므로 원본 `nettrace` 파일이 변환된 파일과 함께 보존됩니다.

## <a name="using-dotnet-trace-to-collect-counter-values-over-time"></a>`dotnet-trace`를 사용하여 시간 경과에 따른 카운터 값 수집

프로덕션 환경과 같은 성능에 민감한 설정에서 `EventCounter`를 기본 상태 모니터링에 사용하려고 하고 추적을 실시간으로 감시하지 않고 수집하려는 경우에도 `dotnet-trace`를 사용하여 이를 수행할 수 있습니다.

예를 들어 런타임 성능 카운터 값을 수집하려면 다음 명령을 사용할 수 있습니다.

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

이 명령은 간단한 상태 모니터링을 위해 런타임 카운터에서 초당 한 번씩 보고하도록 지시합니다. `EventCounterIntervalSec=1`을 더 높은 값(예: 60)으로 바꾸면 카운터 데이터에서 세분성이 낮은 추적을 수집할 수 있습니다.

오버헤드(및 추적 크기)를 더 줄이기 위해 런타임 이벤트를 사용하지 않도록 설정하려면 다음 명령을 사용하여 런타임 이벤트 및 관리형 스택 프로파일러를 사용하지 않도록 설정할 수 있습니다.

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

## <a name="net-providers"></a>.NET 공급자

.NET Core 런타임은 다음과 같은 .NET 공급자를 지원합니다. .NET Core에서 동일한 키워드를 사용하여 `Event Tracing for Windows (ETW)` 및 `EventPipe` 추적을 모두 사용하도록 설정합니다.

| 공급자 이름                            | 정보 |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [런타임 공급자](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[CLR 런타임 키워드](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [런다운 공급자](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[CLR 런다운 키워드](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | 샘플 프로파일러를 사용하도록 설정합니다. |
