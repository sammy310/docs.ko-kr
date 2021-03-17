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
# <a name="the-dapr-bindings-building-block"></a><span data-ttu-id="cad6b-103">6Apr 바인딩 빌딩 블록</span><span class="sxs-lookup"><span data-stu-id="cad6b-103">The Dapr bindings building block</span></span>

<span data-ttu-id="cad6b-104">Azure Functions 및 AWS 람다와 같은 클라우드 기반 *서버* 를 사용 하지 않는 제품은 분산 아키텍처 공간 전반에서 널리 채택 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-104">Cloud-based *serverless* offerings, such as Azure Functions and AWS Lambda, have gained wide adoption across the distributed architecture space.</span></span> <span data-ttu-id="cad6b-105">많은 이점 중에서 마이크로 서비스는 외부 시스템에서 *이벤트를 처리* 하거나 이벤트를 *호출* 하 여 기본 복잡성 및 배관 문제를 추상화 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-105">Among many benefits, they enable a microservice to *handle events from* or *invoke events in* an external system - abstracting away the underlying complexity and plumbing concerns.</span></span> <span data-ttu-id="cad6b-106">외부 리소스는 다양 한 플랫폼과 공급 업체에 걸친 데이터 저장소, 메시지 시스템 및 웹 리소스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-106">External resources are many: They include datastores, message systems, and web resources, across different platforms and vendors.</span></span> <span data-ttu-id="cad6b-107">Doorstep [구성](https://docs.dapr.io/developing-applications/building-blocks/bindings/bindings-overview/) 요소는이 두 개의 응용 프로그램에 대 한 동일한 리소스 바인딩 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-107">The [Dapr bindings building block](https://docs.dapr.io/developing-applications/building-blocks/bindings/bindings-overview/) brings these same resource binding capabilities to the doorstep of your Dapr applications.</span></span>

## <a name="what-it-solves"></a><span data-ttu-id="cad6b-108">해결 방법</span><span class="sxs-lookup"><span data-stu-id="cad6b-108">What it solves</span></span>

<span data-ttu-id="cad6b-109">서비스는 서버를 사용 하 여 직접 응용 프로그램 외부에서 외부 리소스에 비즈니스 작업을 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-109">Dapr resource bindings enable your services to integrate business operations across external resources outside of the immediate application.</span></span> <span data-ttu-id="cad6b-110">외부 시스템의 이벤트가 컨텍스트 정보를 전달 하는 서비스에서 작업을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-110">An event from an external system could trigger an operation in your service passing in contextual information.</span></span> <span data-ttu-id="cad6b-111">그러면 서비스는 다른 외부 시스템에서 이벤트를 트리거하여 컨텍스트 페이로드 정보를 전달 하 여 작업을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-111">Your service could then expand the operation by triggering an event in another external system, passing in contextual payload information.</span></span> <span data-ttu-id="cad6b-112">서비스는 외부 리소스를 결합 하거나 인식 하지 않고 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-112">Your service communicates without coupling or awareness of the external resource.</span></span> <span data-ttu-id="cad6b-113">이러한 통로는 미리 정의 된 Aa4 구성 요소 내에 캡슐화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-113">The plumbing is encapsulated inside pre-defined Dapr components.</span></span> <span data-ttu-id="cad6b-114">사용할 4Apr 구성 요소는 코드 변경 없이 런타임에 쉽게 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-114">The Dapr component to use can be easily swapped at runtime without code changes.</span></span>

<span data-ttu-id="cad6b-115">예를 들어 사용자가 키워드를 트 윗 때마다 이벤트를 트리거하는 Twitter 계정을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-115">Consider, for example, a Twitter account that triggers an event whenever a user tweets a keyword.</span></span> <span data-ttu-id="cad6b-116">서비스는 트 윗를 수신 하 고 처리 하는 이벤트 처리기를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-116">Your service exposes an event handler that receives and processes the tweet.</span></span> <span data-ttu-id="cad6b-117">완료 되 면 서비스에서 외부 Twilio 서비스를 호출 하는 이벤트를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-117">Once complete, your service triggers an event that invokes an external Twilio service.</span></span> <span data-ttu-id="cad6b-118">Twilio는 트 윗를 포함 하는 SMS 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-118">Twilio sends an SMS message that includes the tweet.</span></span> <span data-ttu-id="cad6b-119">그림 8-1에서는이 작업의 개념적 아키텍처를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-119">Figure 8-1 show the conceptual architecture of this operation.</span></span>

![입력 바인딩](media/bindings/bindings-architecture.png)

<span data-ttu-id="cad6b-121">**그림 8-1**.</span><span class="sxs-lookup"><span data-stu-id="cad6b-121">**Figure 8-1**.</span></span> <span data-ttu-id="cad6b-122">Eapr 리소스 바인딩의 개념적 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-122">Conceptual architecture of a Dapr resource binding.</span></span>

<span data-ttu-id="cad6b-123">처음에는이 책의 앞부분에서 설명한 [게시/구독 패턴과](publish-subscribe.md) 비슷한 방법으로 리소스 바인딩 동작이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-123">At first glance, resource binding behavior may appear similar to the [Publish/Subscribe pattern](publish-subscribe.md) described earlier in this book.</span></span> <span data-ttu-id="cad6b-124">유사성을 공유 하는 경우 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-124">While they share similarities, there are differences.</span></span> <span data-ttu-id="cad6b-125">게시/구독은 Eapr 서비스 간의 비동기 통신을 중심으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-125">Publish/subscribe focuses on asynchronous communication between Dapr services.</span></span> <span data-ttu-id="cad6b-126">리소스 바인딩의 범위는 훨씬 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-126">Resource binding has a much wider scope.</span></span> <span data-ttu-id="cad6b-127">소프트웨어 플랫폼 간의 시스템 상호 운용성에 중점을 둔 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-127">It focuses on system interoperability across software platforms.</span></span> <span data-ttu-id="cad6b-128">마이크로 서비스 응용 프로그램 외부의 서로 다른 응용 프로그램, 데이터 저장소 및 서비스 간에 정보를 교환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-128">Exchanging information between disparate applications, datastores, and services outside your microservice application.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="cad6b-129">작동 방식</span><span class="sxs-lookup"><span data-stu-id="cad6b-129">How it works</span></span>

<span data-ttu-id="cad6b-130">Eapr 리소스 바인딩은 구성 요소 구성 파일로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-130">Dapr resource binding starts with a component configuration file.</span></span> <span data-ttu-id="cad6b-131">이 YAML 파일은 구성 설정과 함께 바인딩할 리소스의 유형을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-131">This YAML file describes the type of resource to which you'll bind along with its configuration settings.</span></span> <span data-ttu-id="cad6b-132">구성 된 서비스는 리소스에서 이벤트를 받거나 이벤트를 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-132">Once configured, your service can receive events from the resource or trigger events on it.</span></span>

> [!NOTE]
> <span data-ttu-id="cad6b-133">바인딩 구성은 나중에 *구성 요소* 섹션에서 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-133">Binding configurations are presented in detail later in the *Components* section.</span></span>

### <a name="input-bindings"></a><span data-ttu-id="cad6b-134">입력 바인딩</span><span class="sxs-lookup"><span data-stu-id="cad6b-134">Input bindings</span></span>

<span data-ttu-id="cad6b-135">입력 바인딩은 외부 리소스에서 들어오는 이벤트를 사용 하 여 코드를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-135">Input bindings trigger your code with incoming events from external resources.</span></span> <span data-ttu-id="cad6b-136">이벤트 및 데이터를 수신 하려면 *이벤트 처리기* 가 되는 서비스에서 공용 끝점을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-136">To receive events and data, you register a public endpoint from your service that becomes the *event handler*.</span></span> <span data-ttu-id="cad6b-137">그림 8-2은 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-137">Figure 8-2 shows the flow:</span></span>

![6apr 입력 바인딩 흐름](media/bindings/input-binding-flow.png)

<span data-ttu-id="cad6b-139">**그림 8-2**.</span><span class="sxs-lookup"><span data-stu-id="cad6b-139">**Figure 8-2**.</span></span> <span data-ttu-id="cad6b-140">6apr 입력 바인딩 흐름입니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-140">Dapr input binding flow.</span></span>

<span data-ttu-id="cad6b-141">그림 8.2에서는 외부 Twitter 계정에서 이벤트를 수신 하는 단계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-141">Figure 8.2 describes the steps for receiving events from an external Twitter account:</span></span>

1. <span data-ttu-id="cad6b-142">D Apr 사이드카는 바인딩 구성 파일을 읽고 외부 리소스에 대해 지정 된 이벤트를 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-142">The Dapr sidecar reads the binding configuration file and subscribes to the event specified for the external resource.</span></span> <span data-ttu-id="cad6b-143">예제에서 이벤트 원본은 Twitter 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-143">In the example, the event source is a Twitter account.</span></span>
1. <span data-ttu-id="cad6b-144">일치 하는 트 윗이 Twitter에 게시 되 면, 사이드카에서 실행 되는 바인딩 구성 요소에서 이벤트를 선택 하 고 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-144">When a matching Tweet is published on Twitter, the binding component running in the Dapr sidecar picks it up and triggers an event.</span></span>
1. <span data-ttu-id="cad6b-145">사이드카는 바인딩에 대해 구성 된 끝점 (즉, 이벤트 처리기)을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-145">The Dapr sidecar invokes the endpoint (that is, event handler) configured for the binding.</span></span> <span data-ttu-id="cad6b-146">이 예제에서 서비스는 `/tweet` 포트 6000에서 끝점에 대 한 HTTP POST를 수신 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-146">In the example, the service listens for an HTTP POST on the `/tweet` endpoint on port 6000.</span></span> <span data-ttu-id="cad6b-147">HTTP POST 작업 이므로 이벤트의 JSON 페이로드가 요청 본문으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-147">Because it's an HTTP POST operation, the JSON payload for the event is passed in the request body.</span></span>
1. <span data-ttu-id="cad6b-148">이벤트를 처리 한 후 서비스에서 HTTP 상태 코드를 반환 합니다 `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="cad6b-148">After handling the event, the service returns an HTTP status code `200 OK`.</span></span>

<span data-ttu-id="cad6b-149">다음 ASP.NET Core 컨트롤러는 Twitter 바인딩에 의해 트리거되는 이벤트를 처리 하는 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-149">The following ASP.NET Core controller provides an example of handling an event triggered by the Twitter binding:</span></span>

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

<span data-ttu-id="cad6b-150">작업에 오류가 발생 하는 경우 적절 한 400 또는 500 수준 HTTP 상태 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-150">If the operation should error, you would return the appropriate 400 or 500 level HTTP status code.</span></span> <span data-ttu-id="cad6b-151">*최소 한 번의 배달* 보장 기능을 제공 하는 바인딩의 경우, 사이드카는 트리거를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-151">For bindings that feature *at-least-once-delivery* guarantees, the Dapr sidecar will retry the trigger.</span></span> <span data-ttu-id="cad6b-152">[1]을 (를) 확인 하 여 *최소 한 번* 또는 *정확히 한 번* 의 배달 보장을 제공 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-152">Check out [Dapr documentation for resource bindings][1] to see whether they offer *at-least-once* or *exactly-once* delivery guarantees.</span></span>

### <a name="output-bindings"></a><span data-ttu-id="cad6b-153">출력 바인딩</span><span class="sxs-lookup"><span data-stu-id="cad6b-153">Output bindings</span></span>

<span data-ttu-id="cad6b-154">또한 6apr에는 *출력 바인딩* 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-154">Dapr also includes *output binding* capabilities.</span></span> <span data-ttu-id="cad6b-155">이를 통해 서비스는 외부 리소스를 호출 하는 이벤트를 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-155">They enable your service to trigger an event that invokes an external resource.</span></span> <span data-ttu-id="cad6b-156">다시, 출력 바인딩을 설명 하는 바인딩 구성 YAML 파일을 구성 하 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-156">Again, you start by configuring a binding configuration YAML file that describes the output binding.</span></span> <span data-ttu-id="cad6b-157">응용 프로그램의 Gapr 사이드카에서 바인딩 API를 호출 하는 이벤트를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-157">Once in place, you trigger an event that invokes the bindings API on the Dapr sidecar of your application.</span></span> <span data-ttu-id="cad6b-158">그림 8-3에서는 출력 바인딩의 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-158">Figure 8-3 shows the flow of an output binding:</span></span>

![6apr 출력 바인딩 흐름](media/bindings/output-binding-flow.png)

<span data-ttu-id="cad6b-160">**그림 8-3**.</span><span class="sxs-lookup"><span data-stu-id="cad6b-160">**Figure 8-3**.</span></span> <span data-ttu-id="cad6b-161">6apr 출력 바인딩 흐름입니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-161">Dapr output binding flow.</span></span>

1. <span data-ttu-id="cad6b-162">사이드카는 외부 리소스에 연결 하는 방법에 대 한 정보를 사용 하 여 바인딩 구성 파일을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-162">The Dapr sidecar reads the binding configuration file with the information on how to connect to the external resource.</span></span> <span data-ttu-id="cad6b-163">예제에서 외부 리소스는 Twilio SMS 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-163">In the example, the external resource is a Twilio SMS account.</span></span>
1. <span data-ttu-id="cad6b-164">응용 프로그램은 `/v1.0/bindings/sms` 사이드카에서 끝점을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-164">Your application invokes the `/v1.0/bindings/sms` endpoint on the Dapr sidecar.</span></span> <span data-ttu-id="cad6b-165">이 경우 HTTP POST를 사용 하 여 API를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-165">In this case, it uses an HTTP POST to invoke the API.</span></span> <span data-ttu-id="cad6b-166">GRPC를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-166">It's also possible to use gRPC.</span></span>
1. <span data-ttu-id="cad6b-167">D Apr 사이드카에서 실행 되는 바인딩 구성 요소는 메시지를 보내는 외부 메시징 시스템을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-167">The binding component running in the Dapr sidecar calls the external messaging system to send the message.</span></span> <span data-ttu-id="cad6b-168">메시지에는 POST 요청에 전달 된 페이로드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-168">The message will contain the payload passed in the POST request.</span></span>

<span data-ttu-id="cad6b-169">예를 들어, 말아 2-a를 사용 하 여 Eapr API를 호출 하 여 출력 바인딩을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-169">As an example, you can invoke an output binding by invoking the Dapr API using curl:</span></span>

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

<span data-ttu-id="cad6b-170">HTTP 포트는 Eapr 사이드카에서 사용 하는 것과 동일 합니다 (이 경우 기본 Eapr HTTP 포트 `3500` ).</span><span class="sxs-lookup"><span data-stu-id="cad6b-170">Note that the HTTP port is the same as used by the Dapr sidecar (in this case, the default Dapr HTTP port `3500`).</span></span>

<span data-ttu-id="cad6b-171">페이로드의 구조 (즉, 전송 되는 메시지)는 바인딩 마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-171">The structure of the payload (that is, message sent) will vary per binding.</span></span> <span data-ttu-id="cad6b-172">위의 예제에서 페이로드는 메시지를 포함 하는 요소를 포함 합니다 `data` .</span><span class="sxs-lookup"><span data-stu-id="cad6b-172">In the example above, the payload contains a `data` element with a message.</span></span> <span data-ttu-id="cad6b-173">다른 형식의 외부 리소스에 대 한 바인딩은 특히 전송 되는 메타 데이터의 경우 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-173">Bindings to other types of external resources can be different, especially for the metadata that is sent.</span></span> <span data-ttu-id="cad6b-174">각 페이로드에는 `operation` 바인딩이 실행 되는 작업을 정의 하는 필드도 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-174">Each payload must also contain an `operation` field, that defines the operation the binding will execute.</span></span> <span data-ttu-id="cad6b-175">위의 예에서는 `create` SMS 메시지를 만드는 작업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-175">The above example specifies a `create` operation that creates the SMS message.</span></span> <span data-ttu-id="cad6b-176">일반적인 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-176">Common operations include:</span></span>

- <span data-ttu-id="cad6b-177">create</span><span class="sxs-lookup"><span data-stu-id="cad6b-177">create</span></span>
- <span data-ttu-id="cad6b-178">Get</span><span class="sxs-lookup"><span data-stu-id="cad6b-178">get</span></span>
- <span data-ttu-id="cad6b-179">delete</span><span class="sxs-lookup"><span data-stu-id="cad6b-179">delete</span></span>
- <span data-ttu-id="cad6b-180">list</span><span class="sxs-lookup"><span data-stu-id="cad6b-180">list</span></span>

<span data-ttu-id="cad6b-181">바인딩에서 지 원하는 작업의 작성자에 게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-181">It's up to the author of the binding which operations the binding supports.</span></span> <span data-ttu-id="cad6b-182">각 바인딩에 대 한 설명서에서는 사용 가능한 작업과 해당 작업을 호출 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-182">The documentation for each binding describes the available operations and how to invoke them.</span></span>

## <a name="using-the-dapr-net-sdk"></a><span data-ttu-id="cad6b-183">Dapr .NET SDK 사용</span><span class="sxs-lookup"><span data-stu-id="cad6b-183">Using the Dapr .NET SDK</span></span>

<span data-ttu-id="cad6b-184">Dapr .NET SDK는 .NET Core 개발자를 위한 언어 관련 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-184">The Dapr .NET SDK provides language-specific support for .NET Core developers.</span></span> <span data-ttu-id="cad6b-185">다음 예제에서는에 대 한 호출이 `HttpClient.PostAsync()` 메서드로 대체 됩니다 `DaprClient.InvokeBindingAsync()` .</span><span class="sxs-lookup"><span data-stu-id="cad6b-185">In the following example, the call to the `HttpClient.PostAsync()` is replaced with the `DaprClient.InvokeBindingAsync()` method.</span></span> <span data-ttu-id="cad6b-186">이 특수 메서드는 구성 된 출력 바인딩 호출을 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-186">This specialized method simplifies invoking a configured output binding:</span></span>

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

<span data-ttu-id="cad6b-187">메서드에는 `metadata` 및 값이 필요 `message` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-187">The method expects the `metadata` and `message` values.</span></span>

<span data-ttu-id="cad6b-188">바인딩을 호출 하는 데 사용 되는 경우는 `DaprClient` gRPC를 사용 하 여 사이드카에서 EAPR API를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-188">When used to invoke a binding, the `DaprClient` uses gRPC to call the Dapr API on the Dapr sidecar.</span></span>

## <a name="binding-components"></a><span data-ttu-id="cad6b-189">바인딩 구성 요소</span><span class="sxs-lookup"><span data-stu-id="cad6b-189">Binding components</span></span>

<span data-ttu-id="cad6b-190">내부적으로 리소스 바인딩은 Eapr 바인딩 구성 요소를 사용 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-190">Under the hood, resource bindings are implemented with Dapr binding components.</span></span> <span data-ttu-id="cad6b-191">이들은 커뮤니티에서 제공 하 고 Go로 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-191">They're contributed by the community and written in Go.</span></span> <span data-ttu-id="cad6b-192">아직 Eapr 바인딩이 존재 하지 않는 외부 리소스와 통합 해야 하는 경우 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-192">If you need to integrate with an external resource for which no Dapr binding exists yet, you can create it yourself.</span></span> <span data-ttu-id="cad6b-193">D 4의 [구성 요소](https://github.com/dapr/components-contrib) 를 확인 하 여 바인딩에 기여할 수 있는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-193">Check out the [Dapr components-contrib repo](https://github.com/dapr/components-contrib) to see how you can contribute a binding.</span></span>

> [!NOTE]
> <span data-ttu-id="cad6b-194">Eapr 및 모든 구성 요소는 [Golang](https://golang.org/) (Go) 언어로 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-194">Dapr and all of its components are written in the [Golang](https://golang.org/) (Go) language.</span></span> <span data-ttu-id="cad6b-195">Go는 최신 클라우드 네이티브 프로그래밍 플랫폼으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-195">Go is considered a modern, cloud-native programming platform.</span></span>

<span data-ttu-id="cad6b-196">YAML 구성 파일을 사용 하 여 바인딩을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-196">You configure bindings using a YAML configuration file.</span></span> <span data-ttu-id="cad6b-197">Twitter 바인딩에 대 한 구성 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-197">Here's an example configuration for the Twitter binding:</span></span>

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

<span data-ttu-id="cad6b-198">각 바인딩 구성에 `metadata` 는 및 필드가 있는 일반 요소가 포함 `name` `namespace` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-198">Each binding configuration contains a general `metadata` element with a `name` and `namespace` field.</span></span> <span data-ttu-id="cad6b-199">구성 된 필드에 따라 서비스를 호출 하는 끝점을 결정 합니다 `name` .</span><span class="sxs-lookup"><span data-stu-id="cad6b-199">Dapr will determine the endpoint to invoke your service based upon the configured `name` field.</span></span> <span data-ttu-id="cad6b-200">위의 예제에서, C4는 이벤트가 발생할 때 서비스에서로 주석이 지정 된 메서드를 호출 `/twitter-mention` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-200">In the above example, Dapr will invoke the method annotated with `/twitter-mention` in your service when an event occurs.</span></span>

<span data-ttu-id="cad6b-201">요소에서 바인딩과 `spec` 함께 바인딩의를 지정 `type` `metadata` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-201">In the `spec` element, you specify the `type` of the binding along with binding specific `metadata`.</span></span> <span data-ttu-id="cad6b-202">이 예제에서는 해당 API를 사용 하 여 Twitter 계정에 액세스 하기 위한 자격 증명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-202">The example specifies credentials for accessing a Twitter account using its API.</span></span> <span data-ttu-id="cad6b-203">메타 데이터는 입력 및 출력 바인딩 간에 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-203">The metadata can differ between input and output bindings.</span></span> <span data-ttu-id="cad6b-204">예를 들어 입력 바인딩으로 Twitter를 사용 하려면 트 윗에서 필드를 사용 하 여 검색할 텍스트를 지정 해야 합니다 `query` .</span><span class="sxs-lookup"><span data-stu-id="cad6b-204">For example, to use Twitter as an input binding, you need to specify the text to search for in tweets using the `query` field.</span></span> <span data-ttu-id="cad6b-205">일치 하는 트 윗가 전송 될 때마다 사이드카는 `/twitter-mention` 서비스에서 끝점을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-205">Every time a matching tweet is sent, the Dapr sidecar will invoke the `/twitter-mention` endpoint on the service.</span></span> <span data-ttu-id="cad6b-206">트 윗의 내용도 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-206">It will also deliver the contents of the tweet.</span></span>

<span data-ttu-id="cad6b-207">바인딩은 입력, 출력 또는 둘 다로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-207">A binding can be configured for input, output, or both.</span></span> <span data-ttu-id="cad6b-208">흥미롭게도 바인딩에서는 입력 또는 출력 구성을 명시적으로 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-208">Interestingly, the binding doesn't explicitly specify input or output configuration.</span></span> <span data-ttu-id="cad6b-209">대신 구성 값과 함께 바인딩을 사용 하 여 방향이 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-209">Instead, the direction is inferred by the usage of the binding along with configuration values.</span></span>

<span data-ttu-id="cad6b-210">[리소스 바인딩에 대 한 4Apr 설명서] [1]는 사용 가능한 바인딩 및 해당 특정 구성 설정의 전체 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-210">The [Dapr documentation for resource bindings][1] provides a complete list of the available bindings and their specific configuration settings.</span></span>

### <a name="cron-binding"></a><span data-ttu-id="cad6b-211">Cron 바인딩</span><span class="sxs-lookup"><span data-stu-id="cad6b-211">Cron binding</span></span>

<span data-ttu-id="cad6b-212">Eapr의 Cron 바인딩에 주의 하세요.</span><span class="sxs-lookup"><span data-stu-id="cad6b-212">Pay close attention to Dapr's Cron binding.</span></span> <span data-ttu-id="cad6b-213">외부 시스템의 이벤트를 구독 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-213">It doesn't subscribe to events from an external system.</span></span> <span data-ttu-id="cad6b-214">대신이 바인딩은 구성 가능한 간격 일정을 사용 하 여 응용 프로그램을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-214">Instead, this binding uses a configurable interval schedule to trigger your application.</span></span> <span data-ttu-id="cad6b-215">바인딩은 구성 가능한 지연 시간을 사용 하 여 무한 루프를 구현할 필요 없이 절전 모드를 해제 하 고 일정 한 간격으로 작업을 수행할 수 있는 간단한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-215">The binding provides a simple way to implement a background worker to wake up and do some work at a regular interval, without the need to implement an endless loop with a configurable delay.</span></span> <span data-ttu-id="cad6b-216">Cron 바인딩 구성의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-216">Here's an example of a Cron binding configuration:</span></span>

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

<span data-ttu-id="cad6b-217">이 예제에서 d 4는 `/checkOrderBacklog` 30 분 마다 끝점을 호출 하 여 서비스를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-217">In this example, Dapr triggers a service by invoking the `/checkOrderBacklog` endpoint every 30 minutes.</span></span> <span data-ttu-id="cad6b-218">값을 지정 하는 데 사용할 수 있는 몇 가지 패턴이 있습니다 `schedule` .</span><span class="sxs-lookup"><span data-stu-id="cad6b-218">There are several patterns available for specifying the `schedule` value.</span></span> <span data-ttu-id="cad6b-219">자세한 내용은 [Cron binding 설명서](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/cron/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cad6b-219">For more information, see the [Cron binding documentation](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/cron/).</span></span>

## <a name="reference-application-eshopondapr"></a><span data-ttu-id="cad6b-220">참조 응용 프로그램: eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="cad6b-220">Reference application: eShopOnDapr</span></span>

<span data-ttu-id="cad6b-221">함께 제공 되는 eShopOnDapr reference 응용 프로그램은 출력 바인딩 예제를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-221">The accompanying eShopOnDapr reference application implements an output binding example.</span></span> <span data-ttu-id="cad6b-222">새 주문이 배치 될 때 사용자에 게 전자 메일을 보내는 데 사용 하는 Eapr [SendGrid](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/sendgrid/) 바인딩을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-222">It triggers the Dapr [SendGrid](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/sendgrid/) binding to send a user an email when a new order is placed.</span></span> <span data-ttu-id="cad6b-223">이 바인딩은 `eshop-email.yaml` 파일의 구성 요소 폴더에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-223">You can find this binding in the `eshop-email.yaml` file in the components folder:</span></span>

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

<span data-ttu-id="cad6b-224">이 구성은 [Twilio SendGrid](https://github.com/dapr/components-contrib/tree/master/bindings/twilio) binding 구성 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-224">This configuration uses the [Twilio SendGrid](https://github.com/dapr/components-contrib/tree/master/bindings/twilio) binding component.</span></span> <span data-ttu-id="cad6b-225">서비스에 연결 하기 위한 API 키가 Eapr 비밀 참조를 사용 하는 방법에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="cad6b-225">Note how the API key for connecting to the service consumes a Dapr secret reference.</span></span> <span data-ttu-id="cad6b-226">이 접근 방식은 구성 파일 외부에서 비밀을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-226">This approach keeps secrets outside of the configuration file.</span></span> <span data-ttu-id="cad6b-227">Eapr 암호에 대 한 자세한 내용은 [비밀 빌딩 블록 챕터](secrets.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cad6b-227">Read the [secrets building block chapter](secrets.md) to learn more about Dapr secrets.</span></span>

<span data-ttu-id="cad6b-228">바인딩 구성은 사이드카의 끝점을 사용 하 여 호출할 수 있는 바인딩 구성 요소를 지정 합니다 `/sendmail` .</span><span class="sxs-lookup"><span data-stu-id="cad6b-228">The binding configuration specifies a binding component that can be invoked using the `/sendmail` endpoint on the Dapr sidecar.</span></span> <span data-ttu-id="cad6b-229">주문이 시작 될 때마다 전자 메일을 전송 하는 코드 조각은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-229">Here's a code snippet in which an email is sent whenever an order is started:</span></span>

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

<span data-ttu-id="cad6b-230">이 예제에서 볼 수 있듯이에 `message` 는 메시지 본문이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-230">As you can see in this example, `message` contains the message body.</span></span> <span data-ttu-id="cad6b-231">`CreateEmailBody`메서드는 단순히 본문 텍스트를 사용 하 여 문자열의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-231">The `CreateEmailBody` method simply formats a string with the body text.</span></span> <span data-ttu-id="cad6b-232">는 전자 `metadata` 메일 보낸 사람, 받는 사람 및 전자 메일 메시지의 제목을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-232">The `metadata` specifies the email sender, recipient, and the subject for the email message.</span></span> <span data-ttu-id="cad6b-233">이러한 값이 정적 이면 구성 파일의 메타 데이터 필드에도 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-233">If these values are static, they can also be included in the metadata fields in the configuration file.</span></span> <span data-ttu-id="cad6b-234">호출할 바인딩의 이름이이 `sendmail` 고 작업은 `create` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-234">The name of the binding to invoke is `sendmail` and the operation is `create`.</span></span>

## <a name="summary"></a><span data-ttu-id="cad6b-235">요약</span><span class="sxs-lookup"><span data-stu-id="cad6b-235">Summary</span></span>

<span data-ttu-id="cad6b-236">Eapr 리소스 바인딩을 사용 하면 라이브러리 또는 Sdk에 대 한 종속성을 취하지 않고 다른 외부 리소스 및 시스템과 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-236">Dapr resource bindings enable you to integrate with different external resources and systems without taking dependencies on their libraries or SDKs.</span></span> <span data-ttu-id="cad6b-237">이러한 외부 시스템은 서비스 버스 또는 메시지 브로커와 같은 메시징 시스템이 아니어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-237">These external systems don't necessarily have to be messaging systems like a service bus or message broker.</span></span> <span data-ttu-id="cad6b-238">또한 데이터 저장소와 Twitter 또는 SendGrid 같은 웹 리소스에 대 한 바인딩이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-238">Bindings also exist for datastores and web resources like Twitter or SendGrid.</span></span>

<span data-ttu-id="cad6b-239">입력 바인딩 또는 트리거는 외부 시스템에서 발생 하는 이벤트에 대응 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-239">Input bindings (or triggers) react to events occurring in an external system.</span></span> <span data-ttu-id="cad6b-240">응용 프로그램에서 미리 구성 된 공용 HTTP 끝점을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-240">They invoke the public HTTP endpoints pre-configured in your application.</span></span> <span data-ttu-id="cad6b-241">6apr는 구성의 바인딩 이름을 사용 하 여 응용 프로그램에서 호출할 끝점을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-241">Dapr uses the name of the binding in the configuration to determine the endpoint to call in your application.</span></span>

<span data-ttu-id="cad6b-242">출력 바인딩은 외부 시스템으로 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-242">Output bindings will send messages to an external system.</span></span> <span data-ttu-id="cad6b-243">Tapr 사이드카의 끝점에서 HTTP POST를 수행 하 여 출력 바인딩을 트리거합니다 `/v1.0/bindings/<binding-name>` .</span><span class="sxs-lookup"><span data-stu-id="cad6b-243">You trigger an output binding by doing an HTTP POST on the `/v1.0/bindings/<binding-name>` endpoint on the Dapr sidecar.</span></span> <span data-ttu-id="cad6b-244">GRPC를 사용 하 여 바인딩을 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-244">You can also use gRPC to invoke the binding.</span></span> <span data-ttu-id="cad6b-245">.NET SDK는 `InvokeBindingAsync` gRPC를 사용 하 여 Dapr 바인딩을 호출 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-245">The .NET SDK offers a `InvokeBindingAsync` method to invoke Dapr bindings using gRPC.</span></span>

<span data-ttu-id="cad6b-246">Wapr 구성 요소를 사용 하 여 바인딩을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-246">You implement a binding with a Dapr component.</span></span> <span data-ttu-id="cad6b-247">이러한 구성 요소는 커뮤니티에 의해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-247">These components are contributed by the community.</span></span> <span data-ttu-id="cad6b-248">각 바인딩 구성 요소의 구성에는 추상화 하는 외부 시스템에 특정 한 메타 데이터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-248">Each binding component's configuration has metadata that is specific for the external system it abstracts.</span></span> <span data-ttu-id="cad6b-249">또한 지원 되는 명령과 페이로드의 구조는 바인딩 구성 요소 마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cad6b-249">Also, the commands it supports and the structure of the payload will differ per binding component.</span></span>

### <a name="references"></a><span data-ttu-id="cad6b-250">참조</span><span class="sxs-lookup"><span data-stu-id="cad6b-250">References</span></span>

- [<span data-ttu-id="cad6b-251">리소스 바인딩에 대 한 4apr 설명서</span><span class="sxs-lookup"><span data-stu-id="cad6b-251">Dapr documentation for resource bindings</span></span>](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/)

>[!div class="step-by-step"]
><span data-ttu-id="cad6b-252">[이전](publish-subscribe.md)
>[다음](observability.md)</span><span class="sxs-lookup"><span data-stu-id="cad6b-252">[Previous](publish-subscribe.md)
[Next](observability.md)</span></span>
