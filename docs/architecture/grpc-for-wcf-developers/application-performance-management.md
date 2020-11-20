---
title: 응용 프로그램 성능 관리-WCF 개발자를 위한 gRPC
description: ASP.NET Core gRPC 응용 프로그램에 대 한 로깅, 메트릭 및 추적입니다.
ms.date: 09/02/2019
ms.openlocfilehash: 8a13d1c4df95768e55c90ac491150bfc78ec2bab
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982344"
---
# <a name="application-performance-management"></a>애플리케이션 성능 관리

Kubernetes와 같은 프로덕션 환경에서는 응용 프로그램이 최적으로 실행 되 고 있는지 확인 하는 것이 중요 합니다. 로깅 및 메트릭은 특히 중요 합니다. GRPC를 비롯 한 ASP.NET Core는 *추적* 데이터 뿐만 아니라 로그 메시지 및 메트릭 데이터를 생성 하 고 관리 하기 위한 기본 제공 지원을 제공 합니다.

## <a name="the-difference-between-logging-and-metrics"></a>로깅 및 메트릭 간의 차이점

*로깅은* 시스템에서 발생 한 작업에 대 한 세부 정보를 기록 하는 텍스트 메시지와 관련 됩니다. 로그 메시지에는 스택 추적과 같은 예외 데이터 또는 메시지에 대 한 컨텍스트를 제공 하는 구조화 된 데이터가 포함 될 수 있습니다. 로깅 출력은 일반적으로 검색 가능한 텍스트 저장소에 기록 됩니다.

*메트릭은* 대시보드에서 차트 및 그래프를 사용 하 여 집계 하 고 표시 하도록 디자인 된 숫자 데이터를 나타냅니다. 대시보드는 응용 프로그램의 전반적인 상태 및 성능에 대 한 뷰를 제공 합니다. 임계값을 초과 하는 경우 메트릭 데이터를 사용 하 여 자동화 된 경고를 트리거할 수도 있습니다. 다음은 메트릭 데이터의 몇 가지 예입니다.

- 요청을 처리 하는 데 걸린 시간입니다.
- 서비스 인스턴스에서 처리 되는 초당 요청 수입니다.
- 인스턴스의 실패 한 요청 수입니다.

## <a name="logging-in-aspnet-core-grpc"></a>ASP.NET Core gRPC 로그인

