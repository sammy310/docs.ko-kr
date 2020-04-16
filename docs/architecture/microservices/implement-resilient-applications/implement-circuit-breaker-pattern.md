---
title: 회로 차단기 패턴 구현
description: HTTP 다시 시도에 대한 보완 시스템으로 회로 차단기 패턴을 구현하는 방법을 알아봅니다.
ms.date: 03/03/2020
ms.openlocfilehash: bebe0b4a622db928175f78f8d3e303d3d7adf170
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988887"
---
# <a name="implement-the-circuit-breaker-pattern"></a><span data-ttu-id="e682e-103">회로 차단기 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="e682e-103">Implement the Circuit Breaker pattern</span></span>

<span data-ttu-id="e682e-104">앞에서 설명한 것처럼 원격 서비스나 리소스에 연결할 때 발생할 수 있는 복구에 소요되는 시간이 유동적인 오류를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-104">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="e682e-105">이러한 종류의 오류를 처리하면 애플리케이션의 안정성과 탄력성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-105">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="e682e-106">분산된 환경에서는 느린 네트워크 연결 및 시간 초과 등과 같은 일시적 오류 때문에, 또는 리소스가 느리게 응답하거나 일시적으로 사용할 수 없어 원격 리소스 및 서비스에 대한 호출이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-106">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are responding slowly or are temporarily unavailable.</span></span> <span data-ttu-id="e682e-107">이러한 오류는 일반적으로 짧은 시간 안에 자체적으로 해결되며, "다시 시도 패턴"과 같은 전략을 사용하여 이러한 오류를 처리할 수 있는 강력한 클라우드 애플리케이션을 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-107">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the "Retry pattern".</span></span>

<span data-ttu-id="e682e-108">그러나 해결에 더 오랜 시간이 필요한 예기치 않은 이벤트로 인한 오류 상황도 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-108">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="e682e-109">이러한 오류의 심각도는 부분적 연결 손실에서부터 전체 서비스 오류에까지 이를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-109">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="e682e-110">이러한 상황에서 애플리케이션이 성공할 가능성이 없는 작업을 계속 다시 시도하는 것은 무의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-110">In these situations, it might be pointless for an application to continually retry an operation that's unlikely to succeed.</span></span>

<span data-ttu-id="e682e-111">이보다는 작업에 실패했음을 받아들이고 그에 따라 오류를 처리하도록 애플리케이션을 코딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-111">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="e682e-112">Http 다시 시도를 부주의하게 사용하면 자신의 소프트웨어 내에서 [DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)(서비스 거부) 공격이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-112">Using Http retries carelessly could result in creating a Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) attack within your own software.</span></span> <span data-ttu-id="e682e-113">마이크로 서비스가 실패하거나 느리게 수행되면 여러 클라이언트에서 실패한 요청을 반복적으로 다시 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-113">As a microservice fails or performs slowly, multiple clients might repeatedly retry failed requests.</span></span> <span data-ttu-id="e682e-114">이로 인해 실패한 서비스를 대상으로 하는 트래픽이 기하 급수적으로 증가할 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-114">That creates a dangerous risk of exponentially increasing traffic targeted at the failing service.</span></span>

<span data-ttu-id="e682e-115">따라서 계속 시도할 필요가 없는 경우 과도한 요청을 중지할 수 있도록 일종의 방어막이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-115">Therefore, you need some kind of defense barrier so that excessive requests stop when it isn't worth to keep trying.</span></span> <span data-ttu-id="e682e-116">이러한 방어막은 정확히 회로 차단기입니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-116">That defense barrier is precisely the circuit breaker.</span></span>

