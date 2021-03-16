---
title: .NET의 로깅 공급자
description: .NET 애플리케이션에서 로깅 공급자 API를 사용하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 02/16/2021
ms.openlocfilehash: 7265e51a4d92cd99abebef2ebf0bc5db37b306e3
ms.sourcegitcommit: 456b3cd82a87b453fa737b4661295070d1b6d684
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "102402152"
---
# <a name="logging-providers-in-net"></a><span data-ttu-id="57fcc-103">.NET의 로깅 공급자</span><span class="sxs-lookup"><span data-stu-id="57fcc-103">Logging providers in .NET</span></span>

<span data-ttu-id="57fcc-104">로그를 표준 출력으로만 표시하는 `Console` 공급자를 제외하고 로깅 공급자는 로그를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-104">Logging providers persist logs, except for the `Console` provider, which only displays logs as standard output.</span></span> <span data-ttu-id="57fcc-105">예를 들어 Azure Application Insights 공급자는 Azure Application Insights의 로그를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-105">For example, the Azure Application Insights provider stores logs in Azure Application Insights.</span></span> <span data-ttu-id="57fcc-106">여러 공급자를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-106">Multiple providers can be enabled.</span></span>

<span data-ttu-id="57fcc-107">기본 .NET 작업자 앱 템플릿:</span><span class="sxs-lookup"><span data-stu-id="57fcc-107">The default .NET Worker app templates:</span></span>

