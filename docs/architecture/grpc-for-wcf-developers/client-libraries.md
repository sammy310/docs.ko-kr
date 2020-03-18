---
title: WCF 개발자를 위한 gRPC 클라이언트 라이브러리 만들기
description: gRPC 서비스에 대한 공유 클라이언트 라이브러리/패키지에 대한 토론.
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401774"
---
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="dc55c-103">gRPC 클라이언트 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="dc55c-103">Create gRPC client libraries</span></span>

<span data-ttu-id="dc55c-104">gRPC 응용 프로그램에 대 한 클라이언트 라이브러리를 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="dc55c-105">조직 내에서 파일의 `.proto` 공유 라이브러리를 만들 수 있으며 다른 팀에서는 이러한 파일을 사용하여 자체 프로젝트에서 클라이언트 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="dc55c-106">그러나 개인 NuGet 리포지토리가 있고 다른 많은 팀이 .NET Core를 사용하는 경우 서비스 프로젝트의 일부로 클라이언트 NuGet 패키지를 만들고 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-106">But if you have a private NuGet repository and many other teams are using .NET Core, you can create and publish client NuGet packages as part of your service project.</span></span> <span data-ttu-id="dc55c-107">이는 서비스를 공유하고 홍보하는 좋은 방법이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-107">This can be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="dc55c-108">클라이언트 라이브러리를 배포하는 한 가지 장점은 유용한 "편의성" 메서드 및 속성을 사용하여 생성된 gRPC 및 Protobuf 클래스를 향상시킬 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-108">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="dc55c-109">클라이언트 코드에서 서버와 마찬가지로 모든 클래스가 `partial`로 선언되므로 생성된 코드를 편집하지 않고 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-109">In the client code, as in the server, all the classes are declared as `partial`, so you can extend them without editing the generated code.</span></span> <span data-ttu-id="dc55c-110">즉, 기본 형식에 생성자, 메서드 및 계산된 속성을 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-110">This means it's easy to add constructors, methods, and calculated properties to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="dc55c-111">필수 기능을 제공하기 위해 사용자 지정 코드를 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-111">You shouldn't use custom code to provide essential functionality.</span></span> <span data-ttu-id="dc55c-112">이 필수 기능은 공유 라이브러리를 사용하는 .NET 팀으로 제한하고 Python 또는 Java와 같은 다른 언어 나 플랫폼을 사용하는 팀에는 제공하지 않으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-112">You don't want to restrict that essential functionality to .NET teams that use the shared library, and not provide it to teams that use other languages or platforms, such as Python or Java.</span></span>

<span data-ttu-id="dc55c-113">가능한 한 많은 팀이 gRPC 서비스에 액세스할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-113">Ensure that as many teams as possible can access your gRPC service.</span></span> <span data-ttu-id="dc55c-114">이 작업을 수행하는 가장 좋은 `.proto` 방법은 개발자가 자신의 클라이언트를 생성할 수 있도록 파일을 공유하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-114">The best way to do this is to share `.proto` files so developers can generate their own clients.</span></span> <span data-ttu-id="dc55c-115">이는 서로 다른 팀이 서로 다른 프로그래밍 언어와 프레임워크를 자주 사용하거나 API에 외부에서 액세스할 수 있는 다중 플랫폼 환경에서 특히 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-115">This is particularly true in a multi-platform environment, where different teams frequently use different programming languages and frameworks, or where your API is externally accessible.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="dc55c-116">유용한 확장</span><span class="sxs-lookup"><span data-stu-id="dc55c-116">Useful extensions</span></span>