<span data-ttu-id="e682e-117">회로 차단기 패턴은 "다시 시도 패턴"과 다른 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-117">The Circuit Breaker pattern has a different purpose than the "Retry pattern".</span></span> <span data-ttu-id="e682e-118">"다시 시도 패턴"을 사용하면 애플리케이션에서 작업이 결국 성공한다고 예상하여 작업을 다시 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-118">The "Retry pattern" enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="e682e-119">회로 차단기 패턴은 애플리케이션이 실패할 가능성이 있는 작업을 수행하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-119">The Circuit Breaker pattern prevents an application from performing an operation that's likely to fail.</span></span> <span data-ttu-id="e682e-120">애플리케이션에서 이 두 패턴을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-120">An application can combine these two patterns.</span></span> <span data-ttu-id="e682e-121">그러나 다시 시도 논리는 회로 차단기에서 반환하는 모든 예외에 민감해야 하며, 회로 차단기에서 일시적 오류가 아니라고 나타내는 경우 다시 시도를 중단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-121">However, the retry logic should be sensitive to any exception returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implement-circuit-breaker-pattern-with-ihttpclientfactory-and-polly"></a><span data-ttu-id="e682e-122">`IHttpClientFactory` 및 Polly를 통한 회로 차단기 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="e682e-122">Implement Circuit Breaker pattern with `IHttpClientFactory` and Polly</span></span>

<span data-ttu-id="e682e-123">다시 시도를 구현할 때 회로 차단기에 권장되는 방법은 Polly와 같이 입증된 .NET 라이브러리와 `IHttpClientFactory`와의 네이티브 통합을 활용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-123">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly and its native integration with `IHttpClientFactory`.</span></span>

<span data-ttu-id="e682e-124">`IHttpClientFactory` 나가는 미들웨어 파이프라인에 회로 차단기 정책을 추가하는 것은 `IHttpClientFactory`를 사용할 때 이미 사용하고 있는 코드에 하나의 증분 코드 부분을 추가하는 것만큼 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-124">Adding a circuit breaker policy into your `IHttpClientFactory` outgoing middleware pipeline is as simple as adding a single incremental piece of code to what you already have when using `IHttpClientFactory`.</span></span>

<span data-ttu-id="e682e-125">여기서 HTTP 호출 다시 시도에 사용된 코드에 추가되는 유일한 부분은 ConfigureServices() 메서드의 일부인 다음 증분 코드와 같이 사용하려는 정책 목록에 회로 차단기 정책을 추가하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-125">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown in the following incremental code, part of the ConfigureServices() method.</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Sample. Default lifetime is 2 minutes
        .AddHttpMessageHandler<HttpClientAuthorizationDelegatingHandler>()
        .AddPolicyHandler(GetRetryPolicy())
        .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="e682e-126">`AddPolicyHandler()`는 사용할 `HttpClient` 개체에 정책을 추가하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-126">The `AddPolicyHandler()` method is what adds policies to the `HttpClient` objects you'll use.</span></span> <span data-ttu-id="e682e-127">이 경우 회로 차단기에 대한 Polly 정책이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-127">In this case, it's adding a Polly policy for a circuit breaker.</span></span>

