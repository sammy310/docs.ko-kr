---
title: .NET의 고성능 로깅
author: IEvangelist
description: LoggerMessage를 사용하여 고성능 로깅 시나리오에 적은 개체 할당을 필요로 하는 캐시 가능한 대리자를 만드는 방법을 알아봅니다.
ms.author: dapine
ms.date: 01/04/2021
ms.openlocfilehash: 0031ff7a9f70cb0cf724fdf6dfa4fbe0a44af7c1
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "102402134"
---
# <a name="high-performance-logging-in-net"></a>.NET의 고성능 로깅

<xref:Microsoft.Extensions.Logging.LoggerMessage> 클래스는 <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> 및 <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogDebug%2A>와 같은 [로거 확장 메서드](xref:Microsoft.Extensions.Logging.LoggerExtensions)에 비해 적은 개체 할당 및 감소된 계산 오버헤드를 필요로 하는 캐시 가능한 대리자를 만드는 기능을 노출합니다. 고성능 로깅 시나리오의 경우 <xref:Microsoft.Extensions.Logging.LoggerMessage> 패턴을 사용합니다.

<xref:Microsoft.Extensions.Logging.LoggerMessage>는 로거 확장 메서드에 비해 다음과 같은 성능 이점을 제공합니다.

- 로거 확장 메서드는 `object`에 대한 `int`와 같은 "boxing"(변환) 값 형식이 필요합니다. <xref:Microsoft.Extensions.Logging.LoggerMessage> 패턴은 정적 <xref:System.Action> 필드 및 강력한 형식의 매개 변수가 있는 확장 메서드를 사용하여 boxing을 방지합니다.
- 로거 확장 메서드는 로그 메시지가 기록될 때마다 메시지 템플릿(명명된 형식 문자열)을 구문 분석해야 합니다. <xref:Microsoft.Extensions.Logging.LoggerMessage>는 메시지가 정의될 때 템플릿 구문 분석이 한번만 필요합니다.

샘플 앱에서는 우선 순위 큐 처리 작업자 서비스를 사용하는 <xref:Microsoft.Extensions.Logging.LoggerMessage> 기능을 보여 줍니다. 이 앱은 작업 항목을 우선 순위에 따라 처리합니다. 이러한 작업이 발생하는 대로 로그 메시지는 <xref:Microsoft.Extensions.Logging.LoggerMessage> 패턴을 사용하여 생성됩니다.

## <a name="define-a-logger-message"></a>로거 메시지 정의

[Define(LogLevel, EventId, String)](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A)을 사용하여 메시지 로깅을 위한 <xref:System.Action> 대리자를 만듭니다. <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> 오버로드는 명명된 형식 문자열(템플릿)로 최대 6개의 형식 매개 변수 전달을 허용합니다.

<xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> 메서드에 제공된 문자열은 템플릿이며 보간된 문자열이 아닙니다. 자리 표시자는 형식이 지정된 순서로 채워집니다. 템플릿의 자리 표시자 이름은 템플릿에서 알기 쉽고 일관되어야 합니다. 구조적 로그 데이터 내에서 속성 이름으로 사용됩니다. 자리 표시자 이름으로 [파스칼식 대/소문자](../../standard/design-guidelines/capitalization-conventions.md)를 권장합니다. 예: `{Item}`, `{DateTime}`

각 로그 메시지는 [LoggerMessage.Define](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A)에서 만들어진 정적 필드에 보관된 <xref:System.Action>입니다. 예를 들어 샘플 앱은 작업 항목 처리에 대한 로그 메시지를 설명하는 필드를 만듭니다.

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="FailedProcessingField":::

<xref:System.Action>의 경우 다음을 지정합니다.

- 로그 수준
- 정적 확장 메서드의 이름이 있는 고유한 이벤트 식별자(<xref:Microsoft.Extensions.Logging.EventId>)입니다.
- 메시지 템플릿(명명된 형식 문자열)

작업 항목이 처리를 위해 큐에서 제거될 때 작업자 서비스 앱이 다음을 설정합니다.

- 로그 수준을 <xref:Microsoft.Extensions.Logging.LogLevel.Critical?displayProperty=nameWithType>으로
- 이벤트 ID를 `FailedToProcessWorkItem` 메서드의 이름이 있는 `13`로
- 메시지 템플릿(명명된 형식 문자열)을 문자열로

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="FailedProcessingAssignment":::

