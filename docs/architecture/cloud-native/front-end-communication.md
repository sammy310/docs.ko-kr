---
title: 프런트 엔드 클라이언트 통신
description: 프런트 엔드 클라이언트가 클라우드 네이티브 시스템과 통신하는 방법 알아보기
author: robvet
ms.date: 09/08/2019
ms.openlocfilehash: af26873381509df7807db6ecb37a7d73669adb37
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989079"
---
# <a name="front-end-client-communication"></a>프런트 엔드 클라이언트 통신

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

클라우드 네이티브 시스템에서 프런트 엔드 클라이언트(모바일, 웹 및 데스크톱 응용 프로그램)는 독립적인 백 엔드 마이크로 서비스와 상호 작용하기 위해 통신 채널이 필요합니다.  

옵션은 무엇입니까?

간단하게 하기 위해 프런트 엔드 클라이언트는 그림 4-2에 표시된 백 엔드 마이크로 서비스와 *직접 통신할* 수 있습니다.

![클라이언트를 서비스 통신으로 유도](./media/direct-client-to-service-communication.png)

**그림 4-2.** 클라이언트를 서비스 통신으로 유도

이 방법을 사용하면 각 마이크로 서비스에프런트 엔드 클라이언트가 액세스할 수 있는 공용 끝점이 있습니다. 프로덕션 환경에서는 트래픽을 비례적으로 라우팅하여 마이크로 서비스 앞에 로드 밸러블러를 배치해야 합니다.

구현은 간단하지만 직접 클라이언트 통신은 간단한 마이크로 서비스 응용 프로그램에서만 허용됩니다. 이 패턴은 프론트 엔드 클라이언트를 핵심 백 엔드 서비스와 긴밀하게 결합하여 다음과 같은 여러 가지 문제에 대한 문을 열어 주며 다음과 같은 여러 가지 문제에 대한 문을 열어 주며 다음과 같은 문제를 해결합니다.

- 백 엔드 서비스 리팩터링에 대한 클라이언트 감수성.
- 코어 백 엔드 서비스가 직접 노출됨에 따라 공격 표면이 넓어집니다.
- 각 마이크로 서비스 전반에 걸친 교차 절단 문제의 중복.
- 지나치게 복잡한 클라이언트 코드 - 클라이언트는 여러 끝점을 추적하고 복원력 있는 방식으로 오류를 처리해야 합니다.

대신 널리 사용되는 클라우드 디자인 패턴은 프런트 엔드 응용 프로그램과 백 엔드 서비스 간에 [API 게이트웨이](../microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md) 서비스를 구현하는 것입니다. 패턴은 도 4-3에 도시되어 있다.

![API 게이트웨이 패턴](./media/api-gateway-pattern.png)

**그림 4-3.** API 게이트웨이 패턴

이전 그림에서는 API 게이트웨이 서비스가 백 엔드 코어 마이크로 서비스를 추상화하는 방법을 알아두습니다. 웹 API로 구현되는 이 프록시는 *역방향 프록시*역할을 하며 들어오는 트래픽을 내부 마이크로 서비스로 라우팅합니다.

게이트웨이는 클라이언트를 내부 서비스 분할 및 리팩터링으로부터 격리합니다. 백 엔드 서비스를 변경하는 경우 클라이언트를 손상시키지 않고 게이트웨이에서 서비스를 수용합니다. 또한 ID, 캐싱, 복원력, 계량 및 제한과 같은 교차 절단 문제에 대한 첫 번째 방어선이기도 합니다. 이러한 교차 절단 문제 중 대부분은 백 엔드 코어 서비스에서 게이트웨이로 오프로드되어 백 엔드 서비스를 단순화할 수 있습니다.

API 게이트웨이를 간단하고 빠르게 유지하려면 주의해야 합니다. 일반적으로 비즈니스 논리는 게이트웨이에서 유지됩니다. 복잡한 게이트웨이는 병목 현상이 되고 결국에는 모놀리스 자체가 될 위험이 있습니다. 대규모 시스템에서는 클라이언트 유형(모바일, 웹, 데스크톱) 또는 백 엔드 기능별로 분할된 여러 API 게이트웨이가 노출되는 경우가 많습니다. [프런트 엔드용 백 엔드](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) 패턴은 여러 게이트웨이를 구현하기 위한 방향을 제공합니다. 패턴은 도 4-4에 도시되어 있다.

