---
title: 앱 시작
description: 앱에 대 한 시작 논리를 정의 하는 방법을 알아봅니다.
author: csharpfritz
ms.author: jefritz
ms.date: 11/20/2020
ms.openlocfilehash: d812079f84f67409334d07c4c10c5577446503be
ms.sourcegitcommit: 2f485e721f7f34b87856a51181b5b56624b31fd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "96509704"
---
# <a name="app-startup"></a><span data-ttu-id="5a17b-103">앱 시작</span><span class="sxs-lookup"><span data-stu-id="5a17b-103">App startup</span></span>

<span data-ttu-id="5a17b-104">ASP.NET 용으로 작성 된 응용 프로그램에는 일반적으로 `global.asax.cs` `Application_Start` 구성 되 고 HTML 렌더링과 .net 처리에 사용할 수 있는 서비스를 제어 하는 이벤트를 정의 하는 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-104">Applications that are written for ASP.NET typically have a `global.asax.cs` file that defines the `Application_Start` event that controls which services are configured and made available for both HTML rendering and .NET processing.</span></span> <span data-ttu-id="5a17b-105">이 장에서는 ASP.NET Core 및 Blazor Server와 약간 어떻게 다른 지 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-105">This chapter looks at how things are slightly different with ASP.NET Core and Blazor Server.</span></span>

## <a name="application_start-and-web-forms"></a><span data-ttu-id="5a17b-106">Application_Start 및 Web Forms</span><span class="sxs-lookup"><span data-stu-id="5a17b-106">Application_Start and Web Forms</span></span>

<span data-ttu-id="5a17b-107">기본 web forms `Application_Start` 메서드는 여러 구성 작업을 처리 하기 위해 몇 년 이상 효율적으로 성장 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-107">The default web forms `Application_Start` method has grown in purpose over years to handle many configuration tasks.</span></span>  <span data-ttu-id="5a17b-108">이제 Visual Studio 2019의 기본 템플릿이 있는 새로운 web forms 프로젝트에는 이제 다음과 같은 구성 논리가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-108">A fresh web forms project with the default template in Visual Studio 2019 now contains the following configuration logic:</span></span>

- <span data-ttu-id="5a17b-109">`RouteConfig` -응용 프로그램 URL 라우팅</span><span class="sxs-lookup"><span data-stu-id="5a17b-109">`RouteConfig` - Application URL routing</span></span>
- <span data-ttu-id="5a17b-110">`BundleConfig` -CSS 및 JavaScript 묶음 및 축소</span><span class="sxs-lookup"><span data-stu-id="5a17b-110">`BundleConfig` - CSS and JavaScript bundling and minification</span></span>

<span data-ttu-id="5a17b-111">이러한 개별 파일은 모두 폴더에 상주 `App_Start` 하며 응용 프로그램을 시작할 때 한 번만 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-111">Each of these individual files resides in the `App_Start` folder and run only once at the start of our application.</span></span>  <span data-ttu-id="5a17b-112">`RouteConfig` 기본 프로젝트 템플릿에서는 `FriendlyUrlSettings` 응용 프로그램 url이 파일 확장명을 생략할 수 있도록 web forms 용를 추가 합니다 `.ASPX` .</span><span class="sxs-lookup"><span data-stu-id="5a17b-112">`RouteConfig` in the default project template adds the `FriendlyUrlSettings` for web forms to allow application URLs to omit the `.ASPX` file extension.</span></span>  <span data-ttu-id="5a17b-113">기본 템플릿에는 페이지에 대 한 영구 HTTP 리디렉션 상태 코드 (HTTP 301)를 `.ASPX` 확장명이 없는 파일 이름으로 친숙 한 URL에 제공 하는 지시문도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-113">The default template also contains a directive that provides permanent HTTP redirect status codes (HTTP 301) for the `.ASPX` pages to the friendly URL with the file name that omits the extension.</span></span>

<span data-ttu-id="5a17b-114">ASP.NET Core 및 Blazor를 사용 하면 이러한 메서드를 간소화 하 고 클래스로 통합 `Startup` 하거나 일반적인 웹 기술에 대해 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-114">With ASP.NET Core and Blazor, these methods are either simplified and consolidated into the `Startup` class or they are eliminated in favor of common web technologies.</span></span>

