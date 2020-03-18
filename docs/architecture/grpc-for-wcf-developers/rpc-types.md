---
title: WCF 개발자를 위한 RPC 유형 - gRPC
description: WCF에서 지원하는 원격 프로시저 호출 유형 및 gRPC에서 이에 상응하는 형식 검토
ms.date: 09/02/2019
ms.openlocfilehash: b9d4ce7cae693ed7904229483cbccfe3b299b640
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401786"
---
# <a name="types-of-rpc"></a><span data-ttu-id="4668a-103">RPC 형식</span><span class="sxs-lookup"><span data-stu-id="4668a-103">Types of RPC</span></span>

<span data-ttu-id="4668a-104">WCF(Windows 통신 재단) 개발자는 다음과 같은 RPC(원격 프로시저 호출) 유형을 처리하는 데 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of remote procedure call (RPC):</span></span>

- <span data-ttu-id="4668a-105">요청/회신</span><span class="sxs-lookup"><span data-stu-id="4668a-105">Request/reply</span></span>
- <span data-ttu-id="4668a-106">이중:</span><span class="sxs-lookup"><span data-stu-id="4668a-106">Duplex:</span></span>
  - <span data-ttu-id="4668a-107">세션이 있는 단방향 양면</span><span class="sxs-lookup"><span data-stu-id="4668a-107">One-way duplex with session</span></span>
  - <span data-ttu-id="4668a-108">세션이 있는 전체 양면</span><span class="sxs-lookup"><span data-stu-id="4668a-108">Full duplex with session</span></span>
- <span data-ttu-id="4668a-109">단방향</span><span class="sxs-lookup"><span data-stu-id="4668a-109">One-way</span></span>

<span data-ttu-id="4668a-110">이러한 RPC 형식을 기존 gRPC 개념에 상당히 자연스럽게 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts.</span></span> <span data-ttu-id="4668a-111">이 장에서는 이러한 각 영역을 차례로 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-111">This chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="4668a-112">[5장에서는](migrate-wcf-to-grpc.md) 비슷한 예제를 더 자세히 살펴봅습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-112">[Chapter 5](migrate-wcf-to-grpc.md) will explore similar examples in greater depth.</span></span>

| <span data-ttu-id="4668a-113">WCF</span><span class="sxs-lookup"><span data-stu-id="4668a-113">WCF</span></span> | <span data-ttu-id="4668a-114">gRPC</span><span class="sxs-lookup"><span data-stu-id="4668a-114">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="4668a-115">정기적인 요청/회신</span><span class="sxs-lookup"><span data-stu-id="4668a-115">Regular request/reply</span></span> | <span data-ttu-id="4668a-116">단항 연산자</span><span class="sxs-lookup"><span data-stu-id="4668a-116">Unary</span></span> |
| <span data-ttu-id="4668a-117">클라이언트 콜백 인터페이스를 사용하는 세션이 있는 양면 서비스</span><span class="sxs-lookup"><span data-stu-id="4668a-117">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="4668a-118">서버 스트리밍</span><span class="sxs-lookup"><span data-stu-id="4668a-118">Server streaming</span></span> |
| <span data-ttu-id="4668a-119">세션이 있는 전체 이중 서비스</span><span class="sxs-lookup"><span data-stu-id="4668a-119">Full duplex service with session</span></span> | <span data-ttu-id="4668a-120">양방향 스트리밍</span><span class="sxs-lookup"><span data-stu-id="4668a-120">Bidirectional streaming</span></span> |
| <span data-ttu-id="4668a-121">단방향 작업</span><span class="sxs-lookup"><span data-stu-id="4668a-121">One-way operations</span></span> | <span data-ttu-id="4668a-122">클라이언트 스트리밍</span><span class="sxs-lookup"><span data-stu-id="4668a-122">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="4668a-123">요청/회신</span><span class="sxs-lookup"><span data-stu-id="4668a-123">Request/reply</span></span>

<span data-ttu-id="4668a-124">소량의 데이터를 가져 와서 반환하는 간단한 요청 / 회신 방법을 보려면 가장 간단한 gRPC 패턴인 unary RPC를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-124">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

```protobuf
service Things {
    rpc Get(GetThingRequest) returns (GetThingResponse);
}
```

