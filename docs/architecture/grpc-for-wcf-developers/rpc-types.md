---
title: WCF 개발자를 위한 RPC 유형 - gRPC
description: WCF에서 지원하는 원격 프로시저 호출 유형 및 gRPC에서 이에 상응하는 형식 검토
ms.date: 09/02/2019
ms.openlocfilehash: 40c0779dc015904e9dabbb448075e3c5aa5dc49a
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111090"
---
# <a name="types-of-rpc"></a>RPC 형식

WCF(Windows 통신 재단) 개발자는 다음과 같은 RPC(원격 프로시저 호출) 유형을 처리하는 데 익숙할 것입니다.

- 요청/회신
- 이중:
  - 세션이 있는 단방향 양면
  - 세션이 있는 전체 양면
- 단방향

이러한 RPC 형식을 기존 gRPC 개념에 상당히 자연스럽게 매핑할 수 있습니다. 이 장에서는 이러한 각 영역을 차례로 살펴봅니다. [5장에서는](migrate-wcf-to-grpc.md) 비슷한 예제를 더 자세히 살펴봅습니다.

| WCF | gRPC |
| --- | ---- |
| 정기적인 요청/회신 | 단항 |
| 클라이언트 콜백 인터페이스를 사용하는 세션이 있는 양면 서비스 | 서버 스트리밍 |
| 세션이 있는 전체 이중 서비스 | 양방향 스트리밍 |
| 단방향 작업 | 클라이언트 스트리밍 |

## <a name="requestreply"></a>요청/회신

소량의 데이터를 가져 와서 반환하는 간단한 요청 / 회신 방법을 보려면 가장 간단한 gRPC 패턴인 unary RPC를 사용합니다.

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

보시다시피 gRPC unary RPC 서비스 메서드를 구현하는 것은 WCF 작업을 구현하는 것과 유사합니다. 차이점은 gRPC를 사용하면 인터페이스를 구현하는 대신 기본 클래스 메서드를 재정의한다는 것입니다. 클라이언트는 서비스를 호출하는 비동기 <xref:System.Threading.Tasks.Task%601>및 차단 메서드를 모두 제공하지만 서버에서 gRPC 기본 메서드는 항상 반환됩니다.

## <a name="wcf-duplex-one-way-to-client"></a>WCF 이중, 클라이언트에 대한 한 가지 방법

특정 바인딩이 있는 WCF 응용 프로그램은 클라이언트와 서버 간에 지속적인 연결을 만들 수 있습니다. 서버는 <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> 속성에 지정된 *콜백 인터페이스를* 사용하여 연결이 닫혀도 클라이언트에 데이터를 비동기적으로 보낼 수 있습니다.

gRPC 서비스는 메시지 스트림과 유사한 기능을 제공합니다. 스트림은 구현 측면에서 WCF 듀플렉스 서비스에 *정확히* 매핑되지 는 않지만 동일한 결과를 얻을 수 있습니다.

### <a name="grpc-streaming"></a>gRPC 스트리밍

gRPC는 클라이언트에서 서버로, 서버에서 클라이언트로 영구 스트림을 만드는 것을 지원합니다. 두 유형의 스트림이 동시에 활성화될 수 있습니다. 이 기능을 양방향 스트리밍이라고 합니다.

시간에 따라 임의의 비동기 메시징에 스트림을 사용할 수 있습니다. 또는 단일 요청 또는 응답을 생성하고 전송하기에는 너무 큰 큰 데이터 집합을 전달하는 데 사용할 수 있습니다.

다음 예제에서는 서버 스트리밍 RPC를 보여 주며 있습니다.

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

다음 코드와 같이 이 서버 스트림을 클라이언트 응용 프로그램에서 사용할 수 있습니다.

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
> 서버 스트리밍 RPC는 구독 스타일 서비스에 유용합니다. 또한 전체 데이터 집합을 메모리에 빌드하는 것이 비효율적이거나 불가능한 경우 큰 데이터 집합을 보내는 데도 유용합니다. 그러나 스트리밍 응답은 단일 메시지에서 필드를 `repeated` 보내는 것만큼 빠르지 않습니다. 일반적으로 작은 데이터 집합에는 스트리밍을 사용해서는 안 됩니다.

### <a name="differences-from-wcf"></a>WCF의 차이점

WCF 듀플렉스 서비스는 여러 메서드를 가질 수 있는 클라이언트 콜백 인터페이스를 사용합니다. gRPC 서버 스트리밍 서비스는 단일 스트림을 통해서만 메시지를 보낼 수 있습니다. 여러 메서드가 필요한 경우 [Any 필드 또는 필드 중 하나가](protobuf-any-oneof.md) 있는 메시지 형식을 사용하여 다른 메시지를 보내고 이를 처리하기 위해 클라이언트에 코드를 작성합니다.

WCF에서 세션이 있는 [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) 클래스는 연결이 닫혀있을 때까지 유지됩니다. 세션 내에서 여러 메서드를 호출할 수 있습니다. gRPC에서 구현 `Task` 메서드가 반환하는 것은 연결이 닫혀야 합니다.

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a>WCF 단방향 작업 및 gRPC 클라이언트 스트리밍

WCF는 전송 관련 승인을 `[OperationContract(IsOneWay = true)]`반환하는 단방향 작업(표시)을 제공합니다. gRPC 서비스 메서드는 비어 있더라도 항상 응답을 반환합니다. 클라이언트는 항상 해당 응답을 기다려야 합니다. gRPC에서 메시징의 "불과 잊어버린" 스타일의 경우 클라이언트 스트리밍 서비스를 만들 수 있습니다.

### <a name="thing_logproto"></a>thing_log.프로토

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a>ThingLogService.cs

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

### <a name="thinglog-client-example"></a>ThingLog 클라이언트 예제

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

이전 예제와 같이 클라이언트 스트리밍 RPC를 사용하여 화재 및 잊어버린 메시징을 사용할 수 있습니다. 매우 큰 데이터 집합을 서버에 보내는 데 사용할 수도 있습니다. 성능에 대한 동일한 경고가 적용됩니다: `repeated` 작은 데이터 집합의 경우 일반 메시지에서 필드를 사용합니다.

## <a name="wcf-full-duplex-services"></a>WCF 전이중 서비스

WCF 듀플렉스 바인딩은 서비스 인터페이스와 클라이언트 콜백 인터페이스 모두에서 여러 단방향 작업을 지원합니다. 이 지원을 통해 클라이언트와 서버 간의 지속적인 대화를 수행할 수 있습니다. gRPC는 양방향 스트리밍 RPC와 유사한 것을 지원하며, 여기서 `stream` 두 매개 변수는 수정자로 표시됩니다.

### <a name="chatproto"></a>채팅.프로토

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a>ChatterService.cs

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

이전 예제에서 구현 메서드는 요청 스트림()`IAsyncStreamReader<MessageRequest>`및 응답 스트림()을`IServerStreamWriter<MessageResponse>`모두 수신하는 것을 볼 수 있습니다. 메서드는 연결이 닫혀야 메시지를 읽고 쓸 수 있습니다.

### <a name="chatter-client"></a>채터 클라이언트

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
>[이전](wcf-bindings.md)
>[다음](metadata.md)
