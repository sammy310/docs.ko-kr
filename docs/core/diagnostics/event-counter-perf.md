---
title: .NET Core에서 EventCounters를 사용하여 성능 측정
description: 이 자습서에서는 EventCounters를 사용하여 성능을 측정하는 방법을 알아봅니다.
ms.date: 08/07/2020
ms.topic: tutorial
ms.openlocfilehash: 7b4940e17d01e7ec5a50d11e3c818ecdec2d48cf
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024972"
---
# <a name="tutorial-measure-performance-using-eventcounters-in-net-core"></a>자습서: .NET Core에서 EventCounters를 사용하여 성능 측정

**이 문서의 적용 대상:** ✔️ .NET Core 3.0 SDK 이상 버전

이 자습서에서는 이벤트 빈도가 높을 경우 성능을 측정하는 데 <xref:System.Diagnostics.Tracing.EventCounter>를 사용하는 방법을 알아봅니다. 다양한 공식 .NET Core 패키지, 타사 공급자가 게시한 [사용 가능한 카운터](event-counters.md#available-counters)를 사용하거나 모니터링을 위한 자체 메트릭을 만들 수 있습니다.

이 자습서에서는 다음을 수행합니다.

> [!div class="checklist"]
>
> - <xref:System.Diagnostics.Tracing.EventSource>를 구현합니다.
> - [dotnet-counters](dotnet-counters.md)로 카운터를 모니터링합니다.

## <a name="prerequisites"></a>사전 요구 사항

이 자습서에서는 다음을 사용합니다.

- [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) 이상 버전.
- 이벤트 카운터를 모니터링하기 위한 [dotnet-counters](dotnet-counters.md)
- 진단할 [샘플 디버그 대상](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) 앱.

## <a name="get-the-source"></a>소스 가져오기

이 애플리케이션 예제는 모니터링의 기준으로 사용됩니다. [샘플 ASP.NET Core 리포지토리](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios)는 샘플 브라우저에서 사용할 수 있습니다. zip 파일을 다운로드하고, 다운로드가 끝나면 압축을 풀고, 즐겨 사용하는 IDE에서 엽니다. 애플리케이션을 빌드하고 실행하여 제대로 작동하는지 확인한 다음, 애플리케이션을 중지합니다.

## <a name="implement-an-eventsource"></a>EventSource 구현

밀리초 간격으로 발생하는 이벤트의 경우 이벤트당 오버헤드를 밀리초 미만으로 줄일 수 있습니다. 그러지 않으면 성능에 지대한 영향을 미칠 수 있습니다. 이벤트를 로깅하는 것은 디스크에 무언가를 쓰게 된다는 것을 의미합니다. 디스크가 충분하지 않으면 이벤트가 손실됩니다. 이벤트 자체를 기록하는 것 이외의 솔루션이 필요합니다.

많은 이벤트를 처리할 때 이벤트별 측정값을 파악하는 것은 유용하지 않습니다. 대부분의 경우에는 일부 통계만 있으면 됩니다. 따라서 프로세스 자체 내에서 통계를 가져온 다음, 경우에 따라 통계를 보고하는 이벤트를 작성할 수 있습니다. 이것이 <xref:System.Diagnostics.Tracing.EventCounter>가 수행하는 작업입니다.

다음은 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>를 구현하는 방법의 예입니다. *MinimalEventCounterSource.cs*라는 새 파일을 만들고 코드 조각을 소스로 사용합니다.

:::code language="csharp" source="snippets/EventCounters/MinimalEventCounterSource.cs":::

<xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=nameWithType> 줄은 <xref:System.Diagnostics.Tracing.EventSource>의 일부이며 <xref:System.Diagnostics.Tracing.EventCounter>에 속하지 않으므로 이벤트 카운터와 함께 메시지를 기록할 수 있음을 보여 주기 위해 작성되었습니다.

## <a name="add-an-action-filter"></a>작업 필터 추가

샘플 소스 코드는 ASP.NET Core 프로젝트입니다. 전체 요청 시간을 기록하는 [작업 필터](/aspnet/core/mvc/controllers/filters#action-filters)를 전역적으로 추가할 수 있습니다. *LogRequestTimeFilterAttribute.cs*라는 새 파일을 만들고 다음 코드를 사용합니다.

```csharp
using System.Diagnostics;
using Microsoft.AspNetCore.Http.Extensions;
using Microsoft.AspNetCore.Mvc.Filters;

namespace DiagnosticScenarios
{
    public class LogRequestTimeFilterAttribute : ActionFilterAttribute
    {
        readonly Stopwatch _stopwatch = new Stopwatch();

        public override void OnActionExecuting(ActionExecutingContext context) => _stopwatch.Start();

        public override void OnActionExecuted(ActionExecutedContext context)
        {
            _stopwatch.Stop();

            MinimalEventCounterSource.Log.Request(
                context.HttpContext.Request.GetDisplayUrl(), _stopwatch.ElapsedMilliseconds);
        }
    }
}
```

작업 필터는 요청이 시작되면 <xref:System.Diagnostics.Stopwatch>를 시작하고, 완료되면 중지된 후 경과된 시간을 캡처합니다. 총 시간(밀리초)은 `MinimalEventCounterSource` singleton 인스턴스에 기록됩니다. 이 필터를 적용하려면 필터 컬렉션에 추가해야 합니다. *Startup.cs* 파일에서 이 필터에 포함된 `ConfigureServices` 메서드를 업데이트합니다.

```csharp
public void ConfigureServices(IServiceCollection services) =>
    services.AddControllers(options => options.Filters.Add<LogRequestTimeFilterAttribute>())
            .AddNewtonsoftJson();
```

## <a name="monitor-event-counter"></a>이벤트 카운터 모니터링

<xref:System.Diagnostics.Tracing.EventSource>에 대한 구현과 사용자 지정 작업 필터를 사용하여 애플리케이션을 빌드하고 시작합니다.
메트릭을 <xref:System.Diagnostics.Tracing.EventCounter>에 기록했더라도 해당 통계에 액세스하지 않으면 도움이 되지 않습니다. 통계를 얻으려면 이벤트를 원하는 만큼 자주 발생시키는 타이머와 이벤트를 캡처하는 수신기를 만들어 <xref:System.Diagnostics.Tracing.EventCounter>를 사용하도록 설정해야 합니다. 이렇게 하려면 [dotnet-counters](dotnet-counters.md)를 사용할 수 있습니다.

[dotnet-counters ps](dotnet-counters.md#dotnet-counters-ps) 명령을 사용하여 모니터링할 수 있는 .NET 프로세스의 목록을 표시합니다.

```console
dotnet-counters ps
```

`dotnet-counters ps` 명령 출력의 프로세스 식별자를 사용하면 다음 `dotnet-counters monitor` 명령을 사용하여 이벤트 카운터 모니터링을 시작할 수 있습니다.

```console
dotnet-counters monitor --process-id 2196 Sample.EventCounter.Minimal Microsoft.AspNetCore.Hosting[total-requests,requests-per-second] System.Runtime[cpu-usage]
```

`dotnet-counters monitor` 명령이 실행되는 동안 브라우저에서 <kbd>F5</kbd> 키를 눌러 `https://localhost:5001/api/values` 엔드포인트에 대한 연속 요청 실행을 시작합니다. 몇 초 후에 <kbd>q</kbd>를 눌러 중지합니다.

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[Microsoft.AspNetCore.Hosting]
    Request Rate / 1 sec                               9
    Total Requests                                   134
[System.Runtime]
    CPU Usage (%)                                     13
[Sample.EventCounter.Minimal]
    Request Processing Time (ms)                      34.5
```

`dotnet-counters monitor` 명령은 활성 모니터링에 적합합니다. 그러나 사후 처리 및 분석을 위해 이러한 진단 메트릭을 수집하는 것이 좋습니다. 이 경우 `dotnet-counters collect` 명령을 사용합니다. `collect` 스위치 명령은 `monitor` 명령과 비슷하지만 몇 가지 추가 매개 변수를 허용합니다. 원하는 출력 파일 이름과 형식을 지정할 수 있습니다. *diagnostics.json*이라는 JSON 파일의 경우 다음 명령을 사용합니다.

```console
dotnet-counters collect --process-id 2196 --format json -o diagnostics.json Sample.EventCounter.Minimal Microsoft.AspNetCore.Hosting[total-requests,requests-per-second] System.Runtime[cpu-usage]
```

이 명령이 실행되는 동안 브라우저에서 <kbd>F5</kbd> 키를 다시 눌러 `https://localhost:5001/api/values` 엔드포인트에 대한 연속 요청 실행을 시작합니다. 몇 초 후에 <kbd>q</kbd>를 눌러 중지합니다. *diagnostics.json* 파일이 기록됩니다. 그러나 기록된 JSON 파일은 들여쓰여지지 않습니다. 그렇지만 여기서는 가독성을 위해 들여쓴 상태로 표시됩니다.

```json
{
  "TargetProcess": "DiagnosticScenarios",
  "StartTime": "8/5/2020 3:02:45 PM",
  "Events": [
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "System.Runtime",
      "name": "CPU Usage (%)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Request Rate / 1 sec",
      "counterType": "Rate",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Total Requests",
      "counterType": "Metric",
      "value": 134
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "Sample.EventCounter.Minimal",
      "name": "Request Processing Time (ms)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "System.Runtime",
      "name": "CPU Usage (%)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Request Rate / 1 sec",
      "counterType": "Rate",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Total Requests",
      "counterType": "Metric",
      "value": 134
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "Sample.EventCounter.Minimal",
      "name": "Request Processing Time (ms)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "System.Runtime",
      "name": "CPU Usage (%)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:50Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Request Rate / 1 sec",
      "counterType": "Rate",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:50Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Total Requests",
      "counterType": "Metric",
      "value": 134
    },
    {
      "timestamp": "2020-08-05 15:02:50Z",
      "provider": "Sample.EventCounter.Minimal",
      "name": "Request Processing Time (ms)",
      "counterType": "Metric",
      "value": 0
    }
  ]
}
```

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [EventCounters](event-counters.md)
