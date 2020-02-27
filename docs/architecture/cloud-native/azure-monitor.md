---
title: Azure Monitor
description: Azure Monitor를 사용 하 여 시스템에 대 한 가시성을 확보 합니다.
ms.date: 02/05/2020
ms.openlocfilehash: 87ffca186346c3356c0277809d1d67145d1dd17b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628035"
---
# <a name="azure-monitor"></a>Azure Monitor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

다른 클라우드 공급자는 Azure에 있는 것과 같은 클라우드 응용 프로그램 모니터링 솔루션을 포함 하지 않습니다. Azure Monitor는 시스템 상태를 파악 하 고, 문제에 대 한 통찰력을 제공 하 고, 응용 프로그램을 최적화 하기 위해 설계 된 도구 컬렉션의 포괄적인 이름입니다.

클라우드 네이티브 응용 프로그램이 작동 하는 방식에 대 한 통찰력을 제공 하는 도구에 대 한 컬렉션인 Azure Monitor를 ![합니다. **그림 7-12**을](./media/azure-monitor.png)
합니다. 클라우드 네이티브 응용 프로그램이 작동 하는 방식에 대 한 정보를 제공 하는 도구에 대 한 컬렉션을 Azure Monitor 합니다.

## <a name="gathering-logs-and-metrics"></a>로그 및 메트릭 수집

모니터링 솔루션의 첫 번째 단계는 최대한 많은 데이터를 수집 하는 것입니다. 수집할 수 있는 데이터가 많을 수록 얻을 수 있는 정보를 심층적으로 파악할 수 있습니다. 시스템을 계측 하는 것은 일반적으로 어렵습니다. SNMP (Simple Network Management Protocol)는 컴퓨터 수준 정보를 수집 하기 위한 골드 표준 프로토콜 이지만 많은 지식과 구성이 필요 합니다. 다행히 가장 일반적인 메트릭이 Azure Monitor에 의해 자동으로 수집 되기 때문에 대부분의이 하드 작업은 제거 되었습니다.

