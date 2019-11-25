---
title: HttpClientFactory를 사용하여 복원력 있는 HTTP 요청 구현
description: 애플리케이션에서 사용하기 쉽도록 .NET Core 2.1부터 제공되는 HttpClientFactory를 사용하여 `HttpClient` 인스턴스를 만드는 방법을 알아봅니다.
ms.date: 08/08/2019
ms.openlocfilehash: 9eff4a01361b3dc6f7471bc012c945d048b9a276
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737752"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="ce5a7-103">HttpClientFactory를 사용하여 복원력 있는 HTTP 요청 구현</span><span class="sxs-lookup"><span data-stu-id="ce5a7-103">Use HttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="ce5a7-104">`HttpClientFactory`는 애플리케이션에서 사용할 <xref:System.Net.Http.HttpClient> 인스턴스를 만드는 독창적인 팩터리이며, .NET Core 2.1부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-104">`HttpClientFactory` is an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="ce5a7-105">.NET Core에서 사용할 수 있는 원래의 HttpClient 클래스 문제</span><span class="sxs-lookup"><span data-stu-id="ce5a7-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="ce5a7-106">잘 알려진 원래의 <xref:System.Net.Http.HttpClient> 클래스는 쉽게 사용할 수 있지만, 많은 개발자가 제대로 사용하지 못하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-106">The original and well-known <xref:System.Net.Http.HttpClient> class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span>

<span data-ttu-id="ce5a7-107">첫 번째 문제로, 이 클래스는 삭제할 수 있지만, `HttpClient` 개체를 삭제하는 경우에도 기본 소켓이 즉시 해제되지 않고 '소켓 소모'라는 심각한 문제가 발생할 수 있기 때문에 `using` 문과 함께 사용하는 것이 최선의 선택이 아니라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-107">As a first issue, while this class is disposable, using it with the `using` statement is not the best choice because even when you dispose `HttpClient` object, the underlying socket is not immediately released and can cause a serious issue named ‘sockets exhaustion’.</span></span> <span data-ttu-id="ce5a7-108">이 문제에 대한 자세한 내용은 [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/)(잘못 사용하고 있는 HttpClient로 인해 불안정해지고 있는 소프트웨어) 블로그 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-108">For more information about this issue, see [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) blog post.</span></span>

<span data-ttu-id="ce5a7-109">따라서 `HttpClient`는 한 번 인스턴스화되어 애플리케이션의 수명 동안 다시 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="ce5a7-110">모든 요청에 대해 `HttpClient` 클래스를 인스턴스화하면 과도한 부하에서 사용할 수 있는 소켓 수가 소진됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="ce5a7-111">이 문제로 인해 `SocketException` 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="ce5a7-112">이 문제를 해결하는 데 가능한 방법은 [HttpClient 사용에 관한 Microsoft 문서](../../../csharp/tutorials/console-webapiclient.md)에서 설명한 대로 `HttpClient` 개체를 싱글톤 또는 정적으로 만드는 것을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](../../../csharp/tutorials/console-webapiclient.md).</span></span>

<span data-ttu-id="ce5a7-113">하지만 `HttpClient`에는 싱글톤 또는 정적 개체로 사용할 때 발생할 수 있는 두 번째 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-113">But there’s a second issue with `HttpClient` that you can have when you use it as singleton or static object.</span></span> <span data-ttu-id="ce5a7-114">이 경우 dotnet/corefx GitHub 리포지토리에서 이 [문제](https://github.com/dotnet/corefx/issues/11224)에 대해 설명한 대로 싱글톤 또는 정적 `HttpClient`는 DNS 변경 내용을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-114">In this case, a singleton or static `HttpClient` doesn't respect DNS changes, as explained in this [issue](https://github.com/dotnet/corefx/issues/11224) at the dotnet/corefx GitHub repository.</span></span>

<span data-ttu-id="ce5a7-115">언급한 문제를 해결하고 `HttpClient` 인스턴스를 쉽게 관리하기 위해 .NET Core 2.1에는 Polly를 통합하여 복원력 있는 HTTP 호출을 구현하는 데 사용할 수도 있는 새로운 `HttpClientFactory`가 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-115">To address those mentioned issues and make the management of `HttpClient` instances easier, .NET Core 2.1 introduced a new `HttpClientFactory` that can also be used to implement resilient HTTP calls by integrating Polly with it.</span></span>

