---
title: 높은 CPU 사용량 디버그 - .NET 코어
description: .NET Core의 높은 CPU 사용량을 디버깅하는 과정을 안내하는 자습서입니다.
ms.topic: tutorial
ms.date: 07/20/2020
ms.openlocfilehash: 91f31f77b54398d2f9816890338955bc9b0852e4
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437834"
---
# <a name="debug-high-cpu-usage-in-net-core"></a>.NET 코어에서 높은 CPU 사용량 디버그

**이 문서의 적용 대상: ✔️** .NET Core 3.1. SDK 이상 버전

이 자습서에서는 과도한 CPU 사용량 시나리오를 디버그하는 방법을 알아봅니다. 제공된 예제 [ASP.NET Core 웹앱](/samples/dotnet/samples/diagnostic-scenarios) 소스 코드 리포지토리를 사용하면 교착 상태를 의도적으로 초래할 수 있습니다. 엔드포인트에서 중단 및 스레드 누적이 발생합니다. 다양한 도구를 사용하여 진단 데이터의 몇 가지 주요 부분으로 이 시나리오를 진단하는 방법을 알아봅니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
>
> - 높은 CPU 사용량 조사
> - [dotnet-counters](dotnet-counters.md)를 사용하여 CPU 사용량 확인
> - 추적 생성을 위해 [dotnet-trace](dotnet-trace.md) 사용
> - PerfView에서 성능 프로파일링
> - 과도한 CPU 사용량 진단 및 해결

## <a name="prerequisites"></a>사전 요구 사항

이 자습서에서는 다음을 사용합니다.

- [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) 이상 버전.
- 시나리오를 트리거하는 [샘플 디버그 대상](/samples/dotnet/samples/diagnostic-scenarios).
- 프로세스를 나열하고 프로필을 생성하는 [dotnet-trace](dotnet-trace.md).
- CPU 사용량을 모니터링하는 [dotnet-counters](dotnet-counters.md).

## <a name="cpu-counters"></a>CPU 카운터

진단 데이터를 수집하기 전에 높은 CPU 판단 기준을 관찰해야 합니다. 프로젝트 루트 디렉터리에서 다음 명령을 사용하여 [샘플 애플리케이션](/samples/dotnet/samples/diagnostic-scenarios)을 실행합니다.

```dotnetcli
dotnet run
```

프로세스 ID를 찾으려면 다음 명령을 사용합니다.

```dotnetcli
dotnet-trace ps
```

명령 출력에서 프로세스 ID를 기록해 둡니다. 기존 프로세스 ID는 `22884`였지만 사용자의 프로세스 ID는 다를 것입니다. 현재 CPU 사용량을 확인하려면 [dotnet-counters](dotnet-counters.md) 도구 명령을 사용합니다.

```dotnetcli
dotnet-counters monitor --refresh-interval 1 -p 22884
```

`refresh-interval`은 카운터 폴링 CPU 값 사이의 시간(초)입니다. 출력은 다음과 같은 형태가 됩니다.

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    % Time in GC since last GC (%)                         0
    Allocation Rate / 1 sec (B)                            0
    CPU Usage (%)                                          0
    Exception Count / 1 sec                                0
    GC Heap Size (MB)                                      4
    Gen 0 GC Count / 60 sec                                0
    Gen 0 Size (B)                                         0
    Gen 1 GC Count / 60 sec                                0
    Gen 1 Size (B)                                         0
    Gen 2 GC Count / 60 sec                                0
    Gen 2 Size (B)                                         0
    LOH Size (B)                                           0
    Monitor Lock Contention Count / 1 sec                  0
    Number of Active Timers                                1
    Number of Assemblies Loaded                          140
    ThreadPool Completed Work Item Count / 1 sec           3
    ThreadPool Queue Length                                0
    ThreadPool Thread Count                                7
    Working Set (MB)                                      63
```

웹앱을 실행하면 시작 직후에 CPU가 전혀 소비되지 않고 `0%`에 보고됩니다. 경로 매개 변수로 `60000`을 사용하여 `api/diagscenario/highcpu` 경로로 이동합니다.

`https://localhost:5001/api/diagscenario/highcpu/60000`

이제 [dotnet-counters](dotnet-counters.md) 명령을 다시 실행합니다. `cpu-usage`만 모니터링하려면 `System.Runtime[cpu-usage]`을 명령의 일부로 지정합니다.

```dotnetcli
dotnet-counters monitor --counters System.Runtime[cpu-usage] -p 22884 --refresh-interval 1
```

