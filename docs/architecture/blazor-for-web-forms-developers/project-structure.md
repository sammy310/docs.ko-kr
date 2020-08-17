---
title: 앱에 대 한 프로젝트 구조 Blazor
description: ASP.NET Web Forms 및 프로젝트의 프로젝트 구조를 비교 하는 방법을 알아봅니다 Blazor .
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 09/11/2019
ms.openlocfilehash: 225ebbdd5e23516ae7d5465371e95c73c440c82b
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267778"
---
# <a name="project-structure-for-no-locblazor-apps"></a>앱에 대 한 프로젝트 구조 Blazor

중요 한 프로젝트 구조 차이에도 불구 하 고 ASP.NET Web Forms 하 고 Blazor 다양 한 개념을 공유 합니다. 여기서는 프로젝트의 구조를 살펴보고 Blazor ASP.NET Web Forms 프로젝트와 비교 합니다.

첫 번째 앱을 만들려면 Blazor [ Blazor 시작 단계의](/aspnet/core/blazor/get-started)지침을 따르세요. 지침에 따라 Blazor 서버 앱 또는 Blazor WebAssembly ASP.NET Core에서 호스트 되는 앱을 만들 수 있습니다. 호스팅 모델 관련 논리를 제외 하 고, 두 프로젝트의 대부분의 코드는 동일 합니다.

## <a name="project-file"></a>프로젝트 파일

Blazor 서버 앱은 .NET Core 프로젝트입니다. 서버 앱에 대 한 프로젝트 파일은 다음과 같이 간단 하 게 Blazor 가져올 수 있습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

앱에 대 한 프로젝트 파일은 Blazor WebAssembly 약간 더 복잡 합니다. 정확한 버전 번호는 다를 수 있습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <RazorLangVersion>3.0</RazorLangVersion>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Blazor" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.Build" Version="3.1.0" PrivateAssets="all" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.HttpClient" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.DevServer" Version="3.1.0" PrivateAssets="all" />
  </ItemGroup>

  <ItemGroup>
    <ProjectReference Include="..\Shared\BlazorWebAssemblyApp1.Shared.csproj" />
  </ItemGroup>