## <a name="blazor-server-startup-structure"></a><span data-ttu-id="5a17b-115">Blazor 서버 시작 구조</span><span class="sxs-lookup"><span data-stu-id="5a17b-115">Blazor Server Startup Structure</span></span>

<span data-ttu-id="5a17b-116">Blazor 서버 응용 프로그램은 ASP.NET Core 3.0 이상 버전 위에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-116">Blazor Server applications reside on top of an ASP.NET Core 3.0 or later version.</span></span>  <span data-ttu-id="5a17b-117">ASP.NET Core 웹 응용 프로그램은 `Startup.cs` 응용 프로그램의 루트 폴더에 있는 클래스의 메서드 쌍을 통해 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-117">ASP.NET Core web applications are configured through a pair of methods in the `Startup.cs` class on the root folder of the application.</span></span>  <span data-ttu-id="5a17b-118">시작 클래스의 기본 콘텐츠는 아래에 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-118">The Startup class's default content is listed below</span></span>

```csharp
public class Startup
{
  public Startup(IConfiguration configuration)
  {
    Configuration = configuration;
  }

  public IConfiguration Configuration { get; }

  // This method gets called by the runtime. Use this method to add services to the container.
  // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
  public void ConfigureServices(IServiceCollection services)
  {
    services.AddRazorPages();
    services.AddServerSideBlazor();
    services.AddSingleton<WeatherForecastService>();
  }

  // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
  public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
  {
    if (env.IsDevelopment())
    {
      app.UseDeveloperExceptionPage();
    }
    else
    {
      app.UseExceptionHandler("/Error");
      // The default HSTS value is 30 days. You may want to change this for production scenarios, see https://aka.ms/aspnetcore-hsts.
      app.UseHsts();
    }

    app.UseHttpsRedirection();
    app.UseStaticFiles();

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
      endpoints.MapBlazorHub();
      endpoints.MapFallbackToPage("/_Host");
   });
  }
 }
```

<span data-ttu-id="5a17b-119">ASP.NET Core의 나머지와 마찬가지로 Startup 클래스는 종속성 주입 원칙을 사용 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-119">Like the rest of ASP.NET Core, the Startup class is created with dependency injection principles.</span></span>  <span data-ttu-id="5a17b-120">는 `IConfiguration` 구성 중에 나중에 액세스할 수 있도록 공용 속성에서 생성자 및 스 태 시에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-120">The `IConfiguration` is provided to the constructor and stashed in a public property for later access during configuration.</span></span>

<span data-ttu-id="5a17b-121">`ConfigureServices`ASP.NET Core에 도입 된 메서드를 사용 하면 프레임 워크의 기본 제공 종속성 주입 컨테이너에 대해 다양 한 ASP.NET Core framework 서비스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-121">The `ConfigureServices` method introduced in ASP.NET Core allows for the various ASP.NET Core framework services to be configured for the framework's built-in dependency injection container.</span></span>  <span data-ttu-id="5a17b-122">다양 한 `services.Add*` 방법으로 인증, razor 페이지, MVC 컨트롤러 라우팅, SignalR 및 Blazor 서버 상호 작용과 같은 기능을 사용할 수 있는 서비스를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-122">The various `services.Add*` methods add services that enable features such as authentication, razor pages, MVC controller routing, SignalR, and Blazor Server interactions among many others.</span></span>  <span data-ttu-id="5a17b-123">이 메서드는 ASPX, ASCX, .ASHX 및 ASMX 파일의 구문 분석과 처리가 web.config 구성 파일에서 ASP.NET를 참조 하 여 정의 되었으므로 web forms에서 필요 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-123">This method was not needed in web forms, as the parsing and handling of the ASPX, ASCX, ASHX, and ASMX files were defined by referencing ASP.NET in the web.config configuration file.</span></span>  <span data-ttu-id="5a17b-124">ASP.NET Core의 종속성 주입에 대 한 자세한 내용은 [온라인 설명서](/aspnet/core/fundamentals/dependency-injection)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-124">More information about dependency injection in ASP.NET Core is available in the [online documentation](/aspnet/core/fundamentals/dependency-injection).</span></span>