응용 프로그램 수준 메트릭과 이벤트는 배포 중인 응용 프로그램에만 적용 되므로 자동으로 계측할 수 없습니다. 이러한 메트릭을 수집 하기 위해 고객이 등록 하거나 주문을 완료 하는 경우와 같이 이러한 정보를 직접 보고 하는 데 [사용할 수 있는 sdk 및 api](https://docs.microsoft.com/azure/azure-monitor/app/api-custom-events-metrics) 가 있습니다. 예외는 Application Insights를 통해 캡처 및 Azure Monitor 다시 보고 될 수도 있습니다. Sdk는 Go, Python, JavaScript 및 .NET 언어를 포함 하 여 클라우드 네이티브 응용 프로그램에서 발견 된 대부분의 언어를 지원 합니다.

응용 프로그램의 상태에 대 한 정보를 수집 하는 궁극적인 목표는 최종 사용자에 게 훌륭한 환경이 있는지 확인 하는 것입니다. 사용자에 게 [외부 웹 테스트를](https://docs.microsoft.com/azure/azure-monitor/app/monitor-web-app-availability)수행 하는 것 보다 문제가 발생 하는지 어떻게 알 수 있나요? 이러한 테스트는 전 세계의 위치에서 웹 사이트를 ping 하거나 에이전트가 사이트에 로그인 하 여 사용자 작업을 시뮬레이션 하는 것과 관련 된 것 처럼 간단할 수 있습니다.

## <a name="reporting-data"></a>보고 데이터

데이터를 수집한 후에는 데이터를 조작 하 고 요약 하 여 차트에 표시할 수 있습니다 .이를 통해 사용자는 문제가 발생 한 시기를 즉시 볼 수 있습니다. 이러한 차트를 대시보드 또는 통합 문서에 수집할 수 있습니다 .이 보고서는 시스템의 일부 측면에 대해 이야기를 제공 하도록 설계 되었습니다.

일부 인공 지능 또는 기계 학습 없이 최신 응용 프로그램을 완료할 수 없습니다. 이를 위해 데이터를 Azure의 다양 한 기계 학습 도구에 전달 하 여 다른 방법으로는 숨기는 추세와 정보를 추출할 수 [있습니다](https://www.youtube.com/watch?v=Cuza-I1g9tw) .

Application Insights는 레코드를 찾고 요약 하 고 차트를 그리는 데 사용할 수 있는 Kusto 라는 강력한 쿼리 언어를 제공 합니다. 예를 들어이 쿼리는 11 월 2007 월의 모든 레코드를 찾고, 상태별로 그룹화 하 고, 상위 10 개를 원형 차트로 플롯 합니다.

```kusto
StormEvents
| where StartTime >= datetime(2007-11-01) and StartTime < datetime(2007-12-01)
| summarize count() by State
| top 10 by count_
| render piechart
```

**그림 7-13**](./media/azure-monitor.png)
Application Insights 쿼리의 결과를 ![합니다. Application Insights 쿼리의 결과입니다.

[Kusto](https://dataexplorer.azure.com/clusters/help/databases/Samples) 쿼리를 시험해 볼 수 있습니다 .이는 한 시간 또는 두 번만 소요 될 수 있는 훌륭한 장소입니다. [예제 쿼리](https://docs.microsoft.com/azure/kusto/query/samples) 읽기가 유용할 수도 있습니다.

## <a name="dashboards"></a>대시보드

Azure Monitor에서 정보를 노출 하는 데 사용할 수 있는 여러 가지 대시보드 기술이 있습니다. 아마도 Application Insights에서 쿼리를 실행 하 고 [데이터를 차트에 그리는](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-app-dashboards)것이 가장 간단 합니다.

**그림 7-14**](./media/azure-monitor.png)
주 Azure 대시보드에 포함 된 Application Insights 차트의 예를 ![합니다. 기본 Azure 대시보드에 포함 된 Application Insights 차트의 예입니다.

그런 다음 이러한 차트를 대시보드 기능을 사용 하 여 적절 하 게 Azure Portal에 포함할 수 있습니다. 여러 계층으로 드릴 다운할 수 있는 것과 같이 이루기 요구 사항이 더 많은 사용자의 경우 [Power BI](https://powerbi.microsoft.com/)Azure Monitor 데이터를 사용할 수 있습니다. Power BI은 다양 한 데이터 원본의 데이터를 집계할 수 있는 업계 최고의 엔터프라이즈 클래스, 비즈니스 인텔리전스 도구입니다.

**그림 7-15**](./media/azure-monitor.png)
예제 Power BI 대시보드를 ![합니다. Power BI 대시보드의 예입니다.

## <a name="alerts"></a>경고

경우에 따라 데이터 대시보드가 충분 하지 않을 수 있습니다. 대시보드를 시청 하기 위해 아무도 해제 되지 않은 경우 문제가 해결 될 때까지 몇 시간이 걸릴 수 있습니다. 또는 검색 하기도 합니다. 이를 위해 Azure Monitor에는 상위 [경고 솔루션](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-overview)도 제공 됩니다. 경고는 다음과 같은 다양 한 조건에 의해 트리거될 수 있습니다.

- 메트릭 값
- 로그 검색 쿼리
- 활동 로그 이벤트
- 기본 Azure 플랫폼의 상태
- 웹 사이트 가용성 테스트

트리거될 때 경고는 다양 한 작업을 수행할 수 있습니다. 간단한 쪽에서 경고는 메일 그룹에 전자 메일 알림을 보내거나 개인에 게 문자 메시지를 보낼 수 있습니다. 추가 관련 경고는 특정 응용 프로그램에 대 한 호출에 대 한 사용자를 인식 하는 PagerDuty와 같은 도구에서 워크플로를 트리거할 수 있습니다. 경고는 워크플로에 대 한 무제한 가능성의 잠금 해제 [Microsoft Flow](https://flow.microsoft.com/) 작업을 트리거할 수 있습니다.

경고가 일반적인 원인으로 식별 되므로 경고를 해결 하기 위해 수행 해야 하는 단계의 일반적인 원인에 대 한 세부 정보를 사용 하 여 경고를 향상 시킬 수 있습니다. 고성능 클라우드 네이티브 응용 프로그램 배포는 크기 집합에서 실패 한 노드 제거 또는 자동 크기 조정 작업 트리거 등의 작업을 수행 하는 자동 복구 작업을 시작 하도록 선택할 수 있습니다. 결국 오전 2 시에 호출 직원의 절전 모드를 해제 하 여 라이브 사이트 문제를 해결 하는 데 더 이상 필요 하지 않을 수 있습니다. 시스템은 다음 날에 도착할 때까지 보완 하거나 최소 limp 수 있습니다.

Azure Monitor는 자동으로 기계 학습을 활용 하 여 배포 된 응용 프로그램의 일반 운영 매개 변수를 이해 합니다. 이렇게 하면 일반적인 매개 변수 외부에서 작동 하는 서비스를 검색할 수 있습니다. 예를 들어 사이트의 일반적인 평일 트래픽은 분당 1만 요청 일 수 있습니다. 그런 다음 지정 된 주에 갑자기 요청 수가 분당 매우 이례적인 2만 요청에 도달 합니다. [스마트 감지](https://docs.microsoft.com/azure/azure-monitor/app/proactive-diagnostics) 는 일반에서이 편차를 확인 하 고 경고를 트리거합니다. 동시에 추세 분석은 트래픽 부하가 예상 될 때 가양성 발생을 방지할 수 있을 만큼 지능적입니다.

## <a name="references"></a>참조

- [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview)
- [스마트 경고 관리-MS Ignite-비디오](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
>[이전](monitoring-azure-kubernetes.md)
>[다음](identity.md)
