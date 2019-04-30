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
# <a name="telemetry-with-application-insights"></a>Application Insights로 원격 분석

[Application Insights](https://docs.microsoft.com/azure/application-insights) 는 개발자가 감지, 심사 및 웹 앱, 모바일 앱, 데스크톱 앱과 마이크로 서비스의 문제를 진단할 수 있도록 하는 서버 리스 진단 플랫폼입니다. 포털에서 스위치를 조작 하면 함수 앱에 대 한 Application Insights 켤 수 있습니다. Application Insights 서버를 구성 하거나 사용자 고유의 데이터베이스를 설정 하지 않고 이러한 기능을 모두 제공 합니다. Application Insights의 기능을 모두 자동으로 앱을 통합 하는 서비스로 제공 됩니다.

![Application Insights 로고](./media/application-insights-logo.png)

기존 앱에 Application Insights를 추가 하는 것은 응용 프로그램 설정에 계측 키를 추가 하는 것 만큼 쉽습니다. Application Insights를 사용 하 여 다음을 수행할 수 있습니다.

* 사용자 지정 차트를 만들고 함수 호출의 수와 같은 메트릭을 기반으로 경고, 함수 및 예외를 실행 하는 데 걸리는 시간
* 서버 예외 및 오류 분석
* 작업별 성능 드릴 하 여 타사 종속성을 호출 하는 데 걸리는 시간을 측정
* 함수 앱을 호스트 하는 모든 서버에서 CPU 사용량, 메모리 및 속도 모니터링 합니다.
* 메트릭 요청 수 및 함수 앱에 대 한 대기 시간을 포함 하 여 라이브 스트림을 보려면
* 사용 하 여 [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) 를 검색 하려면 쿼리 및 함수 데이터에 대해 사용자 지정 차트를 만들려면

![메트릭 탐색기](./media/metrics-explorer.png)

기본 제공 원격 분석 외에도 사용자 지정 원격 분석을 생성할 수 이기도 합니다. 다음 코드 조각은 함수 앱에 대해 설정 하는 계측 키를 사용 하는 사용자 지정 원격 분석 클라이언트를 만듭니다.

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

다음 코드에 새 행을 삽입 하는 데 걸리는 시간을 측정 한 [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) 인스턴스:

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

결과 성능 그래프가 표시 됩니다.

![사용자 지정 원격 분석](./media/custom-telemetry.png)

사용자 지정 원격 분석은 32.6 밀리초 새 행을 삽입 하는 평균 시간이 표시 됩니다.

Application Insights에는 서버 리스 응용 프로그램에 대 한 자세한 원격 분석 로그는 강력 하 고 편리한 방법을 제공 합니다. 추적 수준에 대 한 모든 권한을 있고 로그 제공 됩니다. 이벤트, 종속성 및 페이지 보기와 같은 사용자 지정 통계를 추적할 수 있습니다. 마지막으로, 강력한 분석을 사용 하면 중요 한 질문 하 고 차트 및 고급 정보를 생성 하는 쿼리를 작성할 수 있습니다.

자세한 내용은 [Azure Functions 모니터링](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)합니다.

>[!div class="step-by-step"]
>[이전](azure-functions.md)
>[다음](logic-apps.md)