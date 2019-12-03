---
title: GRPC 클라이언트 라이브러리 만들기-WCF 개발자를 위한 gRPC
description: GRPC 서비스용 공유 클라이언트 라이브러리/패키지에 대 한 설명입니다.
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711452"
---
# <a name="create-grpc-client-libraries"></a>GRPC 클라이언트 라이브러리 만들기

GRPC 응용 프로그램에 대 한 클라이언트 라이브러리를 배포할 필요는 없습니다. 조직 내에서 `.proto` 파일의 공유 라이브러리를 만들 수 있으며, 다른 팀은 해당 파일을 사용 하 여 자체 프로젝트에서 클라이언트 코드를 생성할 수 있습니다. 그러나 개인 NuGet 리포지토리가 있고 많은 다른 팀이 .NET Core를 사용 하는 경우 서비스 프로젝트의 일부로 클라이언트 NuGet 패키지를 만들고 게시할 수 있습니다. 이는 서비스를 공유 하 고 승격 하는 좋은 방법일 수 있습니다.

클라이언트 라이브러리를 배포 하는 경우의 한 가지 이점은 생성 된 gRPC 및 Protobuf 클래스를 유용한 "편리한" 메서드와 속성을 사용 하 여 개선할 수 있다는 것입니다. 서버에서와 같이 클라이언트 코드에서 모든 클래스는 `partial`로 선언 되므로 생성 된 코드를 편집 하지 않고 확장할 수 있습니다. 즉, 생성자, 메서드 및 계산 된 속성을 기본 형식에 쉽게 추가할 수 있습니다.

> [!CAUTION]
> 사용자 지정 코드를 사용 하 여 필수 기능을 제공 해서는 안 됩니다. 공유 라이브러리를 사용 하는 .NET 팀에 게 중요 한 기능을 제한 하지 않고 Python 또는 Java와 같은 다른 언어나 플랫폼을 사용 하는 팀에 제공 하지 않으려고 합니다.

가능한 한 많은 팀에서 gRPC 서비스에 액세스할 수 있는지 확인 합니다. 이 작업을 수행 하는 가장 좋은 방법은 개발자가 자체 클라이언트를 생성할 수 있도록 `.proto` 파일을 공유 하는 것입니다. 이는 여러 팀에서 다른 프로그래밍 언어 및 프레임 워크를 자주 사용 하거나 API를 외부에서 액세스할 수 있는 다중 플랫폼 환경에서 특히 그렇습니다.

## <a name="useful-extensions"></a>유용한 확장

.NET에서는 개체 스트림 처리를 위한 두 가지 일반적으로 사용 되는 인터페이스 <xref:System.Collections.Generic.IEnumerable%601> 및 <xref:System.IObservable%601>있습니다. .NET Core 3.0 및 C# 8.0부터 스트림을 비동기적으로 처리 하기 위한 <xref:System.Collections.Generic.IAsyncEnumerable%601> 인터페이스와 인터페이스 사용을 위한 `await foreach` 구문이 있습니다. 이 섹션에서는 이러한 인터페이스를 gRPC 스트림에 적용 하기 위한 재사용 가능한 코드를 제공 합니다.

.NET Core gRPC 클라이언트 라이브러리를 사용 하는 경우 `IAsyncEnumerable<T>` 인터페이스를 만드는 `IAsyncStreamReader<T>`에 대 한 `ReadAllAsync` 확장 메서드가 있습니다. 사후 프로그래밍을 사용 하는 개발자를 위해 `IObservable<T>` 인터페이스를 만드는 동일한 확장 메서드는 다음 섹션의 예제 처럼 보일 수 있습니다.

### <a name="iobservable"></a>IObservable

`IObservable<T>` 인터페이스는 `IEnumerable<T>`의 "사후" 역입니다. 스트림에서 항목을 풀링 하는 대신 반응 방식을 사용 하면 스트림이 구독자에 항목을 푸시할 수 있습니다. 이는 gRPC 스트림과 매우 비슷하며 `IAsyncStreamReader<T>` 인터페이스를 중심으로 `IObservable<T>` 인터페이스를 쉽게 래핑할 수 있습니다.

