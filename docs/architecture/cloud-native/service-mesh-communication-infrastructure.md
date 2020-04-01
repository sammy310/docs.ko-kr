---
title: 서비스 메시 통신 인프라
description: 서비스 메시 기술이 클라우드 네이티브 마이크로 서비스 통신을 간소화하는 방법에 대해 알아봅니다.
author: robvet
ms.date: 03/03/2020
ms.openlocfilehash: 6b177ef33b804ec35f3acb919539a97683e5a487
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523514"
---
# <a name="service-mesh-communication-infrastructure"></a>서비스 메시 통신 인프라

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

이 장에서는 마이크로 서비스 통신의 과제를 탐구했습니다. 개발 팀은 백 엔드 서비스가 서로 통신하는 방식에 민감해야 한다고 말했습니다. 이상적으로는 서비스 간 통신이 적을수록 좋습니다. 그러나 백 엔드 서비스가 작업을 완료하기 위해 서로 의존하는 경우가 많기 때문에 항상 피할 수 있는 것은 아닙니다.

동기 HTTP 통신 및 비동기 메시징을 구현하기 위한 다양한 방법을 살펴봤습니다. 각 경우에 개발자는 통신 코드를 구현해야 하는 부담을 안고 있습니다. 통신 코드는 복잡하고 시간이 많이 많이 됩니다. 잘못된 결정은 심각한 성능 문제를 초래할 수 있습니다.

마이크로 서비스 통신에 대한 보다 현대적인 접근 방식은 서비스 *메시라는*새롭고 빠르게 진화하는 기술을 중심으로 합니다. [서비스 메시는](https://www.nginx.com/blog/what-is-a-service-mesh/) 서비스 간 통신, 복원력 및 많은 교차 절단 문제를 처리하는 기능이 내장된 구성 가능한 인프라 계층입니다. 이러한 우려에 대한 책임은 마이크로 서비스에서 서비스 메시 계층으로 이동합니다. 통신은 마이크로 서비스에서 멀리 추상화됩니다.

서비스 메시의 핵심 구성 요소는 프록시입니다. 클라우드 네이티브 응용 프로그램에서 프록시 인스턴스는 일반적으로 각 마이크로 서비스와 공존합니다. 두 프로세스는 별도의 프로세스에서 실행되는 동안 밀접하게 연결되어 동일한 수명 주기를 공유합니다. 사이드카 [패턴이라고](https://docs.microsoft.com/azure/architecture/patterns/sidecar)하는 이 패턴은 도 4-24에 도시되어 있다.

![사이드 카가 있는 서비스 메쉬](./media/service-mesh-with-side-car.png)

**그림 4-24** 사이드 카가 있는 서비스 메쉬

이전 그림에서는 각 마이크로 서비스와 함께 실행되는 프록시에 의해 메시지가 가로채는 방법을 참고합니다. 각 프록시는 마이크로 서비스와 관련된 트래픽 규칙으로 구성할 수 있습니다. 메시지를 이해하고 서비스 및 외부 세계로 메시지를 라우팅할 수 있습니다.

서비스 간 통신 관리와 함께 서비스 메시는 서비스 검색 및 부하 분산을 지원합니다.

일단 구성되면 서비스 메시는 매우 기능적입니다. 메시는 서비스 검색 끝점에서 해당 인스턴스 풀을 검색합니다. 결과의 대기 시간 및 응답 유형을 기록하는 특정 서비스 인스턴스에 요청을 보냅니다. 최근 요청에 대한 관찰된 대기 시간을 포함하여 여러 요인에 따라 빠른 응답을 반환할 가능성이 가장 높은 인스턴스를 선택합니다.

서비스 메시는 응용 프로그램 수준에서 트래픽, 통신 및 네트워킹 문제를 관리합니다. 메시지와 요청을 이해합니다. 서비스 메시는 일반적으로 컨테이너 오케스트레이터와 통합됩니다. Kubernetes는 서비스 메시를 추가할 수 있는 확장 가능한 아키텍처를 지원합니다.

6장에서는 아키텍처 및 사용 가능한 오픈 소스 구현에 대한 토론을 포함하여 서비스 메시 기술에 대해 자세히 설명합니다.

## <a name="summary"></a>요약

이 장에서는 클라우드 네이티브 통신 패턴에 대해 설명했습니다. 프론트 엔드 클라이언트가 백 엔드 마이크로 서비스와 통신하는 방법을 검토하는 것으로 시작했습니다. 그 과정에서 API 게이트웨이 플랫폼과 실시간 통신에 대해 이야기했습니다. 그런 다음 마이크로 서비스가 다른 백 엔드 서비스와 통신하는 방법을 살펴보았습니다. 서비스 간에 동기 HTTP 통신과 비동기 메시징을 모두 살펴보았습니다. 우리는 클라우드 네이티브 세계에서 곧 출시될 기술인 gRPC를 다루었습니다. 마지막으로 마이크로 서비스 통신을 간소화할 수 있는 서비스 메시라는 새롭고 빠르게 진화하는 기술을 도입했습니다.

특히 클라우드 네이티브 시스템에서 통신을 구현하는 데 도움이 되는 관리되는 Azure 서비스에 중점을 두는 데 중점을 두어 있습니다.

- [Azure 응용 프로그램 게이트웨이](https://docs.microsoft.com/azure/application-gateway/overview)
- [Azure API Management](https://azure.microsoft.com/services/api-management/)
- [Azure SignalR Service](https://azure.microsoft.com/services/signalr-service/)
- [Azure Storage 큐](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction)
- [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
- [Azure 이벤트 허브](https://azure.microsoft.com/services/event-hubs/)

다음으로 클라우드 네이티브 시스템의 분산 데이터로 이동하고 이점과 과제를 해결합니다.

### <a name="references"></a>참조

- [.NET 마이크로 서비스: 컨테이너화된 .NET 응용 프로그램을 위한 아키텍처](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [마이크로 서비스를 위한 서비스 간 통신 설계](https://docs.microsoft.com/azure/architecture/microservices/design/interservice-communication)

- [Azure SignalR 서비스, 실시간 기능을 추가 하기 위해 완전 관리 되는 서비스](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [Azure API 게이트웨이 도입 컨트롤러](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [Azure Kubernetes 서비스(AKS)의 침투 정보](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [gRPC 문서](https://grpc.io/docs/guides/)

- [WCF 개발자를 위한 gRPC](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/)

- [GRPC 서비스와 HTTP API 비교](https://docs.microsoft.com/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

- [.NET 비디오로 gRPC 서비스 구축](https://channel9.msdn.com/Shows/The-Cloud-Native-Show/Building-Microservices-with-gRPC-and-NET)

>[!div class="step-by-step"]
>[이전](grpc.md)
>[다음](Database-per-microservice.md)
