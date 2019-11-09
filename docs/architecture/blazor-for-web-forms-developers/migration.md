---
title: ASP.NET Web Forms에서 Blazor로 마이그레이션
description: 기존 ASP.NET Web Forms 앱을 Blazor로 마이그레이션하는 방법에 대해 알아봅니다.
author: twsouthwick
ms.author: tasou
ms.date: 09/19/2019
ms.openlocfilehash: b6604e000eaf79bcd8da15d72a3d85713c620851
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73842040"
---
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a>ASP.NET Web Forms에서 Blazor로 마이그레이션

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

ASP.NET Web Forms에서 Blazor로 코드 베이스를 마이그레이션하는 작업은 계획을 수행 해야 하는 시간이 많이 걸리는 작업입니다. 이 장에서는 프로세스를 간략하게 설명 합니다. 쉽게 전환할 수 있는 것은 앱이 *N 계층* 아키텍처를 준수 하는지 확인 하는 것입니다. 즉, 앱 모델 (이 경우 Web Forms)은 비즈니스 논리와는 별개입니다. 이러한 계층의 논리적 분리를 통해 .NET Core 및 Blazor로 이동 해야 하는 것을 명확 하 게 파악할 수 있습니다.

이 예제에서는 [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) 에서 사용할 수 있는 eShop 앱을 사용 합니다. eShop는 양식 항목 및 유효성 검사를 통해 CRUD 기능을 제공 하는 카탈로그 서비스입니다.

작업 중인 앱을 Blazor로 마이그레이션해야 하는 이유는 무엇 인가요? 많은 시간이 필요 하지 않습니다. ASP.NET Web Forms는 계속 해 서 많은 년 동안 지원 됩니다. 그러나 Blazor에서 제공 하는 대부분의 기능은 마이그레이션된 앱 에서만 지원 됩니다. 이러한 기능은 다음과 같습니다.

- `Span<T>`와 같은 프레임 워크의 성능 향상
- Weasembomas를 실행 하는 기능
- Linux 및 macOS에 대 한 플랫폼 간 지원
- 다른 앱에 영향을 주지 않고 앱 로컬 배포 또는 공유 프레임 워크 배포

이러한 기능 또는 다른 새로운 기능을 충분히 사용할 수 있는 경우 앱 마이그레이션에 값이 있을 수 있습니다. 마이그레이션은 다른 셰이프를 사용할 수 있습니다. 전체 앱 이거나 변경 내용이 필요한 특정 끝점만 될 수 있습니다. 마이그레이션을 결정 하는 것은 궁극적으로 개발자가 해결할 비즈니스 문제에 따라 달라 집니다.

## <a name="server-side-versus-client-side-hosting"></a>서버 쪽 및 클라이언트 쪽 호스팅

[호스팅 모델](hosting-models.md) 챕터에서 설명한 대로 Blazor 앱은 서버 쪽 및 클라이언트 쪽의 두 가지 방법으로 호스팅될 수 있습니다. 서버 쪽 모델에서는 ASP.NET Core SignalR 연결을 사용 하 여 서버에서 실제 코드를 실행 하는 동안 DOM 업데이트를 관리 합니다. 클라이언트 쪽 모델은 브라우저 내에서 Weasembmbas로 실행 되며 서버 연결이 필요 하지 않습니다. 특정 앱에 가장 적합 한 여러 가지 차이점이 있습니다.

- WebAssembly로 실행은 아직 개발 중 이며 현재 시간에 모든 기능 (예: 스레딩)을 지원 하지 않을 수 있습니다.
- 클라이언트와 서버 간의 통신을 번잡 하면 서버 쪽 모드에서 대기 시간이 발생할 수 있습니다.
- 데이터베이스 및 내부 또는 보호 된 서비스에 대 한 액세스에는 클라이언트 쪽 호스팅을 사용 하는 별도의 서비스가 필요 합니다.

작성 시점에 서버 쪽 모델은 Web Forms 보다 더 유사 합니다. 이 챕터의 대부분은 프로덕션 준비가 완료 된 서버 쪽 호스팅 모델을 중심으로 설명 합니다.

## <a name="create-a-new-project"></a>새 프로젝트 만들기

