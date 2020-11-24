---
title: 진단 도구 개요 - .NET Core
description: .NET Core 애플리케이션을 진단하는 데 사용할 수 있는 도구 및 기술에 대한 개요입니다.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: 3274b72363a3df1dbe1bb29492eedcb134a4f9f2
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982311"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a>.NET Core에서 사용할 수 있는 진단 도구는 무엇인가요?

소프트웨어가 항상 예상한 대로 작동하지는 않지만 .NET Core에는 이러한 문제를 빠르고 효과적으로 진단할 수 있는 도구 및 API가 있습니다.

이 문서는 필요한 다양한 도구를 찾는 데 도움이 됩니다.

## <a name="managed-debuggers"></a>관리형 디버거

[관리형 디버거](managed-debuggers.md)를 사용하여 프로그램과 상호 작용할 수 있습니다. 일시 중지, 증분 실행, 검사 및 다시 시작은 코드 동작에 대한 인사이트를 제공합니다. 디버거는 쉽게 재현될 수 있는 기능 문제를 진단하는 데 사용되는 첫 번째 선택 옵션입니다.

## <a name="logging-and-tracing"></a>로깅 및 추적

[로깅 및 추적](logging-tracing.md)은 관련된 기술입니다. 계측 코드를 참조하여 로그 파일을 만듭니다. 파일에는 프로그램에서 수행하는 작업에 대한 세부 정보가 기록됩니다. 해당 세부 정보를 사용하여 가장 복잡한 문제를 진단할 수 있습니다. 타임스탬프와 결합할 경우 이러한 기술은 성능 조사에도 유용합니다.

## <a name="unit-testing"></a>단위 테스트

[유닛 테스트](../testing/index.md)는 고품질 소프트웨어의 연속 통합 및 배포를 위한 핵심 구성 요소입니다. 단위 테스트는 항목을 중단할 때 조기 경고를 제공하도록 설계되었습니다.

## <a name="collect-diagnostics-in-containers"></a>컨테이너에서 진단 정보 수집

컨테이너화되지 않은 Linux 환경에서 사용되는 것과 동일한 진단 도구를 사용하여 [컨테이너에서 진단 정보를 수집](diagnostics-in-containers.md)할 수도 있습니다. 도구가 Docker 컨테이너에서 작동하는지 확인하는 데 필요한 몇 가지 사용 변경 내용만 있습니다.

## <a name="debug-linux-dumps"></a>Linux 덤프 디버그

[Linux 덤프 디버그](debug-linux-dumps.md)는 Linux에서 덤프를 수집 및 분석하는 방법을 설명합니다.

## <a name="net-core-diagnostic-global-tools"></a>.NET Core 진단 전역 도구

### <a name="dotnet-counters"></a>dotnet-counters

[dotnet-counters](dotnet-counters.md)는 1단계 상태 모니터링 및 성능 조사를 위한 성능 모니터링 도구입니다. <xref:System.Diagnostics.Tracing.EventCounter>API를 통해 게시된 성능 카운터 값을 관찰합니다. 예를 들어 .NET Core 애플리케이션에서 throw되는 CPU 사용량 또는 예외 발생률과 같은 항목을 신속하게 모니터링할 수 있습니다.

### <a name="dotnet-dump"></a>dotnet-dump

[dotnet dump](dotnet-dump.md) 도구는 네이티브 디버거 없이 Windows 및 Linux 코어 덤프를 수집하 고 분석하는 방법입니다.

### <a name="dotnet-gcdump"></a>dotnet-gcdump

[dotnet-gcdump](dotnet-gcdump.md) 도구로 라이브 .NET 프로세스의 GC(가비지 수집기) 덤프를 수집할 수 있습니다.

### <a name="dotnet-trace"></a>dotnet-trace

.NET Core에는 진단 데이터가 노출되는 `EventPipe`라고 하는 기능이 포함되어 있습니다. [dotnet-trace](dotnet-trace.md) 도구를 사용하면 앱에서 흥미로운 프로파일링 데이터를 사용하여 앱 속도가 느려지는 근본 원인이 되는 시나리오를 찾는 데 도움이 될 수 있습니다.

### <a name="dotnet-symbol"></a>dotnet-symbol

[dotnet-symbol](dotnet-symbol.md)은 코어 덤프 또는 미니덤프를 여는 데 필요한 파일(기호, DAC/DBI, 호스트 파일 등)을 다운로드합니다. 다른 컴퓨터에서 캡처된 덤프 파일을 디버깅하기 위한 기호 및 모듈이 필요하면 이 도구를 사용합니다.

### <a name="dotnet-sos"></a>dotnet-sos

[dotnet-sos](dotnet-sos.md)는 Linux 또는 MacOS(또는 이전 디버깅 도구를 사용할 경우 Windows)에 [SOS 디버깅 확장](../../framework/tools/sos-dll-sos-debugging-extension.md)을 설치하는 데 사용됩니다.

### <a name="perfcollect"></a>PerfCollect

[PerfCollect](trace-perfcollect-lttng.md)는 `perf` 및 `LTTng`로 추적을 수집하는 데 사용할 수 있는 bash 스크립트로, Linux 배포판에서 실행되는 .NET 앱에 대한 보다 자세한 성능 분석을 위해 사용할 수 있습니다.

## <a name="net-core-diagnostics-tutorials"></a>.NET Core 진단 자습서

### <a name="debug-a-memory-leak"></a>메모리 누수 디버그

[자습서: 메모리 누수 디버그](debug-memory-leak.md)에서는 메모리 누수를 검색하는 과정을 안내합니다. [dotnet-counters](dotnet-counters.md) 도구는 누수를 확인하는 데 사용되고, [dotnet-dump](dotnet-dump.md) 도구는 누수를 진단하는 데 사용됩니다.

### <a name="debug-high-cpu-usage"></a>높은 CPU 사용량 디버그

[자습서: 높은 CPU 사용량 디버그](debug-highcpu.md)는 높은 CPU 사용량을 조사하는 과정을 안내합니다. [dotnet-counters](dotnet-counters.md) 도구를 사용하여 높은 CPU 사용량을 확인합니다. 그런 다음 [성능 분석 유틸리티(`dotnet-trace`)](dotnet-trace.md) 또는 Linux `perf`를 사용하여 CPU 사용량 프로필을 수집하고 보는 과정을 안내합니다.

### <a name="debug-deadlock"></a>교착 상태 디버그

[자습서: 교착 상태 디버그](debug-deadlock.md)는 [dotnet-dump](dotnet-dump.md) 도구를 사용하여 스레드와 잠금을 조사하는 방법을 안내합니다.

### <a name="measure-performance-using-eventcounters"></a>EventCounters를 사용하여 성능 측정

[자습서: .NET에서 EventCounters를 사용하여 성능 측정](event-counter-perf.md)에서 <xref:System.Diagnostics.Tracing.EventCounter> API를 사용하여 .NET 앱에서 성능을 측정하는 방법을 확인할 수 있습니다.
