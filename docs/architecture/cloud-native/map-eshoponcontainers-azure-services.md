---
title: Azure 서비스에 eShopOnContainers 매핑
description: EShopOnContainers를 azure Kubernetes Service, API 게이트웨이 및 Azure Service Bus와 같은 Azure 서비스에 매핑합니다.
ms.date: 04/20/2020
ms.openlocfilehash: 26fce71ba71f7da643b669396ab59affe592649a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895510"
---
# <a name="mapping-eshoponcontainers-to-azure-services"></a>Azure 서비스에 eShopOnContainers 매핑

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

필수는 아니지만, 프로젝트가 클라우드 네이티브 응용 프로그램으로 빌드 되었으므로 Azure는 eShopOnContainers을 지 원하는 데 적합 합니다. 응용 프로그램은 .NET Core를 사용 하 여 빌드되므로 Docker 호스트에 따라 Linux 또는 Windows 컨테이너에서 실행할 수 있습니다. 응용 프로그램은 각각 고유한 데이터를 포함 하는 여러 자치 마이크로 서비스로 구성 됩니다. 다양 한 마이크로 서비스는 간단한 CRUD 작업에서 보다 복잡 한 DDD 및 CQRS 패턴에 이르는 다양 한 접근 방식을 소개 합니다. 마이크로 서비스는 HTTP를 통해 클라이언트와 메시지 기반 통신을 통해 서로 통신 합니다. 응용 프로그램은 HTTP를 표준 통신 프로토콜로 채택 하 고 Android, iOS 및 Windows 플랫폼에서 실행 되는 ASP.NET Core 및 Xamarin mobile 앱을 포함 하므로 클라이언트에 대해서도 여러 플랫폼을 지원 합니다.

이 응용 프로그램의 아키텍처는 그림 2-5에 나와 있습니다. 왼쪽에는 모바일, 기존 웹 및 웹 SPA (단일 페이지 응용 프로그램) 버전으로 분할 된 클라이언트 앱이 있습니다. 오른쪽에는 시스템을 구성 하는 서버 쪽 구성 요소가 있습니다. 각 구성 요소는 Docker 컨테이너 및 Kubernetes 클러스터에서 호스팅될 수 있습니다. 기존 웹 앱은 노란색으로 표시 된 ASP.NET Core MVC 응용 프로그램에 의해 구동 됩니다. 이 앱과 모바일 및 웹 SPA 응용 프로그램은 하나 이상의 API 게이트웨이를 통해 개별 마이크로 서비스와 통신 합니다. API 게이트웨이는 "프런트 엔드에 대 한 백 엔드" (BFF) 패턴을 따릅니다. 즉, 각 게이트웨이는 지정 된 프런트 엔드 클라이언트를 지원 하도록 설계 되었습니다. 개별 마이크로 서비스는 API 게이트웨이의 오른쪽에 나열 되며 비즈니스 논리와 일종의 지 속성 저장소를 포함 합니다. 여러 서비스는 SQL Server 데이터베이스, Redis cache 인스턴스 및 MongoDB/CosmosDB stores를 사용 합니다. 맨 오른쪽에는 마이크로 서비스 간의 통신에 사용 되는 시스템의 이벤트 버스가 있습니다.

![eShopOnContainers 아키텍처](./media/eshoponcontainers-architecture.png)
**그림 2-5**. EShopOnContainers 아키텍처입니다.

이 아키텍처의 서버 쪽 구성 요소는 모두 Azure 서비스에 쉽게 매핑됩니다.

## <a name="container-orchestration-and-clustering"></a>컨테이너 오케스트레이션 및 클러스터링

응용 프로그램의 컨테이너 호스팅 서비스는 ASP.NET Core MVC 앱에서 개별 카탈로그로 그리고 마이크로 서비스를 정렬 하 여 AKS (Azure Kubernetes Service)에서 호스트 하 고 관리할 수 있습니다. 응용 프로그램은 Docker 및 Kubernetes에서 로컬로 실행할 수 있으며, AKS에서 호스트 되는 스테이징 및 프로덕션 환경에 동일한 컨테이너를 배포할 수 있습니다. 이 프로세스는 다음 섹션에서 볼 수 있듯이 자동화할 수 있습니다.

