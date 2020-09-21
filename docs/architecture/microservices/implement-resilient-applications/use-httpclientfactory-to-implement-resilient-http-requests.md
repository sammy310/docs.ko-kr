---
title: IHttpClientFactory를 사용하여 복원력 있는 HTTP 요청 구현
description: 애플리케이션에서 사용하기 쉽도록 .NET Core 2.1부터 제공되는 IHttpClientFactory를 사용하여 `HttpClient` 인스턴스를 만드는 방법을 알아봅니다.
ms.date: 08/31/2020
ms.openlocfilehash: c54965a9bbb700cfb1f14150773c2df45d109c39
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90678818"
---
# <a name="use-ihttpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="c5677-103">IHttpClientFactory를 사용하여 복원력 있는 HTTP 요청 구현</span><span class="sxs-lookup"><span data-stu-id="c5677-103">Use IHttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="c5677-104"><xref:System.Net.Http.IHttpClientFactory>는 애플리케이션에서 사용할 <xref:System.Net.Http.HttpClient> 인스턴스를 만드는 독창적인 팩터리(.NET Core 2.1부터 사용할 수 있음)인 `DefaultHttpClientFactory`에 의해 구현되는 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-104"><xref:System.Net.Http.IHttpClientFactory> is a contract implemented by `DefaultHttpClientFactory`, an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="c5677-105">.NET Core에서 사용할 수 있는 원래의 HttpClient 클래스 문제</span><span class="sxs-lookup"><span data-stu-id="c5677-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="c5677-106">잘 알려진 원래의 <xref:System.Net.Http.HttpClient> 클래스는 쉽게 사용할 수 있지만, 많은 개발자가 제대로 사용하지 못하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-106">The original and well-known <xref:System.Net.Http.HttpClient> class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span>

<span data-ttu-id="c5677-107">이 클래스는 `IDisposable`을 구현하지만, `using` 문 내에서 해당 클래스를 선언하고 인스턴스화하는 것은 바람직하지 않습니다. `HttpClient` 개체가 삭제될 때 기본 소켓이 즉시 해제되지 않아 ‘소켓 소모’ 문제가 발생할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-107">Though this class implements `IDisposable`, declaring and instantiating it within a `using` statement is not preferred because when the `HttpClient` object gets disposed of, the underlying socket is not immediately released, which can lead to a _socket exhaustion_ problem.</span></span> <span data-ttu-id="c5677-108">이 문제에 대한 자세한 내용은 블로그 게시물 [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/)(잘못 사용하고 있는 HttpClient로 인해 불안정해지고 있는 소프트웨어)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5677-108">For more information about this issue, see the blog post [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span></span>

<span data-ttu-id="c5677-109">따라서 `HttpClient`는 한 번 인스턴스화되어 애플리케이션의 수명 동안 다시 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="c5677-110">모든 요청에 대해 `HttpClient` 클래스를 인스턴스화하면 과도한 부하에서 사용할 수 있는 소켓 수가 소진됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="c5677-111">이 문제로 인해 `SocketException` 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="c5677-112">이 문제를 해결하는 데 가능한 방법은 [HttpClient 사용에 관한 Microsoft 문서](../../../csharp/tutorials/console-webapiclient.md)에서 설명한 대로 `HttpClient` 개체를 singleton 또는 정적으로 만드는 것을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](../../../csharp/tutorials/console-webapiclient.md).</span></span> <span data-ttu-id="c5677-113">이 방법은 단기 콘솔 앱 또는 하루에 몇 번 실행되는 유사한 앱에 좋은 해결책일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-113">This can be a good solution for short-lived console apps or similar, that run a few times a day.</span></span>

