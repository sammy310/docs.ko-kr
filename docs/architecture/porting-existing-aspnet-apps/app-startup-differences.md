---
title: ASP.NET MVC와 ASP.NET Core 간의 앱 시작 차이점
description: ASP.NET MVC 및 ASP.NET Core는 앱이 시작 되는 방법에 따라 크게 다릅니다. 중요 한 차이점과 ASP.NET MVC에서 ASP.NET Core로 마이그레이션하는 방법에 대해 알아봅니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: eaf8d8fac42ddebbb944273b672666e0bd2b1a67
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401825"
---
# <a name="app-startup-differences-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="dcbbd-104">ASP.NET MVC와 ASP.NET Core 간의 앱 시작 차이점</span><span class="sxs-lookup"><span data-stu-id="dcbbd-104">App startup differences between ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="dcbbd-105">ASP.NET MVC 앱은 Windows 운영 체제에서 사용할 수 있는 기본 웹 서버인 IIS (인터넷 정보 서버) 내에 완전히 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-105">ASP.NET MVC apps lived entirely within Internet Information Server (IIS), the primary web server available on Windows operating systems.</span></span> <span data-ttu-id="dcbbd-106">ASP.NET MVC와 달리 ASP.NET Core 앱은 실행 가능한 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-106">Unlike ASP.NET MVC, ASP.NET Core apps are executable apps.</span></span> <span data-ttu-id="dcbbd-107">을 사용 하 여 명령줄에서 실행할 수 있습니다 `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="dcbbd-107">You can run them from the command line, using `dotnet run`.</span></span> <span data-ttu-id="dcbbd-108">모든 c # 프로그램, 일반적으로 `public static void Main()` 또는 유사 변형 (인수나 지원)과 같은 진입점 메서드가 있습니다 `async` .</span><span class="sxs-lookup"><span data-stu-id="dcbbd-108">They have an entry point method like all C# programs, typically `public static void Main()` or a similar variation (perhaps with arguments or `async` support).</span></span> <span data-ttu-id="dcbbd-109">이는 ASP.NET Core 및 ASP.NET MVC의 가장 큰 아키텍처 차이가 며 ASP.NET Core Windows 이외의 시스템에서 실행 될 수 있도록 하는 몇 가지 차이점 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-109">This is perhaps the biggest architectural difference between ASP.NET Core and ASP.NET MVC, and is one of several differences that allows ASP.NET Core to run on non-Windows systems.</span></span>

## <a name="aspnet-mvc-startup"></a><span data-ttu-id="dcbbd-110">ASP.NET MVC 시작</span><span class="sxs-lookup"><span data-stu-id="dcbbd-110">ASP.NET MVC Startup</span></span>

<span data-ttu-id="dcbbd-111">IIS 내에서 호스트 되는 ASP.NET apps는 IIS를 사용 하 여 특정 개체를 인스턴스화하고 요청이 도착 하면 특정 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-111">Hosted within IIS, ASP.NET apps rely on IIS to instantiate certain objects and call certain methods when a request arrives.</span></span> <span data-ttu-id="dcbbd-112">ASP.NET는에서 파생 되는 *global.asax* 파일의 클래스 인스턴스를 만듭니다 `HttpApplication` .</span><span class="sxs-lookup"><span data-stu-id="dcbbd-112">ASP.NET creates an instance of the *Global.asax* file's class, which derives from `HttpApplication`.</span></span> <span data-ttu-id="dcbbd-113">첫 번째 요청을 받으면 요청 자체를 처리 하기 전에 ASP.NET는 `Application_Start` *global.asax* 파일의 클래스에서 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-113">When the first request is received, before handling the request itself, ASP.NET calls the `Application_Start` method in the *Global.asax* file's class.</span></span> <span data-ttu-id="dcbbd-114">ASP.NET MVC 앱을 시작할 때 실행 해야 하는 모든 논리를이 메서드에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-114">Any logic that needs to run when the ASP.NET MVC app begins can be added to this method.</span></span>

