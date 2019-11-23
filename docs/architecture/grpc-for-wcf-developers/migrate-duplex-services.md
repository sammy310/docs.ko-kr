---
title: Wcf 개발자를 위한 gRPC gRPC로 WCF 이중 서비스 마이그레이션
description: 다양 한 형태의 WCF 이중 서비스를 gRPC 스트리밍 서비스로 마이그레이션하는 방법에 대해 알아봅니다.
ms.date: 09/02/2019
ms.openlocfilehash: e2248df20e5c2d8f96055d42ba684749251154bd
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971875"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a>gRPC로 WCF 이중 서비스 마이그레이션

기본 개념이 준비 되었으므로이 섹션에서는 더 복잡 한 *스트리밍* grpc 서비스를 살펴보겠습니다.

WCF (Windows Communication Foundation)에서 이중 서비스를 사용 하는 방법에는 여러 가지가 있습니다. 일부 서비스는 클라이언트에서 시작 된 후 서버에서 데이터를 스트리밍합니다. 다른 전이중 서비스에는 WCF 설명서의 클래식 "계산기" 예제와 같은 보다 지속적인 양방향 통신이 수반 될 수 있습니다. 이 장에서는 두 가지 WCF "Stock 종목" 구현을 사용 하 여 gRPC로 마이그레이션합니다. 하나는 서버 스트리밍 RPC를 사용 하 고 다른 하나는 양방향 스트리밍 RPC를 사용 합니다.

## <a name="server-streaming-rpc"></a>서버 스트리밍 RPC

[Sample SimpleStockTicker WCF 솔루션](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker) *SimpleStockPriceTicker*에는 클라이언트가 주식 기호 목록과의 연결을 시작 하 고 서버에서 *콜백 인터페이스* 를 사용 하 여 업데이트를 전송 하는 데 사용할 수 있는 이중 서비스가 있습니다. 클라이언트는 해당 인터페이스를 구현 하 여 서버에서 호출에 응답 합니다.

### <a name="the-wcf-solution"></a>WCF 솔루션

WCF 솔루션은 .NET Framework 4.x 콘솔 응용 프로그램에서 자체 호스팅 NetTCP 서버로 구현 됩니다.

#### <a name="the-servicecontract"></a>ServiceContract

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

서비스는 콜백 인터페이스 `ISimpleStockTickerCallback`를 사용 하 여 클라이언트에 실시간으로 데이터를 보내는 것 이므로 반환 형식이 없는 단일 메서드를 포함 합니다.

#### <a name="the-callback-interface"></a>콜백 인터페이스

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

이러한 인터페이스의 구현은 테스트 데이터를 제공 하기 위해 가짜 외부 종속성과 함께 솔루션에서 찾을 수 있습니다.

### <a name="grpc-streaming"></a>gRPC 스트리밍

실시간 데이터를 처리 하는 gRPC 방법이 다릅니다. 클라이언트에서 서버로의 호출은 영구적 스트림을 만들 수 있습니다 .이 스트림은 비동기적으로 도착 하는 메시지에 대해 모니터링할 수 있습니다. 이러한 차이에도 불구 하 고 스트림은이 데이터를 처리 하는 보다 직관적인 방법이 될 수 있으며, LINQ, 반응 스트림, 함수형 프로그래밍 등에 중점을 두어 최신 프로그래밍에 더 적합 합니다.

서비스 정의에는 요청에 대 한 메시지와 스트림의 두 가지 메시지가 필요 합니다. 서비스는 `return` 선언에서 `stream` 키워드를 사용 하 여 `StockTickerUpdate` 메시지의 스트림을 반환 합니다. 업데이트에 `Timestamp`을 추가 하 여 가격이 변경 된 정확한 시간을 표시 하는 것이 좋습니다.

#### <a name="simple_stock_tickerproto"></a>simple_stock_ticker proto

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

### <a name="implement-the-simplestockticker"></a>SimpleStockTicker 구현

