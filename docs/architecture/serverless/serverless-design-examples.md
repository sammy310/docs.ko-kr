---
title: 서버리스 디자인 예제 - 서버리스 앱
description: 일정 예약 및 이벤트 기반 처리에서 파일 트리거 및 스트림 프로세스까지 서버리스 아키텍처에서 지원하는 다양한 시나리오를 이해합니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 3aa9b7951fd8f11a65a64c22443de7041aba7d94
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171756"
---
# <a name="serverless-design-examples"></a>서버리스 디자인 예제

서버리스용으로 다양한 디자인 패턴이 존재합니다. 이 섹션에서는 서버리스를 사용하는 몇 가지 일반적인 시나리오를 알아봅니다. 모든 예제에 공통적으로 포함되는 것은 이벤트 트리거와 비즈니스 논리의 기본적인 조합입니다.

## <a name="scheduling"></a>일정 계획

일정 예약은 일반적인 기능입니다. 다음 다이어그램에서는 적절한 무결성 검사가 없는 레거시 데이터베이스를 보여줍니다. 데이터베이스는 주기적으로 삭제되어야 합니다. 서버리스 함수는 잘못된 데이터를 찾아서 정리합니다. 트리거는 일정에 따라 코드를 실행하는 타이머입니다.

![서버리스 일정 예약](./media/serverless-scheduling.png)

## <a name="command-and-query-responsibility-segregation-cqrs"></a>CQRS(명령 및 쿼리 책임 분리)

CQRS(명령과 쿼리의 역할 분리)는 데이터와 데이터를 수정하는 작업을 읽거나 쿼리하기 위해 다른 인터페이스를 제공하는 패턴입니다. 이 패턴은 몇 가지 일반적인 문제를 해결합니다. 기존의 CRUD(만들기, 읽기, 업데이트, 삭제) 기반 시스템에서 동일한 데이터 저장소에 대한 읽기 및 쓰기의 양이 모두 많은 경우 충돌이 발생할 수 있습니다. 잠금이 자주 발생하고 읽기 속도가 크게 느려질 수 있습니다. 데이터가 여러 도메인 개체의 복합으로 표시되고 읽기 작업이 여러 엔터티의 데이터를 결합해야 하는 경우가 자주 있습니다.

CQRS를 사용하면 읽기는 데이터가 사용되는 방식으로 데이터를 모델링하는 특수한 "평면화된" 엔터티를 포함할 수 있습니다. 읽기는 데이터가 저장된 방식과 다르게 처리됩니다. 예를 들어 데이터베이스에서 하위 주소 레코드가 있는 헤더 레코드로 연락처를 저장할 수 있지만 읽기는 헤더 및 주소 속성이 모두 포함된 엔터티를 포함할 수 있습니다. 읽기 모델을 만드는 방법에는 여러 가지가 있습니다. 뷰에서 구체화할 수 있습니다. 업데이트 작업은 격리된 이벤트로 캡슐화될 수 있으며, 그런 다음 두 가지 모델에 대한 업데이트를 트리거합니다. 읽기 및 쓰기에 대해 별도의 모델이 있습니다.

![CQRS 예제](./media/cqrs-example.png)

서버리스는 분리된 엔드포인트를 제공하여 CQRS 패턴을 수용할 수 있습니다. 한 서버리스 함수는 쿼리 또는 읽기를 수용하고 다른 서버리스 함수 또는 함수 집합은 업데이트 작업을 처리합니다. 또한 서버리스 함수는 읽기 모델을 최신 상태로 유지하는 역할을 담당하고 데이터베이스의 [변경 피드](/azure/cosmos-db/change-feed)에 의해 트리거될 수 있습니다. 프런트 엔드 개발은 필요한 엔드포인트에 연결하는 것으로 간소화되었습니다. 이벤트 처리는 백 엔드에서 처리합니다. 또한 이 모델은 여러 팀이 서로 다른 작업을 수행할 수 있기 때문에 대규모 프로젝트에서 효율적으로 크기 조정됩니다.

## <a name="event-based-processing"></a>이벤트 기반 처리

메시지 기반 시스템에서 이벤트는 조치가 필요한 큐 또는 게시자/구독자 토픽으로 수집되는 경우가 많습니다. 이러한 이벤트는 서버리스 함수를 트리거하여 비즈니스 논리를 실행할 수 있습니다. 이벤트 기반 처리의 예로는 이벤트 소싱 시스템이 있습니다. 작업을 완료로 표시하기 위해 "이벤트"가 발생합니다. 이벤트에 의해 트리거된 서버리스 함수가 적절한 데이터베이스 문서를 업데이트합니다. 두 번째 서버리스 함수가 이벤트를 사용하여 시스템의 읽기 모델을 업데이트할 수 있습니다. [Azure Event Grid](/azure/event-grid/overview)는 이벤트를 구독자로서의 함수와 통합하는 방법을 제공합니다.

> 이벤트는 정보 메시지입니다. 자세한 내용은 [이벤트 소싱 패턴](/azure/architecture/patterns/event-sourcing)을 참조하세요.

## <a name="file-triggers-and-transformations"></a>파일 트리거 및 변환

ETL(추출, 변환 및 로드)은 일반적인 비즈니스 기능입니다. 서버리스는 코드를 파이프라인의 일부로 트리거할 수 있으므로 ETL을 위한 훌륭한 솔루션입니다. 개별 코드 구성 요소는 다양한 측면을 처리할 수 있습니다. 한 서버리스 함수는 파일을 다운로드하고, 다른 서버리스 함수는 변환을 적용하고, 또 다른 서버리스 함수는 데이터를 로드합니다. 코드를 독립적으로 테스트 및 배포하여 더 쉽게 유지 관리하고 필요에 따라 크기를 조정할 수 있습니다.

