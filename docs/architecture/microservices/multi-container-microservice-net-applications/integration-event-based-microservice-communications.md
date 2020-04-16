---
title: 마이크로 서비스(통합 이벤트) 간 이벤트 기반 통신 구현
description: 컨테이너화된 .NET 애플리케이션용 .NET Microservices 아키텍처 | 마이크로 서비스 간의 이벤트 기반 통신을 구현하기 위해 통합 이벤트를 이해합니다.
ms.date: 10/02/2018
ms.openlocfilehash: 8a1d4950247d63e5684c85c029efccf8269e7435
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988325"
---
# <a name="implementing-event-based-communication-between-microservices-integration-events"></a><span data-ttu-id="6c5a6-103">마이크로 서비스(통합 이벤트) 간 이벤트 기반 통신 구현</span><span class="sxs-lookup"><span data-stu-id="6c5a6-103">Implementing event-based communication between microservices (integration events)</span></span>

<span data-ttu-id="6c5a6-104">앞서 설명한 대로 이벤트 기반 통신을 사용할 경우 마이크로 서비스는 비즈니스 엔터티를 업데이트할 때처럼 주목할 만한 무엇인가 발생할 때 이벤트를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-104">As described earlier, when you use event-based communication, a microservice publishes an event when something notable happens, such as when it updates a business entity.</span></span> <span data-ttu-id="6c5a6-105">다른 마이크로 서비스는 해당 이벤트를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-105">Other microservices subscribe to those events.</span></span> <span data-ttu-id="6c5a6-106">마이크로 서비스가 이벤트를 수신하면 자체 비즈니스 엔터티를 업데이트할 수 있고 더 많은 이벤트가 게시되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-106">When a microservice receives an event, it can update its own business entities, which might lead to more events being published.</span></span> <span data-ttu-id="6c5a6-107">이는 최종 일관성 개념의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-107">This is the essence of the eventual consistency concept.</span></span> <span data-ttu-id="6c5a6-108">해당 게시/구독 시스템은 일반적으로 이벤트 버스의 구현을 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-108">This publish/subscribe system is usually performed by using an implementation of an event bus.</span></span> <span data-ttu-id="6c5a6-109">이벤트 버스는 이벤트를 구독하고 취소하고 또 이벤트를 게시하기 위해 필요한 API를 갖춘 인터페이스로서 설계 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-109">The event bus can be designed as an interface with the API needed to subscribe and unsubscribe to events and to publish events.</span></span> <span data-ttu-id="6c5a6-110">이벤트 버스는 비동기 통신을 지원하는 메시징 큐 또는 서비스 및 게시/구독 모델 같은 프로세스 간 통신 또는 메시징 서비스에 기반한 하나 이상의 구현이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-110">It can also have one or more implementations based on any inter-process or messaging communication, such as a messaging queue or a service bus that supports asynchronous communication and a publish/subscribe model.</span></span>

<span data-ttu-id="6c5a6-111">다양한 서비스로 확장하는 비즈니스 트랜잭션을 구현할 이벤트를 사용하여 해당 서비스 간의 최종 일관성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-111">You can use events to implement business transactions that span multiple services, which gives you eventual consistency between those services.</span></span> <span data-ttu-id="6c5a6-112">결국 일관된 트랜잭션은 일련의 배포된 작업으로 구성돼 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-112">An eventually consistent transaction consists of a series of distributed actions.</span></span> <span data-ttu-id="6c5a6-113">각 작업에서 마이크로 서비스는 비즈니스 엔터티를 업데이트하고 다음 작업을 트리거하는 이벤트를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-113">At each action, the microservice updates a business entity and publishes an event that triggers the next action.</span></span> <span data-ttu-id="6c5a6-114">아래 그림 6-18에서는 및 이벤트 버스를 통해 게시된 PriceUpdated 이벤트를 보여줍니다. 따라서 가격 업데이트가 장바구니 및 기타 마이크로 서비스로 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-114">Figure 6-18 below, shows a PriceUpdated event published through and event bus, so the price update is propagated to the Basket and other microservices.</span></span>

