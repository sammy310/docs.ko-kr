---
title: Azure Monitor
description: Azure 모니터를 사용하여 시스템에 대한 가시성을 확보합니다.
ms.date: 02/05/2020
ms.openlocfilehash: 4e5ddba6c1c13dc65662a7748d4ae3a58a6a6f68
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805623"
---
# <a name="azure-monitor"></a>Azure Monitor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

다른 클라우드 공급자는 Azure에서 볼 수 있는 클라우드 응용 프로그램 모니터링 솔루션만큼 성숙한 솔루션이 없습니다. Azure Monitor는 시스템 상태, 문제에 대한 통찰력 및 응용 프로그램의 최적화를 제공하도록 설계된 도구 컬렉션의 우산 이름입니다.

![Azure Monitor는 클라우드 네이티브 응용 프로그램의 작동 방식에 대한 통찰력을 제공하는 도구에 대한 컬렉션입니다. ](./media/azure-monitor.png)
 **그림 7-12**. Azure Monitor는 클라우드 네이티브 응용 프로그램의 작동 방식에 대한 통찰력을 제공하는 도구에 대한 컬렉션입니다.

## <a name="gathering-logs-and-metrics"></a>로그 및 메트릭 수집

모니터링 솔루션의 첫 번째 단계는 가능한 한 많은 데이터를 수집하는 것입니다. 수집할 수 있는 데이터가 많을수록 얻을 수 있는 인사이트가 더 깊어집니다. 계측 시스템은 전통적으로 어려웠습니다. 간단한 네트워크 관리 프로토콜(SNMP)은 기계 수준 정보를 수집하기 위한 표준 프로토콜이었지만 많은 지식과 구성이 필요했습니다. 다행히가장 일반적인 메트릭이 Azure Monitor에서 자동으로 수집되기 때문에 이러한 작업의 대부분이 제거되었습니다.

