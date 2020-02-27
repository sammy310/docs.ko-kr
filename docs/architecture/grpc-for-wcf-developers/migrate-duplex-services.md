---
title: Wcf 개발자를 위한 gRPC gRPC로 WCF 이중 서비스 마이그레이션
description: 다양 한 형태의 WCF 이중 서비스를 gRPC 스트리밍 서비스로 마이그레이션하는 방법에 대해 알아봅니다.
ms.date: 09/02/2019
ms.openlocfilehash: 5737f02044ab9e4064f632164db764541a9c4d31
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628542"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a><span data-ttu-id="6e61c-103">gRPC로 WCF 이중 서비스 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="6e61c-103">Migrate WCF duplex services to gRPC</span></span>

<span data-ttu-id="6e61c-104">이제 기본 개념을 이해 했으므로이 섹션에서는 더 복잡 한 *스트리밍* grpc 서비스를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-104">Now that you have a sense of the basic concepts, in this section, you'll look at the more complicated *streaming* gRPC services.</span></span>

<span data-ttu-id="6e61c-105">WCF (Windows Communication Foundation)에서 이중 서비스를 사용 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-105">There are multiple ways to use duplex services in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="6e61c-106">일부 서비스는 클라이언트에서 시작 된 후 서버에서 데이터를 스트리밍합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-106">Some services are initiated by the client and then they stream data from the server.</span></span> <span data-ttu-id="6e61c-107">다른 전이중 서비스에는 WCF 설명서의 클래식 계산기 예제와 같이 더 많은 지속적인 양방향 통신이 수반 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-107">Other full-duplex services might involve more ongoing two-way communication, like the classic Calculator example in the WCF documentation.</span></span> <span data-ttu-id="6e61c-108">이 장에서는 두 가지 가능한 WCF 주식 시세를 구현 하 고 gRPC로 마이그레이션합니다. 하나는 RPC를 사용 하 고 다른 하나는 양방향 스트리밍 RPC를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-108">This chapter will take two possible WCF stock ticker implementations and migrate them to gRPC: one that uses a server streaming RPC and another one that uses a bidirectional streaming RPC.</span></span>

## <a name="server-streaming-rpc"></a><span data-ttu-id="6e61c-109">서버 스트리밍 RPC</span><span class="sxs-lookup"><span data-stu-id="6e61c-109">Server streaming RPC</span></span>

<span data-ttu-id="6e61c-110">[Sample SimpleStockTicker WCF 솔루션](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker)SimpleStockPriceTicker에는 클라이언트에서 주식 기호 목록과의 연결을 시작 하는 이중 서비스가 있으며 서버는 *콜백 인터페이스* 를 사용 하 여 업데이트를 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-110">In the [sample SimpleStockTicker WCF solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), SimpleStockPriceTicker, there's a duplex service for which the client starts the connection with a list of stock symbols, and the server uses the *callback interface* to send updates as they become available.</span></span> <span data-ttu-id="6e61c-111">클라이언트는 해당 인터페이스를 구현 하 여 서버에서 호출에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-111">The client implements that interface to respond to calls from the server.</span></span>

### <a name="the-wcf-solution"></a><span data-ttu-id="6e61c-112">WCF 솔루션</span><span class="sxs-lookup"><span data-stu-id="6e61c-112">The WCF solution</span></span>

<span data-ttu-id="6e61c-113">WCF 솔루션은 .NET Framework 4에서 자체 호스트 된 Net.tcp 서버로 구현 됩니다. *x* 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-113">The WCF solution is implemented as a self-hosted Net.TCP server in a .NET Framework 4.*x* console application.</span></span>

#### <a name="servicecontract"></a><span data-ttu-id="6e61c-114">ServiceContract</span><span class="sxs-lookup"><span data-stu-id="6e61c-114">ServiceContract</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

<span data-ttu-id="6e61c-115">서비스는 콜백 인터페이스 `ISimpleStockTickerCallback`를 사용 하 여 클라이언트에 실시간으로 데이터를 전송 하기 때문에 반환 형식이 없는 단일 메서드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-115">The service has a single method with no return type because it uses the callback interface `ISimpleStockTickerCallback` to send data to the client in real time.</span></span>

#### <a name="the-callback-interface"></a><span data-ttu-id="6e61c-116">콜백 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e61c-116">The callback interface</span></span>

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

<span data-ttu-id="6e61c-117">테스트 데이터를 제공 하기 위해 가짜 외부 종속성과 함께 이러한 인터페이스의 구현을 솔루션에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-117">You can find the implementations of these interfaces in the solution, along with faked external dependencies to provide test data.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="6e61c-118">gRPC 스트리밍</span><span class="sxs-lookup"><span data-stu-id="6e61c-118">gRPC streaming</span></span>