이 초기 마이그레이션 단계는 새 프로젝트를 만드는 것입니다. 이 프로젝트 형식은 .NET Core의 SDK 스타일 프로젝트를 기반으로 하며 이전 프로젝트 형식에서 사용 된 대부분의 상용구를 간소화 합니다. 자세한 내용은 [프로젝트 구조](project-structure.md)의 챕터를 참조 하세요.

프로젝트를 만든 후에는 이전 프로젝트에서 사용 된 라이브러리를 설치 합니다. 이전 Web Forms 프로젝트에서 *패키지 .config* 파일을 사용 하 여 필요한 NuGet 패키지를 나열 했을 수 있습니다. 새 SDK 스타일 프로젝트에서 *패키지 .config* 는 프로젝트 파일의 `<PackageReference>` 요소로 대체 되었습니다. 이 방법의 혜택은 모든 종속성이 전이적으로 설치 된다는 것입니다. 관심 있는 최상위 종속성만 나열 합니다.

사용 중인 많은 종속성은 Entity Framework 6 및 log4net를 포함 하 여 .NET Core에 사용할 수 있습니다. 사용할 수 있는 .NET Core 또는 .NET Standard 버전이 없는 경우에는 .NET Framework 버전이 자주 사용 될 수 있습니다. 진행 정도는 달라질 수 있습니다. .NET Core에서 사용할 수 없는 API를 사용 하면 런타임 오류가 발생 합니다. Visual Studio에서 이러한 패키지를 알려 줍니다. **솔루션 탐색기**의 프로젝트 **참조** 노드에 노란색 아이콘이 표시 됩니다.

Blazor 기반 eShop 프로젝트에서 설치 된 패키지를 볼 수 있습니다. 이전에는 *패키지 .config* 파일이 프로젝트에서 사용 되는 모든 패키지에 나열 되어 거의 50 줄의 파일을 생성 했습니다. *패키지 .config* 의 코드 조각은 다음과 같습니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<packages>
  ...
  <package id="Microsoft.ApplicationInsights.Agent.Intercept" version="2.4.0" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.DependencyCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.PerfCounterCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.Web" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer.TelemetryChannel" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls.Core" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.MSAjax" version="5.0.0" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.WebForms" version="5.0.0" targetFramework="net472" />
  ...
  <package id="System.Memory" version="4.5.1" targetFramework="net472" />
  <package id="System.Numerics.Vectors" version="4.4.0" targetFramework="net472" />
  <package id="System.Runtime.CompilerServices.Unsafe" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Channels" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Tasks.Extensions" version="4.5.1" targetFramework="net472" />
  <package id="WebGrease" version="1.6.0" targetFramework="net472" />
</packages>
```

`<packages>` 요소에는 필요한 모든 종속성이 포함 됩니다. 이러한 패키지는 필요에 따라서 포함 된 패키지를 식별 하기 어렵습니다. 일부 `<package>` 요소는 필요한 종속성의 요구 사항을 충족 하기 위해 간단히 나열 됩니다.

Blazor 프로젝트는 프로젝트 파일의 `<ItemGroup>` 요소 내에서 필요한 종속성을 나열 합니다.

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

Web Forms 개발자의 수명을 간소화 하는 NuGet 패키지 하나는 [Windows 호환 기능 팩](../../core/porting/windows-compat-pack.md)입니다. .NET Core는 플랫폼 간 이지만 일부 기능은 Windows 에서만 사용할 수 있습니다. Windows 관련 기능은 호환 기능 팩을 설치 하 여 사용할 수 있습니다. 이러한 기능의 예로는 레지스트리, WMI 및 디렉터리 서비스가 있습니다. 이 패키지는 약 2만 Api를 추가 하 고 이미 친숙 한 많은 서비스를 활성화 합니다. EShop 프로젝트에는 호환성 팩이 필요 하지 않습니다. 그러나 프로젝트에서 Windows 관련 기능을 사용 하는 경우 패키지는 마이그레이션 작업을 용이 하 게 합니다.

## <a name="enable-startup-process"></a>시작 프로세스 사용

Blazor에 대 한 시작 프로세스는 Web Forms에서 변경 되었으며 다른 ASP.NET Core 서비스에 대해 유사한 설정을 따릅니다. 호스팅된 서버측 Blazor 구성 요소는 일반적인 ASP.NET Core 앱의 일부로 실행 됩니다. Blazor 구성 요소는 Weasembmbomommbmbomomommbomomomomomoma를 사용 하 여 차이점은 구성 요소가 백 엔드 프로세스에서 별도의 서비스로 실행 되는 것입니다. 어느 쪽이 든 시작도 유사 합니다.

*Global.asax.cs* 파일은 Web Forms 프로젝트에 대 한 기본 시작 페이지입니다. EShop 프로젝트에서이 파일은 IoC (제어의 반전) 컨테이너를 구성 하 고 앱 또는 요청에 대 한 다양 한 수명 주기 이벤트를 처리 합니다. 이러한 이벤트 중 일부는 미들웨어를 사용 하 여 처리 됩니다 (예: `Application_BeginRequest`). 다른 이벤트에는 DI (종속성 주입)를 통해 특정 서비스를 재정의 해야 합니다.

예를 들어, eShop 용 *Global.asax.cs* 파일에는 다음 코드가 포함 되어 있습니다.

```csharp
public class Global : HttpApplication, IContainerProviderAccessor
{
    private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

