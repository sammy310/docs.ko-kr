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
# <a name="net-generic-host"></a><span data-ttu-id="1aa0c-103">.NET 일반 호스트</span><span class="sxs-lookup"><span data-stu-id="1aa0c-103">.NET Generic Host</span></span>

<span data-ttu-id="1aa0c-104">작업자 서비스 템플릿은 .NET 제네릭 호스트 <xref:Microsoft.Extensions.Hosting.HostBuilder>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-104">The Worker Service templates create a .NET Generic Host, <xref:Microsoft.Extensions.Hosting.HostBuilder>.</span></span> <span data-ttu-id="1aa0c-105">제네릭 호스트는 콘솔 앱과 같은 다른 유형의 .NET 애플리케이션과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-105">The Generic Host can be used with other types of .NET applications, such as Console apps.</span></span>

<span data-ttu-id="1aa0c-106">*호스트* 는 다음과 같이 앱의 리소스를 캡슐화하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-106">A *host* is an object that encapsulates an app's resources, such as:</span></span>

- <span data-ttu-id="1aa0c-107">DI(종속성 주입)</span><span class="sxs-lookup"><span data-stu-id="1aa0c-107">Dependency injection (DI)</span></span>
- <span data-ttu-id="1aa0c-108">로깅</span><span class="sxs-lookup"><span data-stu-id="1aa0c-108">Logging</span></span>
- <span data-ttu-id="1aa0c-109">Configuration</span><span class="sxs-lookup"><span data-stu-id="1aa0c-109">Configuration</span></span>
- <span data-ttu-id="1aa0c-110">`IHostedService` 구현</span><span class="sxs-lookup"><span data-stu-id="1aa0c-110">`IHostedService` implementations</span></span>

<span data-ttu-id="1aa0c-111">호스트가 시작될 때 서비스 컨테이너의 호스티드 서비스 컬렉션에 등록된 <xref:Microsoft.Extensions.Hosting.IHostedService>의 각 구현에서 <xref:Microsoft.Extensions.Hosting.IHostedService.StartAsync%2A?displayProperty=nameWithType>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-111">When a host starts, it calls <xref:Microsoft.Extensions.Hosting.IHostedService.StartAsync%2A?displayProperty=nameWithType> on each implementation of <xref:Microsoft.Extensions.Hosting.IHostedService> registered in the service container's collection of hosted services.</span></span> <span data-ttu-id="1aa0c-112">작업자 서비스 앱에서 <xref:Microsoft.Extensions.Hosting.BackgroundService> 인스턴스를 포함하는 모든 `IHostedService` 구현은 <xref:Microsoft.Extensions.Hosting.BackgroundService.ExecuteAsync%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-112">In a worker service app, all `IHostedService` implementations that contain <xref:Microsoft.Extensions.Hosting.BackgroundService> instances have their <xref:Microsoft.Extensions.Hosting.BackgroundService.ExecuteAsync%2A?displayProperty=nameWithType> methods called.</span></span>

<span data-ttu-id="1aa0c-113">하나의 개체에 앱의 모든 상호 종속적 리소스를 포함하는 주요 원인은 수명 관리 즉, 앱 시작 및 종료에 대한 제어 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-113">The main reason for including all of the app's interdependent resources in one object is lifetime management: control over app startup and graceful shutdown.</span></span> <span data-ttu-id="1aa0c-114">이는 [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) NuGet 패키지를 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-114">This is achieved with the [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) NuGet package.</span></span>

## <a name="set-up-a-host"></a><span data-ttu-id="1aa0c-115">호스트 설정</span><span class="sxs-lookup"><span data-stu-id="1aa0c-115">Set up a host</span></span>

<span data-ttu-id="1aa0c-116">호스트는 일반적으로 `Program` 클래스의 코드로 구성, 빌드 및 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-116">The host is typically configured, built, and run by code in the `Program` class.</span></span> <span data-ttu-id="1aa0c-117">`Main` 메서드는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-117">The `Main` method:</span></span>

