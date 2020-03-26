---
title: ASP.NET 웹 양식에서 블레이저로 마이그레이션
description: 기존 ASP.NET Web Forms 앱을 Blazor로 마이그레이션하는 방법을 알아봅니다.
author: twsouthwick
ms.author: tasou
ms.date: 09/19/2019
ms.openlocfilehash: 0a10a9a3d5ab32e16cb59a68da57116e20c53e49
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134086"
---
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a>ASP.NET 웹 양식에서 블레이저로 마이그레이션

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

ASP.NET 웹 양식에서 Blazor로 코드 베이스를 마이그레이션하는 것은 계획이 필요한 시간이 많이 소요되는 작업입니다. 이 장에서는 프로세스를 간략하게 설명합니다. 전환을 용이하게 할 수 있는 것은 앱이 *N 계층* 아키텍처를 준수하도록 하는 것입니다. 이러한 논리적계층 분리를 통해 .NET Core 및 Blazor로 이동해야 하는 사항을 명확하게 알 수 있습니다.

이 예제에서는 [GitHub에서](https://github.com/dotnet-architecture/eShopOnBlazor) 사용할 수 있는 eShop 앱이 사용됩니다. eShop은 양식 입력 및 유효성 검사를 통해 CRUD 기능을 제공하는 카탈로그 서비스입니다.

작업 중인 앱을 Blazor로 마이그레이션해야 하는 이유는 무엇입니까? 여러 번, 필요가 없습니다. ASP.NET 웹 폼은 수년 동안 계속 지원될 것입니다. 그러나 Blazor가 제공하는 많은 기능은 마이그레이션된 앱에서만 지원됩니다. 이러한 기능은 다음과 같습니다.

- 프레임워크의 성능 향상과 같은`Span<T>`
- 웹 어셈블리로 실행하는 기능
- Linux 및 macOS용 플랫폼 간 지원
- 다른 앱에 영향을 주지 않고 앱 로컬 배포 또는 공유 프레임워크 배포

이러한 기능이나 다른 새로운 기능이 충분히 매력적인 경우 앱을 마이그레이션할 때 가치가 있을 수 있습니다. 마이그레이션은 다른 모양을 취할 수 있습니다. 전체 앱이거나 변경이 필요한 특정 끝점일 수 있습니다. 마이그레이션 결정은 궁극적으로 개발자가 해결해야 할 비즈니스 문제를 기반으로 합니다.

## <a name="server-side-versus-client-side-hosting"></a>서버 측 및 클라이언트 측 호스팅

[호스팅 모델](hosting-models.md) 장에서 설명한 대로 Blazor 앱은 서버 측과 클라이언트 측의 두 가지 방법으로 호스팅할 수 있습니다. 서버 측 모델은 ASP.NET Core SignalR 연결을 사용하여 서버에서 실제 코드를 실행하는 동안 DOM 업데이트를 관리합니다. 클라이언트 측 모델은 브라우저 내에서 WebAssembly로 실행되며 서버 연결이 필요하지 않습니다. 특정 앱에 가장 적합한 영향을 줄 수 있는 몇 가지 차이점이 있습니다.

- WebAssembly로 실행 중인 경우 아직 개발 중이며 현재 스레딩과 같은 모든 기능을 지원하지 않을 수 있습니다.
- 클라이언트와 서버 간의 수다스러운 통신으로 인해 서버 측 모드에서 대기 시간 문제가 발생할 수 있습니다.
- 데이터베이스 및 내부 또는 보호된 서비스에 액세스하려면 클라이언트 측 호스팅을 통해 별도의 서비스가 필요합니다.

작성 시 서버 쪽 모델은 웹 양식과 더 유사합니다. 이 장의 대부분은 프로덕션 준비가 되어 있으므로 서버 측 호스팅 모델에 중점을 둡니다.

## <a name="create-a-new-project"></a>새 프로젝트 만들기

이 초기 마이그레이션 단계는 새 프로젝트를 만드는 것입니다. 이 프로젝트 유형은 .NET Core의 SDK 스타일 프로젝트를 기반으로 하며 이전 프로젝트 형식에서 사용했던 상용구의 대부분을 단순화합니다. 자세한 내용은 [프로젝트 구조의](project-structure.md)장을 참조하십시오.

프로젝트가 만들어지면 이전 프로젝트에서 사용된 라이브러리를 설치합니다. 이전 웹 폼 *프로젝트에서는 packages.config* 파일을 사용하여 필요한 NuGet 패키지를 나열했을 수 있습니다. 새 SDK 스타일 프로젝트에서 *packages.config가* 프로젝트 `<PackageReference>` 파일의 요소로 대체되었습니다. 이 방법의 이점은 모든 종속성이 전이적으로 설치된다는 것입니다. 관심 있는 최상위 종속성만 나열합니다.

사용 중인 많은 종속성은 엔터티 프레임워크 6 및 log4net을 포함하여 .NET Core에 사용할 수 있습니다. 사용할 수 있는 .NET Core 또는 .NET 표준 버전이 없는 경우 .NET Framework 버전을 사용할 수 있습니다. 마일리지는 다를 수 있습니다. .NET Core에서 사용할 수 없는 API는 런타임 오류를 발생시킵니다. Visual Studio는 이러한 패키지를 알려주는 것입니다. **솔루션 탐색기에서**프로젝트의 **참조** 노드에 노란색 아이콘이 나타납니다.

Blazor 기반 eShop 프로젝트에서 설치된 패키지를 볼 수 있습니다. 이전에는 *packages.config* 파일이 프로젝트에 사용된 모든 패키지를 나열하여 거의 50줄길이의 파일을 생성했습니다. *패키지의 스니펫입니다.config는* 다음과 같은 것입니다.

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

요소에는 `<packages>` 필요한 모든 종속성이 포함됩니다. 이러한 패키지가 필요하기 때문에 이러한 패키지중 어떤 패키지가 포함되어 있는지 식별하기가 어렵습니다. 일부 `<package>` 요소는 필요한 종속성의 요구를 충족하기 위해 간단히 나열됩니다.

Blazor 프로젝트는 프로젝트 파일의 `<ItemGroup>` 요소 내에서 필요한 종속성을 나열합니다.

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

웹 양식 개발자의 수명을 단순화 하는 하나의 NuGet 패키지는 [Windows 호환성 팩](../../core/porting/windows-compat-pack.md). .NET Core는 크로스 플랫폼이지만 일부 기능은 Windows에서만 사용할 수 있습니다. Windows 관련 기능은 호환성 팩을 설치하여 사용할 수 있습니다. 이러한 기능의 예로는 레지스트리, WMI 및 디렉터리 서비스가 있습니다. 이 패키지는 약 20,000개의 API를 추가하고 이미 익숙할 수 있는 많은 서비스를 활성화합니다. eShop 프로젝트에는 호환성 팩이 필요하지 않습니다. 그러나 프로젝트에서 Windows 관련 기능을 사용하는 경우 패키지는 마이그레이션 을 용이하게 합니다.

## <a name="enable-startup-process"></a>시작 프로세스 사용

Blazor의 시작 프로세스가 웹 양식에서 변경되었으며 다른 ASP.NET Core 서비스에 대한 유사한 설정을 따릅니다. 서버 측에서 호스팅되는 경우 Blazor 구성 요소는 일반 ASP.NET Core 앱의 일부로 실행됩니다. WebAssembly를 사용하여 브라우저에서 호스팅되는 경우 Blazor 구성 요소는 유사한 호스팅 모델을 사용합니다. 차이점은 구성 요소가 백 엔드 프로세스와 별도의 서비스로 실행된다는 것입니다. 어느 쪽이든 시작은 비슷합니다.

*Global.asax.cs* 파일은 Web Forms 프로젝트의 기본 시작 페이지입니다. eShop 프로젝트에서 이 파일은 IoC(Control) 컨테이너의 반전을 구성하고 앱 또는 요청의 다양한 수명 주기 이벤트를 처리합니다. 이러한 이벤트 중 일부는 미들웨어(예:)로 `Application_BeginRequest`처리됩니다. 다른 이벤트는 DI(종속성 주입)를 통해 특정 서비스를 재정의해야 합니다.

예를 들어 eShop용 *Global.asax.cs* 파일에는 다음 코드가 포함되어 있습니다.

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

앞의 파일은 `Startup` 서버 쪽 Blazor의 클래스가 됩니다.

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

웹 양식에서 알 수 있는 한 가지 중요한 변경 사항은 DI의 눈에 띄는 것입니다. DI는 ASP.NET 코어 설계의 기본 원칙이었습니다. ASP.NET 코어 프레임워크의 거의 모든 측면에 대한 사용자 지정을 지원합니다. 많은 시나리오에 사용할 수 있는 기본 제공 서비스 공급자도 있습니다. 더 많은 사용자 지정이 필요한 경우 많은 커뮤니티 프로젝트에서 지원할 수 있습니다. 예를 들어 타사 DI 라이브러리 투자를 전달할 수 있습니다.

원래 eShop 앱에는 세션 관리를 위한 몇 가지 구성이 있습니다. 서버 측 Blazor는 통신을 위해 ASP.NET 코어 신호R을 사용하므로 HTTP 컨텍스트와 독립적으로 연결이 발생할 수 있기 때문에 세션 상태가 지원되지 않습니다. 세션 상태를 사용하는 앱은 Blazor 앱으로 실행하기 전에 다시 설계해야 합니다.

앱 시작에 대한 자세한 내용은 [앱 시작을](app-startup.md)참조하십시오.

## <a name="migrate-http-modules-and-handlers-to-middleware"></a>HTTP 모듈 및 처리기를 미들웨어로 마이그레이션

HTTP 모듈 및 처리기는 HTTP 요청 파이프라인을 제어하는 웹 양식의 일반적인 패턴입니다. `IHttpModule` 등록하거나 `IHttpHandler` 등록할 수 있는 클래스이며 들어오는 요청을 처리합니다. Web Forms는 *web.config* 파일에서 모듈과 처리기를 구성합니다. 웹 양식은 또한 앱 수명 주기 이벤트 처리를 기반으로 합니다. ASP.NET 코어 대신 미들웨어를 사용합니다. 미들웨어는 클래스의 `Configure` 방법에 `Startup` 등록되어 있습니다. 미들웨어 실행 순서는 등록 순서에 따라 결정됩니다.

시작 [프로세스 활성화](#enable-startup-process) 섹션에서 웹 폼을 `Application_BeginRequest` 메서드로 수명 주기 이벤트를 발생 했습니다. 이 이벤트는 ASP.NET 코어에서 사용할 수 없습니다. 이 동작을 달성하는 한 가지 방법은 *Startup.cs* 파일 예제에서 볼 수 있는 미들웨어를 구현하는 것입니다. 이 미들웨어는 동일한 논리를 수행한 다음 미들웨어 파이프라인의 다음 처리기로 컨트롤을 전송합니다.

모듈 및 처리기 마이그레이션에 대한 자세한 내용은 [HTTP 처리기 및 모듈을 ASP.NET Core 미들웨어로 마이그레이션을](/aspnet/core/migration/http-modules)참조하십시오.

## <a name="migrate-static-files"></a>정적 파일 마이그레이션

정적 파일(예: HTML, CSS, 이미지 및 JavaScript)을 제공하려면 파일을 미들웨어에 의해 노출해야 합니다. 메서드를 `UseStaticFiles` 호출하면 웹 루트 경로에서 정적 파일을 사용할 수 있습니다. 기본 웹 루트 디렉토리는 *wwwroot이지만*사용자 지정할 수 있습니다. eShop `Configure` `Startup` 클래스의 방법에 포함 된 바와 같이 :

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

eShop 프로젝트는 기본 정적 파일 액세스를 가능하게 합니다. 정적 파일 액세스에 사용할 수 있는 많은 사용자 지정이 있습니다. 기본 파일 또는 파일 브라우저 를 사용하도록 설정하는 방법에 대한 자세한 내용은 [ASP.NET Core의 정적 파일을](/aspnet/core/fundamentals/static-files)참조하십시오.

## <a name="migrate-runtime-bundling-and-minification-setup"></a>런타임 번들 및 축소 설정 마이그레이션

번들 및 축소는 특정 파일 형식을 검색하기 위한 서버 요청의 수와 크기를 줄이는 성능 최적화 기술입니다. 자바 스크립트와 CSS는 종종 클라이언트로 전송되기 전에 번들 또는 축소의 일종을 겪는다. ASP.NET 웹 양식에서 이러한 최적화는 런타임에 처리됩니다. 최적화 규칙은 *App_Start/BundleConfig.cs* 파일로 정의됩니다. ASP.NET 코어에서는 보다 선언적인 접근 방식이 채택됩니다. 파일은 특정 세부 설정과 함께 축소할 파일을 나열합니다.

번들 및 축소에 대한 자세한 내용은 [ASP.NET 코어의 정적 자산을 번들 및 최소화를](/aspnet/core/client-side/bundling-and-minification)참조하십시오.

## <a name="migrate-aspx-pages"></a>ASPX 페이지 마이그레이션

웹 양식 앱의 페이지는 *.aspx* 확장명이 있는 파일입니다. 웹 양식 페이지는 종종 Blazor의 구성 요소에 매핑될 수 있습니다. Blazor 구성 요소는 *.razor* 확장자가 있는 파일에서 작성됩니다. eShop 프로젝트의 경우 5페이지가 Razor 페이지로 변환됩니다.

예를 들어 세부 정보 보기는 웹 양식 프로젝트의 세 파일로 구성됩니다: *Details.aspx,* *Details.aspx.cs*및 *Details.aspx.designer.cs*. Blazor로 변환할 때 코드 숨미기와 마크업이 *Details.razor로*결합됩니다. Razor *컴파일(.designer.cs* 파일에 있는 것과 동일)은 *obj* 디렉터리에 저장되며 기본적으로 **솔루션 탐색기에서**볼 수 없습니다. 웹 양식 페이지는 다음 태그로 구성됩니다.

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

앞의 태그코드 뒤에는 다음 코드가 포함됩니다.

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

Blazor로 변환하면 웹 양식 페이지는 다음 코드로 변환됩니다.

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

코드와 태그가 동일한 파일에 있습니다. 필요한 모든 서비스는 `@inject` 특성을 통해 액세스할 수 있습니다. `@page` 지시문에 따라 이 페이지는 `Catalog/Details/{id}` 경로에서 액세스할 수 있습니다. 경로의 `{id}` 자리 표시자 값이 정수로 제한됩니다. 웹 양식과 달리 [라우팅](pages-routing-layouts.md) 섹션에 설명된 대로 Razor 구성 요소는 해당 경로와 포함된 모든 매개 변수를 명시적으로 명시합니다. 대부분의 웹 폼 컨트롤에는 Blazor에 정확한 대응이 없을 수 있습니다. 동일한 용도로 사용되는 HTML 스니펫이 있는 경우가 많습니다. 예를 들어 `<asp:Label />` 컨트롤을 HTML `<label>` 요소로 대체할 수 있습니다.

### <a name="model-validation-in-blazor"></a>블레이저에서 모델 유효성 검사

Web Forms 코드에 유효성 검사가 포함된 경우 거의 변경되지 않고 있는 내용의 대부분을 전송할 수 있습니다. Blazor에서 실행하면 사용자 지정 JavaScript없이 동일한 유효성 검사 논리를 실행할 수 있다는 이점이 있습니다. 데이터 주석을 사용하면 모델 유효성 검사를 쉽게 수행할 수 있습니다.

예를 들어 *Create.aspx* 페이지에는 유효성 검사가 있는 데이터 입력 양식이 있습니다. 예제 스니펫은 다음과 같습니다.

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

Blazor에서 이와 동등한 태그는 *Create.razor* 파일에 제공됩니다.

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

컨텍스트에는 `EditForm` 유효성 검사 지원이 포함되며 입력 주위에 래핑할 수 있습니다. 데이터 주석은 유효성 검사를 추가하는 일반적인 방법입니다. 이러한 유효성 검사 지원은 `DataAnnotationsValidator` 구성 요소를 통해 추가할 수 있습니다. 이 메커니즘에 대한 자세한 내용은 [ASP.NET 코어 블레이저 양식 및 유효성 검사를](/aspnet/core/blazor/forms-validation)참조하십시오.

## <a name="migrate-built-in-web-forms-controls"></a>기본 제공 웹 양식 컨트롤 마이그레이션

*이 콘텐츠는 곧 출시될 예정입니다.*

## <a name="migrate-configuration"></a>구성 마이그레이션

Web Forms 프로젝트에서 구성 데이터는 *web.config* 파일에 가장 일반적으로 저장됩니다. 구성 데이터는 을 사용하여 `ConfigurationManager`액세스됩니다. 개체를 구문 분석하는 데 서비스가 필요한 경우가 많습니다. .NET Framework 4.7.2를 사용하면 을 통해 `ConfigurationBuilders`구성에 구성성이 추가되었습니다. 이러한 빌더를 통해 개발자는 구성에 대한 다양한 소스를 추가할 수 있었고, 그런 다음 런타임에 구성하여 필요한 값을 검색할 수 있었습니다.

ASP.NET Core는 앱 및 배포에서 사용하는 구성 소스 또는 소스를 정의할 수 있는 유연한 구성 시스템을 도입했습니다. Web `ConfigurationBuilder` Forms 앱에서 사용할 수 있는 인프라는 ASP.NET Core 구성 시스템에서 사용되는 개념을 모델로 했습니다.

다음 코드 조각은 Web Forms eShop 프로젝트에서 *web.config를* 사용하여 구성 값을 저장하는 방법을 보여 줍니다.

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
</configuration>
```

데이터베이스 연결 문자열과 같은 암호가 *web.config*내에 저장되는 것이 일반적입니다. 암호는 필연적으로 소스 제어와 같은 안전하지 않은 위치에 유지됩니다. Blazor on ASP.NET 코어에서는 앞의 XML 기반 구성이 다음 JSON으로 대체됩니다.

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

JSON은 기본 구성 형식입니다. 그러나 ASP.NET 코어는 XML을 비롯한 다른 많은 형식을 지원합니다. 커뮤니티에서 지원하는 여러 형식도 있습니다.

Blazor 프로젝트의 클래스의 `Startup` 생성자는 생성자 `IConfiguration` 주입이라고 하는 DI 기술을 통해 인스턴스를 수락합니다.

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

기본적으로 환경 변수, JSON*파일(appsettings.json* 및 *appsettings.{ 환경}.json)* 및 명령줄 옵션은 구성 개체에서 유효한 구성 원본으로 등록됩니다. 구성 소스는 을 통해 `Configuration[key]`액세스할 수 있습니다. 보다 고급 기술은 옵션 패턴을 사용하여 구성 데이터를 개체에 바인딩하는 것입니다. 구성 및 옵션 패턴에 대한 자세한 내용은 ASP.NET [코어의 구성](/aspnet/core/fundamentals/configuration/) 및 [ASP.NET 코어의 옵션 패턴을](/aspnet/core/fundamentals/configuration/options)각각 참조하십시오.

## <a name="migrate-data-access"></a>데이터 액세스 마이그레이션

데이터 액세스는 모든 앱의 중요한 측면입니다. eShop 프로젝트는 카탈로그 정보를 데이터베이스에 저장하고 EF(Entity Framework) 6을 사용하여 데이터를 검색합니다. EF 6은 .NET Core 3.0에서 지원되므로 프로젝트에서 계속 사용할 수 있습니다.

eShop에는 다음과 같은 EF 관련 변경 사항이 필요했습니다.

- .NET Framework에서 `DbContext` 개체는 양식 *이름=ConnectionString의* 문자열을 허용하고 연결 `ConfigurationManager.AppSettings[ConnectionString]` 문자열을 사용합니다. .NET Core에서는 이 지원되지 않습니다. 연결 문자열을 제공해야 합니다.
- 동기 식으로 데이터베이스에 액세스했습니다. 이 작동 하지만, 확장성 고통을 수 있습니다. 이 논리는 비동기 패턴으로 이동해야 합니다.

데이터 집합 바인딩에 대한 기본 지원은 동일하지 않지만 Blazor는 Razor 페이지에서 C# 지원을 통해 유연성과 전원을 제공합니다. 예를 들어 계산을 수행하고 결과를 표시할 수 있습니다. Blazor의 데이터 패턴에 대한 자세한 내용은 [데이터 액세스](data.md) 장을 참조하십시오.

## <a name="architectural-changes"></a>아키텍처 자체가 변경

마지막으로 Blazor로 마이그레이션할 때 고려해야 할 몇 가지 중요한 아키텍처 차이점이 있습니다. 이러한 변경 사항 중 대부분은 .NET 코어 또는 ASP.NET 코어를 기반으로 하는 모든 것에 적용할 수 있습니다.

Blazor는 .NET Core를 기반으로 하므로 .NET Core에서 지원을 보장하는 데 고려해야 할 사항이 있습니다. 몇 가지 주요 변경 사항으로는 다음과 같은 기능이 제거됩니다.

- 여러 앱 도메인
- 원격
- CAS(코드 액세스 보안)
- 보안 투명도

.NET Core에서 실행되는 데 필요한 변경 내용을 식별하는 기술에 대한 자세한 내용은 [.NET Framework에서 .NET Core로 코드 포트를](/dotnet/core/porting)참조하십시오.

ASP.NET 코어는 ASP.NET 새롭게 해석 된 버전이며 처음에는 분명하지 않은 몇 가지 변경 사항이 있습니다. 주요 변경 사항은 다음과 같습니다.

- 동기화 컨텍스트가 없으므로 ? `HttpContext.Current` `Thread.CurrentPrincipal`또는 기타 정적 접근자가 없음을 의미합니다.
- 그림자 복사 없음
- 요청 대기열 없음

ASP.NET 코어의 많은 작업은 비동기적이며 I/O 바인딩된 작업을 보다 쉽게 오프로드할 수 있습니다. 스레드 풀 리소스를 빠르게 `Task.Wait()` 소모할 수 있는 또는 `Task.GetResult()`을 사용하여 차단하지 않는 것이 중요합니다.

## <a name="migration-conclusion"></a>마이그레이션 결론

이 시점에서 웹 폼 프로젝트를 Blazor로 이동하는 데 필요한 많은 예제를 보았습니다. 전체 예제는 [eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor) 프로젝트를 참조하십시오.

>[!div class="step-by-step"]
>[이전](security-authentication-authorization.md)
