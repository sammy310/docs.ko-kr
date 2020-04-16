---
title: .NET에 대한 Azure SDK로 로깅
description: .NET 클라이언트 라이브러리에 대해 Azure SDK로 로깅을 활성화하는 방법에 대해 알아봅니다.
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: b277045a60ef5cc065d77dad84878872dedc963e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433225"
---
# <a name="logging-with-the-azure-sdk-for-net"></a>.NET에 대한 Azure SDK로 로깅

.NET 클라이언트 라이브러리에 대한 [Azure SDK에는](https://azure.microsoft.com/downloads/) 클라이언트 라이브러리 작업을 기록하는 기능이 포함됩니다. 이를 통해 클라이언트 라이브러리가 Azure 서비스에 대해 하는 I/O 요청 및 응답을 모니터링할 수 있습니다. 일반적으로 로그는 통신 문제를 디버깅하거나 진단하는 데 사용됩니다. 이 문서에서는 .NET에 대한 Azure SDK로 로깅을 사용하도록 설정하는 세 가지 방법을 설명합니다.

- 콘솔 창에 로그
- .NET 진단 추적에 로그
- 사용자 지정 로깅 구성

> [!IMPORTANT]
> 이 문서는 .NET에 대한 Azure SDK의 최신 버전을 사용하는 클라이언트 라이브러리에 적용됩니다. 라이브러리가 지원되는지 확인하려면 [Azure SDK 최신 릴리스](https://azure.github.io/azure-sdk/releases/latest/index.html)목록을 참조하십시오. 응용 프로그램이 이전 버전의 Azure SDK 클라이언트 라이브러리를 사용하는 경우 해당 서비스 설명서의 특정 지침을 참조하십시오.

## <a name="log-information"></a>로그 정보

SDK는 다음 정보를 기록하여 매개 변수 쿼리 및 헤더 값을 삭제하여 개인 데이터를 제거합니다.

HTTP 요청 로그 항목:

- 고유 ID
- HTTP 메서드
- URI
- 나가는 요청 헤더

HTTP 응답 로그 항목:

- I/O 작업 시간(경과 시간)
- 요청 ID
- HTTP 상태 코드
- HTTP 이유 구
- 응답 헤더
- 오류 정보(해당하는 경우)

요청 및 응답 콘텐츠의 경우:

- 콘텐츠 유형 헤더에 따라 텍스트 또는 바이트로 콘텐츠 스트림입니다.
     > [! NOTE} 콘텐츠 로깅은 기본적으로 비활성화되어 있습니다. 활성화하려면 에서 `Diagnostics.IsLoggingContentEnabled` `true` `ClientOptions`설정합니다.

이벤트 로그는 일반적으로 다음 세 가지 수준 중 하나에서 출력됩니다.

- 요청 및 응답 이벤트에 대한 정보 제공
- 오류 경고
- 자세한 메시지 및 콘텐츠 로깅에 대한 자세한 내용

## <a name="enable-logging-with-built-in-methods"></a>기본 제공 메서드를 사용하여 로깅 사용

.NET 클라이언트 라이브러리에 대한 Azure SDK는 .NET에 대한 일반적인 [ `EventSource` 클래스를](/dotnet/api/system.diagnostics.tracing.eventsource)통해 ETW(Windows용 이벤트 추적)에 이벤트를 기록합니다. 이벤트 소스를 사용하면 최소한의 성능 오버헤드로 응용 프로그램 코드에 구조화 된 로깅을 사용할 수 있습니다. 이러한 이벤트 로그에 액세스하려면 이벤트 리스너를 등록해야 합니다.

SDK에는 .NET 응용 프로그램에 대한 포괄적인 로깅을 단순화하는 두 가지 정적 메서드가 포함된 `Azure.Core.Diagnostics.AzureEventSourceListener` 클래스(Azure.Core NuGet 패키지에 `CreateConsoleLogger` 정의됨)가 포함됩니다. `CreateTraceLogger` 이러한 메서드는 로그 수준을 지정하는 선택적 매개 변수를 사용합니다.

### <a name="log-to-the-console-window"></a>콘솔 창에 로그

.NET 클라이언트 라이브러리에 대한 Azure SDK의 핵심 원칙은 포괄적인 로그를 실시간으로 보는 기능을 단순화하는 것입니다. 이 `CreateConsoleLogger` 방법을 사용하면 한 줄의 코드로 콘솔 창으로 로그를 보낼 수 있습니다.

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a>진단 추적에 로그

추적 리스너를 구현하는 경우 이 `CreateTraceLogger` 메서드를 사용하여 표준 .NET 이벤트[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)추적 메커니즘()에 로그온할 수 있습니다. .NET에서 이벤트 추적에 대한 자세한 내용은 [추적 리스너를](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners)참조하십시오. 이 예제는 자세한 내용의 로그 수준을 지정합니다.

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a>사용자 지정 로깅 구성

위에서 언급했듯이 .NET에 대한 Azure SDK에서 로그 메시지를 수신하도록 이벤트 리스너를 등록해야 합니다. 위의 단순화된 메서드 중 하나를 사용하여 포괄적인 로깅을 구현하지 않으려면 `AzureEventSourceListener` 클래스의 인스턴스를 생성하고 작성하는 콜백 함수를 전달할 수 있습니다. 이 메서드는 처리 할 수 있는 로그 메시지를 받을 수 있습니다. 또한 인스턴스를 생성할 때 포함할 로그 수준을 지정할 수 있습니다.

다음 예제에서는 사용자 지정 메시지와 함께 콘솔에 로그온 하 고 수준 자세한 의 Azure 코어 이벤트로 필터링 되는 이벤트 수신기를 만듭니다.

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

- [Azure 앱 서비스에서 앱에 대한 진단 로깅 사용](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- [Azure 보안 로깅 및 감사](https://docs.microsoft.com/azure/security/fundamentals/log-audit) 옵션 검토
- [Azure 플랫폼 로그](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) 사용 방법 알아보기
- [.NET 코어 로깅 및 추적에](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing) 대해 자세히 알아보기
