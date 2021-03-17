---
title: D Apr 게시 & 구독 구성 블록
description: 빌드 블록 구독 및이를 적용 하는 방법에 대 한 자세한 내용은 &
author: edwinvw
ms.date: 02/17/2021
ms.openlocfilehash: 11898430d897ec85b7e367fa0e93ca912279784b
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623826"
---
# <a name="the-dapr-publish--subscribe-building-block"></a><span data-ttu-id="55be0-103">D Apr 게시 & 구독 구성 블록</span><span class="sxs-lookup"><span data-stu-id="55be0-103">The Dapr publish & subscribe building block</span></span>

<span data-ttu-id="55be0-104">[게시-구독 패턴](/azure/architecture/patterns/publisher-subscriber) ("pub/sub" 라고도 함)은 잘 알려져 있고 널리 사용 되는 메시징 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-104">The [Publish-Subscribe pattern](/azure/architecture/patterns/publisher-subscriber) (often referred to as "pub/sub") is a well-known and widely used messaging pattern.</span></span> <span data-ttu-id="55be0-105">설계자는 일반적으로 분산 응용 프로그램에이를 수용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-105">Architects commonly embrace it in distributed applications.</span></span> <span data-ttu-id="55be0-106">그러나이를 구현 하는 것은 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-106">However, the plumbing to implement it can be complex.</span></span> <span data-ttu-id="55be0-107">여러 메시징 제품 간에 미묘한 기능 차이가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-107">There are often subtle feature differences across different messaging products.</span></span> <span data-ttu-id="55be0-108">D p 4는 pub/sub 기능 구현을 크게 간소화 하는 빌딩 블록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-108">Dapr offers a building block that significantly simplifies implementing pub/sub functionality.</span></span>

## <a name="what-it-solves"></a><span data-ttu-id="55be0-109">해결 방법</span><span class="sxs-lookup"><span data-stu-id="55be0-109">What it solves</span></span>