아래와 같이 CPU 사용량이 증가하는 것을 볼 수 있습니다.

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    CPU Usage (%)                                         25
```

요청 기간 동안 CPU 사용량은 약 25%입니다. 호스트 컴퓨터에 따라 CPU 사용량은 다양할 것입니다.

> [!TIP]
> 더 높은 CPU 사용량을 시각화하기 위해 여러 브라우저 탭에서 이 엔드포인트를 동시에 실행할 수 있습니다.

이 시점에서는 CPU가 예상보다 높게 실행되고 있다고 봐도 무방합니다.

## <a name="trace-generation"></a>추적 생성

저속 요청을 분석할 때 코드가 수행하는 작업에 대한 정보를 제공할 수 있는 진단 도구가 필요합니다. 일반적으로 프로파일러를 선택하며, 선택할 수 있는 다양한 프로파일러 옵션이 있습니다.

### <a name="linux"></a>[Linux](#tab/linux)

`perf` 도구를 사용하여 .NET Core 앱 프로필을 생성할 수 있습니다. [샘플 디버그 대상](/samples/dotnet/samples/diagnostic-scenarios)의 이전 인스턴스를 종료합니다.

`COMPlus_PerfMapEnabled` 환경 변수를 설정하여 .NET Core 앱이 `/tmp` 디렉터리에 `map` 파일을 만들도록 합니다. 이 `map` 파일은 `perf`에서 CPU 주소를 이름별로 JIT 생성 함수에 매핑하는 데 사용됩니다. 자세한 내용은 [perf 맵 작성](../run-time-config/debugging-profiling.md#write-perf-map)을 참조하세요.

동일한 터미널 세션에서 [샘플 디버그 대상](/samples/dotnet/samples/diagnostic-scenarios)을 실행합니다.

```dotnetcli
export COMPlus_PerfMapEnabled=1
dotnet run
```

높은 CPU API 엔드포인트(`https://localhost:5001/api/diagscenario/highcpu/60000`)를 다시 실행합니다. 1분 요청 내에서 실행되는 동안 프로세스 ID를 사용하여 `perf` 명령을 실행합니다.

```bash
sudo perf record -p 2266 -g
```

`perf` 명령이 성능 수집 프로세스를 시작합니다. 약 20-30초 동안 실행한 후 <kbd>Ctrl+C</kbd>를 눌러 수집 프로세스를 종료합니다. 동일한 `perf` 명령을 사용하여 추적의 출력을 볼 수 있습니다.

```bash
sudo perf report -f
```

다음 명령을 사용하여 _flame-graph_ 를 생성할 수도 있습니다.

```bash
git clone --depth=1 https://github.com/BrendanGregg/FlameGraph
sudo perf script | FlameGraph/stackcollapse-perf.pl | FlameGraph/flamegraph.pl > flamegraph.svg
```

이 명령은 성능 문제를 조사하기 위해 브라우저에서 볼 수 있는 `flamegraph.svg`를 생성합니다.

[![플레임 그래프 SVG 이미지](media/flamegraph.jpg)](media/flamegraph.jpg#lightbox)

### <a name="windows"></a>[Windows](#tab/windows)

Windows에서는 [dotnet-trace](dotnet-trace.md) 도구를 프로파일러로 사용할 수 있습니다. 이전 [샘플 디버그 대상](/samples/dotnet/samples/diagnostic-scenarios)을 사용하여 높은 CPU 엔드포인트(`https://localhost:5001/api/diagscenario/highcpu/60000`)를 다시 실행합니다. 1분 요청 내에서 실행되는 동안 다음과 같이 `collect` 명령을 사용합니다.

```dotnetcli
dotnet-trace collect -p 22884 --providers Microsoft-DotNETCore-SampleProfiler
```

[dotnet-trace](dotnet-trace.md)를 약 20-30초 동안 실행한 후 <kbd>Enter</kbd>를 눌러 컬렉션을 종료합니다. 그 결과, 동일한 폴더에 `nettrace` 파일이 생성됩니다. `nettrace` 파일은 Windows에서 기존 분석 도구를 사용하는 좋은 방법입니다.

아래와 같이 [`PerfView`](https://github.com/microsoft/perfview/blob/master/documentation/Downloading.md)를 사용하여 `nettrace`를 엽니다.

[![PerfView 이미지](media/perfview.jpg)](media/perfview.jpg#lightbox)

---

## <a name="see-also"></a>참조

- 프로세스를 나열하는 [dotnet-trace](dotnet-trace.md)
- 관리되는 메모리 사용량을 검사하는 [dotnet-counters](dotnet-counters.md)
- 덤프 파일을 수집 및 분석하는 [dotnet-dump](dotnet-dump.md)
- [dotnet/diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [.NET Core의 교착 상태 디버그](debug-deadlock.md)
