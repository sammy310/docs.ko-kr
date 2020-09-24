---
title: 앱 시작
description: 앱에 대 한 시작 논리를 정의 하는 방법을 알아봅니다.
author: csharpfritz
ms.author: jefritz
ms.date: 02/25/2020
ms.openlocfilehash: 883f9a3fbe2d52cb7d0fbc5dfc94ce829a5d2bf3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158190"
---
# <a name="app-startup"></a>앱 시작

ASP.NET 용으로 작성 된 응용 프로그램에는 일반적으로 `global.asax.cs` `Application_Start` 구성 되 고 HTML 렌더링과 .net 처리에 사용할 수 있는 서비스를 제어 하는 이벤트를 정의 하는 파일이 있습니다. 이 장에서는 ASP.NET Core 및 Blazor Server와 약간 어떻게 다른 지 살펴봅니다.

## <a name="application_start-and-web-forms"></a>Application_Start 및 Web Forms

기본 web forms `Application_Start` 메서드는 여러 구성 작업을 처리 하기 위해 몇 년 이상 효율적으로 성장 하 고 있습니다.  이제 Visual Studio 2019의 기본 템플릿이 있는 새로운 web forms 프로젝트에는 이제 다음과 같은 구성 논리가 포함 됩니다.

- `RouteConfig` -응용 프로그램 URL 라우팅
- `BundleConfig` -CSS 및 JavaScript 묶음 및 축소

이러한 개별 파일은 모두 폴더에 상주 `App_Start` 하며 응용 프로그램 시작 시 한 번만 실행 됩니다.  `RouteConfig` 기본 프로젝트 템플릿에서는 `FriendlyUrlSettings` 응용 프로그램 url이 파일 확장명을 생략할 수 있도록 web forms 용를 추가 합니다 `.ASPX` .  기본 템플릿에는 페이지에 대 한 영구 HTTP 리디렉션 상태 코드 (HTTP 301)를 `.ASPX` 확장명이 없는 파일 이름으로 친숙 한 URL에 제공 하는 지시문도 포함 됩니다.

ASP.NET Core 및 Blazor를 사용 하면 이러한 메서드를 간소화 하 고 클래스로 통합 `Startup` 하거나 일반적인 웹 기술에 대해 제거 합니다.

## <a name="blazor-server-startup-structure"></a>Blazor 서버 시작 구조

Blazor 서버 응용 프로그램은 ASP.NET Core 3.0 이상 응용 프로그램 위에 위치 합니다.  ASP.NET Core 웹 응용 프로그램은 `Startup.cs` 응용 프로그램의 루트 폴더에 있는 클래스의 메서드 쌍을 통해 구성 됩니다.  시작 클래스의 기본 콘텐츠는 아래에 나열 되어 있습니다.

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

ASP.NET Core의 나머지와 마찬가지로 Startup 클래스는 종속성 주입 원칙을 사용 하 여 생성 됩니다.  는 `IConfiguration` 구성 중에 나중에 액세스할 수 있도록 공용 속성에서 생성자 및 스 태 시에 제공 됩니다.

`ConfigureServices`ASP.NET Core에 도입 된 메서드를 사용 하면 프레임 워크의 기본 제공 종속성 주입 컨테이너에 대해 다양 한 ASP.NET Core framework 서비스를 구성할 수 있습니다.  다양 한 `services.Add*` 방법으로 인증, razor 페이지, MVC 컨트롤러 라우팅, SignalR 및 Blazor 서버 상호 작용과 같은 기능을 사용할 수 있는 서비스를 추가할 수 있습니다.  이 메서드는 ASPX, ASCX, .ASHX 및 ASMX 파일의 구문 분석과 처리가 web.config 구성 파일에서 ASP.NET를 참조 하 여 정의 되었으므로 web forms에서 필요 하지 않았습니다.  ASP.NET Core의 종속성 주입에 대 한 자세한 내용은 [온라인 설명서](/aspnet/core/fundamentals/dependency-injection)에서 확인할 수 있습니다.

`Configure`메서드는 ASP.NET Core 하는 HTTP 파이프라인의 개념을 소개 합니다.  이 메서드에서는 응용 프로그램에 전송 된 모든 요청을 처리 하는 [미들웨어](middleware.md) 를 위쪽에서 아래쪽으로 선언 합니다. 기본 구성의 이러한 기능 중 대부분은 web forms 구성 파일에 흩어져 있으며 이제는 쉽게 참조할 수 있도록 한 곳에 있습니다.