응용 프로그램 수준 메트릭 및 이벤트는 배포되는 응용 프로그램과 관련이 있으므로 자동으로 계측할 수 없습니다. 이러한 메트릭을 수집하기 위해 고객이 가입하거나 주문을 완료하는 경우와 같은 정보를 직접 보고할 [수 있는 SDK 및 API가 있습니다.](https://docs.microsoft.com/azure/azure-monitor/app/api-custom-events-metrics) 예외를 캡처하여 응용 프로그램 인사이트를 통해 Azure 모니터에 다시 보고할 수도 있습니다. SDK는 이동, 파이썬, 자바 스크립트 및 .NET 언어를 포함하여 클라우드 네이티브 응용 프로그램에서 찾을 수있는 대부분의 모든 언어를 지원합니다.

응용 프로그램의 상태에 대한 정보를 수집하는 궁극적인 목표는 최종 사용자가 좋은 경험을 할 수 있도록 하는 것입니다. 사용자가 [외부 웹 테스트를](https://docs.microsoft.com/azure/azure-monitor/app/monitor-web-app-availability)수행하는 것보다 문제가 발생하는지 알 수 있는 더 좋은 방법은 무엇입니까? 이러한 테스트는 전 세계 여러 위치에서 웹 사이트를 ping하는 것만큼 간단하거나 에이전트가 사이트에 로그인하여 사용자 작업을 시뮬레이션하도록 하는 것과 같이 간단할 수 있습니다.

## <a name="reporting-data"></a>데이터 보고

데이터가 수집되면 차트로 조작, 요약 및 플로팅할 수 있으므로 문제가 발생할 때 즉시 확인할 수 있습니다. 이러한 차트는 대시보드또는 통합 문서로 수집할 수 있으며, 시스템의 일부 측면에 대한 스토리를 전달할 수 있도록 설계된 다중 페이지 보고서입니다.

인공 지능이나 기계 학습이 없다면 최신 응용 프로그램은 완전하지 않을 것입니다. 이를 위해 데이터를 Azure의 다양한 기계 학습 도구로 [전달하여](https://www.youtube.com/watch?v=Cuza-I1g9tw) 숨길 수 있는 추세및 정보를 추출할 수 있습니다.

Application Insights는 Kusto라는 강력한 쿼리 언어를 제공하여 레코드를 찾고 요약하며 차트를 플롯하는 데 사용할 수 있습니다. 예를 들어 이 쿼리는 2007년 11월의 모든 레코드를 찾고 상태별로 그룹화한 다음 상위 10개 레코드를 원형 차트로 플롯합니다.

```kusto
StormEvents
| where StartTime >= datetime(2007-11-01) and StartTime < datetime(2007-12-01)
| summarize count() by State
| top 10 by count_
| render piechart
```

![응용 프로그램 인사이트](./media/azure-monitor.png)
쿼리**그림 7-13의**결과입니다. 응용 프로그램 인사이트 쿼리의 결과입니다.

[Kusto 쿼리를 실험할](https://dataexplorer.azure.com/clusters/help/databases/Samples) 수 있는 놀이터가 있는데, 이 곳은 한두 시간 동안 환상적인 장소입니다. [샘플 쿼리를](https://docs.microsoft.com/azure/kusto/query/samples) 읽는 것도 도움이 될 수 있습니다.

## <a name="dashboards"></a>대시보드

Azure Monitor의 정보를 표시하는 데 사용할 수 있는 여러 가지 대시보드 기술이 있습니다. 가장 간단한 방법은 Application Insights에서 쿼리를 실행하고 [데이터를 차트로 플롯하는 것입니다.](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-app-dashboards)

![기본 Azure 대시보드](./media/azure-monitor.png)
그림**7-14에**포함된 응용 프로그램 인사이트 차트의 예입니다. 기본 Azure 대시보드에 포함된 응용 프로그램 인사이트 차트의 예입니다.

그런 다음 이러한 차트는 대시보드 기능을 사용하여 적절한 Azure 포털에 포함될 수 있습니다. 여러 데이터 계층으로 드릴다운할 수 있는 등 보다 엄격한 요구 사항이 있는 사용자의 경우 [Power BI에서](https://powerbi.microsoft.com/)Azure Monitor 데이터를 사용할 수 있습니다. Power BI는 다양한 데이터 원본의 데이터를 집계할 수 있는 업계 최고의 엔터프라이즈급 비즈니스 인텔리전스 도구입니다.

![예를 들어 Power](./media/azure-monitor.png)
BI 대시보드**그림 7-15.** 파워 BI 대시보드의 예입니다.

## <a name="alerts"></a>경고

경우에 따라 데이터 대시보드가 충분하지 않은 경우가 있습니다. 아무도 대시보드를 보고 깨어 있는 경우 문제가 해결되거나 감지되기까지 몇 시간이 소요될 수 있습니다. 이를 위해 Azure Monitor는 최고 수준의 [경고 솔루션도](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-overview)제공합니다. 경고는 다음과 같은 광범위한 조건에 의해 트리거될 수 있습니다.

- 메트릭 값
- 로그 검색 쿼리
- 활동 로그 이벤트
- 기본 Azure 플랫폼의 상태
- 웹 사이트 가용성 테스트

트리거되면 경고는 다양한 작업을 수행할 수 있습니다. 간단한 측면에서, 경고는 메일링 리스트또는 개인에게 문자 메시지로 전자 메일 알림을 보낼 수 있습니다. 더 많은 관련 경고는 특정 응용 프로그램에 대한 호출 중인 사람을 알고 있는 PagerDuty와 같은 도구에서 워크플로를 트리거할 수 있습니다. 경고는 [Microsoft Flow에서](https://flow.microsoft.com/) 워크플로우에 대한 무한한 가능성에 가까운 잠금을 해제하는 작업을 트리거할 수 있습니다.

경고의 일반적인 원인을 식별하면 경고의 일반적인 원인과 이를 해결하기 위해 수행해야 하는 단계에 대한 세부 정보로 경고를 향상시킬 수 있습니다. 고도로 성숙한 클라우드 네이티브 응용 프로그램 배포는 규모 집합에서 실패한 노드를 제거하거나 자동 크기 조정 작업을 트리거하는 등의 작업을 수행하는 자체 복구 작업을 시작하도록 선택할 수 있습니다. 결국 시스템이 보상하거나 누군가가 다음 날 아침 에 출근 할 때까지 적어도 함께 절뚝 거리기 위해 자신을 조정할 수 있기 때문에 라이브 사이트 문제를 해결하기 위해 2AM에서 대기 직원을 깨울 필요가 없습니다.

Azure Monitor는 자동으로 기계 학습을 활용하여 배포된 응용 프로그램의 정상적인 운영 매개 변수를 이해합니다. 이를 통해 일반 매개 변수 외부에서 작동하는 서비스를 검색할 수 있습니다. 예를 들어 사이트의 일반적인 평일 트래픽은 분당 10,000개의 요청일 수 있습니다. 그런 다음 특정 주에 갑자기 요청 수가 분당 20,000건의 매우 이례적인 요청에 부딪히게 됩니다. [스마트 감지는](https://docs.microsoft.com/azure/azure-monitor/app/proactive-diagnostics) 표준에서 이러한 편차를 감지하고 경고를 트리거합니다. 동시에 추세 분석은 트래픽 로드가 예상될 때 거짓 긍정이 발사되지 않도록 충분히 똑똑합니다.

## <a name="references"></a>참조

- [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview)

>[!div class="step-by-step"]
>[이전](monitoring-azure-kubernetes.md)
>[다음](identity.md)
