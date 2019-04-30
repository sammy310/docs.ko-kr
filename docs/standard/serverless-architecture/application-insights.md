---
title: Application Insights-서버 리스 앱
description: Application Insights는 개발자가 감지, 심사 및 웹 앱, 모바일 앱, 데스크톱 앱과 마이크로 서비스의 문제를 진단할 수 있도록 하는 서버 리스 진단 플랫폼입니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: b4884d483de07c1c2077f7280b6b77c6059572c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051234"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="fb864-103">Application Insights로 원격 분석</span><span class="sxs-lookup"><span data-stu-id="fb864-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="fb864-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) 는 개발자가 감지, 심사 및 웹 앱, 모바일 앱, 데스크톱 앱과 마이크로 서비스의 문제를 진단할 수 있도록 하는 서버 리스 진단 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="fb864-105">포털에서 스위치를 조작 하면 함수 앱에 대 한 Application Insights 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="fb864-106">Application Insights 서버를 구성 하거나 사용자 고유의 데이터베이스를 설정 하지 않고 이러한 기능을 모두 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="fb864-107">Application Insights의 기능을 모두 자동으로 앱을 통합 하는 서비스로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Application Insights 로고](./media/application-insights-logo.png)

<span data-ttu-id="fb864-109">기존 앱에 Application Insights를 추가 하는 것은 응용 프로그램 설정에 계측 키를 추가 하는 것 만큼 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="fb864-110">Application Insights를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-110">With Application Insights you can:</span></span>

* <span data-ttu-id="fb864-111">사용자 지정 차트를 만들고 함수 호출의 수와 같은 메트릭을 기반으로 경고, 함수 및 예외를 실행 하는 데 걸리는 시간</span><span class="sxs-lookup"><span data-stu-id="fb864-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
* <span data-ttu-id="fb864-112">서버 예외 및 오류 분석</span><span class="sxs-lookup"><span data-stu-id="fb864-112">Analyze failures and server exceptions</span></span>
* <span data-ttu-id="fb864-113">작업별 성능 드릴 하 여 타사 종속성을 호출 하는 데 걸리는 시간을 측정</span><span class="sxs-lookup"><span data-stu-id="fb864-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
* <span data-ttu-id="fb864-114">함수 앱을 호스트 하는 모든 서버에서 CPU 사용량, 메모리 및 속도 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
* <span data-ttu-id="fb864-115">메트릭 요청 수 및 함수 앱에 대 한 대기 시간을 포함 하 여 라이브 스트림을 보려면</span><span class="sxs-lookup"><span data-stu-id="fb864-115">View a live stream of metrics including request count and latency for your function apps</span></span>
* <span data-ttu-id="fb864-116">사용 하 여 [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) 를 검색 하려면 쿼리 및 함수 데이터에 대해 사용자 지정 차트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="fb864-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![메트릭 탐색기](./media/metrics-explorer.png)

<span data-ttu-id="fb864-118">기본 제공 원격 분석 외에도 사용자 지정 원격 분석을 생성할 수 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="fb864-119">다음 코드 조각은 함수 앱에 대해 설정 하는 계측 키를 사용 하는 사용자 지정 원격 분석 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="fb864-120">다음 코드에 새 행을 삽입 하는 데 걸리는 시간을 측정 한 [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) 인스턴스:</span><span class="sxs-lookup"><span data-stu-id="fb864-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="fb864-121">결과 성능 그래프가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-121">The resulting performance graph is shown:</span></span>

![사용자 지정 원격 분석](./media/custom-telemetry.png)

<span data-ttu-id="fb864-123">사용자 지정 원격 분석은 32.6 밀리초 새 행을 삽입 하는 평균 시간이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="fb864-124">Application Insights에는 서버 리스 응용 프로그램에 대 한 자세한 원격 분석 로그는 강력 하 고 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="fb864-125">추적 수준에 대 한 모든 권한을 있고 로그 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="fb864-126">이벤트, 종속성 및 페이지 보기와 같은 사용자 지정 통계를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="fb864-127">마지막으로, 강력한 분석을 사용 하면 중요 한 질문 하 고 차트 및 고급 정보를 생성 하는 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="fb864-128">자세한 내용은 [Azure Functions 모니터링](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb864-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fb864-129">[이전](azure-functions.md)
>[다음](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="fb864-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>