</Project>
```

BlazorWebAssembly프로젝트는 기반 .net 런타임의 브라우저에서 실행 되므로 .Net Core 대신 .NET Standard를 대상 WebAssembly 으로 합니다. 서버 또는 개발자 컴퓨터에서 사용할 수 있는 것과 같은 방법으로 웹 브라우저에 .NET을 설치할 수 없습니다. 따라서 프로젝트는 Blazor 개별 패키지 참조를 사용 하 여 프레임 워크를 참조 합니다.

비교 하 여 기본 ASP.NET Web Forms 프로젝트에는 *.csproj* 파일에 거의 300 줄의 XML이 포함 되어 있으며, 대부분의 XML은 프로젝트의 다양 한 코드 및 콘텐츠 파일을 명시적으로 나열 합니다. .NET Core 및 .NET Standard 기반 프로젝트의 많은 단순화는 sdk를 참조 하 여 가져온 기본 대상 및 속성에서 제공 됩니다 `Microsoft.NET.Sdk.Web` . 일반적으로 웹 sdk 라고 합니다. 웹 SDK에는 프로젝트에 코드 및 콘텐츠 파일의 포함을 간소화 하는 와일드 카드 및 기타 편리 하며 포함 되어 있습니다. 파일을 명시적으로 나열할 필요가 없습니다. .NET Core를 대상으로 하는 경우 웹 SDK는 .NET Core 및 ASP.NET Core 공유 프레임 워크에 대 한 프레임 워크 참조도 추가 합니다. 프레임 워크는 솔루션 탐색기 창의 **종속성**  >  **프레임 워크** 노드에서 볼 수 **Solution Explorer** 있습니다. 공유 프레임 워크는 .NET Core를 설치할 때 컴퓨터에 설치 된 어셈블리의 컬렉션입니다.

지원 되기는 하지만 개별 어셈블리 참조는 .NET Core 프로젝트에서 더 일반적이 지 않습니다. 대부분의 프로젝트 종속성은 NuGet 패키지 참조로 처리 됩니다. .NET Core 프로젝트에서 최상위 패키지 종속성을 참조 하기만 하면 됩니다. 전이적 종속성이 자동으로 포함 됩니다. ASP.NET Web Forms 프로젝트에서 일반적으로 발견 되는 *packages.config* 파일을 사용 하는 대신 패키지 참조는 요소를 사용 하 여 프로젝트 파일에 추가 됩니다 `<PackageReference>` .

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>진입점

Blazor서버 앱의 진입점은 콘솔 앱에서 볼 수 있는 것 처럼 *Program.cs* 파일에 정의 됩니다. 앱이 실행 되 면 웹 앱과 관련 된 기본값을 사용 하 여 웹 호스트 인스턴스를 만들고 실행 합니다. 웹 호스트는 Blazor 서버 앱의 수명 주기를 관리 하 고 호스트 수준 서비스를 설정 합니다. 이러한 서비스의 예로는 구성, 로깅, 종속성 주입 및 HTTP 서버가 있습니다. 이 코드는 대부분 상용구 이며 변경 되지 않은 상태로 유지 되는 경우가 많습니다.

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

BlazorWebAssembly또한 앱은 *Program.cs*에서 진입점을 정의 합니다. 코드는 약간 다르게 보입니다. 코드는 앱 호스트를 설정 하 여 앱에 동일한 호스트 수준 서비스를 제공 한다는 점에서 유사 합니다. WebAssembly그러나 응용 프로그램 호스트는 브라우저에서 직접 실행 되므로 HTTP 서버를 설정 하지 않습니다.

Blazor 앱에는 `Startup` 응용 프로그램에 대 한 시작 논리를 정의 하 *는 global.asax* 파일 대신 클래스가 있습니다. `Startup`클래스는 앱 및 앱 별 서비스를 구성 하는 데 사용 됩니다. Blazor서버 앱에서 `Startup` 클래스는 Blazor 클라이언트 브라우저와 서버 간에에서 사용 되는 실시간 연결에 대 한 끝점을 설정 하는 데 사용 됩니다. 앱에서 Blazor WebAssembly `Startup` 클래스는 앱의 루트 구성 요소를 정의 하 고 렌더링 해야 하는 위치를 정의 합니다. `Startup` [앱 시작](./app-startup.md) 섹션의 클래스를 자세히 살펴보겠습니다.

## <a name="static-files"></a>정적 파일

ASP.NET Web Forms 프로젝트와 달리 프로젝트의 모든 파일을 Blazor 정적 파일로 요청할 수 있는 것은 아닙니다. *Wwwroot* 폴더의 파일만 웹 주소 지정할 수 있습니다. 이 폴더는 앱의 "웹 루트" 라고 합니다. 앱의 웹 루트 외부에 있는 모든 항목은 웹 주소 지정이 가능 *하지 않습니다* . 이 설치 프로그램은 웹을 통해 프로젝트 파일이 실수로 노출 되는 것을 방지 하는 추가 보안 수준을 제공 합니다.

## <a name="configuration"></a>구성

ASP.NET Web Forms apps의 구성은 일반적으로 하나 이상의 *web.config* 파일을 사용 하 여 처리 됩니다. Blazor 앱은 일반적으로 *web.config* 파일을 포함 하지 않습니다. 이 경우 IIS에서 호스팅되는 경우에만 파일이 IIS 관련 설정을 구성 하는 데 사용 됩니다. 대신, Blazor 서버 앱은 ASP.NET Core 구성 추상화를 사용 합니다 Blazor WebAssembly . 현재 앱은 동일한 구성 추상화를 지원 하지만 이후에 추가 된 기능 일 수 있습니다. 예를 들어 기본 Blazor 서버 앱은 *appsettings.js*에 일부 설정을 저장 합니다.

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  },
  "AllowedHosts": "*"
}
```

[구성 섹션에서](./config.md) ASP.NET Core 프로젝트의 구성에 대해 자세히 알아봅니다.

## <a name="razor-components"></a>Razor 구성 요소

프로젝트에서 대부분의 파일 Blazor 은 *razor* 파일입니다. Razor는 웹 UI를 동적으로 생성 하는 데 사용 되는 HTML 및 c #을 기반으로 하는 템플릿 언어입니다. *Razor* 파일은 앱의 UI를 구성 하는 구성 요소를 정의 합니다. 대부분의 경우 구성 요소는 서버와 앱 모두에서 동일 Blazor Blazor WebAssembly 합니다. 의 구성 요소 Blazor 는 ASP.NET Web Forms의 사용자 컨트롤과 유사 합니다.

