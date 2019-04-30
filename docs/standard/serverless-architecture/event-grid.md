---
title: Azure Event Grid-서버 리스 앱
description: Azure Event Grid는 안정적인 이벤트 배달 및 이벤트별 지불 모델을 대규모로 라우팅에 대 한 서버 리스 솔루션입니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4970130ede0c96c645129ee6c8c7d54cb1114042
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959386"
---
# <a name="event-grid"></a>Event Grid

[Azure Event Grid](/azure/event-grid/overview) 이벤트 기반 응용 프로그램에 대 한 서버 리스 인프라를 제공 합니다. 모든 원본에서 Event Grid에 게시 하 고 모든 플랫폼에서 메시지를 사용할 수 있습니다. 또한 event Grid는 응용 프로그램 통합을 간소화 하는 Azure 리소스에서 이벤트에 대 한 기본 제공 지원 합니다. 예를 들어 파일이 업로드 되는 경우 앱에 알리기 위해 blob 저장소 이벤트를 구독할 수 있습니다. 응용 프로그램 수 되는 다른 클라우드 또는 온-프레미스 응용 프로그램을 사용자 지정 이벤트 그리드 메시지를 게시 합니다. Event Grid는 안정적으로 대규모를 처리 하도록 구축 되었습니다. 게시 및 구독 하는 데 필요한 인프라를 설정 하는 오버 헤드 없이 메시지는 이점을 얻을 수 있습니다.

![Event Grid 로고](./media/event-grid-logo.png)

Event grid의 주요 기능은 다음과 같습니다.

* 완전히 관리 되는 이벤트 라우팅입니다.
* 거의 대규모로 실시간 이벤트 배달 합니다.
* 내부와 Azure 외부의 광범위 한 검사 합니다.

## <a name="scenarios"></a>시나리오

Event Grid는 여러 가지 시나리오를 해결합니다. 이 섹션에서는 가장 일반적인 세 가지 다룹니다.

### <a name="ops-automation"></a>작업 자동화

![작업 자동화](./media/ops-automation.png)