    static IContainerProvider _containerProvider;
    IContainer container;

    public IContainerProvider ContainerProvider
    {
        get { return _containerProvider; }
    }

    protected void Application_Start(object sender, EventArgs e)
    {
        // Code that runs on app startup
        RouteConfig.RegisterRoutes(RouteTable.Routes);
        BundleConfig.RegisterBundles(BundleTable.Bundles);
        ConfigureContainer();
        ConfigDataBase();
    }

    /// <summary>
    /// Track the machine name and the start time for the session inside the current session
    /// </summary>
    protected void Session_Start(Object sender, EventArgs e)
    {
        HttpContext.Current.Session["MachineName"] = Environment.MachineName;
        HttpContext.Current.Session["SessionStartTime"] = DateTime.Now;
    }

    /// <summary>
    /// http://docs.autofac.org/en/latest/integration/webforms.html
    /// </summary>
    private void ConfigureContainer()
    {
        var builder = new ContainerBuilder();
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
        builder.RegisterModule(new ApplicationModule(mockData));
        container = builder.Build();
        _containerProvider = new ContainerProvider(container);
    }

    private void ConfigDataBase()
    {
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);

        if (!mockData)
        {
            Database.SetInitializer<CatalogDBContext>(container.Resolve<CatalogDBInitializer>());
        }
    }

    protected void Application_BeginRequest(object sender, EventArgs e)
    {
        //set the property to our new object
        LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper();

        LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo();

        _log.Debug("Application_BeginRequest");
    }
}
```

위의 파일은 서버 쪽 Blazor의 `Startup` 클래스가 됩니다.

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    public IConfiguration Configuration { get; }

    public IWebHostEnvironment Env { get; }

    // This method gets called by the runtime. Use this method to add services to the container.
    // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddRazorPages();
        services.AddServerSideBlazor();

        if (Configuration.GetValue<bool>("UseMockData"))
        {
            services.AddSingleton<ICatalogService, CatalogServiceMock>();
        }
        else
        {
            services.AddScoped<ICatalogService, CatalogService>();
            services.AddScoped<IDatabaseInitializer<CatalogDBContext>, CatalogDBInitializer>();
            services.AddSingleton<CatalogItemHiLoGenerator>();
            services.AddScoped(_ => new CatalogDBContext(Configuration.GetConnectionString("CatalogDBContext")));
        }
    }

    // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
    public void Configure(IApplicationBuilder app, ILoggerFactory loggerFactory)
    {
        loggerFactory.AddLog4Net("log4Net.xml");

        if (Env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
        else
        {
            app.UseExceptionHandler("/Home/Error");
        }

        // Middleware for Application_BeginRequest
        app.Use((ctx, next) =>
        {
            LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper(ctx);
            LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo(ctx);
            return next();
        });

        app.UseStaticFiles();

        app.UseRouting();

        app.UseEndpoints(endpoints =>
        {
            endpoints.MapBlazorHub();
            endpoints.MapFallbackToPage("/_Host");
        });

        ConfigDataBase(app);
    }

    private void ConfigDataBase(IApplicationBuilder app)
    {
        using (var scope = app.ApplicationServices.CreateScope())
        {
            var initializer = scope.ServiceProvider.GetService<IDatabaseInitializer<CatalogDBContext>>();

            if (initializer != null)
            {
                Database.SetInitializer(initializer);
            }
        }
    }
}
```

