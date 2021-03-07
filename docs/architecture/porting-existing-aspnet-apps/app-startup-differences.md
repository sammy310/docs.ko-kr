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
# <a name="app-startup-differences-between-aspnet-mvc-and-aspnet-core"></a>ASP.NET MVC와 ASP.NET Core 간의 앱 시작 차이점

ASP.NET MVC 앱은 Windows 운영 체제에서 사용할 수 있는 기본 웹 서버인 IIS (인터넷 정보 서버) 내에 완전히 포함 됩니다. ASP.NET MVC와 달리 ASP.NET Core 앱은 실행 가능한 앱입니다. 을 사용 하 여 명령줄에서 실행할 수 있습니다 `dotnet run` . 모든 c # 프로그램, 일반적으로 `public static void Main()` 또는 유사 변형 (인수나 지원)과 같은 진입점 메서드가 있습니다 `async` . 이는 ASP.NET Core 및 ASP.NET MVC의 가장 큰 아키텍처 차이가 며 ASP.NET Core Windows 이외의 시스템에서 실행 될 수 있도록 하는 몇 가지 차이점 중 하나입니다.

## <a name="aspnet-mvc-startup"></a>ASP.NET MVC 시작

IIS 내에서 호스트 되는 ASP.NET apps는 IIS를 사용 하 여 특정 개체를 인스턴스화하고 요청이 도착 하면 특정 메서드를 호출 합니다. ASP.NET는에서 파생 되는 *global.asax* 파일의 클래스 인스턴스를 만듭니다 `HttpApplication` . 첫 번째 요청을 받으면 요청 자체를 처리 하기 전에 ASP.NET는 `Application_Start` *global.asax* 파일의 클래스에서 메서드를 호출 합니다. ASP.NET MVC 앱을 시작할 때 실행 해야 하는 모든 논리를이 메서드에 추가할 수 있습니다.

ASP.NET MVC 및 Web API에 대 한 많은 NuGet 패키지는 [Webactivator](https://github.com/davidebbo/WebActivator) 패키지를 사용 하 여 앱을 시작 하는 동안 코드를 실행할 수 있도록 합니다. 규칙에 따라이 코드는 일반적으로 *App_Start* 폴더에 추가 되 고 특성을 통해 즉시 실행 되거나 바로 뒤에 실행 되도록 구성 됩니다 `Application_Start` .

또한 [OWIN (Open Web Interface for .net) 및 ASP.NET MVC와 함께 Katana 프로젝트](/aspnet/aspnet/overview/owin-and-katana/getting-started-with-owin-and-katana)를 사용할 수 있습니다. 이 작업을 수행할 때 앱은 ASP.NET Core 동작 방식과 매우 유사한 방식으로 요청 미들웨어를 설정 하는 *Startup.cs* 파일을 포함 합니다.

ASP.NET MVC 앱이 시작 될 때 코드를 실행 해야 하는 경우 일반적으로 이러한 방법 중 하나를 사용 합니다.

## <a name="aspnet-core-startup"></a>ASP.NET Core 시작

앞에서 설명한 것 처럼 ASP.NET Core apps는 독립 실행형 프로그램입니다. 따라서 일반적으로 앱에 대 한 진입점을 포함 하는 *Program.cs* 파일을 포함 합니다. 이 파일의 일반적인 예는 그림 2-1에 나와 있습니다.

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

**그림 2-1**. 일반적인 ASP.NET Core *Program.cs* 파일입니다.

그림 2-1에 표시 된 코드는 앱에 대 한 *호스트* 를 만들고, 빌드하고, 실행 합니다. ASP.NET Core 앱은 표시 된에 의해 구성 된 호스트 내에서 실행 됩니다 `IHostBuilder` . 를 사용 하 여 ASP.NET Core 앱을 완전히 구성할 수는 있지만 `IHostBuilder` 일반적으로이 작업은 클래스에서 수행 됩니다 `Startup` .

`Startup`클래스는 호스트에 및의 두 메서드를 `ConfigureServices` 노출 `Configure` 합니다. `ConfigureServices`메서드는 앱이 사용 하는 서비스와 해당 수명을 정의 하는 데 사용 됩니다. `Configure`메서드는 미들웨어로 구성 된 요청 파이프라인을 설정 하 여 앱에 대 한 각 요청을 처리 하는 방법을 정의 하는 데 사용 됩니다.

앱의 서비스 또는 요청 파이프라인을 구성 하는 것과 관련 된 코드 외에 앱은 앱이 시작 될 때 실행 되어야 하는 다른 코드가 있을 수 있습니다. 이러한 코드는 일반적으로 *Program.cs* 에 배치 되거나로 등록 됩니다 .이는 `IHostedService` 앱이 시작 될 때 [일반 호스트](/aspnet/core/fundamentals/host/generic-host?preserve-view=true&view=aspnetcore-3.1) 에 의해 시작 됩니다.

`IHostedService`인터페이스는 및의 두 메서드를 노출 합니다 `StartAsync` `StopAsync` . 에서 인터페이스를 등록 하면 `ConfigureServices` 호스트에서 rest를 수행 하 여 앱이 `StartAsync` 시작 되기 전에 메서드를 호출 합니다.

## <a name="porting-considerations"></a>포팅 고려 사항

앱을 ASP.NET MVC에서 ASP.NET Core 마이그레이션하려는 팀은 앱이 시작 될 때 실행 되는 코드를 식별 하 고 ASP.NET Core 앱에서 이러한 코드에 대 한 적절 한 위치를 결정 해야 합니다. 앱이 시작 될 때, 특히 비동기 코드를 실행 하는 데 필요한 사용자 지정 코드의 경우 일반적으로 이러한 코드를 구현에 배치 하는 것이 좋습니다 `IHostedService` .

## <a name="references"></a>참조

- [IIS 7에 대 한 ASP.NET 응용 프로그램 수명 주기 개요](/previous-versions/aspnet/bb470252(v=vs.100))
- [ASP.NET 응용 프로그램 수명 주기 개요 IIS 5 및 6](/previous-versions/aspnet/ms178473(v=vs.100))
- [OWIN 및 Katana 시작](/aspnet/aspnet/overview/owin-and-katana/getting-started-with-owin-and-katana)
- [WebActivator](https://github.com/davidebbo/WebActivator)
- [ASP.NET Core에서 앱 시작](/aspnet/core/fundamentals/startup?preserve-view=true&view=aspnetcore-3.1)
- [ASP.NET Core의 .NET 일반 호스트](/aspnet/core/fundamentals/host/generic-host?preserve-view=true&view=aspnetcore-3.1)
- [IHostedService](../microservices/multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md)

>[!div class="step-by-step"]
>[이전](architectural-differences.md)
>[다음](hosting-differences.md)
