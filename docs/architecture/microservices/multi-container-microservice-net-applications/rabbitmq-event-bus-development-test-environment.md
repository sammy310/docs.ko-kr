---
title: RabbitMQ를 사용하여 개발 또는 테스트 환경에 대한 이벤트 서비스 구현
description: 컨테이너화된 .NET 애플리케이션의 .NET 마이크로 서비스 아키텍처 | RabbitMQ를 사용하여 개발 또는 테스트 환경의 통합 이벤트에 대해 이벤트 버스 메시징 구현
ms.date: 10/02/2018
ms.openlocfilehash: ba1cea9384893955ae0743ac8d6a34c350224cd5
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711194"
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="e29b7-103">RabbitMQ를 사용하여 개발 또는 테스트 환경에 대한 이벤트 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="e29b7-103">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="e29b7-104">컨테이너에서 실행 중인 RabbitMQ에 기반하는 사용자 지정 이벤트 버스를 만들면 eShopOnContainers 애플리케이션이 수행한 대로 개발 및 테스트 환경에 대해서만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-104">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="e29b7-105">프로덕션에 사용 가능한 서비스 버스의 일부로 빌드하지 않으면 프로덕션 환경에 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-105">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="e29b7-106">간단한 사용자 지정 이벤트 버스에는 상용 서비스 버스에 있는 프로덕션에 사용 가능한 중요한 여러 기능이 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-106">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="e29b7-107">eShopOnContainers에서 이벤트 버스 사용자 지정 구현 중 하나는 기본적으로 RabbitMQ API를 사용하는 라이브러리입니다(Azure Service Bus에 기반한 다른 구현이 있음).</span><span class="sxs-lookup"><span data-stu-id="e29b7-107">One of the event bus custom implementation in eShopOnContainers is basically a library using the RabbitMQ API (There’s another implementation based on Azure Service Bus).</span></span>

<span data-ttu-id="e29b7-108">RabbitMQ를 사용하는 이벤트 버스 구현을 통해 그림 6-21에 표시된 대로 마이크로 서비스가 이벤트를 구독하고, 게시하고, 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-108">The event bus implementation with RabbitMQ lets microservices subscribe to events, publish events, and receive events, as shown in Figure 6-21.</span></span>

![메시지 발신자와 메시지 수신자 사이의 RabbitMQ를 보여 주는 다이어그램](./media/rabbitmq-event-bus-development-test-environment/rabbitmq-implementation.png)

<span data-ttu-id="e29b7-110">**그림 6-21**</span><span class="sxs-lookup"><span data-stu-id="e29b7-110">**Figure 6-21.**</span></span> <span data-ttu-id="e29b7-111">이벤트 버스의 RabbitMQ 구현</span><span class="sxs-lookup"><span data-stu-id="e29b7-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="e29b7-112">RabbitMQ는 메시지 게시자와 구독자 간에 배포를 처리하는 중개자의 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-112">RabbitMQ functions as an intermediary between message publisher and subscribers, to handle distribution.</span></span> <span data-ttu-id="e29b7-113">코드에서 EventBusRabbitMQ 클래스는 제네릭 IEventBus 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-113">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="e29b7-114">이 개발/테스트 버전에서 프로덕션 버전으로 교체할 수 있도록 종속성 주입에 기반합니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-114">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
}
```

<span data-ttu-id="e29b7-115">샘플 개발/테스트 이벤트 버스의 RabbitMQ 구현은 상용구 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-115">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="e29b7-116">RabbitMQ 서버에 대한 연결을 처리하고 큐에 메시지 이벤트를 게시하기 위한 코드를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-116">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="e29b7-117">또한 각 이벤트 유형에 대해 통합 이벤트 처리기의 컬렉션 사전을 구현해야 합니다. 이러한 이벤트 유형에는 그림 6-21에 표시된 대로 각 수신기 마이크로 서비스에 대한 다른 인스턴스화 및 구독이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-117">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 6-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="e29b7-118">RabbitMQ를 사용하여 단순 게시 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="e29b7-118">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="e29b7-119">다음 코드는 전체 시나리오를 보여주기 위해 RabbitMQ에서 이벤트 버스를 구현하는 ***간소화된*** 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-119">The following code is a ***simplified*** version of an event bus implementation for RabbitMQ, to showcase the whole scenario.</span></span> <span data-ttu-id="e29b7-120">실제로는 이러한 방식으로 연결을 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-120">You don't really handle the connection this way.</span></span> <span data-ttu-id="e29b7-121">전체 구현을 확인하려면 [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) 리포지토리에서 실제 코드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e29b7-121">To see the full implementation, see the actual code in the [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) repository.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Publish(IntegrationEvent @event)
    {
        var eventName = @event.GetType().Name;
        var factory = new ConnectionFactory() { HostName = _connectionString };
        using (var connection = factory.CreateConnection())
        using (var channel = connection.CreateModel())
        {
            channel.ExchangeDeclare(exchange: _brokerName,
                type: "direct");
            string message = JsonConvert.SerializeObject(@event);
            var body = Encoding.UTF8.GetBytes(message);
            channel.BasicPublish(exchange: _brokerName,
                routingKey: eventName,
                basicProperties: null,
                body: body);
       }
    }
}
```