- <span data-ttu-id="1aa0c-118"><xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder> 메서드를 호출하여 작성기 개체를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-118">Calls a <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder> method to create and configure a builder object.</span></span>
- <span data-ttu-id="1aa0c-119"><xref:Microsoft.Extensions.Hosting.IHostBuilder.Build>를 호출하여 <xref:Microsoft.Extensions.Hosting.IHost> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-119">Calls <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> to create an <xref:Microsoft.Extensions.Hosting.IHost> instance.</span></span>
- <span data-ttu-id="1aa0c-120">호스트 개체에 대해 <xref:Microsoft.Extensions.Hosting.HostingAbstractionsHostExtensions.Run%2A> 또는 <xref:Microsoft.Extensions.Hosting.HostingAbstractionsHostExtensions.RunAsync%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-120">Calls <xref:Microsoft.Extensions.Hosting.HostingAbstractionsHostExtensions.Run%2A> or <xref:Microsoft.Extensions.Hosting.HostingAbstractionsHostExtensions.RunAsync%2A> method on the host object.</span></span>

<span data-ttu-id="1aa0c-121">.NET 작업자 서비스 템플릿은 다음과 같은 코드를 생성하여 제네릭 호스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-121">The .NET Worker Service templates generate the following code to create a Generic Host:</span></span>

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

## <a name="default-builder-settings"></a><span data-ttu-id="1aa0c-122">기본 작성기 설정</span><span class="sxs-lookup"><span data-stu-id="1aa0c-122">Default builder settings</span></span>

<span data-ttu-id="1aa0c-123"><xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A> 메서드는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-123">The <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A> method:</span></span>

