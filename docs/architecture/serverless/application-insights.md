---
title: Application Insights 서버 리스 앱
description: Application Insights는 개발자가 웹 앱, 모바일 앱, 데스크톱 앱 및 마이크로 서비스의 문제를 감지, 심사 및 진단할 수 있도록 하는 서버 리스 진단 플랫폼입니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7c1013ac029645a2da44aaf1c3b6ba74ca3f3dde
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522740"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="cc2d8-103">Application Insights 원격 분석</span><span class="sxs-lookup"><span data-stu-id="cc2d8-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="cc2d8-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) 는 개발자가 웹 앱, 모바일 앱, 데스크톱 앱 및 마이크로 서비스의 문제를 감지, 심사 및 진단할 수 있도록 하는 서버 리스 진단 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="cc2d8-105">포털에서 스위치를 대칭 이동 하 여 함수 앱에 대 한 Application Insights를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="cc2d8-106">Application Insights는 서버를 구성 하거나 사용자 고유의 데이터베이스를 설정 하지 않고도 이러한 모든 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="cc2d8-107">모든 Application Insights 기능을 앱과 자동으로 통합 하는 서비스로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Application Insights 로고](./media/application-insights-logo.png)

<span data-ttu-id="cc2d8-109">기존 앱에 Application Insights을 추가 하는 것은 응용 프로그램의 설정에 계측 키를 추가 하는 것 만큼 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="cc2d8-110">Application Insights를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-110">With Application Insights you can:</span></span>

- <span data-ttu-id="cc2d8-111">함수 호출 수, 함수를 실행 하는 데 걸리는 시간, 예외 등의 메트릭에 따라 사용자 지정 차트 및 경고 만들기</span><span class="sxs-lookup"><span data-stu-id="cc2d8-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
- <span data-ttu-id="cc2d8-112">오류 및 서버 예외 분석</span><span class="sxs-lookup"><span data-stu-id="cc2d8-112">Analyze failures and server exceptions</span></span>
- <span data-ttu-id="cc2d8-113">작업 별로 성능을 자세히 살펴보고 타사 종속성을 호출 하는 데 걸리는 시간을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
- <span data-ttu-id="cc2d8-114">함수 앱을 호스트 하는 모든 서버에서 CPU 사용량, 메모리 및 비율 모니터링</span><span class="sxs-lookup"><span data-stu-id="cc2d8-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
- <span data-ttu-id="cc2d8-115">함수 앱에 대 한 요청 수 및 대기 시간을 포함 하 여 메트릭의 라이브 스트림 보기</span><span class="sxs-lookup"><span data-stu-id="cc2d8-115">View a live stream of metrics including request count and latency for your function apps</span></span>
- <span data-ttu-id="cc2d8-116">[분석](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) 을 사용 하 여 함수 데이터에서 사용자 지정 차트 검색, 쿼리 및 만들기</span><span class="sxs-lookup"><span data-stu-id="cc2d8-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![메트릭 탐색기](./media/metrics-explorer.png)

<span data-ttu-id="cc2d8-118">기본 제공 원격 분석 외에도 사용자 지정 원격 분석을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="cc2d8-119">다음 코드 조각은 함수 앱에 설정 된 계측 키를 사용 하 여 사용자 지정 원격 분석 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="cc2d8-120">다음 코드는 [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) 인스턴스에 새 행을 삽입 하는 데 걸리는 시간을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="cc2d8-121">결과 성능 그래프가 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-121">The resulting performance graph is shown:</span></span>

![사용자 지정 원격 분석](./media/custom-telemetry.png)

<span data-ttu-id="cc2d8-123">사용자 지정 원격 분석은 새 행을 삽입 하는 평균 시간을 32.6 밀리초로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="cc2d8-124">Application Insights는 서버 리스 응용 프로그램에 대 한 자세한 원격 분석을 강력 하 고 편리한 방법으로 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="cc2d8-125">제공 된 추적 및 로깅 수준에 대 한 모든 권한을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="cc2d8-126">이벤트, 종속성 및 페이지 보기와 같은 사용자 지정 통계를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="cc2d8-127">마지막으로, 강력한 분석을 통해 중요 한 질문을 하 고 차트 및 고급 정보를 생성 하는 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="cc2d8-128">자세한 내용은 [Azure Functions 모니터링](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc2d8-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cc2d8-129">[이전](azure-functions.md)
>[다음](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="cc2d8-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>