이 코드는 관찰 가능 개체 작업을 기본적으로 지원 하지 C# 않으므로 `IAsyncEnumerable<T>` 코드 보다 깁니다. 구현 클래스를 수동으로 만들어야 합니다. 그러나 제네릭 클래스 이지만 단일 구현은 모든 형식에서 작동 합니다.

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public class GrpcStreamObservable<T> : IObservable<T>
    {
        private readonly IAsyncStreamReader<T> _reader;
        private readonly CancellationToken _token;
        private int _used;

        public Observable(IAsyncStreamReader<T> reader, CancellationToken token = default)
        {
            _reader = reader;
            _token = token;
            _used = 0;
        }

        public IDisposable Subscribe(IObserver<T> observer) =>
            Interlocked.Exchange(ref _used, 1) == 0
                ? new GrpcStreamSubscription(_reader, observer, _token)
                : throw new InvalidOperationException("Subscribe can only be called once.");

    }
}
```

> [!IMPORTANT]
> 이러한 관찰 가능한 구현을 통해 여러 구독자가 스트림에서 읽으려고 하면 비정상 상황이 발생 하므로 `Subscribe` 메서드를 한 번만 호출할 수 있습니다. 관찰 가능 개체에는이 구현과 함께 사용할 수 있는 버퍼링 및 반복 가능한 공유를 사용할 수 있도록 하는 `Replay`와 같은 연산자가 [있습니다.](https://www.nuget.org/packages/System.Reactive.Linq)

`GrpcStreamSubscription` 클래스는 `IAsyncStreamReader`열거를 처리 합니다.

```csharp
public class GrpcStreamSubscription : IDisposable
{
    private readonly Task _task;
    private readonly CancellationTokenSource _tokenSource;
    private bool _completed;

    public Subscription(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        Debug.Assert(reader != null);
        Debug.Assert(observer != null);
        _tokenSource = new CancellationTokenSource();
        token.Register(_tokenSource.Cancel);
        _task = Run(reader, observer, _tokenSource.Token);
    }

    private async Task Run(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        while (!token.IsCancellationRequested)
        {
            try
            {
                if (!await reader.MoveNext(token)) break;
            }
            catch (RpcException e) when (e.StatusCode == Grpc.Core.StatusCode.NotFound)
            {
                break;
            }
            catch (OperationCanceledException)
            {
                break;
            }
            catch (Exception e)
            {
                observer.OnError(e);
                _completed = true;
                return;
            }

            observer.OnNext(reader.Current);
        }

        _completed = true;
        observer.OnCompleted();
    }

    public void Dispose()
    {
        if (!_completed && !_tokenSource.IsCancellationRequested)
        {
            _tokenSource.Cancel();
        }

        _tokenSource.Dispose();
        _task.Dispose();
    }

}
```

이제 필요한 모든 항목은 스트림 판독기에서 관찰 가능 개체를 만드는 간단한 확장 메서드입니다.

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public static class AsyncStreamReaderObservableExtensions
    {
        public static IObservable<T> AsObservable<T>(this IAsyncStreamReader<T> reader) =>
            new GrpcStreamObservable<T>(reader);
    }
}
```

## <a name="summary"></a>요약

`IAsyncEnumerable` 및 `IObservable` 모델은 잘 지원 되며 .NET의 비동기 데이터 스트림을 처리 하는 잘 문서화 된 방법입니다. gRPC 스트림은 .NET Core와의 긴밀 한 통합 및 사후 및 비동기 프로그래밍 스타일을 제공 하 여 두 패러다임에 잘 매핑됩니다.

>[!div class="step-by-step"]
>[이전](streaming-versus-repeated.md)
>[다음](security.md)