Event Grid 속도 자동화 하는 데 도움이 및 알림으로써 정책 적용을 간소화할 수 있습니다 [Azure Automation](https://docs.microsoft.com/azure/automation) 인프라 프로 비전 된 경우.

### <a name="application-integration"></a>응용 프로그램 통합

![응용 프로그램 통합](./media/app-integration.png)

다른 서비스에 앱을 연결할 Event Grid를 사용할 수 있습니다. 표준 HTTP 프로토콜 사용도 레거시 앱 쉽게 수정할 수 있습니다 Event Grid 메시지를 게시 합니다. 웹 후크 다른 서비스 및 Event Grid 메시지를 사용 하는 플랫폼에 사용할 수 있습니다.

### <a name="serverless-apps"></a>서버 리스 앱

![서버 리스 앱](./media/serverless-apps.png)

Event Grid는 Azure Functions, Logic Apps 또는 고유한 사용자 지정 코드 트리거할 수 있습니다. Event Grid를 사용 하는 데 필요한 주요 이점은 사용 한다는 것입니다를 *푸시* 이벤트가 발생할 때 메시지를 전송 하는 메커니즘입니다. 푸시 아키텍처 더 적은 리소스를 소비 하는 것 보다 좋아집니다 *폴링* 메커니즘입니다. 폴링 일정 한 간격으로 업데이트 확인 해야 합니다.

## <a name="event-grid-vs-other-azure-messaging-services"></a>다른 Azure 메시징 서비스 및 이벤트 표

Azure를 비롯 한 여러 메시징 서비스를 제공 [Event Hubs](https://docs.microsoft.com/azure/event-hubs) 하 고 [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)합니다. 각 사용 사례는 특정 집합을 해결 하기 위해 설계 되었습니다. 다음 다이어그램은 서비스 간의 차이점에 대 한 개략적인 개요를 제공합니다.

![Azure 메시징 비교](./media/azure-messaging-services.png)

자세한 비교를 참조 하세요 [메시징 서비스 비교](https://docs.microsoft.com/azure/event-grid/compare-messaging-services)합니다.

## <a name="performance-targets"></a>성능 목표

다음 성능을 이용할 수 있습니다 하는 Event Grid를 사용 하 여 보장 합니다.

* 백분위 99의 종단 간 대기 시간을 1 초 미만의 합니다.
* 99.99% 가용성입니다.
* 지역 마다 초당 10 백만 이벤트입니다.
* 지역당 100 백만 구독입니다.
* 대기 시간이 50ms 일 게시자입니다.
* 지 수 백오프 1 일 창의 보장 된 배달을 위해을 사용 하 여 24 시간에 다시 시도 하세요.
* 투명 한 지역 장애 조치 합니다.

## <a name="event-grid-schema"></a>Event Grid 스키마

Event Grid 사용자 지정 이벤트를 래핑하는 표준 스키마를 사용 합니다. 스키마는 봉투 (envelope)에 사용자 지정 데이터 요소를 래핑하는 같습니다. Event Grid 메시지의 예는 다음과 같습니다.

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

메시지에 대 한 모든 항목은 제외 하 고 표준는 `data` 속성입니다. 메시지를 검사 하 고 사용할 수 있습니다 합니다 `eventType` 및 `dataVersion` 취소 페이로드 사용자 지정 부분을 직렬화 하 합니다.

## <a name="azure-resources"></a>: Azure 리소스

Event Grid를 사용 하는 데 필요한 주요 이점은 Azure에서 생성 된 자동 메시지 수입니다. Azure에서 리소스 자동으로 게시 하는 *항목* 다양 한 이벤트를 구독할 수 있도록 합니다. 다음 표에서 리소스 유형, 메시지 유형 및 자동으로 사용할 수 있는 이벤트를 나열 합니다.

| Azure 리소스 | 이벤트 유형 | 설명 |
| -------------- | ---------- | ----------- |
| Azure 구독 | Microsoft.Resources.ResourceWriteSuccess | 발생 경우 리소스 만들기 또는 업데이트 작업이 성공 합니다. |
| | Microsoft.Resources.ResourceWriteFailure | 리소스 만들기 또는 업데이트 작업이 실패할 때 발생 합니다. |
| | Microsoft.Resources.ResourceWriteCancel | 발생 리소스 만들기 또는 업데이트 작업이 면 취소 됩니다. |
|  | Microsoft.Resources.ResourceDeleteSuccess | 리소스 삭제 작업이 성공할 때 발생 합니다. |
|  | Microsoft.Resources.ResourceDeleteFailure | 리소스 삭제 작업이 실패할 때 발생 합니다. |
| | Microsoft.Resources.ResourceDeleteCancel | 리소스 삭제 작업이 취소 될 때 발생 합니다. 이 이벤트에는 템플릿 배포가 취소 될 때 발생 합니다. |
| Blob Storage | Microsoft.Storage.BlobCreated | Blob을 만들 때 발생 합니다. |
| | Microsoft.Storage.BlobDeleted | Blob을 삭제할 때 발생 합니다. |
| Event hubs | Microsoft.EventHub.CaptureFileCreated | 캡처 파일을 만들 때 발생 합니다.
| IoT Hub | Microsoft.Devices.DeviceCreated | IoT hub에 장치를 등록할 때 게시 합니다. |
| | Microsoft.Devices.DeviceDeleted | IoT hub에서 장치를 삭제 하는 경우 게시 합니다. |
| 리소스 그룹 | Microsoft.Resources.ResourceWriteSuccess | 발생 경우 리소스 만들기 또는 업데이트 작업이 성공 합니다. |
| | Microsoft.Resources.ResourceWriteFailure | 리소스 만들기 또는 업데이트 작업이 실패할 때 발생 합니다. |
| | Microsoft.Resources.ResourceWriteCancel | 발생 리소스 만들기 또는 업데이트 작업이 면 취소 됩니다. |
| | Microsoft.Resources.ResourceDeleteSuccess | 리소스 삭제 작업이 성공할 때 발생 합니다. |
| | Microsoft.Resources.ResourceDeleteFailure | 리소스 삭제 작업이 실패할 때 발생 합니다. |
| | Microsoft.Resources.ResourceDeleteCancel | 리소스 삭제 작업이 취소 될 때 발생 합니다. 이 이벤트에는 템플릿 배포가 취소 될 때 발생 합니다. |

자세한 내용은 [Azure Event Grid 이벤트 스키마](https://docs.microsoft.com/azure/event-grid/event-schema)합니다.

Event Grid의 하나라도 온-프레미스를 실행 하는 응용 프로그램에서에서 액세스할 수 있습니다.

## <a name="conclusion"></a>결론

이 장에서 Azure Functions, Logic Apps 및 Event Grid의 구성 된 Azure 서버 리스 플랫폼에 대해 알아보았습니다. 이러한 리소스를 사용 하 여 완전히 서버 리스 앱 아키텍처를 빌드할 수도 있고 온-프레미스 서버 및 다른 클라우드 리소스와 상호 작용 하는 하이브리드 솔루션을 만들 수 있습니다. 같은 서버 리스 데이터 플랫폼을 통해 결합 [Azure SQL](https://docs.microsoft.com/azure/sql-database) 또는 [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), 완전히 관리 되는 클라우드 네이티브 응용 프로그램을 빌드할 수 있습니다.

## <a name="recommended-resources"></a>권장 되는 리소스

* [App service 계획](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
* [Application Insights](https://docs.microsoft.com/azure/application-insights)
* [Application Insights 분석](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
* [Azure: 서버 리스 Azure Functions를 사용 하 여 클라우드로 앱 가져오기](https://channel9.msdn.com/events/Connect/2017/E102)
* [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
* [Azure Event Grid 이벤트 스키마](https://docs.microsoft.com/azure/event-grid/event-schema)
* [Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs)
* [Azure Functions 설명서](https://docs.microsoft.com/azure/azure-functions)
* [Azure Functions 트리거 및 바인딩 개념](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
* [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)
* [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)
* [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
* [1.x와 2.x 비교 함수](https://docs.microsoft.com/azure/azure-functions/functions-versions)
* [Azure 온-프레미스 데이터 게이트웨이 사용 하 여 온-프레미스 데이터 원본에 연결](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
* [Azure portal에서 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
* [Azure CLI를 사용 하 여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
* [Visual Studio를 사용 하 여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
* [지원 되는 언어 기능](https://docs.microsoft.com/azure/azure-functions/supported-languages)
* [Azure Functions 모니터링](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
* [Azure Functions 프록시 사용](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
>[이전](logic-apps.md)
>[다음](durable-azure-functions.md)
