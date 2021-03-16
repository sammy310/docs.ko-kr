---
title: .NET 일반 호스트
author: IEvangelist
description: 앱 시작 및 수명 관리를 담당하는 .NET 제네릭 호스트에 대해 알아봅니다.
ms.author: dapine
ms.date: 12/18/2020
ms.openlocfilehash: bf6d5ad624bbed46994633abace0af64712757f3
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "102402121"
---
# <a name="net-generic-host"></a>.NET 일반 호스트

작업자 서비스 템플릿은 .NET 제네릭 호스트 <xref:Microsoft.Extensions.Hosting.HostBuilder>를 만듭니다. 제네릭 호스트는 콘솔 앱과 같은 다른 유형의 .NET 애플리케이션과 함께 사용할 수 있습니다.

*호스트* 는 다음과 같이 앱의 리소스를 캡슐화하는 개체입니다.

- DI(종속성 주입)
- 로깅
- Configuration
- `IHostedService` 구현

호스트가 시작될 때 서비스 컨테이너의 호스티드 서비스 컬렉션에 등록된 <xref:Microsoft.Extensions.Hosting.IHostedService>의 각 구현에서 <xref:Microsoft.Extensions.Hosting.IHostedService.StartAsync%2A?displayProperty=nameWithType>을 호출합니다. 작업자 서비스 앱에서 <xref:Microsoft.Extensions.Hosting.BackgroundService> 인스턴스를 포함하는 모든 `IHostedService` 구현은 <xref:Microsoft.Extensions.Hosting.BackgroundService.ExecuteAsync%2A?displayProperty=nameWithType> 메서드를 호출합니다.

하나의 개체에 앱의 모든 상호 종속적 리소스를 포함하는 주요 원인은 수명 관리 즉, 앱 시작 및 종료에 대한 제어 때문입니다. 이는 [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) NuGet 패키지를 사용하여 수행됩니다.

## <a name="set-up-a-host"></a>호스트 설정

호스트는 일반적으로 `Program` 클래스의 코드로 구성, 빌드 및 실행됩니다. `Main` 메서드는 다음 작업을 수행합니다.

- <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder> 메서드를 호출하여 작성기 개체를 만들고 구성합니다.
- <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build>를 호출하여 <xref:Microsoft.Extensions.Hosting.IHost> 인스턴스를 만듭니다.
- 호스트 개체에 대해 <xref:Microsoft.Extensions.Hosting.HostingAbstractionsHostExtensions.Run%2A> 또는 <xref:Microsoft.Extensions.Hosting.HostingAbstractionsHostExtensions.RunAsync%2A> 메서드를 호출합니다.