Web Forms에서 볼 수 있는 중요 한 변경 내용 중 하나는 DI의 우월성입니다. DI는 ASP.NET Core 설계에서 안내 하는 원칙입니다. ASP.NET Core framework의 거의 모든 측면에 대 한 사용자 지정을 지원 합니다. 여러 시나리오에 사용할 수 있는 기본 제공 서비스 공급자도 있습니다. 더 많은 사용자 지정이 필요한 경우 많은 커뮤니티 프로젝트에서 지원할 수 있습니다. 예를 들어 타사 DI 라이브러리 투자를 전달할 수 있습니다.

원래 eShop 앱에는 세션 관리에 대 한 몇 가지 구성이 있습니다. 서버 쪽 Blazor는 통신을 위해 ASP.NET Core SignalR를 사용 하기 때문에 HTTP 컨텍스트와 관계 없이 연결이 발생할 수 있으므로 세션 상태가 지원 되지 않습니다. 세션 상태를 사용 하는 앱은 Blazor 앱으로 실행 하기 전에 다시 설계 해야 합니다.

앱 시작에 대 한 자세한 내용은 [앱 시작](app-startup.md)을 참조 하세요.

## <a name="migrate-http-modules-and-handlers-to-middleware"></a>HTTP 모듈 및 처리기를 미들웨어로 마이그레이션

Http 모듈 및 처리기는 HTTP 요청 파이프라인을 제어 하기 위한 Web Forms 일반적인 패턴입니다. `IHttpModule` 또는 `IHttpHandler`를 구현 하는 클래스를 등록 하 고 들어오는 요청을 처리할 수 있습니다. Web Forms는 *web.config* 파일에서 모듈 및 처리기를 구성 합니다. 또한 Web Forms는 앱 수명 주기 이벤트 처리에 따라 크게 달라 집니다. ASP.NET Core는 미들웨어를 대신 사용 합니다. 미들웨어는 `Startup` 클래스의 `Configure` 메서드에 등록 됩니다. 미들웨어 실행 순서는 등록 순서에 따라 결정 됩니다.

