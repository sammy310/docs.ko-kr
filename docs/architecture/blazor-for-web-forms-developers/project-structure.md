---
title: 블레이저 앱의 프로젝트 구조
description: ASP.NET 웹 양식 및 Blazor 프로젝트의 프로젝트 구조를 비교하는 방법을 알아봅니다.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 2c383e86ff22f5a3460476998992b66e9417cc11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401744"
---
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="0236c-103">블레이저 앱의 프로젝트 구조</span><span class="sxs-lookup"><span data-stu-id="0236c-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="0236c-104">ASP.NET 웹 폼과 블레이저(Blazor)는 프로젝트 구조의 큰 차이에도 불구하고 비슷한 개념을 많이 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="0236c-105">여기서는 Blazor 프로젝트의 구조를 살펴보고 ASP.NET 웹 폼 프로젝트와 비교하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="0236c-106">첫 번째 Blazor 앱을 만들려면 [Blazor](/aspnet/core/blazor/get-started)시작 단계의 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="0236c-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="0236c-107">지침에 따라 블레이저 서버 앱 또는 ASP.NET 코어에서 호스팅되는 블레이저 웹어셈블리 앱을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="0236c-108">호스팅 모델별 논리를 제외하고 두 프로젝트의 대부분의 코드는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="0236c-109">프로젝트 파일</span><span class="sxs-lookup"><span data-stu-id="0236c-109">Project file</span></span>

<span data-ttu-id="0236c-110">블레이저 서버 앱은 .NET 코어 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-110">Blazor Server apps are .NET Core projects.</span></span> <span data-ttu-id="0236c-111">Blazor Server 앱의 프로젝트 파일은 다음과 같이 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="0236c-112">Blazor WebAssembly 앱의 프로젝트 파일은 약간 더 관련이 있는 것처럼 보입니다(정확한 버전 번호는 다를 수 있음).</span><span class="sxs-lookup"><span data-stu-id="0236c-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

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

<span data-ttu-id="0236c-113">Blazor 웹 어셈블리 프로젝트는 웹 Assembly 기반 .NET 런타임의 브라우저에서 실행되기 때문에 .NET 코어 대신 .NET 표준을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-113">Blazor WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="0236c-114">서버 나 개발자 컴퓨터에서 할 수 있는 것처럼 웹 브라우저에 .NET을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="0236c-115">따라서 프로젝트는 개별 패키지 참조를 사용하여 Blazor 프레임워크를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="0236c-116">이에 비해 기본 ASP.NET Web Forms 프로젝트에는 *.csproj* 파일에 거의 300줄의 XML이 포함되어 있으며, 대부분은 프로젝트의 다양한 코드 및 콘텐츠 파일을 명시적으로 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="0236c-117">.NET Core 및 .NET 표준 기반 프로젝트의 많은 단순화는 단순히 웹 SDK라고도 하는 `Microsoft.NET.Sdk.Web` SDK를 참조하여 가져온 기본 대상 및 속성에서 비롯됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="0236c-118">Web SDK에는 프로젝트에 코드 및 콘텐츠 파일을 포함시키는 것을 간소화하는 와일드카드 및 기타 편의가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="0236c-119">파일을 명시적으로 나열할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="0236c-120">.NET 코어를 대상으로 할 때 웹 SDK는 .NET 코어와 ASP.NET 코어 공유 프레임워크 모두에 프레임워크 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="0236c-121">프레임워크는 **솔루션 탐색기** 창의 **종속성** > **프레임워크** 노드에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="0236c-122">공유 프레임워크는 .NET Core를 설치할 때 컴퓨터에 설치된 어셈블리의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="0236c-123">지원되지만 .NET Core 프로젝트에서개별 어셈블리 참조는 덜 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="0236c-124">대부분의 프로젝트 종속성은 NuGet 패키지 참조로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="0236c-125">.NET Core 프로젝트에서 최상위 패키지 종속성만 참조하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="0236c-126">전이 종속성은 자동으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="0236c-127">ASP.NET Web Forms 프로젝트에서 흔히 볼 수 있는 *packages.config* 파일을 사용하여 패키지를 참조하는 `<PackageReference>` 대신 패키지 참조가 요소를 사용하여 프로젝트 파일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="0236c-128">진입점</span><span class="sxs-lookup"><span data-stu-id="0236c-128">Entry point</span></span>