`TraderSys.StockMarket` 클래스 라이브러리의 세 클래스를 대상 솔루션의 새 .NET Standard 클래스 라이브러리로 복사 하 여 WCF 프로젝트의 가짜 `StockPriceSubscriber`를 다시 사용 합니다. 모범 사례를 더 잘 따르려면 `Factory` 유형을 추가 하 여 인스턴스를 만들고 ASP.NET Core의 종속성 주입 서비스에 `IStockPriceSubscriberFactory`를 등록 합니다.

#### <a name="the-factory-implementation"></a>팩터리 구현

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

#### <a name="registering-the-factory"></a>팩터리 등록

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

이제이 클래스를 사용 하 여 gRPC StockTicker 서비스를 구현할 수 있습니다.

#### <a name="stocktickerservicecs"></a>StockTickerService.cs

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
            // Handle any errors due to broken connection etc.
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

여기에서 볼 수 있듯이 `.proto` 파일의 선언에서는 메서드가 `StockTickerUpdate` 메시지 스트림을 "반환" 한다고 표시 하지만 실제로는 바닐라 `Task`을 반환 합니다. 스트림을 만드는 작업은 생성 된 코드와 사용할 준비가 된 `IServerStreamWriter<StockTickerUpdate>` 응답 스트림을 제공 하는 gRPC 런타임 라이브러리에 의해 처리 됩니다.

연결이 열려 있는 동안 서비스 클래스의 인스턴스가 활성 상태로 유지 되는 WCF 이중 서비스와 달리 gRPC 서비스는 반환 된 작업을 사용 하 여 서비스를 활성 상태로 유지 합니다. 연결이 닫힐 때까지 작업을 완료 하면 안 됩니다.

서비스는 `ServerCallContext`에서 `CancellationToken`를 사용 하 여 클라이언트가 연결을 닫은 시기를 알 수 있습니다. 간단한 정적 메서드인 `AwaitCancellation`은 토큰이 취소 될 때 완료 되는 작업을 만드는 데 사용 됩니다.

`Subscribe` 메서드에서 `StockPriceSubscriber`를 가져오고 응답 스트림에 쓰는 이벤트 처리기를 추가 합니다. 그런 다음 연결이 닫힐 때까지 기다린 후 `subscriber`를 즉시 삭제 하 여 닫힌 스트림에 데이터를 쓰지 못하도록 합니다.

`WriteUpdateAsync` 메서드에는 스트림에 메시지를 쓸 때 발생할 수 있는 오류를 처리할 수 있는 `try`/`catch` 블록이 있습니다. 네트워크를 통한 영구 연결에서 중요 한 고려 사항으로, 의도적으로 또는 장애 때문에 언제 든 지 중단 될 수 있습니다.

### <a name="using-the-stocktickerservice-from-a-client-application"></a>클라이언트 응용 프로그램에서 StockTickerService 사용

이전 섹션의 동일한 단계를 수행 하 여 `.proto` 파일에서 공유할 수 있는 클라이언트 클래스 라이브러리를 만듭니다. 이 샘플에는 클라이언트를 사용 하는 방법을 보여 주는 .NET Core 3.0 콘솔 응용 프로그램이 있습니다.

#### <a name="example-programcs"></a>예 Program.cs

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

이 경우 생성 된 클라이언트의 `Subscribe` 메서드는 비동기가 아닙니다. 해당 `MoveNext` 메서드가 비동기이 고 처음 호출 될 때 스트림이 연결 될 때까지 완료 되지 않으므로 스트림은 즉시 만들어지고 사용할 수 있습니다.

스트림은 비동기 `DisplayAsync` 메서드에 전달 됩니다. 그런 다음 응용 프로그램은 사용자가 키를 누를 때까지 대기한 다음 `DisplayAsync` 메서드를 취소 하 고 종료 하기 전에 작업이 완료 될 때까지 기다립니다.

> [!NOTE]
> 이 코드는 `Main` 메서드가 종료 C# 될 때 새 8 "using 선언" 구문을 사용 하 여 스트림과 채널을 삭제 합니다. 사소한 변경 이지만 들여쓰기와 빈 줄을 줄이는 것이 좋습니다.