<span data-ttu-id="55be0-110">Publish-Subscribe 패턴의 주요 이점은 **느슨한 결합** 이며, 때로는 [임시](/azure/architecture/guide/technology-choices/messaging#decoupling)분리 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-110">The primary advantage of the Publish-Subscribe pattern is **loose coupling**, sometimes referred to as [temporal decoupling](/azure/architecture/guide/technology-choices/messaging#decoupling).</span></span> <span data-ttu-id="55be0-111">메시지 ( **구독자**)를 사용 하는 서비스에서 메시지 ( **게시자**)를 전송 하는 서비스를 분리 하는 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-111">The pattern decouples services that send messages (the **publishers**) from services that consume messages (the **subscribers**).</span></span> <span data-ttu-id="55be0-112">게시자와 구독자는 모두 서로를 인식 하지 못합니다. 둘 다 메시지를 배포 하는 중앙 집중식 **메시지 브로커** 에 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-112">Both publishers and subscribers are unaware of each other - both are dependent on a centralized **message broker** that distributes the messages.</span></span>

<span data-ttu-id="55be0-113">그림 7-1에는 pub/sub 패턴의 상위 수준 아키텍처가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-113">Figure 7-1 shows the high-level architecture of the pub/sub pattern.</span></span>

![Pub/sub 패턴](./media/publish-subscribe/pub-sub-pattern.png)

<span data-ttu-id="55be0-115">**그림 7-1**.</span><span class="sxs-lookup"><span data-stu-id="55be0-115">**Figure 7-1**.</span></span> <span data-ttu-id="55be0-116">Pub/sub 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-116">The pub/sub pattern.</span></span>

<span data-ttu-id="55be0-117">위의 그림에서 패턴의 단계를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-117">From the previous figure, note the steps of the pattern:</span></span>

1. <span data-ttu-id="55be0-118">게시자는 메시지 브로커로 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-118">Publishers send messages to the message broker.</span></span>
1. <span data-ttu-id="55be0-119">구독자는 메시지 브로커의 구독에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-119">Subscribers bind to a subscription on the message broker.</span></span>
1. <span data-ttu-id="55be0-120">메시지 broker는 메시지의 복사본을 관심이 있는 구독으로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-120">The message broker forwards a copy of the message to interested subscriptions.</span></span>
1. <span data-ttu-id="55be0-121">구독자는 구독에서 메시지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-121">Subscribers consume messages from their subscriptions.</span></span>

<span data-ttu-id="55be0-122">대부분의 메시지 브로커는 받은 후 메시지를 유지할 수 있는 큐 메커니즘을 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-122">Most message brokers encapsulate a queueing mechanism that can persist messages once received.</span></span> <span data-ttu-id="55be0-123">이를 통해 메시지 broker는 메시지를 저장 하 여 **내구성** 을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-123">With it, the message broker guarantees **durability** by storing the message.</span></span> <span data-ttu-id="55be0-124">게시자가 메시지를 보낼 때 구독자를 즉시 사용할 수 없거나 온라인 상태가 아니어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-124">Subscribers don't need to be immediately available or even online when a publisher sends a message.</span></span> <span data-ttu-id="55be0-125">구독자는 사용할 수 있게 되 면 메시지를 받고 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-125">Once available, the subscriber receives and processes the message.</span></span>  <span data-ttu-id="55be0-126">D 4는 메시지 배달에 대 한 **최소 한 번** 의 의미 체계를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-126">Dapr guarantees **At-Least-Once** semantics for message delivery.</span></span> <span data-ttu-id="55be0-127">메시지를 게시 한 후에는 관심 있는 모든 구독자에 게 한 번 이상 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-127">Once a message is published, it will be delivered at least once to any interested subscriber.</span></span>

 > <span data-ttu-id="55be0-128">서비스에서 메시지를 한 번만 처리할 수 있는 경우에는 [멱 등 성 검사](/azure/architecture/microservices/design/api-design#idempotent-operations) 를 제공 하 여 동일한 메시지가 여러 번 처리 되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-128">If your service can only process a message once, you'll need to provide an [idempotency check](/azure/architecture/microservices/design/api-design#idempotent-operations) to ensure that the same message is not processed multiple times.</span></span> <span data-ttu-id="55be0-129">이러한 논리를 코딩할 수 있지만 Azure Service Bus와 같은 일부 메시지 브로커는 기본 제공 *중복 검색* 메시징 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-129">While such logic can be coded, some message brokers, such as Azure Service Bus, provide built-in *duplicate detection* messaging capabilities.</span></span>

<span data-ttu-id="55be0-130">상용 및 오픈 소스 모두에서 사용할 수 있는 여러 가지 메시지 broker 제품이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-130">There are several message broker products available - both commercially and open-source.</span></span> <span data-ttu-id="55be0-131">각에는 장점과 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-131">Each has advantages and drawbacks.</span></span> <span data-ttu-id="55be0-132">사용자의 작업은 적절 한 broker에 시스템 요구 사항을 일치 시키는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-132">Your job is to match your system requirements to the appropriate broker.</span></span> <span data-ttu-id="55be0-133">선택한 후에는 메시지 브로커에서 응용 프로그램을 분리 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-133">Once selected, it's a best practice to decouple your application from message broker plumbing.</span></span> <span data-ttu-id="55be0-134">*추상화* 내에 broker를 래핑하여이 기능을 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-134">You achieve this functionality by wrapping the broker inside an *abstraction*.</span></span> <span data-ttu-id="55be0-135">추상화는 메시지를 캡슐화 하 고 일반 pub/sub 작업을 코드에 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-135">The abstraction encapsulates the message plumbing and exposes generic pub/sub operations to your code.</span></span> <span data-ttu-id="55be0-136">코드는 실제 메시지 브로커가 아닌 추상화와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-136">Your code communicates with the abstraction, not the actual message broker.</span></span> <span data-ttu-id="55be0-137">의사 결정을 내릴 때 추상화 및 해당 기본 구현을 작성 하 고 유지 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-137">While a wise decision, you'll have to write and maintain the abstraction and its underlying implementation.</span></span> <span data-ttu-id="55be0-138">이 방법에는 복잡 하 고 반복적 이며 오류가 발생할 수 있는 사용자 지정 코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-138">This approach requires custom code that can be complex, repetitive, and error-prone.</span></span>

<span data-ttu-id="55be0-139">D Apr 게시 & 구독 빌딩 블록은 메시징 추상화 및 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-139">The Dapr publish & subscribe building block provides the messaging abstraction and implementation out-of-the-box.</span></span> <span data-ttu-id="55be0-140">작성 해야 하는 사용자 지정 코드는 미리 빌드된 후에는 Eapr 빌딩 블록 내에 캡슐화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-140">The custom code you would have had to write is prebuilt and encapsulated inside the Dapr building block.</span></span> <span data-ttu-id="55be0-141">이를 바인딩하고 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-141">You bind to it and consume it.</span></span> <span data-ttu-id="55be0-142">메시징 배관 코드를 작성 하는 대신 사용자와 팀은 고객에 게 가치를 더하는 비즈니스 기능을 만드는 데 주력 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-142">Instead of writing messaging plumbing code, you and your team focus on creating business functionality that adds value to your customers.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="55be0-143">작동 방식</span><span class="sxs-lookup"><span data-stu-id="55be0-143">How it works</span></span>

<span data-ttu-id="55be0-144">D Apr 게시 & 구독 구성 요소는 메시지를 보내고 받기 위한 플랫폼 독립적인 API 프레임 워크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-144">The Dapr publish & subscribe building block provides a platform-agnostic API framework to send and receive messages.</span></span> <span data-ttu-id="55be0-145">서비스는 명명 된 [항목](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions#topics-and-subscriptions)에 메시지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-145">Your services publish messages to a named [topic](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions#topics-and-subscriptions).</span></span> <span data-ttu-id="55be0-146">서비스는 항목을 구독 하 여 메시지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-146">Your services subscribe to a topic to consume messages.</span></span>

<span data-ttu-id="55be0-147">서비스는 사이드카에서 pub/sub API를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-147">The service calls the pub/sub API on the Dapr sidecar.</span></span> <span data-ttu-id="55be0-148">그런 다음 사이드카은 특정 메시지 브로커 제품을 캡슐화 하는 미리 정의 된 Eapr pub/sub 구성 요소에 대 한 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-148">The sidecar then makes calls into a pre-defined Dapr pub/sub component that encapsulates a specific message broker product.</span></span> <span data-ttu-id="55be0-149">그림 7-2에서는 4 월 pub/sub 메시징 스택을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-149">Figure 7-2 shows the Dapr pub/sub messaging stack.</span></span>

![Pub/sub stack](./media/publish-subscribe/pub-sub-buildingblock.png)

<span data-ttu-id="55be0-151">**그림 7-2**.</span><span class="sxs-lookup"><span data-stu-id="55be0-151">**Figure 7-2**.</span></span> <span data-ttu-id="55be0-152">6Apr pub/sub 스택입니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-152">The Dapr pub/sub stack.</span></span>

<span data-ttu-id="55be0-153">여러 가지 방법으로 4 월 게시 & 구독 빌딩 블록을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-153">The Dapr publish & subscribe building block can be invoked in many ways.</span></span>

<span data-ttu-id="55be0-154">가장 낮은 수준에서 모든 프로그래밍 플랫폼은 **NATIVE API** 를 사용 하 여 HTTP 또는 grpc를 통해 빌딩 블록을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-154">At the lowest level, any programming platform can invoke the building block over HTTP or gRPC using the **Dapr native API**.</span></span> <span data-ttu-id="55be0-155">메시지를 게시 하려면 다음 API 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-155">To publish a message, you make the following API call:</span></span>

``` http
http://localhost:<dapr-port>/v1.0/publish/<pub-sub-name>/<topic>
```

<span data-ttu-id="55be0-156">위의 호출에는 몇 가지 다양 한 4 가지 특정 URL 세그먼트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-156">There are several Dapr specific URL segments in the above call:</span></span>

- <span data-ttu-id="55be0-157">`<dapr-port>` 은 (는) 사이드카에서 수신 대기 하는 포트 번호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-157">`<dapr-port>` provides the port number upon which the Dapr sidecar is listening.</span></span>
- <span data-ttu-id="55be0-158">`<pub-sub-name>` 선택한 Wapr pub/sub 구성 요소의 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-158">`<pub-sub-name>` provides the name of the selected Dapr pub/sub component.</span></span>
- <span data-ttu-id="55be0-159">`<topic>` 메시지를 게시할 토픽의 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-159">`<topic>` provides the name of the topic to which the message is published.</span></span>

<span data-ttu-id="55be0-160">*말아* 명령줄 도구를 사용 하 여 메시지를 게시 하면 다음과 같은 작업을 수행해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-160">Using the *curl* command-line tool to publish a message, you can try it out:</span></span>

``` curl
curl -X POST http://localhost:3500/v1.0/publish/pubsub/newOrder \
  -H "Content-Type: application/json" \
  -d '{ "orderId": "1234", "productId": "5678", "amount": 2 }'
```

<span data-ttu-id="55be0-161">항목을 구독 하 여 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-161">You receive messages by subscribing to a topic.</span></span> <span data-ttu-id="55be0-162">시작 시에는 필요한 구독을 식별 하 고 만들기 위해 잘 알려진 끝점에서 응용 프로그램을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-162">At startup, the Dapr runtime will call the application on a well-known endpoint to identify and create the required subscriptions:</span></span>

``` http
http://localhost:<appPort>/dapr/subscribe
```

- <span data-ttu-id="55be0-163">`<appPort>` 응용 프로그램이 수신 대기 하는 포트의 사이드카를에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-163">`<appPort>` informs the Dapr sidecar of the port upon which the application is listening.</span></span>

<span data-ttu-id="55be0-164">이 끝점을 직접 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-164">You can implement this endpoint yourself.</span></span> <span data-ttu-id="55be0-165">그러나 Eapr는 보다 직관적인 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-165">But Dapr provides more intuitive ways of implementing it.</span></span> <span data-ttu-id="55be0-166">이 기능은이 장의 뒷부분에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-166">We'll address this functionality later in this chapter.</span></span>

<span data-ttu-id="55be0-167">호출의 응답에는 응용 프로그램에서 구독할 항목의 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-167">The response from the call contains a list of topics to which the applications will subscribe.</span></span> <span data-ttu-id="55be0-168">각에는 토픽에서 메시지를 받을 때 호출할 끝점이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-168">Each includes an endpoint to call when the topic receives a message.</span></span> <span data-ttu-id="55be0-169">응답의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-169">Here's an example of a response:</span></span>

```json
[
  {
    "pubsubname": "pubsub",
    "topic": "newOrder",
    "route": "/orders"
  },
  {
    "pubsubname": "pubsub",
    "topic": "newProduct",
    "route": "/productCatalog/products"
  }
]
```

<span data-ttu-id="55be0-170">JSON 응답에서 응용 프로그램이 항목 및를 구독 하려고 하는 것을 볼 수 있습니다 `newOrder` `newProduct` .</span><span class="sxs-lookup"><span data-stu-id="55be0-170">In the JSON response, you can see the application wants to subscribe to topics `newOrder` and `newProduct`.</span></span> <span data-ttu-id="55be0-171">각각에 대해 끝점과를 등록 `/orders` `/productCatalog/products` 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-171">It registers the endpoints `/orders` and `/productCatalog/products` for each, respectively.</span></span> <span data-ttu-id="55be0-172">두 구독 모두에 대해 응용 프로그램은 이름이 인 Eapr 구성 요소에 바인딩합니다 `pubsub` .</span><span class="sxs-lookup"><span data-stu-id="55be0-172">For both subscriptions, the application is binding to the Dapr component named `pubsub`.</span></span>

<span data-ttu-id="55be0-173">그림 7-3에서는 예제의 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-173">Figure 7-3 presents the flow of the example.</span></span>

![예: d 4를 사용 하 여 pub/sub flow](media/publish-subscribe/pub-sub-flow.png)

<span data-ttu-id="55be0-175">**그림 7-3**.</span><span class="sxs-lookup"><span data-stu-id="55be0-175">**Figure 7-3**.</span></span> <span data-ttu-id="55be0-176">t 4를 사용 하는 pub/sub flow.</span><span class="sxs-lookup"><span data-stu-id="55be0-176">pub/sub flow with Dapr.</span></span>

<span data-ttu-id="55be0-177">위의 그림에서 흐름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-177">From the previous figure, note the flow:</span></span>

1. <span data-ttu-id="55be0-178">Service B에 대 한 Bapr 사이드카는 `/dapr/subscribe` 서비스 b (소비자)에서 끝점을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-178">The Dapr sidecar for Service B calls the `/dapr/subscribe` endpoint from Service B (the consumer).</span></span> <span data-ttu-id="55be0-179">서비스는 만들려는 구독을 사용 하 여 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-179">The service responds with the subscriptions it wants to create.</span></span>
1. <span data-ttu-id="55be0-180">Service B의 Bapr 사이드카는 메시지 브로커에 요청 된 구독을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-180">The Dapr sidecar for Service B creates the requested subscriptions on the message broker.</span></span>
1. <span data-ttu-id="55be0-181">서비스 A는 사이드카 서비스의 끝점에서 메시지를 게시 `/v1.0/publish/<pub-sub-name>/<topic>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-181">Service A publishes a message at the `/v1.0/publish/<pub-sub-name>/<topic>` endpoint on the Dapr Service A sidecar.</span></span>
1. <span data-ttu-id="55be0-182">사이드카 서비스는 메시지를 메시지 브로커에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-182">The Service A sidecar publishes the message to the message broker.</span></span>
1. <span data-ttu-id="55be0-183">메시지 브로커가 Service B 사이드카 메시지의 복사본을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-183">The message broker sends a copy of the message to the Service B sidecar.</span></span>
1. <span data-ttu-id="55be0-184">서비스 B 사이드카는 서비스 B의 구독 (이 경우)에 해당 하는 끝점을 호출 합니다 `/orders` . 서비스는 HTTP 상태 코드를 사용 하 여 응답 `200 OK` 하므로 사이드카은 메시지를 처리 하는 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-184">The Service B sidecar calls the endpoint corresponding to the subscription (in this case `/orders`) on Service B. The service responds with an HTTP status-code `200 OK` so the sidecar will consider the message as being handled successfully.</span></span>

<span data-ttu-id="55be0-185">이 예제에서는 메시지가 성공적으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-185">In the example, the message is handled successfully.</span></span> <span data-ttu-id="55be0-186">하지만 Service B에서 요청을 처리 하는 동안 문제가 발생 하면 응답을 사용 하 여 메시지에 대해 수행할 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-186">But if something goes wrong while Service B is handling the request, it can use the response to specify what needs to happen with the message.</span></span> <span data-ttu-id="55be0-187">HTTP 상태 코드를 반환 하면 `404` 오류가 기록 되 고 메시지가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-187">When it returns an HTTP status-code `404`, an error is logged and the message is dropped.</span></span> <span data-ttu-id="55be0-188">또는 이외의 다른 상태 코드를 사용 하 여 `200` `404` 경고를 기록 하 고 메시지를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-188">With any other status-code than `200` or `404`, a warning is logged and the message is retried.</span></span> <span data-ttu-id="55be0-189">또는 서비스 B는 응답 본문에 JSON 페이로드를 포함 하 여 메시지에 대해 수행 해야 하는 작업을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-189">Alternatively, Service B can explicitly specify what needs to happen with the message by including a JSON payload in the body of the response:</span></span>

```json
{
  "status": "<status>"
}
```

<span data-ttu-id="55be0-190">다음 표에서는 사용 가능한 값을 보여 줍니다 `status` .</span><span class="sxs-lookup"><span data-stu-id="55be0-190">The following table shows the available `status` values:</span></span>

| <span data-ttu-id="55be0-191">상태</span><span class="sxs-lookup"><span data-stu-id="55be0-191">Status</span></span>           | <span data-ttu-id="55be0-192">작업</span><span class="sxs-lookup"><span data-stu-id="55be0-192">Action</span></span>                                                       |
| ---------------- | ------------------------------------------------------------ |
| <span data-ttu-id="55be0-193">SUCCESS</span><span class="sxs-lookup"><span data-stu-id="55be0-193">SUCCESS</span></span>          | <span data-ttu-id="55be0-194">메시지는 성공적으로 처리 되 고 삭제 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-194">The message is considered as processed successfully and dropped.</span></span> |
| <span data-ttu-id="55be0-195">다시 시도</span><span class="sxs-lookup"><span data-stu-id="55be0-195">RETRY</span></span>            | <span data-ttu-id="55be0-196">메시지를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-196">The message is retried.</span></span>                                      |
| <span data-ttu-id="55be0-197">DROP</span><span class="sxs-lookup"><span data-stu-id="55be0-197">DROP</span></span>             | <span data-ttu-id="55be0-198">경고가 기록 되 고 메시지가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-198">A warning is logged and the message is dropped.</span></span>              |
| <span data-ttu-id="55be0-199">기타 모든 상태</span><span class="sxs-lookup"><span data-stu-id="55be0-199">Any other status</span></span> | <span data-ttu-id="55be0-200">메시지를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-200">The message is retried.</span></span>                                      |

### <a name="competing-consumers"></a><span data-ttu-id="55be0-201">경쟁 소비자</span><span class="sxs-lookup"><span data-stu-id="55be0-201">Competing consumers</span></span>

<span data-ttu-id="55be0-202">토픽을 구독 하는 응용 프로그램을 확장 하는 경우 경쟁 소비자를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-202">When scaling out an application that subscribes to a topic, you have to deal with competing consumers.</span></span> <span data-ttu-id="55be0-203">하나의 응용 프로그램 인스턴스만 토픽에 전송 된 메시지를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-203">Only one application instance should handle a message sent to the topic.</span></span> <span data-ttu-id="55be0-204">다행히 4는 이러한 문제를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-204">Luckily, Dapr handles that problem.</span></span> <span data-ttu-id="55be0-205">동일한 응용 프로그램 id를 사용 하는 서비스의 여러 인스턴스가 토픽을 구독할 경우, d 4는 각 메시지를 하나에만 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-205">When multiple instances of a service with the same application-id subscribe to a topic, Dapr delivers each message to only one of them.</span></span>

### <a name="sdks"></a><span data-ttu-id="55be0-206">SDK</span><span class="sxs-lookup"><span data-stu-id="55be0-206">SDKs</span></span>

<span data-ttu-id="55be0-207">네이티브 기본 Api에 대 한 HTTP 호출을 수행 하는 것은 시간이 많이 걸리고 추상적입니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-207">Making HTTP calls to the native Dapr APIs is time-consuming and abstract.</span></span> <span data-ttu-id="55be0-208">호출은 HTTP 수준에서 제공 되므로 serialization 및 HTTP 응답 코드와 같은 배관 문제를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-208">Your calls are crafted at the HTTP level, and you'll need to handle plumbing concerns such as serialization and HTTP response codes.</span></span> <span data-ttu-id="55be0-209">다행히 직관적인 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-209">Fortunately, there's a more intuitive way.</span></span> <span data-ttu-id="55be0-210">D 4는 인기 있는 개발 플랫폼에 대 한 몇 가지 언어별 Sdk를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-210">Dapr provides several language-specific SDKs for popular development platforms.</span></span> <span data-ttu-id="55be0-211">이 문서를 작성할 당시에는 Go, Node.js, Python, .NET, Java 및 JavaScript를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-211">At the time of this writing, Go, Node.js, Python, .NET, Java, and JavaScript are available.</span></span>

## <a name="use-the-dapr-net-sdk"></a><span data-ttu-id="55be0-212">Dapr .NET SDK 사용</span><span class="sxs-lookup"><span data-stu-id="55be0-212">Use the Dapr .NET SDK</span></span>

<span data-ttu-id="55be0-213">.NET 개발자를 위해 [dapr .NET SDK](https://www.nuget.org/packages/Dapr.Client) 는 dapr를 사용 하는 보다 생산적인 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-213">For .NET Developers, the [Dapr .NET SDK](https://www.nuget.org/packages/Dapr.Client) provides a more productive way of working with Dapr.</span></span> <span data-ttu-id="55be0-214">SDK는 `DaprClient` Dapr 기능을 직접 호출할 수 있는 클래스를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-214">The SDK exposes a `DaprClient` class through which you can directly invoke Dapr functionality.</span></span> <span data-ttu-id="55be0-215">직관적이 고 사용 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-215">It's intuitive and easy to use.</span></span>

<span data-ttu-id="55be0-216">메시지를 게시 하기 위해는 `DaprClient` 메서드를 노출 `PublishEventAsync` 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-216">To publish a message, the `DaprClient` exposes a `PublishEventAsync` method.</span></span>

```csharp
var data = new OrderData
{
  orderId = "123456",
  productId = "67890",
  amount = 2
};

var daprClient = new DaprClientBuilder().Build();

await daprClient.PublishEventAsync<OrderData>("pubsub", "newOrder", data);
```

- <span data-ttu-id="55be0-217">첫 번째 인수는 `pubsub` 메시지 브로커 구현을 제공 하는 Eapr 구성 요소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-217">The first argument `pubsub` is the name of the Dapr component that provides the message broker implementation.</span></span> <span data-ttu-id="55be0-218">구성 요소에 대해서는이 챕터의 뒷부분에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-218">We'll address components later in this chapter.</span></span>
- <span data-ttu-id="55be0-219">두 번째 인수는 `neworder` 메시지를 보낼 토픽의 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-219">The second argument `neworder` provides the name of the topic to send the message to.</span></span>
- <span data-ttu-id="55be0-220">세 번째 인수는 메시지의 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-220">The third argument is the payload of the message.</span></span>
- <span data-ttu-id="55be0-221">메서드의 제네릭 형식 매개 변수를 사용 하 여 .NET 형식의 메시지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-221">You can specify the .NET type of the message using the generic type parameter of the method.</span></span>

<span data-ttu-id="55be0-222">메시지를 수신 하려면 등록 된 항목에 대해 끝점을 구독에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-222">To receive messages, you bind an endpoint to a subscription for a registered topic.</span></span> <span data-ttu-id="55be0-223">AspNetCore library for Eapr를 사용 하면이를 편리 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-223">The AspNetCore library for Dapr makes this trivial.</span></span> <span data-ttu-id="55be0-224">예를 들어 기존 ASP.NET WebAPI action 메서드가 있다고 가정 합니다 `CreateOrder` .</span><span class="sxs-lookup"><span data-stu-id="55be0-224">Assume, for example, that you have an existing ASP.NET WebAPI action method entitled `CreateOrder`:</span></span>

```csharp
[HttpPost("/orders")]
public async Task<ActionResult> CreateOrder(Order order)
```

 > <span data-ttu-id="55be0-225">[AspNetCore](https://www.nuget.org/packages/Dapr.AspNetCore) NuGet 패키지에 대 한 참조를 프로젝트에 추가 하 여 eapr ASP.NET Core 통합을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-225">You must add a reference to the [Dapr.AspNetCore](https://www.nuget.org/packages/Dapr.AspNetCore) NuGet package in your project to consume the Dapr ASP.NET Core integration.</span></span>

<span data-ttu-id="55be0-226">이 작업 메서드를 토픽에 바인딩하려면 특성을 사용 하 여 데코 레이트 합니다 `Topic` .</span><span class="sxs-lookup"><span data-stu-id="55be0-226">To bind this action method to a topic, you decorate it with the `Topic` attribute:</span></span>

```csharp
[Topic("pubsub", "newOrder")]
[HttpPost("/orders")]
public async Task<ActionResult> CreateOrder(Order order)
```

<span data-ttu-id="55be0-227">이 특성을 사용 하 여 두 가지 주요 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-227">You specify two key elements with this attribute:</span></span>

- <span data-ttu-id="55be0-228">대상으로 할 수 있는 (이 경우)에 해당 하는 d 4의 pub/sub 구성 요소 `pubsub` 입니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-228">The Dapr pub/sub component to target (in this case `pubsub`).</span></span>
- <span data-ttu-id="55be0-229">구독할 항목입니다 (이 경우 `newOrder` ).</span><span class="sxs-lookup"><span data-stu-id="55be0-229">The topic to subscribe to (in this case `newOrder`).</span></span>

<span data-ttu-id="55be0-230">그런 다음 해당 항목에 대 한 메시지를 받을 때 해당 작업 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-230">Dapr then invokes that action method as it receives messages for that topic.</span></span>

<span data-ttu-id="55be0-231">또한 ASP.NET Core를 사용 하도록 설정 하 여 Eapr를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-231">You'll also need to enable ASP.NET Core to use Dapr.</span></span> <span data-ttu-id="55be0-232">Dapr .NET SDK는 클래스에서 호출할 수 있는 몇 가지 확장 메서드를 제공 합니다 `Startup` .</span><span class="sxs-lookup"><span data-stu-id="55be0-232">The Dapr .NET SDK provides several extension methods that can be invoked in the `Startup` class.</span></span>

<span data-ttu-id="55be0-233">`ConfigureServices`메서드에서 다음 확장 메서드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-233">In the `ConfigureServices` method, you must add the following extension method:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // ...
    services.AddControllers().AddDapr();
}
```

<span data-ttu-id="55be0-234">확장 메서드에 확장 메서드를 추가 하면 `AddDapr` `AddControllers` 필요한 서비스를 등록 하 여 MVC 파이프라인에 6apr를 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-234">Appending the `AddDapr` extension-method to the `AddControllers` extension-method registers the necessary services to integrate Dapr into the MVC pipeline.</span></span> <span data-ttu-id="55be0-235">또한 `DaprClient` 인스턴스를 종속성 주입 컨테이너에 등록 하 고이를 서비스에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-235">It also registers a `DaprClient` instance into the dependency injection container, which then can be injected anywhere into your service.</span></span>

<span data-ttu-id="55be0-236">`Configure`메서드에서 다음 미들웨어 구성 요소를 추가 하 여 d 4를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-236">In the `Configure` method, you must add the following middleware components to enable Dapr:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    // ...
    app.UseCloudEvents();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapSubscribeHandler();
        // ...
    });
}
```

<span data-ttu-id="55be0-237">에 대 한 `UseCloudEvents` 호출은 **CloudEvents** 미들웨어를 ASP.NET Core 미들웨어 파이프라인에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-237">The call to `UseCloudEvents` adds **CloudEvents** middleware into to the ASP.NET Core middleware pipeline.</span></span> <span data-ttu-id="55be0-238">이 미들웨어는 CloudEvents 구조화 된 형식을 사용 하는 요청을 래핑 해제 하므로 수신 메서드에서 이벤트 페이로드를 직접 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-238">This middleware will unwrap requests that use the CloudEvents structured format, so the receiving method can read the event payload directly.</span></span>

> <span data-ttu-id="55be0-239">[CloudEvents](https://cloudevents.io/) 는 표준화 된 메시징 형식으로, 플랫폼 간 이벤트 정보를 설명 하는 일반적인 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-239">[CloudEvents](https://cloudevents.io/) is a standardized messaging format, providing a common way to describe event information across platforms.</span></span> <span data-ttu-id="55be0-240">CloudEvents을 채택 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-240">Dapr embraces CloudEvents.</span></span> <span data-ttu-id="55be0-241">CloudEvents에 대 한 자세한 내용은 [CloudEvents 사양](https://github.com/cloudevents/spec/tree/v1.0)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55be0-241">For more information about CloudEvents, see the [cloudevents specification](https://github.com/cloudevents/spec/tree/v1.0).</span></span>

<span data-ttu-id="55be0-242">`MapSubscribeHandler`끝점 라우팅 구성에서를 호출 하면 응용 프로그램에 대 한 4 월 구독 끝점이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-242">The call to `MapSubscribeHandler` in the endpoint routing configuration will add a Dapr subscribe endpoint to the application.</span></span> <span data-ttu-id="55be0-243">이 끝점은에 대 한 요청에 응답 `/dapr/subscribe` 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-243">This endpoint will respond to requests on `/dapr/subscribe`.</span></span> <span data-ttu-id="55be0-244">이 끝점을 호출 하면 특성을 사용 하 여 데코레이팅된 모든 WebAPI 작업 메서드가 자동으로 검색 되 `Topic` 고,이에 대 한 구독을 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-244">When this endpoint is called, it will automatically find all WebAPI action methods decorated with the `Topic` attribute and instruct Dapr to create subscriptions for them.</span></span>

## <a name="pubsub-components"></a><span data-ttu-id="55be0-245">Pub/sub 구성 요소</span><span class="sxs-lookup"><span data-stu-id="55be0-245">Pub/sub components</span></span>

<span data-ttu-id="55be0-246">이 경우에는 메시지의 실제 전송을 처리 하는 4 개의 [pub/sub 구성 요소](https://github.com/dapr/components-contrib/tree/master/pubsub)</span><span class="sxs-lookup"><span data-stu-id="55be0-246">Dapr [pub/sub components](https://github.com/dapr/components-contrib/tree/master/pubsub) handle the actual transport of the messages.</span></span> <span data-ttu-id="55be0-247">몇 가지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-247">Several are available.</span></span> <span data-ttu-id="55be0-248">각는 pub/sub 기능을 구현 하기 위해 특정 메시지 브로커 제품을 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-248">Each encapsulates a specific message broker product to implement the pub/sub functionality.</span></span> <span data-ttu-id="55be0-249">작성 시 다음 pub/sub 구성 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-249">At the time of writing, the following pub/sub components were available:</span></span>

- <span data-ttu-id="55be0-250">Apache Kafka</span><span class="sxs-lookup"><span data-stu-id="55be0-250">Apache Kafka</span></span>
- <span data-ttu-id="55be0-251">Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="55be0-251">Azure Event Hubs</span></span>
- <span data-ttu-id="55be0-252">Azure Service Bus</span><span class="sxs-lookup"><span data-stu-id="55be0-252">Azure Service Bus</span></span>
- <span data-ttu-id="55be0-253">AWS SNS/SQS</span><span class="sxs-lookup"><span data-stu-id="55be0-253">AWS SNS/SQS</span></span>
- <span data-ttu-id="55be0-254">GCP Pub/Sub</span><span class="sxs-lookup"><span data-stu-id="55be0-254">GCP Pub/Sub</span></span>
- <span data-ttu-id="55be0-255">Hazelcast</span><span class="sxs-lookup"><span data-stu-id="55be0-255">Hazelcast</span></span>
- <span data-ttu-id="55be0-256">MQTT</span><span class="sxs-lookup"><span data-stu-id="55be0-256">MQTT</span></span>
- <span data-ttu-id="55be0-257">NAT</span><span class="sxs-lookup"><span data-stu-id="55be0-257">NATS</span></span>
- <span data-ttu-id="55be0-258">Pulsar</span><span class="sxs-lookup"><span data-stu-id="55be0-258">Pulsar</span></span>
- <span data-ttu-id="55be0-259">RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="55be0-259">RabbitMQ</span></span>
- <span data-ttu-id="55be0-260">Redis 스트림</span><span class="sxs-lookup"><span data-stu-id="55be0-260">Redis Streams</span></span>

> [!NOTE]
> <span data-ttu-id="55be0-261">Azure cloud stack에는 메시징 기능 (Azure Service Bus) 및 이벤트 스트리밍 (Azure Event Hub) 가용성이 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-261">The Azure cloud stack has both messaging functionality (Azure Service Bus) and event streaming (Azure Event Hub) availability.</span></span>

<span data-ttu-id="55be0-262">이러한 구성 요소는 [GitHub의 구성 요소-참여 저장소](https://github.com/dapr/components-contrib/tree/master/pubsub)에서 커뮤니티에 의해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-262">These components are created by the community in a [component-contrib repository on GitHub](https://github.com/dapr/components-contrib/tree/master/pubsub).</span></span> <span data-ttu-id="55be0-263">아직 지원 되지 않는 메시지 브로커에 대 한 사용자 고유의 Bapr 구성 요소를 작성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-263">You're encouraged to write your own Dapr component for a message broker that isn't yet supported.</span></span>

### <a name="configure-pubsub-components"></a><span data-ttu-id="55be0-264">Pub/sub 구성 요소 구성</span><span class="sxs-lookup"><span data-stu-id="55be0-264">Configure pub/sub components</span></span>

<span data-ttu-id="55be0-265">Eapr 구성 파일을 사용 하 여 사용할 pub/sub 구성 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-265">Using a Dapr configuration file, you can specify the pub/sub component(s) to use.</span></span> <span data-ttu-id="55be0-266">이 구성에는 여러 필드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-266">This configuration contains several fields.</span></span> <span data-ttu-id="55be0-267">`name`필드는 사용 하려는 pub/sub 구성 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-267">The `name` field specifies the pub/sub component that you want to use.</span></span> <span data-ttu-id="55be0-268">메시지를 보내거나 받을 때이 이름을 지정 해야 합니다 (앞에서 설명한 것 처럼 `PublishEventAsync` 메서드 시그니처에서).</span><span class="sxs-lookup"><span data-stu-id="55be0-268">When sending or receiving a message, you need to specify this name (as you saw earlier in the `PublishEventAsync` method signature).</span></span>

<span data-ttu-id="55be0-269">아래에 RabbitMQ message broker 구성 요소를 구성 하는 데 사용할 수 있는 4 가지 구성 파일의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-269">Below you see an example of a Dapr configuration file for configuring a RabbitMQ message broker component:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: pubsub-rq
spec:
  type: pubsub.rabbitmq
  version: v1
  metadata:
  - name: host
    value: "amqp://localhost:5672"
  - name: durable
    value: true
```

