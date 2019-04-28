---
title: 서버 리스 디자인 예-서버 리스 앱
description: 다양 한 일정 및 이벤트 기반 처리 파일 트리거를 스트림 프로세스에서 서버 리스 아키텍처를 지 원하는 시나리오를 이해 합니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: d165746ff2f03b0edc59a9284052323a0c1fd05b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784441"
---
# <a name="serverless-design-examples"></a>서버리스 디자인 예제

에 대 한 많은 디자인 패턴은 서버 리스 합니다. 이 섹션에서는 서버 리스를 사용 하는 몇 가지 일반적인 시나리오를 캡처합니다. 새로운 모든 예제에서는 서로 공통 되는 이벤트 트리거 및 비즈니스 논리의 기본 조합입니다.

## <a name="scheduling"></a>일정 예약

작업을 예약 하는 것은 일반적인 함수입니다. 다음 다이어그램에는 적절 한 무결성 검사 되지 않은 레거시 데이터베이스를 보여 줍니다. 데이터베이스를 주기적으로 삭제 해야 합니다. 서버 리스 함수 잘못 된 데이터를 찾아서이 정리 합니다. 트리거 타이머 일정에 따라 코드를 실행 하는 경우

![서버 리스 예약](./media/serverless-scheduling.png)

## <a name="command-and-query-responsibility-segregation-cqrs"></a>명령 및 쿼리 책임 분리 (CQRS)

명령 및 쿼리 역할 구분 (CQRS) 데이터 읽기 (또는 쿼리)에 대 한 다른 인터페이스 및 데이터를 수정 하는 작업을 제공 하는 패턴입니다. 몇 가지 일반적인 문제를 해결 하는 것입니다. 기존 만들기 읽기 업데이트 삭제 (CRUD) 기반 시스템에서는 동일한 데이터 저장소에 많은 양의 읽기 및 쓰기 모두에서 충돌이 발생할 수 있습니다. 잠금 자주 발생 하 고 읽기 크게 느려질 수 있습니다. 종종 여러 도메인 개체 및 읽기 작업의 복합 다른 엔터티에서 데이터를 결합 해야 하는 대로 데이터가 표시 됩니다.

CQRS를 사용 하 여 읽기 사용 되는 방식으로 데이터를 모델링 하는 특별 한 "일반된" 엔터티를 포함할 수 있습니다. 읽기 보다 저장 되는 방법을 다르게 처리 됩니다. 예를 들어, 데이터베이스는 헤더 레코드는 자식 주소 레코드를 사용 하 여 연락처를 저장할 수 있습니다, 있지만 읽기 헤더와 주소 속성을 사용 하 여 엔터티에 포함 될 수 있습니다. 읽기 모델을 만드는 다양 한 가지가 있습니다. 뷰에서 구체화할 수 있습니다. 업데이트 작업은 다음 두 가지 모델에 대 한 업데이트를 트리거하는 격리 된 이벤트로 캡슐화 할 수 있었습니다. 별도 모델 읽기 및 쓰기에 존재 합니다.

![CQRS 예제](./media/cqrs-example.png)

