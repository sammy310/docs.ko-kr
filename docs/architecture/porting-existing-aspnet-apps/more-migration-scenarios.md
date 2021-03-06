---
title: 추가 마이그레이션 시나리오
description: 이 섹션에서는 .NET Framework 앱을 .NET Core/.NET 5로 업그레이드 하는 추가 마이그레이션 시나리오 및 기술에 대해 설명 합니다.
author: ardalis
ms.date: 02/11/2021
ms.openlocfilehash: fa1b756d8852854e50127ae3e7443e2949cceaa8
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401724"
---
# <a name="more-migration-scenarios"></a><span data-ttu-id="34a52-103">추가 마이그레이션 시나리오</span><span class="sxs-lookup"><span data-stu-id="34a52-103">More migration scenarios</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="34a52-104">이 섹션에서는 다양 한 ASP.NET 앱 시나리오에 대해 설명 하 고 각 시나리오를 해결 하기 위한 특정 기술을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-104">This section describes several different ASP.NET app scenarios, and offers specific techniques for solving each of them.</span></span> <span data-ttu-id="34a52-105">이 섹션을 사용 하 여 앱에 적용할 수 있는 시나리오를 식별 하 고 앱 및 해당 호스팅 환경에 대해 작동 하는 기술을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-105">You can use this section to identify scenarios applicable to your app, and evaluate which techniques will work for your app and its hosting environment.</span></span>

## <a name="migrate-aspnet-mvc-5-and-webapi-2-to-aspnet-core-mvc"></a><span data-ttu-id="34a52-106">ASP.NET MVC 5와 WebApi 2를 ASP.NET Core MVC로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="34a52-106">Migrate ASP.NET MVC 5 and WebApi 2 to ASP.NET Core MVC</span></span>

<span data-ttu-id="34a52-107">ASP.NET MVC 5 및 Web API 2 앱에서 일반적인 시나리오는 동일한 응용 프로그램에 두 제품을 설치 하는 것 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-107">A common scenario in ASP.NET MVC 5 and Web API 2 apps was for both products to be installed in the same application.</span></span> <span data-ttu-id="34a52-108">이는 많은 팀에서 사용 하는 지원 되는 비교적 일반적인 방법 이지만, 두 제품이 서로 다른 추상화를 사용 하기 때문에 몇 가지 중복 노력이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-108">This is a supported and relatively common approach used by many teams, but because the two products use different abstractions, there is some redundant effort needed.</span></span> <span data-ttu-id="34a52-109">예를 들어 ASP.NET MVC에 대 한 경로 설정은에서 메서드를 사용 하 여 수행 됩니다 (예 `RouteCollection` : `MapMvcAttributeRoutes()` 및) `MapRoute()` .</span><span class="sxs-lookup"><span data-stu-id="34a52-109">For example, setting up routes for ASP.NET MVC is done using methods on `RouteCollection`, such as `MapMvcAttributeRoutes()` and `MapRoute()`.</span></span> <span data-ttu-id="34a52-110">하지만 ASP.NET Web API 2 라우팅은 `HttpConfiguration` 및와 같은 및 메서드로 관리 `MapHttpAttributeRoutes()` 됩니다 `MapHttpRoute()` .</span><span class="sxs-lookup"><span data-stu-id="34a52-110">But ASP.NET Web API 2 routing is managed with `HttpConfiguration` and methods like `MapHttpAttributeRoutes()` and `MapHttpRoute()`.</span></span>

<span data-ttu-id="34a52-111">`eShopLegacyMVC`앱은 ASP.NET MVC와 WEB API를 모두 포함 하 고, `App_Start` 둘 다에 대 한 경로를 설정 하기 위해 해당 폴더에 메서드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-111">The `eShopLegacyMVC` app includes both ASP.NET MVC and Web API, and includes methods in its `App_Start` folder for setting up routes for both.</span></span> <span data-ttu-id="34a52-112">또한 Autofac를 사용 하 여 종속성 주입을 지원 합니다 .이를 위해 구성 해야 하는 두 가지 유사한 작업 집합이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-112">It also supports dependency injection using Autofac, which also requires two sets of similar work to configure:</span></span>

```csharp
protected IContainer RegisterContainer()
{
    var builder = new ContainerBuilder();

    var thisAssembly = Assembly.GetExecutingAssembly();
    builder.RegisterControllers(thisAssembly);      // MVC controllers
    builder.RegisterApiControllers(thisAssembly);   // Web API controllers

    var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
    builder.RegisterModule(new ApplicationModule(mockData));

    var container = builder.Build();

    // set mvc resolver
    DependencyResolver.SetResolver(new AutofacDependencyResolver(container));

    // set webapi resolver
    var resolver = new AutofacWebApiDependencyResolver(container);
    GlobalConfiguration.Configuration.DependencyResolver = resolver;

    return container;
}
```

