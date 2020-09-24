---
title: 복원력 있는 통신
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 복원 력 있는 통신
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 18b26223634efc5c05f680d0cbb7c8cbc2490a59
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166042"
---
# <a name="resilient-communications"></a>복원 력 있는 통신

이 책 전체에서 마이크로 서비스 기반 아키텍처 접근 방식을 받아들이고 했습니다. 이러한 아키텍처는 중요 한 이점을 제공 하지만 많은 문제를 제공 합니다.

- *Out-of-process 네트워크 통신.* 각 마이크로 서비스는 네트워크 정체, 대기 시간 및 일시적인 오류를 소개 하는 네트워크 프로토콜을 통해 통신 합니다.

- *서비스 검색.* 자체 IP 주소 및 포트가 있는 컴퓨터 클러스터에서 실행 될 때 마이크로 서비스에서 서로를 검색 하 고 통신 하는 방법

- *복구.* 단기 오류를 관리 하 고 시스템을 안정적으로 유지 하려면 어떻게 해야 하나요?

- *부하 분산.* 인바운드 트래픽은 마이크로 서비스의 여러 인스턴스에 걸쳐 어떻게 분산 되나요?

- *보안.* 전송 수준 암호화 및 인증서 관리와 같은 보안 문제는 어떻게 적용 되나요?

- *분산 모니터링.* -여러 사용 마이크로 서비스에서 단일 요청에 대 한 추적 및 모니터링의 상관 관계를 어떻게 파악 하 고 캡처해야 하나요?

다양 한 라이브러리 및 프레임 워크를 사용 하 여 이러한 문제를 해결할 수 있지만 구현에는 비용이 많이 들고 복잡 하며 시간이 많이 걸릴 수 있습니다. 비즈니스 논리에 결합 된 인프라 문제도 해결 합니다.

## <a name="service-mesh"></a>서비스 메시

