---
title: WCF 개발자를 위한 RPC gRPC의 유형
description: WCF에서 지원 되는 원격 프로시저 호출의 유형 및 gRPC의 해당 항목에 대 한 검토
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: ce5bf03b01dff3f7bb201ff08c9065abc2e58360
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841380"
---
# <a name="types-of-rpc"></a>RPC 형식

WCF (Windows Communication Foundation) 개발자는 다음과 같은 형식의 RPC (원격 프로시저 호출)를 처리 하는 데 사용 될 것입니다.

- 요청/회신
- 양면지
  - 세션을 사용 하는 단방향 이중
  - 세션이 포함 된 전이중
- 단방향

이러한 RPC 형식을 기존 gRPC 개념에 매우 자연스럽 게 매핑할 수 있으며,이 장에서는 이러한 각 영역을 차례로 살펴보겠습니다. [5 장](migrate-wcf-to-grpc.md)에서 비슷한 예를 훨씬 더 자세히 탐색 합니다.

| WCF | gRPC |
| --- | ---- |
| 일반 요청/회신 | 단항 |
| 클라이언트 콜백 인터페이스를 사용 하는 세션을 사용 하는 이중 서비스 | 서버 스트리밍 |
| 세션이 포함 된 전이중 서비스 | 양방향 스트리밍 |
| 단방향 작업 | 클라이언트 스트리밍 |

## <a name="requestreply"></a>요청/회신

적은 양의 데이터를 사용 하 고 반환 하는 간단한 요청/회신 방법의 경우 가장 간단한 gRPC 패턴 인 단항 RPC를 사용 합니다.

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

여기서 볼 수 있듯이 gRPC 단항 RPC 서비스 메서드를 구현 하는 것은 gRPC를 사용 하는 경우 인터페이스를 구현 하는 대신 기본 클래스 메서드를 재정의 한다는 점을 제외 하 고 WCF 작업을 구현 하는 것과 매우 비슷합니다. 서버에서 gRPC 기본 메서드는 서비스를 호출 하는 비동기 및 차단 메서드를 모두 제공 하지만 항상 <xref:System.Threading.Tasks.Task%601>반환 합니다.

## <a name="wcf-duplex-one-way-to-client"></a>WCF 이중, 클라이언트에 대 한 단방향

WCF 응용 프로그램 (특정 바인딩 사용)은 클라이언트와 서버 간에 영구 연결을 만들 수 있으며, 서버는 <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> 속성에 지정 된 *콜백 인터페이스* 를 사용 하 여 연결이 닫힐 때까지 비동기적으로 데이터를 클라이언트로 보낼 수 있습니다.

gRPC 서비스는 메시지 스트림과 비슷한 기능을 제공 합니다. 스트림은 구현 측면에서 WCF 이중 서비스와 *정확히* 매핑되지 않지만 동일한 결과를 얻을 수 있습니다.

### <a name="grpc-streaming"></a>gRPC 스트리밍

gRPC는 클라이언트에서 서버로, 그리고 서버에서 클라이언트로의 영구적 스트림을 만들 수 있도록 지원 합니다. 두 유형의 스트림이 동시에 활성화 될 수 있습니다. 이를 양방향 스트리밍 이라고 합니다. 스트림은 시간이 지남에 따라 임의의 비동기 메시징에 사용 하거나, 너무 커서 단일 요청 또는 응답으로 생성 하 고 보낼 수 없는 큰 데이터 집합을 전달 하는 데 사용할 수 있습니다.

다음 예제에서는 RPC를 서버 스트리밍 하는 방법을 보여 줍니다.

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

이 서버 스트림은 다음 코드와 같이 클라이언트 응용 프로그램에서 사용 될 수 있습니다.

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
> 서버 스트리밍 Rpc는 구독 스타일 서비스에 유용 하며 메모리에서 전체 데이터 집합을 작성 하는 것이 비효율적 이거나 불가능 한 경우 매우 큰 데이터 집합을 전송 하는 데에도 유용 합니다. 그러나 스트리밍 응답은 단일 메시지에 `repeated` 필드를 전송 하는 것 만큼 속도가 빠르기 때문에 작은 데이터 집합에 대 한 규칙 스트리밍을 사용 하면 안 됩니다.

### <a name="differences-to-wcf"></a>WCF와의 차이점

WCF 이중 서비스는 여러 메서드를 사용할 수 있는 클라이언트 콜백 인터페이스를 사용 합니다. GRPC 서버 스트리밍 서비스는 단일 스트림으로만 메시지를 보낼 수 있습니다. 여러 메서드를 사용 해야 하는 경우에는 [임의의 필드 또는 필드 중 하나](protobuf-any-oneof.md) 를 사용 하 여 메시지 유형을 사용 하 여 다른 메시지를 보내고 클라이언트에서 코드를 작성 하 여 처리 합니다.

WCF에서는 세션이 있는 [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) 클래스가 연결을 닫을 때까지 활성 상태로 유지 되 고 세션 내에서 여러 메서드가 호출 될 수 있습니다. GRPC에서 구현 메서드가 반환 하는 `Task`는 연결이 닫힐 때까지 완료 되지 않아야 합니다.

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a>WCF 단방향 작업 및 gRPC 클라이언트 스트리밍

WCF는 전송 관련 승인을 반환 하는 단방향 작업 (`[OperationContract(IsOneWay = true)]`로 표시 됨)을 제공 합니다. gRPC 서비스 메서드는 비어 있는 경우에도 항상 응답을 반환 하 고 클라이언트는 항상 해당 응답을 대기 해야 합니다. GRPC의 "실행 후 제거" 스타일 메시지의 경우 클라이언트 스트리밍 서비스를 만들 수 있습니다.

### <a name="thing_logproto"></a>thing_log proto

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

### <a name="thinglog-client-example"></a>ThingLog client 예제

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

이전 예제와 같이 클라이언트 스트리밍 Rpc를 다시 사용 하 여 서버에 매우 큰 데이터 집합을 보낼 수도 있습니다. 성능에 대 한 동일한 경고가 발생 합니다. 작은 데이터 집합의 경우 일반 메시지의 `repeated` 필드를 사용 합니다.

## <a name="wcf-full-duplex-services"></a>WCF 전이중 서비스

WCF 이중 바인딩은 서비스 인터페이스와 클라이언트 콜백 인터페이스 모두에서 여러 단방향 작업을 지원 하 여 클라이언트와 서버 간에 진행 되는 대화를 허용 합니다. gRPC는 양방향 스트리밍 Rpc와 유사한 항목을 지원 합니다. 두 매개 변수는 모두 `stream` 한정자로 표시 됩니다.

### <a name="chatproto"></a>채팅-프로토콜

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

이전 예제에서 구현 메서드가 요청 스트림 (`IAsyncStreamReader<MessageRequest>`)과 응답 스트림 (`IServerStreamWriter<MessageResponse>`)을 모두 수신 하 고 연결이 닫힐 때까지 메시지를 읽고 쓸 수 있음을 확인할 수 있습니다.

### <a name="chatter-client"></a>Chatter 클라이언트

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
