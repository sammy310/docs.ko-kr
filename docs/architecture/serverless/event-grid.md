---
title: Azure Event Grid - 서버리스 앱
description: Azure Event Grid는 안정적으로 이벤트를 전달하고 이벤트별 요금 모델을 통해 대규모로 라우팅할 수 있는 서버리스 솔루션입니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 408e1b9cd1b1e5316c7c6a17bb1b0c76a38f9e11
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135713"
---
# <a name="event-grid"></a>Event Grid

[Azure Event Grid](/azure/event-grid/overview)는 이벤트 기반 애플리케이션을 위한 서버리스 인프라를 제공합니다. 모든 원본에서 Event Grid에 게시하고 모든 플랫폼에서 메시지를 사용할 수 있습니다. 또한 Event Grid는 애플리케이션과의 통합을 간소화하기 위해 Azure 리소스의 이벤트를 기본적으로 지원합니다. 예를 들어 Blob 스토리지 이벤트를 구독하여 파일이 업로드될 때 앱에 알릴 수 있습니다. 그러면 애플리케이션은 다른 클라우드 또는 온-프레미스 애플리케이션에서 사용하는 사용자 지정 이벤트 그리드 메시지를 게시할 수 있습니다. Event Grid는 안정적으로 대규모 이벤트를 처리할 수 있도록 빌드되었습니다. 필요한 인프라를 설정하는 오버헤드 없이 메시지를 게시하고 구독할 수 있는 이점을 얻을 수 있습니다.

![Event Grid 로고](./media/event-grid-logo.png)

Event Grid의 주요 기능은 다음과 같습니다.

- 완전 관리형 이벤트 라우팅
- 거의 실시간으로 대규모 이벤트 전달
- Azure 내부 및 외부 모두에서 광범위한 적용 범위

## <a name="scenarios"></a>시나리오

Event Grid는 다양한 시나리오에 적용할 수 있습니다. 이 섹션에서는 가장 일반적인 세 가지 시나리오에 대해 설명합니다.

### <a name="ops-automation"></a>작업 자동화

![작업 자동화](./media/ops-automation.png)

