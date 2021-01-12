---
title: 로깅 및 추적 - .NET Core
description: .NET Core 로깅 및 추적에 대해 간략히 설명합니다.
ms.date: 10/12/2020
ms.openlocfilehash: fac8eeed63e8737ad42699d81b421747b207c69a
ms.sourcegitcommit: 35ca2255c6c86968eaef9e3a251c9739ce8e4288
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2020
ms.locfileid: "97753629"
---
# <a name="net-core-logging-and-tracing"></a>.NET Core 로깅 및 추적

로깅과 추적은 실제로 동일한 기술에 대한 두 가지 이름입니다. 간단한 기술은 컴퓨터 초기부터 사용되었습니다. 단지 나중에 사용할 쓰기 출력을 작성하기 위해 애플리케이션을 계측하는 것과 관련이 있습니다.

## <a name="reasons-to-use-logging-and-tracing"></a>로깅 및 추적을 사용하는 이유

이 간단한 기술은 놀라울 정도로 강력합니다. 디버거가 실패하는 경우 다음과 같이 사용할 수 있습니다.

- 오랜 기간 동안 발생하는 문제는 기존 디버거로 디버그하기가 어려울 수 있습니다. 로그를 사용하면 오랜 기간에 걸친 사후 검토를 자세히 수행할 수 있습니다. 이와 대조적으로 디버거는 실시간 분석으로 제한됩니다.
- 다중 스레드 애플리케이션과 분산 애플리케이션은 디버그하기 어려운 경우가 많습니다.  디버거를 연결하면 동작이 수정되는 경향이 있습니다. 복잡한 시스템을 이해하기 위해 필요에 따라 자세한 로그를 분석할 수 있습니다.
- 분산 애플리케이션의 문제는 여러 구성 요소 간의 복잡한 상호 작용으로 인해 발생할 수 있으며, 디버거를 시스템의 모든 부분에 연결하는 것이 적절하지 않을 수 있습니다.
- 많은 서비스가 중단되지 않아야 합니다. 디버거를 연결하면 시간 제한 오류가 발생하는 경우가 많습니다.
- 문제는 항상 예측되는 것이 아닙니다. 로깅 및 추적은 문제가 발생하는 경우 프로그램에서 항상 기록할 수 있도록 낮은 오버헤드로 설계되었습니다.

## <a name="net-core-apis"></a>.NET Core API

### <a name="print-style-apis"></a>인쇄 스타일 API

<xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType> 및 <xref:System.Diagnostics.Debug?displayProperty=nameWithType> 클래스는 각각 로깅에 편리한 비슷한 인쇄 스타일 API를 제공합니다.

사용할 인쇄 스타일 API를 선택하는 것은 사용자에게 달려 있습니다. 주요 차이점은 다음과 같습니다.

- <xref:System.Console?displayProperty=nameWithType>
  - 항상 사용하도록 설정되어 있으며 항상 콘솔에 기록됩니다.
  - 고객이 릴리스에서 확인해야 하는 정보에 유용합니다.
  - 가장 간단한 방법이므로 임시 디버깅에 자주 사용됩니다. 이 디버그 코드는 소스 제어에 체크인되지 않는 경우가 많습니다.
- <xref:System.Diagnostics.Trace?displayProperty=nameWithType>
  - 소스에 `#define TRACE`를 추가하거나 컴파일할 때 `/d:TRACE` 옵션을 지정하여 `TRACE`를 정의한 경우에만 사용할 수 있습니다.
  - 연결된 <xref:System.Diagnostics.Trace.Listeners>(기본적으로 <xref:System.Diagnostics.DefaultTraceListener>)에 씁니다.
  - 대부분의 빌드에서 사용하도록 설정될 로그를 만드는 경우 이 API를 사용합니다.
- <xref:System.Diagnostics.Debug?displayProperty=nameWithType>
  - 소스에 `#define DEBUG`를 추가하거나 컴파일할 때 `/d:DEBUG` 옵션을 지정하여 `DEBUG`를 정의한 경우에만 사용할 수 있습니다.
  - 연결된 디버거에 씁니다.
  - `COMPlus_DebugWriteToStdErr`가 설정된 경우 `*nix`에서 stderr에 씁니다.
  - 디버그 빌드에서만 사용하도록 설정될 로그를 만드는 경우 이 API를 사용합니다.

### <a name="logging-events"></a>이벤트 로깅