[시작 프로세스 사용](#enable-startup-process) 섹션에서 `Application_BeginRequest` 방법으로 Web Forms 하 여 수명 주기 이벤트를 발생 시킵니다. 이 이벤트는 ASP.NET Core에서 사용할 수 없습니다. 이 동작을 수행 하는 한 가지 방법은 *Startup.cs* 파일 예제에서 볼 수 있듯이 미들웨어를 구현 하는 것입니다. 이 미들웨어는 동일한 논리를 수행한 다음 미들웨어 파이프라인의 다음 처리기로 제어를 전달 합니다.

모듈 및 처리기를 마이그레이션하는 방법에 대 한 자세한 내용은 [HTTP 처리기 및 모듈을 ASP.NET Core 미들웨어로 마이그레이션](/aspnet/core/migration/http-modules)을 참조 하세요.

## <a name="migrate-static-files"></a>정적 파일 마이그레이션

HTML, CSS, 이미지 및 JavaScript와 같은 정적 파일을 제공 하려면 파일을 미들웨어에서 노출 해야 합니다. `UseStaticFiles` 메서드를 호출 하면 웹 루트 경로에서 정적 파일을 제공할 수 있습니다. 기본 웹 루트 디렉터리는 *wwwroot*이지만 사용자 지정할 수 있습니다. EShop의 `Startup` 클래스의 `Configure` 메서드에 포함 되어 있습니다.

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

EShop 프로젝트를 사용 하면 기본 정적 파일에 액세스할 수 있습니다. 정적 파일 액세스에 사용할 수 있는 많은 사용자 지정이 있습니다. 기본 파일 또는 파일 브라우저를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [ASP.NET Core의 정적 파일](/aspnet/core/fundamentals/static-files)을 참조 하세요.

## <a name="migrate-runtime-bundling-and-minification-setup"></a>런타임 묶음 및 축소 설정 마이그레이션

묶음 및 축소는 특정 파일 형식을 검색 하기 위해 서버 요청의 수와 크기를 줄이기 위한 성능 최적화 기술입니다. JavaScript 및 CSS는 클라이언트에 전송 되기 전에 몇 가지 형태의 묶음 또는 축소를 수행 하는 경우가 많습니다. ASP.NET Web Forms에서 이러한 최적화는 런타임에 처리 됩니다. 최적화 규칙은 *App_Start/bundleconfig.cs* 파일을 정의 합니다. ASP.NET Core에는 보다 선언적인 방법이 도입 되었습니다. 파일에는 특정 축소 설정과 함께 파일을 표시 합니다.

묶음 및 축소에 대 한 자세한 내용은 [ASP.NET Core의 번들 및 미니 정적 자산](/aspnet/core/client-side/bundling-and-minification)을 참조 하세요.

## <a name="migrate-aspx-pages"></a>ASPX 페이지 마이그레이션

Web Forms 앱의 페이지는 확장명이 *.aspx* 인 파일입니다. Web Forms 페이지는 종종 Blazor의 구성 요소에 매핑될 수 있습니다. Blazor 구성 요소는 확장명이 *razor* 인 파일에 작성 됩니다. EShop 프로젝트의 경우 5 개의 페이지가 Razor 페이지로 변환 됩니다.

예를 들어 세부 정보 보기는 Web Forms 프로젝트의 세 가지 *파일 (* *Details.aspx.cs*, *Details.aspx.designer.cs 및*)로 구성 됩니다. Blazor로 변환 하는 경우 코드 숨김과 태그가 *자세히. razor*로 결합 됩니다. Razor 컴파일 ( *designer.cs* 파일에 해당)은 *obj* 디렉터리에 저장 되며 기본적으로 **솔루션 탐색기**에서 볼 수 없습니다. Web Forms 페이지는 다음 태그로 구성 됩니다.

```aspx-csharp
<%@ Page Title="Details" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Details.aspx.cs" Inherits="eShopLegacyWebForms.Catalog.Details" %>

<asp:Content ID="Details" ContentPlaceHolderID="MainContent" runat="server">
    <h2 class="esh-body-title">Details</h2>

    <div class="container">
        <div class="row">
            <asp:Image runat="server" CssClass="col-md-6 esh-picture" ImageUrl='<%#"/Pics/" + product.PictureFileName%>' />
            <dl class="col-md-6 dl-horizontal">
                <dt>Name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Name%>' />
                </dd>

                <dt>Description
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Description%>' />
                </dd>

                <dt>Brand
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogBrand.Brand%>' />
                </dd>

                <dt>Type
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogType.Type%>' />
                </dd>
                <dt>Price
                </dt>

                <dd>
                    <asp:Label CssClass="esh-price" runat="server" Text='<%#product.Price%>' />
                </dd>

                <dt>Picture name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.PictureFileName%>' />
                </dd>

                <dt>Stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.AvailableStock%>' />
                </dd>

                <dt>Restock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.RestockThreshold%>' />
                </dd>

                <dt>Max stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.MaxStockThreshold%>' />
                </dd>

            </dl>
        </div>

        <div class="form-actions no-color esh-link-list">
            <a runat="server" href='<%# GetRouteUrl("EditProductRoute", new {id =product.Id}) %>' class="esh-link-item">Edit
            </a>
            |
            <a runat="server" href="~" class="esh-link-item">Back to list
            </a>
        </div>

    </div>
</asp:Content>
```

위의 태그 코드 뒤에는 다음 코드가 포함 되어 있습니다.

```csharp
using eShopLegacyWebForms.Models;
using eShopLegacyWebForms.Services;
using log4net;
using System;
using System.Web.UI;

namespace eShopLegacyWebForms.Catalog
{
    public partial class Details : System.Web.UI.Page
    {
        private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

        protected CatalogItem product;

        public ICatalogService CatalogService { get; set; }

        protected void Page_Load(object sender, EventArgs e)
        {
            var productId = Convert.ToInt32(Page.RouteData.Values["id"]);
            _log.Info($"Now loading... /Catalog/Details.aspx?id={productId}");
            product = CatalogService.FindCatalogItem(productId);

            this.DataBind();
        }
    }
}
```

Blazor로 변환 될 때 Web Forms 페이지는 다음 코드로 변환 됩니다.

```razor
@page "/Catalog/Details/{id:int}"
@inject ICatalogService CatalogService
@inject ILogger<Details> Logger

<h2 class="esh-body-title">Details</h2>

<div class="container">
    <div class="row">
        <img class="col-md-6 esh-picture" src="@($"/Pics/{_item.PictureFileName}")">

        <dl class="col-md-6 dl-horizontal">
            <dt>
                Name
            </dt>

            <dd>
                @_item.Name
            </dd>

            <dt>
                Description
            </dt>

            <dd>
                @_item.Description
            </dd>

            <dt>
                Brand
            </dt>

            <dd>
                @_item.CatalogBrand.Brand
            </dd>

            <dt>
                Type
            </dt>

            <dd>
                @_item.CatalogType.Type
            </dd>
            <dt>
                Price
            </dt>

            <dd>
                @_item.Price
            </dd>

            <dt>
                Picture name
            </dt>

            <dd>
                @_item.PictureFileName
            </dd>

            <dt>
                Stock
            </dt>

            <dd>
                @_item.AvailableStock
            </dd>

            <dt>
                Restock
            </dt>

            <dd>
                @_item.RestockThreshold
            </dd>

            <dt>
                Max stock
            </dt>

            <dd>
                @_item.MaxStockThreshold
            </dd>

        </dl>
    </div>

    <div class="form-actions no-color esh-link-list">
        <a href="@($"/Catalog/Edit/{_item.Id}")" class="esh-link-item">
            Edit
        </a>
        |
        <a href="/" class="esh-link-item">
            Back to list
        </a>
    </div>

</div>

@code {
    private CatalogItem _item;

    [Parameter]
    public int Id { get; set; }

    protected override void OnInitialized()
    {
        Logger.LogInformation("Now loading... /Catalog/Details/{Id}", Id);

        _item = CatalogService.FindCatalogItem(Id);
    }
}
```

코드와 태그가 동일한 파일에 있습니다. 모든 필수 서비스에는 `@inject` 특성을 사용 하 여 액세스할 수 있습니다. `@page` 지시문에 따라이 페이지는 `Catalog/Details/{id}` 경로에서 액세스할 수 있습니다. 경로의 `{id}` 자리 표시자 값이 정수로 제한 되었습니다. [라우팅](pages-routing-layouts.md) 섹션에 설명 된 대로 Web Forms와 달리 Razor 구성 요소는 해당 경로 및 포함 된 모든 매개 변수를 명시적으로 명시 합니다. 많은 Web Forms 컨트롤의 Blazor에 정확히 일치 하는 항목이 없을 수 있습니다. 동일한 용도로 사용 되는 것과 동일한 HTML 코드 조각이 종종 있습니다. 예를 들어 `<asp:Label />` 컨트롤을 HTML `<label>` 요소로 바꿀 수 있습니다.

### <a name="model-validation-in-blazor"></a>Blazor의 모델 유효성 검사

Web Forms 코드에 유효성 검사가 포함 된 경우 거의 변경 하지 않고 많은 항목을 전송할 수 있습니다. Blazor에서 실행 하는 경우의 혜택은 사용자 지정 JavaScript가 없어도 동일한 유효성 검사 논리를 실행할 수 있다는 것입니다. 데이터 주석을 사용 하면 모델의 유효성을 쉽게 확인할 수 있습니다.

예를 들어, *Create .aspx* 페이지에는 유효성 검사가 포함 된 데이터 입력 양식이 있습니다. 예제 코드 조각은 다음과 같습니다.

```aspx
<div class="form-group">
    <label class="control-label col-md-2">Name</label>
    <div class="col-md-3">
        <asp:TextBox ID="Name" runat="server" CssClass="form-control"></asp:TextBox>
        <asp:RequiredFieldValidator runat="server" ControlToValidate="Name" Display="Dynamic"
            CssClass="field-validation-valid text-danger" ErrorMessage="The Name field is required." />
    </div>
</div>
```

Blazor에서 동일한 태그는 *Create. razor* 파일에 제공 됩니다.

```razor
<EditForm Model="_item" OnValidSubmit="@...">
    <DataAnnotationsValidator />

    <div class="form-group">
        <label class="control-label col-md-2">Name</label>
        <div class="col-md-3">
            <InputText class="form-control" @bind-Value="_item.Name" />
            <ValidationMessage For="(() => _item.Name)" />
        </div>
    </div>

    ...
</EditForm>
```

`EditForm` 컨텍스트에는 유효성 검사 지원이 포함 되며 입력 주위에 래핑할 수 있습니다. 데이터 주석은 유효성 검사를 추가 하는 일반적인 방법입니다. 이러한 유효성 검사 지원은 `DataAnnotationsValidator` 구성 요소를 통해 추가할 수 있습니다. 이 메커니즘에 대 한 자세한 내용은 [ASP.NET Core Blazor forms 및 유효성 검사](/aspnet/core/blazor/forms-validation)를 참조 하세요.

## <a name="migrate-built-in-web-forms-controls"></a>기본 제공 Web Forms 컨트롤 마이그레이션

*이 콘텐츠는 곧 제공 될 예정입니다.*

## <a name="migrate-configuration"></a>구성 마이그레이션

Web Forms 프로젝트에서 구성 데이터는 가장 일반적으로 web.config 파일에 저장 *됩니다.* 구성 데이터는 `ConfigurationManager`를 사용 하 여 액세스 됩니다. 개체를 구문 분석 하려면 서비스가 자주 필요 했습니다. .NET Framework 4.7.2를 사용 하 여 composability가 `ConfigurationBuilders`를 통해 구성에 추가 되었습니다. 이러한 빌더를 통해 개발자는 런타임에 구성 된 구성에 대해 다양 한 소스를 추가 하 여 필요한 값을 검색할 수 있습니다.

ASP.NET Core에는 앱 및 배포에 사용 되는 구성 소스 또는 소스를 정의할 수 있는 유연한 구성 시스템이 도입 되었습니다. Web Forms 앱에서 사용할 수 있는 `ConfigurationBuilder` 인프라는 ASP.NET Core 구성 시스템에서 사용 되는 개념에 따라 모델링 되었습니다.

다음 코드 조각에서는 Web Forms eShop 프로젝트가 *web.config* 를 사용 하 여 구성 값을 저장 하는 방법을 보여 줍니다.

```xml
<configuration>
  <configSections>
    <section name="entityFramework" type="System.Data.Entity.Internal.ConfigFile.EntityFrameworkSection, EntityFramework, Version=6.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" requirePermission="false" />
  </configSections>
  <connectionStrings>
    <add name="CatalogDBContext" connectionString="Data Source=(localdb)\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;" providerName="System.Data.SqlClient" />
  </connectionStrings>
  <appSettings>
    <add key="UseMockData" value="true" />
    <add key="UseCustomizationData" value="false" />
  </appSettings>
```

데이터베이스 연결 문자열과 같은 *비밀이 web.config 내*에 저장 되는 것이 일반적입니다. 비밀은 원본 제어와 같은 안전 하지 않은 위치에 유지 됩니다. Blazor ASP.NET Core에 대 한를 사용 하면 앞의 XML 기반 구성이 다음 JSON으로 바뀝니다.

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

JSON은 기본 구성 형식입니다. 그러나 ASP.NET Core는 XML을 비롯 한 다른 많은 형식을 지원 합니다. 또한 몇 가지 커뮤니티 지원 형식이 있습니다.

Blazor 프로젝트의 `Startup` 클래스의 생성자는 생성자 주입 이라고 하는 DI 기술을 통해 `IConfiguration` 인스턴스를 허용 합니다.

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    ...
}
```

기본적으로 환경 변수, JSON 파일 (*appsettings* 및 *appsettings. { Environment}. json*) 및 명령줄 옵션은 구성 개체에 유효한 구성 원본으로 등록 됩니다. 구성 소스는 `Configuration[key]`를 통해 액세스할 수 있습니다. 고급 기술은 옵션 패턴을 사용 하 여 구성 데이터를 개체에 바인딩하는 것입니다. 구성 및 옵션 패턴에 대 한 자세한 내용은 [ASP.NET Core의 구성](/aspnet/core/fundamentals/configuration/) 및 [ASP.NET Core의 옵션 패턴](/aspnet/core/fundamentals/configuration/options)을 참조 하세요.

## <a name="migrate-data-access"></a>데이터 액세스 마이그레이션

데이터 액세스는 모든 앱의 중요 한 측면입니다. EShop 프로젝트는 카탈로그 정보를 데이터베이스에 저장 하 고 Entity Framework (EF) 6을 사용 하 여 데이터를 검색 합니다. EF 6은 .NET Core 3.0에서 지원 되기 때문에 프로젝트에서 계속 사용할 수 있습니다.

EShop에는 다음과 같은 EF 관련 변경이 필요 했습니다.

- .NET Framework에서 `DbContext` 개체는 *name = ConnectionString* 형식의 문자열을 수락 하 고 `ConfigurationManager.AppSettings[ConnectionString]`의 연결 문자열을 사용 하 여 연결 합니다. .NET Core에서는 지원 되지 않습니다. 연결 문자열을 제공 해야 합니다.
- 동기 방식으로 데이터베이스에 액세스 했습니다. 이 기능이 작동 하지만 확장성이 저하 될 수 있습니다. 이 논리는 비동기 패턴으로 이동 해야 합니다.

데이터 집합 바인딩에 대 한 기본 지원이 없어도 Blazor는 Razor 페이지에서 유연 하 고 강력한 C# 기능을 제공 합니다. 예를 들어 계산을 수행 하 고 결과를 표시할 수 있습니다. Blazor의 데이터 패턴에 대 한 자세한 내용은 [데이터 액세스](data.md) 챕터를 참조 하세요.

## <a name="architectural-changes"></a>아키텍처 변경

마지막으로 Blazor로 마이그레이션할 때 고려해 야 할 몇 가지 중요 한 아키텍처 차이점이 있습니다. 이러한 변경 내용 중 상당수는 .NET Core 또는 ASP.NET Core을 기반으로 하는 모든 항목에 적용 됩니다.

Blazor는 .NET Core를 기반으로 하기 때문에 .NET Core에 대 한 지원을 보장 하기 위해 고려해 야 할 사항이 있습니다. 주요 변경 내용 중 일부는 다음과 같은 기능을 제거 하는 것입니다.

- 다중 Appdomain
- 원격 통신
- CAS(코드 액세스 보안)
- 보안 투명도

.NET Core에서 실행 하는 데 필요한 변경 내용을 식별 하는 방법에 대 한 자세한 내용은 [.NET Framework에서 .Net core로 코드 이식](/dotnet/core/porting)을 참조 하세요.

ASP.NET Core는 ASP.NET의 다시 발생 한 버전 이며, 처음에는 명확 하지 않을 수 있는 몇 가지 변경 사항이 있습니다. 주요 변경 내용은 다음과 같습니다.

- 동기화 컨텍스트가 없습니다. 즉, `HttpContext.Current`, `Thread.CurrentPrincipal`또는 기타 정적 접근자가 없음을 의미 합니다.
- 섀도 복사 안 함
- 요청 큐 없음

ASP.NET Core의 많은 작업은 비동기 이므로 i/o 바인딩된 작업을 보다 쉽게 로드할 수 있습니다. 스레드 풀 리소스를 신속 하 게 고갈 시킬 수 있는 `Task.Wait()` 또는 `Task.GetResult()`를 사용 하 여 차단 하지 않는 것이 중요 합니다.

## <a name="migration-conclusion"></a>마이그레이션 결론

이 시점에서 Web Forms 프로젝트를 Blazor로 이동 하는 데 필요한 여러 가지 예를 살펴보았습니다. 전체 예제를 보려면 [eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor) 프로젝트를 참조 하세요.

>[!div class="step-by-step"]
>[이전](security-authentication-authorization.md)
