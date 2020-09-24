---
title: 서비스 메시 통신 인프라
description: Service 메시 기술이 클라우드 네이티브 마이크로 서비스 통신을 간소화 하는 방법에 대해 알아봅니다.
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 39dc1ded06eb0b92a2a1b40cfe981d9bd49bf381
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165951"
---
# <a name="service-mesh-communication-infrastructure"></a>서비스 메시 통신 인프라

이 장에서는 마이크로 서비스 통신의 과제를 살펴보았습니다. 개발 팀이 백 엔드 서비스와 통신 하는 방법에 대 한 중요 한 사항이 있습니다. 이상적으로 서비스 간 통신은 더 효율적입니다. 그러나 백 엔드 서비스에서 작업을 완료 하기 위해 서로 의존 하는 경우가 종종 있기 때문에 방지는 항상 가능 하지 않습니다.

동기 HTTP 통신과 비동기 메시징 구현에 대 한 여러 가지 방법을 살펴보았습니다. 각 사례에서 개발자는 통신 코드 구현에 부담이 됩니다. 통신 코드는 복잡 하 고 시간이 많이 소요 됩니다. 잘못 된 결정은 심각한 성능 문제를 일으킬 수 있습니다.

새롭고 신속 하 게 진화 하는 기술 *서비스 메시*를 중심으로 하는 마이크로 서비스 communication의 최신 접근 방식입니다. 서비스 [메시](https://www.nginx.com/blog/what-is-a-service-mesh/) 는 서비스 간 통신, 복원 력 및 많은 크로스 절삭 문제를 처리 하는 기본 제공 기능이 포함 된 구성 가능한 인프라 계층입니다. 이러한 문제에 대 한 책임을 마이크로 서비스 및 서비스 메시 계층으로 이동 합니다. 통신은 마이크로 서비스에서 벗어나 추상화 됩니다.

서비스 메시의 주요 구성 요소는 프록시입니다. 클라우드 네이티브 응용 프로그램에서 프록시 인스턴스는 일반적으로 각 마이크로 서비스와 공동 배치 됩니다. 별도의 프로세스에서 실행 되는 동안 둘은 밀접 하 게 연결 되 고 동일한 수명 주기를 공유 합니다. [사이드카 패턴](/azure/architecture/patterns/sidecar)이라고 하는이 패턴은 그림 4-24에 나와 있습니다.

![측 자동차를 사용 하는 서비스 메시](./media/service-mesh-with-side-car.png)

**그림 4-24** 측 자동차를 사용 하는 서비스 메시

위의 그림에서는 각 마이크로 서비스 함께 실행 되는 프록시가 메시지를 가로채는 방법을 설명 합니다. 각 프록시는 마이크로 서비스 관련 된 트래픽 규칙을 사용 하 여 구성할 수 있습니다. 메시지를 이해 하 고 서비스와 외부 세계에서 메시지를 라우팅할 수 있습니다.

서비스 및 서비스 간 통신 관리와 함께 서비스 메시는 서비스 검색 및 부하 분산을 지원 합니다.

구성 된 후에는 서비스 메쉬가 매우 작동 합니다. 메시는 서비스 검색 끝점에서 해당 인스턴스의 풀을 검색 합니다. 특정 서비스 인스턴스로 요청을 보내고 결과의 대기 시간 및 응답 유형을 기록 합니다. 최근 요청에 대해 관찰 된 대기 시간을 비롯 하 여 다양 한 요인을 기반으로 빠른 응답을 반환할 가능성이 가장 높은 인스턴스를 선택 합니다.

서비스 메시는 응용 프로그램 수준에서 트래픽, 통신 및 네트워킹 문제를 관리 합니다. 메시지와 요청을 이해 합니다. 일반적으로 서비스 메시는 컨테이너 orchestrator와 통합 됩니다. Kubernetes는 서비스 메시를 추가할 수 있는 확장 가능한 아키텍처를 지원 합니다.

6 장에서는 아키텍처와 사용 가능한 오픈 소스 구현에 대 한 논의를 포함 하 여 서비스 메시 기술에 대해 자세히 설명 합니다.

## <a name="summary"></a>요약

이 장에서는 클라우드 기본 통신 패턴에 대해 설명 했습니다. 프런트 엔드 클라이언트가 백 엔드 마이크로 서비스와 통신 하는 방식을 검토 하 여 시작 했습니다. 이 과정을 통해 API Gateway 플랫폼과 실시간 통신에 대해 알아보았습니다. 그런 다음 마이크로 서비스가 다른 백 엔드 서비스와 통신 하는 방법을 살펴보았습니다. 서비스 간 동기 HTTP 통신과 비동기 메시징을 모두 살펴보았습니다. 클라우드 기본 세계에서 예정 된 기술인 gRPC를 다루었습니다. 마지막으로 마이크로 서비스 통신을 간소화할 수 있는 새롭고 신속 하 게 진화 하는 기술 서비스 메시를 도입 했습니다.

클라우드 네이티브 시스템에서 통신을 구현 하는 데 도움이 되는 관리 되는 Azure 서비스에 대 한 특별 한 강조는 다음과 같습니다.

- [Azure Application Gateway](/azure/application-gateway/overview)
- [Azure API Management](https://azure.microsoft.com/services/api-management/)
- [Azure SignalR Service](https://azure.microsoft.com/services/signalr-service/)
- [Azure Storage 큐](/azure/storage/queues/storage-queues-introduction)
- [Azure Service Bus](/azure/service-bus-messaging/service-bus-messaging-overview)
- [Azure Event Grid](/azure/event-grid/overview)
- [Azure 이벤트 허브](https://azure.microsoft.com/services/event-hubs/)

이제 클라우드 네이티브 시스템에서 분산 된 데이터로 이동 하 고 그에 따른 이점과 과제가 제공 됩니다.

### <a name="references"></a>참조

- [.NET 마이크로 서비스: 컨테이너 화 된 .NET 응용 프로그램에 대 한 아키텍처](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [마이크로 서비스에 대 한 서비스 간 통신 디자인](/azure/architecture/microservices/design/interservice-communication)

- [실시간 기능을 추가 하는 완전히 관리 되는 서비스인 Azure SignalR Service](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [Azure API 게이트웨이 수신 컨트롤러](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [AKS (Azure Kubernetes Service)의 수신 정보](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [gRPC 설명서](https://grpc.io/docs/guides/)

- [WCF 개발자를 위한 gRPC](../grpc-for-wcf-developers/index.md)

- [GRPC 서비스와 HTTP Api 비교](/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

- [.NET 비디오를 사용 하 여 gRPC 서비스 빌드](https://channel9.msdn.com/Shows/The-Cloud-Native-Show/Building-Microservices-with-gRPC-and-NET)

>[!div class="step-by-step"]
>[이전](grpc.md)
>[다음](distributed-data.md)