![이벤트 버스와의 비동기 이벤트 기반 통신을 보여 주는 다이어그램](./media/integration-event-based-microservice-communications/event-driven-communication.png)

<span data-ttu-id="6c5a6-116">**그림 6-18**.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-116">**Figure 6-18**.</span></span> <span data-ttu-id="6c5a6-117">이벤트 버스에 기반한 이벤트 구동 통신</span><span class="sxs-lookup"><span data-stu-id="6c5a6-117">Event-driven communication based on an event bus</span></span>

<span data-ttu-id="6c5a6-118">이 섹션에서는 그림 6-18에 보이는 것 같이 일반 이벤트 버스 인터페이스를 사용하여 .NET와의 통신을 구현할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-118">This section describes how you can implement this type of communication with .NET by using a generic event bus interface, as shown in Figure 6-18.</span></span> <span data-ttu-id="6c5a6-119">RabbitMQ, Azure Service Bus 또는 기타 다른 타사 오픈 소스나 상용 서비스 버스 같은 인프라 또는 다른 기술을 사용하는 다양한 잠재적인 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-119">There are multiple potential implementations, each using a different technology or infrastructure such as RabbitMQ, Azure Service Bus, or any other third-party open-source or commercial service bus.</span></span>

## <a name="using-message-brokers-and-services-buses-for-production-systems"></a><span data-ttu-id="6c5a6-120">생산 시스템을 위해 메시지 브로커나 서비스 버스 사용</span><span class="sxs-lookup"><span data-stu-id="6c5a6-120">Using message brokers and services buses for production systems</span></span>

<span data-ttu-id="6c5a6-121">아키텍처 섹션에서 설명한 대로, 추상적인 이벤트 버스를 구현하기 위한 여러 메시징 기술을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-121">As noted in the architecture section, you can choose from multiple messaging technologies for implementing your abstract event bus.</span></span> <span data-ttu-id="6c5a6-122">그러나 이러한 기술은 수준이 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-122">But these technologies are at different levels.</span></span> <span data-ttu-id="6c5a6-123">예를 들어, 메시징 브로커 전송 기술인 RabbitMQ는 Azure Service Bus, NServiceBus, MassTransit, 또는 Brighter 같은 상업용 제품보다 수준이 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-123">For instance, RabbitMQ, a messaging broker transport, is at a lower level than commercial products like Azure Service Bus, NServiceBus, MassTransit, or Brighter.</span></span> <span data-ttu-id="6c5a6-124">이런 제품 대부분은 RabbitMQ 또는 Azure Service Bus에 기반해 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-124">Most of these products can work on top of either RabbitMQ or Azure Service Bus.</span></span> <span data-ttu-id="6c5a6-125">제품의 선택 기준은 애플리케이션에 얼마나 많은 기본 확장성과 얼마나 많은 기능이 필요한지에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-125">Your choice of product depends on how many features and how much out-of-the-box scalability you need for your application.</span></span>

<span data-ttu-id="6c5a6-126">개발 환경을 위한 이벤트 버스 개념 증명 구현하기 위해서는 eShopOnContainers 샘플에서와 같이 컨테이너로서 실행하는 RabbitMQ에서의 간단한 구현으로 충분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-126">For implementing just an event bus proof-of-concept for your development environment, as in the eShopOnContainers sample, a simple implementation on top of RabbitMQ running as a container might be enough.</span></span> <span data-ttu-id="6c5a6-127">높은 확장성이 필요한 중요 업무용 생산 시스템을 위해 Azure Service Bus를 평가하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-127">But for mission-critical and production systems that need high scalability, you might want to evaluate and use Azure Service Bus.</span></span>

