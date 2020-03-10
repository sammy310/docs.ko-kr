---
title: WCF 개발자를 위한 RPC gRPC의 유형
description: WCF에서 지원 되는 원격 프로시저 호출의 유형 및 gRPC의 해당 항목에 대 한 검토
ms.date: 09/02/2019
ms.openlocfilehash: 58f097bac61395e6810155e8ae9a6bbf2219ec5e
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78675165"
---
# <a name="types-of-rpc"></a><span data-ttu-id="6a09c-103">RPC 형식</span><span class="sxs-lookup"><span data-stu-id="6a09c-103">Types of RPC</span></span>

<span data-ttu-id="6a09c-104">WCF (Windows Communication Foundation) 개발자는 다음과 같은 형식의 RPC (원격 프로시저 호출)를 처리 하는 데 사용 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of remote procedure call (RPC):</span></span>

- <span data-ttu-id="6a09c-105">요청/회신</span><span class="sxs-lookup"><span data-stu-id="6a09c-105">Request/reply</span></span>
- <span data-ttu-id="6a09c-106">양면지</span><span class="sxs-lookup"><span data-stu-id="6a09c-106">Duplex:</span></span>
  - <span data-ttu-id="6a09c-107">세션을 사용 하는 단방향 이중</span><span class="sxs-lookup"><span data-stu-id="6a09c-107">One-way duplex with session</span></span>
  - <span data-ttu-id="6a09c-108">세션이 포함 된 전이중</span><span class="sxs-lookup"><span data-stu-id="6a09c-108">Full duplex with session</span></span>
- <span data-ttu-id="6a09c-109">단방향</span><span class="sxs-lookup"><span data-stu-id="6a09c-109">One-way</span></span>

<span data-ttu-id="6a09c-110">이러한 RPC 형식을 기존 gRPC 개념에 매우 자연스럽 게 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts.</span></span> <span data-ttu-id="6a09c-111">이 장에서는 이러한 각 영역을 차례로 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-111">This chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="6a09c-112">[5 장에서](migrate-wcf-to-grpc.md) 는 비슷한 예를 더 자세히 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-112">[Chapter 5](migrate-wcf-to-grpc.md) will explore similar examples in greater depth.</span></span>

| <span data-ttu-id="6a09c-113">WCF</span><span class="sxs-lookup"><span data-stu-id="6a09c-113">WCF</span></span> | <span data-ttu-id="6a09c-114">gRPC</span><span class="sxs-lookup"><span data-stu-id="6a09c-114">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="6a09c-115">일반 요청/회신</span><span class="sxs-lookup"><span data-stu-id="6a09c-115">Regular request/reply</span></span> | <span data-ttu-id="6a09c-116">단항 연산자</span><span class="sxs-lookup"><span data-stu-id="6a09c-116">Unary</span></span> |
| <span data-ttu-id="6a09c-117">클라이언트 콜백 인터페이스를 사용 하는 세션을 사용 하는 이중 서비스</span><span class="sxs-lookup"><span data-stu-id="6a09c-117">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="6a09c-118">서버 스트리밍</span><span class="sxs-lookup"><span data-stu-id="6a09c-118">Server streaming</span></span> |
| <span data-ttu-id="6a09c-119">세션이 포함 된 전이중 서비스</span><span class="sxs-lookup"><span data-stu-id="6a09c-119">Full duplex service with session</span></span> | <span data-ttu-id="6a09c-120">양방향 스트리밍</span><span class="sxs-lookup"><span data-stu-id="6a09c-120">Bidirectional streaming</span></span> |
| <span data-ttu-id="6a09c-121">단방향 작업</span><span class="sxs-lookup"><span data-stu-id="6a09c-121">One-way operations</span></span> | <span data-ttu-id="6a09c-122">클라이언트 스트리밍</span><span class="sxs-lookup"><span data-stu-id="6a09c-122">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="6a09c-123">요청/회신</span><span class="sxs-lookup"><span data-stu-id="6a09c-123">Request/reply</span></span>

<span data-ttu-id="6a09c-124">적은 양의 데이터를 사용 하 고 반환 하는 간단한 요청/회신 방법의 경우 가장 간단한 gRPC 패턴 인 단항 RPC를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-124">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

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