더 이상 파일에 저장 된 사용자 지정 오류 페이지의 구성이 `web.config` 아니라, 이제 응용 프로그램 환경에 레이블이 지정 되지 않은 경우 항상 표시 되도록 구성 됩니다 `Development` .  또한 ASP.NET Core 응용 프로그램은 이제 메서드 호출을 통해 기본적으로 TLS를 사용 하 여 보안 페이지를 제공 하도록 구성 됩니다 `UseHttpsRedirection` .

그런 다음 예기치 않은 구성 방법이에 나열 됩니다 `UseStaticFiles` .  ASP.NET Core에서는 정적 파일에 대 한 요청 (예: JavaScript, CSS, 이미지 파일)에 대 한 지원을 명시적으로 사용 하도록 설정 해야 하며, 앱의 *wwwroot* 폴더에 있는 파일만 기본적으로 주소를 지정할 수 있습니다.

다음 줄은 web forms에서 구성 옵션 중 하나를 복제 하는 첫 번째입니다 `UseRouting` .  이 메서드는 파이프라인에 ASP.NET Core 라우터를 추가 하 고 여기에서 구성 하거나 라우팅을 고려할 수 있는 개별 파일에서 구성할 수 있습니다.  라우팅 구성에 대 한 자세한 내용은 [라우팅 섹션](pages-routing-layouts.md)에서 찾을 수 있습니다.

이 메서드의 마지막 문은 ASP.NET Core 수신 대기 하는 끝점을 정의 합니다.  이러한 위치는 웹 서버에서 액세스할 수 있고 .NET에서 처리 되 고 사용자에 게 반환 되는 일부 콘텐츠를 받을 수 있는 웹 액세스 가능한 위치입니다.  첫 번째 항목은 `MapBlazorHub` Blazor 구성 요소의 상태 및 렌더링이 처리 되는 서버에 실시간 및 영구 연결을 제공 하는 데 사용할 SignalR hub를 구성 합니다.  `MapFallbackToPage`메서드 호출은 Blazor 응용 프로그램을 시작 하는 페이지의 웹 액세스 가능 위치를 나타내며, 클라이언트 쪽에서의 딥 링크 요청을 처리 하도록 응용 프로그램을 구성 합니다.  브라우저를 열고 기본 프로젝트 템플릿 등의 응용 프로그램에서 Blazor 처리 된 경로를 직접 탐색 하는 경우이 기능이 작동 하는 것을 볼 수 있습니다 `/counter` . 요청은 *_Host* 에 의해 처리 되 고,이 페이지에서 Blazor 라우터를 실행 하 고 카운터 페이지를 렌더링 합니다.

## <a name="upgrading-the-bundleconfig-process"></a>BundleConfig 프로세스 업그레이드

CSS 스타일 시트 및 JavaScript 파일과 같은 자산을 번들로 제공 하는 기술은 신속 하 게 진화 하는 도구와 이러한 리소스를 관리 하는 기술을 제공 하는 다른 기술을 통해 크게 발전 했습니다  이를 위해 Grunt/Gulp/WebPack과 같은 노드 명령줄 도구를 사용 하 여 정적 자산을 패키지 하는 것이 좋습니다.

Grunt, Gulp 및 WebPack 명령줄 도구와 연결 된 구성은 응용 프로그램에 추가할 수 있으며, ASP.NET Core 응용 프로그램 빌드 프로세스 중에 이러한 파일을 자동으로 무시 합니다.  `Target`Gulp 스크립트와 `min` 해당 스크립트 내부의 대상을 트리거하는 다음과 유사한 구문을 사용 하 여 프로젝트 파일 내에를 추가 하 여 작업을 실행 하는 호출을 추가할 수 있습니다.

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="gulp min" />
</Target>
```

CSS 및 JavaScript 파일을 관리 하기 위한 두 전략에 대 한 자세한 내용은 [ASP.NET Core 설명서의 번들 및 미니 고 정적 자산](/aspnet/core/client-side/bundling-and-minification) 에서 제공 됩니다.

>[!div class="step-by-step"]
>[이전](project-structure.md)
>[다음](components.md)