.NET 작업자 서비스 템플릿은 다음과 같은 코드를 생성하여 제네릭 호스트를 만듭니다.

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureServices((hostContext, services) =>
            {
                services.AddHostedService<Worker>();
            });
}
```

## <a name="default-builder-settings"></a>기본 작성기 설정

<xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A> 메서드는 다음 작업을 수행합니다.

- 콘텐츠 루트를 <xref:System.IO.Directory.GetCurrentDirectory>에서 반환된 경로로 설정합니다.
- 다음에서 [호스트 구성](#host-configuration)을 로드합니다.
  - 접두사가 `DOTNET_`인 환경 변수.
  - 명령줄 인수.
- 다음에서 앱 구성을 로드합니다.
  - *appsettings.json*.
  - *appsettings.{Environment}.json*.
  - 비밀 관리자: 앱이 `Development` 환경에서 실행되는 경우
  - 환경 변수.
  - 명령줄 인수.
- 다음 로깅 공급자를 추가합니다.
  - Console
  - Debug
  - EventSource
  - EventLog(Windows에서 실행 중인 경우에만)
- 환경이 `Development`일 때 범위 유효성 검사 및 [종속성 유효성 검사](xref:Microsoft.Extensions.DependencyInjection.ServiceProviderOptions.ValidateOnBuild)를 사용하도록 설정합니다.

`ConfigureServices` 메서드는 <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection?displayProperty=nameWithType> 인스턴스에 서비스를 추가하는 기능을 노출합니다. 나중에 종속성 주입에서 이러한 서비스를 사용할 수 있습니다.

## <a name="framework-provided-services"></a>프레임워크에서 제공하는 서비스

다음 서비스가 자동으로 등록됩니다.

- [IHostApplicationLifetime](#ihostapplicationlifetime)
- [IHostLifetime](#ihostlifetime)
- [IHostEnvironment](#ihostenvironment)

## <a name="ihostapplicationlifetime"></a>IHostApplicationLifetime

<xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime> 서비스를 모든 클래스에 주입하여 시작 후 및 정상 종료 작업을 처리합니다. 인터페이스의 세 가지 속성은 앱 시작 및 앱 중지 이벤트 처리기 메서드를 등록하는 데 사용되는 취소 토큰입니다. 인터페이스에는 <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime.StopApplication> 메서드도 포함됩니다.

다음 예제는 `IHostApplicationLifetime` 이벤트를 등록하는 `IHostedService` 구현입니다.

:::code language="csharp" source="snippets/configuration/app-lifetime/ExampleHostedService.cs" highlight="18-20":::

`ExampleHostedService` 구현을 추가하도록 작업자 서비스 템플릿을 수정할 수 있습니다.

:::code language="csharp" source="snippets/configuration/app-lifetime/Program.cs" range="1-16,36" highlight="15":::

애플리케이션은 다음 샘플 출력을 작성합니다.

:::code language="csharp" source="snippets/configuration/app-lifetime/Program.cs" range="17-35":::

## <a name="ihostlifetime"></a>IHostLifetime

<xref:Microsoft.Extensions.Hosting.IHostLifetime> 구현은 호스트가 시작될 때와 중지될 때를 제어합니다. 등록된 마지막 구현이 사용됩니다.

`Microsoft.Extensions.Hosting.Internal.ConsoleLifetime`은 기본 `IHostLifetime` 구현입니다. `ConsoleLifetime`:

- <kbd>Ctrl</kbd>+<kbd>C</kbd>, [SIGINT](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGINT) 또는 [SIGTERM](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGTERM)을 수신 대기하고 <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime.StopApplication%2A>을 호출하여 종료 프로세스를 시작합니다.
- `RunAsync` 및 `WaitForShutdownAsync`와 같은 확장의 차단을 해제합니다.

## <a name="ihostenvironment"></a>IHostEnvironment

<xref:Microsoft.Extensions.Hosting.IHostEnvironment> 서비스를 클래스에 삽입하여 다음 설정에 대한 정보를 가져옵니다.

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.ApplicationName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.ContentRootFileProvider?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.ContentRootPath?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.EnvironmentName?displayProperty=nameWithType>

## <a name="host-configuration"></a>호스트 구성

호스트 구성은 [IHostEnvironment](#ihostenvironment) 구현의 속성을 구성하는 데 사용됩니다.

호스트 구성은 <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureAppConfiguration%2A> 메서드 내의 [HostBuilderContext.Configuration](xref:Microsoft.Extensions.Hosting.HostBuilderContext.Configuration)에 있습니다. `ConfigureAppConfiguration` 메서드를 호출할 때 `HostBuilderContext` 및 `IConfigurationBuilder`가 `configureDelegate`에 전달됩니다. `configureDelegate`는 `Action<HostBuilderContext, IConfigurationBuilder>`로 정의됩니다. 호스트 빌더 컨텍스트는 `IConfiguration`의 인스턴스인 `.Configuration` 속성을 노출합니다. 이는 호스트에서 빌드된 구성을 나타내며, `IConfigurationBuilder`는 앱을 구성하는 데 사용되는 빌더 개체입니다.

> [!TIP]
> `ConfigureAppConfiguration`가 호출된 후에는 `HostBuilderContext.Configuration`이 [앱 구성](#app-configuration)으로 바뀝니다.

호스트 구성을 추가하려면 `IHostBuilder`에서 <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureHostConfiguration%2A>을 호출합니다. `ConfigureHostConfiguration` 항목은 부가적 결과와 함께 여러 번 호출할 수 있습니다. 호스트는 지정된 키에 마지막으로 값을 설정하는 옵션을 사용합니다.

다음 예제에서는 호스트 구성을 만듭니다.

:::code language="csharp" source="snippets/configuration/console-host/Program.cs" highlight="19-25":::

## <a name="app-configuration"></a>앱 구성

앱 구성은 `IHostBuilder`에서 <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureAppConfiguration%2A>을 호출하여 생성됩니다. `ConfigureAppConfiguration` 항목은 부가적 결과와 함께 여러 번 호출할 수 있습니다. 앱은 지정된 키에 마지막으로 값을 설정하는 옵션을 사용합니다.

`ConfigureAppConfiguration`에 의해 생성된 구성은 다음 작업을 위해 [HostBuilderContext.Configuration](xref:Microsoft.Extensions.Hosting.HostBuilderContext.Configuration%2A)에서 사용 가능하거나 DI의 서비스로 사용할 수 있습니다. 호스트 구성도 앱 구성에 추가됩니다.

자세한 내용은 [.NET의 구성](configuration.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [.NET의 구성](configuration.md)
- [ASP.NET Core 웹 호스트](/aspnet/core/fundamentals/host/web-host)
- 제네릭 호스트 버그는 [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) 리포지토리에서 만들어야 합니다.