구조적 로깅 저장소는 로깅을 보강하도록 이벤트 ID로 제공될 경우 이벤트 이름을 사용할 수 있습니다. 예를 들어 [Serilog](https://github.com/serilog/serilog-extensions-logging)는 이벤트 이름을 사용합니다.

<xref:System.Action>은 강력한 형식의 확장 메서드를 통해 호출됩니다. `PriorityItemProcessed` 메서드는 작업 항목이 처리될 때마다 메시지를 기록합니다. 반면, 예외가 발생하는 경우 `FailedToProcessWorkItem`이 호출됩니다.

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="15-18":::

앱의 콘솔 출력을 검사합니다.

```console
crit: WorkerServiceOptions.Example.Worker[13]
      Epic failure processing item!
      System.Exception: Failed to verify communications.
         at WorkerServiceOptions.Example.Worker.ExecuteAsync(CancellationToken stoppingToken) in
         ..\Worker.cs:line 27
```

로그 메시지에 매개 변수를 전달하려면 정적 필드를 만들 때 최대 6개의 형식을 정의합니다. 샘플 앱에서는 <xref:System.Action> 필드의 `WorkItem` 형식을 정의하여 항목을 처리할 때 작업 항목 세부 정보를 기록합니다.

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemField":::

대리자의 로그 메시지 템플릿은 제공되는 형식에서 해당 자리 표시자 값을 받습니다. 샘플 앱은 항목 매개 변수가 `WorkItem`인 작업 항목을 추가하기 위한 대리자를 정의합니다.

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemAssignment":::

작업 항목을 처리 중임을 기록하는 정적 확장 메서드 `PriorityItemProcessed`는 작업 항목 인수 값을 받아 <xref:System.Action> 대리자에게 전달합니다.

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemMethod":::

작업자 서비스의 `ExecuteAsync` 메서드에서 메시지를 기록하기 위해 `PriorityItemProcessed`가 호출됩니다.

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="12":::

앱의 콘솔 출력을 검사합니다.

```console
info: WorkerServiceOptions.Example.Worker[1]
      Processing priority item: Priority-Extreme (50db062a-9732-4418-936d-110549ad79e4): 'Verify communications'
```

## <a name="define-logger-message-scope"></a>로거 메시지 범위 정의

[DefineScope(String)](xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A) 메서드는 [로그 범위](logging.md#log-scopes)를 정의하기 위한 <xref:System.Func%601> 대리자를 만듭니다. <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> 오버로드는 명명된 형식 문자열(템플릿)로 최대 3개의 형식 매개 변수 전달을 허용합니다.

<xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> 메서드의 경우와 마찬가지로 <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> 메서드에 제공된 문자열은 템플릿이며 보간된 문자열이 아닙니다. 자리 표시자는 형식이 지정된 순서로 채워집니다. 템플릿의 자리 표시자 이름은 템플릿에서 알기 쉽고 일관되어야 합니다. 구조적 로그 데이터 내에서 속성 이름으로 사용됩니다. 자리 표시자 이름으로 [파스칼식 대/소문자](../../standard/design-guidelines/capitalization-conventions.md)를 권장합니다. 예: `{Item}`, `{DateTime}`

<xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> 메서드를 사용하여 일련의 로그 메시지에 적용하도록 [로그 범위](logging.md#log-scopes)를 정의합니다. *appsettings.json* 의 콘솔 로거 섹션에서 `IncludeScopes`를 사용하도록 설정합니다.

:::code language="json" source="snippets/configuration/worker-service-options/appsettings.json" highlight="3-5":::

로그 범위를 만들려면 범위에 대한 <xref:System.Func%601> 대리자를 보유하는 필드를 추가합니다. 샘플 앱은 `_processingWorkScope`라는 필드를 만듭니다(*Internal/LoggerExtensions.cs*).

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkField":::

<xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A>를 사용하여 대리자를 만듭니다. 대리자가 호출되는 경우 템플릿 인수로 사용하기 위해 최대 세 개의 형식을 지정할 수 있습니다. 샘플 앱에서는 처리가 시작된 날짜/시간을 포함하는 메시지 템플릿을 사용합니다.

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkAssignment":::

로그 메시지에 대한 정적 확장 메서드를 제공합니다. 메시지 템플릿에 표시되는 명명된 속성에 대한 모든 형식 매개 변수를 포함합니다. 샘플 앱은 기록할 사용자 지정 타임스탬프에 `DateTime`을 사용하고 `_processingWorkScope`를 반환합니다.

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkMethod":::

범위는 [using](../../csharp/language-reference/keywords/using-statement.md) 블록에서 로깅 확장 호출을 래핑합니다.

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="4":::

앱의 콘솔 출력에서 로그 메시지를 검사합니다. 다음 결과에는 로그 범위 메시지가 포함된 로그 메시지의 우선 순위가 표시되어 있습니다.

```console
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Extreme (f5090ede-a337-4041-b914-f6bc0db5ae64): 'Verify communications'
info: Microsoft.Hosting.Lifetime[0]
      Application started. Press Ctrl+C to shut down.
info: Microsoft.Hosting.Lifetime[0]
      Hosting environment: Development
info: Microsoft.Hosting.Lifetime[0]
      Content root path: ..\worker-service-options
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-High (496d440f-2007-4391-b179-09d75ab52373): 'Validate collection'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Medium (dea9e3f4-d7df-46d2-b7cd-5e0232eb98a5): 'Propagate selections'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Medium (089d7f0d-da72-4b55-92fe-57b147838056): 'Enter pooling [contention]'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Low (6e68c4be-089f-4450-9080-1ea63fcbb686): 'Health check network'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Deferred (6f324134-6bb6-455f-81d4-553ab307c421): 'Ping weather service'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Deferred (37bf736c-7a26-4a2a-9e56-e89bcf3b8f35): 'Set process state'
```

## <a name="see-also"></a>참고 항목

- [.NET의 로깅](logging.md)
