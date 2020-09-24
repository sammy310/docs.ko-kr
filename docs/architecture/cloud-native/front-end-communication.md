---
title: 프런트 엔드 클라이언트 통신
description: 프런트 엔드 클라이언트가 클라우드 네이티브 시스템과 통신 하는 방법 알아보기
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 147adb3d0375f8bf5dadf14e1237aa93e9e42908
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158112"
---
# <a name="front-end-client-communication"></a>프런트 엔드 클라이언트 통신

클라우드 네이티브 시스템에서 프런트 엔드 클라이언트 (모바일, 웹 및 데스크톱 응용 프로그램)는 독립적인 백 엔드 마이크로 서비스와 상호 작용 하기 위해 통신 채널이 필요 합니다.  

그 옵션은 무엇입니까?

간단히 하기 위해 프런트 엔드 클라이언트는 그림 4-2에 표시 된 백 엔드 마이크로 서비스와 *직접 통신할* 수 있습니다.

![클라이언트와 서비스 간 통신](./media/direct-client-to-service-communication.png)

**그림 4-2.** 클라이언트와 서비스 간 통신

이 접근 방식을 사용 하는 경우 각 마이크로 서비스에는 프런트 엔드 클라이언트에서 액세스할 수 있는 공용 끝점이 있습니다. 프로덕션 환경에서는 부하 분산 장치를 마이크로 서비스 앞에 놓고 트래픽을 비례적으로 라우팅합니다.

간단 하 게 구현할 수 있는 반면, 직접 클라이언트 통신은 간단한 마이크로 서비스 응용 프로그램에만 허용 됩니다. 이 패턴은 프런트 엔드 클라이언트를 핵심 백 엔드 서비스에 긴밀 하 게 결합 다음을 비롯 한 다양 한 문제에 대 한 도어를 엽니다.

- 클라이언트에서 백 엔드 서비스 영향력 합니다.
- 핵심 백 엔드 서비스가 직접 노출 되는 더 광범위 한 공격 노출 영역입니다.
- 각 마이크로 서비스 간 교차 자르기 문제를 복제 합니다.
- 과도 하 게 복잡 한 클라이언트 코드-클라이언트는 여러 끝점을 추적 하 고 복원 력 있는 방식으로 오류를 처리 해야 합니다.

대신, 광범위 하 게 허용 되는 클라우드 디자인 패턴은 프런트 엔드 응용 프로그램과 백 엔드 서비스 간에 [API 게이트웨이 서비스](../microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md) 를 구현 하는 것입니다. 이 패턴은 그림 4-3에 나와 있습니다.

![API 게이트웨이 패턴](./media/api-gateway-pattern.png)

**그림 4-3.** API 게이트웨이 패턴

위의 그림에서 API Gateway 서비스가 백 엔드 핵심 마이크로 서비스를 추상화 하는 방법을 확인 합니다. 웹 API로 구현 되는 *역방향 프록시*역할을 하 여 들어오는 트래픽을 내부 마이크로 서비스로 라우팅합니다.

게이트웨이는 내부 서비스 분할 및 리팩터링의 클라이언트를 분리 합니다. 백 엔드 서비스를 변경 하는 경우 클라이언트를 중단 하지 않고 게이트웨이에서 해당 서비스를 수용 합니다. 또한 id, 캐싱, 복원 력, 계량, 제한과 같은 교차 절삭 문제에 대 한 첫 번째 방어선입니다. 이러한 교차 잘라내기 문제는 대부분 백 엔드 핵심 서비스에서 게이트웨이로 오프 로드 되어 백 엔드 서비스를 간소화할 수 있습니다.

API 게이트웨이를 간단 하 고 신속 하 게 유지 하기 위해 주의를 기울여야 합니다. 일반적으로 비즈니스 논리는 게이트웨이에서 유지 됩니다. 복잡 한 게이트웨이는 병목 상태가 되 고 궁극적으로는 모놀리식가 될 위험이 있습니다. 규모가 큰 시스템은 종종 클라이언트 유형 (모바일, 웹, 데스크톱) 또는 백 엔드 기능을 통해 분할 된 여러 API 게이트웨이를 노출 합니다. [백 엔드 For 프런트 엔드](/azure/architecture/patterns/backends-for-frontends) 패턴은 여러 게이트웨이를 구현 하는 방향을 제공 합니다. 이 패턴은 그림 4-4에 나와 있습니다.