<span data-ttu-id="5a17b-125">`Configure`메서드는 ASP.NET Core 하는 HTTP 파이프라인의 개념을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-125">The `Configure` method introduces the concept of the HTTP pipeline to ASP.NET Core.</span></span>  <span data-ttu-id="5a17b-126">이 메서드에서는 응용 프로그램에 전송 된 모든 요청을 처리 하는 [미들웨어](middleware.md) 를 위쪽에서 아래쪽으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-126">In this method, we declare from top to bottom the [Middleware](middleware.md) that will handle every request sent to our application.</span></span> <span data-ttu-id="5a17b-127">기본 구성의 이러한 기능 중 대부분은 web forms 구성 파일에 흩어져 있으며 이제는 쉽게 참조할 수 있도록 한 곳에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-127">Most of these features in the default configuration were scattered across the web forms configuration files and are now in one place for ease of reference.</span></span>

<span data-ttu-id="5a17b-128">더 이상 파일에 저장 된 사용자 지정 오류 페이지의 구성이 `web.config` 아니라, 이제 응용 프로그램 환경에 레이블이 지정 되지 않은 경우 항상 표시 되도록 구성 됩니다 `Development` .</span><span class="sxs-lookup"><span data-stu-id="5a17b-128">No longer is the configuration of the custom error page placed in a `web.config` file, but now is configured to always be shown if the application environment is not labeled `Development`.</span></span>  <span data-ttu-id="5a17b-129">또한 ASP.NET Core 응용 프로그램은 이제 메서드 호출을 통해 기본적으로 TLS를 사용 하 여 보안 페이지를 제공 하도록 구성 됩니다 `UseHttpsRedirection` .</span><span class="sxs-lookup"><span data-stu-id="5a17b-129">Additionally, ASP.NET Core applications are now configured to serve secure pages with TLS by default with the `UseHttpsRedirection` method call.</span></span>

<span data-ttu-id="5a17b-130">그런 다음 예기치 않은 구성 방법이에 나열 됩니다 `UseStaticFiles` .</span><span class="sxs-lookup"><span data-stu-id="5a17b-130">Next, an unexpected configuration method is listed to `UseStaticFiles`.</span></span>  <span data-ttu-id="5a17b-131">ASP.NET Core에서는 정적 파일에 대 한 요청 (예: JavaScript, CSS, 이미지 파일)에 대 한 지원을 명시적으로 사용 하도록 설정 해야 하며, 앱의 *wwwroot* 폴더에 있는 파일만 기본적으로 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-131">In ASP.NET Core, support for requests for static files (like JavaScript, CSS, and image files) must be explicitly enabled, and only files in the app's *wwwroot* folder are publicly addressable by default.</span></span>

<span data-ttu-id="5a17b-132">다음 줄은 web forms에서 구성 옵션 중 하나를 복제 하는 첫 번째입니다 `UseRouting` .</span><span class="sxs-lookup"><span data-stu-id="5a17b-132">The next line is the first that replicates one of the configuration options from web forms: `UseRouting`.</span></span>  <span data-ttu-id="5a17b-133">이 메서드는 파이프라인에 ASP.NET Core 라우터를 추가 하 고 여기에서 구성 하거나 라우팅을 고려할 수 있는 개별 파일에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-133">This method adds the ASP.NET Core router to the pipeline and it can be either configured here or in the individual files that it can consider routing to.</span></span>  <span data-ttu-id="5a17b-134">라우팅 구성에 대 한 자세한 내용은 [라우팅 섹션](pages-routing-layouts.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-134">More information about routing configuration can be found in the [Routing section](pages-routing-layouts.md).</span></span>