<span data-ttu-id="6e61c-119">실시간 데이터를 처리 하기 위한 gRPC 프로세스는 WCF 프로세스와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-119">The gRPC process for handling real-time data is different from the WCF process.</span></span> <span data-ttu-id="6e61c-120">클라이언트에서 서버로의 호출은 영구적 스트림을 만들 수 있습니다 .이 스트림은 비동기적으로 도착 하는 메시지에 대해 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-120">A call from client to server can create a persistent stream, which can be monitored for messages that arrive asynchronously.</span></span> <span data-ttu-id="6e61c-121">이러한 차이에도 불구 하 고 스트림은이 데이터를 처리 하는 보다 직관적인 방법일 수 있으며 LINQ, 반응 스트림, 함수형 프로그래밍 등을 강조 하는 최신 프로그래밍에서 더 관련성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-121">Despite the difference, streams can be a more intuitive way of dealing with this data and are more relevant in modern programming, which emphasizes LINQ, Reactive Streams, functional programming, and so on.</span></span>

<span data-ttu-id="6e61c-122">서비스 정의에는 요청 및 스트림에 대 한 두 개의 메시지가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-122">The service definition needs two messages: one for the request and one for the stream.</span></span> <span data-ttu-id="6e61c-123">서비스는 `return` 선언에서 `stream` 키워드를 사용 하 여 `StockTickerUpdate` 메시지의 스트림을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-123">The service returns a stream of the `StockTickerUpdate` message with the `stream` keyword in its `return` declaration.</span></span> <span data-ttu-id="6e61c-124">업데이트에 `Timestamp`을 추가 하 여 가격 변경의 정확한 시간을 표시 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-124">We recommend that you add a `Timestamp` to the update to show the exact time of the price change.</span></span>

#### <a name="simple_stock_tickerproto"></a><span data-ttu-id="6e61c-125">simple_stock_ticker proto</span><span class="sxs-lookup"><span data-stu-id="6e61c-125">simple_stock_ticker.proto</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.SimpleStockTickerServer.Protos";

import "google/protobuf/timestamp.proto";

package SimpleStockTickerServer;

service SimpleStockTicker {
  rpc Subscribe (SubscribeRequest) returns (stream StockTickerUpdate);
}

message SubscribeRequest {
  repeated string symbols = 1;
}

message StockTickerUpdate {
  string symbol = 1;
  int32 price_cents = 2;
  google.protobuf.Timestamp time = 3;
}
```

### <a name="implement-simplestockticker"></a><span data-ttu-id="6e61c-126">SimpleStockTicker 구현</span><span class="sxs-lookup"><span data-stu-id="6e61c-126">Implement SimpleStockTicker</span></span>

<span data-ttu-id="6e61c-127">`TraderSys.StockMarket` 클래스 라이브러리의 세 클래스를 대상 솔루션의 새 .NET Standard 클래스 라이브러리로 복사 하 여 WCF 프로젝트의 가짜 `StockPriceSubscriber`를 다시 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-127">Reuse the fake `StockPriceSubscriber` from the WCF project by copying the three classes from the `TraderSys.StockMarket` class library into a new .NET Standard class library in the target solution.</span></span> <span data-ttu-id="6e61c-128">모범 사례를 더 잘 따르려면 `Factory` 유형을 추가 하 여 인스턴스를 만들고 `IStockPriceSubscriberFactory` ASP.NET Core 종속성 주입 서비스에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-128">To better follow best practices, add a `Factory` type to create instances of it, and register the `IStockPriceSubscriberFactory` with the ASP.NET Core dependency injection services.</span></span>

#### <a name="the-factory-implementation"></a><span data-ttu-id="6e61c-129">팩터리 구현</span><span class="sxs-lookup"><span data-stu-id="6e61c-129">The factory implementation</span></span>

```csharp
public interface IStockPriceSubscriberFactory
{
    IStockPriceSubscriber GetSubscriber(string[] symbols);
}