서버는 분리 된 끝점을 제공 하 여 CQRS 패턴을 수용할 수 있습니다. 하나의 서버 리스 함수 수용 쿼리 또는 읽기 및 업데이트 작업을 다른 서버 리스 함수 또는 함수 집합을 처리 합니다. 서버 리스 함수 읽기 모델을 최신 상태로 유지 하는 일을 담당 수도 및 데이터베이스에 의해 트리거될 수 있습니다 [변경 피드](https://docs.microsoft.com/azure/cosmos-db/change-feed)합니다. 필요한 끝점에 연결 하는 프런트 엔드 개발 간소화 됩니다. 이벤트 처리는 백 엔드에서 처리 됩니다. 다양 한 작업에 다른 팀 작업 수 있으므로 대규모 프로젝트에이 모델도 확장 됩니다.

## <a name="event-based-processing"></a>이벤트 기반 처리

메시지 기반 시스템에서 이벤트 종종 큐 또는 항목에 따라 처리 게시자/구독자에서 수집 됩니다. 이러한 이벤트는 비즈니스 논리의 일부를 실행 하는 서버 리스 함수를 트리거할 수 있습니다. 이벤트 기반 처리의 예로 이벤트 기반 시스템입니다. "이벤트" 발생 한 작업을 완료로 표시 합니다. 이벤트에 의해 트리거되는 서버 리스 함수는 적절 한 데이터베이스 문서를 업데이트 합니다. 두 번째 서버 리스 함수는 시스템에 대 한 읽기 모델을 업데이트 하는 이벤트를 사용할 수 있습니다. [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview) 구독자로 함수를 사용 하 여 이벤트를 통합 하는 방법을 제공 합니다.

> 이벤트는 정보 메시지입니다. 자세한 내용은 [이벤트 소싱 패턴](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)합니다.

## <a name="file-triggers-and-transformations"></a>파일 트리거 및 변환

추출, 변환 및 로드 (ETL)는 일반적인 비즈니스 함수입니다. 서버 리스는 훌륭한 솔루션 ETL에 대 한 코드는 파이프라인의 일부로 트리거될 수 있기 때문입니다. 개별 코드 구성 요소는 다양 한 측면을 해결할 수 있습니다. 하나의 서버 리스 함수 파일을 다운로드할 수 있습니다, 다른 적용 변환 및 데이터를 로드 하는 다른 코드를 테스트 하 고 독립적으로 배포할 수 있습니다 쉽게 유지 관리 하 고 필요한 경우 크기를 조정 합니다.

![서버 리스 파일 트리거 및 변환](./media/serverless-file-triggers.png)

다이어그램에서에서 구문 분석 된 데이터를 제공 "쿨 저장소" [Azure Stream Analytics](https://docs.microsoft.com/azure/stream-analytics)합니다. 데이터 스트림에서 발생 하는 모든 문제는 변칙을 해결 하기 위해 Azure Function을 트리거합니다.

## <a name="asynchronous-background-processing-and-messaging"></a>비동기 백그라운드 처리 및 메시징

비동기 메시징 및 백그라운드 처리 응용 프로그램을 기다릴 필요 없이 프로세스를 시작할 수 있습니다. 비동기 처리의 예로 OCR 앱. 이미지를 제출 하 고 처리를 위해 대기 합니다. 텍스트를 추출 하는 이미지 검색 시간이 걸릴 수 하 고 알림을 완료 되 면 전송 됩니다. 서버는 호출과 결과이 시나리오를 모두 처리할 수 있습니다.

## <a name="web-apps-and-apis"></a>웹 앱 및 Api

널리 사용 되는 시나리오에 대 한 서버 리스는 N 계층 응용 프로그램에 가장 일반적으로 UI 레이어를 웹 앱 인 것입니다. 단일 페이지 응용 프로그램 (SPA)의 인기도 최근에 사항이 급증 했 했습니다. SPA 앱 단일 페이지를 렌더링 한 다음 전체 페이지를 다시 로드 하지 않고 새 UI를 동적으로 렌더링 하는 API 호출 및 반환된 된 데이터에 의존 합니다. 클라이언트 쪽 렌더링에 훨씬 빠르고 응답성 우수한 응용 프로그램을 최종 사용자에 게 제공합니다.

API 요청을 처리할 HTTP 호출에 의해 트리거되는 서버 리스 끝점을 사용할 수 있습니다. 예를 들어 ad 서비스 회사는 사용자 지정 광고를 요청 하려면 사용자 프로필 정보를 사용 하 여 서버 리스 함수를 호출할 수 있습니다. 서버 리스 함수 사용자 지정 ad를 반환 하 고 웹 페이지를 렌더링 합니다.

![서버 리스 웹 API](./media/serverless-web-api.png)

## <a name="data-pipeline"></a>데이터 파이프라인

서버 리스 functions 데이터 파이프라인을 용이 하 게 사용할 수 있습니다. 이 예제에서는 파일을 테이블의 데이터 행에 CSV 파일에서 데이터를 변환 하는 함수를 트리거합니다. 구성 된 테이블에는 최종 사용자에 게 분석을 제공 하는 Power BI 대시보드를 수 있습니다.

![서버 리스 데이터 파이프라인](./media/serverless-data-pipeline.png)

## <a name="stream-processing"></a>Stream 처리

장치 및 센서를 실시간으로 종종 처리 해야 하는 데이터 스트림을 생성 합니다. 메시지 및 스트림에서 캡처할 수 있는 기술의 여러 가지 [Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) 하 고 [IoT Hub](https://docs.microsoft.com/azure/iot-hub) 하 [Service Bus](https://docs.microsoft.com/azure/service-bus)합니다. 전송에 관계 없이 서버 리스는 이상적인 메커니즘이 들어오는 메시지 및 데이터 스트림을 처리 합니다. 서버는 대용량 데이터의 요구 사항에 맞게 신속 하 게 확장할 수 있습니다. 서버 리스 코드 데이터 및 구조화 된 형식으로 작업 및 분석에 대 한 출력을 구문 분석에 비즈니스 논리를 적용할 수 있습니다.

![서버 리스 스트림 처리](./media/serverless-stream-processing.png)

## <a name="api-gateway"></a>API 게이트웨이

API 게이트웨이 클라이언트에 대 한 항목의 단일 지점을 제공 하 고 백 엔드 서비스에 요청을 지능적으로 라우팅합니다. 서비스의 큰 집합을 관리 하는 것이 유용 합니다. 또한 버전 관리를 처리 및 클라이언트가 서로 다른 환경에 쉽게 연결 하 여 개발을 간소화 합니다. 서버는 백 엔드 API 게이트웨이 통해 단일 프런트 엔드를 제공 하는 동안 개별 마이크로 서비스의 확장을 처리할 수 있습니다.

![서버 리스 API 게이트웨이](./media/serverless-api-gateway.png)

## <a name="recommended-resources"></a>권장 되는 리소스

* [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
* [Azure IoT Hub](https://docs.microsoft.com/azure/iot-hub)
* [분산 데이터 관리의 문제 및 솔루션](../microservices-architecture/architect-microservice-container-applications/distributed-data-management.md)
* [마이크로 서비스 디자인: 마이크로 서비스 경계 식별](https://docs.microsoft.com/azure/architecture/microservices/microservice-boundaries)
* [Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
* [이벤트 소싱 패턴](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)
* [회로 차단기 패턴 구현](../microservices-architecture/implement-resilient-applications/implement-circuit-breaker-pattern.md)
* [IoT Hub](https://docs.microsoft.com/azure/iot-hub)
* [Service Bus](https://docs.microsoft.com/azure/service-bus)
* [변경 피드 지원의 Azure Cosmos DB를 사용 하 여 작업](https://docs.microsoft.com/azure/cosmos-db/change-feed)

>[!div class="step-by-step"]
>[이전](serverless-architecture-considerations.md)
>[다음](azure-serverless-platform.md)