<span data-ttu-id="c5677-114">개발자가 겪는 또 다른 문제는 장기 실행 프로세스에서 `HttpClient`의 공유 인스턴스를 사용하는 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-114">Another issue that developers run into is when using a shared instance of `HttpClient` in long-running processes.</span></span> <span data-ttu-id="c5677-115">HttpClient가 singleton 또는 정적 개체로 인스턴스화되는 상황에서 이 [문제](https://github.com/dotnet/runtime/issues/18348)에서 dotnet/런타임 GitHub 리포지토리에 대해 설명된 대로 DNS 변경 사항을 처리하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-115">In a situation where the HttpClient is instantiated as a singleton or a static object, it fails to handle the DNS changes as described in this [issue](https://github.com/dotnet/runtime/issues/18348) of the dotnet/runtime GitHub repository.</span></span>

<span data-ttu-id="c5677-116">그러나 문제는 `HttpClient` 자체가 아니라 [HttpClient의 기본 생성자](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor)에 있습니다. 이 생성자는 위에서 언급한 ‘소켓 소모’ 및 DNS 변경 문제가 있는 새로운 구체적인 <xref:System.Net.Http.HttpMessageHandler> 인스턴스를 만들기 때문입니다. </span><span class="sxs-lookup"><span data-stu-id="c5677-116">However, the issue isn't really with `HttpClient` per se, but with the [default constructor for HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), because it creates a new concrete instance of <xref:System.Net.Http.HttpMessageHandler>, which is the one that has *sockets exhaustion* and DNS changes issues mentioned above.</span></span>

<span data-ttu-id="c5677-117">위에서 언급한 문제를 해결하고 `HttpClient` 인스턴스를 관리할 수 있게 만들기 위해 .NET Core 2.1에서는 DI(종속성 주입)를 통해 앱에서 `HttpClient` 인스턴스를 구성하고 만드는 데 사용할 수 있는 <xref:System.Net.Http.IHttpClientFactory> 인터페이스를 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-117">To address the issues mentioned above and to make `HttpClient` instances manageable, .NET Core 2.1 introduced the <xref:System.Net.Http.IHttpClientFactory> interface which can be used to configure and create `HttpClient` instances in an app through Dependency Injection (DI).</span></span> <span data-ttu-id="c5677-118">또한 Polly 기반 미들웨어에 대한 확장을 제공하여 HttpClient에서의 처리기 위임을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-118">It also provides extensions for Polly-based middleware to take advantage of delegating handlers in HttpClient.</span></span>

<span data-ttu-id="c5677-119">[Polly](http://www.thepollyproject.org/)는 미리 정의된 정책을 사용하여 개발자가 흐름 및 스레드로부터 안전한 방식으로 애플리케이션에 복원력을 추가하는 데 도움이 되는 일시적인 오류 처리 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-119">[Polly](http://www.thepollyproject.org/) is a transient-fault-handling library that helps developers add resiliency to their applications, by using some pre-defined policies in a fluent and thread-safe manner.</span></span>

## <a name="benefits-of-using-ihttpclientfactory"></a><span data-ttu-id="c5677-120">IHttpClientFactory 사용의 이점</span><span class="sxs-lookup"><span data-stu-id="c5677-120">Benefits of using IHttpClientFactory</span></span>

<span data-ttu-id="c5677-121"><xref:System.Net.Http.IHttpMessageHandlerFactory>도 구현하는 <xref:System.Net.Http.IHttpClientFactory>의 현재 구현은 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-121">The current implementation of <xref:System.Net.Http.IHttpClientFactory>, that also implements <xref:System.Net.Http.IHttpMessageHandlerFactory>, offers the following benefits:</span></span>

- <span data-ttu-id="c5677-122">논리적 `HttpClient` 개체를 명명하고 구성하기 위한 중앙 위치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-122">Provides a central location for naming and configuring logical `HttpClient` objects.</span></span> <span data-ttu-id="c5677-123">예를 들어 특정 마이크로 서비스에 액세스하도록 미리 구성된 클라이언트(서비스 에이전트)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-123">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="c5677-124">`HttpClient`에서 처리기를 위임하고 Polly 기반 미들웨어를 구현하여 나가는 미들웨어에 대한 개념을 체계화하여 Polly의 복원력 정책을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-124">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly's policies for resiliency.</span></span>
- <span data-ttu-id="c5677-125">`HttpClient`에는 나가는 HTTP 요청을 위해 함께 연결될 수 있는 처리기 위임이라는 개념이 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-125">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="c5677-126">HTTP 클라이언트를 팩터리에 등록하고, Polly 처리기를 사용하여 Polly 정책을 다시 시도, 회로 차단기 등에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-126">You can register HTTP clients into the factory and you can use a Polly handler to use Polly policies for Retry, CircuitBreakers, and so on.</span></span>
- <span data-ttu-id="c5677-127"><xref:System.Net.Http.HttpMessageHandler>의 수명을 관리하여 `HttpClient` 수명을 직접 관리할 때 발생할 수 있는 언급된 문제를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-127">Manage the lifetime of <xref:System.Net.Http.HttpMessageHandler> to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span>

> [!TIP]
> <span data-ttu-id="c5677-128">연결된 `HttpMessageHandler`가 팩터리에서 관리되기 때문에, DI에 의해 삽입되는 `HttpClient` 인스턴스는 안전하게 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-128">The `HttpClient` instances injected by DI, can be disposed of safely, because the associated `HttpMessageHandler` is managed by the factory.</span></span> <span data-ttu-id="c5677-129">사실상 삽입된 `HttpClient` 인스턴스는 DI 측면에서 ‘범위가 제한’됩니다. </span><span class="sxs-lookup"><span data-stu-id="c5677-129">As a matter of fact, injected `HttpClient` instances are *Scoped* from a DI perspective.</span></span>

> [!NOTE]
> <span data-ttu-id="c5677-130">`IHttpClientFactory`의 구현(`DefaultHttpClientFactory`)은 `Microsoft.Extensions.DependencyInjection` NuGet 패키지의 DI 구현과 긴밀한 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-130">The implementation of `IHttpClientFactory` (`DefaultHttpClientFactory`) is tightly tied to the DI implementation in the `Microsoft.Extensions.DependencyInjection` NuGet package.</span></span> <span data-ttu-id="c5677-131">다른 DI 컨테이너를 사용하는 방법에 대한 자세한 내용은 이 [GitHub 토론](https://github.com/dotnet/extensions/issues/1345)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5677-131">For more information about using other DI containers, see this [GitHub discussion](https://github.com/dotnet/extensions/issues/1345).</span></span>

## <a name="multiple-ways-to-use-ihttpclientfactory"></a><span data-ttu-id="c5677-132">IHttpClientFactory를 사용하는 여러 가지 방법</span><span class="sxs-lookup"><span data-stu-id="c5677-132">Multiple ways to use IHttpClientFactory</span></span>

<span data-ttu-id="c5677-133">애플리케이션에서 `IHttpClientFactory`를 사용할 수 있는 몇 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-133">There are several ways that you can use `IHttpClientFactory` in your application:</span></span>

- <span data-ttu-id="c5677-134">기본적인 사용 방법</span><span class="sxs-lookup"><span data-stu-id="c5677-134">Basic usage</span></span>
- <span data-ttu-id="c5677-135">명명된 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="c5677-135">Use Named Clients</span></span>
- <span data-ttu-id="c5677-136">형식화된 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="c5677-136">Use Typed Clients</span></span>
- <span data-ttu-id="c5677-137">생성된 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="c5677-137">Use Generated Clients</span></span>

<span data-ttu-id="c5677-138">간단히 하기 위해 이 지침에서는 `IHttpClientFactory`를 사용하는 가장 구조적인 방법, 즉 형식화된 클라이언트(서비스 에이전트 패턴)를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-138">For the sake of brevity, this guidance shows the most structured way to use `IHttpClientFactory`, which is to use Typed Clients (Service Agent pattern).</span></span> <span data-ttu-id="c5677-139">그러나 모든 옵션이 현재 [`IHttpClientFactory` 사용에 대한 이 문서](/aspnet/core/fundamentals/http-requests#consumption-patterns)에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-139">However, all options are documented and are currently listed in this [article covering the `IHttpClientFactory` usage](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span></span>

## <a name="how-to-use-typed-clients-with-ihttpclientfactory"></a><span data-ttu-id="c5677-140">형식화된 클라이언트를 IHttpClientFactory에 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="c5677-140">How to use Typed Clients with IHttpClientFactory</span></span>

<span data-ttu-id="c5677-141">그렇다면 “형식화된 클라이언트”란 무엇일까요?</span><span class="sxs-lookup"><span data-stu-id="c5677-141">So, what's a "Typed Client"?</span></span> <span data-ttu-id="c5677-142">일부 특정 용도를 위해 사전 구성된 `HttpClient`입니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-142">It's just an `HttpClient` that's pre-configured for some specific use.</span></span> <span data-ttu-id="c5677-143">이 구성에는 기본 서버, HTTP 헤더 또는 시간 제한과 같은 특정 값이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-143">This configuration can include specific values such as the base server, HTTP headers or time outs.</span></span>

<span data-ttu-id="c5677-144">다음 다이어그램은 `IHttpClientFactory`와 함께 형식화된 클라이언트를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-144">The following diagram shows how Typed Clients are used with `IHttpClientFactory`:</span></span>

![형식화된 클라이언트를 IHttpClientFactory에 사용하는 방법을 보여 주는 다이어그램.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

<span data-ttu-id="c5677-146">**그림 8-4**.</span><span class="sxs-lookup"><span data-stu-id="c5677-146">**Figure 8-4**.</span></span> <span data-ttu-id="c5677-147">형식화된 클라이언트 클래스에 `IHttpClientFactory` 사용</span><span class="sxs-lookup"><span data-stu-id="c5677-147">Using `IHttpClientFactory` with Typed Client classes.</span></span>

<span data-ttu-id="c5677-148">위 이미지의 `ClientService`(컨트롤러 또는 클라이언트 코드에서 사용됨)는 등록된 `IHttpClientFactory`에서 만든 `HttpClient`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-148">In the above image, a `ClientService` (used by a controller or client code) uses an `HttpClient` created by the registered `IHttpClientFactory`.</span></span> <span data-ttu-id="c5677-149">이 팩터리는 풀의 `HttpMessageHandler`를 `HttpClient`에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-149">This factory assigns an `HttpMessageHandler` from a pool to the `HttpClient`.</span></span> <span data-ttu-id="c5677-150">확장 메서드 <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A>를 사용하여 DI 컨테이너에 `IHttpClientFactory`를 등록할 때 Polly의 정책을 사용하여 `HttpClient`를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-150">The `HttpClient` can be configured with Polly's policies when registering the `IHttpClientFactory` in the DI container with the extension method <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A>.</span></span>

<span data-ttu-id="c5677-151">위의 구조를 구성하려면 <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>용 <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A> 확장 메서드를 포함하는 `Microsoft.Extensions.Http` NuGet 패키지를 설치하여 애플리케이션에서 <xref:System.Net.Http.IHttpClientFactory>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-151">To configure the above structure, add <xref:System.Net.Http.IHttpClientFactory> in your application by installing the `Microsoft.Extensions.Http` NuGet package that includes the <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A> extension method for <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="c5677-152">이 확장 메서드는 인터페이스 `IHttpClientFactory`에 대한 singleton으로 사용할 내부 `DefaultHttpClientFactory` 클래스를 등록하고</span><span class="sxs-lookup"><span data-stu-id="c5677-152">This extension method registers the internal `DefaultHttpClientFactory` class to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="c5677-153"><xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder>에 대한 일시적인 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-153">It defines a transient configuration for the <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder>.</span></span> <span data-ttu-id="c5677-154">풀에서 가져온 이 메시지 처리기(<xref:System.Net.Http.HttpMessageHandler> 개체)는 팩터리에서 반환된 `HttpClient`에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-154">This message handler (<xref:System.Net.Http.HttpMessageHandler> object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="c5677-155">다음 코드에서는 `AddHttpClient()`를 사용하여 `HttpClient`를 사용해야 하는 형식화된 클라이언트(서비스 에이전트)를 등록하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-155">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="c5677-156">이전 코드에 표시된 대로 클라이언트 서비스를 등록하면 `DefaultClientFactory`에서 각 서비스에 대한 표준 `HttpClient`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-156">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create a standard `HttpClient` for each service.</span></span>

<span data-ttu-id="c5677-157">또한 다음 코드와 같이 등록에 예를 들어 기준 주소를 구성하고 일부 복원력 정책을 추가하기 위한 인스턴스 관련 구성을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-157">You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:</span></span>

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="c5677-158">예를 들어 다음 코드에서는 위의 정책 중 하나를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-158">Just for the example sake, you can see one of the above policies in the next code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

<span data-ttu-id="c5677-159">[다음 문서](implement-http-call-retries-exponential-backoff-polly.md)에서 Polly 사용에 대한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-159">You can find more details about using Polly in the [Next article](implement-http-call-retries-exponential-backoff-polly.md).</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="c5677-160">HttpClient 수명</span><span class="sxs-lookup"><span data-stu-id="c5677-160">HttpClient lifetimes</span></span>

<span data-ttu-id="c5677-161">`IHttpClientFactory`에서 `HttpClient` 개체를 가져올 때마다 새 인스턴스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-161">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="c5677-162">그러나 `HttpMessageHandler`의 수명이 만료되지 않은 한, 각 `HttpClient`는 `IHttpClientFactory`에 의해 풀링되어 다시 사용되는 `HttpMessageHandler`를 사용하여 리소스 사용량을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-162">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="c5677-163">각 처리기가 일반적으로 자체 기본 HTTP 연결을 관리하고 필요 이상으로 처리기를 만드는 것은 연결 지연을 발생시킬 수 있으므로 처리기의 풀링이 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-163">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="c5677-164">또한 일부 처리기는 무한정으로 연결을 열어 놓아 처리기가 DNS 변경에 대응하는 것을 막을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-164">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="c5677-165">풀의 `HttpMessageHandler` 개체에는 수명이 있으며, 이 수명은 풀의 `HttpMessageHandler` 인스턴스를 다시 사용할 수 있는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-165">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="c5677-166">기본값은 2분이지만, 형식화된 클라이언트별로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-166">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="c5677-167">재정의하려면 다음 코드와 같이 클라이언트를 만들 때 반환되는 <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder>에서 `SetHandlerLifetime()`을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-167">To override it, call `SetHandlerLifetime()` on the <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder> that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

<span data-ttu-id="c5677-168">클라이언트마다 고유하게 구성된 처리기 수명 값이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-168">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="c5677-169">처리기 만료를 사용하지 않도록 설정하려면 수명을 `InfiniteTimeSpan`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-169">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="c5677-170">삽입되고 구성된 HttpClient를 사용하는 형식화된 클라이언트 클래스 구현</span><span class="sxs-lookup"><span data-stu-id="c5677-170">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="c5677-171">이전 단계와 같이 샘플 코드의 클래스(예: 'BasketService', 'CatalogService', 'OrderingService' 등)와 같은 형식화된 클라이언트 클래스를 정의해야 합니다. 형식화된 클라이언트는 생성자를 통해 삽입된 `HttpClient` 개체를 수락하고 이 개체를 사용하여 일부 원격 HTTP 서비스를 호출하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-171">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like 'BasketService', 'CatalogService', 'OrderingService', etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="c5677-172">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="c5677-172">For example:</span></span>

```csharp
public class CatalogService : ICatalogService
{
    private readonly HttpClient _httpClient;
    private readonly string _remoteServiceBaseUrl;

    public CatalogService(HttpClient httpClient)
    {
        _httpClient = httpClient;
    }

    public async Task<Catalog> GetCatalogItems(int page, int take,
                                               int? brand, int? type)
    {
        var uri = API.Catalog.GetAllCatalogItems(_remoteServiceBaseUrl,
                                                 page, take, brand, type);

        var responseString = await _httpClient.GetStringAsync(uri);

        var catalog = JsonConvert.DeserializeObject<Catalog>(responseString);
        return catalog;
    }
}
```

<span data-ttu-id="c5677-173">형식화된 클라이언트(예제에서는 `CatalogService`)는 DI(종속성 주입)를 통해 활성화됩니다. 즉, `HttpClient` 외에도 생성자에 등록된 모든 서비스를 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-173">The Typed Client (`CatalogService` in the example) is activated by DI (Dependency Injection), that means it can accept any registered service in its constructor, in addition to `HttpClient`.</span></span>

<span data-ttu-id="c5677-174">형식화된 클라이언트는 사실상 임시 개체입니다. 즉, 새 인스턴스가 필요할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-174">A Typed Client is effectively a transient object, that means a new instance is created each time one is needed.</span></span> <span data-ttu-id="c5677-175">생성될 때마다 새 `HttpClient` 인스턴스를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-175">It receives a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="c5677-176">그러나 풀의 `HttpMessageHandler` 개체는 여러 `HttpClient` 인스턴스에서 재사용되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-176">However, the `HttpMessageHandler` objects in the pool are the objects that are reused by multiple `HttpClient` instances.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="c5677-177">형식화된 클라이언트 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="c5677-177">Use your Typed Client classes</span></span>

<span data-ttu-id="c5677-178">마지막으로, 형식화된 클래스를 구현한 후에는 `AddHttpClient()`에 등록하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-178">Finally, once you have your typed classes implemented, you can have them registered and configured with `AddHttpClient()`.</span></span> <span data-ttu-id="c5677-179">그러면 DI를 통해 서비스를 삽입한 모든 곳에서 해당 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-179">After that you can use them wherever have services injected by DI.</span></span> <span data-ttu-id="c5677-180">예를 들어 eShopOnContainers의 다음 코드와 같이 MVC 웹 앱 컨트롤러 또는 Razor 페이지 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-180">For example, in a Razor page code or controller of an MVC web app, like in the following code from eShopOnContainers:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.WebMVC.Controllers
{
    public class CatalogController : Controller
    {
        private ICatalogService _catalogSvc;

        public CatalogController(ICatalogService catalogSvc) =>
                                                           _catalogSvc = catalogSvc;

        public async Task<IActionResult> Index(int? BrandFilterApplied,
                                               int? TypesFilterApplied,
                                               int? page,
                                               [FromQuery]string errorMsg)
        {
            var itemsPage = 10;
            var catalog = await _catalogSvc.GetCatalogItems(page ?? 0,
                                                            itemsPage,
                                                            BrandFilterApplied,
                                                            TypesFilterApplied);
            //… Additional code
        }

        }
}
```

<span data-ttu-id="c5677-181">지금까지 위의 코드 조각에서는 일반적인 HTTP 요청을 수행하는 예만 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-181">Up to this point, the above code snippet has only shown the example of performing regular HTTP requests.</span></span> <span data-ttu-id="c5677-182">이외의 유용한 기능은 다음 섹션에서 설명됩니다. 다음 섹션에서는 `HttpClient`에서 수행하는 모든 HTTP 요청이 지수 백오프로 다시 시도, 회로 차단기, 인증 토큰을 사용하는 보안 기능 또는 기타 사용자 지정 기능과 같은 복원력 있는 정책을 사용할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-182">But the 'magic' comes in the following sections where it shows how all the HTTP requests made by `HttpClient`, can have resilient policies such as retries with exponential backoff, circuit breakers, security features using auth tokens, or even any other custom feature.</span></span> <span data-ttu-id="c5677-183">정책을 추가하고 처리기를 등록된 형식화된 클라이언트에 위임하기만 하면 이 모든 기능을 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5677-183">And all of these can be done just by adding policies and delegating handlers to your registered Typed Clients.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c5677-184">추가 자료</span><span class="sxs-lookup"><span data-stu-id="c5677-184">Additional resources</span></span>

- <span data-ttu-id="c5677-185">**.NET Core에서 HttpClientFactory 사용**</span><span class="sxs-lookup"><span data-stu-id="c5677-185">**Using HttpClientFactory in .NET Core**</span></span>  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- <span data-ttu-id="c5677-186">**`dotnet/extensions` GitHub 리포지토리의 HttpClientFactory 소스 코드**</span><span class="sxs-lookup"><span data-stu-id="c5677-186">**HttpClientFactory source code in the `dotnet/extensions` GitHub repository**</span></span>  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- <span data-ttu-id="c5677-187">**Polly(.NET 복원력 및 transient-fault-handling 라이브러리)**</span><span class="sxs-lookup"><span data-stu-id="c5677-187">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <http://www.thepollyproject.org/>
  
- <span data-ttu-id="c5677-188">**종속성 주입 없이 IHttpClientFactory 사용(GitHub 문제)**</span><span class="sxs-lookup"><span data-stu-id="c5677-188">**Using IHttpClientFactory without dependency injection (GitHub issue)**</span></span>  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
><span data-ttu-id="c5677-189">[이전](implement-resilient-entity-framework-core-sql-connections.md)
>[다음](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="c5677-189">[Previous](implement-resilient-entity-framework-core-sql-connections.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