Event Grid는 인프라를 프로비전할 때 [Azure Automation](https://docs.microsoft.com/azure/automation)에 알려 자동화를 가속화하고 정책 적용을 간소화하는 데 도움이 됩니다.

### <a name="application-integration"></a>애플리케이션 통합

![애플리케이션 통합](./media/app-integration.png)

Event Grid를 사용하여 앱을 다른 서비스에 연결할 수 있습니다. 표준 HTTP 프로토콜을 사용하면 레거시 앱도 쉽게 수정하여 Event Grid 메시지를 게시할 수 있습니다. 웹후크를 사용하면 다른 서비스 및 플랫폼에서 Event Grid 메시지를 사용할 수 있습니다.

### <a name="serverless-apps"></a>서버리스 앱

![서버리스 앱](./media/serverless-apps.png)

Event Grid는 Azure Functions, Logic Apps 또는 사용자 지정 코드를 트리거할 수 있습니다. Event Grid를 사용하는 주요 이점은 이벤트가 발생할 때 메시지를 보내기 위해 *푸시* 메커니즘을 사용한다는 것입니다. 푸시 아키텍처는 *폴링* 메커니즘보다 적은 리소스를 사용하고 더 효율적으로 크기 조정됩니다. 폴링은 정기적으로 업데이트를 확인해야 합니다.

## <a name="event-grid-vs-other-azure-messaging-services"></a>Event Grid 및 기타 Azure 메시징 서비스

Azure는 [Event Hubs](https://docs.microsoft.com/azure/event-hubs) 및 [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)를 비롯한 여러 메시징 서비스를 제공합니다. 각 서비스는 특정 사용 사례 집합을 해결하도록 디자인되었습니다. 다음 다이어그램에서는 서비스 간 차이점에 대한 개략적인 개요를 제공합니다.

![Azure 메시징 비교](./media/azure-messaging-services.png)

보다 자세한 비교는 [메시징 서비스 비교](https://docs.microsoft.com/azure/event-grid/compare-messaging-services)를 참조하세요.

## <a name="performance-targets"></a>성능 목표

Event Grid 사용하여 다음과 같은 성능 보장을 활용할 수 있습니다.

- 99번째 백분위 수에서 종단 간 대기 시간 1초 미만
- 99.99% 가용성입니다.
- 지역별 초당 이벤트 수 1,000만 개
- 지역별 구독 수 1억 개
- 게시자 대기 시간 50ms
- 1일 이내 전송 보장을 위해 지수 백오프를 사용하여 24시간 다시 시도
- 투명한 지역 장애 조치(failover)

## <a name="event-grid-schema"></a>Event Grid 스키마

Event Grid는 표준 스키마를 사용하여 사용자 지정 이벤트를 래핑합니다. 스키마는 사용자 지정 데이터 요소를 래핑하는 봉투(envelope)와 같습니다. 다음은 Event Grid 메시지의 예입니다.

```json
[{
    "id": "03e24f21-a955-43cc-8921-1f61a6081ce0",
    "eventType": "myCustomEvent",
    "subject": "foo/bar/12",
    "eventTime": "2018-09-22T10:36:01+00:00",
    "data": {
        "favoriteColor": "blue",
        "favoriteAnimal": "panther",
        "favoritePlanet": "Jupiter"
    },
    "dataVersion": "1.0"
}]
```

메시지에 대한 모든 것은 `data` 속성을 제외하고 표준입니다. 메시지를 검사하고 `eventType` 및 `dataVersion`을 사용하여 페이로드의 사용자 지정 부분을 역직렬화할 수 있습니다.

## <a name="azure-resources"></a>: Azure 리소스

Event Grid를 사용하는 주요 이점은 Azure에서 생성되는 자동 메시지입니다. Azure에서 리소스는 다양한 이벤트를 구독할 수 있게 해주는 *토픽*에 자동으로 게시됩니다. 다음 표에서는 자동으로 사용할 수 있는 리소스 유형, 메시지 유형 및 이벤트를 보여줍니다.

| Azure 리소스 | 이벤트 유형 | 설명 |
| -------------- | ---------- | ----------- |
| Azure 구독 | Microsoft.Resources.ResourceWriteSuccess | 리소스 생성 또는 업데이트 작업이 성공하면 발생합니다. |
| | Microsoft.Resources.ResourceWriteFailure | 리소스 생성 또는 업데이트 작업이 실패하면 발생합니다. |
| | Microsoft.Resources.ResourceWriteCancel | 리소스 생성 또는 업데이트 작업이 취소되면 발생합니다. |
|  | Microsoft.Resources.ResourceDeleteSuccess | 리소스 삭제 작업이 성공하면 발생합니다. |
|  | Microsoft.Resources.ResourceDeleteFailure | 리소스 삭제 작업이 실패하면 발생합니다. |
| | Microsoft.Resources.ResourceDeleteCancel | 리소스 삭제 작업이 취소되면 발생합니다. 이 이벤트는 템플릿 배포가 취소될 때 발생합니다. |
| Blob Storage | Microsoft.Storage.BlobCreated | Blob을 만들 때 발생합니다. |
| | Microsoft.Storage.BlobDeleted | Blob을 삭제할 때 발생합니다. |
| 이벤트 허브(영문) | Microsoft.EventHub.CaptureFileCreated | 캡처 파일을 만들 때 발생합니다.
| IoT Hub | Microsoft.Devices.DeviceCreated | IoT 허브에 디바이스를 등록하는 경우 게시합니다. |
| | Microsoft.Devices.DeviceDeleted | IoT 허브에서 디바이스를 삭제하는 경우 게시합니다. |
| 리소스 그룹 | Microsoft.Resources.ResourceWriteSuccess | 리소스 생성 또는 업데이트 작업이 성공하면 발생합니다. |
| | Microsoft.Resources.ResourceWriteFailure | 리소스 생성 또는 업데이트 작업이 실패하면 발생합니다. |
| | Microsoft.Resources.ResourceWriteCancel | 리소스 생성 또는 업데이트 작업이 취소되면 발생합니다. |
| | Microsoft.Resources.ResourceDeleteSuccess | 리소스 삭제 작업이 성공하면 발생합니다. |
| | Microsoft.Resources.ResourceDeleteFailure | 리소스 삭제 작업이 실패하면 발생합니다. |
| | Microsoft.Resources.ResourceDeleteCancel | 리소스 삭제 작업이 취소되면 발생합니다. 이 이벤트는 템플릿 배포가 취소될 때 발생합니다. |

자세한 내용은 [Azure Event Grid 이벤트 스키마](https://docs.microsoft.com/azure/event-grid/event-schema)를 참조하세요.

온-프레미스에서 실행되는 애플리케이션도 포함해 모든 종류의 애플리케이션에서 Event Grid에 액세스할 수 있습니다.

## <a name="conclusion"></a>결론

이 장에서는 Azure Functions, Logic Apps 및 Event Grid로 구성된 Azure 서버리스 플랫폼에 대해 알아보았습니다. 이러한 리소스를 사용하여 온전하게 서버리스 앱 아키텍처를 빌드하거나 다른 클라우드 리소스 및 온-프레미스 서버와 상호 작용하는 하이브리드 솔루션을 만들 수 있습니다. [Azure SQL](https://docs.microsoft.com/azure/sql-database) 또는 [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction) 같은 서버리스 데이터 플랫폼과 결합하여 완전 관리형 클라우드 네이티브 애플리케이션을 빌드할 수 있습니다.

## <a name="recommended-resources"></a>권장되는 리소스

- [App Service 계획](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
- [Application Insights](https://docs.microsoft.com/azure/application-insights)
- [Application Insights 분석](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
- [Azure: 서버리스 Azure Functions를 사용하여 앱을 클라우드로 전환](https://channel9.msdn.com/events/Connect/2017/E102)
- [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
- [Azure Event Grid 이벤트 스키마](https://docs.microsoft.com/azure/event-grid/event-schema)
- [Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs)
- [Azure Functions 설명서](https://docs.microsoft.com/azure/azure-functions) 리소스를 참조하세요.
- [Azure Functions 트리거 및 바인딩 개념](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
- [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)
- [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)
- [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
- [Azure 온-프레미스 데이터 게이트웨이를 사용하여 온-프레미스 데이터 원본에 연결](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
- [Azure Portal에서 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
- [Azure CLI를 사용하여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
- [Visual Studio를 사용하여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
- [Functions 지원 언어](https://docs.microsoft.com/azure/azure-functions/supported-languages)
- [Azure Functions 모니터링](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)

>[!div class="step-by-step"]
>[이전](logic-apps.md)
>[다음](durable-azure-functions.md)
