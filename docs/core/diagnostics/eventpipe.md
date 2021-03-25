---
title: EventPipe 개요
description: EventPipe에 대해 알아보고 성능 문제를 진단하기 위해 .NET 애플리케이션 추적에 이를 사용하는 방법을 알아봅니다.
ms.date: 11/09/2020
ms.topic: overview
ms.openlocfilehash: 0b4782306c85590d74b521edd254659fb162b0c2
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103624164"
---
# <a name="eventpipe"></a>EventPipe

EventPipe는 ETW 또는 LTTng처럼 추적 데이터를 수집하는 데 사용할 수 있는 런타임 구성 요소입니다. EventPipe의 목표는 .NET 개발자가 ETW 또는 LTTng처럼 플랫폼별 OS 네이티브 구성 요소를 사용하지 않고도 .NET 애플리케이션을 쉽게 추적할 수 있도록 하는 것입니다.

EventPipe는 많은 진단 도구에서 사용되는 메커니즘으로, 런타임에서 내보낸 이벤트뿐만 아니라 [EventSource](xref:System.Diagnostics.Tracing.EventSource)로 작성된 사용자 지정 이벤트를 사용하는 데 사용할 수 있습니다.

이 문서는 EventPipe에 대한 개요로, EventPipe를 사용하는 시기 및 방법, 요구 사항에 가장 적합하도록 구성하는 방법을 설명합니다.

## <a name="eventpipe-basics"></a>EventPipe 기본 사항

EventPipe는 Just-In-Time 컴파일러나 가비지 수집기와 같은 런타임 구성 요소에서 내보낸 이벤트와 라이브러리 및 사용자 코드에서 [EventSource](xref:System.Diagnostics.Tracing.EventSource) 인스턴스로 작성된 이벤트를 집계합니다.

