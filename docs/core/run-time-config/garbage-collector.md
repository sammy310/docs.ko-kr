---
title: 가비지 수집기 구성 설정
description: 가비지 수집기가 .NET Core 앱의 메모리를 관리하는 방식을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/13/2019
ms.topic: reference
ms.openlocfilehash: e7f6877a3cbc7f28776a93b9126f4b64026487fa
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998818"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a>가비지 수집을 위한 런타임 구성 옵션

이 페이지에는 런타임에 변경할 수 있는 가비지 수집기(GC) 설정에 관한 정보가 포함되어 있습니다. 실행 중인 앱의 최고 성능을 달성하려는 경우 이러한 설정을 사용해 보시기 바랍니다. 그러나 기본값으로도 일반적인 상황에 있는 대부분의 애플리케이션에서 최적의 성능을 얻을 수 있습니다.

이 페이지에서는 설정이 그룹별로 정리되어 있습니다. 각 그룹에 포함된 설정은 특정 결과를 얻기 위해 서로 함께 사용되는 경우가 많습니다.

> [!NOTE]
>
> - 이러한 설정은 앱이 실행 중일 때 동적으로 변경될 수도 있으므로 사용자가 설정한 런타임 설정이 재정의될 수 있습니다.
> - [대기 시간 수준](../../standard/garbage-collection/latency.md)과 같은 일부 설정은 디자인 타임에 API를 통해서만 설정됩니다. 이러한 설정은 이 페이지에 나와 있지 않습니다.
> - 숫자 값의 경우, *runtimeconfig.json* 파일에 있는 설정에는 10진수 표기법을 사용하고, 환경 변수 설정에는 16진수 표기법을 사용합니다.

## <a name="flavors-of-garbage-collection"></a>가비지 수집 버전

가비지 수집의 2가지 주요 버전은 워크스테이션 GC와 서버 GC입니다. 둘 사이의 차이점에 대한 자세한 내용은 [가비지 수집 기본 사항](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)을 참조하세요.

가비지 수집의 하위 버전은 백그라운드와 비동시입니다.

다음 설정을 사용하여 가비지 수집의 버전을 선택합니다.

### <a name="systemgcservercomplus_gcserver"></a>System.GC.Server/COMPlus_gcServer

