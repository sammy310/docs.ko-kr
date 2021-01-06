---
title: Wcf 개발자를 위한 gRPC를 wcf 개발자에 게 권장 하는 이유
description: GRPC가 최신 아키텍처 및 플랫폼으로 마이그레이션하려는 WCF 개발자에 게 적합 한 이유에 대 한 설명입니다.
ms.date: 12/15/2020
ms.openlocfilehash: 058f85297610116e96c8580fcefb10ee6dfcf935
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97937976"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a>WCF 개발자에게 gRPC를 권장하는 이유

GRPC의 언어와 기술에 대해 자세히 살펴보기 전에 gRPC가 .NET으로 마이그레이션해야 하는 WCF (Windows Communication Foundation) 개발자를 위한 적절 한 솔루션인 이유를 설명 해야 합니다.

## <a name="similarity-to-wcf"></a>WCF와 유사성

gRPC의 구현 및 접근 방식은 다르지만 gRPC를 사용하여 서비스를 개발하고 사용하는 환경은 WCF 개발자에게 직관적이어야 합니다. 기본 목표는 동일 합니다. 네트워킹에 대해 걱정할 필요 없이 클라이언트와 서버가 동일한 플랫폼에 있는 것 처럼 코딩할 수 있도록 합니다.

두 플랫폼 모두 인터페이스를 선언 하는 프로세스는 서로 다르므로 인터페이스를 선언 하 고 구현 하는 원칙을 공유 합니다. 또한 5 장에서 볼 수 있듯이 gRPC가 지 원하는 다양 한 유형의 RPC 호출은 WCF 서비스에 사용할 수 있는 바인딩에 잘 매핑됩니다.

## <a name="benefits-of-grpc"></a>gRPC의 이점

gRPC는 다음과 같은 이유 때문에 다른 솔루션을 나타냅니다.

### <a name="performance"></a>성능

HTTP/1.1이 아닌 HTTP/2를 사용 하면 사람이 읽을 수 있는 메시지에 대 한 요구 사항이 제거 되 고 더 작고 더 빠른 이진 프로토콜을 사용 합니다. 이 방법은 컴퓨터를 구문 분석 하는 것이 더 효율적입니다. HTTP/2는 단일 연결에 대 한 멀티플렉싱 요청도 지원 합니다. 이 지원을 통해 큐를 대기 하지 않고 준비 되는 즉시 응답을 보낼 수 있습니다. (HTTP/1.1에서는이 문제를 "줄의 (유월) 차단" 이라고 합니다. ") GRPC를 사용 하는 경우 더 많은 리소스가 필요 하며,이를 통해 모바일 장치와 느린 네트워크에서 사용할 수 있는 좋은 솔루션을 만들 수 있습니다.

### <a name="interoperability"></a>상호 운용성

.NET, Java, Python, Go, C++, Node.js, Swift, Dart, Ruby 및 PHP를 비롯한 모든 주요 프로그래밍 언어와 플랫폼에 대한 gRPC 도구 및 라이브러리가 있습니다. 프로토콜을 통해 이진 통신 형식 및 각 플랫폼에 대 한 효율적인 코드 생성 덕분에 개발자는 전체 플랫폼 간 지원을 제공 하면서도 고성능 앱을 빌드할 수 있습니다.

### <a name="usability-and-productivity"></a>유용성 및 생산성

gRPC는 포괄적인 RPC 솔루션입니다. 여러 언어 및 플랫폼에서 일관되게 작동합니다. 또한 많은 필수 상용구 코드를 자동으로 생성 하 여 뛰어난 도구를 제공 합니다. 따라서 비즈니스 논리에 집중 하기 위해 더 많은 개발자 시간을 확보할 수 있습니다.

### <a name="streaming"></a>스트리밍

gRPC에는 WCF의 전이중 서비스와 유사한 기능을 제공 하는 전체 양방향 스트리밍이 있습니다. gRPC 스트리밍은 일반적인 인터넷 연결, 부하 분산 장치 및 서비스 메시를 통해 작동할 수 있습니다.

### <a name="deadlinetimeouts-and-cancellation"></a>최종 기한/시간 초과 및 취소

gRPC를 통해 클라이언트는 RPC가 완료될 때까지 최대 시간을 지정할 수 있습니다. 지정된 최종 기한을 초과하면 서버에서 클라이언트와 별개로 작업을 취소할 수 있습니다. 마감일 및 취소는 리소스 사용 제한을 적용 하는 데 도움이 되도록 추가 gRPC 호출을 통해 전파 될 수 있습니다. 클라이언트는 최종 기한을 초과 하거나 필요한 경우 (예: 사용자 상호 작용으로 인해) 이전에 작업을 중지할 수도 있습니다.

### <a name="security"></a>보안

gRPC는 TLS 종단 간 암호화 된 연결에 대해 HTTP/2를 사용 하는 경우 암시적으로 안전 합니다. 클라이언트 인증서 인증에 대 한 지원 ( [6 장](security.md)참조)은 클라이언트와 서버 간의 보안 및 신뢰를 강화 합니다.

>[!div class="step-by-step"]
>[이전](network-protocols.md)
>[다음](protocol-buffers.md)