```csharp
public class ThingService : Things.ThingsBase
{
    public override async Task<GetThingResponse> Get(GetThingRequest request, ServerCallContext context)
    {
        // Get thing from database
        return new GetThingResponse { Thing = thing };
    }
}
```

```csharp
public async Task ShowThing(int thingId)
{
    var thing = await _thingsClient.GetAsync(new GetThingRequest { ThingId = thingId });
    Console.WriteLine($"{thing.Name}");
}
```

<span data-ttu-id="4668a-125">보시다시피 gRPC unary RPC 서비스 메서드를 구현하는 것은 WCF 작업을 구현하는 것과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-125">As you can see, implementing a gRPC unary RPC service method is similar to implementing a WCF operation.</span></span> <span data-ttu-id="4668a-126">차이점은 gRPC를 사용하면 인터페이스를 구현하는 대신 기본 클래스 메서드를 재정의한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-126">The difference is that with gRPC, you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="4668a-127">클라이언트는 서비스를 호출하는 비동기 <xref:System.Threading.Tasks.Task%601>및 차단 메서드를 모두 제공하지만 서버에서 gRPC 기본 메서드는 항상 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-127">On the server, gRPC base methods always return <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="4668a-128">WCF 이중, 클라이언트에 대한 한 가지 방법</span><span class="sxs-lookup"><span data-stu-id="4668a-128">WCF duplex, one way to client</span></span>

<span data-ttu-id="4668a-129">특정 바인딩이 있는 WCF 응용 프로그램은 클라이언트와 서버 간에 지속적인 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-129">WCF applications (with certain bindings) can create a persistent connection between client and server.</span></span> <span data-ttu-id="4668a-130">서버는 <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> 속성에 지정된 *콜백 인터페이스를* 사용하여 연결이 닫혀도 클라이언트에 데이터를 비동기적으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-130">The server can asynchronously send data to the client until the connection is closed, by using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="4668a-131">gRPC 서비스는 메시지 스트림과 유사한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-131">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="4668a-132">스트림은 구현 측면에서 WCF 듀플렉스 서비스에 *정확히* 매핑되지 는 않지만 동일한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-132">Streams don't map *exactly* to WCF duplex services in terms of implementation, but you can achieve the same results.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="4668a-133">gRPC 스트리밍</span><span class="sxs-lookup"><span data-stu-id="4668a-133">gRPC streaming</span></span>

<span data-ttu-id="4668a-134">gRPC는 클라이언트에서 서버로, 서버에서 클라이언트로 영구 스트림을 만드는 것을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-134">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="4668a-135">두 유형의 스트림이 동시에 활성화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-135">Both types of stream can be active concurrently.</span></span> <span data-ttu-id="4668a-136">이 기능을 양방향 스트리밍이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-136">This ability is called bidirectional streaming.</span></span>

<span data-ttu-id="4668a-137">시간에 따라 임의의 비동기 메시징에 스트림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-137">You can use streams for arbitrary, asynchronous messaging over time.</span></span> <span data-ttu-id="4668a-138">또는 단일 요청 또는 응답을 생성하고 전송하기에는 너무 큰 큰 데이터 집합을 전달하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-138">Or you can use them for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="4668a-139">다음 예제에서는 서버 스트리밍 RPC를 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-139">The following example shows a server-streaming RPC.</span></span>

```protobuf
service ClockStreamer {
    rpc Subscribe(ClockSubscribeRequest) returns (stream ClockMessage);
}
```

```csharp
public class ClockStreamerService : ClockStreamer.ClockStreamerBase
{
    public override async Task Subscribe(ClockSubscribeRequest request,
        IServerStreamWriter<ClockMessage> responseStream,
        ServerCallContext context)
    {
        while (!context.CancellationToken.IsCancellationRequested)
        {
            var time = DateTimeOffset.UtcNow;
            await responseStream.WriteAsync(new ClockMessage { message = $"The time is {time:t}." });
            await Task.Delay(TimeSpan.FromSeconds(10), context.CancellationToken);
        }
    }
}
```

<span data-ttu-id="4668a-140">다음 코드와 같이 이 서버 스트림을 클라이언트 응용 프로그램에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-140">This server stream can be consumed from a client application, as shown in the following code:</span></span>

