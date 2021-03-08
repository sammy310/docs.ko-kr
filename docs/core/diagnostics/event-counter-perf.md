---
title: .NET Core에서 EventCounters를 사용하여 성능 측정
description: 이 자습서에서는 EventCounters를 사용하여 성능을 측정하는 방법을 알아봅니다.
ms.date: 08/07/2020
ms.topic: tutorial
ms.openlocfilehash: bde54ce1996b2f4e2a703c23384eadece06e66cb
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105312"
---
# <a name="tutorial-measure-performance-using-eventcounters-in-net-core"></a><span data-ttu-id="fe54a-103">자습서: .NET Core에서 EventCounters를 사용하여 성능 측정</span><span class="sxs-lookup"><span data-stu-id="fe54a-103">Tutorial: Measure performance using EventCounters in .NET Core</span></span>

<span data-ttu-id="fe54a-104">**이 문서의 적용 대상:** ✔️ .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="fe54a-104">**This article applies to: ✔️** .NET Core 3.0 SDK and later versions</span></span>

<span data-ttu-id="fe54a-105">이 자습서에서는 이벤트 빈도가 높을 경우 성능을 측정하는 데 <xref:System.Diagnostics.Tracing.EventCounter>를 사용하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-105">In this tutorial, you'll learn how an <xref:System.Diagnostics.Tracing.EventCounter> can be used to measure performance with a high frequency of events.</span></span> <span data-ttu-id="fe54a-106">다양한 공식 .NET Core 패키지, 타사 공급자가 게시한 [사용 가능한 카운터](available-counters.md)를 사용하거나 모니터링을 위한 자체 메트릭을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-106">You can use the [available counters](available-counters.md) published by various official .NET Core packages, third-party providers, or create your own metrics for monitoring.</span></span>

<span data-ttu-id="fe54a-107">이 자습서에서는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-107">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="fe54a-108"><xref:System.Diagnostics.Tracing.EventSource>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-108">Implement an <xref:System.Diagnostics.Tracing.EventSource>.</span></span>
> - <span data-ttu-id="fe54a-109">[dotnet-counters](dotnet-counters.md)로 카운터를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-109">Monitor counters with [dotnet-counters](dotnet-counters.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fe54a-110">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe54a-110">Prerequisites</span></span>

<span data-ttu-id="fe54a-111">이 자습서에서는 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-111">The tutorial uses:</span></span>

- <span data-ttu-id="fe54a-112">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet) 이상 버전.</span><span class="sxs-lookup"><span data-stu-id="fe54a-112">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet) or a later version.</span></span>
- <span data-ttu-id="fe54a-113">이벤트 카운터를 모니터링하기 위한 [dotnet-counters](dotnet-counters.md)</span><span class="sxs-lookup"><span data-stu-id="fe54a-113">[dotnet-counters](dotnet-counters.md) to monitor event counters.</span></span>
- <span data-ttu-id="fe54a-114">진단할 [샘플 디버그 대상](/samples/dotnet/samples/diagnostic-scenarios) 앱.</span><span class="sxs-lookup"><span data-stu-id="fe54a-114">A [sample debug target](/samples/dotnet/samples/diagnostic-scenarios) app to diagnose.</span></span>

## <a name="get-the-source"></a><span data-ttu-id="fe54a-115">소스 가져오기</span><span class="sxs-lookup"><span data-stu-id="fe54a-115">Get the source</span></span>

<span data-ttu-id="fe54a-116">이 애플리케이션 예제는 모니터링의 기준으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-116">The sample application will be used as a basis for monitoring.</span></span> <span data-ttu-id="fe54a-117">[샘플 ASP.NET Core 리포지토리](/samples/dotnet/samples/diagnostic-scenarios)는 샘플 브라우저에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-117">The [sample ASP.NET Core repository](/samples/dotnet/samples/diagnostic-scenarios) is available from the samples browser.</span></span> <span data-ttu-id="fe54a-118">zip 파일을 다운로드하고, 다운로드가 끝나면 압축을 풀고, 즐겨 사용하는 IDE에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-118">You download the zip file, extract it once downloaded, and open it in your favorite IDE.</span></span> <span data-ttu-id="fe54a-119">애플리케이션을 빌드하고 실행하여 제대로 작동하는지 확인한 다음, 애플리케이션을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-119">Build and run the application to ensure that it works properly, then stop the application.</span></span>

## <a name="implement-an-eventsource"></a><span data-ttu-id="fe54a-120">EventSource 구현</span><span class="sxs-lookup"><span data-stu-id="fe54a-120">Implement an EventSource</span></span>

<span data-ttu-id="fe54a-121">밀리초 간격으로 발생하는 이벤트의 경우 이벤트당 오버헤드를 밀리초 미만으로 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-121">For events that happen every few milliseconds, you'll want the overhead per event to be low (less than a millisecond).</span></span> <span data-ttu-id="fe54a-122">그러지 않으면 성능에 지대한 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-122">Otherwise, the impact on performance will be significant.</span></span> <span data-ttu-id="fe54a-123">이벤트를 로깅하는 것은 디스크에 무언가를 쓰게 된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-123">Logging an event means you're going to write something to disk.</span></span> <span data-ttu-id="fe54a-124">디스크가 충분하지 않으면 이벤트가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-124">If the disk is not fast enough, you will lose events.</span></span> <span data-ttu-id="fe54a-125">이벤트 자체를 기록하는 것 이외의 솔루션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-125">You need a solution other than logging the event itself.</span></span>