AKS는 컨테이너의 개별 클러스터에 대 한 관리 서비스를 제공 합니다. 응용 프로그램은 위의 아키텍처 다이어그램에 표시 된 각 마이크로 서비스에 대해 별도의 AKS 클러스터를 배포 합니다. 이 접근 방식을 사용 하면 각 개별 서비스를 리소스 요구에 따라 독립적으로 확장할 수 있습니다. 각 마이크로 서비스를 독립적으로 배포할 수 있으며, 이러한 배포에는 시스템 가동 중지 시간이 0이 발생 해야 합니다.

## <a name="api-gateway"></a>API Gateway

EShopOnContainers 응용 프로그램에는 여러 개의 프런트 엔드 클라이언트와 여러 개의 서로 다른 백 엔드 서비스가 있습니다. 클라이언트 응용 프로그램과이를 지 원하는 마이크로 서비스 간에는 일대일 대응이 없습니다. 이러한 시나리오에서는 여러 백 엔드 서비스를 안전 하 게 사용 하 여 인터페이스에 클라이언트 소프트웨어를 작성할 때 상당한 복잡성이 있을 수 있습니다. 각 클라이언트는 이러한 복잡성을 해결 해야 하며,이로 인해 중복이 발생 하 고 서비스 변경 또는 새로운 정책이 구현 될 때 업데이트를 수행할 수 있는 많은 위치가 중복 될 수 있습니다.

APIM (Azure API Management)은 조직에서 일관 되 고 관리 가능한 방식으로 Api를 게시 하는 데 도움이 됩니다. APIM은 세 가지 구성 요소인 API 게이트웨이 및 관리 포털 (Azure Portal) 및 개발자 포털로 구성 됩니다.

API 게이트웨이는 API 호출을 수락 하 고 적절 한 백 엔드 API로 라우팅합니다. 또한 코드 수정 없이 (예: 이전 인터페이스가 필요한 클라이언트를 수용 하기 위해) API 키 또는 JWT 토큰 및 API 변환의 유효성 검사와 같은 추가 서비스를 제공할 수 있습니다.

Azure Portal API 스키마를 정의 하 고 다양 한 Api를 제품에 패키지할 수 있습니다. 또한 사용자 액세스를 구성 하 고, 보고서를 보고, 할당량 또는 변환에 대 한 정책을 구성할 수 있습니다.

개발자 포털은 개발자를 위한 기본 리소스로 사용 됩니다. 개발자에 게 API 설명서를 제공 하 고 대화형 테스트 콘솔을 제공 하며 자체 사용에 대 한 보고서를 제공 합니다. 또한 개발자는 포털을 사용 하 여 구독 및 API 키 지원을 포함 하 여 자신의 계정을 만들고 관리 합니다.