![API 게이트웨이 패턴](./media/backend-for-frontend-pattern.png)

**그림 4-4.** 프런트 엔드 패턴용 백엔드

이전 그림에서는 클라이언트 유형(웹, 모바일 또는 데스크톱 앱)에 따라 들어오는 트래픽이 특정 API 게이트웨이로 전송되는 방법을 참고합니다. 이 방법은 폼 팩터, 성능 및 디스플레이 제한에 따라 각 장치의 기능이 크게 다르기 때문에 의미가 있습니다. 일반적으로 모바일 응용 프로그램은 브라우저 또는 데스크톱 응용 프로그램보다 기능이 적습니다. 각 게이트웨이는 해당 장치의 기능 및 기능에 맞게 최적화할 수 있습니다.

시작하려면 자체 API 게이트웨이 서비스를 빌드할 수 있습니다. GitHub의 빠른 검색은 많은 예제를 제공합니다. 그러나 여러 프레임워크와 상용 게이트웨이 제품을 사용할 수 있습니다.

## <a name="ocelot-gateway"></a>오셀롯 게이트웨이

간단한 .NET 클라우드 네이티브 응용 프로그램의 경우 [Ocelot 게이트웨이를](https://github.com/ThreeMammals/Ocelot)고려할 수 있습니다. Ocelot는 .NET 마이크로 서비스에 대해 생성된 오픈 소스 API 게이트웨이로, 시스템에 통합된 진입점이 필요합니다. 가볍고 빠르며 확장성이 있습니다.

다른 API 게이트웨이와 마찬가지로 주요 기능은 들어오는 HTTP 요청을 다운스트림 서비스로 전달하는 것입니다. 또한 .NET Core 미들웨어 파이프라인에서 구성할 수 있는 다양한 기능을 지원합니다. 해당 기능 집합은 다음 표에 표시됩니다.

|오셀롯 특징  | |
| :-------- | :-------- |
| 라우팅 | 인증 |
| 요청 집계 | 권한 부여 |
| 서비스 디스커버리(영사 및 유레카) | 제한 |
| 부하 분산 | 로깅, 추적 |
| 캐싱 | 헤더/쿼리 문자열 변환 |
| 상관 관계 통과 | 사용자 정의 미들웨어 |
| 서비스 품질 | 다시 시도 정책 |

각 Ocelot 게이트웨이는 JSON 구성 파일에서 업스트림 및 다운스트림 주소와 구성 가능한 기능을 지정합니다. 클라이언트는 Ocelot 게이트웨이에 HTTP 요청을 보냅니다. 수신되면 Ocelot는 해당 파이프라인을 통해 HttpRequest 개체를 구성에 의해 지정된 상태로 조작합니다. 파이프라인이 끝나면 Ocelot는 새 HTTPResponseObject를 만들고 다운스트림 서비스에 전달합니다. 응답의 경우 Ocelot는 파이프라인을 반대로 하여 응답을 클라이언트로 다시 보냅니다.

오셀롯은 NuGet 패키지로 사용할 수 있습니다. NET 표준 2.0을 대상으로 하여 .NET Core 2.0+ 및 .NET Framework 4.6.1+ 런타임과 호환됩니다. OcelotHTTP를 말하는 모든 것과 통합 하 고 .NET 코어 지원 하는 플랫폼에서 실행: 리눅스, 맥 OS, 그리고 윈도우. Ocelot은 확장 가능하며 Docker 컨테이너, Azure Kubernetes 서비스 또는 기타 퍼블릭 클라우드를 비롯한 많은 최신 플랫폼을 지원합니다.  오셀롯은 [영사,](https://www.consul.io) [GraphQL,](https://graphql.org)넷플릭스의 [유레카](https://github.com/Netflix/eureka)와 같은 오픈 소스 패키지와 통합된다.

상용 API 게이트웨이의 풍부한 기능 집합이 필요하지 않은 간단한 클라우드 네이티브 응용 프로그램에 Ocelot을 고려하십시오.

## <a name="azure-application-gateway"></a>Azure Application Gateway

간단한 게이트웨이 요구 사항의 경우 [Azure 응용 프로그램 게이트웨이](https://docs.microsoft.com/azure/application-gateway/overview)를 고려할 수 있습니다. Azure [PaaS 서비스로](https://azure.microsoft.com/overview/what-is-paas/)사용할 수 있으며 URL 라우팅, SSL 종료 및 웹 응용 프로그램 방화벽과 같은 기본 게이트웨이 기능이 포함되어 있습니다. 이 서비스는 [계층-7 부하 분산](https://www.nginx.com/resources/glossary/layer-7-load-balancing/) 기능을 지원합니다. 계층 7에서는 하위 수준 TCP 네트워크 패킷뿐만 아니라 HTTP 메시지의 실제 내용을 기반으로 요청을 라우팅할 수 있습니다.

이 책 전반에 걸쳐, 우리는 [Kubernetes에서](https://www.infoworld.com/article/3268073/what-is-kubernetes-your-next-application-platform.html)클라우드 네이티브 시스템을 호스팅하는 것을 전파합니다. 컨테이너 오케스트레이터인 Kubernetes는 컨테이너화된 워크로드의 배포, 크기 조정 및 운영 문제를 자동화합니다. Azure 응용 프로그램 게이트웨이Azure [Kubernetes 서비스](https://azure.microsoft.com/services/kubernetes-service/) 클러스터에 대 한 API 게이트웨이로 구성할 수 있습니다.

[응용 프로그램 게이트웨이 침투 컨트롤러를](https://azure.github.io/application-gateway-kubernetes-ingress/) 사용 하 고 Azure 응용 프로그램 게이트웨이 Azure [Kubernetes 서비스로](https://azure.microsoft.com/services/kubernetes-service/)직접 작동 할 수 있습니다. 그림 4.5는 아키텍처를 나타낸다.

![Application Gateway 수신 컨트롤러](./media/application-gateway-ingress-controller.png)

**그림 4-5.** Application Gateway 수신 컨트롤러

Kubernetes에는 침투라는 HTTP(레벨 7) 부하 분산을 지원하는 기본 제공 기능이 포함되어 [있습니다.](https://kubernetes.io/docs/concepts/services-networking/ingress/) Inress는 AKS 내의 마이크로 서비스 인스턴스가 외부 세계에 노출되는 방법에 대한 규칙 집합을 정의합니다. 이전 이미지에서 inress 컨트롤러는 클러스터에 대해 구성된 inress 규칙을 해석하고 Azure 응용 프로그램 게이트웨이를 자동으로 구성합니다. 이러한 규칙에 따라 응용 프로그램 게이트웨이는 AKS 내에서 실행되는 마이크로 서비스로 트래픽을 라우팅합니다. 수신 컨트롤러는 수신 규칙의 변경 내용을 수신하고 Azure 응용 프로그램 게이트웨이를 적절하게 변경합니다.

## <a name="azure-api-management"></a>Azure API Management

보통에서 대규모 클라우드 네이티브 시스템의 경우 [Azure API 관리를](https://azure.microsoft.com/services/api-management/)고려할 수 있습니다. 이는 API 게이트웨이 요구 사항을 해결할 뿐만 아니라 모든 기능을 갖춘 개발자 및 관리 환경을 제공하는 클라우드 기반 서비스입니다. API 관리는 그림 4-6에 나와 있습니다.

![Azure API Management](./media/azure-api-management.png)

**그림 4-6.** Azure API Management

먼저 API Management는 구성 가능한 규칙 및 정책에 따라 백 엔드 서비스에 대한 제어된 액세스를 허용하는 게이트웨이 서버를 노출합니다. 이러한 서비스는 Azure 클라우드, 온-프레임 데이터 센터 또는 기타 공용 클라우드에 있을 수 있습니다. API 키와 JWT 토큰은 누가 무엇을 할 수 있는지를 결정합니다. 모든 트래픽은 분석 목적으로 기록됩니다.

개발자의 경우 API Management는 서비스, 설명서 및 샘플 코드를 호출하기 위한 액세스 권한을 제공하는 개발자 포털을 제공합니다. 개발자는 Swagger/Open API를 사용하여 서비스 끝점을 검사하고 사용량을 분석할 수 있습니다. 이 서비스는 .NET, Java, Golang 등 주요 개발 플랫폼에서 작동합니다.

게시자 포털은 관리자가 API를 노출하고 동작을 관리하는 관리 대시보드를 노출합니다. 서비스 액세스 권한을 부여하고, 서비스 상태를 모니터링하고, 서비스 원격 분석을 수집할 수 있습니다. 관리자는 각 끝점에 *정책을* 적용하여 동작에 영향을 미칩니다. [정책은](https://docs.microsoft.com/azure/api-management/api-management-howto-policies) 각 서비스 호출에 대해 순차적으로 실행되는 미리 빌드된 명령문입니다.  정책은 인바운드 호출, 아웃바운드 호출 또는 오류 시 호출에 대해 구성됩니다. 정책을 결합할 때 결정적인 순서를 사용할 수 있도록 다양한 서비스 범위에 정책을 적용할 수 있습니다. 이 제품은 미리 빌드된 [정책이](https://docs.microsoft.com/azure/api-management/api-management-policies)다수 와 함께 제공됩니다.

다음은 정책이 클라우드 네이티브 서비스의 동작에 영향을 줄 수 있는 예입니다.  

- 서비스 액세스를 제한합니다.
- 인증을 적용합니다.  
- 필요한 경우 단일 소스에서 호출하는 스로틀입니다.
- 캐싱을 사용하도록 설정합니다.
- 특정 IP 주소의 통화를 차단합니다.
- 서비스의 흐름을 제어합니다.
- SOAP에서 REST로 또는 XML에서 JSON으로 다른 데이터 형식 간에 요청을 변환합니다.

Azure API Management는 클라우드 또는 데이터 센터에서 어디서나 호스팅되는 백 엔드 서비스를 노출할 수 있습니다. 클라우드 네이티브 시스템에 노출될 수 있는 레거시 서비스의 경우 REST API와 SOAP API를 모두 지원합니다. API 관리를 통해 다른 Azure 서비스도 노출될 수 있습니다. Azure [Service Bus](https://azure.microsoft.com/services/service-bus/) 또는 Azure 논리 앱과 같은 Azure 백업 서비스 위에 관리되는 API를 배치할 수 [있습니다.](https://azure.microsoft.com/services/logic-apps/) Azure API Management에는 기본 제공 로드 밸런싱 지원이 포함되어 있지 않으며 로드 밸런싱 서비스와 함께 사용해야 합니다.

Azure API 관리는 [네 가지 계층에서](https://azure.microsoft.com/pricing/details/api-management/)사용할 수 있습니다.

- Developer
- Basic
- Standard
- Premium

개발자 계층은 비프로덕션 워크로드 및 평가를 위한 것입니다. 다른 계층은 점진적으로 더 많은 전력, 기능 및 더 높은 서비스 수준 계약(SLA)을 제공합니다. 프리미엄 계층은 [Azure 가상 네트워크](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) 및 [다중 지역 지원을](https://docs.microsoft.com/azure/api-management/api-management-howto-deploy-multi-region)제공합니다. 모든 등급은 시간당 고정 가격을 가합니다.

최근 Microsoft는 Azure API 관리를 위한 [API 관리 서버없는 계층을](https://azure.microsoft.com/blog/announcing-azure-api-management-for-serverless-architectures/) 발표했습니다. 소비 가격 *책정 계층이라고*하는 이 서비스는 서버리스 컴퓨팅 모델을 중심으로 설계된 API 관리의 변형입니다. 이전에 표시된 "사전 할당된" 가격 책정 계층과 달리 소비 계층은 즉각적인 프로비저닝 및 액션당 지불 가격을 제공합니다.

API 게이트웨이 기능을 사용하면 다음과 같은 사용 사례에 대해 다음과 같은 기능을 사용할 수 있습니다.

- 마이크로 서비스는 Azure Functions 및 Azure [논리 앱과](https://azure.microsoft.com/services/logic-apps/)같은 서버없는 기술을 사용하여 [구현되었습니다.](https://docs.microsoft.com/azure/azure-functions/functions-overview)
- 서비스 버스 큐 및 토픽, Azure 저장소 등과 같은 Azure 백업 서비스 리소스입니다.
- 트래픽이 가끔 큰 스파이크를 가지고 있지만 대부분의 시간 동안 낮은 남아 있는 마이크로 서비스.

소비 계층은 동일한 기본 서비스 API 관리 구성 요소를 사용하지만 동적으로 할당된 리소스를 기반으로 완전히 다른 아키텍처를 사용합니다. 서버리스 컴퓨팅 모델과 완벽하게 일치합니다.

- 관리할 인프라가 없습니다.
- 유휴 용량이 없습니다.
- 고가용성.
- 자동 배율 조정.
- 비용은 실제 사용량을 기준으로 합니다.
  
새로운 소비 계층은 서버없는 리소스를 API로 노출시키는 클라우드 네이티브 시스템에 적합합니다.

> 작성 시 소비 계층은 Azure 클라우드에서 미리 보기상태입니다.

## <a name="real-time-communication"></a>실시간 통신

실시간 또는 푸시 통신은 HTTP를 통해 백 엔드 클라우드 네이티브 시스템과 통신하는 프런트 엔드 애플리케이션의 또 다른 옵션입니다. 금융 시세, 온라인 교육, 게임 및 작업 진행 업데이트와 같은 응용 프로그램에는 백 엔드에서 즉각적인 실시간 응답이 필요합니다. 일반 HTTP 통신에서는 클라이언트가 새 데이터를 사용할 수 있는 시기를 알 수 없습니다. 클라이언트는 지속적으로 *폴링하거나* 서버에 요청을 보내야 합니다. *실시간* 통신을 통해 서버는 언제든지 새 데이터를 클라이언트에 푸시할 수 있습니다.

실시간 시스템은 종종 고주파 데이터 흐름과 많은 수의 동시 클라이언트 연결을 특징으로 합니다. 실시간 연결을 수동으로 구현하면 빠르게 복잡해질 수 있으며, 연결된 클라이언트에 대한 확장성과 안정적인 메시징을 보장하기 위해 사소한 인프라가 필요합니다. Azure Redis Cache의 인스턴스와 클라이언트 선호도에 대한 고정 세션으로 구성된 로드 밸런서 집합을 관리하는 자신을 찾을 수 있습니다.

[Azure SignalR 서비스는](https://azure.microsoft.com/services/signalr-service/) 클라우드 네이티브 응용 프로그램에 대한 실시간 통신을 간소화하는 완전히 관리되는 Azure 서비스입니다. 용량 프로비저닝, 크기 조정 및 영구 연결과 같은 기술 구현 세부 정보는 추상화됩니다. 99.9%의 서비스 수준 계약으로 처리됩니다. 인프라 배관이 아닌 응용 프로그램 기능에 중점을 둡니다.

클라우드 기반 HTTP 서비스가 활성화되면 브라우저, 모바일 및 데스크톱 응용 프로그램을 비롯한 연결된 클라이언트에 직접 콘텐츠 업데이트를 푸시할 수 있습니다. 클라이언트는 서버를 폴링할 필요 없이 업데이트됩니다. Azure SignalR는 WebSocket, 서버 측 이벤트 및 긴 폴링을 포함하여 실시간 연결을 만드는 전송 기술을 추상화합니다. 개발자는 연결된 클라이언트의 전체 또는 특정 하위 집합에 메시지를 보내는 데 중점을 둡니다.

그림 4-7은 Azure SignalR이 활성화된 클라우드 네이티브 응용 프로그램에 연결하는 HTTP 클라이언트 집합을 보여 주며 있습니다.

![Azure SignalR](./media/azure-signalr-service.png)

**그림 4-7.** Azure SignalR

Azure SignalR 서비스의 또 다른 장점은 서버리스 클라우드 네이티브 서비스를 구현하는 데 있습니다. Azure Functions 트리거를 통해 코드가 요청 시 실행될 수 있습니다. 이 시나리오는 코드가 클라이언트와의 긴 연결을 유지하지 않기 때문에 까다로울 수 있습니다. Azure SignalR Service는 이미 사용자를 위해 연결을 관리하므로 이러한 상황을 처리할 수 있습니다.

Azure SignalR 서비스는 Azure SQL Database, Service Bus 또는 Redis Cache와 같은 다른 Azure 서비스와 긴밀하게 통합되어 클라우드 네이티브 응용 프로그램에 대한 많은 가능성을 열어줍니다.

>[!div class="step-by-step"]
>[이전](communication-patterns.md)
>[다음](service-to-service-communication.md)