```csharp
public async Task TellTheTimeAsync(CancellationToken token)
{
    var channel = GrpcChannel.ForAddress("https://localhost:5001");
    var client = new ClockStreamer.ClockStreamerClient(channel);

    var request = new ClockSubscribeRequest();
    var response = client.Subscribe(request);

    await foreach (var update in response.ResponseStream.ReadAllAsync(token))
    {
        Console.WriteLine(update.Message);
    }
}
```

> [!NOTE]
> <span data-ttu-id="4668a-141">서버 스트리밍 RPC는 구독 스타일 서비스에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-141">Server-streaming RPCs are useful for subscription-style services.</span></span> <span data-ttu-id="4668a-142">또한 전체 데이터 집합을 메모리에 빌드하는 것이 비효율적이거나 불가능한 경우 큰 데이터 집합을 보내는 데도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-142">They're also useful for sending large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="4668a-143">그러나 스트리밍 응답은 단일 메시지에서 필드를 `repeated` 보내는 것만큼 빠르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-143">However, streaming responses isn't as fast as sending `repeated` fields in a single message.</span></span> <span data-ttu-id="4668a-144">일반적으로 작은 데이터 집합에는 스트리밍을 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-144">As a rule, streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-from-wcf"></a><span data-ttu-id="4668a-145">WCF의 차이점</span><span class="sxs-lookup"><span data-stu-id="4668a-145">Differences from WCF</span></span>

<span data-ttu-id="4668a-146">WCF 듀플렉스 서비스는 여러 메서드를 가질 수 있는 클라이언트 콜백 인터페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-146">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="4668a-147">gRPC 서버 스트리밍 서비스는 단일 스트림을 통해서만 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-147">A gRPC server-streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="4668a-148">여러 메서드가 필요한 경우 [Any 필드 또는 필드 중 하나가](protobuf-any-oneof.md) 있는 메시지 형식을 사용하여 다른 메시지를 보내고 이를 처리하기 위해 클라이언트에 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-148">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="4668a-149">WCF에서 세션이 있는 [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) 클래스는 연결이 닫혀있을 때까지 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-149">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed.</span></span> <span data-ttu-id="4668a-150">세션 내에서 여러 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-150">Multiple methods can be called within the session.</span></span> <span data-ttu-id="4668a-151">gRPC에서 구현 `Task` 메서드가 반환하는 것은 연결이 닫혀야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-151">In gRPC, the `Task` that the implementation method returns shouldn't finish until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="4668a-152">WCF 단방향 작업 및 gRPC 클라이언트 스트리밍</span><span class="sxs-lookup"><span data-stu-id="4668a-152">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="4668a-153">WCF는 전송 관련 승인을 `[OperationContract(IsOneWay = true)]`반환하는 단방향 작업(표시)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-153">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="4668a-154">gRPC 서비스 메서드는 비어 있더라도 항상 응답을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-154">gRPC service methods always return a response, even if it's empty.</span></span> <span data-ttu-id="4668a-155">클라이언트는 항상 해당 응답을 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-155">The client should always await that response.</span></span> <span data-ttu-id="4668a-156">gRPC에서 메시징의 "불과 잊어버린" 스타일의 경우 클라이언트 스트리밍 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-156">For the "fire-and-forget" style of messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="4668a-157">thing_log.프로토</span><span class="sxs-lookup"><span data-stu-id="4668a-157">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="4668a-158">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="4668a-158">ThingLogService.cs</span></span>

```csharp
public class ThingLogService : Protos.ThingLog.ThingLogBase
{
    private static readonly ConnectionClosedResponse EmptyResponse = new ConnectionClosedResponse();
    private readonly ILogger<ThingLogService> _logger;
    public ThingLogService(ILogger<ThingLogService> logger)
    {
        _logger = logger;
    }

    public override async Task<CompletedResponse> OpenConnection(IAsyncStreamReader<Thing> requestStream, ServerCallContext context)
    {
        while (await requestStream.MoveNext(context.CancellationToken))
        {
            _logger.LogInformation(requestStream.Current.Description);
        }
        return EmptyResponse;
    }
}
```

### <a name="thinglog-client-example"></a><span data-ttu-id="4668a-159">ThingLog 클라이언트 예제</span><span class="sxs-lookup"><span data-stu-id="4668a-159">ThingLog client example</span></span>