![서버리스 파일 트리거 및 변환](./media/serverless-file-triggers.png)

다이어그램에서 "쿨 스토리지"는 [Azure Stream Analytics](/azure/stream-analytics)에서 구문 분석되는 데이터를 제공합니다. 데이터 스트림에서 발생하는 모든 문제는 변칙을 해결하기 위해 Azure 함수를 트리거합니다.

## <a name="asynchronous-background-processing-and-messaging"></a>비동기 백그라운드 처리 및 메시징

비동기 메시징 및 백그라운드 처리를 사용하면 애플리케이션이 대기하지 않고 프로세스를 시작할 수 있습니다. 비동기 처리의 예로는 OCR 앱이 있습니다. 이미지가 제출되고 처리를 위해 큐에서 대기합니다. 이미지를 검색하여 텍스트를 추출하는 데 시간이 걸릴 수 있으며, 작업이 완료되면 알림이 전송됩니다. 서버리스는 이 시나리오에서 호출과 결과를 모두 처리할 수 있습니다.

## <a name="web-apps-and-apis"></a>웹앱 및 API

서버리스의 인기 있는 시나리오 하나는 N 계층 애플리케이션입니다. 가장 일반적인 것은 UI 레이어가 웹앱인 시나리오입니다. SPA(단일 페이지 애플리케이션)의 인기는 최근 급상승하고 있습니다. SPA 앱은 단일 페이지를 렌더링한 다음, API 호출과 반환된 데이터를 사용하여 전체 페이지를 다시 로드하지 않고 새 UI를 동적으로 렌더링합니다. 클라이언트 측 렌더링은 최종 사용자에게 속도 및 응답성이 훨씬 뛰어난 애플리케이션을 제공합니다.

HTTP 호출로 트리거된 서버리스 엔드포인트를 사용하여 API 요청을 처리할 수 있습니다. 예를 들어 광고 서비스 회사는 사용자 프로필 정보를 사용하여 서버리스 함수를 호출하여 사용자 지정 광고를 요청할 수 있습니다. 서버리스 함수가 사용자 지정 광고를 반환하고 웹 페이지가 광고를 렌더링합니다.

![서버리스 웹 API](./media/serverless-web-api.png)

## <a name="data-pipeline"></a>데이터 파이프라인

서버리스 함수를 사용하여 데이터 파이프라인을 쉽게 만들 수 있습니다. 이 예제에서 파일은 CSV 파일의 데이터를 테이블의 데이터 행으로 변환하는 함수를 트리거합니다. 구성된 테이블을 사용하면 Power BI 대시보드가 최종 사용자에게 분석을 제공할 수 있습니다.

![서버리스 데이터 파이프라인](./media/serverless-data-pipeline.png)

## <a name="stream-processing"></a>스트림 처리

장치 및 센서는 실시간으로 처리해야 하는 데이터 스트림을 생성하는 경우가 많습니다. [Event Hubs](/azure/event-hubs/event-hubs-what-is-event-hubs) 및 [IoT Hub](/azure/iot-hub)에서 [Service Bus](/azure/service-bus)까지 메시지와 스트림을 캡처할 수 있는 여러 기술이 있습니다. 전송 여부와 관계없이 서버리스는 데이터 및 데이터 스트림을 처리하는 데 적합한 메커니즘입니다. 서버리스는 대량 데이터 수요를 충족하기 위해 신속하게 확장할 수 있습니다. 서버리스 코드는 비즈니스 논리를 적용하여 데이터를 구문 분석하고 작업 및 분석을 위해 구조화된 형식으로 출력할 수 있습니다.

![서버리스 스트림 처리](./media/serverless-stream-processing.png)

## <a name="api-gateway"></a>API 게이트웨이

API 게이트웨이는 클라이언트에 대한 단일 진입점을 제공하고 지능적으로 요청을 백 엔드 서비스로 라우팅합니다. 대규모 서비스 집합을 관리하는 데 유용합니다. 또한 클라이언트를 서로 다른 환경에 간편하게 연결하여 버전 관리를 처리하고 개발을 간소화할 수 있습니다. 서버리스는 API 게이트웨이를 통해 단일 프런트 엔드를 제공하는 동시에 개별 마이크로 서비스의 백 엔드 크기 조정을 처리할 수 있습니다.

![서버리스 API 게이트웨이](./media/serverless-api-gateway.png)

## <a name="recommended-resources"></a>권장되는 리소스

- [Azure Event Grid](/azure/event-grid/overview)
- [Azure IoT Hub](/azure/iot-hub)
- [분산 데이터 관리의 문제 및 솔루션](../microservices/architect-microservice-container-applications/distributed-data-management.md)
- [마이크로 서비스 디자인: 마이크로 서비스 경계 식별](/azure/architecture/microservices/microservice-boundaries)
- [Event Hubs](/azure/event-hubs/event-hubs-what-is-event-hubs)
- [이벤트 소싱 패턴](/azure/architecture/patterns/event-sourcing)
- [회로 차단기 패턴 구현](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md)
- [IoT Hub](/azure/iot-hub)
- [Service Bus](/azure/service-bus)
- [Azure Cosmos DB에서 변경 피드 지원 사용](/azure/cosmos-db/change-feed)

>[!div class="step-by-step"]
>[이전](serverless-architecture-considerations.md)
>[다음](azure-serverless-platform.md)