APIM을 사용 하 여 응용 프로그램은 각각 특정 프런트 엔드 클라이언트의 백 엔드를 제공 하는 여러 가지 서비스 그룹을 노출할 수 있습니다. APIM은 복잡 한 시나리오에 권장 됩니다. 간단한 요구를 위해 간단한 API 게이트웨이 Ocelot를 사용할 수 있습니다. EShopOnContainers 앱은 응용 프로그램 자체와 동일한 응용 프로그램 환경에 배포할 수 있기 때문에 Ocelot를 사용 합니다. [EShopOnContainers, APIM 및 Ocelot에 대해 자세히 알아보세요.](https://docs.microsoft.com/dotnet/architecture/microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern#azure-api-management)

응용 프로그램이 AKS를 사용 하는 경우 또 다른 옵션은 AKS 클러스터 내에서 pod로 Azure 게이트웨이 수신 컨트롤러를 배포 하는 것입니다. 이렇게 하면 클러스터가 Azure 애플리케이션 게이트웨이와 통합 되어 게이트웨이가 AKS pod에 대 한 트래픽 부하를 분산할 수 있습니다. [AKS에 대 한 Azure 게이트웨이 수신 컨트롤러에 대해 자세히 알아보세요](https://github.com/Azure/application-gateway-kubernetes-ingress).

## <a name="data"></a>데이터

EShopOnContainers에서 사용 하는 다양 한 백 엔드 서비스에는 저장소 요구 사항이 다릅니다. 여러 마이크로 서비스는 SQL Server 데이터베이스를 사용 합니다. 바구니 마이크로 서비스는 지 속성에 대 한 Redis 캐시를 활용 합니다. 마이크로 서비스 위치에는 해당 데이터에 대 한 MongoDB API가 필요 합니다. Azure는 이러한 각 데이터 형식을 지원 합니다.

SQL Server 데이터베이스 지원의 경우 Azure에는 단일 데이터베이스부터 확장성이 뛰어난 SQL Database 탄력적 풀 까지의 모든 항목에 대 한 제품이 있습니다. 개별 마이크로 서비스는 각자의 개별 SQL Server 데이터베이스와 빠르고 쉽게 통신 하도록 구성할 수 있습니다. 이러한 데이터베이스는 요구 사항에 따라 각 개별 마이크로 서비스을 지원 하기 위해 필요에 따라 확장할 수 있습니다.

EShopOnContainers 응용 프로그램은 요청 사이에 사용자의 현재 장바구니를 저장 합니다. 이는 Redis 캐시에 데이터를 저장 하는 바구니 마이크로 서비스에서 관리 합니다. 개발 중에이 캐시를 컨테이너에 배포할 수 있지만 프로덕션 환경에서는 Redis 용 Azure Cache를 활용할 수 있습니다. Redis 용 Azure Cache는 Redis 인스턴스 또는 컨테이너를 직접 배포 하 고 관리할 필요 없이 고성능 및 안정성을 제공 하는 완전히 관리 되는 서비스입니다.

위치 마이크로 서비스는 지 속성에 MongoDB NoSQL 데이터베이스를 사용 합니다. 개발 중에는 데이터베이스를 자체 컨테이너에 배포할 수 있지만 프로덕션 환경에서는 서비스에서 [MongoDB에 대 한 Azure Cosmos DB의 API](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction)를 활용할 수 있습니다. Azure Cosmos DB의 이점 중 하나는 MongoDB, Cassandra, Gremlin 및 Azure Table Storage를 포함 하 여 SQL API 및 일반적인 NoSQL Api를 비롯 한 여러 통신 프로토콜을 활용 하는 기능입니다. Azure Cosmos DB는이를 사용 하는 서비스의 요구를 충족 하도록 확장할 수 있는 완전히 관리 되 고 전 세계적으로 분산 된 Database as a Service를 제공 합니다.

클라우드 네이티브 응용 프로그램의 분산 데이터에 대해서는 [5 장에서](distributed-data.md)자세히 설명 합니다.

## <a name="event-bus"></a>이벤트 버스

응용 프로그램은 이벤트를 사용 하 여 서로 다른 서비스 간의 변경 내용을 전달 합니다. 이 기능은 다양 한 구현을 사용 하 여 구현할 수 있으며 로컬 eShopOnContainers 응용 프로그램은 [RabbitMQ](https://www.rabbitmq.com/)를 사용 합니다. Azure에서 호스트 되는 경우 응용 프로그램은 메시징에 대 한 [Azure Service Bus](https://docs.microsoft.com/azure/service-bus/) 활용 합니다. Azure Service Bus는 완전히 관리 되는 통합 메시지 브로커로, 응용 프로그램과 서비스가 분리 되 고 신뢰할 수 있는 비동기 방식으로 서로 통신할 수 있습니다. Azure Service Bus는 개별 큐를 지원 하며 게시자-구독자 시나리오를 지원 하기 위한 별도의 *항목* 을 지원 합니다. EShopOnContainers 응용 프로그램은 Azure Service Bus와 함께 항목을 활용 하 여 지정 된 메시지에 대응 하는 데 필요한 다른 마이크로 서비스로 메시지를 분산 하는 기능을 지원 합니다.

## <a name="resiliency"></a>복원력

EShopOnContainers 응용 프로그램은 프로덕션에 배포 된 후에는 여러 Azure 서비스를 활용 하 여 복원 력을 향상 시킬 수 있습니다. 응용 프로그램은 Application Insights와 통합 되어 앱의 가용성을 기반으로 보고 및 경고를 제공할 수 있는 상태 검사를 게시 합니다. 또한 Azure 리소스는 버그 및 성능 문제를 식별 하 고 수정 하는 데 사용할 수 있는 진단 로그를 제공 합니다. 리소스 로그는 응용 프로그램에서 다양 한 Azure 리소스를 사용 하는 시기 및 방법에 대 한 자세한 정보를 제공 합니다. [6 장](resiliency.md)에서 클라우드 기본 복원 기능에 대해 자세히 알아보세요.

>[!div class="step-by-step"]
>[이전](introduce-eshoponcontainers-reference-app.md)
>[다음](deploy-eshoponcontainers-azure.md)
