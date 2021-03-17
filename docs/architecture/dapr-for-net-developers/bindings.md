---
title: 6Apr 바인딩 빌딩 블록
description: 바인딩 구성 요소에 대 한 설명, 해당 기능, 이점 및 적용 방법
author: edwinvw
ms.date: 02/17/2021
ms.openlocfilehash: d6f8b2aa90b15e5b9cd7b5c29938660d1b2907e9
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623956"
---
# <a name="the-dapr-bindings-building-block"></a>6Apr 바인딩 빌딩 블록

Azure Functions 및 AWS 람다와 같은 클라우드 기반 *서버* 를 사용 하지 않는 제품은 분산 아키텍처 공간 전반에서 널리 채택 하 고 있습니다. 많은 이점 중에서 마이크로 서비스는 외부 시스템에서 *이벤트를 처리* 하거나 이벤트를 *호출* 하 여 기본 복잡성 및 배관 문제를 추상화 하는 데 사용할 수 있습니다. 외부 리소스는 다양 한 플랫폼과 공급 업체에 걸친 데이터 저장소, 메시지 시스템 및 웹 리소스를 포함 합니다. Doorstep [구성](https://docs.dapr.io/developing-applications/building-blocks/bindings/bindings-overview/) 요소는이 두 개의 응용 프로그램에 대 한 동일한 리소스 바인딩 기능을 제공 합니다.

## <a name="what-it-solves"></a>해결 방법

서비스는 서버를 사용 하 여 직접 응용 프로그램 외부에서 외부 리소스에 비즈니스 작업을 통합할 수 있습니다. 외부 시스템의 이벤트가 컨텍스트 정보를 전달 하는 서비스에서 작업을 트리거할 수 있습니다. 그러면 서비스는 다른 외부 시스템에서 이벤트를 트리거하여 컨텍스트 페이로드 정보를 전달 하 여 작업을 확장할 수 있습니다. 서비스는 외부 리소스를 결합 하거나 인식 하지 않고 통신 합니다. 이러한 통로는 미리 정의 된 Aa4 구성 요소 내에 캡슐화 됩니다. 사용할 4Apr 구성 요소는 코드 변경 없이 런타임에 쉽게 바꿀 수 있습니다.

예를 들어 사용자가 키워드를 트 윗 때마다 이벤트를 트리거하는 Twitter 계정을 고려 합니다. 서비스는 트 윗를 수신 하 고 처리 하는 이벤트 처리기를 노출 합니다. 완료 되 면 서비스에서 외부 Twilio 서비스를 호출 하는 이벤트를 트리거합니다. Twilio는 트 윗를 포함 하는 SMS 메시지를 보냅니다. 그림 8-1에서는이 작업의 개념적 아키텍처를 보여 줍니다.

![입력 바인딩](media/bindings/bindings-architecture.png)

**그림 8-1**. Eapr 리소스 바인딩의 개념적 아키텍처입니다.

처음에는이 책의 앞부분에서 설명한 [게시/구독 패턴과](publish-subscribe.md) 비슷한 방법으로 리소스 바인딩 동작이 표시 될 수 있습니다. 유사성을 공유 하는 경우 차이점이 있습니다. 게시/구독은 Eapr 서비스 간의 비동기 통신을 중심으로 합니다. 리소스 바인딩의 범위는 훨씬 더 큽니다. 소프트웨어 플랫폼 간의 시스템 상호 운용성에 중점을 둔 것입니다. 마이크로 서비스 응용 프로그램 외부의 서로 다른 응용 프로그램, 데이터 저장소 및 서비스 간에 정보를 교환 합니다.

## <a name="how-it-works"></a>작동 방식

Eapr 리소스 바인딩은 구성 요소 구성 파일로 시작 합니다. 이 YAML 파일은 구성 설정과 함께 바인딩할 리소스의 유형을 설명 합니다. 구성 된 서비스는 리소스에서 이벤트를 받거나 이벤트를 트리거할 수 있습니다.

> [!NOTE]
> 바인딩 구성은 나중에 *구성 요소* 섹션에서 자세히 설명 합니다.

### <a name="input-bindings"></a>입력 바인딩

입력 바인딩은 외부 리소스에서 들어오는 이벤트를 사용 하 여 코드를 트리거합니다. 이벤트 및 데이터를 수신 하려면 *이벤트 처리기* 가 되는 서비스에서 공용 끝점을 등록 합니다. 그림 8-2은 흐름을 보여 줍니다.

![6apr 입력 바인딩 흐름](media/bindings/input-binding-flow.png)

**그림 8-2**. 6apr 입력 바인딩 흐름입니다.

그림 8.2에서는 외부 Twitter 계정에서 이벤트를 수신 하는 단계를 설명 합니다.

1. D Apr 사이드카는 바인딩 구성 파일을 읽고 외부 리소스에 대해 지정 된 이벤트를 구독 합니다. 예제에서 이벤트 원본은 Twitter 계정입니다.
1. 일치 하는 트 윗이 Twitter에 게시 되 면, 사이드카에서 실행 되는 바인딩 구성 요소에서 이벤트를 선택 하 고 트리거합니다.
1. 사이드카는 바인딩에 대해 구성 된 끝점 (즉, 이벤트 처리기)을 호출 합니다. 이 예제에서 서비스는 `/tweet` 포트 6000에서 끝점에 대 한 HTTP POST를 수신 대기 합니다. HTTP POST 작업 이므로 이벤트의 JSON 페이로드가 요청 본문으로 전달 됩니다.
1. 이벤트를 처리 한 후 서비스에서 HTTP 상태 코드를 반환 합니다 `200 OK` .

다음 ASP.NET Core 컨트롤러는 Twitter 바인딩에 의해 트리거되는 이벤트를 처리 하는 예제를 제공 합니다.

```csharp
[ApiController]
public class SomeController : ControllerBase
{
    public class TwitterTweet
    {
        [JsonPropertyName("id_str")]
        public string ID {get; set; }

        [JsonPropertyName("text")]
        public string Text {get; set; }
    }

    [HttpPost("/tweet")]
    public ActionResult Post(TwitterTweet tweet)
    {
        // Handle tweet
        Console.WriteLine("Tweet received: {0}: {1}", tweet.ID, tweet.Text);

        // ...

        // Acknowledge message
        return Ok();
    }
}
```

작업에 오류가 발생 하는 경우 적절 한 400 또는 500 수준 HTTP 상태 코드를 반환 합니다. *최소 한 번의 배달* 보장 기능을 제공 하는 바인딩의 경우, 사이드카는 트리거를 다시 시도 합니다. [1]을 (를) 확인 하 여 *최소 한 번* 또는 *정확히 한 번* 의 배달 보장을 제공 하는지 확인 합니다.

### <a name="output-bindings"></a>출력 바인딩

또한 6apr에는 *출력 바인딩* 기능이 포함 되어 있습니다. 이를 통해 서비스는 외부 리소스를 호출 하는 이벤트를 트리거할 수 있습니다. 다시, 출력 바인딩을 설명 하는 바인딩 구성 YAML 파일을 구성 하 여 시작 합니다. 응용 프로그램의 Gapr 사이드카에서 바인딩 API를 호출 하는 이벤트를 트리거합니다. 그림 8-3에서는 출력 바인딩의 흐름을 보여 줍니다.

![6apr 출력 바인딩 흐름](media/bindings/output-binding-flow.png)

**그림 8-3**. 6apr 출력 바인딩 흐름입니다.

1. 사이드카는 외부 리소스에 연결 하는 방법에 대 한 정보를 사용 하 여 바인딩 구성 파일을 읽습니다. 예제에서 외부 리소스는 Twilio SMS 계정입니다.
1. 응용 프로그램은 `/v1.0/bindings/sms` 사이드카에서 끝점을 호출 합니다. 이 경우 HTTP POST를 사용 하 여 API를 호출 합니다. GRPC를 사용할 수도 있습니다.
1. D Apr 사이드카에서 실행 되는 바인딩 구성 요소는 메시지를 보내는 외부 메시징 시스템을 호출 합니다. 메시지에는 POST 요청에 전달 된 페이로드가 포함 됩니다.

예를 들어, 말아 2-a를 사용 하 여 Eapr API를 호출 하 여 출력 바인딩을 호출할 수 있습니다.

```console
curl -X POST http://localhost:3500/v1.0/bindings/sms \
  -H "Content-Type: application/json" \
  -d '{
        "data": "Welcome to this awesome service",
        "metadata": {
          "toNumber": "555-3277"
        },
        "operation": "create"
      }'
```

HTTP 포트는 Eapr 사이드카에서 사용 하는 것과 동일 합니다 (이 경우 기본 Eapr HTTP 포트 `3500` ).

페이로드의 구조 (즉, 전송 되는 메시지)는 바인딩 마다 다릅니다. 위의 예제에서 페이로드는 메시지를 포함 하는 요소를 포함 합니다 `data` . 다른 형식의 외부 리소스에 대 한 바인딩은 특히 전송 되는 메타 데이터의 경우 다를 수 있습니다. 각 페이로드에는 `operation` 바인딩이 실행 되는 작업을 정의 하는 필드도 포함 되어야 합니다. 위의 예에서는 `create` SMS 메시지를 만드는 작업을 지정 합니다. 일반적인 작업은 다음과 같습니다.

- create
- Get
- delete
- list

바인딩에서 지 원하는 작업의 작성자에 게 있습니다. 각 바인딩에 대 한 설명서에서는 사용 가능한 작업과 해당 작업을 호출 하는 방법을 설명 합니다.

## <a name="using-the-dapr-net-sdk"></a>Dapr .NET SDK 사용

Dapr .NET SDK는 .NET Core 개발자를 위한 언어 관련 지원을 제공 합니다. 다음 예제에서는에 대 한 호출이 `HttpClient.PostAsync()` 메서드로 대체 됩니다 `DaprClient.InvokeBindingAsync()` . 이 특수 메서드는 구성 된 출력 바인딩 호출을 간소화 합니다.

```csharp
private async Task SendSMSAsync([FromServices] DaprClient daprClient)
{
    var message = "Welcome to this awesome service";
    var metadata = new Dictionary<string, string>
    {
      { "toNumber", "555-3277" }
    };
    await daprClient.InvokeBindingAsync("sms", "create", message, metadata);
}
```

메서드에는 `metadata` 및 값이 필요 `message` 합니다.

바인딩을 호출 하는 데 사용 되는 경우는 `DaprClient` gRPC를 사용 하 여 사이드카에서 EAPR API를 호출 합니다.

## <a name="binding-components"></a>바인딩 구성 요소

내부적으로 리소스 바인딩은 Eapr 바인딩 구성 요소를 사용 하 여 구현 됩니다. 이들은 커뮤니티에서 제공 하 고 Go로 작성 되었습니다. 아직 Eapr 바인딩이 존재 하지 않는 외부 리소스와 통합 해야 하는 경우 직접 만들 수 있습니다. D 4의 [구성 요소](https://github.com/dapr/components-contrib) 를 확인 하 여 바인딩에 기여할 수 있는 방법을 확인 합니다.

> [!NOTE]
> Eapr 및 모든 구성 요소는 [Golang](https://golang.org/) (Go) 언어로 작성 됩니다. Go는 최신 클라우드 네이티브 프로그래밍 플랫폼으로 간주 됩니다.

YAML 구성 파일을 사용 하 여 바인딩을 구성 합니다. Twitter 바인딩에 대 한 구성 예제는 다음과 같습니다.

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: twitter-mention
  namespace: default
spec:
  type: bindings.twitter
  version: v1
  metadata:
  - name: consumerKey
    value: "****" # twitter api consumer key, required
  - name: consumerSecret
    value: "****" # twitter api consumer secret, required
  - name: accessToken
    value: "****" # twitter api access token, required
  - name: accessSecret
    value: "****" # twitter api access secret, required
  - name: query
    value: "dapr" # your search query, required
```

각 바인딩 구성에 `metadata` 는 및 필드가 있는 일반 요소가 포함 `name` `namespace` 됩니다. 구성 된 필드에 따라 서비스를 호출 하는 끝점을 결정 합니다 `name` . 위의 예제에서, C4는 이벤트가 발생할 때 서비스에서로 주석이 지정 된 메서드를 호출 `/twitter-mention` 합니다.

요소에서 바인딩과 `spec` 함께 바인딩의를 지정 `type` `metadata` 합니다. 이 예제에서는 해당 API를 사용 하 여 Twitter 계정에 액세스 하기 위한 자격 증명을 지정 합니다. 메타 데이터는 입력 및 출력 바인딩 간에 다를 수 있습니다. 예를 들어 입력 바인딩으로 Twitter를 사용 하려면 트 윗에서 필드를 사용 하 여 검색할 텍스트를 지정 해야 합니다 `query` . 일치 하는 트 윗가 전송 될 때마다 사이드카는 `/twitter-mention` 서비스에서 끝점을 호출 합니다. 트 윗의 내용도 전달 됩니다.

바인딩은 입력, 출력 또는 둘 다로 구성할 수 있습니다. 흥미롭게도 바인딩에서는 입력 또는 출력 구성을 명시적으로 지정 하지 않습니다. 대신 구성 값과 함께 바인딩을 사용 하 여 방향이 유추 됩니다.

[리소스 바인딩에 대 한 4Apr 설명서] [1]는 사용 가능한 바인딩 및 해당 특정 구성 설정의 전체 목록을 제공 합니다.

### <a name="cron-binding"></a>Cron 바인딩

Eapr의 Cron 바인딩에 주의 하세요. 외부 시스템의 이벤트를 구독 하지 않습니다. 대신이 바인딩은 구성 가능한 간격 일정을 사용 하 여 응용 프로그램을 트리거합니다. 바인딩은 구성 가능한 지연 시간을 사용 하 여 무한 루프를 구현할 필요 없이 절전 모드를 해제 하 고 일정 한 간격으로 작업을 수행할 수 있는 간단한 방법을 제공 합니다. Cron 바인딩 구성의 예는 다음과 같습니다.

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: checkOrderBacklog
  namespace: default
spec:
  type: bindings.cron
  version: v1
  metadata:
  - name: schedule
    value: "@every 30m"
```

이 예제에서 d 4는 `/checkOrderBacklog` 30 분 마다 끝점을 호출 하 여 서비스를 트리거합니다. 값을 지정 하는 데 사용할 수 있는 몇 가지 패턴이 있습니다 `schedule` . 자세한 내용은 [Cron binding 설명서](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/cron/)를 참조 하세요.

## <a name="reference-application-eshopondapr"></a>참조 응용 프로그램: eShopOnDapr

함께 제공 되는 eShopOnDapr reference 응용 프로그램은 출력 바인딩 예제를 구현 합니다. 새 주문이 배치 될 때 사용자에 게 전자 메일을 보내는 데 사용 하는 Eapr [SendGrid](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/sendgrid/) 바인딩을 트리거합니다. 이 바인딩은 `eshop-email.yaml` 파일의 구성 요소 폴더에서 찾을 수 있습니다.

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: sendmail
  namespace: eshop
spec:
  type: bindings.twilio.sendgrid
  version: v1
  metadata:
  - name: apiKey
    secretKeyRef:
      name: sendGridAPIKey
auth:
  secretStore: eshop-secretstore
```

이 구성은 [Twilio SendGrid](https://github.com/dapr/components-contrib/tree/master/bindings/twilio) binding 구성 요소를 사용 합니다. 서비스에 연결 하기 위한 API 키가 Eapr 비밀 참조를 사용 하는 방법에 유의 하세요. 이 접근 방식은 구성 파일 외부에서 비밀을 유지 합니다. Eapr 암호에 대 한 자세한 내용은 [비밀 빌딩 블록 챕터](secrets.md) 를 참조 하세요.

바인딩 구성은 사이드카의 끝점을 사용 하 여 호출할 수 있는 바인딩 구성 요소를 지정 합니다 `/sendmail` . 주문이 시작 될 때마다 전자 메일을 전송 하는 코드 조각은 다음과 같습니다.

```csharp
public Task Handle(OrderStartedDomainEvent notification, CancellationToken cancellationToken)
{
    var string message = CreateEmailBody(notification);
    var metadata = new Dictionary<string, string>
    {
        {"emailFrom", "eShopOn@dapr.io"},
        {"emailTo", notification.UserName},
        {"subject", $"Your eShopOnDapr order #{notification.Order.Id}"}
    };
    return _daprClient.InvokeBindingAsync("sendmail", "create", message, metadata, cancellationToken);
}
```

이 예제에서 볼 수 있듯이에 `message` 는 메시지 본문이 포함 되어 있습니다. `CreateEmailBody`메서드는 단순히 본문 텍스트를 사용 하 여 문자열의 형식을 지정 합니다. 는 전자 `metadata` 메일 보낸 사람, 받는 사람 및 전자 메일 메시지의 제목을 지정 합니다. 이러한 값이 정적 이면 구성 파일의 메타 데이터 필드에도 포함 될 수 있습니다. 호출할 바인딩의 이름이이 `sendmail` 고 작업은 `create` 입니다.

## <a name="summary"></a>요약

Eapr 리소스 바인딩을 사용 하면 라이브러리 또는 Sdk에 대 한 종속성을 취하지 않고 다른 외부 리소스 및 시스템과 통합할 수 있습니다. 이러한 외부 시스템은 서비스 버스 또는 메시지 브로커와 같은 메시징 시스템이 아니어도 됩니다. 또한 데이터 저장소와 Twitter 또는 SendGrid 같은 웹 리소스에 대 한 바인딩이 있습니다.

입력 바인딩 또는 트리거는 외부 시스템에서 발생 하는 이벤트에 대응 합니다. 응용 프로그램에서 미리 구성 된 공용 HTTP 끝점을 호출 합니다. 6apr는 구성의 바인딩 이름을 사용 하 여 응용 프로그램에서 호출할 끝점을 결정 합니다.

출력 바인딩은 외부 시스템으로 메시지를 보냅니다. Tapr 사이드카의 끝점에서 HTTP POST를 수행 하 여 출력 바인딩을 트리거합니다 `/v1.0/bindings/<binding-name>` . GRPC를 사용 하 여 바인딩을 호출할 수도 있습니다. .NET SDK는 `InvokeBindingAsync` gRPC를 사용 하 여 Dapr 바인딩을 호출 하는 메서드를 제공 합니다.

Wapr 구성 요소를 사용 하 여 바인딩을 구현 합니다. 이러한 구성 요소는 커뮤니티에 의해 제공 됩니다. 각 바인딩 구성 요소의 구성에는 추상화 하는 외부 시스템에 특정 한 메타 데이터가 있습니다. 또한 지원 되는 명령과 페이로드의 구조는 바인딩 구성 요소 마다 다릅니다.

### <a name="references"></a>참조

- [리소스 바인딩에 대 한 4apr 설명서](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/)

>[!div class="step-by-step"]
>[이전](publish-subscribe.md)
>[다음](observability.md)
