---
title: Application Insights - 서버리스 앱
description: Application Insights는 개발자가 웹앱, 모바일 앱, 데스크톱 앱 및 마이크로 서비스의 문제를 감지, 심사 및 진단할 수 있게 해주는 서버리스 진단 플랫폼입니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7c1013ac029645a2da44aaf1c3b6ba74ca3f3dde
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522740"
---
# <a name="telemetry-with-application-insights"></a>Application Insights를 사용하여 원격 분석

[Application Insights](https://docs.microsoft.com/azure/application-insights)는 개발자가 웹앱, 모바일 앱, 데스크톱 앱 및 마이크로 서비스의 문제를 감지, 심사 및 진단할 수 있게 해주는 서버리스 진단 플랫폼입니다. 포털에서 스위치를 대칭 이동하여 함수 앱에 Application Insights를 켤 수 있습니다. Application Insights는 사용자가 서버를 구성하거나 자체 데이터베이스를 설정하지 않아도 이러한 기능을 모두 제공합니다. 모든 Application Insights 기능은 앱과 자동 통합되는 서비스로 제공됩니다.

![Application Insights 로고](./media/application-insights-logo.png)

기존 앱에 Application Insights를 추가하는 것은 애플리케이션의 설정에 계측 키를 추가하는 정도로 간단합니다. Application Insights로 다음을 수행할 수 있습니다.

- 함수 호출 횟수, 함수를 실행하는 데 걸리는 시간, 예외 등의 메트릭에 따라 사용자 지정 차트 및 경고 만들기
- 실패 및 서버 예외 분석
- 작업별 성능을 분석하고 타사 종속성을 호출하는 데 걸리는 시간을 측정
- 함수 앱을 호스트하는 모든 서버에서 CPU 사용량, 메모리 및 속도를 모니터링
- 함수 앱에 대한 요청 횟수 및 대기 시간을 포함하 여 메트릭의 라이브 스트림 보기
- [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)를 사용하여 함수 데이터 검색, 쿼리 및 사용자 지정 차트 만들기

![메트릭 탐색기](./media/metrics-explorer.png)

기본 제공 원격 분석 외에도 사용자 지정 원격 분석을 생성할 수 있습니다. 다음 코드 조각은 함수 앱에 설정된 계측 키를 사용하여 사용자 지정 원격 분석 클라이언트를 만듭니다.

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

다음 코드는 [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) 인스턴스에 새 행을 삽입하는 데 걸리는 시간을 측정합니다.

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

결과 성능 그래프가 다음과 같이 표시됩니다.

![사용자 지정 원격 분석](./media/custom-telemetry.png)

사용자 지정 원격 분석에서 새 행을 삽입하는 평균 시간이 32.6밀리초로 나타납니다.

Application Insights는 서버리스 애플리케이션에 대한 자세한 원격 분석을 기록하는 강력하고 편리한 방법을 제공합니다. 사용자는 제공된 추적 및 로깅 수준에 대한 모든 권한을 가집니다. 또한 이벤트, 종속성 및 페이지 보기와 같은 사용자 지정 통계를 추적할 수 있습니다. 마지막으로, 강력한 분석을 통해 중요한 질문을 하고 차트 및 고급 정보를 생성하는 쿼리를 작성할 수 있습니다.

자세한 내용은 [Azure Functions 모니터링](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)을 참조하세요.

>[!div class="step-by-step"]
>[이전](azure-functions.md)
>[다음](logic-apps.md)