각 Razor 구성 요소 파일은 프로젝트가 빌드될 때 .NET 클래스로 컴파일됩니다. 생성 된 클래스는 구성 요소의 상태, 렌더링 논리, 수명 주기 메서드, 이벤트 처리기 및 기타 논리를 캡처합니다. [다시 사용 Blazor 가능한 UI 구성 요소 빌드](./components.md) 섹션에서 구성 요소를 작성 하는 방법을 살펴보겠습니다.

*_Imports razor* 파일은 razor 구성 요소 파일이 아닙니다. 대신, 동일한 폴더와 해당 하위 폴더에 있는 다른 *razor* 파일로 가져오기 위한 razor 지시문 집합을 정의 합니다. 예를 들어 *_Imports razor* 파일은 `using` 일반적으로 사용 되는 네임 스페이스에 대 한 지시문을 추가 하는 일반적인 방법입니다.

```razor
@using System.Net.Http
@using Microsoft.AspNetCore.Authorization
@using Microsoft.AspNetCore.Components.Authorization
@using Microsoft.AspNetCore.Components.Forms
@using Microsoft.AspNetCore.Components.Routing
@using Microsoft.AspNetCore.Components.Web
@using Microsoft.JSInterop
@using BlazorApp1
@using BlazorApp1.Shared
```

## <a name="pages"></a>페이지

앱의 페이지는 어디에 Blazor 있나요? Blazor ASP.NET Web Forms apps의 *.aspx* 파일과 같이 주소 지정 가능한 페이지에 대 한 별도의 파일 확장명을 정의 하지 않습니다. 대신, 페이지는 구성 요소에 경로를 할당 하 여 정의 됩니다. 경로는 일반적으로 Razor 지시어를 사용 하 여 할당 됩니다 `@page` . 예를 들어 `Counter` *Pages/Counter. razor* 파일에서 작성 된 구성 요소는 다음 경로를 정의 합니다.

```razor
@page "/counter"
```

에서 라우팅은 Blazor 서버가 아닌 클라이언트 쪽에서 처리 됩니다. 사용자가 브라우저에서 탐색할 때는 Blazor 탐색을 가로채 고 일치 하는 경로를 사용 하 여 구성 요소를 렌더링 합니다.

현재 구성 요소 경로는 *.aspx* 페이지와 마찬가지로 구성 요소의 파일 위치에 의해 유추 되지 않습니다. 이 기능은 나중에 추가 될 수 있습니다. 각 경로는 구성 요소에서 명시적으로 지정 해야 합니다. 라우팅할 수 있는 구성 요소를 *Pages* 폴더에 저장 하는 것은 특별 한 의미가 없으며 전적으로 규칙입니다.

Blazor [페이지, 라우팅 및 레이아웃](./pages-routing-layouts.md) 섹션에서 라우팅하는 방법에 대해 더 자세히 살펴보겠습니다.

## <a name="layout"></a>Layout

ASP.NET Web Forms apps에서 일반 페이지 레이아웃은 마스터*페이지 (site.master*)를 사용 하 여 처리 됩니다. Blazor앱에서 페이지 레이아웃은 레이아웃 구성 요소 (*Shared/mainlayout. razor*)를 사용 하 여 처리 됩니다. 레이아웃 구성 요소는 [페이지, 라우팅 및 레이아웃](./pages-routing-layouts.md) 섹션에 자세히 설명 되어 있습니다.

## <a name="bootstrap-no-locblazor"></a>부트스트랩 Blazor

부트스트랩 하려면 Blazor 앱에서 다음을 수행 해야 합니다.

- 페이지에서 루트 구성 요소 (*응용 프로그램 Razor*)를 렌더링 해야 하는 위치를 지정 합니다.
- 해당 Blazor 프레임 워크 스크립트를 추가 합니다.