- 애플리케이션이 워크스테이션 가비지 수집과 서버 가비지 수집 중 어느 것을 사용하는지 구성합니다.
- 기본값: 워크스테이션 가비지 수집(`false`).

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.Server` | `false` - 워크스테이션<br/>`true` - 서버 | .NET Core 1.0 |
| **환경 변수** | `COMPlus_gcServer` | `0` - 워크스테이션<br/>`1` - 서버 | .NET Core 1.0 |
| **.NET Framework의 app.config** | [GCServer](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | `false` - 워크스테이션<br/>`true` - 서버 |  |

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a>System.GC.Concurrent/COMPlus_gcConcurrent

- 백그라운드(동시) 가비지 수집이 사용하도록 설정되었는지 여부를 구성합니다.
- 기본값: 사용(`true`).
- 자세한 내용은 [백그라운드 가비지 수집](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) 및 [백그라운드 서버 가비지 수집](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection)을 참조하세요.

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.Concurrent` | `true` - 백그라운드 GC<br/>`false` - 비동시 GC | .NET Core 1.0 |
| **환경 변수** | `COMPlus_gcConcurrent` | `true` - 백그라운드 GC<br/>`false` - 비동시 GC | .NET Core 1.0 |
| **.NET Framework의 app.config** | [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | `true` - 백그라운드 GC<br/>`false` - 비동시 GC |  |

## <a name="manage-resource-usage"></a>리소스 사용량 관리

이 섹션에서 설명하는 설정은 가비지 수집기의 메모리 및 프로세서 사용량을 관리하는 데 사용합니다.

이들 중 일부 설정에 대한 자세한 내용은 [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)(워크스테이션 및 서버 GC의 중간 지점) 블로그 게시물을 참조하세요.

### <a name="systemgcheapcountcomplus_gcheapcount"></a>System.GC.HeapCount/COMPlus_GCHeapCount

- 가비지 수집기가 생성하는 힙의 개수를 제한합니다.
- 서버 가비지 수집(GC)에만 적용됩니다.
- GC 프로세서 선호도가 사용하도록 설정된 경우(기본값), 힙 개수 설정은 `n` GC 힙/스레드의 선호도를 처음 `n`개의 프로세서로 지정합니다. (정확히 어떤 프로세서의 선호도를 지정하려는지 지정하려면 선호도 지정 마스크 또는 선호도 지정 범위 설정을 사용하세요.)
- GC 프로세서 선호도를 사용하지 않도록 설정하는 경우, 이 설정으로 GC 힙 개수가 제한됩니다.
- 자세한 내용은 [GCHeapCount 설명](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)을 참조하세요.

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapCount` | *10진수 값* | .NET Core 3.0 |
| **환경 변수** | `COMPlus_GCHeapCount` | *16진수 값* | .NET Core 3.0 |
| **.NET Framework의 app.config** | [GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | *10진수 값* | 4.6.2 |

> [!TIP]
> *runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다. 옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다. 예를 들어, 힙의 개수를 16으로 제한하려면 JSON 파일의 경우 값을 16으로 지정하고 환경 변수의 경우 값을 10으로 지정합니다.

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a>System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask

- 가비지 수집기 스레드가 사용할 정확한 프로세서를 지정합니다.
- `System.GC.NoAffinitize`를 `true`로 설정하여 프로세서 선호도를 사용하지 않도록 설정한 경우, 이 설정은 무시됩니다.
- 서버 가비지 수집(GC)에만 적용됩니다.
- 값은 프로세스에서 사용할 수 있는 프로세서를 정의하는 비트 마스크입니다. 예를 들어, 10진수 값 1023(환경 변수를 사용하는 경우에는 16진수 값 3FF)은 이진 표기법으로 0011 1111 1111입니다. 이는 처음 10개의 프로세서를 사용하도록 지정합니다. 다음 10개의 프로세서, 즉 프로세서 10~19를 지정하려면 10진수 값 1047552(또는 16진수 값 FFC00)을 지정합니다. 이는 이진수 값 1111 1111 1100 0000 0000과 같습니다.

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapAffinitizeMask` | *10진수 값* | .NET Core 3.0 |
| **환경 변수** | `COMPlus_GCHeapAffinitizeMask` | *16진수 값* | .NET Core 3.0 |
| **.NET Framework의 app.config** | [GCHeapAffinitizeMask](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | *10진수 값* | 4.6.2 |

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a>System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges

- 가비지 수집기 스레드가 사용할 프로세서 목록을 지정합니다.
- 이 설정은 64개가 넘는 프로세서를 지정할 수 있다는 점을 제외하면 `System.GC.HeapAffinitizeMask`와 비슷합니다.
- Windows 운영 체제에서는 번호 또는 범위 앞에 해당하는 [CPU 그룹](/windows/win32/procthread/processor-groups)(예: “0:1-10,0:12,1:50-52,1:70”)을 붙입니다.
- `System.GC.NoAffinitize`를 `true`로 설정하여 프로세서 선호도를 사용하지 않도록 설정한 경우, 이 설정은 무시됩니다.
- 서버 가비지 수집(GC)에만 적용됩니다.
- 자세한 내용은 Maoni Stephens의 블로그에서 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)(CPU가 64개가 넘는 머신에서 GC를 위한 CPU 구성 개선하기) 게시물을 참조하세요.

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.GCHeapAffinitizeRanges` | 쉼표로 구분된 프로세서 번호 또는 프로세서 번호 범위 목록.<br/>Unix 예: “1-10,12,50-52,70”<br/>Windows 예: “0:1-10,0:12,1:50-52,1:70” | .NET Core 3.0 |
| **환경 변수** | `COMPlus_GCHeapAffinitizeRanges` | 쉼표로 구분된 프로세서 번호 또는 프로세서 번호 범위 목록.<br/>Unix 예: “1-10,12,50-52,70”<br/>Windows 예: “0:1-10,0:12,1:50-52,1:70” | .NET Core 3.0 |

### <a name="complus_gccpugroup"></a>COMPlus_GCCpuGroup

- 가비지 수집기가 [CPU 그룹](/windows/win32/procthread/processor-groups)을 사용하는지 여부는 구성합니다.

  64비트 Windows 컴퓨터에 여러 개의 CPU 그룹이 있는 경우, 다시 말해서 64개가 넘는 프로세서가 있는 경우, 이 요소를 사용하도록 설정하면 가비지 수집이 모든 CPU 그룹으로 확장됩니다. 가비지 수집기는 모든 코어를 사용하여 힙을 만들고 분산합니다.

- 64비트 Windows 운영 체제의 서버 가비지 수집(GC)에만 적용됩니다.
- 기본값: 사용 안 함(`0`).
- 자세한 내용은 Maoni Stephens의 블로그에서 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)(CPU가 64개가 넘는 머신에서 GC를 위한 CPU 구성 개선하기) 게시물을 참조하세요.

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | 해당 사항 없음 | 해당 사항 없음 | 해당 사항 없음 |
| **환경 변수** | `COMPlus_GCCpuGroup` | `0` - 사용 안 함<br/>`1` - 사용 | .NET Core 1.0 |
| **.NET Framework의 app.config** | [GCCpuGroup](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | `false` - 사용 안 함<br/>`true` - 사용 |  |

> [!NOTE]
> 모든 CPU 그룹의 스레드 풀에서도 스레드를 분산하도록 CLR(공용 언어 런타임)을 구성하려면 [Thread_UseAllCpuGroups 요소](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) 옵션을 사용하도록 설정합니다. .NET Core 앱의 경우, `COMPlus_Thread_UseAllCpuGroups` 환경 변수의 값을 `1`로 설정하여 이 옵션을 사용하도록 설정할 수 있습니다.

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a>System.GC.NoAffinitize/COMPlus_GCNoAffinitize

- 가비지 수집 스레드가 프로세서를 *선호*하도록 지정할지 여부를 지정합니다. GC 스레드의 선호도를 지정한다는 것은 특정 CPU에서만 실행할 수 있음을 의미합니다. 각 GC 스레드에 대해 힙이 생성됩니다.
- 서버 가비지 수집(GC)에만 적용됩니다.
- 기본값: 가비지 수집 스레드가 프로세서를 선호하도록 지정(`false`).

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.NoAffinitize` | `false` - 선호<br/>`true` - 선호 안 함 | .NET Core 3.0 |
| **환경 변수** | `COMPlus_GCNoAffinitize` | `0` - 선호<br/>`1` - 선호 안 함 | .NET Core 3.0 |
| **.NET Framework의 app.config** | [GCNoAffinitize](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | `false` - 선호<br/>`true` - 선호 안 함 | 4.6.2 |

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a>System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit

- GC 힙 및 GC 기록의 최대 커밋 크기를 바이트 단위로 지정합니다.

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimit` | *10진수 값* | .NET Core 3.0 |
| **환경 변수** | `COMPlus_GCHeapHardLimit` | *16진수 값* | .NET Core 3.0 |

> [!TIP]
> *runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다. 옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다. 예를 들어, 힙의 하드 한도를 80,000바이트로 지정하려면 JSON 파일의 경우 값을 80000으로 지정하고 환경 변수의 경우 값을 13880으로 지정합니다.

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a>System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent

- GC 힙의 사용량을 총 메모리의 백분율로 지정합니다.

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitPercent` | *10진수 값* | .NET Core 3.0 |
| **환경 변수** | `COMPlus_GCHeapHardLimitPercent` | *16진수 값* | .NET Core 3.0 |

> [!TIP]
> *runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다. 옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다. 예를 들어, 힙의 사용량을 30%로 제한하려면 JSON 파일의 경우 값을 30으로 지정하고 환경 변수의 경우 값을 1E로 지정합니다.

### <a name="systemgcretainvmcomplus_gcretainvm"></a>System.GC.RetainVM/COMPlus_GCRetainVM

- 삭제해야 할 세그먼트를 나중에 사용할 수 있도록 대기 목록에 둘지 아니면 해제하여 운영 체제(OS)로 돌려보낼지를 구성합니다.
- 기본값: 세그먼트를 해제하여 운영 체제로 돌려보냅니다(`false`).

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.RetainVM` | `false` - OS로 해제<br/>`true` - 대기 목록에 두기| .NET Core 1.0 |
| **환경 변수** | `COMPlus_GCRetainVM` | `0` - OS로 해제<br/>`1` - 대기 목록에 두기 | .NET Core 1.0 |

## <a name="large-pages"></a>큰 페이지

### <a name="complus_gclargepages"></a>COMPlus_GCLargePages

- 힙의 하드 한도가 설정된 경우 큰 페이지를 사용할지 여부를 지정합니다.
- 기본값: 사용 안 함(`0`).
- 이것은 실험적인 설정입니다.

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | 해당 사항 없음 | 해당 사항 없음 | 해당 사항 없음 |
| **환경 변수** | `COMPlus_GCLargePages` | `0` - 사용 안 함<br/>`1` - 사용 | .NET Core 3.0 |

## <a name="large-objects"></a>큰 개체

### <a name="complus_gcallowverylargeobjects"></a>COMPlus_gcAllowVeryLargeObjects

- 64비트 플랫폼에서 총 크기가 2기가바이트(GB)보다 큰 배열에 대한 가비지 수집기 지원을 구성합니다.
- 기본값: 사용(`1`).
- 이 옵션은 이후 버전의 .NET에서 더 이상 사용되지 않을 수 있습니다.

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | 해당 사항 없음 | 해당 사항 없음 | 해당 사항 없음 |
| **환경 변수** | `COMPlus_gcAllowVeryLargeObjects` | `1` - 사용<br/> `0` - 사용 안 함 | .NET Core 1.0 |
| **.NET Framework의 app.config** | [gcAllowVeryLargeObjects](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | `1` - 사용<br/> `0` - 사용 안 함 | .NET Framework 4.5 |

## <a name="large-object-heap-threshold"></a>큰 개체 힙 임계값

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a>System.GC.LOHThreshold/COMPlus_GCLOHThreshold

- 개체가 큰 개체 힙(LOH)으로 이동되도록 하는 임계값 크기를 바이트 단위로 지정합니다.
- 기본 임계값은 85,000바이트입니다.
- 사용자가 지정하는 값은 기본 임계값보다 커야 합니다.

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.LOHThreshold` | *10진수 값* | .NET Core 1.0 |
| **환경 변수** | `COMPlus_GCLOHThreshold` | *16진수 값* | .NET Core 1.0 |
| **.NET Framework의 app.config** | [GCLOHThreshold](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | *10진수 값* | .NET Framework 4.8 |

> [!TIP]
> *runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다. 옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다. 예를 들어, 임계값 크기를 120,000바이트로 설정하려면 JSON 파일의 경우 값을 120000으로 지정하고 환경 변수의 경우 값을 1D4C0으로 지정합니다.

## <a name="standalone-gc"></a>독립 실행형 GC

### <a name="complus_gcname"></a>COMPlus_GCName

- 런타임이 로드하려는 가비지 수집기를 포함하는 라이브러리의 경로를 지정합니다.
- 자세한 내용은 [Standalone GC loader design](https://github.com/dotnet/coreclr/blob/master/Documentation/design-docs/standalone-gc-loading.md)(독립 실행형 GC 로더 설계)을 참조하세요.

| | 설정 이름 | 값 | 도입된 버전 |
| - | - | - | - |
| **runtimeconfig.json** | 해당 사항 없음 | 해당 사항 없음 | 해당 사항 없음 |
| **환경 변수** | `COMPlus_GCName` | *string_path* | .NET Core 2.0 |