<span data-ttu-id="34a52-113">ASP.NET Core 사용 하도록 이러한 앱을 업그레이드 하는 경우 이러한 중복 된 작업과 때때로 수반 되는 혼동은 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-113">When upgrading these apps to use ASP.NET Core, this duplicate effort and the confusion that sometimes accompanies it is eliminated.</span></span> <span data-ttu-id="34a52-114">ASP.NET Core MVC는 라우팅, 필터 등에 대해 하나의 규칙 집합을 포함 하는 통합 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-114">ASP.NET Core MVC is a unified framework with one set of rules for routing, filters, and more.</span></span> <span data-ttu-id="34a52-115">종속성 주입은 .NET Core 자체에 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-115">Dependency injection is built into .NET Core itself.</span></span> <span data-ttu-id="34a52-116">`Startup.cs`샘플의 앱에 표시 된 것 처럼이 모든 것을에서 구성할 수 있습니다 `eShopPorted` .</span><span class="sxs-lookup"><span data-stu-id="34a52-116">All of this can can be configured in `Startup.cs`, as is shown in the `eShopPorted` app in the sample.</span></span>

## <a name="migrate-httpresponsemessage-to-aspnet-core"></a><span data-ttu-id="34a52-117">ASP.NET Core로 HttpResponseMessage 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="34a52-117">Migrate HttpResponseMessage to ASP.NET Core</span></span>

<span data-ttu-id="34a52-118">일부 ASP.NET Web API 앱에는를 반환 하는 작업 메서드가 있을 수 있습니다 `HttpResponseMessage` .</span><span class="sxs-lookup"><span data-stu-id="34a52-118">Some ASP.NET Web API apps may have action methods that return `HttpResponseMessage`.</span></span> <span data-ttu-id="34a52-119">이 형식은 ASP.NET Core에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-119">This type does not exist in ASP.NET Core.</span></span> <span data-ttu-id="34a52-120">다음은 `Delete` `ResponseMessage` 기본에서 도우미 메서드를 사용 하 여 동작 메서드에서 사용 하는 예제입니다 `ApiController` .</span><span class="sxs-lookup"><span data-stu-id="34a52-120">Below is an example of its usage in a `Delete` action method, using the `ResponseMessage` helper method on the base `ApiController`:</span></span>

```csharp
// DELETE api/<controller>/5
[HttpDelete]
public IHttpActionResult Delete(int id)
{
    var brandToDelete = _service.GetCatalogBrands().FirstOrDefault(x => x.Id == id);
    if (brandToDelete == null)
    {
        return ResponseMessage(new HttpResponseMessage(HttpStatusCode.NotFound));
    }

    // demo only - don't actually delete
    return ResponseMessage(new HttpResponseMessage(HttpStatusCode.OK));
}
```

<span data-ttu-id="34a52-121">ASP.NET Core MVC에는 모든 일반적인 HTTP 응답 상태 코드에 대해 사용할 수 있는 도우미 메서드가 있으므로 위의 메서드가 다음 코드로 포팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-121">In ASP.NET Core MVC, there are helper methods available for all of the common HTTP response status codes, so the above method would be ported to the following code:</span></span>

```csharp
[HttpDelete("{id}")]
public IActionResult Delete(int id)
{
    var brandToDelete = _service.GetCatalogBrands().FirstOrDefault(x => x.Id == id);
    if (brandToDelete == null)
    {
        return NotFound();
    }

    // demo only - don't actually delete
    return Ok();
}
```

<span data-ttu-id="34a52-122">도우미가 없는 사용자 지정 상태 코드를 반환 해야 하는 경우 언제 든 지를 사용 하 여 원하는 `return StatusCode(int statusCode)` 숫자 코드를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-122">If you do find that you need to return a custom status code for which no helper exists, you can always use `return StatusCode(int statusCode)` to return any numeric code you like.</span></span>

## <a name="migrate-content-negotiation-from-aspnet-web-api-to-aspnet-core"></a><span data-ttu-id="34a52-123">ASP.NET Web API에서 ASP.NET Core 콘텐츠 협상 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="34a52-123">Migrate content negotiation from ASP.NET Web API to ASP.NET Core</span></span>