<span data-ttu-id="e682e-128">좀 더 모듈화된 방법을 사용하기 위해 회로 차단기 정책은 다음 코드와 같이 `GetCircuitBreakerPolicy()`라는 별도의 메서드로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-128">To have a more modular approach, the Circuit Breaker Policy is defined in a separate method called `GetCircuitBreakerPolicy()`, as shown in the following code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetCircuitBreakerPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .CircuitBreakerAsync(5, TimeSpan.FromSeconds(30));
}
```

<span data-ttu-id="e682e-129">위의 코드 예제에서 Http 요청을 다시 시도할 때 5개의 연속된 오류가 발생하면 회로를 차단하거나 열리도록 회로 차단기 정책이 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-129">In the code example above, the circuit breaker policy is configured so it breaks or opens the circuit when there have been five consecutive faults when retrying the Http requests.</span></span> <span data-ttu-id="e682e-130">이 경우 회로가 30초 동안 끊깁니다. 이 기간에는 호출이 실제로 배치되는 것이 아니라 회로 차단기에 의해 즉시 실패하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-130">When that happens, the circuit will break for 30 seconds: in that period, calls will be failed immediately by the circuit-breaker rather than actually be placed.</span></span>  <span data-ttu-id="e682e-131">정책은 [관련 예외 및 HTTP 상태 코드](/aspnet/core/fundamentals/http-requests#handle-transient-faults)를 자동으로 오류로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-131">The policy automatically interprets [relevant exceptions and HTTP status codes](/aspnet/core/fundamentals/http-requests#handle-transient-faults) as faults.</span></span>  

<span data-ttu-id="e682e-132">또한 HTTP 호출을 수행하는 클라이언트 애플리케이션 또는 서비스와 다른 환경에 배포된 특정 리소스에 문제가 있는 경우 회로 차단기를 사용하여 요청을 대체 인프라로 리디렉션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-132">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you had issues in a particular resource that's deployed in a different environment than the client application or service that's performing the HTTP call.</span></span> <span data-ttu-id="e682e-133">이런 식으로 클라이언트 애플리케이션이 아닌 백 엔드 마이크로 서비스에만 영향을 미치는 데이터 센터에서 중단이 발생한 경우, 클라이언트 애플리케이션이 대체(fallback) 서비스로 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-133">That way, if there's an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="e682e-134">Polly는 이 [장애 조치(failover) 정책](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) 시나리오를 자동화하기 위해 새 정책을 계획하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-134">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="e682e-135">이러한 모든 기능은 사용자를 위해 Azure에서 위치 투명성을 사용하여 자동으로 관리하는 대신, .NET 코드 내에서 장애 조치를 관리하는 경우를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-135">All those features are for cases where you're managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

<span data-ttu-id="e682e-136">사용 관점에서 HttpClient를 사용하는 경우 이전 섹션과 같이 코드가 `IHttpClientFactory`를 통해 `HttpClient`를 사용할 때와 동일하므로 여기서는 추가할 새로운 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-136">From a usage point of view, when using HttpClient, there’s no need to add anything new here because the code is the same than when using `HttpClient` with `IHttpClientFactory`, as shown in previous sections.</span></span>

## <a name="test-http-retries-and-circuit-breakers-in-eshoponcontainers"></a><span data-ttu-id="e682e-137">eShopOnContainers에서 HTTP 다시 시도 및 회로 차단기 테스트</span><span class="sxs-lookup"><span data-stu-id="e682e-137">Test Http retries and circuit breakers in eShopOnContainers</span></span>

<span data-ttu-id="e682e-138">Docker 호스트에서 eShopOnContainers 솔루션을 시작할 때마다 여러 컨테이너를 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-138">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="e682e-139">SQL Server 컨테이너처럼 일부 컨테이너는 시작과 초기화가 더 느립니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-139">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="e682e-140">특히 처음 Docker에 eShopOnContainers 애플리케이션을 배포하는 경우 이미지와 데이터베이스를 설정해야 하기 때문에 이 문제가 더욱 두드러집니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-140">This is especially true the first time you deploy the eShopOnContainers application into Docker because it needs to set up the images and the database.</span></span> <span data-ttu-id="e682e-141">일부 컨테이너가 다른 컨테이너보다 늦게 시작되기 때문에 이전 섹션에서 설명한 대로 도커-작성 수준에서 컨테이너 간의 종속성을 설정했다 하더라도 나머지 서비스에서 최초에 HTTP 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-141">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="e682e-142">이러한 컨테이너 간 도커-작성 종속성은 프로세스 수준에 국한됩니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-142">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="e682e-143">컨테이너의 진입점 프로세스는 시작될 수 있지만 SQL Server는 쿼리 준비가 되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-143">The container's entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="e682e-144">그 결과 오류가 연쇄 발생하고 특정 컨테이너를 사용하려 할 때 애플리케이션에 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-144">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="e682e-145">또한 애플리케이션을 클라우드에 배포할 때도 시작 중에 이런 종류의 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-145">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="e682e-146">이 경우 클러스터의 노드 전체에서 컨테이너 수의 균형을 유지할 때 오케스트레이터가 한 노드나 VM의 컨테이너를 다른 곳으로 옮길 수 있습니다(즉 새 인스턴스 시작).</span><span class="sxs-lookup"><span data-stu-id="e682e-146">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster's nodes.</span></span>

<span data-ttu-id="e682e-147">모든 컨테이너를 시작할 때 이러한 문제를 해결하는 'eShopOnContainers' 방법은 앞에서 설명한 다시 시도 패턴을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-147">The way 'eShopOnContainers' solves those issues when starting all the containers is by using the Retry pattern illustrated earlier.</span></span>

### <a name="test-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="e682e-148">eShopOnContainers에서 회로 차단기 테스트</span><span class="sxs-lookup"><span data-stu-id="e682e-148">Test the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="e682e-149">eShopOnContainers를 사용하여 회로를 차단하거나 열고, 테스트할 수 있는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-149">There are a few ways you can break/open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="e682e-150">한 옵션은 회로 차단기 정책에서 재시도 허용 횟수를 1로 낮추고 전체 솔루션을 Docker에 다시 배포하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-150">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="e682e-151">단일 재시도 상황에서 배포 중에 HTTP 요청이 실패하면 회로 차단기가 열리고 오류가 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-151">With a single retry, there's a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="e682e-152">또 다른 옵션은 **Basket** 마이크로 서비스에서 구현된 사용자 지정 미들웨어를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-152">Another option is to use custom middleware that's implemented in the **Basket** microservice.</span></span> <span data-ttu-id="e682e-153">이 미들웨어를 사용할 때는 모든 HTTP 요청이 캐시되고 상태 코드 500을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-153">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="e682e-154">다음과 같이 실패 URI에 대한 GET 요청을 수행하여 마들웨어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-154">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

- `GET http://localhost:5103/failing`\
  <span data-ttu-id="e682e-155">이 요청은 미들웨어의 현재 상태를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-155">This request returns the current state of the middleware.</span></span> <span data-ttu-id="e682e-156">미들웨어를 사용할 경우 이 요청은 상태 코드 500을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-156">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="e682e-157">미들웨어를 사용하지 않으면 응답이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-157">If the middleware is disabled, there's no response.</span></span>