#### <a name="consume-the-stream"></a>스트림 사용

서버가 클라이언트에서 직접 메서드를 호출할 수 있도록 하는 WCF 사용 콜백 인터페이스입니다. gRPC 스트림은 다르게 작동 합니다. 클라이언트는 반환 된 스트림을 반복 하 고 `IEnumerable`을 반환 하는 로컬 메서드에서 반환 된 것 처럼 메시지를 처리 합니다.

`IAsyncStreamReader<T>` 형식은 `IEnumerator<T>`와 매우 유사 하 게 작동 합니다. 더 많은 데이터가 있는 경우 true를 반환 하는 `MoveNext` 메서드와 최신 값을 반환 하는 `Current` 속성이 있습니다. 유일한 차이점은 `MoveNext` 메서드가 `bool`아니라 `Task<bool>`를 반환 한다는 것입니다. `ReadAllAsync` 확장 메서드는 새 `await foreach` 구문과 함께 사용할 수 C# 있는 표준 8 `IAsyncEnumerable`의 스트림을 래핑합니다.

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
> 이 챕터의 끝에 있는 [클라이언트 라이브러리](client-libraries.md#iobservable) 섹션에서는 사후 프로그래밍 패턴을 사용 하는 개발자를 위해 확장 메서드 및 클래스를 추가 하 여 `IObservable<T>` `IAsyncStreamReader<T>` 래핑하는 방법에 대해 살펴봅니다.

또한 코드에서 <xref:System.Threading.CancellationToken>를 사용 하 여 루프를 중단 하기 때문에 발생 하는 <xref:System.OperationCanceledException> 뿐 아니라 네트워크 오류의 가능성으로 인해 여기에서 예외를 catch 해야 합니다. `RpcException` 형식에는 `StatusCode`를 포함 하 여 gRPC 런타임 오류에 대 한 유용한 정보가 많이 있습니다. 자세한 내용은 [4 장의 *오류 처리* ](error-handling.md)를 참조 하세요.

## <a name="bidirectional-streaming"></a>양방향 스트리밍

WCF 전이중 서비스는 양방향으로 비동기 실시간 메시징을 허용 합니다. 서버 스트리밍 예제에서 클라이언트는 요청을 시작한 다음 업데이트 스트림을 받습니다. 더 나은 버전의 서비스를 사용 하면 클라이언트가 새 구독을 중지 하 고 만들지 않고도 목록에서 주식을 추가 하 고 제거할 수 있습니다. 해당 기능은 [FullStockTicker 샘플 솔루션](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker)에 구현 되었습니다.

`IFullStockTickerService` 인터페이스는 다음과 같은 세 가지 메서드를 제공 합니다.

- `Subscribe`는 연결을 시작 합니다.
- `AddSymbol` 하 여 시청할 스톡 기호를 추가 합니다.
- `RemoveSymbol`는 조사 목록에서 기호를 제거 합니다.

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

콜백 인터페이스는 동일 하 게 유지 됩니다.

이제 메시지가 전달 되는 두 개의 데이터 스트림 (클라이언트에서 서버로, 다른 하나는 서버에서 클라이언트로)이 있으므로 gRPC에서이 패턴을 구현 하는 것은 간단 하지 않습니다. 여러 메서드를 사용 하 여 추가 및 제거 작업을 구현 하는 것은 불가능 하지만 [3 장](protobuf-any-oneof.md)에서 설명 하는 `Any` 형식 또는 `oneof` 키워드를 사용 하 여 단일 스트림에서 여러 유형의 메시지를 전달할 수 있습니다.

허용 되는 특정 형식 집합이 있는 경우 `oneof`는 것이 더 좋은 방법입니다. `AddSymbolRequest` 또는 `RemoveSymbolRequest`를 보유할 수 있는 `ActionMessage`을 사용 합니다.

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

`ActionMessage` 메시지의 스트림을 사용 하는 양방향 스트리밍 서비스를 선언 합니다.

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

이 서비스에 대 한 구현은 앞의 예제와 유사 합니다. 단, `Subscribe` 메서드의 첫 번째 매개 변수는 이제 `Add` 및 `Remove` 요청을 처리 하는 데 사용할 수 있는 `IAsyncStreamReader<ActionMessage>`입니다.

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
        // Handle any errors due to broken connection etc.
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

GRPC가 우리에 대해 생성 한 `ActionMessage` 클래스를 사용 하 여 `Add` 및 `Remove` 속성 중 하나만 설정할 수 있으며, `null` 되지 않는 메시지는 사용 되는 메시지 유형을 찾기 위한 올바른 방법 이지만 더 나은 방법이 있습니다. 또한 코드 생성은 다음과 같이 `ActionMessage` 클래스에 `enum ActionOneOfCase`를 만들었습니다.

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

`ActionMessage` 개체의 속성 `ActionCase` `switch` 문과 함께 사용 하 여 설정 된 필드를 확인할 수 있습니다.

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
> `switch` 문에 알 수 없는 `ActionOneOfCase` 값이 발견 되 면 경고를 기록 하는 `default` 사례가 있습니다. 이는 클라이언트가 더 많은 작업을 추가한 `.proto` 파일의 최신 버전을 사용 하 고 있음을 나타내는 데 유용 합니다. 이것은 `switch`를 사용 하 여 알려진 필드의 `null` 테스트 하는 것 보다 좋은 한 가지 이유입니다.

### <a name="use-the-fullstocktickerservice-from-a-client-application"></a>클라이언트 응용 프로그램에서 FullStockTickerService 사용

이 보다 복잡 한 클라이언트의 사용을 보여 주는 간단한 .NET Core 3.0 WPF 응용 프로그램이 있습니다. 전체 응용 프로그램은 [GitHub에서](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker)찾을 수 있습니다.

클라이언트는 종속성 주입에서 `FullStockTicker.FullStockTickerClient` 형식의 인스턴스를 가져오는 `MainWindowViewModel` 클래스에서 사용 됩니다.

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

이제 `client.Subscribe()` 메서드에서 반환 되는 개체는 gRPC 라이브러리 `AsyncDuplexStreamingCall<TRequest, TResponse>`형식의 인스턴스로, 서버에 요청을 보내기 위한 `RequestStream`를 제공 하 고 응답을 처리 하기 위한 `ResponseStream`를 제공 합니다.

요청 스트림은 일부 WPF `ICommand` 메서드에서 기호를 추가 및 제거 하는 데 사용 됩니다. 각 작업에 대해 `ActionMessage` 개체에 대 한 관련 필드를 설정 합니다.

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
> 메시지에 `oneof` 필드 값을 설정 하면 이전에 설정 된 모든 필드가 자동으로 지워집니다.

응답 스트림은 `async` 메서드에서 처리 되며, 반환 되는 `Task`은 창이 닫힐 때 삭제 됩니다.

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

### <a name="client-clean-up"></a>클라이언트 정리

창이 닫히고 `MainWindowViewModel` 삭제 된 경우 (`MainWindow`의 `Closed` 이벤트) `AsyncDuplexStreamingCall` 개체를 적절 하 게 삭제 하는 것이 좋습니다. 특히 `RequestStream`의 `CompleteAsync` 메서드를 호출 하 여 서버에서 스트림을 정상적으로 닫아야 합니다. 다음 예제에서는 샘플 뷰 모델의 `DisposeAsync` 메서드를 보여 줍니다.

```csharp
public ValueTask DisposeAsync()
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

요청 스트림을 닫으면 서버에서 적절 한 시간 내에 자체 리소스를 삭제할 수 있습니다. 이렇게 하면 서비스의 효율성 및 확장성을 향상 시키고 예외를 방지할 수 있습니다.

>[!div class="step-by-step"]
>[이전](migrate-request-reply.md)
>[다음](streaming-versus-repeated.md)