<span data-ttu-id="34a52-124">ASP.NET Web API 2는 기본적으로 [콘텐츠 협상](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation) 을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-124">ASP.NET Web API 2 supports [content negotiation](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation) natively.</span></span> <span data-ttu-id="34a52-125">샘플 앱에는 `BrandsController` 해당 결과를 XML 또는 JSON으로 나열 하 여이 지원을 보여 주는이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-125">The sample app includes a `BrandsController` that demonstrates this support by listing its results in either XML or JSON.</span></span> <span data-ttu-id="34a52-126">이는 요청의 헤더를 기반으로 `Accept` 하며, 또는를 포함 하는 경우 변경 됩니다 `application/xml` `application/json` .</span><span class="sxs-lookup"><span data-stu-id="34a52-126">This is based on the request's `Accept` header, and changes when it includes `application/xml` or `application/json`.</span></span>

<span data-ttu-id="34a52-127">ASP.NET MVC 5 앱은에서 기본 제공 되는 콘텐츠 협상을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-127">ASP.NET MVC 5 apps do not have content negotiation support built in.</span></span>

<span data-ttu-id="34a52-128">콘텐츠 협상은 더 유연 하 고 많은 수의 클라이언트에서 API를 사용할 수 있도록 하기 때문에 특정 인코딩 유형을 반환 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-128">Content negotiation is preferable to returning a specific encoding type, as it is more flexible and makes the API available to a larger number of clients.</span></span> <span data-ttu-id="34a52-129">현재 특정 형식을 반환 하는 작업 메서드가 있는 경우 코드를 ASP.NET Core으로 이식할 때 콘텐츠 협상을 지 원하는 결과 형식을 반환 하도록 수정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-129">If you currently have action methods that return a specific format, you should consider modifying them to return a result type that supports content negotiation when you port the code to ASP.NET Core.</span></span>

<span data-ttu-id="34a52-130">다음 코드는 클라이언트 헤더 내용에 관계 없이 JSON 형식으로 데이터를 반환 합니다 `Accept` .</span><span class="sxs-lookup"><span data-stu-id="34a52-130">The following code returns data in JSON format regardless of client `Accept` header content:</span></span>

```csharp
[HttpGet]
public ActionResult Index()
{
    return Json(new { Message = "Hello World!" });
}
```

<span data-ttu-id="34a52-131">[ASP.NET CORE MVC](/aspnet/core/web-api/advanced/formatting)는 적절 한 [반환 형식이](/aspnet/core/web-api/action-return-types) 사용 된 경우 기본적으로 콘텐츠 협상을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-131">[ASP.NET Core MVC supports content negotiation natively](/aspnet/core/web-api/advanced/formatting), provided an appropriate [return type](/aspnet/core/web-api/action-return-types) is used.</span></span> <span data-ttu-id="34a52-132">콘텐츠 협상은 컨트롤러 도우미 메서드에서 반환 하는 상태 코드 관련 작업 결과에서 반환 되는 [ObjectResult]에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-132">Content negotiation is implemented by [ObjectResult] which is returned by the status code-specific action results returned by the controller helper methods.</span></span> <span data-ttu-id="34a52-133">ASP.NET Core MVC에서 구현 되 고 콘텐츠 협상을 사용 하는 이전 작업 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-133">The previous action method, implemented in ASP.NET Core MVC and using content negotiation, would be:</span></span>

```csharp
public IActionResult Index()
{
    return Ok(new { Message = "Hello World!"} );
}
```

<span data-ttu-id="34a52-134">이렇게 하면 기본적으로 JSON 형식으로 데이터가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-134">This will default to returning the data in JSON format.</span></span> <span data-ttu-id="34a52-135">[적절 한 포맷터를 사용 하 여 앱을 구성한 경우](/aspnet/core/web-api/advanced/formatting)XML 및 기타 형식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34a52-135">XML and other formats will be used [if the app has been configured with the appropriate formatter](/aspnet/core/web-api/advanced/formatting).</span></span>

## <a name="references"></a><span data-ttu-id="34a52-136">참조</span><span class="sxs-lookup"><span data-stu-id="34a52-136">References</span></span>

- [<span data-ttu-id="34a52-137">ASP.NET Web API 콘텐츠 협상</span><span class="sxs-lookup"><span data-stu-id="34a52-137">ASP.NET Web API Content Negotiation</span></span>](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation)
- [<span data-ttu-id="34a52-138">ASP.NET Core Web API에서 응답 데이터 서식 지정</span><span class="sxs-lookup"><span data-stu-id="34a52-138">Format response data in ASP.NET Core Web API</span></span>](/aspnet/core/web-api/advanced/formatting)

>[!div class="step-by-step"]
><span data-ttu-id="34a52-139">[이전](example-migration-eshop.md)
>[다음](deployment-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="34a52-139">[Previous](example-migration-eshop.md)
[Next](deployment-scenarios.md)</span></span>