<span data-ttu-id="6c5a6-128">분산 개발을 더 쉽게 만드는 장기 운영 프로세스를 위한 [Sagas](https://docs.particular.net/nservicebus/sagas/) 같이 고수준의 추상적 개념과 더 풍성한 기능을 요구하는 경우, NServiceBus, MassTransit, Brighter 같은 기타 상업용 및 오픈소스 서비스 버스는 평가할 만한 가치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-128">If you require high-level abstractions and richer features like [Sagas](https://docs.particular.net/nservicebus/sagas/) for long-running processes that make distributed development easier, other commercial and open-source service buses like NServiceBus, MassTransit, and Brighter are worth evaluating.</span></span> <span data-ttu-id="6c5a6-129">이 경우 사용할 추상적 개념과 API는 일반적으로 사용자 자신의 추상적 개념([eShopOnContainers에 제공되는 단순 이벤트 버스 추상적 개념](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/BuildingBlocks/EventBus/EventBus/Abstractions/IEventBus.cs)과 같은)이 아닌 고수준의 서비스 버스에서 제공하는 추상적 개념이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-129">In this case, the abstractions and API to use would usually be directly the ones provided by those high-level service buses instead of your own abstractions (like the [simple event bus abstractions provided at eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/BuildingBlocks/EventBus/EventBus/Abstractions/IEventBus.cs)).</span></span> <span data-ttu-id="6c5a6-130">이를 위해 [NServiceBus를 사용하여 포크된 eShopOnContainers](https://go.particular.net/eShopOnContainers)(특정 소프트웨어에 의해 구현된 추가 파생 샘플)를 연구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-130">For that matter, you can research the [forked eShopOnContainers using NServiceBus](https://go.particular.net/eShopOnContainers) (additional derived sample implemented by Particular Software).</span></span>

<span data-ttu-id="6c5a6-131">물론, RabbitMQ 및 Docker 같은 저수준의 기술을 기반으로 한 사용자 고유의 서비스 버스 기능은 항상 빌드할 수 있지만 “항목을 새로 개발하기 위해” 필요한 작업은 사용자 지정 엔터프라이즈 애플리케이션에 지나치게 높은 비용이 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-131">Of course, you could always build your own service bus features on top of lower-level technologies like RabbitMQ and Docker, but the work needed to "reinvent the wheel" might be too costly for a custom enterprise application.</span></span>

<span data-ttu-id="6c5a6-132">다시 말하면: eShopOnContainers 샘플에 소개된 샘플 이벤트 버스 추상화 및 구현은 개념 증명으로만 사용하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-132">To reiterate: the sample event bus abstractions and implementation showcased in the eShopOnContainers sample are intended to be used only as a proof of concept.</span></span> <span data-ttu-id="6c5a6-133">현재 섹션에 설명된 대로 비동기 및 이벤트 기반 통신을 원하는 경우 프로덕션 요구 사항에 가장 적합한 서비스 버스 제품을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-133">Once you have decided that you want to have asynchronous and event-driven communication, as explained in the current section, you should choose the service bus product that best fits your needs for production.</span></span>

## <a name="integration-events"></a><span data-ttu-id="6c5a6-134">통합 이벤트</span><span class="sxs-lookup"><span data-stu-id="6c5a6-134">Integration events</span></span>

<span data-ttu-id="6c5a6-135">통합 이벤트는 여러 마이크로 서비스 또는 외부 시스템에 걸쳐 동기화된 도메인 상태 전환에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-135">Integration events are used for bringing domain state in sync across multiple microservices or external systems.</span></span> <span data-ttu-id="6c5a6-136">이 작업은 마이크로 서비스 외부에 통합 이벤트를 게시함으로써 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-136">This is done by publishing integration events outside the microservice.</span></span> <span data-ttu-id="6c5a6-137">이벤트가 여러 수신기 마이크로 서비스(통합 이벤트를 구독하는 만큼 많은 마이크로 서비스)에 게시될 경우 각 수신기 마이크로 서비스에서의 적절한 이벤트 처리기가 해당 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-137">When an event is published to multiple receiver microservices (to as many microservices as are subscribed to the integration event), the appropriate event handler in each receiver microservice handles the event.</span></span>

<span data-ttu-id="6c5a6-138">통합 이벤트는 기본적으로 다음 예제와 같은 데이터 보유 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-138">An integration event is basically a data-holding class, as in the following example:</span></span>

```csharp
public class ProductPriceChangedIntegrationEvent : IntegrationEvent
{
    public int ProductId { get; private set; }
    public decimal NewPrice { get; private set; }
    public decimal OldPrice { get; private set; }

    public ProductPriceChangedIntegrationEvent(int productId, decimal newPrice,
        decimal oldPrice)
    {
        ProductId = productId;
        NewPrice = newPrice;
        OldPrice = oldPrice;
    }
}
```

<span data-ttu-id="6c5a6-139">통합 이벤트는 각 마이크로 서비스의 애플리케이션 수준에서 정의될 수 있으므로 Viewmodel이 서버와 클라이언트에서 정의되는 방법과 유사한 방식으로 마이크로 서비스가 서로 분리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-139">The integration events can be defined at the application level of each microservice, so they are decoupled from other microservices, in a way comparable to how ViewModels are defined in the server and client.</span></span> <span data-ttu-id="6c5a6-140">여러 마이크로 서비스에 걸쳐 있는 일반적인 통합 이벤트 라이브러리의 공유는 권장되지 않습니다. 이렇게 하면 단일 이벤트 정의 데이터 라이브러리와 마이크로 서비스가 연결되게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-140">What is not recommended is sharing a common integration events library across multiple microservices; doing that would be coupling those microservices with a single event definition data library.</span></span> <span data-ttu-id="6c5a6-141">여러 마이크로 서비스에 걸쳐 있는 공용 도메인 모델을 공유하고 싶지 않은 것과 동일한 이유로 이 작업을 수행하고 싶지 않습니다. 마이크로 서비스는 전적으로 자율적이어야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-141">You do not want to do that for the same reasons that you do not want to share a common domain model across multiple microservices: microservices must be completely autonomous.</span></span>

<span data-ttu-id="6c5a6-142">마이크로 서비스에 걸쳐 공유해야 할 몇 가지 유형의 라이브러리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-142">There are only a few kinds of libraries you should share across microservices.</span></span> <span data-ttu-id="6c5a6-143">하나는 eShopOnContainers에서처럼 [이벤트 버스 클라이언트 API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus)와 같은 최종 애플리케이션 블록으로서의 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-143">One is libraries that are final application blocks, like the [Event Bus client API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus), as in eShopOnContainers.</span></span> <span data-ttu-id="6c5a6-144">다른 하나는 JSON 직렬 변환기와 같은 NuGet 구성 요소로서 공유될 수 있는 도구를 구성하는 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-144">Another is libraries that constitute tools that could also be shared as NuGet components, like JSON serializers.</span></span>

## <a name="the-event-bus"></a><span data-ttu-id="6c5a6-145">이벤트 버스</span><span class="sxs-lookup"><span data-stu-id="6c5a6-145">The event bus</span></span>

<span data-ttu-id="6c5a6-146">이벤트 버스는 그림 6-19에 나와 있는 것처럼 서로를 명확히 인식하기 위한 구성 요소를 요구하지 않고 마이크로 서비스 간의 게시/구독 스타일 통신을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-146">An event bus allows publish/subscribe-style communication between microservices without requiring the components to explicitly be aware of each other, as shown in Figure 6-19.</span></span>

![기본 게시/구독 패턴을 보여 주는 다이어그램](./media/integration-event-based-microservice-communications/publish-subscribe-basics.png)

<span data-ttu-id="6c5a6-148">**그림 6-19**.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-148">**Figure 6-19**.</span></span> <span data-ttu-id="6c5a6-149">이벤트 버스를 사용한 게시/구독 기본 사항</span><span class="sxs-lookup"><span data-stu-id="6c5a6-149">Publish/subscribe basics with an event bus</span></span>

<span data-ttu-id="6c5a6-150">위 다이어그램에서는 마이크로 서비스 A는 게시자가 구독자를 알 필요 없이, 구독하는 마이크로 서비스 B와 C에 배포되는 이벤트 버스에 게시됨을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-150">The above diagram shows that microservice A publishes to Event Bus, which distributes to subscribing microservices B and C, without the publisher needing to know the subscribers.</span></span> <span data-ttu-id="6c5a6-151">이벤트 버스는 관찰자 패턴 및 게시-구독 패턴과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-151">The event bus is related to the Observer pattern and the publish-subscribe pattern.</span></span>

### <a name="observer-pattern"></a><span data-ttu-id="6c5a6-152">관찰자 패턴</span><span class="sxs-lookup"><span data-stu-id="6c5a6-152">Observer pattern</span></span>

<span data-ttu-id="6c5a6-153">[관찰자 패턴](https://en.wikipedia.org/wiki/Observer_pattern)에서, 기본 개체(관찰 가능한 객체라고도 함)가 관련 정보(이벤트)를 관심 있는 다른 개체(관찰자 라고도 함)에게 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-153">In the [Observer pattern](https://en.wikipedia.org/wiki/Observer_pattern), your primary object (known as the Observable) notifies other interested objects (known as Observers) with relevant information (events).</span></span>

### <a name="publishsubscribe-pubsub-pattern"></a><span data-ttu-id="6c5a6-154">게시-구독(Pub/Sub) 패턴</span><span class="sxs-lookup"><span data-stu-id="6c5a6-154">Publish/Subscribe (Pub/Sub) pattern</span></span>

<span data-ttu-id="6c5a6-155">[게시/구독 패턴](https://docs.microsoft.com/previous-versions/msp-n-p/ff649664(v=pandp.10))의 목적은 관찰자 패턴과 동일합니다. 특정 이벤트가 발생할 경우 다른 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-155">The purpose of the [Publish/Subscribe pattern](https://docs.microsoft.com/previous-versions/msp-n-p/ff649664(v=pandp.10)) is the same as the Observer pattern: you want to notify other services when certain events take place.</span></span> <span data-ttu-id="6c5a6-156">하지만 관찰자 패턴과 Pub/Sub 패턴 간에는 중요한 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-156">But there is an important difference between the Observer and Pub/Sub patterns.</span></span> <span data-ttu-id="6c5a6-157">관찰자 패턴에서는 관찰 가능 객체가 직접 관찰자에게 브로드캐스트를 수행함으로써 서로를 “알게”됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-157">In the observer pattern, the broadcast is performed directly from the observable to the observers, so they "know" each other.</span></span> <span data-ttu-id="6c5a6-158">하지만 Pub/Sub 패턴을 사용할 경우 게시자 및 구독자 모두 알고 있는 브로커 또는 메시지 브로커 또는 이벤트 버스라는 세 번째 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-158">But when using a Pub/Sub pattern, there is a third component, called broker or message broker or event bus, which is known by both the publisher and subscriber.</span></span> <span data-ttu-id="6c5a6-159">따라서 Pub/Sub 패턴을 사용 하는 경우 게시자와 구독자는 앞서 언급한 이벤트 버스 또는 메시지 브로커 덕분에 정확하게 분리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-159">Therefore, when using the Pub/Sub pattern the publisher and the subscribers are precisely decoupled thanks to the mentioned event bus or message broker.</span></span>

### <a name="the-middleman-or-event-bus"></a><span data-ttu-id="6c5a6-160">매개자 또는 이벤트 버스</span><span class="sxs-lookup"><span data-stu-id="6c5a6-160">The middleman or event bus</span></span>

<span data-ttu-id="6c5a6-161">게시자와 구독자 간에 익명성을 어떻게 달성합니까?</span><span class="sxs-lookup"><span data-stu-id="6c5a6-161">How do you achieve anonymity between publisher and subscriber?</span></span> <span data-ttu-id="6c5a6-162">모든 통신을 매개자가 처리하게 하는 것이 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-162">An easy way is let a middleman take care of all the communication.</span></span> <span data-ttu-id="6c5a6-163">이벤트 버스는 이러한 매개자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-163">An event bus is one such middleman.</span></span>

<span data-ttu-id="6c5a6-164">이벤트 버스는 일반적으로 두 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-164">An event bus is typically composed of two parts:</span></span>

- <span data-ttu-id="6c5a6-165">추상적 개념 또는 인터페이스 및</span><span class="sxs-lookup"><span data-stu-id="6c5a6-165">The abstraction or interface.</span></span>

- <span data-ttu-id="6c5a6-166">하나 이상의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-166">One or more implementations.</span></span>

<span data-ttu-id="6c5a6-167">그림 6-19에서는 애플리케이션의 관점에서 이벤트 버스가 어떻게 Pub/Sub 채널에 불과한지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-167">In Figure 6-19 you can see how, from an application point of view, the event bus is nothing more than a Pub/Sub channel.</span></span> <span data-ttu-id="6c5a6-168">이 비동기 통신을 구현하는 방법은 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-168">The way you implement this asynchronous communication can vary.</span></span> <span data-ttu-id="6c5a6-169">환경 요구 사항에 따라 두 요구 사항(예를 들어, 생산 대 개발 환경)을 서로 교체할 수 있도록 다양한 구현 방법을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-169">It can have multiple implementations so that you can swap between them, depending on the environment requirements (for example, production versus development environments).</span></span>

<span data-ttu-id="6c5a6-170">그림 6-20에서는 RabbitMQ, Azure Service Bus 또는 다른 이벤트/메시지 브로커 같은 메시징 인프라 기술을 기반으로 다중 구현을 통해 이벤트 버스의 추상적 개념을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-170">In Figure 6-20 you can see an abstraction of an event bus with multiple implementations based on infrastructure messaging technologies like RabbitMQ, Azure Service Bus, or another event/message broker.</span></span>

![이벤트 버스 추상화 레이어 추가를 보여 주는 다이어그램](./media/integration-event-based-microservice-communications/multiple-implementations-event-bus.png)

<span data-ttu-id="6c5a6-172">**그림 6-20.**</span><span class="sxs-lookup"><span data-stu-id="6c5a6-172">**Figure 6- 20.**</span></span> <span data-ttu-id="6c5a6-173">이벤트 버스의 다중 구현</span><span class="sxs-lookup"><span data-stu-id="6c5a6-173">Multiple implementations of an event bus</span></span>

<span data-ttu-id="6c5a6-174">RabbitMQ Azure Service bus 등 여러 기술로 구현할 수 있도록 인터페이스를 통해 이벤트 버스를 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-174">It's good to have the event bus defined through an interface so it can be implemented with several technologies, like RabbitMQ Azure Service bus or others.</span></span> <span data-ttu-id="6c5a6-175">그러나 전에 언급 한 것 처럼 고유한 추상적 개념(이벤트 버스 인터페이스) 사용은 추상적 개념의 지원을 받는 기본 이벤트 버스 기능이 필요한 경우에만 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-175">However, and as mentioned previously, using your own abstractions (the event bus interface) is good only if you need basic event bus features supported by your abstractions.</span></span> <span data-ttu-id="6c5a6-176">더 풍부한 서비스 버스 기능이 필요하면 고유한 추상적 개념 대신에 선호하는 상업용 서비스 버스가 제공하는 추상적 개념과 API를 사용해야 할지도 모릅니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-176">If you need richer service bus features, you should probably use the API and abstractions provided by your preferred commercial service bus instead of your own abstractions.</span></span>

### <a name="defining-an-event-bus-interface"></a><span data-ttu-id="6c5a6-177">이벤트 버스 인터페이스 정의</span><span class="sxs-lookup"><span data-stu-id="6c5a6-177">Defining an event bus interface</span></span>

<span data-ttu-id="6c5a6-178">이벤트 버스 인터페이스에 대한 구현 코드 및 탐색 목적으로 가능한 구현부터 시작하도록 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-178">Let's start with some implementation code for the event bus interface and possible implementations for exploration purposes.</span></span> <span data-ttu-id="6c5a6-179">인터페이스는 다음 인터페이스에서와 같이 일반적이고 간단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-179">The interface should be generic and straightforward, as in the following interface.</span></span>

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent @event);

    void Subscribe<T, TH>()
        where T : IntegrationEvent
        where TH : IIntegrationEventHandler<T>;

    void SubscribeDynamic<TH>(string eventName)
        where TH : IDynamicIntegrationEventHandler;

    void UnsubscribeDynamic<TH>(string eventName)
        where TH : IDynamicIntegrationEventHandler;

    void Unsubscribe<T, TH>()
        where TH : IIntegrationEventHandler<T>
        where T : IntegrationEvent;
}
```

<span data-ttu-id="6c5a6-180">`Publish` 메서드는 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-180">The `Publish` method is straightforward.</span></span> <span data-ttu-id="6c5a6-181">이벤트 버스는 모든 마이크로 서비스로 전달되는 통합 이벤트 또는 해당 이벤트를 구독하는 외부 애플리케이션을 브로드캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-181">The event bus will broadcast the integration event passed to it to any microservice, or even an external application, subscribed to that event.</span></span> <span data-ttu-id="6c5a6-182">이 메서드 해당 이벤트를 게시하는 마이크로 서비스가 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-182">This method is used by the microservice that is publishing the event.</span></span>

<span data-ttu-id="6c5a6-183">`Subscribe` 메서드(인수에 따라 몇 가지 구현이 있을 수 있습니다)는 이벤트를 수신하려는 마이크로 서비스에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-183">The `Subscribe` methods (you can have several implementations depending on the arguments) are used by the microservices that want to receive events.</span></span> <span data-ttu-id="6c5a6-184">이 메서드는 두 개의 인수를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-184">This method has two arguments.</span></span> <span data-ttu-id="6c5a6-185">첫 번째는 (`IntegrationEvent`)을 구독할 통합 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-185">The first is the integration event to subscribe to (`IntegrationEvent`).</span></span> <span data-ttu-id="6c5a6-186">두 번째 인수는 `IIntegrationEventHandler<T>`로 명명된 통합 이벤트 처리기(또는 콜백 메서드)로서, 수신기 마이크로 서비스가 해당 통합 이벤트 메시지를 수신할 때 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a6-186">The second argument is the integration event handler (or callback method), named `IIntegrationEventHandler<T>`, to be executed when the receiver microservice gets that integration event message.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6c5a6-187">추가 자료</span><span class="sxs-lookup"><span data-stu-id="6c5a6-187">Additional resources</span></span>

<span data-ttu-id="6c5a6-188">프로덕션 환경에서 사용할 수 있는 몇 가지 메시징 솔루션:</span><span class="sxs-lookup"><span data-stu-id="6c5a6-188">Some production-ready messaging solutions:</span></span>

- <span data-ttu-id="6c5a6-189">**Azure Service Bus** </span><span class="sxs-lookup"><span data-stu-id="6c5a6-189">**Azure Service Bus** </span></span>\
  <https://docs.microsoft.com/azure/service-bus-messaging/>
  
- <span data-ttu-id="6c5a6-190">**NServiceBus** </span><span class="sxs-lookup"><span data-stu-id="6c5a6-190">**NServiceBus** </span></span>\
  <https://particular.net/nservicebus>
  
- <span data-ttu-id="6c5a6-191">**MassTransit** </span><span class="sxs-lookup"><span data-stu-id="6c5a6-191">**MassTransit** </span></span>\
  <https://masstransit-project.com/>

> [!div class="step-by-step"]
> <span data-ttu-id="6c5a6-192">[이전](database-server-container.md)
> [다음](rabbitmq-event-bus-development-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="6c5a6-192">[Previous](database-server-container.md)
[Next](rabbitmq-event-bus-development-test-environment.md)</span></span>
