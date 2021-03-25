---
title: Polly를 통해 지수 백오프를 사용하여 HTTP 호출 다시 시도 구현
description: Polly와 IHttpClientFactory를 사용하여 HTTP 오류를 처리하는 방법을 알아봅니다.
ms.date: 01/13/2021
ms.openlocfilehash: c2831f73ed38b48fd32fa241f8fe1792b9adf3d4
ms.sourcegitcommit: 1d3af230ec30d8d061be7a887f6ba38a530c4ece
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511790"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-ihttpclientfactory-and-polly-policies"></a>IHttpClientFactory 및 Polly 정책을 통해 지수 백오프를 사용하여 HTTP 호출 다시 시도 구현

지수 백오프를 사용하는 다시 시도는 오픈 소스 [Polly 라이브러리](https://github.com/App-vNext/Polly)와 같은 고급 .NET 라이브러리를 활용하는 것이 좋습니다.

Polly는 복원력 및 일시적인 오류 처리 기능을 제공하는 .NET 라이브러리입니다. 다시 시도, 회로 차단기, 격벽(Bulkhead) 격리, 시간 제한 및 대체와 같은 Polly 정책을 적용하여 이러한 기능을 구현할 수 있습니다. Polly는 .NET Framework 4.x 및 .NET Standard 1.0, 1.1 및 2.0(.NET Core 이상 지원)을 대상으로 합니다.

다음 단계에서는 이전 섹션에서 설명한 `IHttpClientFactory`에 통합된 Polly를 통해 Http 다시 시도를 사용하는 방법을 보여 줍니다.

**.NET 5 패키지 참조**

`IHttpClientFactory`는 .NET Core 2.1부터 사용할 수 있지만 프로젝트에서 NuGet의 최신 .NET Core 5 패키지를 사용하는 것이 좋습니다. 또한 일반적으로 확장 패키지 `Microsoft.Extensions.Http.Polly`를 참조해야 합니다.

**시작 시 Polly의 재시도 정책을 사용하여 클라이언트 구성**

이전 섹션과 같이 표준 Startup.ConfigureServices(...) 메서드에서 명명되거나 형식화된 클라이언트 HttpClient 구성을 정의해야 하지만, 이제는 아래와 같이 지수 백오프를 사용하는 Http 다시 시도에 대한 정책을 지정하는 증분 코드를 추가합니다.

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

**AddPolicyHandler()** 는 사용할 `HttpClient` 개체에 정책을 추가하는 메서드입니다. 이 경우 지수 백오프를 사용하는 HTTP 다시 시도에 대한 Polly 정책을 추가합니다.

좀 더 모듈화된 방법을 사용하기 위해 HTTP 재시도 정책은 다음 코드와 같이 `Startup.cs` 파일 내에서 별도의 메서드로 정의할 수 있습니다.

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2,
                                                                    retryAttempt)));
}
```

Polly를 사용하면 HTTP 예외(예: 오류 로깅)가 발생하는 경우 수행할 다시 시도 횟수, 지수 백오프 구성 및 작업이 포함된 재시도 정책을 정의할 수 있습니다. 이 경우 정책은 2초에서 시작하여 지수 다시 시도를 6회 시도하도록 구성됩니다.

## <a name="add-a-jitter-strategy-to-the-retry-policy"></a>재시도 정책에 지터 전략 추가

일반 재시도 정책은 동시성, 확장성 및 경합이 높은 경우 시스템에 영향을 미칠 수 있습니다. 부분 작동 중단 상황에서 여러 클라이언트로부터 유사한 재시도가 대규모로 발생하는 문제를 해결하기 위해 재시도 알고리즘/정책에 지터 전략을 추가하면 좋습니다. 이렇게 하면 지수 백오프에 임의성을 추가하여 엔드투엔드 시스템의 전체 성능을 높일 수 있습니다. 이렇게 문제가 발생했을 때 급증 문제를 분산시킵니다. 원칙은 다음 예제에서 확인할 수 있습니다.

```csharp
Random jitterer = new Random();
var retryWithJitterPolicy = HttpPolicyExtensions
    .HandleTransientHttpError()
    .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
    .WaitAndRetryAsync(6,    // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                      + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

Polly는 프로젝트 웹 사이트를 통해 프로덕션 준비가 완료된 지터 알고리즘을 제공합니다.

## <a name="additional-resources"></a>추가 자료

- **패턴 다시 시도**  
  [https://docs.microsoft.com/azure/architecture/patterns/retry](/azure/architecture/patterns/retry)

- **Polly 및 IHttpClientFactory**  
  <https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory>

- **Polly(.NET 복원력 및 transient-fault-handling 라이브러리)**  
  <https://github.com/App-vNext/Polly>

- **Polly: 지터를 사용하여 다시 시도**  
  <https://github.com/App-vNext/Polly/wiki/Retry-with-jitter>

- **Marc Brooker. 지터: 임의성으로 작업을 더 효율적인 만들기**  
  <https://brooker.co.za/blog/2015/03/21/backoff.html>

>[!div class="step-by-step"]
>[이전](use-httpclientfactory-to-implement-resilient-http-requests.md)
>[다음](implement-circuit-breaker-pattern.md)