public class StockPriceSubscriberFactory : IStockPriceSubscriberFactory
{
    public IStockPriceSubscriber GetSubscriber(string[] symbols)
    {
        return new StockPriceSubscriber(symbols);
    }
}
```

#### <a name="register-the-factory"></a><span data-ttu-id="6e61c-130">팩터리 등록</span><span class="sxs-lookup"><span data-stu-id="6e61c-130">Register the factory</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

<span data-ttu-id="6e61c-131">이제이 클래스를 사용 하 여 gRPC `StockTickerService`를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-131">This class can now be used to implement the gRPC `StockTickerService`.</span></span>

#### <a name="stocktickerservicecs"></a><span data-ttu-id="6e61c-132">StockTickerService.cs</span><span class="sxs-lookup"><span data-stu-id="6e61c-132">StockTickerService.cs</span></span>

```csharp
public class StockTickerService : Protos.SimpleStockTicker.SimpleStockTickerBase
{
    private readonly IStockPriceSubscriberFactory _subscriberFactory;

    public StockTickerService(IStockPriceSubscriberFactory subscriberFactory)
    {
        _subscriberFactory = subscriberFactory;
    }

    public override async Task Subscribe(SubscribeRequest request, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
    {
        var subscriber = _subscriberFactory.GetSubscriber(request.Symbols.ToArray());

        subscriber.Update += async (sender, args) =>
            await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

        await AwaitCancellation(context.CancellationToken);
    }

    private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
    {
        try
        {
            await stream.WriteAsync(new StockTickerUpdate
            {
                Symbol = symbol,
                PriceCents = (int)(price * 100),
                Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
            });
        }
        catch (Exception e)
        {
            // Handle any errors caused by broken connection, etc.
            _logger.LogError($"Failed to write message: {e.Message}");
        }
    }

    private static Task AwaitCancellation(CancellationToken token)
    {
        var completion = new TaskCompletionSource<object>();
        token.Register(() => completion.SetResult(null));
        return completion.Task;
    }
}
```

<span data-ttu-id="6e61c-133">여기에서 볼 수 있듯이 `.proto` 파일의 선언에서는 메서드가 `StockTickerUpdate` 메시지의 스트림을 반환 한다는 것을 나타내지만 실제로 `Task`를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-133">As you can see, although the declaration in the `.proto` file says the method returns a stream of `StockTickerUpdate` messages, it actually returns a `Task`.</span></span> <span data-ttu-id="6e61c-134">스트림을 만드는 작업은 생성 된 코드와 사용할 준비가 된 `IServerStreamWriter<StockTickerUpdate>` 응답 스트림을 제공 하는 gRPC 런타임 라이브러리에 의해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-134">The job of creating the stream is handled by the generated code and the gRPC runtime libraries, which provide the `IServerStreamWriter<StockTickerUpdate>` response stream, ready to use.</span></span>

<span data-ttu-id="6e61c-135">연결이 열려 있는 동안 서비스 클래스의 인스턴스가 활성 상태로 유지 되는 WCF 이중 서비스와 달리 gRPC 서비스는 반환 된 작업을 사용 하 여 서비스를 활성 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-135">Unlike a WCF duplex service, where the instance of the service class is kept alive while the connection is open, the gRPC service uses the returned task to keep the service alive.</span></span> <span data-ttu-id="6e61c-136">연결이 닫힐 때까지 작업을 완료 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-136">The task shouldn't complete until the connection is closed.</span></span>

<span data-ttu-id="6e61c-137">서비스는 `ServerCallContext`에서 `CancellationToken`를 사용 하 여 클라이언트가 연결을 닫은 시기를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-137">The service can tell when the client has closed the connection by using the `CancellationToken` from the `ServerCallContext`.</span></span> <span data-ttu-id="6e61c-138">간단한 정적 메서드인 `AwaitCancellation`은 토큰이 취소 될 때 완료 되는 작업을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-138">A simple static method, `AwaitCancellation`, is used to create a task that completes when the token is canceled.</span></span>

<span data-ttu-id="6e61c-139">`Subscribe` 메서드에서 `StockPriceSubscriber`를 가져오고 응답 스트림에 쓰는 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-139">In the `Subscribe` method, then, get a `StockPriceSubscriber` and add an event handler that writes to the response stream.</span></span> <span data-ttu-id="6e61c-140">그런 다음 연결이 닫힐 때까지 기다린 후 `subscriber`를 즉시 삭제 하 여 닫힌 스트림에 데이터를 쓰지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-140">Then wait for the connection to be closed before immediately disposing the `subscriber` to prevent it from trying to write data to the closed stream.</span></span>

<span data-ttu-id="6e61c-141">`WriteUpdateAsync` 메서드에는 스트림에 메시지가 기록 될 때 발생할 수 있는 오류를 처리할 수 있는 `try`/`catch` 블록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-141">The `WriteUpdateAsync` method has a `try`/`catch` block to handle any errors that might happen when a message is written to the stream.</span></span> <span data-ttu-id="6e61c-142">이러한 고려 사항은 네트워크를 통해 지속적으로 연결 하는 데 중요 하며, 의도적으로 또는 장애 중 어디에 있든 간에 중단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-142">This consideration is important in persistent connections over networks, which could be broken at any millisecond, whether intentionally or because of a failure somewhere.</span></span>

### <a name="use-stocktickerservice-from-a-client-application"></a><span data-ttu-id="6e61c-143">클라이언트 응용 프로그램에서 StockTickerService 사용</span><span class="sxs-lookup"><span data-stu-id="6e61c-143">Use StockTickerService from a client application</span></span>

<span data-ttu-id="6e61c-144">이전 섹션의 동일한 단계를 수행 하 여 `.proto` 파일에서 공유할 수 있는 클라이언트 클래스 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-144">Follow the same steps in the previous section to create a shareable client class library from the `.proto` file.</span></span> <span data-ttu-id="6e61c-145">이 샘플에는 클라이언트를 사용 하는 방법을 보여 주는 .NET Core 3.0 콘솔 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-145">In the sample, there's a .NET Core 3.0 console application that demonstrates how to use the client.</span></span>

#### <a name="example-programcs"></a><span data-ttu-id="6e61c-146">예 Program.cs</span><span class="sxs-lookup"><span data-stu-id="6e61c-146">Example Program.cs</span></span>

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        using var channel = GrpcChannel.ForAddress("https://localhost:5001");
        var client = new SimpleStockTicker.SimpleStockTickerClient(channel);

        var request = new SubscribeRequest();
        request.Symbols.AddRange(args);

        using var stream = client.Subscribe(request);

        var tokenSource = new CancellationTokenSource();

        var task = DisplayAsync(stream.ResponseStream, tokenSource.Token);

        WaitForExitKey();

        tokenSource.Cancel();
        await task;
    }
}
```

<span data-ttu-id="6e61c-147">이 경우 생성 된 클라이언트의 `Subscribe` 메서드는 비동기가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-147">In this case, the `Subscribe` method on the generated client isn't asynchronous.</span></span> <span data-ttu-id="6e61c-148">해당 `MoveNext` 메서드가 비동기이 고 처음 호출 될 때 스트림이 활성 상태가 될 때까지 완료 되지 않으므로 스트림은 즉시 만들어지고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-148">The stream is created and usable right away because its `MoveNext` method is asynchronous and the first time it's called it won't complete until the connection is alive.</span></span>

<span data-ttu-id="6e61c-149">스트림은 비동기 `DisplayAsync` 메서드에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-149">The stream is passed to an asynchronous `DisplayAsync` method.</span></span> <span data-ttu-id="6e61c-150">그런 다음 응용 프로그램은 사용자가 키를 누를 때까지 대기한 다음 `DisplayAsync` 메서드를 취소 하 고 종료 하기 전에 작업이 완료 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-150">The application then waits for the user to press a key, and then cancels the `DisplayAsync` method and waits for the task to complete before exiting.</span></span>

> [!NOTE]
> <span data-ttu-id="6e61c-151">이 코드는 new C# 8 `using` 선언 구문을 사용 하 여 `Main` 메서드가 종료 될 때 스트림과 채널을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-151">This code uses the new C# 8 `using` declaration syntax to dispose of the stream and the channel when the `Main` method exits.</span></span> <span data-ttu-id="6e61c-152">사소한 변경 이지만 들여쓰기와 빈 줄을 줄이는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-152">It's a small change, but a nice one that reduces indentations and empty lines.</span></span>

#### <a name="consume-the-stream"></a><span data-ttu-id="6e61c-153">스트림 사용</span><span class="sxs-lookup"><span data-stu-id="6e61c-153">Consume the stream</span></span>

<span data-ttu-id="6e61c-154">WCF는 콜백 인터페이스를 사용 하 여 서버가 클라이언트에서 직접 메서드를 호출할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-154">WCF uses callback interfaces to allow the server to call methods directly on the client.</span></span> <span data-ttu-id="6e61c-155">gRPC 스트림은 다르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-155">gRPC streams work differently.</span></span> <span data-ttu-id="6e61c-156">클라이언트는 반환 된 스트림을 반복 하 고 `IEnumerable`을 반환 하는 로컬 메서드에서 반환 된 것 처럼 메시지를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-156">The client iterates over the returned stream and processes messages, just as though they were returned from a local method returning an `IEnumerable`.</span></span>

<span data-ttu-id="6e61c-157">`IAsyncStreamReader<T>` 형식은 `IEnumerator<T>`와 매우 유사 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-157">The `IAsyncStreamReader<T>` type works much like an `IEnumerator<T>`.</span></span> <span data-ttu-id="6e61c-158">더 많은 데이터가 있는 경우 true를 반환 하 고, 최신 값을 반환 하는 `Current` 속성을 반환 하는 `MoveNext` 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-158">There's a `MoveNext` method that returns true as long as there's more data, and a `Current` property that returns the latest value.</span></span> <span data-ttu-id="6e61c-159">유일한 차이점은 `MoveNext` 메서드가 `bool`아니라 `Task<bool>`를 반환 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-159">The only difference is that the `MoveNext` method returns a `Task<bool>` instead of just a `bool`.</span></span> <span data-ttu-id="6e61c-160">`ReadAllAsync` 확장 메서드는 새 `await foreach` 구문과 함께 사용할 수 C# 있는 표준 8 `IAsyncEnumerable`의 스트림을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-160">The `ReadAllAsync` extension method wraps the stream in a standard C# 8 `IAsyncEnumerable` that can be used with the new `await foreach` syntax.</span></span>

```csharp
static async Task DisplayAsync(IAsyncStreamReader<StockTickerUpdate> stream, CancellationToken token)
{
    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            Console.WriteLine($"{update.Symbol}: {update.Price}");
        }
    }
    catch (RpcException e) when (e.StatusCode == StatusCode.Cancelled)
    {
        return;
    }
    catch (OperationCanceledException)
    {
        Console.WriteLine("Finished.");
    }
}
```

> [!TIP]
> <span data-ttu-id="6e61c-161">사후 프로그래밍 패턴을 사용 하는 개발자의 경우이 챕터의 끝에 있는 [클라이언트 라이브러리](client-libraries.md#iobservable) 섹션에서는 확장 메서드 및 클래스를 추가 하 여 `IObservable<T>``IAsyncStreamReader<T>` 래핑하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-161">For developers using reactive programming patterns, the section on [client libraries](client-libraries.md#iobservable) at the end of this chapter shows how to add an extension method and classes to wrap `IAsyncStreamReader<T>` in an `IObservable<T>`.</span></span>

<span data-ttu-id="6e61c-162">여기서는 네트워크 오류의 가능성으로 인해 예외를 catch 해야 하며 코드에서 <xref:System.Threading.CancellationToken>를 사용 하 여 루프를 중단 하기 때문에 발생 하는 <xref:System.OperationCanceledException> 때문에 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-162">Again, be sure to catch exceptions here because of the possibility of network failure, and because of the <xref:System.OperationCanceledException> that will inevitably be thrown because the code is using a <xref:System.Threading.CancellationToken> to break the loop.</span></span> <span data-ttu-id="6e61c-163">`RpcException` 형식에는 `StatusCode`를 포함 하 여 gRPC 런타임 오류에 대 한 유용한 정보가 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-163">The `RpcException` type has a lot of useful information about gRPC runtime errors, including the `StatusCode`.</span></span> <span data-ttu-id="6e61c-164">자세한 내용은 [4 장의 *오류 처리* ](error-handling.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e61c-164">For more information, see [*Error handling* in Chapter 4](error-handling.md).</span></span>

## <a name="bidirectional-streaming"></a><span data-ttu-id="6e61c-165">양방향 스트리밍</span><span class="sxs-lookup"><span data-stu-id="6e61c-165">Bidirectional streaming</span></span>

<span data-ttu-id="6e61c-166">WCF 전이중 서비스는 양방향으로 비동기 실시간 메시징을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-166">A WCF full-duplex service allows for asynchronous, real-time messaging in both directions.</span></span> <span data-ttu-id="6e61c-167">서버 스트리밍 예제에서 클라이언트는 요청을 시작한 다음 업데이트 스트림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-167">In the server streaming example, the client starts a request and then receives a stream of updates.</span></span> <span data-ttu-id="6e61c-168">더 나은 버전의 서비스를 사용 하면 클라이언트가 새 구독을 중지 하 고 만들지 않고도 목록에서 주식을 추가 하 고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-168">A better version of that service would allow the client to add and remove stocks from the list without having to stop and create a new subscription.</span></span> <span data-ttu-id="6e61c-169">해당 기능은 [FullStockTicker 샘플 솔루션](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker)에 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-169">That functionality has been implemented in the [FullStockTicker sample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span></span>

<span data-ttu-id="6e61c-170">`IFullStockTickerService` 인터페이스는 다음과 같은 세 가지 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-170">The `IFullStockTickerService` interface provides three methods:</span></span>

- <span data-ttu-id="6e61c-171">`Subscribe`는 연결을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-171">`Subscribe` starts the connection.</span></span>
- <span data-ttu-id="6e61c-172">`AddSymbol` 하 여 시청할 스톡 기호를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-172">`AddSymbol` adds a stock symbol to watch.</span></span>
- <span data-ttu-id="6e61c-173">`RemoveSymbol`는 조사 목록에서 기호를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-173">`RemoveSymbol` removes a symbol from the watched list.</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(IFullStockTickerCallback))]
public interface IFullStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe();

    [OperationContract(IsOneWay = true)]
    void AddSymbol(string symbol);

    [OperationContract(IsOneWay = true)]
    void RemoveSymbol(string symbol);
}
```

<span data-ttu-id="6e61c-174">콜백 인터페이스는 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-174">The callback interface remains the same.</span></span>

<span data-ttu-id="6e61c-175">이제 메시지가 전달 되는 두 개의 데이터 스트림 (클라이언트에서 서버로, 다른 하나는 서버에서 클라이언트로)이 있으므로 gRPC에서이 패턴을 구현 하는 것은 간단 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-175">Implementing this pattern in gRPC is less straightforward because there are now two streams of data with messages being passed: one from client to server and another from server to client.</span></span> <span data-ttu-id="6e61c-176">여러 메서드를 사용 하 여 추가 및 제거 작업을 구현할 수는 없지만, [3 장](protobuf-any-oneof.md)에서 설명 하는 `Any` 형식 또는 `oneof` 키워드를 사용 하 여 단일 스트림에서 둘 이상의 메시지 유형을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-176">It isn't possible to use multiple methods to implement the add and remove operations, but you can pass more than one type of message on a single stream by using either the `Any` type or the `oneof` keyword, which were covered in [Chapter 3](protobuf-any-oneof.md).</span></span>

<span data-ttu-id="6e61c-177">허용 되는 특정 형식 집합이 있는 경우 `oneof`는 것이 더 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-177">In a case where there's a specific set of types that are acceptable, `oneof` is a better way to go.</span></span> <span data-ttu-id="6e61c-178">`AddSymbolRequest` 또는 `RemoveSymbolRequest`을 보유할 수 있는 `ActionMessage`을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-178">Use an `ActionMessage` that can hold either an `AddSymbolRequest` or a `RemoveSymbolRequest`:</span></span>

```protobuf
message ActionMessage {
  oneof action {
    AddSymbolRequest add = 1;
    RemoveSymbolRequest remove = 2;
  }
}

message AddSymbolRequest {
  string symbol = 1;
}

message RemoveSymbolRequest {
  string symbol = 1;
}
```

<span data-ttu-id="6e61c-179">`ActionMessage` 메시지의 스트림을 사용 하는 양방향 스트리밍 서비스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-179">Declare a bidirectional streaming service that takes a stream of `ActionMessage` messages:</span></span>

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

<span data-ttu-id="6e61c-180">이 서비스의 구현은 앞의 예제와 유사 합니다. 단, `Subscribe` 메서드의 첫 번째 매개 변수는 이제 `Add` 및 `Remove` 요청을 처리 하는 데 사용할 수 있는 `IAsyncStreamReader<ActionMessage>`입니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-180">The implementation for this service is similar to that of the previous example, except the first parameter of the `Subscribe` method is now an `IAsyncStreamReader<ActionMessage>`, which can be used to handle the `Add` and `Remove` requests:</span></span>

```csharp
public override async Task Subscribe(IAsyncStreamReader<ActionMessage> requestStream, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
{
    using var subscriber = _subscriberFactory.GetSubscriber();

    subscriber.Update += async (sender, args) =>
        await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

    var actionsTask = HandleActions(requestStream, subscriber, context.CancellationToken);

    _logger.LogInformation("Subscription started.");
    await AwaitCancellation(context.CancellationToken);

    try { await actionsTask; } catch { /* Ignored */ }

    _logger.LogInformation("Subscription finished.");
}

private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
{
    try
    {
        await stream.WriteAsync(new StockTickerUpdate
        {
            Symbol = symbol,
            PriceCents = (int)(price * 100),
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }
    catch (Exception e)
    {
        // Handle any errors caused by broken connection, etc.
        _logger.LogError($"Failed to write message: {e.Message}");
    }
}

private static Task AwaitCancellation(CancellationToken token)
{
    var completion = new TaskCompletionSource<object>();
    token.Register(() => completion.SetResult(null));
    return completion.Task;
}
```

<span data-ttu-id="6e61c-181">GRPC가 생성 한 `ActionMessage` 클래스는 `Add` 및 `Remove` 속성 중 하나만 설정할 수 있도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-181">The `ActionMessage` class that gRPC has generated guarantees that only one of the `Add` and `Remove` properties can be set.</span></span> <span data-ttu-id="6e61c-182">어떤 종류의 메시지를 사용 하 고 있는지를 확인 하는 것은 `null` 되지 않은 것을 찾기 위한 올바른 방법 이지만 더 나은 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-182">Finding which one isn't `null` is a valid way to determine which type of message is used, but there's a better way.</span></span> <span data-ttu-id="6e61c-183">또한 코드 생성은 다음과 같이 `ActionMessage` 클래스에 `enum ActionOneOfCase`를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-183">The code generation also created an `enum ActionOneOfCase` in the `ActionMessage` class, which looks like this:</span></span>

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

<span data-ttu-id="6e61c-184">`ActionMessage` 개체의 속성 `ActionCase` `switch` 문과 함께 사용 하 여 설정 된 필드를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-184">The property `ActionCase` on the `ActionMessage` object can be used with a `switch` statement to determine which field is set:</span></span>

```csharp
private async Task HandleActions(IAsyncStreamReader<ActionMessage> requestStream, IFullStockPriceSubscriber subscriber, CancellationToken token)
{
    await foreach (var action in requestStream.ReadAllAsync(token))
    {
        switch (action.ActionCase)
        {
            case ActionMessage.ActionOneofCase.None:
                _logger.LogWarning("No Action specified.");
                break;
            case ActionMessage.ActionOneofCase.Add:
                subscriber.Add(action.Add.Symbol);
                break;
            case ActionMessage.ActionOneofCase.Remove:
                subscriber.Remove(action.Remove.Symbol);
                break;
            default:
                _logger.LogWarning($"Unknown Action '{action.ActionCase}'.");
                break;
        }
    }
}
```

> [!TIP]
> <span data-ttu-id="6e61c-185">`switch` 문에 알 수 없는 `ActionOneOfCase` 값이 발견 되 면 경고를 기록 하는 `default` 사례가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-185">The `switch` statement has a `default` case that logs a warning if it encounters an unknown `ActionOneOfCase` value.</span></span> <span data-ttu-id="6e61c-186">이는 클라이언트가 더 많은 작업을 추가한 `.proto` 파일의 최신 버전을 사용 하 고 있음을 나타내는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-186">This could be useful to indicate that a client is using a later version of the `.proto` file that has added more actions.</span></span> <span data-ttu-id="6e61c-187">이것은 `switch`를 사용 하 여 알려진 필드의 `null` 테스트 하는 것 보다 좋은 한 가지 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-187">This is one reason why using a `switch` is better than testing for `null` on known fields.</span></span>

### <a name="use-fullstocktickerservice-from-a-client-application"></a><span data-ttu-id="6e61c-188">클라이언트 응용 프로그램에서 FullStockTickerService 사용</span><span class="sxs-lookup"><span data-stu-id="6e61c-188">Use FullStockTickerService from a client application</span></span>

<span data-ttu-id="6e61c-189">이 보다 복잡 한 클라이언트를 사용 하는 방법을 보여 주는 간단한 .NET Core 3.0 WPF 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-189">There's a simple .NET Core 3.0 WPF application that demonstrates the use of this more complex client.</span></span> <span data-ttu-id="6e61c-190">[GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker)에서 전체 응용 프로그램을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-190">You can find the full application on [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span></span>

<span data-ttu-id="6e61c-191">클라이언트는 종속성 주입에서 `FullStockTicker.FullStockTickerClient` 형식의 인스턴스를 가져오는 `MainWindowViewModel` 클래스에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-191">The client is used in the `MainWindowViewModel` class, which gets an instance of the `FullStockTicker.FullStockTickerClient` type from dependency injection:</span></span>

```csharp
public class MainWindowViewModel : IAsyncDisposable, INotifyPropertyChanged
{
    private readonly FullStockTicker.FullStockTickerClient _client;
    private readonly AsyncDuplexStreamingCall<ActionMessage, StockTickerUpdate> _duplexStream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _responseTask;
    private string _addSymbol;

    public MainWindowViewModel(FullStockTicker.FullStockTickerClient client)
    {
        _cancellationTokenSource = new CancellationTokenSource();
        _client = client;
        _duplexStream = _client.Subscribe();
        _responseTask = HandleResponsesAsync(_cancellationTokenSource.Token);

        AddCommand = new AsyncCommand(Add, CanAdd);
    }
```

<span data-ttu-id="6e61c-192">이제 `client.Subscribe()` 메서드에서 반환 되는 개체는 gRPC 라이브러리 형식의 인스턴스이며 `AsyncDuplexStreamingCall<TRequest, TResponse>`는 서버에 요청을 보내는 데 필요한 `RequestStream`를 제공 하 고 응답을 처리 하기 위한 `ResponseStream`를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-192">The object returned by the `client.Subscribe()` method is now an instance of the gRPC library type `AsyncDuplexStreamingCall<TRequest, TResponse>`, which provides a `RequestStream` for sending requests to the server and a `ResponseStream` for handling responses.</span></span>

<span data-ttu-id="6e61c-193">요청 스트림은 일부 WPF `ICommand` 메서드에서 기호를 추가 및 제거 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-193">The request stream is used from some WPF `ICommand` methods to add and remove symbols.</span></span> <span data-ttu-id="6e61c-194">각 작업에 대해 `ActionMessage` 개체에 대 한 관련 필드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-194">For each operation, set the relevant field on an `ActionMessage` object:</span></span>

```csharp
private async Task Add()
{
    if (CanAdd())
    {
        await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Add = new AddSymbolRequest {Symbol = AddSymbol}});
    }
}

public async Task Remove(PriceViewModel priceViewModel)
{
    await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Remove = new RemoveSymbolRequest {Symbol = priceViewModel.Symbol}});
    Prices.Remove(priceViewModel);
}
```

> [!IMPORTANT]
> <span data-ttu-id="6e61c-195">메시지에 `oneof` 필드 값을 설정 하면 이전에 설정 된 필드가 자동으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-195">Setting a `oneof` field's value on a message automatically clears any fields that have been set previously.</span></span>

<span data-ttu-id="6e61c-196">응답 스트림은 `async` 메서드에서 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-196">The stream of responses is handled in an `async` method.</span></span> <span data-ttu-id="6e61c-197">창이 닫히면 반환 되는 `Task` 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-197">The `Task` it returns is held to be disposed when the window is closed:</span></span>

```csharp
private async Task HandleResponsesAsync(CancellationToken token)
{
    var stream = _duplexStream.ResponseStream;

    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            var price = Prices.FirstOrDefault(p => p.Symbol.Equals(update.Symbol));
            if (price == null)
            {
                price = new PriceViewModel(this) {Symbol = update.Symbol, Price = update.PriceCents / 100m};
                Prices.Add(price);
            }
            else
            {
                price.Price = update.PriceCents / 100m;
            }
        }
    }
    catch (OperationCancelledException) { }
}
```

### <a name="client-cleanup"></a><span data-ttu-id="6e61c-198">클라이언트 정리</span><span class="sxs-lookup"><span data-stu-id="6e61c-198">Client cleanup</span></span>

<span data-ttu-id="6e61c-199">창이 닫히고 `MainWindowViewModel` 삭제 된 경우 (`MainWindow`의 `Closed` 이벤트) `AsyncDuplexStreamingCall` 개체를 적절 하 게 삭제 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-199">When the window is closed and the `MainWindowViewModel` is disposed (from the `Closed` event of `MainWindow`), we recommend that you properly dispose the `AsyncDuplexStreamingCall` object.</span></span> <span data-ttu-id="6e61c-200">특히 `RequestStream`의 `CompleteAsync` 메서드를 호출 하 여 서버에서 스트림을 정상적으로 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-200">In particular, the `CompleteAsync` method on the `RequestStream` should be called to gracefully close the stream on the server.</span></span> <span data-ttu-id="6e61c-201">이 예제에서는 샘플 뷰 모델의 `DisposeAsync` 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-201">This example shows the `DisposeAsync` method from the sample view-model:</span></span>

```csharp
public async ValueTask DisposeAsync()
{
    try
    {
        await _duplexStream.RequestStream.CompleteAsync().ConfigureAwait(false);
        await _responseTask.ConfigureAwait(false);
    }
    finally
    {
        _duplexStream.Dispose();
    }
}
```

<span data-ttu-id="6e61c-202">요청 스트림을 닫으면 서버에서 적절 한 방식으로 자체 리소스를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-202">Closing request streams enables the server to dispose of its own resources in a timely way.</span></span> <span data-ttu-id="6e61c-203">이렇게 하면 서비스의 효율성 및 확장성을 향상 시키고 예외를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e61c-203">This improves the efficiency and scalability of services and prevents exceptions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6e61c-204">[이전](migrate-request-reply.md)
>[다음](streaming-versus-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="6e61c-204">[Previous](migrate-request-reply.md)
[Next](streaming-versus-repeated.md)</span></span>