<span data-ttu-id="dc55c-117">.NET에는 개체 스트림을 처리하기 위해 일반적으로 사용되는 두 <xref:System.Collections.Generic.IEnumerable%601> <xref:System.IObservable%601>가지 인터페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-117">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="dc55c-118">.NET Core 3.0 및 C# 8.0부터 <xref:System.Collections.Generic.IAsyncEnumerable%601> 는 비동기적으로 스트림을 처리하는 인터페이스와 `await foreach` 인터페이스를 사용하기 위한 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-118">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="dc55c-119">이 섹션에서는 gRPC 스트림에 이러한 인터페이스를 적용하기 위한 재사용 가능한 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-119">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="dc55c-120">.NET Core gRPC 클라이언트 라이브러리를 사용하면 `ReadAllAsync` 인터페이스를 `IAsyncStreamReader<T>` 만드는 `IAsyncEnumerable<T>` 확장 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-120">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>` interface.</span></span> <span data-ttu-id="dc55c-121">반응형 프로그래밍을 사용하는 개발자의 경우 `IObservable<T>` 인터페이스를 만드는 동등한 확장 메서드가 다음 섹션의 예제와 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-121">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` interface might look like the example in the following section.</span></span>

### <a name="iobservable"></a><span data-ttu-id="dc55c-122">아이오서볼(IOb)</span><span class="sxs-lookup"><span data-stu-id="dc55c-122">IObservable</span></span>

<span data-ttu-id="dc55c-123">인터페이스는 `IObservable<T>` 의 "반응성" 역입니다. `IEnumerable<T>`</span><span class="sxs-lookup"><span data-stu-id="dc55c-123">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="dc55c-124">스트림에서 항목을 가져오는 대신 반응형 접근 방식을 사용하면 스트림에서 구독자에게 항목을 푸시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-124">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="dc55c-125">이는 gRPC 스트림과 매우 유사하며 `IObservable<T>` `IAsyncStreamReader<T>` 인터페이스를 중심으로 인터페이스를 래핑하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-125">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` interface around an `IAsyncStreamReader<T>` interface.</span></span>

<span data-ttu-id="dc55c-126">C#에는 관찰 `IAsyncEnumerable<T>` 가능한 작업에 대한 기본 제공 지원이 없기 때문에 이 코드는 코드보다 깁니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-126">This code is longer than the `IAsyncEnumerable<T>` code, because C# doesn't have built-in support for working with observables.</span></span> <span data-ttu-id="dc55c-127">구현 클래스를 수동으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-127">You have to create the implementation class manually.</span></span> <span data-ttu-id="dc55c-128">하지만 일반 클래스이므로 단일 구현이 모든 형식에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-128">It's a generic class, though, so a single implementation works across all types.</span></span>

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
> <span data-ttu-id="dc55c-129">이 관찰 가능한 구현을 `Subscribe` 사용하면 여러 구독자가 스트림에서 읽으려고 하면 혼란이 발생할 수 있으므로 메서드를 한 번만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-129">This observable implementation allows the `Subscribe` method to be called only once, because having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="dc55c-130">이 구현과 함께 `Replay` 사용할 수 있는 관찰 가능한 버퍼링 및 반복 가능한 공유를 가능하게 하는 [System.Reactive.Linq와](https://www.nuget.org/packages/System.Reactive.Linq)같은 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-130">There are operators, such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="dc55c-131">클래스는 `GrpcStreamSubscription` 다음의 열거를 처리합니다. `IAsyncStreamReader`</span><span class="sxs-lookup"><span data-stu-id="dc55c-131">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`:</span></span>

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

<span data-ttu-id="dc55c-132">이제 필요한 것은 스트림 리더기에서 관찰 가능한 을 만드는 간단한 확장 메서드뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-132">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="dc55c-133">요약</span><span class="sxs-lookup"><span data-stu-id="dc55c-133">Summary</span></span>

<span data-ttu-id="dc55c-134">`IAsyncEnumerable` 모델과 `IObservable` 모델은 .NET에서 비동기 데이터 스트림을 처리하는 잘 지원되고 잘 문서화된 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-134">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="dc55c-135">gRPC 스트림은 두 패러다임에 잘 매핑되어 .NET Core와 긴밀한 통합을 제공하며, 반응성 및 비동기 프로그래밍 스타일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc55c-135">gRPC streams map well to both paradigms, offering close integration with .NET Core, and reactive and asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dc55c-136">[이전](streaming-versus-repeated.md)
>[다음](security.md)</span><span class="sxs-lookup"><span data-stu-id="dc55c-136">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