<span data-ttu-id="0236c-129">Blazor Server 앱의 진입점은 콘솔 앱에서 볼 수 있는 *것처럼 Program.cs* 파일에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="0236c-130">앱이 실행되면 웹 앱과 관련된 기본값을 사용하여 웹 호스트 인스턴스를 만들고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="0236c-131">웹 호스트는 Blazor Server 앱의 수명 주기를 관리하고 호스트 수준 서비스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="0236c-132">이러한 서비스의 예로는 구성, 로깅, 종속성 주입 및 HTTP 서버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="0236c-133">이 코드는 대부분 상용구이며 종종 변경되지 않은 상태로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-133">This code is mostly boilerplate and is often left unchanged.</span></span>

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

<span data-ttu-id="0236c-134">Blazor 웹 어셈블리 앱은 *Program.cs*진입점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-134">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="0236c-135">코드는 약간 다르게 보입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-135">The code looks slightly different.</span></span> <span data-ttu-id="0236c-136">코드는 앱에 동일한 호스트 수준 서비스를 제공하도록 앱 호스트를 설정한다는 점에서 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="0236c-137">그러나 WebAssembly 앱 호스트는 브라우저에서 직접 실행되므로 HTTP 서버를 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="0236c-138">Blazor 앱에는 `Startup` 앱의 시작 논리를 정의하는 *Global.asax* 파일 대신 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-138">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="0236c-139">클래스는 `Startup` 앱 및 앱 별 서비스를 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="0236c-140">Blazor Server 앱에서 `Startup` 클래스는 클라이언트 브라우저와 서버 간에 Blazor가 사용하는 실시간 연결에 대한 끝점을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="0236c-141">Blazor WebAssembly 앱에서 `Startup` 클래스는 앱의 루트 구성 요소와 렌더링 위치를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="0236c-142">앱 `Startup` [시작](./app-startup.md) 섹션에서 클래스를 자세히 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="0236c-143">정적 파일</span><span class="sxs-lookup"><span data-stu-id="0236c-143">Static files</span></span>

<span data-ttu-id="0236c-144">ASP.NET Web Forms 프로젝트와 달리 Blazor 프로젝트의 모든 파일을 정적 파일로 요청할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="0236c-145">*wwwroot* 폴더의 파일만 웹 주소 지정이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="0236c-146">이 폴더는 앱의 "웹 루트"라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="0236c-147">앱의 웹 루트 외부의 모든 것은 웹 주소 지정이 *가능하지 않습니다.*</span><span class="sxs-lookup"><span data-stu-id="0236c-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="0236c-148">이 설정은 웹을 통해 프로젝트 파일이 실수로 노출되는 것을 방지하는 추가 보안 수준을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="0236c-149">구성</span><span class="sxs-lookup"><span data-stu-id="0236c-149">Configuration</span></span>

<span data-ttu-id="0236c-150">ASP.NET Web Forms 앱의 구성은 일반적으로 하나 이상의 *web.config* 파일을 사용하여 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="0236c-151">Blazor 앱에는 일반적으로 *web.config* 파일이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-151">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="0236c-152">이 경우 파일은 IIS에서 호스팅될 때만 IIS 관련 설정을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="0236c-153">대신 Blazor Server 앱은 ASP.NET 핵심 구성 추상화를 사용합니다(Blazor WebAssembly 앱은 현재 동일한 구성 추상화를 지원하지 않지만 나중에 추가된 기능일 수 있음).</span><span class="sxs-lookup"><span data-stu-id="0236c-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="0236c-154">예를 들어, 기본 Blazor Server 앱은 *appsettings.json 의*일부 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="0236c-155">구성 [섹션에서](./config.md) 핵심 프로젝트의 구성에 대해 자세히 알아봅니다ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0236c-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="0236c-156">Razor 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0236c-156">Razor components</span></span>

