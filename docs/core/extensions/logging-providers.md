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
# <a name="logging-providers-in-net"></a>.NET의 로깅 공급자

로그를 표준 출력으로만 표시하는 `Console` 공급자를 제외하고 로깅 공급자는 로그를 유지합니다. 예를 들어 Azure Application Insights 공급자는 Azure Application Insights의 로그를 저장합니다. 여러 공급자를 사용하도록 설정할 수 있습니다.

기본 .NET 작업자 앱 템플릿:

- [제네릭 호스트](generic-host.md)를 사용합니다.
- 다음 로깅 공급자를 추가하는 <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A>를 호출합니다.
  - [콘솔](#console)
  - [디버그](#debug)
  - [EventSource](#event-source)
  - [EventLog](#windows-eventlog): Windows에만 해당

:::code language="csharp" source="snippets/configuration/console/Program.cs" highlight="18":::

위의 코드는 .NET 작업자 앱 템플릿을 사용하여 만든 `Program` 클래스를 보여 줍니다. 다음 몇 개 섹션에서는 제네릭 호스트를 사용하는 .NET 작업자 앱 템플릿을 기반으로 하는 샘플을 제공합니다.

`Host.CreateDefaultBuilder`를 통해 추가된 로깅 공급자의 기본 세트를 재정의하려면 `ClearProviders`를 호출하고 원하는 로깅 공급자를 추가합니다. 예를 들어, 다음 코드는

- <xref:Microsoft.Extensions.Logging.LoggingBuilderExtensions.ClearProviders%2A>를 호출하여 작성기에서 <xref:Microsoft.Extensions.Logging.ILoggerProvider> 인스턴스를 모두 제거합니다.
- [Console](#console) 로깅 공급자를 추가합니다.

```csharp
static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureLogging(logging =>
        {
            logging.ClearProviders();
            logging.AddConsole();
        });
```

추가 공급자는 다음을 참조하세요.

- [기본 제공 로깅 공급자](#built-in-logging-providers)
- [타사 로깅 공급자](#third-party-logging-providers)

## <a name="configure-a-service-that-depends-on-ilogger"></a>ILogger에 종속되는 서비스 구성

`ILogger<T>`에 종속되는 서비스를 구성하려면 생성자 주입을 사용하거나 팩터리 메서드를 제공합니다. 팩터리 메서드 접근 방식은 다른 옵션이 없는 경우에만 권장됩니다. 예를 들어 DI에서 제공하는 `ILogger<T>` 인스턴스가 필요한 서비스를 살펴보겠습니다.

```csharp
.ConfigureServices(services =>
    services.AddSingleton<IExampleService>(container =>
        new DefaultExampleService
        {
            Logger = container.GetRequiredService<ILogger<IExampleService>>()
        }));
```

이전 코드는 DI 컨테이너가 `IExampleService`의 인스턴스를 처음 생성해야 할 때 실행되는 [Func<IServiceProvider, IExampleService>](/dotnet/api/system.func-2)입니다. 이러한 방식으로 등록된 서비스에 액세스할 수 있습니다.

## <a name="built-in-logging-providers"></a>기본 로깅 공급자

Microsoft 확장에는 런타임 라이브러리의 일부로 다음 로깅 공급자가 포함됩니다.

- [콘솔](#console)
- [디버그](#debug)
- [EventSource](#event-source)
- [EventLog](#windows-eventlog)

다음 로깅 공급자는 Microsoft에서 제공되지만 런타임 라이브러리의 일부로 제공되지 않습니다. 해당 공급자는 추가 NuGet 패키지로 설치해야 합니다.

- [AzureAppServicesFile 및 AzureAppServicesBlob](#azure-app-service)
- [ApplicationInsights](#azure-application-insights)

### <a name="console"></a>Console

`Console` 공급자는 콘솔에 출력을 로그합니다.

### <a name="debug"></a>디버그

`Debug` 공급자는 [System.Diagnostics.Debug](/dotnet/api/system.diagnostics.debug) 클래스를 사용하여 로그 출력을 기록합니다. `System.Diagnostics.Debug.WriteLine`을 호출하여 `Debug` 공급자에 기록합니다.

Linux에서 `Debug` 공급자 로그 위치는 배포판마다 다르며 다음 중 하나일 수 있습니다.

- */var/log/message*
- */var/log/syslog*

### <a name="event-source"></a>이벤트 원본

`EventSource` 공급자는 이름이 `Microsoft-Extensions-Logging`인 플랫폼 간 이벤트 원본에 기록합니다. Windows에서 공급자는 [ETW](/windows/win32/etw/event-tracing-portal)를 사용합니다.

#### <a name="dotnet-trace-tooling"></a>dotnet 추적 도구

[dotnet 추적](../diagnostics/dotnet-trace.md) 도구는 실행 중인 프로세스의 .NET Core 추적을 수집할 수 있도록 하는 플랫폼 간 CLI 전역 도구입니다. 이 도구는 <xref:Microsoft.Extensions.Logging.EventSource.LoggingEventSource>를 사용하여 <xref:Microsoft.Extensions.Logging.EventSource> 공급자 데이터를 수집합니다.

설치 지침은 [dotnet-trace](../diagnostics/dotnet-trace.md)를 참조하세요. `dotnet-trace`를 사용하는 진단 자습서를 보려면 [.NET Core에서 높은 CPU 사용량 디버그](../diagnostics/debug-highcpu.md)를 참조하세요.

### <a name="windows-eventlog"></a>Windows EventLog

`EventLog` 공급자는 로그 출력을 Windows 이벤트 로그에 보냅니다. 다른 공급자와 달리 `EventLog` 공급자는 기본 비공급자 설정을 상속하지 ***않습니다***. `EventLog` 로그 설정을 지정하지 않으면 기본적으로 `LogLevel.Warning`으로 설정됩니다.

<xref:Microsoft.Extensions.Logging.LogLevel.Warning?displayProperty=nameWithType> 수준보다 낮은 이벤트를 기록하려면 로그 수준을 명시적으로 설정합니다. 다음 예제에서는 이벤트 로그 기본 로그 수준을 <xref:Microsoft.Extensions.Logging.LogLevel.Information?displayProperty=nameWithType>으로 설정합니다.

```json
"Logging": {
  "EventLog": {
    "LogLevel": {
      "Default": "Information"
    }
  }
}
```

[AddEventLog 오버로드](xref:Microsoft.Extensions.Logging.EventLoggerFactoryExtensions)는 <xref:Microsoft.Extensions.Logging.EventLog.EventLogSettings>를 전달할 수 있습니다. `null`이거나 지정하지 않으면 다음 기본 설정이 사용됩니다.

- `LogName`: “Application”
- `SourceName`: “.NET Runtime”
- `MachineName`: 로컬 머신 이름이 사용됩니다.

다음 코드에서는 `SourceName`을 기본값 `".NET Runtime"`에서 `CustomLogs`로 변경합니다.

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

### <a name="azure-app-service"></a>Azure App Service

[Microsoft.Extensions.Logging.AzureAppServices](https://www.nuget.org/packages/Microsoft.Extensions.Logging.AzureAppServices) 공급자 패키지는 Azure App Service 앱의 파일 시스템과 Azure Storage 계정의 [Blob 스토리지](/azure/storage/blobs/storage-quickstart-blobs-dotnet#what-is-blob-storage)에 텍스트 파일을 기록합니다.

공급자 패키지는 런타임 라이브러리에 포함되지 않습니다. 이 공급자를 사용하려면 프로젝트에 공급자 패키지를 추가합니다.

공급자 설정을 구성하려면 다음 예제와 같이 <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureFileLoggerOptions> 및 <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureBlobLoggerOptions>를 사용합니다.

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

Azure App Service에 배포하는 경우 앱은 Azure Portal에서 **App Service** 페이지에 있는 [App Service 로그](/azure/app-service/web-sites-enable-diagnostic-log/#enable-application-logging-windows) 섹션의 설정을 사용합니다. 다음 설정이 업데이트되면 앱을 다시 시작하거나 재배포하지 않아도 변경 내용이 즉시 적용됩니다.

- **애플리케이션 로깅(파일 시스템)**
- **애플리케이션 로깅(Blob)**

로그 파일의 기본 위치는 *D:\\home\\LogFiles\\Application* 폴더이며, 기본 파일 이름은 *diagnostics-yyyymmdd.txt* 입니다. 기본 파일 크기 제한은 10MB이고, 보존되는 기본 최대 파일 수는 2입니다. 기본 BLOB 이름은 *{app-name}{timestamp}/yyyy/mm/dd/hh/{guid}-applicationLog.txt* 입니다.

이 공급자는 프로젝트가 Azure 환경에서 실행되는 경우에만 로그합니다.

#### <a name="azure-log-streaming"></a>Azure 로그 스트리밍

Azure 로그 스트리밍을 통해 다음에서 로그 활동을 실시간으로 볼 수 있습니다.

- 앱 서버
- 웹 서버
- 실패한 요청 추적

Azure 로그 스트리밍을 구성하려면:

- 앱의 포털 페이지에서 **App Service 로그** 페이지로 이동합니다.
- **애플리케이션 로깅(파일 시스템)** 을 **On** 으로 설정합니다.
- 로그 **수준** 을 선택합니다. 이 설정은 Azure 로그 스트리밍에만 적용됩니다.

**로그 스트림** 페이지로 이동하여 로그를 봅니다. 로드되는 메시지는 `ILogger` 인터페이스를 사용하여 로그됩니다.

### <a name="azure-application-insights"></a>Azure Application Insights

[Microsoft.Extensions.Logging.ApplicationInsights](https://www.nuget.org/packages/Microsoft.Extensions.Logging.ApplicationInsights) 공급자 패키지는 [Azure Application Insights](/azure/azure-monitor/app/cloudservices)에 로그를 기록합니다. Application Insights는 웹앱을 모니터링하고 원격 분석 데이터를 쿼리 및 분석하기 위한 도구를 제공하는 서비스입니다. 이 공급자를 사용하는 경우 Application Insights 도구를 사용하여 로그를 쿼리 및 분석할 수 있습니다.

자세한 내용은 다음 자료를 참조하세요.

- [Application Insights 개요](/azure/application-insights/app-insights-overview)
- [.NET Core ILogger 로그용 ApplicationInsightsLoggerProvider](/azure/azure-monitor/app/ilogger) - 나머지 Application Insights 원격 분석 없이 로깅 공급자를 구현하려면 여기에서 시작합니다.
- [Application Insights 로깅 어댑터](/azure/azure-monitor/app/asp-net-trace-logs).
- [Application Insights SDK 설치, 구성 및 초기화](/learn/modules/instrument-web-app-code-with-application-insights) - Microsoft Learn 사이트의 대화형 자습서입니다.

## <a name="third-party-logging-providers"></a>타사 로깅 공급자

다음은 다양한 .NET 워크로드에서 작동하는 일부 타사 로깅 프레임워크입니다.

- [elmah.io](https://elmah.io)([GitHub 리포지토리](https://github.com/elmahio/Elmah.Io.Extensions.Logging))
- [Gelf](https://docs.graylog.org/en/2.3/pages/gelf.html)([GitHub 리포지토리](https://github.com/mattwcole/gelf-extensions-logging))
- [JSNLog](http://jsnlog.com)([GitHub 리포지토리](https://github.com/mperdeck/jsnlog))
- [KissLog.net](https://kisslog.net)([GitHub 리포지토리](https://github.com/catalingavan/KissLog-net))
- [Log4Net](https://logging.apache.org/log4net)([GitHub 리포지토리](https://github.com/apache/logging-log4net))
- [Loggr](https://loggr.net)([GitHub 리포지토리](https://github.com/imobile3/Loggr.Extensions.Logging))
- [NLog](https://nlog-project.org)([GitHub 리포지토리](https://github.com/NLog/NLog.Extensions.Logging))
- [NReco.Logging](https://github.com/nreco/logging/blob/master/README.md)([GitHub 리포지토리](https://github.com/nreco/logging))
- [Sentry](https://sentry.io/welcome) ([GitHub repo](https://github.com/getsentry/sentry-dotnet))
- [Serilog](https://serilog.net)([GitHub 리포지토리](https://github.com/serilog/serilog-sinks-console))
- [Stackdriver](https://cloud.google.com/dotnet/docs/stackdriver#logging)([GitHub 리포지토리](https://github.com/googleapis/google-cloud-dotnet))

일부 타사 프레임워크는 [구조적 로깅이라고 하는 의미 체계 로깅](https://softwareengineering.stackexchange.com/questions/312197/benefits-of-structured-logging-vs-basic-logging)을 수행할 수 있습니다.

타사 프레임워크를 사용하는 방법은 다음과 같이 기본 공급자 중 하나를 사용하는 방법과 비슷합니다.

1. 프로젝트에 NuGet 패키지를 추가합니다.
1. 로깅 프레임워크에서 제공되는 `ILoggerFactory` 또는 `ILoggingBuilder` 확장 메서드를 호출합니다.

자세한 내용은 각 공급자의 설명서를 참조하세요. 타사 로깅 공급자는 Microsoft에서 지원되지 않습니다.

## <a name="see-also"></a>참고 항목

- [.NET에 로그인](logging.md)
- [.NET에서 사용자 지정 로깅 공급자 구현](custom-logging-provider.md)
- [.NET의 고성능 로깅](high-performance-logging.md)