<span data-ttu-id="6a09c-125">여기에서 볼 수 있듯이 gRPC 단항 RPC 서비스 메서드를 구현 하는 것은 WCF 작업을 구현 하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-125">As you can see, implementing a gRPC unary RPC service method is similar to implementing a WCF operation.</span></span> <span data-ttu-id="6a09c-126">GRPC의 경우 인터페이스를 구현 하는 대신 기본 클래스 메서드를 재정의 한다는 점이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-126">The difference is that with gRPC, you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="6a09c-127">클라이언트는 서비스를 호출 하는 비동기 및 차단 메서드를 모두 제공 하지만 서버에서 gRPC 기본 메서드는 항상 <xref:System.Threading.Tasks.Task%601>을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-127">On the server, gRPC base methods always return <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="6a09c-128">WCF 이중, 클라이언트에 대 한 한 가지 방법</span><span class="sxs-lookup"><span data-stu-id="6a09c-128">WCF duplex, one way to client</span></span>

<span data-ttu-id="6a09c-129">WCF 응용 프로그램 (특정 바인딩 사용)은 클라이언트와 서버 간에 영구 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-129">WCF applications (with certain bindings) can create a persistent connection between client and server.</span></span> <span data-ttu-id="6a09c-130">서버는 <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> 속성에 지정 된 *콜백 인터페이스* 를 사용 하 여 연결이 닫힐 때까지 클라이언트에 데이터를 비동기적으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-130">The server can asynchronously send data to the client until the connection is closed, by using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="6a09c-131">gRPC 서비스는 메시지 스트림과 비슷한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-131">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="6a09c-132">스트림은 구현 측면에서 WCF 이중 서비스와 *정확히* 매핑되지 않지만 동일한 결과를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-132">Streams don't map *exactly* to WCF duplex services in terms of implementation, but you can achieve the same results.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="6a09c-133">gRPC 스트리밍</span><span class="sxs-lookup"><span data-stu-id="6a09c-133">gRPC streaming</span></span>

<span data-ttu-id="6a09c-134">gRPC는 클라이언트에서 서버로, 그리고 서버에서 클라이언트로의 영구적 스트림을 만들 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-134">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="6a09c-135">두 스트림 유형 모두 동시에 활성화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-135">Both types of stream can be active concurrently.</span></span> <span data-ttu-id="6a09c-136">이 기능을 양방향 스트리밍 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-136">This ability is called bidirectional streaming.</span></span> 

<span data-ttu-id="6a09c-137">시간에 따른 임의의 비동기 메시징의 스트림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-137">You can use streams for arbitrary, asynchronous messaging over time.</span></span> <span data-ttu-id="6a09c-138">또는 단일 요청이 나 응답으로 생성 하 여 전송 하기에 너무 큰 큰 데이터 집합을 전달 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-138">Or you can use them for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="6a09c-139">다음 예제에서는 서버 스트리밍 RPC를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-139">The following example shows a server-streaming RPC.</span></span>

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

<span data-ttu-id="6a09c-140">다음 코드와 같이이 서버 스트림은 클라이언트 응용 프로그램에서 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-140">This server stream can be consumed from a client application, as shown in the following code:</span></span>

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
> <span data-ttu-id="6a09c-141">서버 스트리밍 Rpc는 구독 스타일 서비스에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-141">Server-streaming RPCs are useful for subscription-style services.</span></span> <span data-ttu-id="6a09c-142">또한 메모리에서 전체 데이터 집합을 빌드하는 것이 비효율적 이거나 불가능 한 경우에도 많은 데이터 집합을 보내는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-142">They're also useful for sending large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="6a09c-143">그러나 스트리밍 응답은 단일 메시지에 `repeated` 필드를 전송 하는 만큼 빠르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-143">However, streaming responses isn't as fast as sending `repeated` fields in a single message.</span></span> <span data-ttu-id="6a09c-144">일반적으로 작은 데이터 집합에는 스트리밍을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-144">As a rule, streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-from-wcf"></a><span data-ttu-id="6a09c-145">WCF와의 차이점</span><span class="sxs-lookup"><span data-stu-id="6a09c-145">Differences from WCF</span></span>

