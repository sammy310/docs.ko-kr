---
title: 복원력 있는 통신
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 복원 력 있는 통신
ms.date: 06/30/2019
ms.openlocfilehash: 324f5426af1c892db73aa6fc2336a19b7a8e499e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "73841224"
---
# <a name="resilient-communications"></a>복원 력 있는 통신

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

이 책 전체에서 기존의 모놀리식 응용 프로그램 디자인을 벗어나 이동 하는 것을 evangelized, 일련의 자체 포함 된 서비스를 독립적으로 실행 하 고 각 서비스와 통신 하는 마이크로 서비스 기반 아키텍처를 수용 하는 장점에 대해 살펴보았습니다. HTTP 및 HTTPS와 같은 표준 통신 프로토콜을 사용 하는 기타 이러한 아키텍처는 많은 중요 한 이점을 제공 하지만 많은 과제가 있습니다. 예를 들어 다음과 같은 사항을 고려해 야 합니다.

- *Out-of-process 네트워크 통신.* 각 서비스는 네트워크 정체, 대기 시간 및 일시적인 오류를 소개 하는 네트워크 프로토콜을 통해 통신 합니다.
- *서비스 검색.* 자체 IP 주소 및 포트가 있는 컴퓨터 클러스터에서 각 서비스를 실행 하는 경우 서비스에서 서로 어떻게 검색 하 고 통신 하나요?
- *복구.* 단기 오류를 관리 하 고 시스템을 안정적으로 유지 하려면 어떻게 해야 하나요?
- *부하 분산.* 인바운드 트래픽은 서비스의 여러 인스턴스에 걸쳐 어떻게 분산 되나요?
- *보안.* 전송 수준 암호화 및 인증서 관리와 같은 보안 문제는 어떻게 적용 되나요?
- *분산 모니터링.* -여러 사용 서비스에서 단일 요청에 대 한 추적 및 모니터링을 상호 연결 하 고 캡처하는 방법은 무엇입니까?

이러한 문제는 다양 한 라이브러리 및 프레임 워크를 사용 하 여 해결할 수 있지만 코드 베이스 내에서 구현 하는 것은 비용이 많이 들고 복잡 하며 시간이 많이 걸릴 수 있습니다. 또한 인프라 관심사가 비즈니스 논리에 결합 된 솔루션을 사용 합니다.

## <a name="service-mesh"></a>서비스 메시