- <span data-ttu-id="1aa0c-124">콘텐츠 루트를 <xref:System.IO.Directory.GetCurrentDirectory>에서 반환된 경로로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-124">Sets the content root to the path returned by <xref:System.IO.Directory.GetCurrentDirectory>.</span></span>
- <span data-ttu-id="1aa0c-125">다음에서 [호스트 구성](#host-configuration)을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-125">Loads [host configuration](#host-configuration) from:</span></span>
  - <span data-ttu-id="1aa0c-126">접두사가 `DOTNET_`인 환경 변수.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-126">Environment variables prefixed with `DOTNET_`.</span></span>
  - <span data-ttu-id="1aa0c-127">명령줄 인수.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-127">Command-line arguments.</span></span>
- <span data-ttu-id="1aa0c-128">다음에서 앱 구성을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-128">Loads app configuration from:</span></span>
  - <span data-ttu-id="1aa0c-129">*appsettings.json*.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-129">*appsettings.json*.</span></span>
  - <span data-ttu-id="1aa0c-130">*appsettings.{Environment}.json*.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-130">*appsettings.{Environment}.json*.</span></span>
  - <span data-ttu-id="1aa0c-131">비밀 관리자: 앱이 `Development` 환경에서 실행되는 경우</span><span class="sxs-lookup"><span data-stu-id="1aa0c-131">Secret Manager when the app runs in the `Development` environment.</span></span>
  - <span data-ttu-id="1aa0c-132">환경 변수.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-132">Environment variables.</span></span>
  - <span data-ttu-id="1aa0c-133">명령줄 인수.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-133">Command-line arguments.</span></span>
- <span data-ttu-id="1aa0c-134">다음 로깅 공급자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-134">Adds the following logging providers:</span></span>
  - <span data-ttu-id="1aa0c-135">Console</span><span class="sxs-lookup"><span data-stu-id="1aa0c-135">Console</span></span>
  - <span data-ttu-id="1aa0c-136">Debug</span><span class="sxs-lookup"><span data-stu-id="1aa0c-136">Debug</span></span>
  - <span data-ttu-id="1aa0c-137">EventSource</span><span class="sxs-lookup"><span data-stu-id="1aa0c-137">EventSource</span></span>
  - <span data-ttu-id="1aa0c-138">EventLog(Windows에서 실행 중인 경우에만)</span><span class="sxs-lookup"><span data-stu-id="1aa0c-138">EventLog (only when running on Windows)</span></span>
- <span data-ttu-id="1aa0c-139">환경이 `Development`일 때 범위 유효성 검사 및 [종속성 유효성 검사](xref:Microsoft.Extensions.DependencyInjection.ServiceProviderOptions.ValidateOnBuild)를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-139">Enables scope validation and [dependency validation](xref:Microsoft.Extensions.DependencyInjection.ServiceProviderOptions.ValidateOnBuild) when the environment is `Development`.</span></span>

<span data-ttu-id="1aa0c-140">`ConfigureServices` 메서드는 <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection?displayProperty=nameWithType> 인스턴스에 서비스를 추가하는 기능을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-140">The `ConfigureServices` method exposes the ability to add services to the <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="1aa0c-141">나중에 종속성 주입에서 이러한 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-141">Later, these services can be made available from dependency injection.</span></span>

## <a name="framework-provided-services"></a><span data-ttu-id="1aa0c-142">프레임워크에서 제공하는 서비스</span><span class="sxs-lookup"><span data-stu-id="1aa0c-142">Framework-provided services</span></span>

<span data-ttu-id="1aa0c-143">다음 서비스가 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-143">The following services are registered automatically:</span></span>

- [<span data-ttu-id="1aa0c-144">IHostApplicationLifetime</span><span class="sxs-lookup"><span data-stu-id="1aa0c-144">IHostApplicationLifetime</span></span>](#ihostapplicationlifetime)
- [<span data-ttu-id="1aa0c-145">IHostLifetime</span><span class="sxs-lookup"><span data-stu-id="1aa0c-145">IHostLifetime</span></span>](#ihostlifetime)
- [<span data-ttu-id="1aa0c-146">IHostEnvironment</span><span class="sxs-lookup"><span data-stu-id="1aa0c-146">IHostEnvironment</span></span>](#ihostenvironment)

## <a name="ihostapplicationlifetime"></a><span data-ttu-id="1aa0c-147">IHostApplicationLifetime</span><span class="sxs-lookup"><span data-stu-id="1aa0c-147">IHostApplicationLifetime</span></span>

<span data-ttu-id="1aa0c-148"><xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime> 서비스를 모든 클래스에 주입하여 시작 후 및 정상 종료 작업을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-148">Inject the <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime> service into any class to handle post-startup and graceful shutdown tasks.</span></span> <span data-ttu-id="1aa0c-149">인터페이스의 세 가지 속성은 앱 시작 및 앱 중지 이벤트 처리기 메서드를 등록하는 데 사용되는 취소 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-149">Three properties on the interface are cancellation tokens used to register app start and app stop event handler methods.</span></span> <span data-ttu-id="1aa0c-150">인터페이스에는 <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime.StopApplication> 메서드도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-150">The interface also includes a <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime.StopApplication> method.</span></span>

<span data-ttu-id="1aa0c-151">다음 예제는 `IHostApplicationLifetime` 이벤트를 등록하는 `IHostedService` 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-151">The following example is an `IHostedService` implementation that registers `IHostApplicationLifetime` events:</span></span>

:::code language="csharp" source="snippets/configuration/app-lifetime/ExampleHostedService.cs" highlight="18-20":::

<span data-ttu-id="1aa0c-152">`ExampleHostedService` 구현을 추가하도록 작업자 서비스 템플릿을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-152">The Worker Service template could be modified to add the `ExampleHostedService` implementation:</span></span>

:::code language="csharp" source="snippets/configuration/app-lifetime/Program.cs" range="1-16,36" highlight="15":::

<span data-ttu-id="1aa0c-153">애플리케이션은 다음 샘플 출력을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-153">The application would write the following sample output:</span></span>

:::code language="csharp" source="snippets/configuration/app-lifetime/Program.cs" range="17-35":::

## <a name="ihostlifetime"></a><span data-ttu-id="1aa0c-154">IHostLifetime</span><span class="sxs-lookup"><span data-stu-id="1aa0c-154">IHostLifetime</span></span>

<span data-ttu-id="1aa0c-155"><xref:Microsoft.Extensions.Hosting.IHostLifetime> 구현은 호스트가 시작될 때와 중지될 때를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-155">The <xref:Microsoft.Extensions.Hosting.IHostLifetime> implementation controls when the host starts and when it stops.</span></span> <span data-ttu-id="1aa0c-156">등록된 마지막 구현이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-156">The last implementation registered is used.</span></span>

<span data-ttu-id="1aa0c-157">`Microsoft.Extensions.Hosting.Internal.ConsoleLifetime`은 기본 `IHostLifetime` 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-157">`Microsoft.Extensions.Hosting.Internal.ConsoleLifetime` is the default `IHostLifetime` implementation.</span></span> <span data-ttu-id="1aa0c-158">`ConsoleLifetime`:</span><span class="sxs-lookup"><span data-stu-id="1aa0c-158">`ConsoleLifetime`:</span></span>

- <span data-ttu-id="1aa0c-159"><kbd>Ctrl</kbd>+<kbd>C</kbd>, [SIGINT](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGINT) 또는 [SIGTERM](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGTERM)을 수신 대기하고 <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime.StopApplication%2A>을 호출하여 종료 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-159">Listens for <kbd>Ctrl</kbd>+<kbd>C</kbd>, [SIGINT](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGINT), or [SIGTERM](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGTERM) and calls <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime.StopApplication%2A> to start the shutdown process.</span></span>
- <span data-ttu-id="1aa0c-160">`RunAsync` 및 `WaitForShutdownAsync`와 같은 확장의 차단을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-160">Unblocks extensions such as `RunAsync` and `WaitForShutdownAsync`.</span></span>

## <a name="ihostenvironment"></a><span data-ttu-id="1aa0c-161">IHostEnvironment</span><span class="sxs-lookup"><span data-stu-id="1aa0c-161">IHostEnvironment</span></span>

<span data-ttu-id="1aa0c-162"><xref:Microsoft.Extensions.Hosting.IHostEnvironment> 서비스를 클래스에 삽입하여 다음 설정에 대한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-162">Inject the <xref:Microsoft.Extensions.Hosting.IHostEnvironment> service into a class to get information about the following settings:</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.ApplicationName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.ContentRootFileProvider?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.ContentRootPath?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.EnvironmentName?displayProperty=nameWithType>

## <a name="host-configuration"></a><span data-ttu-id="1aa0c-163">호스트 구성</span><span class="sxs-lookup"><span data-stu-id="1aa0c-163">Host configuration</span></span>

<span data-ttu-id="1aa0c-164">호스트 구성은 [IHostEnvironment](#ihostenvironment) 구현의 속성을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-164">Host configuration is used to configure properties of the [IHostEnvironment](#ihostenvironment) implementation.</span></span>

<span data-ttu-id="1aa0c-165">호스트 구성은 <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureAppConfiguration%2A> 메서드 내의 [HostBuilderContext.Configuration](xref:Microsoft.Extensions.Hosting.HostBuilderContext.Configuration)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-165">The host configuration is available in [HostBuilderContext.Configuration](xref:Microsoft.Extensions.Hosting.HostBuilderContext.Configuration) within the <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureAppConfiguration%2A> method.</span></span> <span data-ttu-id="1aa0c-166">`ConfigureAppConfiguration` 메서드를 호출할 때 `HostBuilderContext` 및 `IConfigurationBuilder`가 `configureDelegate`에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-166">When calling the `ConfigureAppConfiguration` method, the `HostBuilderContext` and `IConfigurationBuilder` are passed into the `configureDelegate`.</span></span> <span data-ttu-id="1aa0c-167">`configureDelegate`는 `Action<HostBuilderContext, IConfigurationBuilder>`로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-167">The `configureDelegate` is defined as an `Action<HostBuilderContext, IConfigurationBuilder>`.</span></span> <span data-ttu-id="1aa0c-168">호스트 빌더 컨텍스트는 `IConfiguration`의 인스턴스인 `.Configuration` 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-168">The host builder context exposes the `.Configuration` property, which is an instance of `IConfiguration`.</span></span> <span data-ttu-id="1aa0c-169">이는 호스트에서 빌드된 구성을 나타내며, `IConfigurationBuilder`는 앱을 구성하는 데 사용되는 빌더 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-169">It represents the configuration built from the host, whereas the `IConfigurationBuilder` is the builder object used to configure the app.</span></span>

> [!TIP]
> <span data-ttu-id="1aa0c-170">`ConfigureAppConfiguration`가 호출된 후에는 `HostBuilderContext.Configuration`이 [앱 구성](#app-configuration)으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-170">After `ConfigureAppConfiguration` is called the `HostBuilderContext.Configuration` is replaced with the [app config](#app-configuration).</span></span>

<span data-ttu-id="1aa0c-171">호스트 구성을 추가하려면 `IHostBuilder`에서 <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureHostConfiguration%2A>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-171">To add host configuration, call <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureHostConfiguration%2A> on `IHostBuilder`.</span></span> <span data-ttu-id="1aa0c-172">`ConfigureHostConfiguration` 항목은 부가적 결과와 함께 여러 번 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-172">`ConfigureHostConfiguration` can be called multiple times with additive results.</span></span> <span data-ttu-id="1aa0c-173">호스트는 지정된 키에 마지막으로 값을 설정하는 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-173">The host uses whichever option sets a value last on a given key.</span></span>

<span data-ttu-id="1aa0c-174">다음 예제에서는 호스트 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-174">The following example creates host configuration:</span></span>

:::code language="csharp" source="snippets/configuration/console-host/Program.cs" highlight="19-25":::

## <a name="app-configuration"></a><span data-ttu-id="1aa0c-175">앱 구성</span><span class="sxs-lookup"><span data-stu-id="1aa0c-175">App configuration</span></span>

<span data-ttu-id="1aa0c-176">앱 구성은 `IHostBuilder`에서 <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureAppConfiguration%2A>을 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-176">App configuration is created by calling <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureAppConfiguration%2A> on `IHostBuilder`.</span></span> <span data-ttu-id="1aa0c-177">`ConfigureAppConfiguration` 항목은 부가적 결과와 함께 여러 번 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-177">`ConfigureAppConfiguration` can be called multiple times with additive results.</span></span> <span data-ttu-id="1aa0c-178">앱은 지정된 키에 마지막으로 값을 설정하는 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-178">The app uses whichever option sets a value last on a given key.</span></span>

<span data-ttu-id="1aa0c-179">`ConfigureAppConfiguration`에 의해 생성된 구성은 다음 작업을 위해 [HostBuilderContext.Configuration](xref:Microsoft.Extensions.Hosting.HostBuilderContext.Configuration%2A)에서 사용 가능하거나 DI의 서비스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-179">The configuration created by `ConfigureAppConfiguration` is available in [HostBuilderContext.Configuration](xref:Microsoft.Extensions.Hosting.HostBuilderContext.Configuration%2A) for subsequent operations and as a service from DI.</span></span> <span data-ttu-id="1aa0c-180">호스트 구성도 앱 구성에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-180">The host configuration is also added to the app configuration.</span></span>

<span data-ttu-id="1aa0c-181">자세한 내용은 [.NET의 구성](configuration.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-181">For more information, see [Configuration in .NET](configuration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1aa0c-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1aa0c-182">See also</span></span>

- [<span data-ttu-id="1aa0c-183">.NET의 구성</span><span class="sxs-lookup"><span data-stu-id="1aa0c-183">Configuration in .NET</span></span>](configuration.md)
- [<span data-ttu-id="1aa0c-184">ASP.NET Core 웹 호스트</span><span class="sxs-lookup"><span data-stu-id="1aa0c-184">ASP.NET Core Web Host</span></span>](/aspnet/core/fundamentals/host/web-host)
- <span data-ttu-id="1aa0c-185">제네릭 호스트 버그는 [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) 리포지토리에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa0c-185">Generic host bugs should be created in the [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) repo</span></span>
