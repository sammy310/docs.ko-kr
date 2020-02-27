---
title: 네트워크 프로토콜-WCF 개발자를 위한 gRPC
description: GRPC 네트워크 프로토콜에 대 한 개요입니다.
ms.date: 09/02/2019
ms.openlocfilehash: 1ceb140f7b7ac7e796a87612ebb9d21e28d33968
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628490"
---
# <a name="network-protocols"></a>네트워크 프로토콜

Windows Communication Foundation (WCF)와 달리 gRPC는 네트워킹의 기반으로 HTTP/2를 사용 합니다. 이는 HTTP/1.1 에서만 작동 하는 WCF 및 SOAP에 비해 상당한 이점을 제공 합니다. GRPC를 사용 하려는 개발자에 게는 HTTP/2에 대 한 대안이 없다는 것을 알 수 있고, h t t p/2에 대 한 자세한 정보를 제공 하 고, gRPC 사용의 추가 혜택을 확인 하는 것이 좋습니다.

2015의 Internet 공학적 작업 Force에서 릴리스된 HTTP/2는 Google에서 이미 사용 중인 실험적 SPDY 프로토콜에서 파생 되었습니다. 이는 HTTP/1.1 보다 더 효율적이 고, 더 빠르고, 안전 하도록 설계 되었습니다.

## <a name="key-features-of-http2"></a>HTTP/2의 주요 기능

이 목록에는 HTTP/2의 주요 기능 및 장점 중 일부가 나와 있습니다.

### <a name="binary-protocol"></a>이진 프로토콜

요청/응답 주기에는 더 이상 텍스트 명령이 필요 하지 않습니다. 이렇게 하면 명령의 구현이 간소화 되 고 속도가 빨라집니다. 특히 데이터를 구문 분석 하는 것이 더 빨라지고 메모리를 사용 하는 경우에는 성능 향상을 위해 네트워크 대기 시간이 줄어들고 네트워크 리소스를 전반적으로 더 효율적으로 사용할 수 있습니다.

### <a name="streams"></a>스트림

스트림을 사용 하 여 송신자와 수신자 간에 수명이 긴 연결을 만들 수 있습니다 .이를 통해 여러 메시지나 프레임을 비동기적으로 보낼 수 있습니다. 다중 스트림은 단일 HTTP/2 연결을 통해 독립적으로 작동할 수 있습니다.

### <a name="request-multiplexing-over-a-single-tcp-connection"></a>단일 TCP 연결에 대 한 요청 멀티플렉싱

이 기능은 HTTP/2의 가장 중요 한 혁신 중 하나입니다. 데이터에 대해 여러 병렬 요청을 허용 하기 때문에 이제 단일 서버에서 웹 파일을 동시에 다운로드할 수 있습니다. Websites는 더 빠르게 로드 되며 최적화의 필요성이 줄어듭니다. 이전 요청이 완료 될 때까지 준비 된 응답이 전송 될 때까지 대기 해야 하는 줄의 (유월) 차단입니다 .이 차단으로 인해 TCP 전송 수준에서 유월 차단이 계속 발생할 수 있습니다.

### <a name="nettcp-like-performance-cross-platform"></a>Net.tcp와 같은 성능, 플랫폼 간

기본적으로 gRPC와 HTTP/2의 조합은 개발자에 게 WCF에 대 한 Net.tcp 바인딩의 최소 속도와 효율성을 제공 하 고, 경우에 따라 속도와 효율성을 향상 시킬 수도 있습니다. 하지만 Net.tcp와 달리 HTTP/2를 통한 gRPC는 .NET 응용 프로그램으로 제한 되지 않습니다.

>[!div class="step-by-step"]
>[이전](interface-definition-language.md)
>[다음](why-grpc.md)