보다 신속 하 게 진화 하는 새로운 기술 *서비스 메시*를 고려 하는 것이 더 좋습니다. [서비스 메시](https://www.nginx.com/blog/what-is-a-service-mesh/) 는 서비스 통신 및 위에서 언급 한 많은 문제를 처리 하는 기본 제공 기능이 포함 된 구성 가능한 인프라 계층입니다. 이러한 문제를 비즈니스 코드에서 분리 각 서비스를 제공 하는 인스턴스인 서비스 프록시로 이동 합니다. [사이드카 패턴](https://docs.microsoft.com/azure/architecture/patterns/sidecar)이라고 하는 서비스 메시 프록시는 비즈니스 코드에서 격리 및 캡슐화를 제공 하기 위해 별도의 프로세스에 배포 됩니다. 그러나 프록시는 함께 생성 되는 서비스와 밀접 하 게 연결 되며 수명 주기를 공유 합니다. 그림 6-9에서는이 시나리오를 보여 줍니다.

![측 자동차를 사용 하는 서비스 메시](./media/service-mesh-with-side-car.png)

**그림 6-9** 측 자동차를 사용 하는 서비스 메시

위의 그림에서 프록시는 마이크로 서비스와 클러스터 간의 통신을 차단 하 고 관리 하는 방법을 확인 합니다.

서비스 메시는 논리적으로 서로 다른 두 구성 요소인 [데이터 평면과](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) [컨트롤 평면](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc)으로 분할 됩니다. 그림 6-10에서는 이러한 구성 요소와 해당 책임을 보여 줍니다.

![서비스 메시 컨트롤 및 데이터 평면](./media/istio-control-and-data-plane.png)

**그림 6-10.** 서비스 메시 컨트롤 및 데이터 평면

구성 된 후에는 서비스 메쉬가 매우 작동 합니다. 서비스 검색 끝점에서 인스턴스의 해당 풀을 검색할 수 있습니다. 그런 다음 특정 인스턴스에 요청을 보내 결과의 대기 시간 및 응답 유형을 기록할 수 있습니다. 메시는 최근 요청에 대 한 관찰 된 대기 시간을 비롯 하 여 많은 요소를 기준으로 빠른 응답을 반환할 가능성이 가장 높은 인스턴스를 선택할 수 있습니다.

인스턴스가 응답 하지 않거나 실패 하면 메시는 다른 인스턴스에서 요청을 다시 시도할 수 있습니다. 풀이 일관 되 게 오류를 반환 하는 경우 메시는 나중에 다시 사용할 수 있도록 부하 분산 풀에서 제거할 수 있습니다. 요청 시간이 초과 되 면 메시에 실패할 수 있습니다. 그런 다음 요청을 다시 시도 합니다. 메시는 메트릭 및 분산 추적의 형태로 동작을 캡처하여 중앙 메트릭 시스템으로 내보낼 수 있습니다.

## <a name="istio-and-envoy"></a>Istio 및 엔보이

몇 가지 서비스 메시 옵션이 현재 존재 하는 반면,이 문서를 작성할 때 가장 인기 있는 [Istio](https://istio.io/docs/concepts/what-is-istio/) 가 있습니다. IBM, Google 및 Lyft에서 공동으로 제공 되는 것은 신규 또는 기존 배포 응용 프로그램에 통합할 수 있는 오픈 소스 제품입니다. 마이크로 서비스를 보호, 연결 및 모니터링 하기 위한 일관 되 고 완전 한 솔루션을 제공 합니다. 해당 기능에는 다음이 포함 됩니다.

- 강력한 id 기반 인증 및 권한 부여를 사용 하 여 클러스터에서 서비스 간 통신을 보호 합니다.
- HTTP, [Grpc](https://grpc.io/), WEBSOCKET 및 TCP 트래픽에 대 한 자동 부하 분산.
- 풍부한 라우팅 규칙, 다시 시도, 장애 조치 (failover) 및 오류 주입을 통해 트래픽 동작을 세부적으로 제어 합니다.
- 액세스 제어, 요율 제한 및 할당량을 지 원하는 플러그형 정책 계층 및 구성 API
- 클러스터 수신 및 송신을 포함 하 여 클러스터 내의 모든 트래픽에 대 한 자동 메트릭, 로그 및 추적

Istio 구현에 대 한 주요 구성 요소는 [엔보이 프록시](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)를 담당 하는 프록시 서비스입니다. Lyft에서 시작 하 여 이후에 [클라우드 기본 컴퓨팅 파운데이션](https://www.cncf.io/) (1 장에서 설명)에 기여 하 고, 엔보이 프록시는 각 서비스와 함께 실행 되며 다음과 같은 기능에 대 한 플랫폼 독립적인 토대를 제공 합니다.

- 동적 서비스 검색.
- 부하 분산.
- TLS 종료.
- HTTP 및 gRPC 프록시.
- 회로 차단기 복원 력.
- 상태 검사.
- [카나리아](https://martinfowler.com/bliki/CanaryRelease.html) 배포를 사용 하 여 업데이트를 롤링 합니다.

앞에서 설명한 것 처럼 엔보이는 클러스터의 각 마이크로 서비스에 대 한 사이드카으로 배포 됩니다.

## <a name="integration-with-azure-kubernetes-services"></a>Azure Kubernetes Services와의 통합

Azure cloud는 Istio를 수용 하 고 Azure Kubernetes 서비스 내에서이를 직접 지원 합니다. 다음 링크를 통해 시작할 수 있습니다.

- [AKS에 Istio 설치](https://docs.microsoft.com/azure/aks/istio-install)
- [AKS 및 Istio 사용](https://docs.microsoft.com/azure/aks/istio-scenario-routing)

>[!div class="step-by-step"]
>[이전](infrastructure-resiliency-azure.md)
>[다음](monitoring-health.md)