그런 다음 이벤트를 직렬화하고 파일에 직접 쓰거나 out-of-process에서 진단 포트를 통해 사용할 수 있습니다. Windows에서 진단 포트는 `NamedPipe`로 구현됩니다. Linux 또는 macOS와 같은 Windows가 아닌 플랫폼에서는 Unix 도메인 소켓을 사용하여 구현됩니다. 진단 포트 및 사용자 지정 프로세스 간 통신 프로토콜을 통해 상호 작용하는 방법에 대한 자세한 내용은 [진단 IPC 프로토콜 설명서](https://github.com/dotnet/diagnostics/blob/master/documentation/design-docs/ipc-protocol.md)를 참조하세요.

EventPipe는 직렬화된 이벤트를 `.nettrace` 파일 형식으로 기록하며, 진단 포트를 통해 스트림으로 기록하거나 파일에 직접 기록합니다. EventPipe serialization 형식에 대한 자세한 내용은 [EventPipe format documentation](https://github.com/microsoft/perfview/blob/master/src/TraceEvent/EventPipe/EventPipeFormat.md)(EventPipe 형식 설명서)을 참조하세요.

## <a name="eventpipe-vs-etwlttng"></a>EventPipe 및 ETW/LTTng

EventPipe는 .NET 런타임(CoreCLR)의 일부이며 .NET Core에서 지원하는 모든 플랫폼에서 동일한 방식으로 작동하도록 설계되었습니다. 따라서 `dotnet-counters`, `dotnet-gcdump`, `dotnet-trace` 같은 EventPipe 기반 추적 도구가 여러 플랫폼에서 원활하게 작동할 수 있습니다.

그러나 EventPipe는 런타임 기본 제공 구성 요소이기 때문에 범위는 관리 코드와 런타임 자체로 제한됩니다. EventPipe는 네이티브 코드 스택 확인이나 다양한 커널 이벤트 가져오기와 같은 하위 수준 이벤트를 추적하는 데 사용할 수 없습니다. 앱에서 C/C++ interop을 사용하거나 C++로 작성된 런타임 자체를 추적하거나 커널 이벤트(즉, 네이티브 스레드 컨텍스트 전환 이벤트)가 필요한 앱의 동작을 심층 진단하려는 경우 ETW 또는 [perf/LTTng](./trace-perfcollect-lttng.md)를 사용해야 합니다.

EventPipe와 ETW/LTTng의 또 다른 주요 차이점은 관리자/루트 권한 요구 사항입니다. ETW 또는 LTTng를 사용하여 애플리케이션을 추적하려면 관리자/루트여야 합니다. 추적 프로그램(예: `dotnet-trace`)이 애플리케이션을 시작한 사용자와 동일한 사용자로 실행되는 한 EventPipe를 사용하여 애플리케이션을 추적할 수 있습니다.

다음 표에서는 EventPipe와 ETW/LTTng의 차이점을 요약합니다.

|기능|EventPipe|ETW|LTTng|
|-------|---------|---|-----------|
|플랫폼 간|예|아니요(Windows에서만)|아니요(지원되는 Linux 배포판에서만)|
|관리자/루트 권한 필요|아니요|예|예|
|OS/커널 이벤트를 가져올 수 있음|아니요|예|예|
|기본 호출 스택을 확인할 수 있음|아니요|예|예|

## <a name="use-eventpipe-to-trace-your-net-application"></a>EventPipe를 사용하여 .NET 애플리케이션 추적

EventPipe를 사용하여 다음과 같은 여러 가지 방법으로 .NET 애플리케이션을 추적할 수 있습니다.

* EventPipe를 기반으로 빌드되는 [진단 도구](#tools-that-use-eventpipe) 중 하나를 사용합니다.

* [Microsoft.Diagnostics.NETCore.Client](https://github.com/dotnet/diagnostics/blob/master/documentation/diagnostics-client-library-instructions.md) 라이브러리를 사용하여 EventPipe 세션을 구성하고 시작하는 고유한 도구를 직접 작성합니다.

* [환경 변수](#trace-using-environment-variables)를 사용하여 EventPipe를 시작합니다.

EventPipe 이벤트를 포함하는 `nettrace` 파일을 생성한 후에는 [`PerfView`](https://github.com/Microsoft/perfview#perfview-overview) 또는 Visual Studio에서 파일을 볼 수 있습니다. Windows가 아닌 플랫폼에서는 [`dotnet-trace convert`](./dotnet-trace.md#dotnet-trace-convert) 명령을 사용하여 `nettrace` 파일을 `speedscope` 또는 `Chromium` 추적 형식으로 변환하고 [`speedscope`](https://www.speedscope.app/) 또는 Chrome DevTools를 사용하여 볼 수 있습니다.

[TraceEvent](https://github.com/Microsoft/perfview/blob/master/documentation/TraceEvent/TraceEventLibrary.md)를 사용하여 프로그래밍 방식으로 EventPipe 추적을 분석할 수도 있습니다.

### <a name="tools-that-use-eventpipe"></a>EventPipe를 사용하는 도구

EventPipe를 사용하여 애플리케이션을 추적하는 가장 쉬운 방법입니다. 이러한 각 도구를 사용하는 방법에 대한 자세한 내용은 각 도구의 설명서를 참조하세요.

* [dotnet-counters](./dotnet-counters.md)를 사용하면 .NET 런타임 및 핵심 라이브러리에서 내보낸 다양한 메트릭뿐만 아니라 직접 작성할 수 있는 사용자 지정 메트릭을 모니터링하고 수집할 수 있습니다.

* [dotnet-gcdump](./dotnet-gcdump.md)를 사용하면 라이브 프로세스의 GC 힙 덤프를 수집하여 애플리케이션의 관리되는 힙을 분석할 수 있습니다.

* [dotnet-trace](./dotnet-trace.md)를 사용하면 애플리케이션의 추적을 수집하여 성능을 분석할 수 있습니다.

## <a name="trace-using-environment-variables"></a>환경 변수를 사용하여 추적

EventPipe를 사용하는 기본 메커니즘은 `dotnet-trace` 또는 `Microsoft.Diagnostics.NETCore.Client` 라이브러리를 사용하는 것입니다.

그러나 다음 환경 변수를 사용하여 앱에서 EventPipe 세션을 설정하고 파일에 직접 추적을 기록할 수 있습니다. 추적을 중지하려면 애플리케이션을 종료합니다.

* `COMPlus_EnableEventPipe`: 파일에 직접 기록하는 EventPipe 세션을 시작하려면 `1`로 설정합니다. 기본값은 `0`입니다.

* `COMPlus_EventPipeOutputPath`: `COMPlus_EnableEventPipe`를 통해 실행하도록 구성된 경우 출력 EventPipe 추적 파일의 경로입니다. 기본값은 `trace.nettrace`이며, 앱이 실행되는 것과 동일한 디렉터리에 생성됩니다.

* `COMPlus_EventPipeCircularMB`: EventPipe의 내부 버퍼 크기(MB)를 나타내는 16진수 값입니다. 해당 구성 값은 EventPipe가 `COMPlus_EnableEventPipe`를 통해 실행되도록 구성된 경우에만 사용됩니다. 기본 버퍼 크기는 1,024MB이며 `0x400` == `1024`이므로 `400`으로 설정되는 해당 환경 변수로 변환됩니다.

  > [!NOTE]
  > 대상 프로세스가 이벤트를 너무 자주 기록하는 경우 이 버퍼가 오버플로되고 일부 이벤트가 삭제될 수 있습니다. 너무 많은 이벤트가 삭제되는 경우에는 버퍼 크기를 늘려 삭제된 이벤트 수가 감소하는지 확인하세요. 버퍼 크기를 늘려도 삭제된 이벤트 수가 감소하지 않는다면 이는 느린 판독기로 인해 대상 프로세스의 버퍼가 플러시되지 않기 때문일 수 있습니다.

* `COMPlus_EventPipeProcNumbers`: `1`로 설정하여 EventPipe 이벤트 헤더에서 프로세서 번호를 캡처할 수 있도록 합니다. 기본값은 `0`입니다.

* `COMPlus_EventPipeConfig`: `COMPlus_EnableEventPipe`를 사용하여 EventPipe 세션을 시작할 때 EventPipe 세션 구성을 설정합니다.
  구문은 다음과 같습니다.

  `<provider>:<keyword>:<level>`

  쉼표로 연결하여 여러 공급자를 지정할 수도 있습니다.

  `<provider1>:<keyword1>:<level1>,<provider2>:<keyword2>:<level2>`

  이 환경 변수는 설정되지 않았지만 `COMPlus_EnableEventPipe`에서 EventPipe를 사용하도록 설정한 경우 다음 키워드 및 수준으로 다음 공급자를 사용하도록 설정하여 추적을 시작합니다.

  - `Microsoft-Windows-DotNETRuntime:4c14fccbd:5`
  - `Microsoft-Windows-DotNETRuntimePrivate:4002000b:5`
  - `Microsoft-DotNETCore-SampleProfiler:0:5`

  .NET의 잘 알려진 몇 가지 공급자에 대해 자세히 알아보려면 [잘 알려진 이벤트 공급자](./well-known-event-providers.md)를 참조하세요.
