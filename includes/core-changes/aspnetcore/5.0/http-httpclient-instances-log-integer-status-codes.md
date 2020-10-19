---
ms.openlocfilehash: f1556fac0e8aa79c87cd5e74c1b603582ff5db1b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160548"
---
### <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a>HTTP: IHttpClientFactory 로그 정수 상태 코드에서 생성된 HttpClient 인스턴스

<xref:System.Net.Http.IHttpClientFactory>에서 생성된 <xref:System.Net.Http.HttpClient> 인스턴스는 상태 코드 이름이 아니라 정수로 HTTP 상태 코드를 기록합니다.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 1

#### <a name="old-behavior"></a>이전 동작

로깅은 HTTP 상태 코드의 텍스트 설명을 사용합니다. 다음 로그 메시지를 고려하세요.

```output
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

#### <a name="new-behavior"></a>새 동작

로깅은 HTTP 상태 코드의 정수 값을 사용합니다. 다음 로그 메시지를 고려하세요.

```output
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

#### <a name="reason-for-change"></a>변경 이유

이 로깅의 원래 동작은 항상 정수 값을 사용한 ASP.NET Core의 다른 부분과 일치하지 않습니다. 불일치로 인해 로그는 [Elasticsearch](https://www.elastic.co/elasticsearch/)와 같은 구조화된 로깅 시스템을 통해 쿼리하기 어려워집니다. 자세한 컨텍스트는 [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549)를 참조하세요.

정수 값을 사용하면 값 범위에서 쿼리가 허용되므로 텍스트보다 더 유연합니다.

정수 상태 코드를 캡처할 다른 로그 값을 추가하는 것이 고려되었습니다. 안타깝게도 이렇게 하면 나머지 ASP.NET Core와 또 다른 불일치가 발생합니다. HttpClient 로깅 및 HTTP 서버/호스팅 로깅은 이미 동일한 `StatusCode` 키 이름을 사용합니다.

#### <a name="recommended-action"></a>권장 조치

가장 좋은 방법은 상태 코드의 정수 값을 사용하도록 로깅 쿼리를 업데이트하는 것입니다. 이 옵션을 선택하면 여러 ASP.NET Core 버전에 걸쳐 쿼리를 작성하기 어려울 수 있습니다. 그러나 이 목적으로 정수를 사용하면 로그 쿼리 시 훨씬 더 유연합니다.

이전 동작과의 호환성을 적용하고 텍스트 상태 코드를 사용해야 하는 경우 `IHttpClientFactory` 로깅을 고유한 항목으로 바꿉니다.

1. 다음 클래스의 .NET Core 3.1 버전을 프로젝트에 복사합니다.

    * [LoggingHttpMessageHandlerBuilderFilter](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [LoggingHttpMessageHandler](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [LoggingScopeHttpMessageHandler](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [HttpHeadersLogValue](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http) NuGet 패키지에서 퍼블릭 형식과 충돌하지 않도록 클래스 이름을 바꿉니다.

1. `LoggingHttpMessageHandlerBuilderFilter`의 기본 제공 구현을 프로젝트의 `Startup.ConfigureServices` 메서드에 있는 고유한 항목으로 바꿉니다. 예를 들어:

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        // Other service registrations go first. Code omitted for brevity.

        // Place the following after all AddHttpClient registrations.
        services.RemoveAll<IHttpMessageHandlerBuilderFilter>();

        services.AddSingleton<IHttpMessageHandlerBuilderFilter,
                              MyLoggingHttpMessageHandlerBuilderFilter>();
    }
    ```

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:System.Net.Http.HttpClient`

-->
