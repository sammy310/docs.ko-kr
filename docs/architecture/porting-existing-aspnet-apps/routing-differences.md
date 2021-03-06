---
title: ASP.NET MVC와 ASP.NET Core 간의 라우팅 차이점
description: ASP.NET MVC의 런타임에는 라우팅을 어떻게 정의 하 고 어떻게 작동 하나요? ASP.NET Core 앱에서 라우팅이 어떻게 다릅니까?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: d5c18948248f03a19c97461efe3df38a5be9360b
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401717"
---
# <a name="routing-differences-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="04f07-104">ASP.NET MVC와 ASP.NET Core 간의 라우팅 차이점</span><span class="sxs-lookup"><span data-stu-id="04f07-104">Routing differences between ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="04f07-105">라우팅은 들어오는 브라우저 요청을 특정 컨트롤러 작업 (또는 Razor Pages 처리기)에 매핑하는 작업을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-105">Routing is responsible for mapping incoming browser requests to particular controller actions (or Razor Pages handlers).</span></span> <span data-ttu-id="04f07-106">이 섹션에서는 ASP.NET MVC (및 Web API)와 ASP.NET Core (MVC, Razor Pages 및 기타) 간에 라우팅이 어떻게 다른 지 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-106">This section covers how routing differs between ASP.NET MVC (and Web API) and ASP.NET Core (MVC, Razor Pages, and otherwise).</span></span>

## <a name="routing-in-aspnet-mvc-and-web-api"></a><span data-ttu-id="04f07-107">ASP.NET MVC 및 Web API의 라우팅</span><span class="sxs-lookup"><span data-stu-id="04f07-107">Routing in ASP.NET MVC and Web API</span></span>

<span data-ttu-id="04f07-108">ASP.NET MVC는 라우팅에 대 한 두 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-108">ASP.NET MVC offers two approaches to routing:</span></span>

1. <span data-ttu-id="04f07-109">경로 테이블은 들어오는 요청을 컨트롤러 작업에 일치 시키는 데 사용할 수 있는 경로 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-109">The route table, which is a collection of routes that can be used to match incoming requests to controller actions.</span></span>
1. <span data-ttu-id="04f07-110">특성 라우팅은 동일한 기능을 수행 하지만 전역 경로 테이블을 편집 하는 대신 작업 자체를 데코레이팅하는 방법으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-110">Attribute routing, which performs the same function but is achieved by decorating the actions themselves, rather than editing a global route table.</span></span>

## <a name="route-table"></a><span data-ttu-id="04f07-111">경로 테이블</span><span class="sxs-lookup"><span data-stu-id="04f07-111">Route table</span></span>

<span data-ttu-id="04f07-112">경로 테이블은 앱이 시작 될 때 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-112">The route table is configured when the app starts up.</span></span> <span data-ttu-id="04f07-113">일반적으로 정적 메서드 호출은 다음과 같이 전역 경로 컬렉션을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-113">Typically, a static method call is used to configure the global route collection, like so:</span></span>

```csharp
public class MvcApplication : System.Web.HttpApplication
{
    public static void RegisterRoutes(RouteCollection routes)
    {
        routes.IgnoreRoute("{resource}.axd/{*pathInfo}");
        routes.MapRoute(
            name: "Default",
            url: "{controller}/{action}/{id}",
            defaults: new { controller = "Home", action = "Index", id = "" },
            constraints: new { id = "\\d+" }
        );
    }

    protected void Application_Start()
    {
        RegisterRoutes(RouteTable.Routes);
    }
}
```

<span data-ttu-id="04f07-114">위의 코드에서 경로 테이블은를 `RouteCollection` 사용 하 여 새 경로를 추가 하는 데 사용 되는 형식으로 관리 됩니다 `MapRoute` .</span><span class="sxs-lookup"><span data-stu-id="04f07-114">In the preceding code, the route table is managed by the `RouteCollection` type, which is used to add new routes with `MapRoute`.</span></span> <span data-ttu-id="04f07-115">경로 이름은로 지정 되며, 컨트롤러, 작업, 영역 및 기타 자리 표시자에 대 한 매개 변수를 포함할 수 있는 경로 문자열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-115">Routes are named and include a route string, which can include parameters for controllers, actions, areas, and other placeholders.</span></span> <span data-ttu-id="04f07-116">앱이 표준 규칙을 따르는 경우이 규칙에 대 한 모든 예외를 제외 하 고 추가 경로를 사용 하 여이 규칙의 모든 작업을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-116">If an app follows a standard convention, most of its actions can be handled by this single default route, with any exceptions to this convention configured using additional routes.</span></span>