![API 게이트웨이 패턴](./media/backend-for-frontend-pattern.png)

**그림 4-4.** 프런트 엔드 패턴의 백 엔드

위의 그림에서는 들어오는 트래픽이 클라이언트 유형 (웹, 모바일 또는 데스크톱 앱)에 따라 특정 API 게이트웨이로 전송 되는 방법을 설명 합니다. 이 방법은 각 장치의 기능이 폼 팩터, 성능 및 디스플레이 제한에서 크게 다를 수 있기 때문에 유용 합니다. 일반적으로 모바일 응용 프로그램은 브라우저 또는 데스크톱 응용 프로그램 보다 더 작은 기능을 노출 합니다. 각 게이트웨이는 해당 장치의 기능 및 기능에 맞게 최적화할 수 있습니다.

시작 하려면 고유한 API 게이트웨이 서비스를 빌드할 수 있습니다. GitHub를 빠르게 검색 하면 많은 예제를 제공 합니다. 그러나 사용할 수 있는 프레임 워크와 상용 게이트웨이 제품은 여러 가지가 있습니다.

## <a name="ocelot-gateway"></a>Ocelot 게이트웨이

간단한 .NET 클라우드 네이티브 응용 프로그램의 경우 [Ocelot 게이트웨이](https://github.com/ThreeMammals/Ocelot)를 고려할 수 있습니다. Ocelot는 시스템에 대 한 진입점을 통합 해야 하는 .NET 마이크로 서비스에 대해 생성 된 오픈 소스 API 게이트웨이입니다. 간단 하 고 빠르게 확장 가능 합니다.

모든 API 게이트웨이와 마찬가지로 기본 기능은 들어오는 HTTP 요청을 다운스트림 서비스에 전달 하는 것입니다. 또한 .NET Core 미들웨어 파이프라인에서 구성할 수 있는 다양 한 기능을 지원 합니다. 해당 기능 집합은 다음 표에 나와 있습니다.

|Ocelot 기능  | |
| :-------- | :-------- |
| 라우팅 | 인증 |
| 요청 집계 | 권한 부여 |
| 서비스 검색 (Consul 및 Eureka 포함) | 제한 |
| 부하 분산 | 로깅, 추적 |
| 캐싱 | 헤더/쿼리 문자열 변환 |
| 상관 관계 통과 | 사용자 지정 미들웨어 |
| 서비스 품질 | 다시 시도 정책 |

각 Ocelot 게이트웨이는 JSON 구성 파일에서 업스트림 및 다운스트림 주소와 구성 가능한 기능을 지정 합니다. 클라이언트는 HTTP 요청을 Ocelot 게이트웨이로 보냅니다. 수신 되 면 Ocelot은 파이프라인을 통해 HttpRequest 개체를 전달 하 여 해당 구성에 지정 된 상태로 해당 개체를 조작 합니다. 파이프라인의 끝에서 Ocelot는 새 HTTPResponseObject를 만들고 다운스트림 서비스에 전달 합니다. 응답의 경우 Ocelot는 파이프라인을 반대로 되돌리고 응답을 클라이언트에 다시 보냅니다.

Ocelot는 NuGet 패키지로 사용할 수 있습니다. NET Standard 2.0를 대상으로 하 여 .NET Core 2.0 + 및 .NET Framework 4.6.1 + 런타임과 호환 되도록 합니다. Ocelot는 HTTP를 말하는 것과 .NET Core에서 지 원하는 플랫폼 (Linux, macOS 및 Windows)에서 실행 되는 것과 통합 됩니다. Ocelot는 확장 가능 하며 Docker 컨테이너, Azure Kubernetes 서비스 또는 기타 공용 클라우드를 비롯 한 다양 한 최신 플랫폼을 지원 합니다.  Ocelot은 [Consul](https://www.consul.io), [GraphQL](https://graphql.org)및 Netflix [Eureka](https://github.com/Netflix/eureka)와 같은 오픈 소스 패키지와 통합 됩니다.

상업적 API 게이트웨이의 풍부한 기능 집합이 필요 하지 않은 간단한 클라우드 네이티브 응용 프로그램에 대해 Ocelot을 고려 합니다.

## <a name="azure-application-gateway"></a>Azure Application Gateway

간단한 게이트웨이 요구 사항에 대 한 [Azure 애플리케이션 게이트웨이](/azure/application-gateway/overview)를 고려할 수 있습니다. Azure [PaaS 서비스로](https://azure.microsoft.com/overview/what-is-paas/)사용할 수 있으며 URL 라우팅, SSL 종료 및 웹 응용 프로그램 방화벽과 같은 기본 게이트웨이 기능을 포함 합니다. 이 서비스는 [계층 7 부하 분산](https://www.nginx.com/resources/glossary/layer-7-load-balancing/) 기능을 지원 합니다. 계층 7을 사용 하면 하위 수준 TCP 네트워크 패킷 뿐만 아니라 HTTP 메시지의 실제 콘텐츠를 기반으로 요청을 라우팅할 수 있습니다.

이 책 전체에서는 [Kubernetes](https://www.infoworld.com/article/3268073/what-is-kubernetes-your-next-application-platform.html)에서 클라우드 네이티브 시스템을 전도 합니다. 컨테이너 오 케 스트레이 터 Kubernetes는 컨테이너 화 된 워크 로드의 배포, 크기 조정 및 운영 문제를 자동화 합니다. Azure 애플리케이션 게이트웨이는 [Azure Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/) 클러스터에 대 한 API 게이트웨이로 구성할 수 있습니다.

[Application Gateway 수신 컨트롤러](https://azure.github.io/application-gateway-kubernetes-ingress/) 를 사용 하면 Azure 애플리케이션 게이트웨이가 [Azure Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/)에서 직접 작업할 수 있습니다. 그림 4.5은 아키텍처를 보여 줍니다.

![Application Gateway 수신 컨트롤러](./media/application-gateway-ingress-controller.png)

**그림 4-5.** Application Gateway 수신 컨트롤러

Kubernetes에는 [수신](https://kubernetes.io/docs/concepts/services-networking/ingress/)이라고 하는 HTTP (수준 7) 부하 분산을 지 원하는 기본 제공 기능이 포함 되어 있습니다. 수신은 AKS 내의 마이크로 서비스 인스턴스를 외부 세계에 노출 하는 방법에 대 한 규칙 집합을 정의 합니다. 이전 이미지에서 수신 컨트롤러는 클러스터에 대해 구성 된 수신 규칙을 해석 하 고 Azure 애플리케이션 게이트웨이를 자동으로 구성 합니다. 이러한 규칙에 따라 Application Gateway는 AKS 내부에서 실행 되는 마이크로 서비스로 트래픽을 라우팅합니다. 수신 컨트롤러는 수신 규칙에 대 한 변경 내용을 수신 대기 하 고 Azure 애플리케이션 게이트웨이의 적절 한 변경을 수행 합니다.

## <a name="azure-api-management"></a>Azure API Management

중간 규모에서 대규모 클라우드 네이티브 시스템의 경우 [Azure API Management](https://azure.microsoft.com/services/api-management/)를 고려할 수 있습니다. API 게이트웨이 요구 사항을 해결할 뿐만 아니라 모든 기능을 갖춘 개발자 및 관리 환경을 제공 하는 클라우드 기반 서비스입니다. API Management은 그림 4-6에 나와 있습니다.

![Azure API Management](./media/azure-api-management.png)

**그림 4-6.** Azure API Management

시작 하기 위해 구성 가능한 규칙 및 정책에 따라 백 엔드 서비스에 대 한 제어 된 액세스를 허용 하는 게이트웨이 서버를 API Management 노출 합니다. 이러한 서비스는 Azure cloud, 온-프레미스 데이터 센터 또는 다른 공용 클라우드에 있을 수 있습니다. API 키와 JWT 토큰은 어떤 작업을 수행할 수 있는지를 결정 합니다. 모든 트래픽은 분석 용도로 기록 됩니다.

개발자를 위한 API Management 서비스, 설명서 및이를 호출 하는 샘플 코드에 대 한 액세스를 제공 하는 개발자 포털을 제공 합니다. 개발자는 Swagger/Open API를 사용 하 여 서비스 끝점을 검사 하 고 사용을 분석할 수 있습니다. 이 서비스는 .NET, Java, Golang 등의 주요 개발 플랫폼에서 작동 합니다.

게시자 포털은 관리자가 Api를 노출 하 고 해당 동작을 관리 하는 관리 대시보드를 제공 합니다. 서비스 액세스를 부여 하 고, 서비스 상태를 모니터링 하 고, 수집 된 서비스 원격 분석을 수행할 수 있습니다. 관리자는 동작에 영향을 주기 위해 각 끝점에 *정책을* 적용 합니다. [정책은](/azure/api-management/api-management-howto-policies) 각 서비스 호출에 대해 순차적으로 실행 되는 미리 작성 된 문입니다.  정책은 인바운드 호출 또는 아웃 바운드 호출에 대해 구성 되거나 오류 발생 시 호출 됩니다. 정책을 조합할 때 결정적 정렬을 사용 하도록 설정 하기 위해 다른 서비스 범위에 정책을 적용할 수 있습니다. 제품은 미리 작성 된 많은 수의 [정책과](/azure/api-management/api-management-policies)함께 제공 됩니다.

정책에서 클라우드 네이티브 서비스의 동작에 영향을 주는 방법에 대 한 예는 다음과 같습니다.  

- 서비스 액세스를 제한 합니다.
- 인증을 적용 합니다.  
- 필요한 경우 단일 소스에서 호출을 제한 합니다.
- 캐싱을 사용하도록 설정합니다.
- 특정 IP 주소에서 호출을 차단 합니다.
- 서비스의 흐름을 제어 합니다.
- 요청을 SOAP에서 REST로 또는 다른 데이터 형식 (예: XML에서 JSON)으로 변환 합니다.

Azure API Management는 클라우드 또는 데이터 센터의 어디에서 나 호스트 되는 백 엔드 서비스를 노출할 수 있습니다. 클라우드 네이티브 시스템에 노출할 수 있는 레거시 서비스의 경우 REST 및 SOAP Api를 모두 지원 합니다. API Management를 통해 다른 Azure 서비스를 노출할 수도 있습니다. [Azure Service Bus](https://azure.microsoft.com/services/service-bus/) 또는 [Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)와 같이 Azure 지원 서비스 위에 관리 되는 API를 추가할 수 있습니다. Azure API Management에는 부하 분산 지원이 기본적으로 포함 되어 있지 않으며 부하 분산 서비스와 함께 사용 해야 합니다.

Azure API Management는 다음과 같은 [네 가지 계층](https://azure.microsoft.com/pricing/details/api-management/)에서 제공 됩니다.

- 개발자
- Basic
- Standard
- Premium

개발자 계층은 비프로덕션 워크 로드 및 평가를 위한 것입니다. 다른 계층은 점차적으로 더 많은 기능을 제공 하 고 Sla (서비스 수준 계약)를 더 많이 제공 합니다. 프리미엄 계층은 [Azure Virtual Network](/azure/virtual-network/virtual-networks-overview) 및 [다중 지역 지원을](/azure/api-management/api-management-howto-deploy-multi-region)제공 합니다. 모든 계층에는 시간당 고정 가격이 있습니다.

Azure 클라우드는 Azure API Management에 대 한 [서버 리스 계층](https://azure.microsoft.com/blog/announcing-azure-api-management-for-serverless-architectures/) 도 제공 합니다. *소비 가격 책정 계층*이라고 하는 서비스는 서버 리스 컴퓨팅 모델을 중심으로 디자인 된 API Management의 변형입니다. 이전에 표시 된 "미리 할당 된" 가격 책정 계층과 달리 소비 계층은 즉각적인 프로 비전 및 작업별 요금 책정을 제공 합니다.

다음 사용 사례에 대해 API 게이트웨이 기능을 사용 하도록 설정 합니다.

- [Azure Functions](/azure/azure-functions/functions-overview) 및 [Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)와 같이 서버를 사용 하지 않는 기술을 사용 하 여 구현 된 마이크로 서비스입니다.
- Azure 지원 서비스 리소스 (예: 큐, 항목, Azure storage 및 기타)를 Service Bus 합니다.
- 트래픽이 크게 급증 하지만 대부분의 시간을 유지 하는 마이크로 서비스

소비 계층은 동일한 기본 서비스 API Management 구성 요소를 사용 하지만 동적으로 할당 된 리소스에 따라 완전히 다른 아키텍처를 사용 합니다. 서버 리스 컴퓨팅 모델에 완벽 하 게 부합 합니다.

- 관리할 인프라가 없습니다.
- 유휴 용량이 없습니다.
- 고가용성.
- 자동 크기 조정.
- 비용은 실제 사용량을 기준으로 합니다.
  
새 소비 계층은 서버를 사용 하지 않는 리소스를 Api로 노출 하는 클라우드 네이티브 시스템에 매우 적합 합니다.

## <a name="real-time-communication"></a>실시간 통신

실시간 또는 푸시 통신은 HTTP를 통해 백 엔드 클라우드 네이티브 시스템과 통신 하는 프런트 엔드 응용 프로그램에 대 한 또 다른 옵션입니다. 금융 시세표, 온라인 교육, 게임 및 작업 진행 상황 업데이트와 같은 응용 프로그램에는 즉시 백 엔드에서 실시간 응답이 필요 합니다. 정상적인 HTTP 통신을 사용 하는 경우 클라이언트에서 새 데이터를 사용할 수 있는 시기를 알 수 있는 방법이 없습니다. 클라이언트는 지속적으로 요청을 *폴링하고* 서버로 요청을 보내야 합니다. *실시간* 통신을 사용 하면 서버는 언제 든 지 새 데이터를 클라이언트에 푸시할 수 있습니다.

실시간 시스템은 종종 높은 빈도의 데이터 흐름과 많은 동시 클라이언트 연결로 구분 됩니다. 실시간 연결을 수동으로 구현 하는 것이 복잡 해질 수 있으며, 연결 된 클라이언트에 대 한 확장성과 안정적인 메시징을 보장 하기 위해 단순한 인프라가 필요 합니다. 클라이언트 선호도에 대해 고정 세션으로 구성 된 부하 분산 장치 집합 및 Azure Redis Cache 인스턴스를 관리 하는 것을 확인할 수 있습니다.

[Azure SignalR service](https://azure.microsoft.com/services/signalr-service/) 는 클라우드 네이티브 응용 프로그램에 대 한 실시간 통신을 간소화 하는 완전히 관리 되는 azure 서비스입니다. 용량 프로 비전, 크기 조정 및 영구 연결과 같은 기술 구현 정보를 추상화 합니다. 99.9% 서비스 수준 계약을 사용 하 여 처리 됩니다. 인프라가 아닌 응용 프로그램 기능에 집중 합니다.

사용 하도록 설정 되 면 클라우드 기반 HTTP 서비스는 브라우저, 모바일 및 데스크톱 응용 프로그램을 포함 하 여 콘텐츠 업데이트를 연결 된 클라이언트에 직접 푸시할 수 있습니다. 클라이언트는 서버를 폴링할 필요 없이 업데이트 됩니다. Azure SignalR는 Websocket, 서버측 이벤트 및 긴 폴링을 포함 하 여 실시간 연결을 만드는 전송 기술을 추상화 합니다. 개발자는 연결 된 클라이언트의 모든 또는 특정 하위 집합에 메시지를 보내는 데 중점을 둡니다.

그림 4-7에서는 Azure SignalR를 사용 하는 클라우드 네이티브 응용 프로그램에 연결 하는 HTTP 클라이언트 집합을 보여 줍니다.

![Azure SignalR](./media/azure-signalr-service.png)

**그림 4-7.** Azure SignalR

Azure SignalR 서비스의 또 다른 장점은 서버 리스 클라우드 네이티브 서비스를 구현 하는 것과 함께 제공 됩니다. Azure Functions 트리거를 사용 하 여 요청 시 코드가 실행 될 것입니다. 코드가 클라이언트와 긴 연결을 유지 하지 않기 때문에이 시나리오는 복잡할 수 있습니다. Azure SignalR Service는 이미 사용자를 위해 연결을 관리하므로 이러한 상황을 처리할 수 있습니다.

Azure SignalR Service는 Azure SQL Database, Service Bus, Redis Cache 등의 다른 Azure 서비스와 긴밀 하 게 통합 되어 클라우드 네이티브 응용 프로그램에 대 한 여러 가지 가능성을 엽니다.

>[!div class="step-by-step"]
>[이전](communication-patterns.md)
>[다음](service-to-service-communication.md)