<span data-ttu-id="0236c-157">Blazor 프로젝트의 대부분의 파일은 *.razor* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="0236c-158">Razor는 웹 UI를 동적으로 생성하는 데 사용되는 HTML 및 C#을 기반으로 하는 템플릿 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="0236c-159">*.razor* 파일은 앱의 UI를 구성하는 구성 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="0236c-160">대부분의 경우 구성 요소는 블레이저 서버와 블레이저 웹 어셈블리 앱 모두에 대해 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="0236c-161">Blazor의 구성 요소는 ASP.NET 웹 양식의 사용자 컨트롤과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="0236c-162">각 Razor 구성 요소 파일은 프로젝트를 빌드할 때 .NET 클래스로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="0236c-163">생성된 클래스는 구성 요소의 상태, 렌더링 논리, 수명 주기 메서드, 이벤트 처리기 및 기타 논리를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="0236c-164">블레이저 섹션을 사용하여 [재사용 가능한 UI 구성 요소 작성에](./components.md) 대해 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="0236c-165">*_Imports.razor* 파일은 Razor 구성 요소 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="0236c-166">대신 동일한 폴더 와 하위 폴더에 있는 다른 *.razor* 파일로 가져올 Razor 지시문 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="0236c-167">예를 들어 *_Imports.razor* 파일은 일반적으로 사용되는 `using` 네임스페이스에 대한 문을 추가하는 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-167">For example, a *_Imports.razor* file is a conventional way to add `using` statements for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="0236c-168">페이지</span><span class="sxs-lookup"><span data-stu-id="0236c-168">Pages</span></span>