<span data-ttu-id="ce5a7-116">[Polly](http://www.thepollyproject.org/)는 미리 정의된 정책을 사용하여 개발자가 흐름 및 스레드로부터 안전한 방식으로 애플리케이션에 복원력을 추가하는 데 도움이 되는 일시적인 오류 처리 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-116">[Polly](http://www.thepollyproject.org/) is transient-fault-handling library that helps developers add resiliency to their applications, by using some pre-defined policies in a fluent and thread-safe manner.</span></span>

## <a name="what-is-httpclientfactory"></a><span data-ttu-id="ce5a7-117">HttpClientFactory란?</span><span class="sxs-lookup"><span data-stu-id="ce5a7-117">What is HttpClientFactory</span></span>

<span data-ttu-id="ce5a7-118">`HttpClientFactory`는 다음과 같이 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-118">`HttpClientFactory` is designed to:</span></span>

- <span data-ttu-id="ce5a7-119">논리적 `HttpClient` 개체를 명명하고 구성하기 위한 중앙 위치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-119">Provide a central location for naming and configuring logical `HttpClient` objects.</span></span> <span data-ttu-id="ce5a7-120">예를 들어 특정 마이크로 서비스에 액세스하도록 미리 구성된 클라이언트(서비스 에이전트)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-120">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="ce5a7-121">`HttpClient`에서 처리기를 위임하고 Polly 기반 미들웨어를 구현하여 나가는 미들웨어에 대한 개념을 체계화하여 Polly의 복원력 정책을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-121">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly’s policies for resiliency.</span></span>
- <span data-ttu-id="ce5a7-122">`HttpClient`에는 나가는 HTTP 요청을 위해 함께 연결될 수 있는 처리기 위임이라는 개념이 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-122">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="ce5a7-123">HTTP 클라이언트를 팩터리에 등록하고, Polly 처리기를 사용하여 Polly 정책을 다시 시도, 회로 차단기 등에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-123">You register HTTP clients into the factory and you can use a Polly handler to use Polly policies for Retry, CircuitBreakers, and so on.</span></span>
- <span data-ttu-id="ce5a7-124">`HttpClientMessageHandlers`의 수명을 관리하여 `HttpClient` 수명을 직접 관리할 때 발생할 수 있는 언급된 문제를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-124">Manage the lifetime of `HttpClientMessageHandlers` to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span>

> [!NOTE]
> <span data-ttu-id="ce5a7-125">`HttpClientFactory`는 `Microsoft.Extensions.DependencyInjection` NuGet 패키지의 DI(종속성 주입) 구현과 깊은 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-125">`HttpClientFactory` is tightly tied to the dependency injection (DI) implementation in the `Microsoft.Extensions.DependencyInjection` NuGet package.</span></span> <span data-ttu-id="ce5a7-126">다른 종속성 주입 컨테이너를 사용하는 방법에 대한 자세한 내용은 이 [GitHub 토론](https://github.com/aspnet/Extensions/issues/1345)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-126">For more information about using other dependency injection containers, see this [GitHub discussion](https://github.com/aspnet/Extensions/issues/1345).</span></span>

## <a name="multiple-ways-to-use-httpclientfactory"></a><span data-ttu-id="ce5a7-127">HttpClientFactory를 사용하는 여러 가지 방법</span><span class="sxs-lookup"><span data-stu-id="ce5a7-127">Multiple ways to use HttpClientFactory</span></span>

<span data-ttu-id="ce5a7-128">애플리케이션에서 `HttpClientFactory`를 사용할 수 있는 몇 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-128">There are several ways that you can use `HttpClientFactory` in your application:</span></span>

- <span data-ttu-id="ce5a7-129">`HttpClientFactory` 직접 사용</span><span class="sxs-lookup"><span data-stu-id="ce5a7-129">Use `HttpClientFactory` Directly</span></span>
- <span data-ttu-id="ce5a7-130">명명된 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="ce5a7-130">Use Named Clients</span></span>
- <span data-ttu-id="ce5a7-131">형식화된 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="ce5a7-131">Use Typed Clients</span></span>
- <span data-ttu-id="ce5a7-132">생성된 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="ce5a7-132">Use Generated Clients</span></span>

<span data-ttu-id="ce5a7-133">간단히 하기 위해 이 지침에서는 `HttpClientFactory`를 사용하는 가장 구조적인 방법, 즉 형식화된 클라이언트(서비스 에이전트 패턴)를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-133">For the sake of brevity, this guidance shows the most structured way to use `HttpClientFactory`, which is to use Typed Clients (Service Agent pattern).</span></span> <span data-ttu-id="ce5a7-134">그러나 모든 옵션이 현재 [HttpClientFactory 사용에 대한 이 문서](/aspnet/core/fundamentals/http-requests#consumption-patterns)에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-134">However, all options are documented and are currently listed in this [article covering HttpClientFactory usage](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span></span>

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a><span data-ttu-id="ce5a7-135">형식화된 클라이언트를 HttpClientFactory에 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="ce5a7-135">How to use Typed Clients with HttpClientFactory</span></span>

<span data-ttu-id="ce5a7-136">그렇다면 “형식화된 클라이언트”란 무엇일까요?</span><span class="sxs-lookup"><span data-stu-id="ce5a7-136">So, what's a "Typed Client"?</span></span> <span data-ttu-id="ce5a7-137">`DefaultHttpClientFactory`에 의해 삽입 시 구성되는 `HttpClient`입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-137">It's just an `HttpClient` that's configured upon injection by the `DefaultHttpClientFactory`.</span></span>

<span data-ttu-id="ce5a7-138">다음 다이어그램은 `HttpClientFactory`와 함께 형식화된 클라이언트를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-138">The following diagram shows how Typed Clients are used with `HttpClientFactory`:</span></span>

![형식화된 클라이언트를 HttpClientFactory와 함께 사용하는 방법을 보여 주는 다이어그램입니다.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

<span data-ttu-id="ce5a7-140">**그림 8-4**.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-140">**Figure 8-4**.</span></span> <span data-ttu-id="ce5a7-141">형식화된 클라이언트 클래스와 함께 HttpClientFactory 사용</span><span class="sxs-lookup"><span data-stu-id="ce5a7-141">Using HttpClientFactory with Typed Client classes.</span></span>

<span data-ttu-id="ce5a7-142">위 이미지의 ClientService(컨트롤러 또는 클라이언트 코드에서 사용됨)는 등록된 `IHttpClientFactory`에서 만든 `HttpClient`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-142">In the above image, a ClientService (used by a controller or client code) uses an `HttpClient` created by the registered `IHttpClientFactory`.</span></span> <span data-ttu-id="ce5a7-143">이 팩터리는 관리하는 풀의 `HttpMessageHandler`를 `HttpClient`에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-143">This factory assigns the `HttpClient` an `HttpMessageHandler` from a pool it manages.</span></span> <span data-ttu-id="ce5a7-144">확장 메서드 `AddHttpClient`를 사용하여 DI 컨테이너에 `IHttpClientFactory`를 등록할 때 Polly의 정책을 사용하여 `HttpClient`를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-144">The `HttpClient` can be configured with Polly's policies when registering the `IHttpClientFactory` in the DI container with the extension method `AddHttpClient`.</span></span>

<span data-ttu-id="ce5a7-145">위의 구조를 구성하려면 `IServiceCollection`용 `AddHttpClient()` 확장 메서드를 포함하는 `Microsoft.Extensions.Http` NuGet 패키지를 설치하여 애플리케이션에서 `HttpClientFactory`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-145">To configure the above structure, add `HttpClientFactory` in your application by installing the `Microsoft.Extensions.Http` NuGet package that includes the `AddHttpClient()` extension method for `IServiceCollection`.</span></span> <span data-ttu-id="ce5a7-146">이 확장 메서드는 `IHttpClientFactory` 인터페이스에 대한 싱글톤으로 사용할 `DefaultHttpClientFactory`를 등록하고,</span><span class="sxs-lookup"><span data-stu-id="ce5a7-146">This extension method registers the `DefaultHttpClientFactory` to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="ce5a7-147">`HttpMessageHandlerBuilder`에 대한 일시적인 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-147">It defines a transient configuration for the `HttpMessageHandlerBuilder`.</span></span> <span data-ttu-id="ce5a7-148">풀에서 가져온 이 메시지 처리기(`HttpMessageHandler` 개체)는 팩터리에서 반환된 `HttpClient`에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-148">This message handler (`HttpMessageHandler` object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="ce5a7-149">다음 코드에서는 `AddHttpClient()`를 사용하여 `HttpClient`를 사용해야 하는 형식화된 클라이언트(서비스 에이전트)를 등록하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-149">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="ce5a7-150">이전 코드에 표시된 대로 클라이언트 서비스를 등록하면 `DefaultClientFactory`에서 각 서비스에 대한 표준 `HttpClient`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-150">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create a standard `HttpClient` for each service.</span></span>

<span data-ttu-id="ce5a7-151">또한 다음 코드와 같이 등록에 예를 들어 기준 주소를 구성하고 일부 복원력 정책을 추가하기 위한 인스턴스 관련 구성을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-151">You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:</span></span>

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="ce5a7-152">예를 들어 다음 코드에서는 위의 정책 중 하나를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-152">Just for the example sake, you can see one of the above policies in the next code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

<span data-ttu-id="ce5a7-153">[다음 문서](implement-http-call-retries-exponential-backoff-polly.md)에서 Polly 사용에 대한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-153">You can find more details about using Polly in the [Next article](implement-http-call-retries-exponential-backoff-polly.md).</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="ce5a7-154">HttpClient 수명</span><span class="sxs-lookup"><span data-stu-id="ce5a7-154">HttpClient lifetimes</span></span>

<span data-ttu-id="ce5a7-155">`IHttpClientFactory`에서 `HttpClient` 개체를 가져올 때마다 새 인스턴스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-155">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="ce5a7-156">그러나 `HttpMessageHandler`의 수명이 만료되지 않은 한, 각 `HttpClient`는 `IHttpClientFactory`에 의해 풀링되어 다시 사용되는 `HttpMessageHandler`를 사용하여 리소스 사용량을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-156">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="ce5a7-157">각 처리기가 일반적으로 자체 기본 HTTP 연결을 관리하고 필요 이상으로 처리기를 만드는 것은 연결 지연을 발생시킬 수 있으므로 처리기의 풀링이 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-157">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="ce5a7-158">또한 일부 처리기는 무한정으로 연결을 열어 놓아 처리기가 DNS 변경에 대응하는 것을 막을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-158">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="ce5a7-159">풀의 `HttpMessageHandler` 개체에는 수명이 있으며, 이 수명은 풀의 `HttpMessageHandler` 인스턴스를 다시 사용할 수 있는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-159">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="ce5a7-160">기본값은 2분이지만, 형식화된 클라이언트별로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-160">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="ce5a7-161">재정의하려면 다음 코드와 같이 클라이언트를 만들 때 반환되는 `IHttpClientBuilder`에서 `SetHandlerLifetime()`을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-161">To override it, call `SetHandlerLifetime()` on the `IHttpClientBuilder` that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

<span data-ttu-id="ce5a7-162">클라이언트마다 고유하게 구성된 처리기 수명 값이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-162">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="ce5a7-163">처리기 만료를 사용하지 않도록 설정하려면 수명을 `InfiniteTimeSpan`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-163">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="ce5a7-164">삽입되고 구성된 HttpClient를 사용하는 형식화된 클라이언트 클래스 구현</span><span class="sxs-lookup"><span data-stu-id="ce5a7-164">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="ce5a7-165">앞의 단계와 같이 샘플 코드의 클래스(예: ‘BasketService’, ‘CatalogService’, ‘OrderingService’ 등)와 같은 형식화된 클라이언트 클래스를 정의해야 합니다. 형식화된 클라이언트는 생성자를 통해 삽입된 `HttpClient` 개체를 수락하고, 이를 사용하여 일부 원격 HTTP 서비스를 호출하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-165">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like ‘BasketService’, ‘CatalogService’, ‘OrderingService’, etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="ce5a7-166">예:</span><span class="sxs-lookup"><span data-stu-id="ce5a7-166">For example:</span></span>

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

<span data-ttu-id="ce5a7-167">형식화된 클라이언트(예제에서는 CatalogService)는 DI(종속성 삽입)를 통해 활성화됩니다. 즉, HttpClient 외에도 생성자에서 등록된 모든 서비스를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-167">The Typed Client (CatalogService in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to HttpClient.</span></span>

<span data-ttu-id="ce5a7-168">형식화된 클라이언트는 실제로 임시 개체입니다. 즉, 필요할 때마다 새 인스턴스가 만들어지고, 생성될 때마다 새 `HttpClient` 인스턴스를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-168">A Typed Client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="ce5a7-169">그러나 풀의 HttpMessageHandler 개체는 여러 Http 요청에서 다시 사용되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-169">However, the HttpMessageHandler objects in the pool are the objects that are reused by multiple Http requests.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="ce5a7-170">형식화된 클라이언트 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="ce5a7-170">Use your Typed Client classes</span></span>

<span data-ttu-id="ce5a7-171">마지막으로, 형식화된 클래스를 구현하고 `AddHttpClient()`에 등록한 후에는 DI를 사용하여 서비스를 삽입할 수 있는 위치에서 해당 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-171">Finally, once you have your typed classes implemented and have them registered with `AddHttpClient()`, you can use them wherever you can have services injected by DI.</span></span> <span data-ttu-id="ce5a7-172">예를 들어 eShopOnContainers의 다음 코드와 같이 MVC 웹 앱 컨트롤러 또는 Razor 페이지 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-172">For example, in a Razor page code or controller of an MVC web app, like in the following code from eShopOnContainers:</span></span>

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

<span data-ttu-id="ce5a7-173">이 시점까지 보여 준 코드는 정기적인 HTTP 요청만 수행하는 것이지만, 다음 섹션에서는 정책을 추가하고, 등록된 형식화된 클라이언트에 처리기를 위임하여 `HttpClient`에서 수행할 모든 HTTP 요청을 처리하는 ‘마법 같은 일’이 펼쳐집니다. 이 과정에서 지수 백오프를 사용하는 다시 시도, 회로 차단기 또는 다른 사용자 지정 위임 처리기와 같은 복원력 정책을 고려하여 인증 토큰 사용, 기타 사용자 지정 기능 등의 추가 보안 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5a7-173">Up to this point, the code shown is just performing regular Http requests, but the ‘magic’ comes in the following sections where, just by adding policies and delegating handlers to your registered Typed Clients, all the HTTP requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ce5a7-174">추가 자료</span><span class="sxs-lookup"><span data-stu-id="ce5a7-174">Additional resources</span></span>

- <span data-ttu-id="ce5a7-175">**.NET Core에서 HttpClientFactory 사용**</span><span class="sxs-lookup"><span data-stu-id="ce5a7-175">**Using HttpClientFactory in .NET Core**</span></span>  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- <span data-ttu-id="ce5a7-176">**`aspnet/Extensions` GitHub 리포지토리의 HttpClientFactory 소스 코드**</span><span class="sxs-lookup"><span data-stu-id="ce5a7-176">**HttpClientFactory source code in the `aspnet/Extensions` GitHub repository**</span></span>  
  <https://github.com/aspnet/Extensions/tree/master/src/HttpClientFactory>

- <span data-ttu-id="ce5a7-177">**Polly(.NET 복원력 및 transient-fault-handling 라이브러리)**</span><span class="sxs-lookup"><span data-stu-id="ce5a7-177">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <http://www.thepollyproject.org/>
  
- <span data-ttu-id="ce5a7-178">**종속성 주입 없이 HttpClientFactory 사용(GitHub 문제)**</span><span class="sxs-lookup"><span data-stu-id="ce5a7-178">**Using HttpClientFactory without dependency injection (GitHub issue)**</span></span>  
  <https://github.com/aspnet/Extensions/issues/1345>

>[!div class="step-by-step"]
><span data-ttu-id="ce5a7-179">[이전](explore-custom-http-call-retries-exponential-backoff.md)
>[다음](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="ce5a7-179">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