- <span data-ttu-id="57fcc-108">[제네릭 호스트](generic-host.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-108">Use the [Generic Host](generic-host.md).</span></span>
- <span data-ttu-id="57fcc-109">다음 로깅 공급자를 추가하는 <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-109">Call <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A>, which adds the following logging providers:</span></span>
  - [<span data-ttu-id="57fcc-110">콘솔</span><span class="sxs-lookup"><span data-stu-id="57fcc-110">Console</span></span>](#console)
  - [<span data-ttu-id="57fcc-111">디버그</span><span class="sxs-lookup"><span data-stu-id="57fcc-111">Debug</span></span>](#debug)
  - [<span data-ttu-id="57fcc-112">EventSource</span><span class="sxs-lookup"><span data-stu-id="57fcc-112">EventSource</span></span>](#event-source)
  - <span data-ttu-id="57fcc-113">[EventLog](#windows-eventlog): Windows에만 해당</span><span class="sxs-lookup"><span data-stu-id="57fcc-113">[EventLog](#windows-eventlog): Windows only</span></span>

:::code language="csharp" source="snippets/configuration/console/Program.cs" highlight="18":::

<span data-ttu-id="57fcc-114">위의 코드는 .NET 작업자 앱 템플릿을 사용하여 만든 `Program` 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-114">The preceding code shows the `Program` class created with the .NET Worker app templates.</span></span> <span data-ttu-id="57fcc-115">다음 몇 개 섹션에서는 제네릭 호스트를 사용하는 .NET 작업자 앱 템플릿을 기반으로 하는 샘플을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-115">The next several sections provide samples based on the .NET Worker app templates, which use the Generic Host.</span></span>

<span data-ttu-id="57fcc-116">`Host.CreateDefaultBuilder`를 통해 추가된 로깅 공급자의 기본 세트를 재정의하려면 `ClearProviders`를 호출하고 원하는 로깅 공급자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-116">To override the default set of logging providers added by `Host.CreateDefaultBuilder`, call `ClearProviders` and add the logging providers you want.</span></span> <span data-ttu-id="57fcc-117">예를 들어, 다음 코드는</span><span class="sxs-lookup"><span data-stu-id="57fcc-117">For example, the following code:</span></span>

- <span data-ttu-id="57fcc-118"><xref:Microsoft.Extensions.Logging.LoggingBuilderExtensions.ClearProviders%2A>를 호출하여 작성기에서 <xref:Microsoft.Extensions.Logging.ILoggerProvider> 인스턴스를 모두 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-118">Calls <xref:Microsoft.Extensions.Logging.LoggingBuilderExtensions.ClearProviders%2A> to remove all the <xref:Microsoft.Extensions.Logging.ILoggerProvider> instances from the builder.</span></span>
- <span data-ttu-id="57fcc-119">[Console](#console) 로깅 공급자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-119">Adds the [Console](#console) logging provider.</span></span>

```csharp
static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureLogging(logging =>
        {
            logging.ClearProviders();
            logging.AddConsole();
        });
```

<span data-ttu-id="57fcc-120">추가 공급자는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57fcc-120">For additional providers, see:</span></span>

- <span data-ttu-id="57fcc-121">[기본 제공 로깅 공급자](#built-in-logging-providers)</span><span class="sxs-lookup"><span data-stu-id="57fcc-121">[Built-in logging providers](#built-in-logging-providers).</span></span>
- <span data-ttu-id="57fcc-122">[타사 로깅 공급자](#third-party-logging-providers)</span><span class="sxs-lookup"><span data-stu-id="57fcc-122">[Third-party logging providers](#third-party-logging-providers).</span></span>

## <a name="configure-a-service-that-depends-on-ilogger"></a><span data-ttu-id="57fcc-123">ILogger에 종속되는 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="57fcc-123">Configure a service that depends on ILogger</span></span>

<span data-ttu-id="57fcc-124">`ILogger<T>`에 종속되는 서비스를 구성하려면 생성자 주입을 사용하거나 팩터리 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-124">To configure a service that depends on `ILogger<T>`, use constructor injection or provide a factory method.</span></span> <span data-ttu-id="57fcc-125">팩터리 메서드 접근 방식은 다른 옵션이 없는 경우에만 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-125">The factory method approach is recommended only if there is no other option.</span></span> <span data-ttu-id="57fcc-126">예를 들어 DI에서 제공하는 `ILogger<T>` 인스턴스가 필요한 서비스를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-126">For example, consider a service that needs an `ILogger<T>` instance provided by DI:</span></span>

```csharp
.ConfigureServices(services =>
    services.AddSingleton<IExampleService>(container =>
        new DefaultExampleService
        {
            Logger = container.GetRequiredService<ILogger<IExampleService>>()
        }));
```

<span data-ttu-id="57fcc-127">이전 코드는 DI 컨테이너가 `IExampleService`의 인스턴스를 처음 생성해야 할 때 실행되는 [Func<IServiceProvider, IExampleService>](/dotnet/api/system.func-2)입니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-127">The preceding code is a [Func<IServiceProvider, IExampleService>](/dotnet/api/system.func-2) that runs the first time the DI container needs to construct an instance of `IExampleService`.</span></span> <span data-ttu-id="57fcc-128">이러한 방식으로 등록된 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-128">You can access any of the registered services in this way.</span></span>

## <a name="built-in-logging-providers"></a><span data-ttu-id="57fcc-129">기본 로깅 공급자</span><span class="sxs-lookup"><span data-stu-id="57fcc-129">Built-in logging providers</span></span>

<span data-ttu-id="57fcc-130">Microsoft 확장에는 런타임 라이브러리의 일부로 다음 로깅 공급자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-130">Microsoft Extensions include the following logging providers as part of the runtime libraries:</span></span>

- [<span data-ttu-id="57fcc-131">콘솔</span><span class="sxs-lookup"><span data-stu-id="57fcc-131">Console</span></span>](#console)
- [<span data-ttu-id="57fcc-132">디버그</span><span class="sxs-lookup"><span data-stu-id="57fcc-132">Debug</span></span>](#debug)
- [<span data-ttu-id="57fcc-133">EventSource</span><span class="sxs-lookup"><span data-stu-id="57fcc-133">EventSource</span></span>](#event-source)
- [<span data-ttu-id="57fcc-134">EventLog</span><span class="sxs-lookup"><span data-stu-id="57fcc-134">EventLog</span></span>](#windows-eventlog)

<span data-ttu-id="57fcc-135">다음 로깅 공급자는 Microsoft에서 제공되지만 런타임 라이브러리의 일부로 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-135">The following logging providers are shipped by Microsoft, but not as part of the runtime libraries.</span></span> <span data-ttu-id="57fcc-136">해당 공급자는 추가 NuGet 패키지로 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-136">They must be installed as additional NuGet packages.</span></span>

- [<span data-ttu-id="57fcc-137">AzureAppServicesFile 및 AzureAppServicesBlob</span><span class="sxs-lookup"><span data-stu-id="57fcc-137">AzureAppServicesFile and AzureAppServicesBlob</span></span>](#azure-app-service)
- [<span data-ttu-id="57fcc-138">ApplicationInsights</span><span class="sxs-lookup"><span data-stu-id="57fcc-138">ApplicationInsights</span></span>](#azure-application-insights)

### <a name="console"></a><span data-ttu-id="57fcc-139">Console</span><span class="sxs-lookup"><span data-stu-id="57fcc-139">Console</span></span>

<span data-ttu-id="57fcc-140">`Console` 공급자는 콘솔에 출력을 로그합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-140">The `Console` provider logs output to the console.</span></span>

### <a name="debug"></a><span data-ttu-id="57fcc-141">디버그</span><span class="sxs-lookup"><span data-stu-id="57fcc-141">Debug</span></span>

<span data-ttu-id="57fcc-142">`Debug` 공급자는 [System.Diagnostics.Debug](/dotnet/api/system.diagnostics.debug) 클래스를 사용하여 로그 출력을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-142">The `Debug` provider writes log output by using the [System.Diagnostics.Debug](/dotnet/api/system.diagnostics.debug) class.</span></span> <span data-ttu-id="57fcc-143">`System.Diagnostics.Debug.WriteLine`을 호출하여 `Debug` 공급자에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-143">Calls to `System.Diagnostics.Debug.WriteLine` write to the `Debug` provider.</span></span>

<span data-ttu-id="57fcc-144">Linux에서 `Debug` 공급자 로그 위치는 배포판마다 다르며 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-144">On Linux, the `Debug` provider log location is distribution-dependent and may be one of the following:</span></span>

- <span data-ttu-id="57fcc-145">*/var/log/message*</span><span class="sxs-lookup"><span data-stu-id="57fcc-145">*/var/log/message*</span></span>
- <span data-ttu-id="57fcc-146">*/var/log/syslog*</span><span class="sxs-lookup"><span data-stu-id="57fcc-146">*/var/log/syslog*</span></span>

### <a name="event-source"></a><span data-ttu-id="57fcc-147">이벤트 원본</span><span class="sxs-lookup"><span data-stu-id="57fcc-147">Event Source</span></span>

<span data-ttu-id="57fcc-148">`EventSource` 공급자는 이름이 `Microsoft-Extensions-Logging`인 플랫폼 간 이벤트 원본에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-148">The `EventSource` provider writes to a cross-platform event source with the name `Microsoft-Extensions-Logging`.</span></span> <span data-ttu-id="57fcc-149">Windows에서 공급자는 [ETW](/windows/win32/etw/event-tracing-portal)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-149">On Windows, the provider uses [ETW](/windows/win32/etw/event-tracing-portal).</span></span>

#### <a name="dotnet-trace-tooling"></a><span data-ttu-id="57fcc-150">dotnet 추적 도구</span><span class="sxs-lookup"><span data-stu-id="57fcc-150">dotnet trace tooling</span></span>

<span data-ttu-id="57fcc-151">[dotnet 추적](../diagnostics/dotnet-trace.md) 도구는 실행 중인 프로세스의 .NET Core 추적을 수집할 수 있도록 하는 플랫폼 간 CLI 전역 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-151">The [dotnet-trace](../diagnostics/dotnet-trace.md) tool is a cross-platform CLI global tool that enables the collection of .NET Core traces of a running process.</span></span> <span data-ttu-id="57fcc-152">이 도구는 <xref:Microsoft.Extensions.Logging.EventSource.LoggingEventSource>를 사용하여 <xref:Microsoft.Extensions.Logging.EventSource> 공급자 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-152">The tool collects <xref:Microsoft.Extensions.Logging.EventSource> provider data using a <xref:Microsoft.Extensions.Logging.EventSource.LoggingEventSource>.</span></span>

<span data-ttu-id="57fcc-153">설치 지침은 [dotnet-trace](../diagnostics/dotnet-trace.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57fcc-153">See [dotnet-trace](../diagnostics/dotnet-trace.md) for installation instructions.</span></span> <span data-ttu-id="57fcc-154">`dotnet-trace`를 사용하는 진단 자습서를 보려면 [.NET Core에서 높은 CPU 사용량 디버그](../diagnostics/debug-highcpu.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57fcc-154">For a diagnostic tutorial using `dotnet-trace`, see [Debug high CPU usage in .NET Core](../diagnostics/debug-highcpu.md).</span></span>

### <a name="windows-eventlog"></a><span data-ttu-id="57fcc-155">Windows EventLog</span><span class="sxs-lookup"><span data-stu-id="57fcc-155">Windows EventLog</span></span>

<span data-ttu-id="57fcc-156">`EventLog` 공급자는 로그 출력을 Windows 이벤트 로그에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-156">The `EventLog` provider sends log output to the Windows Event Log.</span></span> <span data-ttu-id="57fcc-157">다른 공급자와 달리 `EventLog` 공급자는 기본 비공급자 설정을 상속하지 ***않습니다***.</span><span class="sxs-lookup"><span data-stu-id="57fcc-157">Unlike the other providers, the `EventLog` provider does ***not*** inherit the default non-provider settings.</span></span> <span data-ttu-id="57fcc-158">`EventLog` 로그 설정을 지정하지 않으면 기본적으로 `LogLevel.Warning`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-158">If `EventLog` log settings aren't specified, they default to `LogLevel.Warning`.</span></span>

<span data-ttu-id="57fcc-159"><xref:Microsoft.Extensions.Logging.LogLevel.Warning?displayProperty=nameWithType> 수준보다 낮은 이벤트를 기록하려면 로그 수준을 명시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-159">To log events lower than <xref:Microsoft.Extensions.Logging.LogLevel.Warning?displayProperty=nameWithType>, explicitly set the log level.</span></span> <span data-ttu-id="57fcc-160">다음 예제에서는 이벤트 로그 기본 로그 수준을 <xref:Microsoft.Extensions.Logging.LogLevel.Information?displayProperty=nameWithType>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-160">The following example sets the Event Log default log level to <xref:Microsoft.Extensions.Logging.LogLevel.Information?displayProperty=nameWithType>:</span></span>

```json
"Logging": {
  "EventLog": {
    "LogLevel": {
      "Default": "Information"
    }
  }
}
```

<span data-ttu-id="57fcc-161">[AddEventLog 오버로드](xref:Microsoft.Extensions.Logging.EventLoggerFactoryExtensions)는 <xref:Microsoft.Extensions.Logging.EventLog.EventLogSettings>를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-161">[AddEventLog overloads](xref:Microsoft.Extensions.Logging.EventLoggerFactoryExtensions) can pass in <xref:Microsoft.Extensions.Logging.EventLog.EventLogSettings>.</span></span> <span data-ttu-id="57fcc-162">`null`이거나 지정하지 않으면 다음 기본 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-162">If `null` or not specified, the following default settings are used:</span></span>

- <span data-ttu-id="57fcc-163">`LogName`: “Application”</span><span class="sxs-lookup"><span data-stu-id="57fcc-163">`LogName`: "Application"</span></span>
- <span data-ttu-id="57fcc-164">`SourceName`: “.NET Runtime”</span><span class="sxs-lookup"><span data-stu-id="57fcc-164">`SourceName`: ".NET Runtime"</span></span>
- <span data-ttu-id="57fcc-165">`MachineName`: 로컬 머신 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-165">`MachineName`: The local machine name is used.</span></span>

<span data-ttu-id="57fcc-166">다음 코드에서는 `SourceName`을 기본값 `".NET Runtime"`에서 `CustomLogs`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-166">The following code changes the `SourceName` from the default value of `".NET Runtime"` to `CustomLogs`:</span></span>

```csharp
public class Program
{
    static async Task Main(string[] args)
    {
        using IHost host = CreateHostBuilder(args).Build();

        // Application code should start here.

        await host.RunAsync();
    }

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging =>
                logging.AddEventLog(configuration =>
                    configuration.SourceName = "CustomLogs"));
}
```

### <a name="azure-app-service"></a><span data-ttu-id="57fcc-167">Azure App Service</span><span class="sxs-lookup"><span data-stu-id="57fcc-167">Azure App Service</span></span>

<span data-ttu-id="57fcc-168">[Microsoft.Extensions.Logging.AzureAppServices](https://www.nuget.org/packages/Microsoft.Extensions.Logging.AzureAppServices) 공급자 패키지는 Azure App Service 앱의 파일 시스템과 Azure Storage 계정의 [Blob 스토리지](/azure/storage/blobs/storage-quickstart-blobs-dotnet#what-is-blob-storage)에 텍스트 파일을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-168">The [Microsoft.Extensions.Logging.AzureAppServices](https://www.nuget.org/packages/Microsoft.Extensions.Logging.AzureAppServices) provider package writes logs to text files in an Azure App Service app's file system and to [blob storage](/azure/storage/blobs/storage-quickstart-blobs-dotnet#what-is-blob-storage) in an Azure Storage account.</span></span>

<span data-ttu-id="57fcc-169">공급자 패키지는 런타임 라이브러리에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-169">The provider package isn't included in the runtime libraries.</span></span> <span data-ttu-id="57fcc-170">이 공급자를 사용하려면 프로젝트에 공급자 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-170">To use the provider, add the provider package to the project.</span></span>

<span data-ttu-id="57fcc-171">공급자 설정을 구성하려면 다음 예제와 같이 <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureFileLoggerOptions> 및 <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureBlobLoggerOptions>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-171">To configure provider settings, use <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureFileLoggerOptions> and <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureBlobLoggerOptions>, as shown in the following example:</span></span>

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        using IHost host = CreateHostBuilder(args).Build();

        // Application code should start here.

        await host.RunAsync();
    }

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging =>
                logging.AddAzureWebAppDiagnostics())
            .ConfigureServices(services =>
                services.Configure<AzureFileLoggerOptions>(options =>
                {
                    options.FileName = "azure-diagnostics-";
                    options.FileSizeLimit = 50 * 1024;
                    options.RetainedFileCountLimit = 5;
                })
                .Configure<AzureBlobLoggerOptions>(options =>
                {
                    options.BlobName = "log.txt";
                }));
}
```

<span data-ttu-id="57fcc-172">Azure App Service에 배포하는 경우 앱은 Azure Portal에서 **App Service** 페이지에 있는 [App Service 로그](/azure/app-service/web-sites-enable-diagnostic-log/#enable-application-logging-windows) 섹션의 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-172">When deployed to Azure App Service, the app uses the settings in the [App Service logs](/azure/app-service/web-sites-enable-diagnostic-log/#enable-application-logging-windows) section of the **App Service** page of the Azure portal.</span></span> <span data-ttu-id="57fcc-173">다음 설정이 업데이트되면 앱을 다시 시작하거나 재배포하지 않아도 변경 내용이 즉시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-173">When the following settings are updated, the changes take effect immediately without requiring a restart or redeployment of the app.</span></span>

- <span data-ttu-id="57fcc-174">**애플리케이션 로깅(파일 시스템)**</span><span class="sxs-lookup"><span data-stu-id="57fcc-174">**Application Logging (Filesystem)**</span></span>
- <span data-ttu-id="57fcc-175">**애플리케이션 로깅(Blob)**</span><span class="sxs-lookup"><span data-stu-id="57fcc-175">**Application Logging (Blob)**</span></span>

<span data-ttu-id="57fcc-176">로그 파일의 기본 위치는 *D:\\home\\LogFiles\\Application* 폴더이며, 기본 파일 이름은 *diagnostics-yyyymmdd.txt* 입니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-176">The default location for log files is in the *D:\\home\\LogFiles\\Application* folder, and the default file name is *diagnostics-yyyymmdd.txt*.</span></span> <span data-ttu-id="57fcc-177">기본 파일 크기 제한은 10MB이고, 보존되는 기본 최대 파일 수는 2입니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-177">The default file size limit is 10 MB, and the default maximum number of files retained is 2.</span></span> <span data-ttu-id="57fcc-178">기본 BLOB 이름은 *{app-name}{timestamp}/yyyy/mm/dd/hh/{guid}-applicationLog.txt* 입니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-178">The default blob name is *{app-name}{timestamp}/yyyy/mm/dd/hh/{guid}-applicationLog.txt*.</span></span>

<span data-ttu-id="57fcc-179">이 공급자는 프로젝트가 Azure 환경에서 실행되는 경우에만 로그합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-179">This provider only logs when the project runs in the Azure environment.</span></span>

#### <a name="azure-log-streaming"></a><span data-ttu-id="57fcc-180">Azure 로그 스트리밍</span><span class="sxs-lookup"><span data-stu-id="57fcc-180">Azure log streaming</span></span>

<span data-ttu-id="57fcc-181">Azure 로그 스트리밍을 통해 다음에서 로그 활동을 실시간으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-181">Azure log streaming supports viewing log activity in real time from:</span></span>

- <span data-ttu-id="57fcc-182">앱 서버</span><span class="sxs-lookup"><span data-stu-id="57fcc-182">The app server</span></span>
- <span data-ttu-id="57fcc-183">웹 서버</span><span class="sxs-lookup"><span data-stu-id="57fcc-183">The web server</span></span>
- <span data-ttu-id="57fcc-184">실패한 요청 추적</span><span class="sxs-lookup"><span data-stu-id="57fcc-184">Failed request tracing</span></span>

<span data-ttu-id="57fcc-185">Azure 로그 스트리밍을 구성하려면:</span><span class="sxs-lookup"><span data-stu-id="57fcc-185">To configure Azure log streaming:</span></span>

- <span data-ttu-id="57fcc-186">앱의 포털 페이지에서 **App Service 로그** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-186">Navigate to the **App Service logs** page from the app's portal page.</span></span>
- <span data-ttu-id="57fcc-187">**애플리케이션 로깅(파일 시스템)** 을 **On** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-187">Set **Application Logging (Filesystem)** to **On**.</span></span>
- <span data-ttu-id="57fcc-188">로그 **수준** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-188">Choose the log **Level**.</span></span> <span data-ttu-id="57fcc-189">이 설정은 Azure 로그 스트리밍에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-189">This setting only applies to Azure log streaming.</span></span>

<span data-ttu-id="57fcc-190">**로그 스트림** 페이지로 이동하여 로그를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-190">Navigate to the **Log Stream** page to view logs.</span></span> <span data-ttu-id="57fcc-191">로드되는 메시지는 `ILogger` 인터페이스를 사용하여 로그됩니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-191">The logged messages are logged with the `ILogger` interface.</span></span>

### <a name="azure-application-insights"></a><span data-ttu-id="57fcc-192">Azure Application Insights</span><span class="sxs-lookup"><span data-stu-id="57fcc-192">Azure Application Insights</span></span>

<span data-ttu-id="57fcc-193">[Microsoft.Extensions.Logging.ApplicationInsights](https://www.nuget.org/packages/Microsoft.Extensions.Logging.ApplicationInsights) 공급자 패키지는 [Azure Application Insights](/azure/azure-monitor/app/cloudservices)에 로그를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-193">The [Microsoft.Extensions.Logging.ApplicationInsights](https://www.nuget.org/packages/Microsoft.Extensions.Logging.ApplicationInsights) provider package writes logs to [Azure Application Insights](/azure/azure-monitor/app/cloudservices).</span></span> <span data-ttu-id="57fcc-194">Application Insights는 웹앱을 모니터링하고 원격 분석 데이터를 쿼리 및 분석하기 위한 도구를 제공하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-194">Application Insights is a service that monitors a web app and provides tools for querying and analyzing the telemetry data.</span></span> <span data-ttu-id="57fcc-195">이 공급자를 사용하는 경우 Application Insights 도구를 사용하여 로그를 쿼리 및 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-195">If you use this provider, you can query and analyze your logs by using the Application Insights tools.</span></span>

<span data-ttu-id="57fcc-196">자세한 내용은 다음 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57fcc-196">For more information, see the following resources:</span></span>

- [<span data-ttu-id="57fcc-197">Application Insights 개요</span><span class="sxs-lookup"><span data-stu-id="57fcc-197">Application Insights overview</span></span>](/azure/application-insights/app-insights-overview)
- <span data-ttu-id="57fcc-198">[.NET Core ILogger 로그용 ApplicationInsightsLoggerProvider](/azure/azure-monitor/app/ilogger) - 나머지 Application Insights 원격 분석 없이 로깅 공급자를 구현하려면 여기에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-198">[ApplicationInsightsLoggerProvider for .NET Core ILogger logs](/azure/azure-monitor/app/ilogger) - Start here if you want to implement the logging provider without the rest of Application Insights telemetry.</span></span>
- <span data-ttu-id="57fcc-199">[Application Insights 로깅 어댑터](/azure/azure-monitor/app/asp-net-trace-logs).</span><span class="sxs-lookup"><span data-stu-id="57fcc-199">[Application Insights logging adapters](/azure/azure-monitor/app/asp-net-trace-logs).</span></span>
- <span data-ttu-id="57fcc-200">[Application Insights SDK 설치, 구성 및 초기화](/learn/modules/instrument-web-app-code-with-application-insights) - Microsoft Learn 사이트의 대화형 자습서입니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-200">[Install, configure, and initialize the Application Insights SDK](/learn/modules/instrument-web-app-code-with-application-insights) - Interactive tutorial on the Microsoft Learn site.</span></span>

## <a name="third-party-logging-providers"></a><span data-ttu-id="57fcc-201">타사 로깅 공급자</span><span class="sxs-lookup"><span data-stu-id="57fcc-201">Third-party logging providers</span></span>

<span data-ttu-id="57fcc-202">다음은 다양한 .NET 워크로드에서 작동하는 일부 타사 로깅 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-202">Here are some third-party logging frameworks that work with various .NET workloads:</span></span>

- <span data-ttu-id="57fcc-203">[elmah.io](https://elmah.io)([GitHub 리포지토리](https://github.com/elmahio/Elmah.Io.Extensions.Logging))</span><span class="sxs-lookup"><span data-stu-id="57fcc-203">[elmah.io](https://elmah.io) ([GitHub repo](https://github.com/elmahio/Elmah.Io.Extensions.Logging))</span></span>
- <span data-ttu-id="57fcc-204">[Gelf](https://docs.graylog.org/en/2.3/pages/gelf.html)([GitHub 리포지토리](https://github.com/mattwcole/gelf-extensions-logging))</span><span class="sxs-lookup"><span data-stu-id="57fcc-204">[Gelf](https://docs.graylog.org/en/2.3/pages/gelf.html) ([GitHub repo](https://github.com/mattwcole/gelf-extensions-logging))</span></span>
- <span data-ttu-id="57fcc-205">[JSNLog](http://jsnlog.com)([GitHub 리포지토리](https://github.com/mperdeck/jsnlog))</span><span class="sxs-lookup"><span data-stu-id="57fcc-205">[JSNLog](http://jsnlog.com) ([GitHub repo](https://github.com/mperdeck/jsnlog))</span></span>
- <span data-ttu-id="57fcc-206">[KissLog.net](https://kisslog.net)([GitHub 리포지토리](https://github.com/catalingavan/KissLog-net))</span><span class="sxs-lookup"><span data-stu-id="57fcc-206">[KissLog.net](https://kisslog.net) ([GitHub repo](https://github.com/catalingavan/KissLog-net))</span></span>
- <span data-ttu-id="57fcc-207">[Log4Net](https://logging.apache.org/log4net)([GitHub 리포지토리](https://github.com/apache/logging-log4net))</span><span class="sxs-lookup"><span data-stu-id="57fcc-207">[Log4Net](https://logging.apache.org/log4net) ([GitHub repo](https://github.com/apache/logging-log4net))</span></span>
- <span data-ttu-id="57fcc-208">[Loggr](https://loggr.net)([GitHub 리포지토리](https://github.com/imobile3/Loggr.Extensions.Logging))</span><span class="sxs-lookup"><span data-stu-id="57fcc-208">[Loggr](https://loggr.net) ([GitHub repo](https://github.com/imobile3/Loggr.Extensions.Logging))</span></span>
- <span data-ttu-id="57fcc-209">[NLog](https://nlog-project.org)([GitHub 리포지토리](https://github.com/NLog/NLog.Extensions.Logging))</span><span class="sxs-lookup"><span data-stu-id="57fcc-209">[NLog](https://nlog-project.org) ([GitHub repo](https://github.com/NLog/NLog.Extensions.Logging))</span></span>
- <span data-ttu-id="57fcc-210">[NReco.Logging](https://github.com/nreco/logging/blob/master/README.md)([GitHub 리포지토리](https://github.com/nreco/logging))</span><span class="sxs-lookup"><span data-stu-id="57fcc-210">[NReco.Logging](https://github.com/nreco/logging/blob/master/README.md) ([GitHub repo](https://github.com/nreco/logging))</span></span>
- <span data-ttu-id="57fcc-211">[Sentry](https://sentry.io/welcome) ([GitHub repo](https://github.com/getsentry/sentry-dotnet))</span><span class="sxs-lookup"><span data-stu-id="57fcc-211">[Sentry](https://sentry.io/welcome) ([GitHub repo](https://github.com/getsentry/sentry-dotnet))</span></span>
- <span data-ttu-id="57fcc-212">[Serilog](https://serilog.net)([GitHub 리포지토리](https://github.com/serilog/serilog-sinks-console))</span><span class="sxs-lookup"><span data-stu-id="57fcc-212">[Serilog](https://serilog.net) ([GitHub repo](https://github.com/serilog/serilog-sinks-console))</span></span>
- <span data-ttu-id="57fcc-213">[Stackdriver](https://cloud.google.com/dotnet/docs/stackdriver#logging)([GitHub 리포지토리](https://github.com/googleapis/google-cloud-dotnet))</span><span class="sxs-lookup"><span data-stu-id="57fcc-213">[Stackdriver](https://cloud.google.com/dotnet/docs/stackdriver#logging) ([GitHub repo](https://github.com/googleapis/google-cloud-dotnet))</span></span>

<span data-ttu-id="57fcc-214">일부 타사 프레임워크는 [구조적 로깅이라고 하는 의미 체계 로깅](https://softwareengineering.stackexchange.com/questions/312197/benefits-of-structured-logging-vs-basic-logging)을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-214">Some third-party frameworks can perform [semantic logging, also known as structured logging](https://softwareengineering.stackexchange.com/questions/312197/benefits-of-structured-logging-vs-basic-logging).</span></span>

<span data-ttu-id="57fcc-215">타사 프레임워크를 사용하는 방법은 다음과 같이 기본 공급자 중 하나를 사용하는 방법과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-215">Using a third-party framework is similar to using one of the built-in providers:</span></span>

1. <span data-ttu-id="57fcc-216">프로젝트에 NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-216">Add a NuGet package to your project.</span></span>
1. <span data-ttu-id="57fcc-217">로깅 프레임워크에서 제공되는 `ILoggerFactory` 또는 `ILoggingBuilder` 확장 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-217">Call an `ILoggerFactory` or `ILoggingBuilder` extension method provided by the logging framework.</span></span>

<span data-ttu-id="57fcc-218">자세한 내용은 각 공급자의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57fcc-218">For more information, see each provider's documentation.</span></span> <span data-ttu-id="57fcc-219">타사 로깅 공급자는 Microsoft에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57fcc-219">Third-party logging providers aren't supported by Microsoft.</span></span>

## <a name="see-also"></a><span data-ttu-id="57fcc-220">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57fcc-220">See also</span></span>

- <span data-ttu-id="57fcc-221">[.NET에 로그인](logging.md)</span><span class="sxs-lookup"><span data-stu-id="57fcc-221">[Logging in .NET](logging.md).</span></span>
- <span data-ttu-id="57fcc-222">[.NET에서 사용자 지정 로깅 공급자 구현](custom-logging-provider.md)</span><span class="sxs-lookup"><span data-stu-id="57fcc-222">[Implement a custom logging provider in .NET](custom-logging-provider.md).</span></span>
- <span data-ttu-id="57fcc-223">[.NET의 고성능 로깅](high-performance-logging.md)</span><span class="sxs-lookup"><span data-stu-id="57fcc-223">[High-performance logging in .NET](high-performance-logging.md).</span></span>