### <a name="attribute-routing-in-aspnet-mvc"></a><span data-ttu-id="04f07-117">ASP.NET MVC의 특성 라우팅</span><span class="sxs-lookup"><span data-stu-id="04f07-117">Attribute routing in ASP.NET MVC</span></span>

<span data-ttu-id="04f07-118">해당 작업으로 정의 된 경로는 외부 위치에 정의 된 경로 보다 검색 하 고 이유가 더 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-118">Routes that are defined with their actions may be easier to discover and reason about than routes defined in an external location.</span></span> <span data-ttu-id="04f07-119">특성 라우팅을 사용 하 여 개별 작업 메서드는 특성으로 정의 된 경로를 가질 수 있습니다 `[Route]` .</span><span class="sxs-lookup"><span data-stu-id="04f07-119">Using attribute routing, an individual action method can have its route defined with a `[Route]` attribute:</span></span>

```csharp
public class ProductsController
{
    [Route("products")]
    public ActionResult Index()
    {
        return View();
    }

    [Route("products/{id}")]
    public ActionResult Details(int id)
    {
        return View();
    }
}
```

<span data-ttu-id="04f07-120">[ASP.NET MVC 5의 특성 라우팅은](https://devblogs.microsoft.com/aspnet/attribute-routing-in-asp-net-mvc-5/) 컨트롤러 수준 (및 해당 컨트롤러 내의 모든 작업에 적용 됨)에서 추가 될 수 있는 기본값과 접두사도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-120">[Attribute routing in ASP.NET MVC 5](https://devblogs.microsoft.com/aspnet/attribute-routing-in-asp-net-mvc-5/) also supports defaults and prefixes, which can be added at the controller level (and which are applied to all actions within that controller).</span></span> <span data-ttu-id="04f07-121">자세한 내용은 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04f07-121">Refer to the documentation for details.</span></span>

<span data-ttu-id="04f07-122">특성 라우팅을 설정 하려면 기본 경로 테이블 구성에 한 줄을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-122">Setting up attribute routing requires adding one line to the default route table configuration:</span></span>

```csharp
routes.MapMvcAttributeRoutes();
```

<span data-ttu-id="04f07-123">특성 라우팅은 기본 제공 및 사용자 지정의 경로 제약 조건을 활용할 수 있으며 특성을 사용 하 여 명명 된 경로와 영역을 지원 합니다 `[RouteArea]` .</span><span class="sxs-lookup"><span data-stu-id="04f07-123">Attribute routing can take advantage of route constraints, both built-in and custom, and supports named routes and areas using the `[RouteArea]` attribute.</span></span> <span data-ttu-id="04f07-124">앱에서 영역을 사용 하는 경우 하나 이상의 줄을 추가 하 여 경로 등록 코드에서 해당 영역에 대 한 지원을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-124">If your app uses areas, you'll need to configure support for them in your route registration code by adding one more line:</span></span>

```csharp
routes.MapMvcAttributeRoutes();

AreaRegistration.RegisterAllAreas();
```

### <a name="attribute-routing-in-aspnet-web-api-2"></a><span data-ttu-id="04f07-125">ASP.NET Web API 2에서 특성 라우팅</span><span class="sxs-lookup"><span data-stu-id="04f07-125">Attribute routing in ASP.NET Web API 2</span></span>

<span data-ttu-id="04f07-126">[ASP.NET Web API 2의 특성 라우팅은](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2) ASP.NET MVC 5에서 라우팅과 비슷하지만 사소한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-126">[Attribute routing in ASP.NET Web API 2](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2) is similar to routing in ASP.NET MVC 5, with minor differences.</span></span> <span data-ttu-id="04f07-127">웹 API 2 구성은 일반적으로 앱을 시작 하는 동안 호출 되는 자체 클래스에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-127">Configuring Web API 2 is typically done in its own class, which is called during app startup.</span></span> <span data-ttu-id="04f07-128">특성 라우팅 구성은이 클래스에서 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-128">Attribute routing configuration is handled in this class:</span></span>

```csharp
public static class WebApiConfig
{
    public static void Register(HttpConfiguration config)
    {
        // Attribute routing.
        config.MapHttpAttributeRoutes();

        // Convention-based routing.
        config.Routes.MapHttpRoute(
            name: "DefaultApi",
            routeTemplate: "api/{controller}/{id}",
            defaults: new { id = RouteParameter.Optional }
        );
    }
}
```

<span data-ttu-id="04f07-129">위의 코드에 표시 된 것 처럼 특성 라우팅은 웹 API 앱에서 규칙 기반 라우팅과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-129">As shown in the preceding code, attribute routing may be combined with convention-based routing in Web API apps.</span></span>

<span data-ttu-id="04f07-130">특성 라우팅 외에도 [ASP.NET Web API](/aspnet/web-api/overview/web-api-routing-and-actions/routing-and-action-selection) 는 HTTP 메서드 (예: GET 또는 POST), `{action}` 경로의 자리 표시자 (있는 경우) 및 동작의 매개 변수를 기반으로 호출할 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-130">In addition to attribute routing, [ASP.NET Web API chooses which action to call](/aspnet/web-api/overview/web-api-routing-and-actions/routing-and-action-selection) based on the HTTP method (for example, GET or POST), the `{action}` placeholder in a route (if any), and parameters of the action.</span></span> <span data-ttu-id="04f07-131">대부분의 경우 작업 이름을 "Get" 또는 "Post"로 지정 하면 해당 HTTP 메서드를 일치 시킬 수 있기 때문에 작업 이름이 일치 하는지 여부를 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-131">In many cases, the name of the action will help determine whether it's matched, since prefixing the action name with "Get" or "Post" is used to match the appropriate HTTP method to it.</span></span> <span data-ttu-id="04f07-132">또는와 같은 적절 한 HTTP 메서드 특성을 사용 하 여 작업을 데코레이팅 할 수 있습니다 `[HttpGet]` .이 경우 http 메서드가 접두사로 붙지 않은 작업 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-132">Alternatively, actions can be decorated with an appropriate HTTP method attribute, like `[HttpGet]`, allowing the use of action names that aren't prefixed with an HTTP method.</span></span>

```csharp
public class ProductsController : ApiController
{
    // matched by name and (lack of) parameters
    public IEnumerable<Product> GetAll() { }

    // matched by GET and string parameter
    [HttpGet]
    public IEnumerable<Product> FindProductsByName(string name) { }
}
```

<span data-ttu-id="04f07-133">위의 컨트롤러가 지정 된 경우 작업과 일치 하는 HTTP GET 요청입니다 `localhost:123/products/` `GetAll` .</span><span class="sxs-lookup"><span data-stu-id="04f07-133">Given the above controller, an HTTP GET request to `localhost:123/products/` matches the `GetAll` action.</span></span> <span data-ttu-id="04f07-134">`localhost:123/products?name=ardalis`작업과 일치 하는 HTTP GET 요청 `FindProductsByName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-134">An HTTP GET request to `localhost:123/products?name=ardalis` matches the `FindProductsByName` action.</span></span>

## <a name="routing-in-aspnet-core-31"></a><span data-ttu-id="04f07-135">ASP.NET Core 3.1의 라우팅</span><span class="sxs-lookup"><span data-stu-id="04f07-135">Routing in ASP.NET Core 3.1</span></span>

<span data-ttu-id="04f07-136">ASP.NET Core에서 라우팅은 라우팅 미들웨어에 의해 처리 되 고,이는 들어오는 요청의 Url과 작업 또는 다른 끝점을 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-136">In ASP.NET Core, routing is handled by routing middleware, which matches the URLs of incoming requests to actions or other endpoints.</span></span> <span data-ttu-id="04f07-137">컨트롤러 작업은 일반적으로 라우트된 경로 또는 특성 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-137">Controller actions are either conventionally routed or attribute-routed.</span></span> <span data-ttu-id="04f07-138">기존 라우팅은 ASP.NET MVC 및 Web API에서 사용 되는 경로 테이블 방법과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-138">Conventional routing is similar to the route table approach used in ASP.NET MVC and Web API.</span></span> <span data-ttu-id="04f07-139">기본, 특성 또는 둘 다를 사용 하 든 관계 없이 라우팅 미들웨어를 사용 하도록 앱을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-139">Whether you're using conventional, attribute, or both, you need to configure your app to use the routing middleware.</span></span> <span data-ttu-id="04f07-140">미들웨어를 사용 하려면 메서드에 다음 코드를 추가 합니다 `Startup.Configure` .</span><span class="sxs-lookup"><span data-stu-id="04f07-140">To use the middleware, add the following code to your `Startup.Configure` method:</span></span>

```csharp
app.UseRouting();
```

### <a name="conventional-routing"></a><span data-ttu-id="04f07-141">규칙 기반 라우팅</span><span class="sxs-lookup"><span data-stu-id="04f07-141">Conventional routing</span></span>

<span data-ttu-id="04f07-142">기본 라우팅을 사용 하면 들어오는 Url을 앱의 *끝점과* 일치 시키는 데 사용할 규칙을 하나 이상 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-142">With conventional routing, you set up one or more conventions that will be used to match incoming URLs to *endpoints* in the app.</span></span> <span data-ttu-id="04f07-143">ASP.NET Core에서 이러한 끝점은 ASP.NET MVC 또는 Web API와 같은 컨트롤러 작업 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-143">In ASP.NET Core, these endpoints may be controller actions, like in ASP.NET MVC or Web API.</span></span> <span data-ttu-id="04f07-144">끝점은 Razor Pages, 상태 검사 또는 SignalR 허브가 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-144">The endpoints could also be Razor Pages, Health Checks, or SignalR hubs.</span></span> <span data-ttu-id="04f07-145">이러한 모든 라우팅 가능 기능은 끝점을 사용 하 여 비슷한 방식으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-145">All of these routable features are configured in a similar fashion using endpoints:</span></span>

```csharp
// in Startup.Configure()
app.UseEndpoints(endpoints =>
{
    endpoints.MapHealthChecks("/healthz").RequireAuthorization();
    endpoints.MapControllerRoute(
        name: "default",
        pattern: "{controller=Home}/{action=Index}/{id?}");
    endpoints.MapRazorPages();
});
```

<span data-ttu-id="04f07-146">위의 코드를 사용 `UseRouting` 하 여 상태 검사, 컨트롤러 및 Razor Pages을 비롯 한 다양 한 끝점을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-146">The preceding code is used (in addition to `UseRouting`) to configure various endpoints, including Health Checks, controllers, and Razor Pages.</span></span> <span data-ttu-id="04f07-147">컨트롤러의 경우 위의 구성은 `{controller}/{action}/{id?}` 첫 번째 버전의 ASP.NET MVC 이후에 권장 되는 매우 일반적인 패턴 인 기본 라우팅 규칙을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-147">For controllers, the above configuration specifies a default routing convention, which is the fairly standard `{controller}/{action}/{id?}` pattern that's been recommended since the first versions of ASP.NET MVC.</span></span>

### <a name="attribute-routing"></a><span data-ttu-id="04f07-148">특성 라우팅</span><span class="sxs-lookup"><span data-stu-id="04f07-148">Attribute routing</span></span>

<span data-ttu-id="04f07-149">ASP.NET Core의 특성 라우팅은 컨트롤러에서 라우팅을 구성 하는 데 선호 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-149">Attribute routing in ASP.NET Core is the preferred approach for configuring routing in controllers.</span></span> <span data-ttu-id="04f07-150">Api를 작성 하는 경우에는 `[ApiController]` 컨트롤러에 특성을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-150">If you're building APIs, the `[ApiController]` attribute should be applied to your controllers.</span></span> <span data-ttu-id="04f07-151">무엇 보다도이 특성은 이러한 컨트롤러 클래스의 작업에 특성 라우팅을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-151">Among other things, this attribute requires the use of attribute routing for actions in such controller classes.</span></span>

<span data-ttu-id="04f07-152">ASP.NET Core의 특성 라우팅은 ASP.NET MVC 및 Web API에서 비슷하게 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-152">Attribute routing in ASP.NET Core behaves similarly in ASP.NET MVC and Web API.</span></span> <span data-ttu-id="04f07-153">그러나 특성을 지 원하는 것 외에 `[Route]` 도 경로 정보를 HTTP 메서드 특성의 일부로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-153">In addition to supporting the `[Route]` attribute, however, route information can also be specified as part of the HTTP method attribute:</span></span>

```csharp
[HttpGet("api/products/{id}")]
public async ActionResult<Product> Details(int id)
{
    // ...
}
```

<span data-ttu-id="04f07-154">이전 버전과 마찬가지로 자리 표시자를 사용 하 여 기본 경로를 지정 하 고이 경로를 컨트롤러 클래스 수준 또는 기본 클래스에도 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-154">As with previous versions, you can specify a default route with placeholders, and add this at the controller class level or even on a base class.</span></span> <span data-ttu-id="04f07-155">`[Route]`이러한 모든 경우에 동일한 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-155">You use the same `[Route]` attribute for all of these cases.</span></span> <span data-ttu-id="04f07-156">예를 들어 기본 API 컨트롤러 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04f07-156">For example, a base API controller class might look like this:</span></span>

```csharp
[Route("api/{controller}/{action}/{id?:int}")]
public abstract class BaseApiController : ControllerBase, IApiController
{
    // ...
}
```

<span data-ttu-id="04f07-157">이 특성을 사용 하 여이 형식에서 상속 하는 클래스는 Url을 컨트롤러 이름, 작업 이름 및 선택적 정수 매개 변수를 기반으로 하는 작업으로 라우팅합니다 `id` .</span><span class="sxs-lookup"><span data-stu-id="04f07-157">Using this attribute, classes inheriting from this type would route URLs to actions based on the controller name, action name, and an optional integer `id` parameter.</span></span>

## <a name="references"></a><span data-ttu-id="04f07-158">참조</span><span class="sxs-lookup"><span data-stu-id="04f07-158">References</span></span>

- [<span data-ttu-id="04f07-159">ASP.NET MVC 라우팅 개요</span><span class="sxs-lookup"><span data-stu-id="04f07-159">ASP.NET MVC Routing Overview</span></span>](/aspnet/mvc/overview/older-versions-1/controllers-and-routing/asp-net-mvc-routing-overview-cs)
- [<span data-ttu-id="04f07-160">ASP.NET MVC 5에서 특성 라우팅</span><span class="sxs-lookup"><span data-stu-id="04f07-160">Attribute Routing in ASP.NET MVC 5</span></span>](https://devblogs.microsoft.com/aspnet/attribute-routing-in-asp-net-mvc-5/)
- [<span data-ttu-id="04f07-161">ASP.NET Web API 2에서 특성 라우팅</span><span class="sxs-lookup"><span data-stu-id="04f07-161">Attribute routing in ASP.NET Web API 2</span></span>](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2)
- [<span data-ttu-id="04f07-162">ASP.NET Web API에서 라우팅 및 작업 선택</span><span class="sxs-lookup"><span data-stu-id="04f07-162">Routing and Action Selection in ASP.NET Web API</span></span>](/aspnet/web-api/overview/web-api-routing-and-actions/routing-and-action-selection)
- [<span data-ttu-id="04f07-163">ASP.NET Core에서 라우팅</span><span class="sxs-lookup"><span data-stu-id="04f07-163">Routing in ASP.NET Core</span></span>](/aspnet/core/fundamentals/routing)
- [<span data-ttu-id="04f07-164">ASP.NET Core MVC에서 컨트롤러 작업으로 라우팅</span><span class="sxs-lookup"><span data-stu-id="04f07-164">Routing to controller actions in ASP.NET Core MVC</span></span>](/aspnet/core/mvc/controllers/routing)

>[!div class="step-by-step"]
><span data-ttu-id="04f07-165">[이전](configuration-differences.md)
>[다음](comparing-razor-pages-aspnet-mvc.md)</span><span class="sxs-lookup"><span data-stu-id="04f07-165">[Previous](configuration-differences.md)
[Next](comparing-razor-pages-aspnet-mvc.md)</span></span>