<span data-ttu-id="55be0-270">이 예제에서는 블록에서 메시지 broker 관련 구성을 지정할 수 있는 것을 볼 수 있습니다 `metadata` .</span><span class="sxs-lookup"><span data-stu-id="55be0-270">In this example, you can see that you can specify any message broker-specific configuration in the `metadata` block.</span></span> <span data-ttu-id="55be0-271">이 경우 RabbitMQ는 영 속 큐를 만들도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-271">In this case, RabbitMQ is configured to create durable queues.</span></span> <span data-ttu-id="55be0-272">그러나 RabbitMQ 구성 요소에는 더 많은 구성 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-272">But the RabbitMQ component has more configuration options.</span></span> <span data-ttu-id="55be0-273">각 구성 요소의 구성에는 가능한 필드의 고유한 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-273">Each of the components' configuration will have its own set of possible fields.</span></span> <span data-ttu-id="55be0-274">각 [pub/sub 구성 요소의](https://docs.dapr.io/operations/components/setup-pubsub/supported-pubsub/)설명서에서 사용할 수 있는 필드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-274">You can read which fields are available in the documentation of each [pub/sub component](https://docs.dapr.io/operations/components/setup-pubsub/supported-pubsub/).</span></span>

<span data-ttu-id="55be0-275">코드에서 토픽을 구독 하는 프로그래밍 방식 옆의 경우에는 항목을 구독 하는 선언적 방법도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-275">Next to the programmatic way of subscribing to a topic from code, Dapr pub/sub also provides a declarative way of subscribing to a topic.</span></span> <span data-ttu-id="55be0-276">이 방법은 응용 프로그램 코드에서 Aapr 종속성을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-276">This approach removes the Dapr dependency from the application code.</span></span> <span data-ttu-id="55be0-277">따라서 기존 응용 프로그램은 코드를 변경 하지 않고 토픽을 구독할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-277">Therefore, it also enables an existing application to subscribe to topics without any changes to the code.</span></span> <span data-ttu-id="55be0-278">다음 예에서는 구독을 구성 하기 위한 4Apr 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-278">The following example shows a Dapr configuration file for configuring a subscription:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Subscription
metadata:
  name: newOrder-subscription
spec:
  pubsubname: pubsub
  topic: newOrder
  route: /orders
scopes:
- ServiceB
- ServiceC
```

<span data-ttu-id="55be0-279">모든 구독에서 여러 요소를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-279">You have to specify several elements with every subscription:</span></span>

- <span data-ttu-id="55be0-280">사용할 수 있는 (이 경우)에 해당 하는 d 4의 pub/sub 구성 요소의 이름 `pubsub` 입니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-280">The name of the Dapr pub/sub component you want to use (in this case `pubsub`).</span></span>
- <span data-ttu-id="55be0-281">구독할 항목의 이름입니다 (이 경우 `newOrder` ).</span><span class="sxs-lookup"><span data-stu-id="55be0-281">The name of the topic to subscribe to (in this case `newOrder`).</span></span>
- <span data-ttu-id="55be0-282">이 항목에 대해 호출 해야 하는 API 작업입니다 (이 경우 `/orders` ).</span><span class="sxs-lookup"><span data-stu-id="55be0-282">The API operation that needs to be called for this topic (in this case `/orders`).</span></span>
- <span data-ttu-id="55be0-283">[범위](https://docs.dapr.io/developing-applications/building-blocks/pubsub/pubsub-scopes/) 는 토픽을 게시 하 고 구독할 수 있는 서비스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-283">The [scope](https://docs.dapr.io/developing-applications/building-blocks/pubsub/pubsub-scopes/) can specify which services can publish and subscribe to a topic.</span></span>

## <a name="reference-application-eshopondapr"></a><span data-ttu-id="55be0-284">참조 응용 프로그램: eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="55be0-284">Reference application: eShopOnDapr</span></span>

<span data-ttu-id="55be0-285">함께 제공 되는 [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr) 앱은 4apr를 구현 하는 마이크로 서비스 응용 프로그램을 생성 하는 종단 간 참조 아키텍처를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-285">The accompanying [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr) app provides an end-to-end reference architecture for constructing a microservices application implementing Dapr.</span></span> <span data-ttu-id="55be0-286">eShopOnDapr은 몇 년 전에 만들어진 널리 사용 되는 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) 앱의 진화입니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-286">eShopOnDapr is an evolution of the widely popular [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) app, created several years ago.</span></span> <span data-ttu-id="55be0-287">두 버전 모두 마이크로 서비스에서 [통합 이벤트](https://devblogs.microsoft.com/cesardelatorre/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/#integration-events) 를 전달 하기 위해 pub/sub 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-287">Both versions use the pub/sub pattern for communicating [integration events](https://devblogs.microsoft.com/cesardelatorre/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/#integration-events) across microservices.</span></span> <span data-ttu-id="55be0-288">통합 이벤트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-288">Integration events include:</span></span>

- <span data-ttu-id="55be0-289">사용자가 쇼핑 바구니를 체크 아웃 하는 경우</span><span class="sxs-lookup"><span data-stu-id="55be0-289">When a user checks-out a shopping basket.</span></span>
- <span data-ttu-id="55be0-290">주문에 대 한 지불에 성공한 경우</span><span class="sxs-lookup"><span data-stu-id="55be0-290">When a payment for an order has succeeded.</span></span>
- <span data-ttu-id="55be0-291">구매 유예 기간이 만료 된 경우</span><span class="sxs-lookup"><span data-stu-id="55be0-291">When the grace-period of a purchase has expired.</span></span>

<span data-ttu-id="55be0-292">EShopOnContainers의 이벤트는 다음 인터페이스를 기반으로 합니다 `IEventBus` .</span><span class="sxs-lookup"><span data-stu-id="55be0-292">Eventing in eShopOnContainers is based on the following `IEventBus` interface:</span></span>

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent integrationEvent);

    void Subscribe<T, THandler>()
        where TEvent : IntegrationEvent
        where THandler : IIntegrationEventHandler<T>;
}
```

<span data-ttu-id="55be0-293">이 인터페이스의 구체적 구현은 RabbitMQ 및 Azure Service Bus에 대해 eShopOnContainers에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-293">Concrete implementations of this interface exist in eShopOnContainers for both RabbitMQ and Azure Service Bus.</span></span> <span data-ttu-id="55be0-294">각 구현에는 이해 하기 어렵고 유지 관리가 어려운 많은 사용자 지정 배관 코드가 포함 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-294">Each implementation included a great deal of custom plumbing code that was complex to understand and difficult to maintain.</span></span>

<span data-ttu-id="55be0-295">최신 eShopOnDapr는 i 4를 사용 하 여 pub/sub 동작을 크게 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-295">The newer eShopOnDapr significantly simplifies pub/sub behavior by using Dapr.</span></span> <span data-ttu-id="55be0-296">예를 들어 `IEventBus` 인터페이스는 단일 메서드로 줄었습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-296">For example, the `IEventBus` interface was reduced to a single method:</span></span>

```csharp
public interface IEventBus
{
    Task PublishAsync(IntegrationEvent integrationEvent);
}
```

### <a name="publish-events"></a><span data-ttu-id="55be0-297">이벤트 게시</span><span class="sxs-lookup"><span data-stu-id="55be0-297">Publish events</span></span>

<span data-ttu-id="55be0-298">업데이트 된 eShopOnDapr에서 단일 구현에서는 `DaprEventBus` 모든 지원 메시지 broker를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-298">In the updated eShopOnDapr, a single `DaprEventBus` implementation can support any Dapr-supported message broker.</span></span> <span data-ttu-id="55be0-299">다음 코드 블록은 단순화 된 Publish 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-299">The following code block shows the simplified Publish method.</span></span> <span data-ttu-id="55be0-300">`PublishAsync`메서드가 Capr 클라이언트를 사용 하 여 이벤트를 게시 하는 방법에 유의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55be0-300">Note how the `PublishAsync` method uses the Dapr client to publish an event:</span></span>

```csharp
public class DaprEventBus : IEventBus
{
    private const string PubSubName = "pubsub";

    private readonly DaprClient _daprClient;
    private readonly ILogger<DaprEventBus> _logger;

    public DaprEventBus(DaprClient daprClient, ILogger<DaprEventBus> logger)
    {
        _daprClient = daprClient ?? throw new ArgumentNullException(nameof(daprClient));
        _logger = logger ?? throw new ArgumentNullException(nameof(logger));
    }

    public async Task PublishAsync(IntegrationEvent integrationEvent)
    {
        var topicName = integrationEvent.GetType().Name;

        // Dapr uses System.Text.Json which does not support serialization of a
        // polymorphic type hierarchy by default. Using object as the type
        // parameter causes all properties to be serialized.
        await _daprClient.PublishEventAsync<object>(PubSubName, topicName, integrationEvent);
    }
}
```

<span data-ttu-id="55be0-301">코드 조각에서 볼 수 있듯이 토픽 이름은 이벤트 형식의 이름에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-301">As you can see in the code snippet, the topic name is derived from event type's name.</span></span> <span data-ttu-id="55be0-302">모든 eShop 서비스는 추상화를 사용 하기 때문에 중요 `IEventBus` 한 응용 프로그램 코드를 *변경 하지* 않아도 되는 수정 따라.</span><span class="sxs-lookup"><span data-stu-id="55be0-302">Because all eShop services use the `IEventBus` abstraction, retrofitting Dapr required *absolutely no change* to the mainline application code.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55be0-303">Dapr SDK는를 사용 하 여 `System.Text.Json` 메시지를 serialize/deserialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-303">The Dapr SDK uses `System.Text.Json` to serialize/deserialize messages.</span></span> <span data-ttu-id="55be0-304">그러나에서는 `System.Text.Json` 기본적으로 파생 클래스의 속성을 serialize 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-304">However, `System.Text.Json` doesn't serialize properties of derived classes by default.</span></span> <span data-ttu-id="55be0-305">EShop 코드에서 이벤트는 종종 `IntegrationEvent` 통합 이벤트의 기본 클래스인로 명시적으로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-305">In the eShop code, an event is sometimes explicitly declared as an `IntegrationEvent`, the base class for integration events.</span></span> <span data-ttu-id="55be0-306">이러한 작업은 구체적 이벤트 유형이 비즈니스 논리에 따라 런타임에 동적으로 결정 되기 때문에 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-306">This is done because the concrete event type is determined dynamically at run time based on business logic.</span></span> <span data-ttu-id="55be0-307">결과적으로 이벤트는 파생 클래스가 아닌 기본 클래스의 형식 정보를 사용 하 여 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-307">As a result, the event is serialized using the type information of the base class and not the derived class.</span></span> <span data-ttu-id="55be0-308">`System.Text.Json`이 경우 파생 클래스의 모든 속성을 강제로 serialize 하려면 코드에서를 `object` 제네릭 형식 매개 변수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-308">To force `System.Text.Json` to serialize all properties of the derived class in this case, the code uses `object` as the generic type parameter.</span></span> <span data-ttu-id="55be0-309">자세한 내용은 [.net 설명서](../../standard/serialization/system-text-json-polymorphism.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55be0-309">For more information, see the [.NET documentation](../../standard/serialization/system-text-json-polymorphism.md).</span></span>

<span data-ttu-id="55be0-310">D 4를 사용 하 여 인프라 코드를 **크게 간소화할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-310">With Dapr, the infrastructure code is **dramatically simplified**.</span></span> <span data-ttu-id="55be0-311">서로 다른 메시지 브로커를 구분할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-311">It doesn't need to distinguish between the different message brokers.</span></span> <span data-ttu-id="55be0-312">이 추상화는 d 4에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-312">Dapr provides this abstraction for you.</span></span> <span data-ttu-id="55be0-313">필요한 경우 메시지 브로커를 쉽게 교환 하거나 여러 메시지 브로커 구성 요소를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-313">And if needed, you can easily swap out message brokers or configure multiple message broker components.</span></span>

### <a name="subscribe-to-events"></a><span data-ttu-id="55be0-314">이벤트 구독</span><span class="sxs-lookup"><span data-stu-id="55be0-314">Subscribe to events</span></span>

<span data-ttu-id="55be0-315">이전 eShopOnContainers 앱에는 각 메시지 브로커에 대 한 구독 구현을 처리 하는 *subscriptionmanagers* 가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-315">The earlier eShopOnContainers app contains *SubscriptionManagers* to handle the subscription implementation for each message broker.</span></span> <span data-ttu-id="55be0-316">각 관리자는 구독 이벤트를 처리 하기 위한 복잡 한 메시지 브로커 관련 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-316">Each manager contains complex message broker-specific code for handling subscription events.</span></span> <span data-ttu-id="55be0-317">이벤트를 수신 하려면 각 서비스에서 각 이벤트 형식에 대해 명시적으로 처리기를 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-317">To receive events, each service has to explicitly register a handler for each event-type.</span></span>

<span data-ttu-id="55be0-318">eShopOnDapr는 ASP.NET Core 라이브러리를 사용 하 여 이벤트 구독을 위한 통로를 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-318">eShopOnDapr streamlines the plumbing for event subscriptions by using Dapr ASP.NET Core libraries.</span></span> <span data-ttu-id="55be0-319">각 이벤트는 컨트롤러의 동작 메서드에서 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-319">Each event is handled by an action method in the controller.</span></span> <span data-ttu-id="55be0-320">`Topic`특성은 작업 메서드를 구독할 해당 항목의 이름으로 데코 레이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-320">A `Topic` attribute decorates the action method with the name of the corresponding topic to subscribe to.</span></span> <span data-ttu-id="55be0-321">에서 가져온 코드 조각은 `PaymentService` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-321">Here's a code snippet taken from the `PaymentService`:</span></span>

```csharp
[Route("api/v1/[controller]")]
[ApiController]
public class IntegrationEventController : ControllerBase
{
    private const string DAPR_PUBSUB_NAME = "pubsub";

    private readonly IServiceProvider _serviceProvider;

    public IntegrationEventController(IServiceProvider serviceProvider)
    {
        _serviceProvider = serviceProvider;
    }

    [HttpPost("OrderStatusChangedToValidated")]
    [Topic(DAPR_PUBSUB_NAME, "OrderStatusChangedToValidatedIntegrationEvent")]
    public async Task OrderStarted(OrderStatusChangedToValidatedIntegrationEvent integrationEvent)
    {
        var handler = _serviceProvider.GetRequiredService<OrderStatusChangedToValidatedIntegrationEventHandler>();
        await handler.Handle(integrationEvent);
    }
}
```

<span data-ttu-id="55be0-322">특성에서 `Topic` 이벤트의 .net 형식 이름이 토픽 이름으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-322">In the `Topic` attribute, the name of the .NET type of the event is used as the topic name.</span></span> <span data-ttu-id="55be0-323">이벤트를 처리 하기 위해 이전 eShopOnContainers 코드 베이스에 이미 있던 이벤트 처리기가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-323">For handling the event, an event handler that already existed in the earlier eShopOnContainers code base is invoked.</span></span> <span data-ttu-id="55be0-324">이전 예제에서 토픽 으로부터 받은 메시지는 `OrderStatusChangedToValidatedIntegrationEvent` 기존 이벤트 처리기를 호출 합니다 `OrderStatusChangedToValidatedIntegrationEventHandler` .</span><span class="sxs-lookup"><span data-stu-id="55be0-324">In the previous example, messages received from the `OrderStatusChangedToValidatedIntegrationEvent` topic invoke the existing `OrderStatusChangedToValidatedIntegrationEventHandler` event-handler.</span></span> <span data-ttu-id="55be0-325">D 4에서 구독 및 메시지 브로커에 대 한 기본 시작을 구현 하므로 많은 양의 원본 코드가 사용 되지 않고 코드 베이스에서 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-325">Because Dapr implements the underlying plumbing for subscriptions and message brokers, a large amount of original code became obsolete and was removed from the code-base.</span></span> <span data-ttu-id="55be0-326">이 코드의 대부분은 이해 하 고 유지 관리 하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-326">Much of this code was complex to understand and challenging to maintain.</span></span>

### <a name="use-pubsub-components"></a><span data-ttu-id="55be0-327">Pub/sub 구성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="55be0-327">Use pub/sub components</span></span>

<span data-ttu-id="55be0-328">EShopOnDapr 리포지토리 내에서 폴더는 `deployment` 및의 다양 한 배포 모드를 사용 하 여 응용 프로그램을 배포 하기 위한 파일을 포함 `Docker Compose` `Kubernetes` 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-328">Within the eShopOnDapr repository, a `deployment` folder contains files for deploying the application using different deployment modes: `Docker Compose` and `Kubernetes`.</span></span> <span data-ttu-id="55be0-329">폴더는 폴더를 `dapr` 포함 하는 이러한 각 폴더 내에 있습니다 `components` .</span><span class="sxs-lookup"><span data-stu-id="55be0-329">A `dapr` folder exists within each of these folders that holds a `components` folder.</span></span> <span data-ttu-id="55be0-330">이 폴더에는 `eshop-pubsub.yaml` 응용 프로그램이 pub/sub 동작에 사용할 수 있도록 하는 Eapr pub/sub 구성 요소의 구성이 포함 된 파일이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-330">This folder holds a file `eshop-pubsub.yaml` containing the configuration of the Dapr pub/sub component that the application will use for pub/sub behavior.</span></span> <span data-ttu-id="55be0-331">앞의 코드 조각에서 살펴본 것 처럼 사용 되는 pub/sub 구성 요소의 이름은 `pubsub` 입니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-331">As you saw in the earlier code snippets, the name of the pub/sub component used is `pubsub`.</span></span> <span data-ttu-id="55be0-332">`eshop-pubsub.yaml`폴더에 있는 파일의 내용은 `deployment/compose/dapr/components` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-332">Here's the content of the `eshop-pubsub.yaml` file in the `deployment/compose/dapr/components` folder:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: pubsub
  namespace: default
spec:
  type: pubsub.nats
  version: v1
  metadata:
  - name: natsURL
    value: nats://demo.nats.io:4222
```

<span data-ttu-id="55be0-333">위의 구성은이 예에 대 한 원하는 [nat 메시지 브로커](https://nats.io/) 를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-333">The preceding configuration specifies the desired [NATS message broker](https://nats.io/) for this example.</span></span> <span data-ttu-id="55be0-334">메시지 브로커를 변경 하려면 RabbitMQ 또는 Azure Service Bus와 같은 다른 메시지 브로커를 구성 하 고 yaml 파일을 업데이트 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-334">To change message brokers, you need only to configure a different message broker, such as RabbitMQ or Azure Service Bus and update the yaml file.</span></span> <span data-ttu-id="55be0-335">D 4를 사용 하면 메시지 브로커를 전환할 때 중요 하지 않은 서비스 코드가 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-335">With Dapr, there are no changes to your mainline service code when switching message brokers.</span></span>

<span data-ttu-id="55be0-336">마지막으로 "응용 프로그램에서 여러 메시지 broker가 필요한 이유는 무엇 인가요?" 라는 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-336">Finally, you might ask, "Why would I need multiple message brokers in an application?".</span></span> <span data-ttu-id="55be0-337">시스템이 서로 다른 특성을 가진 워크 로드를 처리 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-337">Many times a system will handle workloads with different characteristics.</span></span> <span data-ttu-id="55be0-338">한 이벤트는 하루에 한 번만 발생 하지만 또 다른 이벤트는 초당 5000 회 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-338">One event may occur 10 times a day, but another event occurs 5,000 times per second.</span></span> <span data-ttu-id="55be0-339">메시징 트래픽을 다른 메시지 브로커로 분할 하면 이점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-339">You may benefit by partitioning messaging traffic to different message brokers.</span></span> <span data-ttu-id="55be0-340">Eapr를 사용 하면 각각 다른 이름을 가진 여러 pub/sub 구성 요소 구성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-340">With Dapr, you can add multiple pub/sub component configurations, each with a different name.</span></span>

## <a name="summary"></a><span data-ttu-id="55be0-341">요약</span><span class="sxs-lookup"><span data-stu-id="55be0-341">Summary</span></span>

<span data-ttu-id="55be0-342">Pub/sub 패턴을 사용 하면 분산 응용 프로그램에서 서비스를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-342">The pub/sub pattern helps you decouple services in a distributed application.</span></span> <span data-ttu-id="55be0-343">응용 프로그램에서이 동작을 구현 하는 과정을 간소화 하는 & 구독 빌딩 블록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-343">The Dapr publish & subscribe building block simplifies implementing this behavior in your application.</span></span>

<span data-ttu-id="55be0-344">이 경우에는 특정 *토픽* 에 메시지를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-344">Through Dapr pub/sub, you can publish messages to a specific *topic*.</span></span> <span data-ttu-id="55be0-345">또한 빌딩 블록은 서비스를 쿼리하여 구독할 항목을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-345">As well, the building block will query your service to determine which topic(s) to subscribe to.</span></span>

<span data-ttu-id="55be0-346">HTTP를 통해 또는 Dapr 용 .NET SDK와 같은 언어별 Sdk 중 하나를 사용 하 여 Dapr pub/sub를 기본적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-346">You can use Dapr pub/sub natively over HTTP or by using one of the language-specific SDKs, such as the .NET SDK for Dapr.</span></span> <span data-ttu-id="55be0-347">.NET SDK는 ASP.NET core 플랫폼과 긴밀 하 게 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-347">The .NET SDK tightly integrates with the ASP.NET core platform.</span></span>

<span data-ttu-id="55be0-348">Eapr를 사용 하면 지원 되는 메시지 브로커 제품을 응용 프로그램에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-348">With Dapr, you can plug a supported message broker product into your application.</span></span> <span data-ttu-id="55be0-349">그런 다음 응용 프로그램에 코드를 변경할 필요 없이 메시지 브로커를 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55be0-349">You can then swap message brokers without requiring code changes to your application.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="55be0-350">[이전](service-invocation.md)
> [다음](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="55be0-350">[Previous](service-invocation.md)
[Next](bindings.md)</span></span>
