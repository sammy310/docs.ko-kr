---
ms.openlocfilehash: 47f42305f4106f5e05e555a859f13c41bb950519
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811278"
---
### <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a><span data-ttu-id="8573e-101">HTTP: IHttpClientFactory 로그 정수 상태 코드에서 생성된 HttpClient 인스턴스</span><span class="sxs-lookup"><span data-stu-id="8573e-101">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>

<span data-ttu-id="8573e-102"><xref:System.Net.Http.IHttpClientFactory>에서 생성된 <xref:System.Net.Http.HttpClient> 인스턴스는 상태 코드 이름이 아니라 정수로 HTTP 상태 코드를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-102"><xref:System.Net.Http.HttpClient> instances created by <xref:System.Net.Http.IHttpClientFactory> log HTTP status codes as integers instead of with status code names.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8573e-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="8573e-103">Version introduced</span></span>

<span data-ttu-id="8573e-104">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="8573e-104">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="8573e-105">이전 동작</span><span class="sxs-lookup"><span data-stu-id="8573e-105">Old behavior</span></span>

<span data-ttu-id="8573e-106">로깅은 HTTP 상태 코드의 텍스트 설명을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-106">Logging uses the textual descriptions of HTTP status codes.</span></span> <span data-ttu-id="8573e-107">다음 로그 메시지를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="8573e-107">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

#### <a name="new-behavior"></a><span data-ttu-id="8573e-108">새 동작</span><span class="sxs-lookup"><span data-stu-id="8573e-108">New behavior</span></span>

<span data-ttu-id="8573e-109">로깅은 HTTP 상태 코드의 정수 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-109">Logging uses the integer values of HTTP status codes.</span></span> <span data-ttu-id="8573e-110">다음 로그 메시지를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="8573e-110">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

#### <a name="reason-for-change"></a><span data-ttu-id="8573e-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="8573e-111">Reason for change</span></span>

<span data-ttu-id="8573e-112">이 로깅의 원래 동작은 항상 정수 값을 사용한 ASP.NET Core의 다른 부분과 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-112">The original behavior of this logging is inconsistent with other parts of ASP.NET Core that have always used integer values.</span></span> <span data-ttu-id="8573e-113">불일치로 인해 로그는 [Elasticsearch](https://www.elastic.co/elasticsearch/)와 같은 구조화된 로깅 시스템을 통해 쿼리하기 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-113">The inconsistency makes logs difficult to query via structured logging systems such as [Elasticsearch](https://www.elastic.co/elasticsearch/).</span></span> <span data-ttu-id="8573e-114">자세한 컨텍스트는 [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8573e-114">For more context, see [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).</span></span>

<span data-ttu-id="8573e-115">정수 값을 사용하면 값 범위에서 쿼리가 허용되므로 텍스트보다 더 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-115">Using integer values is more flexible than text because it allows queries on ranges of values.</span></span>

<span data-ttu-id="8573e-116">정수 상태 코드를 캡처할 다른 로그 값을 추가하는 것이 고려되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-116">Adding another log value to capture the integer status code was considered.</span></span> <span data-ttu-id="8573e-117">안타깝게도 이렇게 하면 나머지 ASP.NET Core와 또 다른 불일치가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-117">Unfortunately, doing so would introduce another inconsistency with the rest of ASP.NET Core.</span></span> <span data-ttu-id="8573e-118">HttpClient 로깅 및 HTTP 서버/호스팅 로깅은 이미 동일한 `StatusCode` 키 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-118">HttpClient logging and HTTP server/hosting logging use the same `StatusCode` key name already.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8573e-119">권장 조치</span><span class="sxs-lookup"><span data-stu-id="8573e-119">Recommended action</span></span>

<span data-ttu-id="8573e-120">가장 좋은 방법은 상태 코드의 정수 값을 사용하도록 로깅 쿼리를 업데이트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-120">The best option is to update logging queries to use the integer values of status codes.</span></span> <span data-ttu-id="8573e-121">이 옵션을 선택하면 여러 ASP.NET Core 버전에 걸쳐 쿼리를 작성하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-121">This option may cause some difficulty writing queries across multiple ASP.NET Core versions.</span></span> <span data-ttu-id="8573e-122">그러나 이 목적으로 정수를 사용하면 로그 쿼리 시 훨씬 더 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-122">However, using integers for this purpose is much more flexible for querying logs.</span></span>

<span data-ttu-id="8573e-123">이전 동작과의 호환성을 적용하고 텍스트 상태 코드를 사용해야 하는 경우 `IHttpClientFactory` 로깅을 고유한 항목으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-123">If you need to force compatibility with the old behavior and use textual status codes, replace the `IHttpClientFactory` logging with your own:</span></span>

1. <span data-ttu-id="8573e-124">다음 클래스의 .NET Core 3.1 버전을 프로젝트에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-124">Copy the .NET Core 3.1 versions of the following classes into your project:</span></span>

    * [<span data-ttu-id="8573e-125">LoggingHttpMessageHandlerBuilderFilter</span><span class="sxs-lookup"><span data-stu-id="8573e-125">LoggingHttpMessageHandlerBuilderFilter</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [<span data-ttu-id="8573e-126">LoggingHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="8573e-126">LoggingHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [<span data-ttu-id="8573e-127">LoggingScopeHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="8573e-127">LoggingScopeHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [<span data-ttu-id="8573e-128">HttpHeadersLogValue</span><span class="sxs-lookup"><span data-stu-id="8573e-128">HttpHeadersLogValue</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. <span data-ttu-id="8573e-129">[Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http) NuGet 패키지에서 퍼블릭 형식과 충돌하지 않도록 클래스 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-129">Rename the classes to avoid conflicts with public types in the [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http) NuGet package.</span></span>

1. <span data-ttu-id="8573e-130">`LoggingHttpMessageHandlerBuilderFilter`의 기본 제공 구현을 프로젝트의 `Startup.ConfigureServices` 메서드에 있는 고유한 항목으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8573e-130">Replace the built-in implementation of `LoggingHttpMessageHandlerBuilderFilter` with your own in the project's `Startup.ConfigureServices` method.</span></span> <span data-ttu-id="8573e-131">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="8573e-131">For example:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        // Other service registrations go first. Code omitted for brevity.

        // Place the following after all AddHttpClient registrations.
        var descriptors = services.Where(
            s => s.ServiceType == typeof(IHttpMessageHandlerBuilderFilter));
        foreach (var descriptor in descriptors)
        {
            services.Remove(descriptor);
        }

        services.AddSingleton<IHttpMessageHandlerBuilderFilter,
                              MyLoggingHttpMessageHandlerBuilderFilter>();
    }
    ```

#### <a name="category"></a><span data-ttu-id="8573e-132">범주</span><span class="sxs-lookup"><span data-stu-id="8573e-132">Category</span></span>

<span data-ttu-id="8573e-133">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8573e-133">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8573e-134">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="8573e-134">Affected APIs</span></span>

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:System.Net.Http.HttpClient`

-->