Blazor서버 앱에서 루트 구성 요소의 호스트 페이지는 *_Host. cshtml* 파일에 정의 되어 있습니다. 이 파일은 구성 요소가 아닌 Razor 페이지를 정의 합니다. Razor Pages Razor 구문를 사용 하 여 .aspx 페이지와 매우 유사한 서버 주소 지정 가능 페이지를 정의 합니다 *.* `Html.RenderComponentAsync<TComponent>(RenderMode)`메서드는 루트 수준 구성 요소를 렌더링 해야 하는 위치를 정의 하는 데 사용 됩니다. `RenderMode`옵션은 구성 요소가 렌더링 되는 방식을 나타냅니다. 다음 표에서는 지원 되는 옵션을 간략하게 설명 합니다 `RenderMode` .

|옵션                        |Description       |
|------------------------------|------------------|
|`RenderMode.Server`           |브라우저와의 연결이 설정 되 면 대화형으로 렌더링 됨|
|`RenderMode.ServerPrerendered`|첫 번째 미리 렌더링 된 대화형으로 렌더링|
|`RenderMode.Static`           |정적 콘텐츠로 렌더링 됨|

*_Framework/blazor.server.js* 에 대 한 스크립트 참조를 사용 하 여 서버와의 실시간 연결을 설정 하 고 모든 사용자 상호 작용 및 UI 업데이트를 처리 합니다.

```razor
@page "/"
@namespace BlazorApp1.Pages
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>BlazorApp1</title>
    <base href="~/" />
    <link rel="stylesheet" href="css/bootstrap/bootstrap.min.css" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>
        @(await Html.RenderComponentAsync<App>(RenderMode.ServerPrerendered))
    </app>

    <script src="_framework/blazor.server.js"></script>
</body>
</html>
```

앱에서 Blazor WebAssembly 호스트 페이지는 *wwwroot/index.html*아래의 간단한 정적 HTML 파일입니다. `<app>`요소는 루트 구성 요소가 렌더링 되어야 하는 위치를 나타내는 데 사용 됩니다.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>Loading...</app>

    <script src="_framework/blazor.webassembly.js"></script>
</body>
</html>
```

렌더링할 특정 구성 요소는 `Startup.Configure` 구성 요소가 렌더링 되어야 하는 위치를 나타내는 해당 CSS 선택기를 사용 하 여 앱의 메서드에서 구성 됩니다.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
    }

    public void Configure(IComponentsApplicationBuilder app)
    {
        app.AddComponent<App>("app");
    }
}
```

## <a name="build-output"></a>빌드 출력

프로젝트를 Blazor 빌드할 때 모든 Razor 구성 요소와 코드 파일은 단일 어셈블리로 컴파일됩니다. ASP.NET Web Forms 프로젝트와 달리에서는 Blazor UI 논리의 런타임 컴파일을 지원 하지 않습니다.

## <a name="run-the-app"></a>앱 실행

서버 앱을 실행 하려면 Blazor `F5` Visual Studio에서 키를 누릅니다. Blazor 앱은 런타임 컴파일을 지원 하지 않습니다. 코드 및 구성 요소 태그 변경의 결과를 확인 하려면 디버거가 연결 된 앱을 다시 빌드하고 다시 시작 합니다. 디버거를 연결 하지 않고 ()를 실행 하는 경우 `Ctrl+F5` Visual Studio는 파일 변경 내용을 감시 하 고 변경 내용이 적용 되 면 앱을 다시 시작 합니다. 변경 사항이 적용 되 면 브라우저를 수동으로 새로 고칩니다.

앱을 실행 하려면 Blazor WebAssembly 다음 방법 중 하나를 선택 합니다.

- 개발 서버를 사용 하 여 직접 클라이언트 프로젝트를 실행 합니다.
- ASP.NET Core를 사용 하 여 앱을 호스팅할 때 서버 프로젝트를 실행 합니다.

BlazorWebAssembly앱은 Visual Studio를 사용 하 여 디버깅을 지원 하지 않습니다. 앱을 실행 하려면 대신을 사용 `Ctrl+F5` `F5` 합니다. 대신 Blazor WebAssembly 브라우저에서 직접 앱을 디버그할 수 있습니다. 자세한 내용은 [디버그 Blazor ASP.NET Core](/aspnet/core/blazor/debug) 를 참조 하세요.

>[!div class="step-by-step"]
>[이전](hosting-models.md)
>[다음](app-startup.md)