<span data-ttu-id="dcbbd-115">ASP.NET MVC 및 Web API에 대 한 많은 NuGet 패키지는 [Webactivator](https://github.com/davidebbo/WebActivator) 패키지를 사용 하 여 앱을 시작 하는 동안 코드를 실행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-115">Many NuGet packages for ASP.NET MVC and Web API use the [WebActivator](https://github.com/davidebbo/WebActivator) package to let them run some code during app startup.</span></span> <span data-ttu-id="dcbbd-116">규칙에 따라이 코드는 일반적으로 *App_Start* 폴더에 추가 되 고 특성을 통해 즉시 실행 되거나 바로 뒤에 실행 되도록 구성 됩니다 `Application_Start` .</span><span class="sxs-lookup"><span data-stu-id="dcbbd-116">By convention, this code would typically be added to an *App_Start* folder and would be configured via attribute to run either immediately before or just after `Application_Start`.</span></span>

<span data-ttu-id="dcbbd-117">또한 [OWIN (Open Web Interface for .net) 및 ASP.NET MVC와 함께 Katana 프로젝트](/aspnet/aspnet/overview/owin-and-katana/getting-started-with-owin-and-katana)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-117">It's also possible to use the [Open Web Interface for .NET (OWIN) and Project Katana with ASP.NET MVC](/aspnet/aspnet/overview/owin-and-katana/getting-started-with-owin-and-katana).</span></span> <span data-ttu-id="dcbbd-118">이 작업을 수행할 때 앱은 ASP.NET Core 동작 방식과 매우 유사한 방식으로 요청 미들웨어를 설정 하는 *Startup.cs* 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-118">When doing so, the app will include a *Startup.cs* file that is responsible for setting up request middleware in a way that's very similar to how ASP.NET Core behaves.</span></span>

<span data-ttu-id="dcbbd-119">ASP.NET MVC 앱이 시작 될 때 코드를 실행 해야 하는 경우 일반적으로 이러한 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-119">If you need to run code when your ASP.NET MVC app starts up, it will typically use one of these approaches.</span></span>

## <a name="aspnet-core-startup"></a><span data-ttu-id="dcbbd-120">ASP.NET Core 시작</span><span class="sxs-lookup"><span data-stu-id="dcbbd-120">ASP.NET Core Startup</span></span>

<span data-ttu-id="dcbbd-121">앞에서 설명한 것 처럼 ASP.NET Core apps는 독립 실행형 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-121">As noted previously, ASP.NET Core apps are standalone programs.</span></span> <span data-ttu-id="dcbbd-122">따라서 일반적으로 앱에 대 한 진입점을 포함 하는 *Program.cs* 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-122">As such, they typically include a *Program.cs* file containing the entry point for the app.</span></span> <span data-ttu-id="dcbbd-123">이 파일의 일반적인 예는 그림 2-1에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-123">A typical example of this file is shown in Figure 2-1.</span></span>

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

<span data-ttu-id="dcbbd-124">**그림 2-1**.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-124">**Figure 2-1**.</span></span> <span data-ttu-id="dcbbd-125">일반적인 ASP.NET Core *Program.cs* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-125">A typical ASP.NET Core *Program.cs* file.</span></span>

<span data-ttu-id="dcbbd-126">그림 2-1에 표시 된 코드는 앱에 대 한 *호스트* 를 만들고, 빌드하고, 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-126">The code shown in Figure 2-1 creates a *host* for the app, builds it, and runs it.</span></span> <span data-ttu-id="dcbbd-127">ASP.NET Core 앱은 표시 된에 의해 구성 된 호스트 내에서 실행 됩니다 `IHostBuilder` .</span><span class="sxs-lookup"><span data-stu-id="dcbbd-127">The ASP.NET Core app runs within the host configured by the `IHostBuilder` shown.</span></span> <span data-ttu-id="dcbbd-128">를 사용 하 여 ASP.NET Core 앱을 완전히 구성할 수는 있지만 `IHostBuilder` 일반적으로이 작업은 클래스에서 수행 됩니다 `Startup` .</span><span class="sxs-lookup"><span data-stu-id="dcbbd-128">While it's possible to completely configure an ASP.NET Core app using the `IHostBuilder`, typically the bulk of this work is done in a `Startup` class.</span></span>

<span data-ttu-id="dcbbd-129">`Startup`클래스는 호스트에 및의 두 메서드를 `ConfigureServices` 노출 `Configure` 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-129">The `Startup` class exposes two methods to the host: `ConfigureServices` and `Configure`.</span></span> <span data-ttu-id="dcbbd-130">`ConfigureServices`메서드는 앱이 사용 하는 서비스와 해당 수명을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-130">The `ConfigureServices` method is used to define the services the app will use and their respective lifetimes.</span></span> <span data-ttu-id="dcbbd-131">`Configure`메서드는 미들웨어로 구성 된 요청 파이프라인을 설정 하 여 앱에 대 한 각 요청을 처리 하는 방법을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-131">The `Configure` method is used to define how each request to the app will be handled by setting up a request pipeline composed of middleware.</span></span>

<span data-ttu-id="dcbbd-132">앱의 서비스 또는 요청 파이프라인을 구성 하는 것과 관련 된 코드 외에 앱은 앱이 시작 될 때 실행 되어야 하는 다른 코드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-132">In addition to code related to configuring the app's services or request pipeline, apps may have other code that must run when the app begins.</span></span> <span data-ttu-id="dcbbd-133">이러한 코드는 일반적으로 *Program.cs* 에 배치 되거나로 등록 됩니다 .이는 `IHostedService` 앱이 시작 될 때 [일반 호스트](/aspnet/core/fundamentals/host/generic-host?preserve-view=true&view=aspnetcore-3.1) 에 의해 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-133">Such code is typically placed in *Program.cs* or registered as an `IHostedService`, which will be started by the [generic host](/aspnet/core/fundamentals/host/generic-host?preserve-view=true&view=aspnetcore-3.1) when the app starts.</span></span>

<span data-ttu-id="dcbbd-134">`IHostedService`인터페이스는 및의 두 메서드를 노출 합니다 `StartAsync` `StopAsync` .</span><span class="sxs-lookup"><span data-stu-id="dcbbd-134">The `IHostedService` interface just exposes two methods, `StartAsync` and `StopAsync`.</span></span> <span data-ttu-id="dcbbd-135">에서 인터페이스를 등록 하면 `ConfigureServices` 호스트에서 rest를 수행 하 여 앱이 `StartAsync` 시작 되기 전에 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-135">You register the interface in `ConfigureServices` and the host does the rest, calling the `StartAsync` method before the app starts up.</span></span>

## <a name="porting-considerations"></a><span data-ttu-id="dcbbd-136">포팅 고려 사항</span><span class="sxs-lookup"><span data-stu-id="dcbbd-136">Porting considerations</span></span>

<span data-ttu-id="dcbbd-137">앱을 ASP.NET MVC에서 ASP.NET Core 마이그레이션하려는 팀은 앱이 시작 될 때 실행 되는 코드를 식별 하 고 ASP.NET Core 앱에서 이러한 코드에 대 한 적절 한 위치를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-137">Teams looking to migrate their apps from ASP.NET MVC to ASP.NET Core need to identify what code is being run when their app starts up and determine the appropriate location for such code in their ASP.NET Core app.</span></span> <span data-ttu-id="dcbbd-138">앱이 시작 될 때, 특히 비동기 코드를 실행 하는 데 필요한 사용자 지정 코드의 경우 일반적으로 이러한 코드를 구현에 배치 하는 것이 좋습니다 `IHostedService` .</span><span class="sxs-lookup"><span data-stu-id="dcbbd-138">For custom code needed to run when the app starts up, especially async code, the recommended approach is typically to put such code into `IHostedService` implementations.</span></span>

## <a name="references"></a><span data-ttu-id="dcbbd-139">참조</span><span class="sxs-lookup"><span data-stu-id="dcbbd-139">References</span></span>

- <span data-ttu-id="dcbbd-140">[IIS 7에 대 한 ASP.NET 응용 프로그램 수명 주기 개요](/previous-versions/aspnet/bb470252(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dcbbd-140">[ASP.NET Application Life Cycle Overview for IIS 7](/previous-versions/aspnet/bb470252(v=vs.100))</span></span>
- <span data-ttu-id="dcbbd-141">[ASP.NET 응용 프로그램 수명 주기 개요 IIS 5 및 6](/previous-versions/aspnet/ms178473(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dcbbd-141">[ASP.NET Application Life Cycle Overview for IIS 5 and 6](/previous-versions/aspnet/ms178473(v=vs.100))</span></span>
- [<span data-ttu-id="dcbbd-142">OWIN 및 Katana 시작</span><span class="sxs-lookup"><span data-stu-id="dcbbd-142">Getting Started with OWIN and Katana</span></span>](/aspnet/aspnet/overview/owin-and-katana/getting-started-with-owin-and-katana)
- [<span data-ttu-id="dcbbd-143">WebActivator</span><span class="sxs-lookup"><span data-stu-id="dcbbd-143">WebActivator</span></span>](https://github.com/davidebbo/WebActivator)
- [<span data-ttu-id="dcbbd-144">ASP.NET Core에서 앱 시작</span><span class="sxs-lookup"><span data-stu-id="dcbbd-144">App Startup in ASP.NET Core</span></span>](/aspnet/core/fundamentals/startup?preserve-view=true&view=aspnetcore-3.1)
- [<span data-ttu-id="dcbbd-145">ASP.NET Core의 .NET 일반 호스트</span><span class="sxs-lookup"><span data-stu-id="dcbbd-145">.NET Generic Host in ASP.NET Core</span></span>](/aspnet/core/fundamentals/host/generic-host?preserve-view=true&view=aspnetcore-3.1)
- [<span data-ttu-id="dcbbd-146">IHostedService</span><span class="sxs-lookup"><span data-stu-id="dcbbd-146">IHostedService</span></span>](../microservices/multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md)

>[!div class="step-by-step"]
><span data-ttu-id="dcbbd-147">[이전](architectural-differences.md)
>[다음](hosting-differences.md)</span><span class="sxs-lookup"><span data-stu-id="dcbbd-147">[Previous](architectural-differences.md)
[Next](hosting-differences.md)</span></span>