<span data-ttu-id="fe54a-126">많은 이벤트를 처리할 때 이벤트별 측정값을 파악하는 것은 유용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-126">When dealing with a large number of events, knowing the measure per event is not useful either.</span></span> <span data-ttu-id="fe54a-127">대부분의 경우에는 일부 통계만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-127">Most of the time all you need is just some statistics out of it.</span></span> <span data-ttu-id="fe54a-128">따라서 프로세스 자체 내에서 통계를 가져온 다음, 경우에 따라 통계를 보고하는 이벤트를 작성할 수 있습니다. 이것이 <xref:System.Diagnostics.Tracing.EventCounter>가 수행하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-128">So you could get the statistics within the process itself and then write an event once in a while to report the statistics, that's what <xref:System.Diagnostics.Tracing.EventCounter> will do.</span></span>

<span data-ttu-id="fe54a-129">다음은 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>를 구현하는 방법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-129">Below is an example of how to implement an <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>.</span></span> <span data-ttu-id="fe54a-130">*MinimalEventCounterSource.cs* 라는 새 파일을 만들고 코드 조각을 소스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-130">Create a new file named *MinimalEventCounterSource.cs* and use the code snippet as its source:</span></span>

:::code language="csharp" source="snippets/EventCounters/MinimalEventCounterSource.cs":::

<span data-ttu-id="fe54a-131"><xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=nameWithType> 줄은 <xref:System.Diagnostics.Tracing.EventSource>의 일부이며 <xref:System.Diagnostics.Tracing.EventCounter>에 속하지 않으므로 이벤트 카운터와 함께 메시지를 기록할 수 있음을 보여 주기 위해 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-131">The <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=nameWithType> line is the <xref:System.Diagnostics.Tracing.EventSource> part and is not part of <xref:System.Diagnostics.Tracing.EventCounter>, it was written to show that you can log a message together with the event counter.</span></span>

## <a name="add-an-action-filter"></a><span data-ttu-id="fe54a-132">작업 필터 추가</span><span class="sxs-lookup"><span data-stu-id="fe54a-132">Add an action filter</span></span>