<span data-ttu-id="5a17b-135">이 메서드의 마지막 문은 ASP.NET Core 수신 대기 하는 끝점을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-135">The final statement in this method defines the endpoints that ASP.NET Core is listening on.</span></span>  <span data-ttu-id="5a17b-136">이러한 경로는 웹 서버에서 액세스할 수 있고 .NET에서 처리 되 고 사용자에 게 반환 되는 일부 콘텐츠를 받을 수 있는 웹 액세스 가능한 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-136">These routes are the web accessible locations that you can access on the web server and receive some content handled by .NET and returned to you.</span></span>  <span data-ttu-id="5a17b-137">첫 번째 항목은 `MapBlazorHub` Blazor 구성 요소의 상태 및 렌더링이 처리 되는 서버에 실시간 및 영구 연결을 제공 하는 데 사용할 SignalR hub를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-137">The first entry, `MapBlazorHub` configures a SignalR hub for use in providing the real-time and persistent connection to the server where the state and rendering of Blazor components is handled.</span></span>  <span data-ttu-id="5a17b-138">`MapFallbackToPage`메서드 호출은 Blazor 응용 프로그램을 시작 하는 페이지의 웹 액세스 가능 위치를 나타내며, 클라이언트 쪽에서의 딥 링크 요청을 처리 하도록 응용 프로그램을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-138">The `MapFallbackToPage` method call indicates the web-accessible location of the page that starts the Blazor application and also configures the application to handle deep-linking requests from the client-side.</span></span>  <span data-ttu-id="5a17b-139">브라우저를 열고 기본 프로젝트 템플릿 등의 응용 프로그램에서 Blazor 처리 된 경로를 직접 탐색 하는 경우이 기능이 작동 하는 것을 볼 수 있습니다 `/counter` .</span><span class="sxs-lookup"><span data-stu-id="5a17b-139">You will see this feature at work if you open a browser and navigate directly to Blazor handled route in your application, such as `/counter` in the default project template.</span></span> <span data-ttu-id="5a17b-140">요청은 *_Host* 에 의해 처리 되 고,이 페이지에서 Blazor 라우터를 실행 하 고 카운터 페이지를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-140">The request gets handled by the *_Host.cshtml* fallback page, which then runs the Blazor router and renders the counter page.</span></span>

## <a name="upgrading-the-bundleconfig-process"></a><span data-ttu-id="5a17b-141">BundleConfig 프로세스 업그레이드</span><span class="sxs-lookup"><span data-stu-id="5a17b-141">Upgrading the BundleConfig Process</span></span>

<span data-ttu-id="5a17b-142">CSS 스타일 시트 및 JavaScript 파일과 같은 자산을 번들로 제공 하는 기술은 신속 하 게 진화 하는 도구와 이러한 리소스를 관리 하는 기술을 제공 하는 다른 기술을 통해 크게 발전 했습니다</span><span class="sxs-lookup"><span data-stu-id="5a17b-142">Technologies for bundling assets like CSS stylesheets and JavaScript files have evolved significantly, with other technologies providing quickly evolving tools and techniques for managing these resources.</span></span>  <span data-ttu-id="5a17b-143">이를 위해 Grunt/Gulp/WebPack과 같은 노드 명령줄 도구를 사용 하 여 정적 자산을 패키지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-143">To this end, we recommend using a Node command-line tool such as Grunt / Gulp / WebPack to package your static assets.</span></span>

<span data-ttu-id="5a17b-144">Grunt, Gulp 및 WebPack 명령줄 도구와 연결 된 구성은 응용 프로그램에 추가할 수 있으며, ASP.NET Core 응용 프로그램 빌드 프로세스 중에 이러한 파일을 자동으로 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-144">The Grunt, Gulp, and WebPack command-line tools and their associated configurations can be added to your application and ASP.NET Core will quietly ignore those files during the application build process.</span></span>  <span data-ttu-id="5a17b-145">`Target`Gulp 스크립트와 `min` 해당 스크립트 내부의 대상을 트리거하는 다음과 유사한 구문을 사용 하 여 프로젝트 파일 내에를 추가 하 여 작업을 실행 하는 호출을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-145">You can add a call to run their tasks by adding a `Target` inside your project file with syntax similar to the following that would trigger a gulp script and the `min` target inside that script</span></span>

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="gulp min" />
</Target>
```

<span data-ttu-id="5a17b-146">CSS 및 JavaScript 파일을 관리 하기 위한 두 전략에 대 한 자세한 내용은 [ASP.NET Core 설명서의 번들 및 미니 고 정적 자산](/aspnet/core/client-side/bundling-and-minification) 에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a17b-146">More details about both strategies to manage your CSS and JavaScript files are available in the [Bundle and minify static assets in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification) documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5a17b-147">[이전](project-structure.md)
>[다음](components.md)</span><span class="sxs-lookup"><span data-stu-id="5a17b-147">[Previous](project-structure.md)
[Next](components.md)</span></span>