ASP.NET Core은 [Microsoft. Extensions. 로깅](https://www.nuget.org/packages/Microsoft.Extensions.Logging) NuGet 패키지의 형태로 로깅을 기본적으로 지원 합니다. 이 라이브러리의 핵심 부분은 웹 SDK에 포함 되어 있으므로 수동으로 설치할 필요가 없습니다. 기본적으로 로그 메시지는 표준 출력 ("콘솔") 및 연결 된 디버거에 기록 됩니다. 영구 외부 데이터 저장소에 로그를 쓰려면 [선택적 로깅 싱크 패키지](/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0#third-party-logging-providers)를 가져와야 할 수 있습니다.

ASP.NET Core gRPC 프레임 워크는이 로깅 프레임 워크에 자세한 진단 로깅 메시지를 작성 하므로 응용 프로그램 자체의 메시지와 함께 처리 하 고 저장할 수 있습니다.

### <a name="produce-log-messages"></a>로그 메시지 생성

로깅 확장은 ASP.NET Core의 종속성 주입 시스템에 자동으로 등록 되므로 gRPC 서비스 유형에 서로 거를 생성자 매개 변수로 지정할 수 있습니다.

```csharp
public class StockData : Stocks.StocksBase
{
    private readonly ILogger<StockData> _logger;

    public StockData(ILogger<StockData> logger)
    {
        _logger = logger;
    }
}
```

요청 및 예외와 같은 많은 로그 메시지는 ASP.NET Core 및 gRPC 프레임 워크 구성 요소에 의해 제공 됩니다. 사용자 고유의 로그 메시지를 추가 하 여 하위 수준의 문제 보다는 응용 프로그램 논리에 대 한 세부 정보 및 컨텍스트를 제공 합니다.

로그 메시지 및 사용 가능한 로깅 싱크 및 대상을 작성 하는 방법에 대 한 자세한 내용은  [.Net Core의 로깅 및 ASP.NET Core](/aspnet/core/fundamentals/logging/)을 참조 하세요.

## <a name="metrics-in-aspnet-core-grpc"></a>ASP.NET Core gRPC의 메트릭

.NET Core 런타임은 메트릭을 내보내고 관찰 하기 위한 구성 요소 집합을 제공 합니다. 여기에는 및 클래스와 같은 Api가 포함 <xref:System.Diagnostics.Tracing.EventSource> <xref:System.Diagnostics.Tracing.EventCounter> 됩니다. 이러한 Api는 [dotnet 카운터 전역 ETW(Windows용 이벤트 추적) 도구](../../core/diagnostics/dotnet-counters.md)등의 외부 프로세스에서 사용할 수 있는 기본 숫자 데이터를 내보낼 수 있습니다. 사용자 고유의 코드에서를 사용 하는 방법에 대 한 자세한 내용은 `EventCounter` [eventcounter 소개](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md)를 참조 하세요.

고급 메트릭 및 더 광범위 한 데이터 저장소에 메트릭 데이터를 작성 하는 경우 [앱 메트릭](https://www.app-metrics.io)이라는 오픈 소스 프로젝트를 사용해 볼 수 있습니다. 이 라이브러리 집합은 코드를 계측할 수 있는 광범위 한 형식을 제공 합니다. 또한 [Application Insights](/azure/azure-monitor/app/app-insights-overview)InfluxDB와 같은 시계열 데이터베이스를 포함 하는 다양 한 종류의 대상에 메트릭을 기록 하는 패키지를 제공 합니다. [AspNetCore](https://www.nuget.org/packages/App.Metrics.AspNetCore.Mvc/) NuGet 패키지는 ASP.NET Core 프레임 워크와의 통합을 통해 자동으로 생성 되는 포괄적인 기본 메트릭 집합을 추가 합니다. 프로젝트 웹 사이트는 [Grafana](https://grafana.com/) 시각화 플랫폼을 사용 하 여 이러한 메트릭을 표시 하기 위한 [템플릿을](https://www.app-metrics.io/samples/grafana/) 제공 합니다.

### <a name="produce-metrics"></a>메트릭 생성

대부분의 메트릭 플랫폼은 다음 형식을 지원 합니다.

| 메트릭 유형 | 설명 |
| ----------- | ----------- |
| 카운터     | 요청 및 오류와 같은 상황이 발생 하는 빈도를 추적 합니다. |
| 계기       | 활성 연결과 같이 시간이 지남에 따라 변경 되는 단일 값을 기록 합니다. |
| 히스토그램   | 임의의 한도에 걸쳐 값의 분포를 측정 합니다. 예를 들어 히스토그램은 데이터 집합 크기를 추적할 수 있습니다. 여기에 포함 된 <10 개 레코드 수, 포함 된 11-100 레코드 수, 포함 된 101-1000 레코드 수, 포함 된 >1000 레코드 수를 계산 합니다. |
| 미터       | 다양 한 시간 범위에서 이벤트가 발생 하는 속도를 측정 합니다. |
| 타이머       | 히스토그램으로 저장 된 이벤트 기간과 발생 비율을 추적 합니다. |

*앱 메트릭을* 사용 하 여 `IMetrics` 종속성 주입을 통해 인터페이스를 가져오고 grpc 서비스에 대해 이러한 메트릭을 기록 하는 데 사용할 수 있습니다. 다음 예제에서는 `Get` 시간이 지남에 따라 생성 된 요청 수를 계산 하는 방법을 보여 줍니다.

```csharp
public class StockData : Stocks.StocksBase
{
    private static readonly CounterOptions GetRequestCounter = new CounterOptions
    {
        Name = "StockData_Get_Requests",
        MeasurementUnit = Unit.Calls
    };

    private readonly IStockRepository _repository;
    private readonly IMetrics _metrics;

    public StockData(IStockRepository repository, IMetrics metrics)
    {
        _repository = repository;
        _metrics = metrics;
    }

    public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
    {
        _metrics.Measure.Counter.Increment(GetRequestCounter);

        // Serve request...
    }
}
```

### <a name="store-and-visualize-metrics-data"></a>메트릭 데이터 저장 및 시각화

메트릭 데이터를 저장 하는 가장 좋은 방법은 타임 스탬프로 표시 된 숫자 데이터 계열을 기록 하도록 디자인 된 특수화 된 데이터 저장소 인 *시계열 데이터베이스* 에 있습니다. 이러한 데이터베이스 중 가장 인기 있는 것은 [프로메테우스](https://prometheus.io/) 및 [InfluxDB](https://www.influxdata.com/products/influxdb-overview/)입니다. Microsoft Azure은 [Azure Monitor](/azure/azure-monitor/overview) 서비스를 통해 전용 메트릭 저장소도 제공 합니다.

메트릭 데이터를 시각화 하기 위한 최신 솔루션은 다양 한 저장소 공급자에서 작동 하는 [Grafana](https://grafana.com)입니다. 다음 이미지는 StockData 예제를 실행 하는 Linkerd 서비스 메시의 메트릭을 표시 하는 예제 Grafana 대시보드를 보여 줍니다.

![Grafana 대시보드의 스크린샷](media/application-performance-management/grafana-screenshot.png)

### <a name="metrics-based-alerting"></a>메트릭 기반 경고

메트릭 데이터의 숫자 특성은 값이 정의 된 허용 오차를 벗어날 때 개발자에 게 알리거나 지원 엔지니어에 게 알리기 위해 가장 적합 한 경고 시스템을 의미 합니다. 이미 언급 된 플랫폼은 전자 메일, 문자 메시지 또는 대시보드 내 시각화를 비롯 한 다양 한 옵션을 통해 경고에 대 한 지원을 제공 합니다.

## <a name="distributed-tracing"></a>분산된 추적

분산 추적은 마이크로 서비스 및 분산 아키텍처를 사용 하 여 확신이 없을 하는 모니터링의 비교적 최근 개발입니다. 클라이언트 브라우저, 응용 프로그램 또는 장치의 단일 요청을 여러 단계와 하위 요청으로 분할 하 고 네트워크에서 많은 서비스를 사용 하는 것을 포함할 수 있습니다. 이렇게 하면 로그 메시지와 메트릭이 트리거된 특정 요청과의 상관 관계를 지정 하기가 어렵습니다. 분산 추적은 요청에 식별자를 적용 하며,이를 통해 로그와 메트릭을 특정 작업과 상관 관계를 지정할 수 있습니다. 이는 [WCF의 종단 간 추적과](../../framework/wcf/diagnostics/tracing/end-to-end-tracing.md)유사 하지만 여러 플랫폼에서 적용 됩니다.

분산 추적은 인기에서 빠르게 성장 하 고 표준화를 시작 합니다. Cloud Native 컴퓨팅 파운데이션은 [오픈 추적 표준을](https://opentracing.io)만들었으며 [JAEGER](https://www.jaegertracing.io/) 및 [탄력적 APM](https://www.elastic.co/products/apm)과 같은 백 엔드 작업을 위한 공급 업체 중립적 라이브러리를 제공 하려고 합니다. 동시에 Google은 동일한 문제 집합을 해결 하기 위해 [OpenCensus 프로젝트](https://opencensus.io/) 를 만들었습니다. 이러한 두 프로젝트는 새 프로젝트 [OpenTelemetry](https://opentelemetry.io)에 병합 되며,이는 미래의 업계 표준입니다.

### <a name="how-distributed-tracing-works"></a>분산 추적 작동 방법

분산 추적은 단일 *추적* 의 일부인 명명 된 시간 제한 *작업의 개념* 을 기반으로 하며,이는 시스템의 여러 노드에서 처리를 포함할 수 있습니다. 새 작업이 시작 되 면 고유 식별자를 사용 하 여 추적이 생성 됩니다. 각 하위 작업에 대해 고유 식별자 및 추적 식별자를 사용 하 여 범위를 만듭니다. 요청이 시스템을 통과할 때 다양 한 구성 요소가 *부모* 의 식별자를 포함 하는 *자식* 범위를 만들 수 있습니다. 범위에는 추적 및 범위 식별자와 키/값 쌍 ( *수하물* 이라고 함) 형식의 유용한 데이터가 포함 된 *컨텍스트가* 있습니다.

### <a name="distributed-tracing-with-diagnosticsource"></a>분산 추적 `DiagnosticSource`

.NET Core에는 분산 추적 및 범위에 잘 매핑되는 내부 모듈이 있습니다. [DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md#diagnosticsource-users-guide). 프로세스 내에서 진단을 생성 하 고 사용 하는 간단한 방법을 제공 하는 것 외에도 모듈에는 `DiagnosticSource` *활동* 의 개념이 있습니다. 활동은 효과적으로 분산 추적의 구현 이거나 추적 내의 범위입니다. 모듈의 내부에서는 식별자 할당을 비롯 한 부모/자식 활동을 처리 합니다. 형식을 사용 하는 방법에 대 한 자세한 내용은 `Activity` [GitHub의 작업 사용자 가이드](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/ActivityUserGuide.md#activity-user-guide)를 참조 하세요.

`DiagnosticSource`는 핵심 프레임 워크의 일부 이기 때문에 몇 가지 핵심 구성 요소에서 지원 됩니다. 여기에는 <xref:System.Net.Http.HttpClient> gRPC 프레임 워크의 명시적 지원을 포함 하 여 Entity Framework Core 및 ASP.NET Core 있습니다. ASP.NET Core 요청을 받으면 [W3C 추적 컨텍스트](https://www.w3.org/TR/trace-context) 표준과 일치 하는 HTTP 헤더 쌍을 확인 합니다. 헤더가 발견 되 면 헤더의 id 값과 컨텍스트를 사용 하 여 활동이 시작 됩니다. 헤더를 찾을 수 없는 경우 작업은 표준 형식과 일치 하는 생성 된 id 값으로 시작 됩니다. 이 활동의 수명 동안 프레임 워크 또는 응용 프로그램 코드에 의해 생성 된 진단은 추적 및 범위 식별자로 태그를 지정할 수 있습니다. `HttpClient`모든 요청에서 현재 활동을 확인 하 고 보내는 요청에 추적 헤더를 자동으로 추가 하 여이를 더 확장 합니다.

ASP.NET Core gRPC 클라이언트 및 서버 라이브러리는 및에 대 한 명시적 지원을 포함 하 고 `DiagnosticSource` `Activity` , 작업을 만들고 헤더 정보를 자동으로 적용 및 사용 합니다.

> [!NOTE]
> 이 모든 것은 수신기에서 진단 정보를 사용 하는 경우에만 발생 합니다. 수신기가 없는 경우에는 진단이 기록 되지 않으며 활동이 생성 되지 않습니다.

### <a name="add-your-own-diagnosticsource-and-activity"></a>`DiagnosticSource`직접 추가`Activity`

사용자 고유의 진단을 추가 하거나 응용 프로그램 코드 내에서 명시적 범위를 만들려면 [DiagnosticSource 사용자 가이드](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md#instrumenting-with-diagnosticsourcediagnosticlistener) 및 [활동 사용자 가이드](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/ActivityUserGuide.md#activity-usage)를 참조 하세요.

### <a name="store-distributed-trace-data"></a>분산 추적 데이터 저장

이 문서를 작성할 당시에는 OpenTelemetry 프로젝트가 아직 초기 단계에 있으므로 .NET 응용 프로그램에는 알파 품질 패키지만 사용할 수 있습니다. OpenTracing 프로젝트는 현재 더 완성도 높은 라이브러리를 제공 합니다.

OpenTracing API는 다음 섹션에 설명 되어 있습니다. 응용 프로그램에서 OpenTelemetry API를 대신 사용 하려는 경우 GitHub의 [OpenTelemetry .NET SDK 리포지토리](https://github.com/open-telemetry/opentelemetry-dotnet) 를 참조 하세요.

#### <a name="use-the-opentracing-package-to-store-distributed-trace-data"></a>OpenTracing 패키지를 사용 하 여 분산 추적 데이터 저장

[OpenTracing NuGet 패키지](https://www.nuget.org/packages/OpenTracing/) 는와 독립적으로 사용할 수 있는 모든 OpenTracing 규격 백 엔드를 지원 합니다 `DiagnosticSource` . OpenTracing API 기여 프로젝트인 [OpenTracing core](https://www.nuget.org/packages/OpenTracing.Contrib.NetCore/)에서 추가 패키지가 있습니다. 이 패키지는 수신기를 추가 `DiagnosticSource` 하 고 백 엔드에 이벤트와 활동을 자동으로 기록 합니다. 이 패키지를 사용 하도록 설정 하는 것은 NuGet에서 설치 하 고 클래스에서 서비스로 추가 하는 것 만큼 간단 `Startup` 합니다.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddOpenTracing();
    }
}
```

OpenTracing 패키지는 추상화 계층 이므로 백 엔드와 관련 된 구현이 필요 합니다. OpenTracing API 구현은 다음과 같은 오픈 소스 백 엔드에 사용할 수 있습니다.

| 이름 | 패키지 | 웹 사이트 |
| ---- | ------- | -------- |
| Jaeger | [Jaeger](https://www.nuget.org/packages/Jaeger/) | [jaegertracing.io](https://jaegertracing.io) |
| 탄력적 APM | [NetCoreAll](https://www.nuget.org/packages/Elastic.Apm.NetCoreAll/) | [elastic.co/products/apm](https://www.elastic.co/products/apm) |

.NET 용 OpenTracing API에 대 한 자세한 내용은 GitHub의 [OpenTracing](https://github.com/opentracing/opentracing-csharp) 및 [OpenTracing, c #/.net Core](https://github.com/opentracing-contrib/csharp-netcore) 리포지토리 (영문)를 참조 하세요.

>[!div class="step-by-step"]
>[이전](load-balancing.md)
>[다음](appendix.md)