<span data-ttu-id="fe54a-133">샘플 소스 코드는 ASP.NET Core 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-133">The sample source code is an ASP.NET Core project.</span></span> <span data-ttu-id="fe54a-134">전체 요청 시간을 기록하는 [작업 필터](/aspnet/core/mvc/controllers/filters#action-filters)를 전역적으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-134">You can add an [action filter](/aspnet/core/mvc/controllers/filters#action-filters) globally that will log the total request time.</span></span> <span data-ttu-id="fe54a-135">*LogRequestTimeFilterAttribute.cs* 라는 새 파일을 만들고 다음 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-135">Create a new file named *LogRequestTimeFilterAttribute.cs*, and use the following code:</span></span>

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

<span data-ttu-id="fe54a-136">작업 필터는 요청이 시작되면 <xref:System.Diagnostics.Stopwatch>를 시작하고, 완료되면 중지된 후 경과된 시간을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-136">The action filter starts a <xref:System.Diagnostics.Stopwatch> as the request begins, and stops after it has completed, capturing the elapsed time.</span></span> <span data-ttu-id="fe54a-137">총 시간(밀리초)은 `MinimalEventCounterSource` singleton 인스턴스에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-137">The total milliseconds is logged to the `MinimalEventCounterSource` singleton instance.</span></span> <span data-ttu-id="fe54a-138">이 필터를 적용하려면 필터 컬렉션에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-138">In order for this filter to be applied, you need to add it to the filters collection.</span></span> <span data-ttu-id="fe54a-139">*Startup.cs* 파일에서 이 필터에 포함된 `ConfigureServices` 메서드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-139">In the *Startup.cs* file, update the `ConfigureServices` method in include this filter.</span></span>

```csharp
public void ConfigureServices(IServiceCollection services) =>
    services.AddControllers(options => options.Filters.Add<LogRequestTimeFilterAttribute>())
            .AddNewtonsoftJson();
```

## <a name="monitor-event-counter"></a><span data-ttu-id="fe54a-140">이벤트 카운터 모니터링</span><span class="sxs-lookup"><span data-stu-id="fe54a-140">Monitor event counter</span></span>

<span data-ttu-id="fe54a-141"><xref:System.Diagnostics.Tracing.EventSource>에 대한 구현과 사용자 지정 작업 필터를 사용하여 애플리케이션을 빌드하고 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-141">With the implementation on an <xref:System.Diagnostics.Tracing.EventSource> and the custom action filter, build and launch the application.</span></span>
<span data-ttu-id="fe54a-142">메트릭을 <xref:System.Diagnostics.Tracing.EventCounter>에 기록했더라도 해당 통계에 액세스하지 않으면 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-142">You logged the metric to the <xref:System.Diagnostics.Tracing.EventCounter>, but unless you access the statistics from of it, it is not useful.</span></span> <span data-ttu-id="fe54a-143">통계를 얻으려면 이벤트를 원하는 만큼 자주 발생시키는 타이머와 이벤트를 캡처하는 수신기를 만들어 <xref:System.Diagnostics.Tracing.EventCounter>를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-143">To get the statistics, you need to enable the <xref:System.Diagnostics.Tracing.EventCounter> by creating a timer that fires as frequently as you want the events, as well as a listener to capture the events.</span></span> <span data-ttu-id="fe54a-144">이렇게 하려면 [dotnet-counters](dotnet-counters.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-144">To do that, you can use [dotnet-counters](dotnet-counters.md).</span></span>

<span data-ttu-id="fe54a-145">[dotnet-counters ps](dotnet-counters.md#dotnet-counters-ps) 명령을 사용하여 모니터링할 수 있는 .NET 프로세스의 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-145">Use the [dotnet-counters ps](dotnet-counters.md#dotnet-counters-ps) command to display a list of .NET processes that can be monitored.</span></span>

```console
dotnet-counters ps
```

<span data-ttu-id="fe54a-146">`dotnet-counters ps` 명령 출력의 프로세스 식별자를 사용하면 다음 `dotnet-counters monitor` 명령을 사용하여 이벤트 카운터 모니터링을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-146">Using the process identifier from the output of the `dotnet-counters ps` command, you can start monitoring the event counter with the following `dotnet-counters monitor` command:</span></span>

```console
dotnet-counters monitor --process-id 2196 --counters Sample.EventCounter.Minimal,Microsoft.AspNetCore.Hosting[total-requests,requests-per-second],System.Runtime[cpu-usage]
```

<span data-ttu-id="fe54a-147">`dotnet-counters monitor` 명령이 실행되는 동안 브라우저에서 <kbd>F5</kbd> 키를 눌러 `https://localhost:5001/api/values` 엔드포인트에 대한 연속 요청 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-147">While the `dotnet-counters monitor` command is running, hold <kbd>F5</kbd> on the browser to start issuing continuous requests to the `https://localhost:5001/api/values` endpoint.</span></span> <span data-ttu-id="fe54a-148">몇 초 후에 <kbd>q</kbd>를 눌러 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-148">After a few seconds stop by pressing <kbd>q</kbd></span></span>

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

<span data-ttu-id="fe54a-149">`dotnet-counters monitor` 명령은 활성 모니터링에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-149">The `dotnet-counters monitor` command is great for active monitoring.</span></span> <span data-ttu-id="fe54a-150">그러나 사후 처리 및 분석을 위해 이러한 진단 메트릭을 수집하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-150">However, you may want to collect these diagnostic metrics for post processing and analysis.</span></span> <span data-ttu-id="fe54a-151">이 경우 `dotnet-counters collect` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-151">For that, use the `dotnet-counters collect` command.</span></span> <span data-ttu-id="fe54a-152">`collect` 스위치 명령은 `monitor` 명령과 비슷하지만 몇 가지 추가 매개 변수를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-152">The `collect` switch command is similar to the `monitor` command, but accepts a few additional parameters.</span></span> <span data-ttu-id="fe54a-153">원하는 출력 파일 이름과 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-153">You can specify the desired output file name and format.</span></span> <span data-ttu-id="fe54a-154">*diagnostics.json* 이라는 JSON 파일의 경우 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-154">For a JSON file named *diagnostics.json* use the following command:</span></span>

```console
dotnet-counters collect --process-id 2196 --format json -o diagnostics.json --counters Sample.EventCounter.Minimal,Microsoft.AspNetCore.Hosting[total-requests,requests-per-second],System.Runtime[cpu-usage]
```

<span data-ttu-id="fe54a-155">이 명령이 실행되는 동안 브라우저에서 <kbd>F5</kbd> 키를 다시 눌러 `https://localhost:5001/api/values` 엔드포인트에 대한 연속 요청 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-155">Again, while the command is running, hold <kbd>F5</kbd> on the browser to start issuing continuous requests to the `https://localhost:5001/api/values` endpoint.</span></span> <span data-ttu-id="fe54a-156">몇 초 후에 <kbd>q</kbd>를 눌러 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-156">After a few seconds stop by pressing <kbd>q</kbd>.</span></span> <span data-ttu-id="fe54a-157">*diagnostics.json* 파일이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-157">The *diagnostics.json* file is written.</span></span> <span data-ttu-id="fe54a-158">그러나 기록된 JSON 파일은 들여쓰여지지 않습니다. 그렇지만 여기서는 가독성을 위해 들여쓴 상태로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe54a-158">The JSON file that is written is not indented, however; for readability it is indented here.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="fe54a-159">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fe54a-159">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fe54a-160">EventCounters</span><span class="sxs-lookup"><span data-stu-id="fe54a-160">EventCounters</span></span>](event-counters.md)