<span data-ttu-id="0236c-169">Blazor 앱의 페이지는 어디에 있습니까?</span><span class="sxs-lookup"><span data-stu-id="0236c-169">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="0236c-170">Blazor는 ASP.NET 웹 폼 앱의 *.aspx* 파일과 같이 주소 지정이 가능한 페이지에 대해 별도의 파일 확장프로그램을 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-170">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="0236c-171">대신, 페이지는 구성 요소에 경로를 할당하 여 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="0236c-172">경로는 일반적으로 `@page` Razor 지시문을 사용하여 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="0236c-173">예를 들어 `Counter` *페이지/Counter.razor* 파일에 작성된 구성 요소는 다음 경로를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="0236c-174">Blazor의 라우팅은 서버가 아닌 클라이언트 측에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="0236c-175">사용자가 브라우저에서 탐색할 때 Blazor는 탐색을 가로챈 다음 일치하는 경로로 구성 요소를 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="0236c-176">구성 요소 경로는 *현재 .aspx* 페이지와 같이 구성 요소의 파일 위치에 의해 유추되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="0236c-177">이 기능은 나중에 추가될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-177">This feature may be added in the future.</span></span> <span data-ttu-id="0236c-178">각 경로는 구성 요소에 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="0236c-179">*페이지* 폴더에 라우팅 가능한 구성 요소를 저장하는 것은 특별한 의미가 없으며 순전히 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="0236c-180">페이지, 라우팅 및 레이아웃 섹션에서 Blazor의 라우팅에 대해 자세히 [살펴보겠습니다.](./pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="0236c-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="0236c-181">레이아웃</span><span class="sxs-lookup"><span data-stu-id="0236c-181">Layout</span></span>

<span data-ttu-id="0236c-182">ASP.NET 웹 폼 앱에서 일반적인 페이지 레이아웃은 마스터*페이지(Site.Master)를*사용하여 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="0236c-183">Blazor 앱에서 페이지 레이아웃은 레이아웃 구성*요소(공유/MainLayout.razor)를*사용하여 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="0236c-184">레이아웃 구성 요소는 페이지, 라우팅 및 레이아웃 섹션에서 자세히 [설명합니다.](./pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="0236c-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="0236c-185">부트스트랩 블레이저</span><span class="sxs-lookup"><span data-stu-id="0236c-185">Bootstrap Blazor</span></span>

<span data-ttu-id="0236c-186">블레이저 부트 스트랩하려면 앱이 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="0236c-187">페이지에서 루트 구성*요소(App.Razor)를*렌더링할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="0236c-188">해당 Blazor 프레임워크 스크립트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="0236c-189">Blazor Server 앱에서 루트 구성 요소의 호스트 페이지는 *_Host.cshtml* 파일에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="0236c-190">이 파일은 구성 요소가 아닌 Razor 페이지를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="0236c-191">Razor 페이지는 Razor 구문을 사용하여 *.aspx* 페이지와 매우 유사하게 서버 주소 지정 이 가능한 페이지를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="0236c-192">이 `Html.RenderComponentAsync<TComponent>(RenderMode)` 메서드는 루트 수준 구성 요소를 렌더링할 위치를 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="0236c-193">이 `RenderMode` 옵션은 구성 요소를 렌더링하는 방식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="0236c-194">다음 표에서는 지원되는 `RenderMode` 옵션에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="0236c-195">옵션</span><span class="sxs-lookup"><span data-stu-id="0236c-195">Option</span></span>                        |<span data-ttu-id="0236c-196">Description</span><span class="sxs-lookup"><span data-stu-id="0236c-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="0236c-197">브라우저와의 연결이 설정되면 대화식으로 렌더링</span><span class="sxs-lookup"><span data-stu-id="0236c-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="0236c-198">먼저 미리 렌더링한 다음 대화형으로 렌더링</span><span class="sxs-lookup"><span data-stu-id="0236c-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="0236c-199">정적 콘텐츠로 렌더링</span><span class="sxs-lookup"><span data-stu-id="0236c-199">Rendered as static content</span></span>|

<span data-ttu-id="0236c-200">*_framework/blazor.server.js에* 대한 스크립트 참조는 서버와의 실시간 연결을 설정한 다음 모든 사용자 상호 작용 및 UI 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="0236c-201">Blazor WebAssembly 앱에서 호스트 페이지는 *wwwroot/index.html*아래의 간단한 정적 HTML 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="0236c-202">이 `<app>` 요소는 루트 구성 요소를 렌더링할 위치를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

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

<span data-ttu-id="0236c-203">렌더링할 특정 구성 요소는 해당 CSS `Startup.Configure` 선택기로 구성요소를 렌더링해야 하는 위치를 나타내는 앱의 메서드에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

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

## <a name="build-output"></a><span data-ttu-id="0236c-204">빌드 출력</span><span class="sxs-lookup"><span data-stu-id="0236c-204">Build output</span></span>

<span data-ttu-id="0236c-205">Blazor 프로젝트가 빌드되면 모든 Razor 구성 요소와 코드 파일이 단일 어셈블리로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="0236c-206">ASP.NET Web Forms 프로젝트와 달리 Blazor는 UI 논리의 런타임 컴파일을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="0236c-207">앱 실행</span><span class="sxs-lookup"><span data-stu-id="0236c-207">Run the app</span></span>

<span data-ttu-id="0236c-208">Blazor 서버 앱을 실행하려면 `F5` Visual Studio를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="0236c-209">Blazor 앱은 런타임 컴파일을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-209">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="0236c-210">코드 및 구성 요소 태그 변경 결과를 보려면 디버거가 연결된 앱을 다시 빌드하고 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="0236c-211">`Ctrl+F5`() 디버거가 첨부되지 않고 실행하는 경우 Visual Studio는 파일 변경을 감시하고 변경이 이루어지면 앱을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="0236c-212">변경 사항이 있을 때 브라우저를 수동으로 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="0236c-213">Blazor 웹 Assembly 앱을 실행하려면 다음 방법 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="0236c-214">개발 서버를 사용하여 클라이언트 프로젝트를 직접 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="0236c-215">ASP.NET Core로 앱을 호스팅할 때 서버 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="0236c-216">블레이저 웹어셈블리 앱은 Visual Studio를 사용하여 디버깅을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-216">Blazor WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="0236c-217">앱을 실행하려면 `Ctrl+F5` `F5`을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="0236c-218">대신 브라우저에서 직접 Blazor 웹 Assembly 앱을 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="0236c-219">자세한 내용은 [디버그 ASP.NET 코어 블레이저를](/aspnet/core/blazor/debug) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0236c-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0236c-220">[이전](hosting-models.md)
>[다음](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="0236c-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