```csharp
public class ThingLogger : IAsyncDisposable
{
    private readonly ThingLog.ThingLogClient _client;
    private readonly AsyncClientStreamingCall<ThingLogRequest, CompletedResponse> _stream;

    public ThingLogger(ThingLog.ThingLogClient client)
    {
        _client = client;
        _stream = client.OpenConnection();
    }

    public async Task WriteAsync(string description)
    {
        await _stream.RequestStream.WriteAsync(new Thing
        {
            Description = description,
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        _stream.Dispose();
    }
}
```

<span data-ttu-id="4668a-160">이전 예제와 같이 클라이언트 스트리밍 RPC를 사용하여 화재 및 잊어버린 메시징을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-160">You can use client-streaming RPCs for fire-and-forget messaging, as shown in the previous example.</span></span> <span data-ttu-id="4668a-161">매우 큰 데이터 집합을 서버에 보내는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-161">You can also use them for sending very large datasets to the server.</span></span> <span data-ttu-id="4668a-162">성능에 대한 동일한 경고가 적용됩니다: `repeated` 작은 데이터 집합의 경우 일반 메시지에서 필드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-162">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="4668a-163">WCF 전이중 서비스</span><span class="sxs-lookup"><span data-stu-id="4668a-163">WCF full-duplex services</span></span>

<span data-ttu-id="4668a-164">WCF 듀플렉스 바인딩은 서비스 인터페이스와 클라이언트 콜백 인터페이스 모두에서 여러 단방향 작업을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-164">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface.</span></span> <span data-ttu-id="4668a-165">이 지원을 통해 클라이언트와 서버 간의 지속적인 대화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-165">This support allows ongoing conversations between client and server.</span></span> <span data-ttu-id="4668a-166">gRPC는 양방향 스트리밍 RPC와 유사한 것을 지원하며, 여기서 `stream` 두 매개 변수는 수정자로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-166">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="4668a-167">채팅.프로토</span><span class="sxs-lookup"><span data-stu-id="4668a-167">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="4668a-168">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="4668a-168">ChatterService.cs</span></span>

```csharp
public class ChatterService : Chatter.ChatterBase
{
    private readonly IChatHub _hub;

    public ChatterService(IChatHub hub)
    {
        _hub = hub;
    }

    public override async Task Connect(IAsyncStreamReader<MessageRequest> requestStream, IServerStreamWriter<MessageResponse> responseStream, ServerCallContext context)
    {
        _hub.MessageReceived += async (sender, args) =>
            await responseStream.WriteAsync(new MessageResponse {Text = args.Message});

        while (await requestStream.MoveNext(context.CancellationToken))
        {
            await _hub.SendAsync(requestStream.Current.Text);
        }
    }
}
```

<span data-ttu-id="4668a-169">이전 예제에서 구현 메서드는 요청 스트림()`IAsyncStreamReader<MessageRequest>`및 응답 스트림()을`IServerStreamWriter<MessageResponse>`모두 수신하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-169">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`).</span></span> <span data-ttu-id="4668a-170">메서드는 연결이 닫혀야 메시지를 읽고 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4668a-170">The method can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="4668a-171">채터 클라이언트</span><span class="sxs-lookup"><span data-stu-id="4668a-171">Chatter client</span></span>

```csharp
public class Chat : IAsyncDisposable
{
    private readonly Chatter.ChatterClient _client;
    private readonly AsyncDuplexStreamingCall<MessageRequest, MessageResponse> _stream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _readTask;

    public Chat(Chatter.ChatterClient client)
    {
        _client = client;
        _stream = _client.Connect();
        _cancellationTokenSource = new CancellationTokenSource();
        _readTask = ReadAsync(_cancellationTokenSource.Token);
    }

    public async Task SendAsync(string message)
    {
        await _stream.RequestStream.WriteAsync(new MessageRequest {Text = message});
    }

    private async Task ReadAsync(CancellationToken token)
    {
        while (await _stream.ResponseStream.MoveNext(token))
        {
            Console.WriteLine(_stream.ResponseStream.Current.Text);
        }
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        await _readTask;
        _stream.Dispose();
    }
}
```

>[!div class="step-by-step"]
><span data-ttu-id="4668a-172">[이전](wcf-bindings.md)
>[다음](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="4668a-172">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