- `GET http://localhost:5103/failing?enable`\
  <span data-ttu-id="e682e-158">이 요청은 미들웨어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-158">This request enables the middleware.</span></span>

- `GET http://localhost:5103/failing?disable`\
  <span data-ttu-id="e682e-159">이 요청은 미들웨어를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-159">This request disables the middleware.</span></span>

<span data-ttu-id="e682e-160">예를 들어, 애플리케이션이 실행되면 아무 브라우저에서나 다음 URI를 통해 요청을 수행하여 미들웨어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-160">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="e682e-161">순서 지정 마이크로 서비스는 포트 5103을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-161">Note that the ordering microservice uses port 5103.</span></span>

`http://localhost:5103/failing?enable`

<span data-ttu-id="e682e-162">그런 다음, 그림 8-5와 같이 URI `http://localhost:5103/failing`을 사용하여 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-162">You can then check the status using the URI `http://localhost:5103/failing`, as shown in Figure 8-5.</span></span>

![실패한 미들웨어 시뮬레이션 상태 확인의 스크린샷](./media/implement-circuit-breaker-pattern/failing-middleware-simulation.png)

<span data-ttu-id="e682e-164">**그림 8-5**.</span><span class="sxs-lookup"><span data-stu-id="e682e-164">**Figure 8-5**.</span></span> <span data-ttu-id="e682e-165">“실패” ASP.NET 미들웨어의 상태 확인 - 이 경우 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-165">Checking the state of the "Failing" ASP.NET middleware – In this case, disabled.</span></span>

<span data-ttu-id="e682e-166">이 시점에서 Basket 마이크로 서비스는 호출될 때마다 상태 코드 500으로 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-166">At this point, the Basket microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="e682e-167">미들웨어가 실행되면 MVC 웹 애플리케이션으로부터 주문을 시도해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-167">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="e682e-168">요청이 실패하기 때문에 회로가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-168">Because the requests fail, the circuit will open.</span></span>

