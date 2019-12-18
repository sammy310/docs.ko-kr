---
title: 디버깅 프로파일링 구성 설정
description: .NET Core 앱의 디버깅 및 프로파일링을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998860"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a>디버깅 및 프로파일링을 위한 런타임 구성 옵션

## <a name="enable-diagnostics"></a>진단 사용

- 디버거, 프로파일러 및 EventPipe 진단이 사용 또는 사용하지 않도록 설정되는지 여부를 구성합니다.
- 기본값: 사용(`1`).

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | 해당 사항 없음 | 해당 사항 없음 |
| **환경 변수** | `COMPlus_EnableDiagnostics` | `1` - 사용<br/>`0` - 사용 안 함 |

## <a name="enable-profiling"></a>프로파일링 사용

- 현재 실행 중인 프로세스에서 프로파일링이 사용하도록 설정되는지 여부를 구성합니다.
- 기본값: 사용 안 함(`0`).

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | 해당 사항 없음 | 해당 사항 없음 |
| **환경 변수** | `CORECLR_ENABLE_PROFILING` | `0` - 사용 안 함<br/>`1` - 사용 |

## <a name="profiler-guid"></a>프로파일러 GUID

- 현재 실행 중인 프로세스에 로드할 프로파일러의 GUID를 지정합니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | 해당 사항 없음 | 해당 사항 없음 |
| **환경 변수** | `CORECLR_PROFILER` | *string-guid* |

## <a name="profiler-location"></a>프로파일러 위치

- 현재 실행 중인 프로세스(또는 32비트 또는 64비트 프로세스)에 로드할 프로파일러 DLL의 경로를 지정합니다.
- 변수가 둘 이상 설정된 경우, 비트 수 관련 변수가 우선적으로 적용됩니다. 이들 변수는 프로파일러의 어느 비트 수를 로드할지 지정합니다.
- 자세한 내용은 [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md)(프로파일러 라이브러리 찾기)를 참조하세요.

| | 설정 이름 | 값 |
| - | - | - |
| **환경 변수** | `CORECLR_PROFILER_PATH` | *string-path* |
| **환경 변수** | `CORECLR_PROFILER_PATH_32` | *string-path* |
| **환경 변수** | `CORECLR_PROFILER_PATH_64` | *string-path* |

## <a name="write-perf-map"></a>perf 맵 작성

- Linux 시스템에서 */tmp/perf-$pid.map*의 작성을 사용하거나 사용하지 않도록 설정합니다.
- 기본값: 사용 안 함(`0`).

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | 해당 사항 없음 | 해당 사항 없음 |
| **환경 변수** | `COMPlus_PerfMapEnabled` | `0` - 사용 안 함<br/>`1` - 사용 |

## <a name="perf-log-markers"></a>Perf 로그 마커

- `COMPlus_PerfMapEnabled`가 `1`로 설정된 경우, perf 로그에서 마커로 사용되거나 무시될 지정된 신호를 사용하거나 사용하지 않도록 설정합니다.
- 기본값: 사용 안 함(`0`).

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | 해당 사항 없음 | 해당 사항 없음 |
| **환경 변수** | `COMPlus_PerfMapIgnoreSignal` | `0` - 사용 안 함<br/>`1` - 사용 |