다음 API는 더 이벤트 지향적입니다. 단순 문자열을 기록하는 대신 이벤트 개체를 기록합니다.

- <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType>
  - EventSource는 기본 루트 .NET Core 추적 API입니다.
  - 모든 .NET Standard 버전에서 사용할 수 있습니다.
  - 직렬화할 수 있는 개체만 추적할 수 있습니다.
  - EventSource를 이용하도록 구성된 [EventListener](xref:System.Diagnostics.Tracing.EventListener) 인스턴스를 통해 in-process로 이용할 수 있습니다.
  - 다음을 통해 out-of-process로 이용할 수 있습니다.
    - 모든 플랫폼에서 [.NET Core의 EventPipe](./eventpipe.md)
    - [ETW(Windows용 이벤트 추적)](/windows/win32/etw/event-tracing-portal)
    - [Linux용 LTTng 추적 프레임워크](https://lttng.org/)
      - 연습: [PerfCollect를 사용하여 LTTng 추적 수집](trace-perfcollect-lttng.md)

- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>
  - .NET Core 및 .NET Framework용 [NuGet 패키지](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource)에 포함되어 있습니다.
  - 프로세스 내에서 직렬화할 수 없는 개체를 추적할 수 있습니다.
  - 로깅된 개체의 선택한 필드를 <xref:System.Diagnostics.Tracing.EventSource>에 쓸 수 있게 하는 브리지가 포함되어 있습니다.

- <xref:System.Diagnostics.Activity?displayProperty=nameWithType>
  - 특정 활동 또는 트랜잭션으로 인해 발생하는 로그 메시지를 식별할 수 있는 명확한 방법을 제공합니다. 이 개체를 사용하여 여러 서비스에서 로그를 상호 연결시킬 수 있습니다.

- <xref:System.Diagnostics.EventLog?displayProperty=nameWithType>
  - Windows만 해당합니다.
  - 메시지를 Windows 이벤트 로그에 씁니다.
  - 시스템 관리자는 Windows 이벤트 로그에 심각한 애플리케이션 오류 메시지가 표시될 것으로 예상합니다.

## <a name="ilogger-and-logging-frameworks"></a>ILogger 및 로깅 프레임워크

하위 수준 API는 로깅 요구 사항에 적합하지 않을 수 있습니다. 로깅 프레임워크를 고려할 수 있습니다.

<xref:Microsoft.Extensions.Logging.ILogger> 인터페이스는 종속성 주입을 통해 로거를 삽입할 수 있는 공용 로깅 인터페이스를 만드는 데 사용되었습니다.

예를 들어 애플리케이션에 가장 적합한 것을 선택할 수 있도록 .NET에서 기본 제공 및 타사 프레임워크를 선택할 수 있도록 지원합니다.

- [.NET 기본 제공 로깅 공급자](../extensions/logging-providers.md#built-in-logging-providers)
- [.NET 타사 로깅 공급자](../extensions/logging-providers.md#third-party-logging-providers)

## <a name="logging-related-references"></a>로깅 관련 참고 자료

- [방법: 추적 및 디버그를 사용한 조건부 컴파일](../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)

- [방법: 애플리케이션 코드에 Trace 문 추가](../../framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)

- [.NET에서 로깅](../extensions/logging.md)은 지원하는 로깅 기술에 대해 간략히 설명합니다.

- [C# 문자열 보간](../../csharp/language-reference/tokens/interpolated.md)은 로깅 코드 작성을 간소화할 수 있습니다.

- [런타임 공급자 이벤트 목록](../../fundamentals/diagnostics/runtime-events.md)

- [.NET의 잘 알려진 이벤트 공급자](well-known-event-providers.md)

- <xref:System.Exception.Message?displayProperty=nameWithType> 속성은 예외를 기록하는 데 유용합니다.

- <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> 클래스는 로그에 스택 정보를 제공하는 데 유용할 수 있습니다.

## <a name="performance-considerations"></a>성능 고려 사항

문자열 형식을 지정하면 CPU 처리 시간이 오래 걸릴 수 있습니다.

성능이 중요한 애플리케이션에 추천되는 고려 사항은 다음과 같습니다.

- 수신 대기하지 않을 때는 로깅을 많이 수행하지 않도록 합니다. 로깅을 먼저 사용하도록 설정되어 있는지 확인하여 비용이 많이 드는 로깅 메시지를 생성하지 않도록 합니다.
- 유용한 것만 기록합니다.
- 고급 서식 지정을 분석 단계까지 연기합니다.