<span data-ttu-id="6a09c-146">WCF 이중 서비스는 여러 메서드를 사용할 수 있는 클라이언트 콜백 인터페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-146">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="6a09c-147">GRPC 서버-스트리밍 서비스는 단일 스트림으로만 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-147">A gRPC server-streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="6a09c-148">여러 메서드를 사용 해야 하는 경우에는 [임의의 필드 또는 필드 중 하나](protobuf-any-oneof.md) 를 사용 하 여 메시지 유형을 사용 하 여 다른 메시지를 보내고 클라이언트에서 코드를 작성 하 여 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-148">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="6a09c-149">WCF에서 세션이 있는 [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) 클래스는 연결이 닫힐 때까지 활성 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-149">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed.</span></span> <span data-ttu-id="6a09c-150">세션 내에서 여러 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-150">Multiple methods can be called within the session.</span></span> <span data-ttu-id="6a09c-151">GRPC에서 구현 메서드가 반환 하는 `Task` 연결이 닫힐 때까지 완료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-151">In gRPC, the `Task` that the implementation method returns shouldn't finish until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="6a09c-152">WCF 단방향 작업 및 gRPC 클라이언트 스트리밍</span><span class="sxs-lookup"><span data-stu-id="6a09c-152">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="6a09c-153">WCF는 전송 관련 승인을 반환 하는 단방향 작업 (`[OperationContract(IsOneWay = true)]`로 표시 됨)을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-153">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="6a09c-154">gRPC 서비스 메서드는 비어 있는 경우에도 항상 응답을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-154">gRPC service methods always return a response, even if it's empty.</span></span> <span data-ttu-id="6a09c-155">클라이언트는 항상 해당 응답을 대기 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-155">The client should always await that response.</span></span> <span data-ttu-id="6a09c-156">GRPC에서 "실행 후 제거" 유형의 메시징에 대 한 클라이언트 스트리밍 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-156">For the "fire-and-forget" style of messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="6a09c-157">thing_log proto</span><span class="sxs-lookup"><span data-stu-id="6a09c-157">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="6a09c-158">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="6a09c-158">ThingLogService.cs</span></span>

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

### <a name="thinglog-client-example"></a><span data-ttu-id="6a09c-159">ThingLog client 예제</span><span class="sxs-lookup"><span data-stu-id="6a09c-159">ThingLog client example</span></span>

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

<span data-ttu-id="6a09c-160">이전 예제에 표시 된 것 처럼 화재 및 잊은 메시징의 클라이언트 스트리밍 Rpc를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-160">You can use client-streaming RPCs for fire-and-forget messaging, as shown in the previous example.</span></span> <span data-ttu-id="6a09c-161">이를 사용 하 여 매우 큰 데이터 집합을 서버에 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-161">You can also use them for sending very large datasets to the server.</span></span> <span data-ttu-id="6a09c-162">성능에 대 한 동일한 경고가 발생 합니다. 작은 데이터 집합의 경우 일반 메시지의 `repeated` 필드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-162">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="6a09c-163">WCF 전이중 서비스</span><span class="sxs-lookup"><span data-stu-id="6a09c-163">WCF full-duplex services</span></span>

<span data-ttu-id="6a09c-164">WCF 이중 바인딩은 서비스 인터페이스와 클라이언트 콜백 인터페이스 모두에서 여러 단방향 작업을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-164">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface.</span></span> <span data-ttu-id="6a09c-165">이 지원을 통해 클라이언트와 서버 간의 지속적인 대화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-165">This support allows ongoing conversations between client and server.</span></span> <span data-ttu-id="6a09c-166">gRPC는 양방향 스트리밍 Rpc와 유사한 항목을 지원 합니다. 두 매개 변수는 모두 `stream` 한정자로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-166">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="6a09c-167">채팅-프로토콜</span><span class="sxs-lookup"><span data-stu-id="6a09c-167">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="6a09c-168">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="6a09c-168">ChatterService.cs</span></span>

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

<span data-ttu-id="6a09c-169">이전 예제에서 구현 메서드가 요청 스트림 (`IAsyncStreamReader<MessageRequest>`)과 응답 스트림 (`IServerStreamWriter<MessageResponse>`)을 모두 수신 하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-169">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`).</span></span> <span data-ttu-id="6a09c-170">메서드는 연결이 닫힐 때까지 메시지를 읽고 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a09c-170">The method can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="6a09c-171">Chatter 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6a09c-171">Chatter client</span></span>

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
><span data-ttu-id="6a09c-172">[이전](wcf-bindings.md)
>[다음](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="6a09c-172">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