<span data-ttu-id="e682e-169">다음 예제에서는 MVC 웹 애플리케이션의 논리에 주문 수행을 위한 수집 블록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-169">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span>  <span data-ttu-id="e682e-170">이 코드가 열림-회로 예외를 수집하면 사용자에게 기다리라고 알리는 친숙한 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-170">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {
            var user = _appUserParser.Parse(HttpContext.User);
            //Http requests using the Typed Client (Service Agent)
            var vm = await _basketSvc.GetBasket(user);
            return View(vm);
        }
        catch (BrokenCircuitException)
        {
            // Catches error when Basket.api is in circuit-opened mode
            HandleBrokenCircuitException();
        }
        return View();
    }

    private void HandleBrokenCircuitException()
    {
        TempData["BasketInoperativeMsg"] = "Basket Service is inoperative, please try later on. (Business message due to Circuit-Breaker)";
    }
}
```

<span data-ttu-id="e682e-171">다음은 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-171">Here's a summary.</span></span> <span data-ttu-id="e682e-172">재시도 정책이 HTTP 요청을 수행하기 위해 몇 차례 시도했고 HTTP 오류를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-172">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="e682e-173">회로 차단기 정책에 설정된 최대 다시 시도 횟수(이 경우 5)에 도달하면 애플리케이션에서 BrokenCircuitException을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-173">When the number of retries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="e682e-174">그 결과 그림 8-6처럼 사용자에게 친숙한 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-174">The result is a friendly message, as shown in Figure 8-6.</span></span>

![장바구니 서비스가 작동하지 않음 오류가 발생한 MVC 웹앱의 스크린샷](./media/implement-circuit-breaker-pattern/basket-service-inoperative.png)

<span data-ttu-id="e682e-176">**그림 8-6**.</span><span class="sxs-lookup"><span data-stu-id="e682e-176">**Figure 8-6**.</span></span> <span data-ttu-id="e682e-177">UI에 오류를 반환한 회로 차단기</span><span class="sxs-lookup"><span data-stu-id="e682e-177">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="e682e-178">회로를 열거나 차단하는 경우에 대해 다른 논리를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-178">You can implement different logic for when to open/break the circuit.</span></span> <span data-ttu-id="e682e-179">또는 대체 데이터 센터나 중복 백 엔드 시스템이 있는 경우 다른 백 엔드 마이크로 서비스에 대해 HTTP 요청을 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-179">Or you can try an HTTP request against a different back-end microservice if there's a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="e682e-180">마지막으로, `CircuitBreakerPolicy`에 대한 또 다른 가능성은 `Isolate`(회로를 강제로 열고 열려 있는 상태로 유지) 및 `Reset`(회로를 다시 닫음)을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-180">Finally, another possibility for the `CircuitBreakerPolicy` is to use `Isolate` (which forces open and holds open the circuit) and `Reset` (which closes it again).</span></span> <span data-ttu-id="e682e-181">이를 사용하여 정책에서 직접 분리 및 재설정을 호출하는 유틸리티 HTTP 엔드포인트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-181">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span>  <span data-ttu-id="e682e-182">이러한 HTTP 엔드포인트는 업그레이드 등의 상황에서 다운스트림을 임시 분리하기 위해 프로덕션에서 적절히 안전하게 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-182">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="e682e-183">또는 오류가 있다고 의심되는 다운스트림 시스템을 보호하기 위해 회로를 수동으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e682e-183">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e682e-184">추가 자료</span><span class="sxs-lookup"><span data-stu-id="e682e-184">Additional resources</span></span>

- <span data-ttu-id="e682e-185">**회로 차단기 패턴**</span><span class="sxs-lookup"><span data-stu-id="e682e-185">**Circuit Breaker pattern**</span></span>\
  [https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker](/azure/architecture/patterns/circuit-breaker)

>[!div class="step-by-step"]
><span data-ttu-id="e682e-186">[이전](implement-http-call-retries-exponential-backoff-polly.md)
>[다음](monitor-app-health.md)</span><span class="sxs-lookup"><span data-stu-id="e682e-186">[Previous](implement-http-call-retries-exponential-backoff-polly.md)
[Next](monitor-app-health.md)</span></span>