더 나은 방법은 *서비스 메시*의 진화 하는 기술입니다. [서비스 메시](https://www.nginx.com/blog/what-is-a-service-mesh/) 는 서비스 통신 및 위에서 언급 한 기타 과제를 처리 하는 기본 제공 기능이 포함 된 구성 가능한 인프라 계층입니다. 이러한 문제를 서비스 프록시로 이동 하 여 이러한 문제를 분리 합니다. 프록시는 비즈니스 코드에서 격리를 제공 하기 위해 별도의 프로세스 ( [사이드카](/azure/architecture/patterns/sidecar)라고 함)에 배포 됩니다. 그러나 사이드카는 서비스에 연결 되며,이를 사용 하 여 생성 되 고 수명 주기를 공유 합니다. 그림 6-7에서는이 시나리오를 보여 줍니다.

![측 자동차를 사용 하는 서비스 메시](./media/service-mesh-with-side-car.png)

**그림 6-7** 측 자동차를 사용 하는 서비스 메시

위의 그림에서 프록시는 마이크로 서비스와 클러스터 간의 통신을 차단 하 고 관리 하는 방법을 확인 합니다.

서비스 메시는 논리적으로 서로 다른 두 구성 요소인 [데이터 평면과](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) [컨트롤 평면](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc)으로 분할 됩니다. 그림 6-8에서는 이러한 구성 요소와 해당 책임을 보여 줍니다.

![서비스 메시 컨트롤 및 데이터 평면](./media/istio-control-and-data-plane.png)

**그림 6-8.** 서비스 메시 컨트롤 및 데이터 평면

구성 된 후에는 서비스 메쉬가 매우 작동 합니다. 서비스 검색 끝점에서 인스턴스의 해당 풀을 검색할 수 있습니다. 그런 다음 메시는 특정 인스턴스에 요청을 보내 결과의 대기 시간 및 응답 유형을 기록할 수 있습니다. 메시는 최근 요청에 대 한 관찰 된 대기 시간을 비롯 하 여 많은 요소를 기준으로 빠른 응답을 반환할 가능성이 가장 높은 인스턴스를 선택할 수 있습니다.

인스턴스가 응답 하지 않거나 실패 하면 메시는 다른 인스턴스에서 요청을 다시 시도 합니다. 오류가 반환 되 면 메시는 로드 균형 조정 풀에서 인스턴스를 제거 하 고 치료 된 후에 다시 말하지만 합니다. 요청 시간이 초과 되 면 메시에 실패할 수 있습니다. 그런 다음 요청을 다시 시도 합니다. 메시는 메트릭 및 분산 추적을 캡처하여 중앙 메트릭 시스템으로 내보냅니다.

## <a name="istio-and-envoy"></a>Istio 및 엔보이

몇 가지 서비스 메시 옵션이 현재 존재 하지만이 문서를 작성할 당시에는 [Istio](https://istio.io/docs/concepts/what-is-istio/) 가 가장 인기 있는 것입니다. Istio는 IBM, Google 및 Lyft의 공동 공동입니다. 새 배포 응용 프로그램 또는 기존 응용 프로그램에 통합 될 수 있는 오픈 소스 제품입니다. 이 기술은 마이크로 서비스를 보호, 연결 및 모니터링 하기 위한 일관 되 고 완전 한 솔루션을 제공 합니다. 해당 기능은 다음과 같습니다.

- 강력한 id 기반 인증 및 권한 부여를 사용 하 여 클러스터에서 서비스 간 통신을 보호 합니다.
- HTTP, [Grpc](https://grpc.io/), WEBSOCKET 및 TCP 트래픽에 대 한 자동 부하 분산.
- 풍부한 라우팅 규칙, 다시 시도, 장애 조치 (failover) 및 오류 주입을 통해 트래픽 동작을 세부적으로 제어 합니다.
- 액세스 제어, 요율 제한 및 할당량을 지 원하는 플러그형 정책 계층 및 구성 API
- 클러스터 수신 및 송신을 포함 하 여 클러스터 내의 모든 트래픽에 대 한 자동 메트릭, 로그 및 추적

Istio 구현에 대 한 주요 구성 요소는 [엔보이 프록시](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)를 담당 하는 프록시 서비스입니다. 각 서비스와 함께 실행 되며 다음과 같은 기능에 대 한 플랫폼 독립적인 토대를 제공 합니다.

- 동적 서비스 검색.
- 부하 분산 -
- TLS 종료.
- HTTP 및 gRPC 프록시.
- 회로 차단기 복원 력.
- 상태 검사.
- [카나리아](https://martinfowler.com/bliki/CanaryRelease.html) 배포를 사용 하 여 업데이트를 롤링 합니다.

앞에서 설명한 것 처럼 엔보이는 클러스터의 각 마이크로 서비스에 대 한 사이드카으로 배포 됩니다.

## <a name="integration-with-azure-kubernetes-services"></a>Azure Kubernetes Services와의 통합

Azure cloud는 Istio를 수용 하 고 Azure Kubernetes 서비스 내에서이를 직접 지원 합니다. 다음 링크를 통해 시작할 수 있습니다.

- [AKS에 Istio 설치](/azure/aks/istio-install)
- [AKS 및 Istio 사용](/azure/aks/istio-scenario-routing)

### <a name="references"></a>참조

- [Polly](http://www.thepollyproject.org/)

- [다시 시도 패턴](/azure/architecture/patterns/retry)

- [회로 차단기 패턴](/azure/architecture/patterns/circuit-breaker)

- [Azure의 복원 력](https://azure.microsoft.com/mediahandler/files/resourcefiles/resilience-in-azure-whitepaper/Resilience%20in%20Azure.pdf)

- [네트워크 대기 시간](https://www.techopedia.com/definition/8553/network-latency)

- [중복](/azure/architecture/guide/design-principles/redundancy)

- [지역에서 복제](/azure/sql-database/sql-database-active-geo-replication)

- [Azure Traffic Manager](/azure/traffic-manager/traffic-manager-overview)

- [자동 크기 조정 지침](/azure/architecture/best-practices/auto-scaling)

- [Istio](https://istio.io/docs/concepts/what-is-istio/)

- [엔보이 프록시](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)

>[!div class="step-by-step"]
>[이전](infrastructure-resiliency-azure.md)
>[다음](monitoring-health.md)
