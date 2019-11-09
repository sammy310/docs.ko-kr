---
title: WCF 개발자를 위한 부하 분산 gRPC-gRPC
description: GRPC 서비스를 사용할 부하 분산 장치 선택
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 18965b9c4765ac693c6ba36ad3ea9848ce858a5c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841554"
---
# <a name="load-balancing-grpc"></a>부하 분산 gRPC

GRPC 응용 프로그램의 일반적인 배포에는 복원 력 및 수평 확장 기능을 제공 하는 서비스의 여러 인스턴스가 포함 됩니다. 이러한 인스턴스 간에 분산 된 들어오는 요청을 부하 분산 하 여 사용 가능한 모든 리소스의 전체 사용량을 제공 합니다. 이 부하 분산을 클라이언트에서 볼 수 없도록 하려면 프록시 부하 분산 장치 서버를 사용 하 여 클라이언트의 요청을 처리 하 고 백 엔드 인스턴스로 라우팅하는 것이 일반적입니다.

부하 분산 장치는 작동 하는 *계층* 에 따라 분류 됩니다. 계층 4 부하 분산 장치는 TCP 소켓, 연결 및 패킷과 같은 *전송* 수준에서 작동 합니다. 계층 7 부하 분산 장치는 *응용 프로그램* 수준에서 작동 하며 특히 grpc 응용 프로그램에 대 한 HTTP/2 요청을 처리 합니다.

## <a name="l4-load-balancers"></a>L4 부하 분산 장치

L4 부하 분산 장치는 클라이언트에서 TCP 연결 요청을 수락 하 고, 백 엔드 인스턴스 중 하나에 대 한 다른 연결을 열고, 실제 처리 없이 두 연결 간에 데이터를 복사 합니다. L4는 뛰어난 성능과 짧은 대기 시간을 제공 하지만 거의 제어 하거나 인텔리전스를 제공 하지 않습니다. 클라이언트에서 연결이 열린 상태로 유지 되는 한 모든 요청은 동일한 백 엔드 인스턴스로 전송 됩니다.

L4 부하 분산 장치의 예는 [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/)입니다.

## <a name="l7-load-balancers"></a>L7 부하 분산 장치

L7 부하 분산 장치는 들어오는 HTTP/2 요청을 구문 분석 하 고 클라이언트에서 연결을 유지 하는 데 걸리는 시간에 관계 없이 요청 별로 요청 별로 백 엔드 인스턴스에 전달 합니다.

L7 부하 분산 장치의 예는 다음과 같습니다.

- [Nginx](https://www.nginx.com/)
- [HAproxy](https://www.haproxy.com/)
- [Traefik](https://traefik.io/)

이에 대 한 규칙으로, L7 부하 분산 장치는 gRPC 및 기타 HTTP/2 응용 프로그램 (일반적으로 HTTP 응용 프로그램의 경우)에 가장 적합 합니다. L4 부하 분산 장치는 gRPC 응용 프로그램에서 *작동* 하지만, 짧은 대기 시간 및 낮은 오버 헤드가 가장 중요 한 경우에 주로 유용 합니다.

> [!IMPORTANT]
> 이 문서를 작성 하는 시점에서 모든 L7 부하 분산 장치는 후행 헤더와 같은 gRPC 서비스에 필요한 모든 HTTP/2 사양의 일부를 지원 하지 않습니다.

TLS 암호화를 사용 하는 경우 부하 분산 장치는 TLS 연결을 종료 하 고 암호화 되지 않은 요청을 백 엔드 응용 프로그램에 전달 하거나 암호화 된 요청을 함께 전달할 수 있습니다. 어느 쪽이 든, 부하 분산 장치를 서버의 공개 키와 개인 키로 구성 하 여 처리 요청을 해독할 수 있도록 해야 합니다.

백 엔드 서비스를 사용 하 여 HTTP/2 요청을 처리 하도록 구성 하는 방법을 알아보려면 기본 부하 분산 장치에 대 한 설명서를 참조 하세요.

## <a name="load-balancing-within-kubernetes"></a>Kubernetes 내의 부하 분산

Kubernetes의 내부 서비스 간 부하 분산에 대 한 자세한 내용은 [서비스 메시의 섹션](service-mesh.md) 을 참조 하세요.

>[!div class="step-by-step"]
>[이전](service-mesh.md)
>[다음](application-performance-management.md)
