---
title: .NET용 Azure SDK를 사용하여 로깅
description: .NET 용 Azure SDK 클라이언트 라이브러리를 사용하여 로깅을 사용하도록 설정하는 방법 알아보기
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: 0b255713bc9c13e0cbdaeb25a3d0fe46e91e815d
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416027"
---
# <a name="logging-with-the-azure-sdk-for-net"></a>.NET용 Azure SDK를 사용하여 로깅

.NET용 [Azure SDK](https://azure.microsoft.com/downloads/) 클라이언트 라이브러리에는 클라이언트 라이브러리 작업을 로그하는 기능이 포함되어 있습니다. 이를 통해 클라이언트 라이브러리가 Azure 서비스에 대해 수행하는 I/O 요청 및 응답을 모니터링할 수 있습니다. 일반적으로 로그는 통신 문제를 디버그하거나 진단하는 데 사용됩니다. 이 문서에서는 .NET용 Azure SDK를 사용하여 로깅하도록 설정하는 세 가지 방법을 설명합니다.

- 콘솔 창에 로그
- .NET 진단 추적에 로그
- 사용자 지정 로깅 구성

> [!IMPORTANT]
> 이 문서는 가장 최신 버전의 .NET용 Azure SDK를 사용하는 클라이언트 라이브러리에 적용됩니다. 라이브러리가 지원되는지 확인하려면 [Azure SDK 최신 릴리스](https://azure.github.io/azure-sdk/releases/latest/index.html) 목록을 참조하세요. 애플리케이션에서 이전 버전의 Azure SDK 클라이언트 라이브러리를 사용하는 경우 해당 서비스 설명서의 특정 지침을 참조하세요.

## <a name="log-information"></a>로그 정보

SDK는 다음 정보를 로그하고, 매개 변수 쿼리 및 헤더 값을 삭제하여 개인 데이터를 제거합니다.

HTTP 요청 로그 항목:

- 고유 ID
- HTTP 메서드
- URI
- 나가는 요청 헤더

HTTP 응답 로그 항목:

- I/O 작업 기간(경과 시간)
- 요청 ID
- HTTP 상태 코드
- HTTP 이유 구문
- 응답 헤더
- 오류 정보(해당하는 경우)

요청 및 응답 콘텐츠:

- 콘텐츠 형식 헤더에 따라 텍스트 또는 바이트로된 콘텐츠 스트림입니다.
     > [!참고} 콘텐츠 로깅은 기본적으로 사용하지 않도록 설정되어 있습니다. 사용하도록 설정하려면 `ClientOptions`에서 `Diagnostics.IsLoggingContentEnabled`를 `true`로 설정합니다.

이벤트 로그는 일반적으로 다음 세 가지 수준 중 하나에서 출력됩니다.

- 요청 및 응답 이벤트에 대한 정보
- 오류에 대한 경고
- 자세한 메시지 및 콘텐츠 로깅에 대한 자세한 정보

## <a name="enable-logging-with-built-in-methods"></a>기본 제공 메서드를 사용하여 로깅 사용

.NET용 Azure SDK 클라이언트 라이브러리는 .NET에서 일반적인 [`EventSource` 클래스](/dotnet/api/system.diagnostics.tracing.eventsource)를 통해 ETW(Windows용 이벤트 추적)에 이벤트를 로그합니다. 이벤트 소스를 사용하면 최소한의 성능 오버헤드로 애플리케이션 코드에서 구조적 로깅을 사용할 수 있습니다. 이러한 이벤트 로그에 대한 액세스 권한을 얻으려면 이벤트 수신기를 등록해야 합니다.

SDK에는 .NET 애플리케이션에 대한 포괄적인 로깅을 간소화하는 두 개의 정적 메서드인 `CreateConsoleLogger` 및 `CreateTraceLogger`를 포함하는 `Azure.Core.Diagnostics.AzureEventSourceListener` 클래스(Azure.Core NuGet 패키지에 정의됨)가 포함되어 있습니다. 이러한 메서드는 로그 수준을 지정하는 선택적 매개 변수를 사용합니다.

### <a name="log-to-the-console-window"></a>콘솔 창에 로그

.NET용 Azure SDK 클라이언트 라이브러리의 핵심 개념은 실시간으로 포괄적인 로그를 보는 기능을 간소화하는 것입니다. `CreateConsoleLogger` 메서드를 사용하면 한 줄의 코드로 로그를 콘솔 창에 보낼 수 있습니다.

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a>진단 추적에 로그

추적 수신기를 구현하는 경우 `CreateTraceLogger` 메서드를 사용하여 표준 .NET 이벤트 추적 메커니즘([`System.Diagnostics.Tracing`](/dotnet/api/system.diagnostics.tracing))에 로그할 수 있습니다. .NET의 이벤트 추적에 대한 자세한 내용은 [추적 수신기](../framework/debug-trace-profile/trace-listeners.md)를 참조하세요. 이 예제에서는 자세한 로그 수준을 지정합니다.

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a>사용자 지정 로깅 구성

위에서 설명한 것처럼 .NET용 Azure SDK에서 로그 메시지를 수신하려면 이벤트 수신기를 등록해야 합니다. 위의 단순화된 메서드 중 하나를 사용하여 포괄적인 로깅을 구현하지 않으려는 경우 `AzureEventSourceListener` 클래스의 인스턴스를 생성하고 작성한 콜백 함수를 전달할 수 있습니다. 이 메서드는 처리할 수 있는 로그 메시지를 수신하지만 필요합니다. 또한 인스턴스를 생성할 때 포함할 로그 수준을 지정할 수 있습니다.

다음 예제에서는 사용자 지정 메시지를 사용하여 콘솔에 로그하고 수준 세부 정보의 Azure 핵심 이벤트로 필터링되는 이벤트 수신기를 만듭니다.

```csharp
using AzureEventSourceListener listener = new AzureEventSourceListener((e, message) =>
    {
        // Only log messages from Azure-Core event source
        if (e.EventSource.Name == "Azure-Core")
        {
            Console.WriteLine($"{DateTime.Now} {message}");
        }
    },
    level: EventLevel.Verbose);
```

## <a name="next-steps"></a>다음 단계

- [Azure App Service에서 앱에 대한 진단 로깅 사용](/azure/app-service/troubleshoot-diagnostic-logs)
- [Azure 보안 로깅 및 감사](/azure/security/fundamentals/log-audit) 옵션 검토
- [Azure 플랫폼 로그](/azure/azure-monitor/platform/platform-logs-overview)를 사용하는 방법 알아보기
- [.NET Core 로깅 및 추적](../core/diagnostics/logging-tracing.md)에 대해 자세히 알아보기