<span data-ttu-id="e29b7-122">eShopOnContainers 애플리케이션에서 게시 메서드의 [실제 코드](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs)는 [Polly](https://github.com/App-vNext/Polly) 재시도 정책을 사용하여 향상됩니다. 그러면 RabbitMQ 컨테이너가 준비되지 않은 경우 특정 횟수로 작업을 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-122">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="e29b7-123">docker-compose가; 컨테이너를 시작할 때 발생할 수 있습니다. 예를 들어 RabbitMQ 컨테이너가 다른 컨테이너보다 느리게 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-123">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="e29b7-124">앞서 언급했듯이 이 코드가 개발/테스트 환경에서만 사용되도록 RabbitMQ에 여러 가지 구성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-124">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="e29b7-125">RabbitMQ API를 사용하여 구독 코드 구현</span><span class="sxs-lookup"><span data-stu-id="e29b7-125">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="e29b7-126">다음 코드는 게시 코드로 RabbitMQ에 대한 이벤트 버스 구현을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-126">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="e29b7-127">일반적으로 개선하는 경우가 아니면 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-127">Again, you usually do not need to change it unless you are improving it.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Subscribe<T, TH>()
        where T : IntegrationEvent
        where TH : IIntegrationEventHandler<T>
    {
        var eventName = _subsManager.GetEventKey<T>();

        var containsKey = _subsManager.HasSubscriptionsForEvent(eventName);
        if (!containsKey)
        {
            if (!_persistentConnection.IsConnected)
            {
                _persistentConnection.TryConnect();
            }

            using (var channel = _persistentConnection.CreateModel())
            {
                channel.QueueBind(queue: _queueName,
                                    exchange: BROKER_NAME,
                                    routingKey: eventName);
            }
        }

        _subsManager.AddSubscription<T, TH>();
    }
}
```

<span data-ttu-id="e29b7-128">각 이벤트 유형에는 RabbitMQ에서 이벤트를 가져오는 관련 채널이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-128">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="e29b7-129">그런 다음, 채널 및 이벤트 유형마다 필요한 만큼 많은 이벤트 처리기가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-129">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="e29b7-130">구독 메서드는 IIntegrationEventHandler 개체를 허용합니다. 이는 현재 마이크로 서비스의 콜백 메서드 및 해당 관련 IntegrationEvent 개체와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-130">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="e29b7-131">그런 다음, 코드는 클라이언트 마이크로 서비스마다 각 통합 이벤트 유형이 가질 수 있는 이벤트 처리기의 목록에 해당 이벤트 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-131">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="e29b7-132">클라이언트 코드가 이벤트를 구독하지 않은 경우 코드가 다른 서비스에서 해당 이벤트를 게시할 때 RabbitMQ의 푸시 스타일로 이벤트를 수신할 수 있도록 이벤트 유형에 대한 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-132">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>

<span data-ttu-id="e29b7-133">위에서 언급한 것처럼, eShopOnContainers에서 구현된 이벤트 버스는 주 시나리오만 처리하므로 프로덕션 환경에서 사용할 수 있는 준비가 되지 않았으므로 교육 목적으로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-133">As mentioned above, the event bus implemented in eShopOnContainers has only and educational purpose, since it only handles the main scenarios, so it's not ready for production.</span></span>

<span data-ttu-id="e29b7-134">프로덕션 시나리오의 경우 아래 추가 리소스(RabbitMQ 관련 내용)와 [마이크로 서비스 간 이벤트 기반 통신 구현](./integration-event-based-microservice-communications.md#additional-resources) 섹션을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e29b7-134">For production scenarios check the additional resources below, specific for RabbitMQ, and the [Implementing event-based communication between microservices](./integration-event-based-microservice-communications.md#additional-resources) section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e29b7-135">추가 자료</span><span class="sxs-lookup"><span data-stu-id="e29b7-135">Additional resources</span></span>

<span data-ttu-id="e29b7-136">RabbitMQ에 대한 지원이 포함된, 프로덕션 환경에서 사용할 수 있는 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="e29b7-136">A production-ready solutions with support for RabbitMQ.</span></span>

- <span data-ttu-id="e29b7-137">**EasyNetQ** - RabbitMQ용 오픈 소스 .NET API 클라이언트</span><span class="sxs-lookup"><span data-stu-id="e29b7-137">**EasyNetQ** - Open Source .NET API client for RabbitMQ </span></span>\
  <http://easynetq.com/>

- <span data-ttu-id="e29b7-138">**MassTransit** </span><span class="sxs-lookup"><span data-stu-id="e29b7-138">**MassTransit** </span></span>\
  <https://masstransit-project.com/>
  
>[!div class="step-by-step"]
><span data-ttu-id="e29b7-139">[이전](integration-event-based-microservice-communications.md)
>[다음](subscribe-events.md)</span><span class="sxs-lookup"><span data-stu-id="e29b7-139">[Previous](integration-event-based-microservice-communications.md)
[Next](subscribe-events.md)</span></span>
