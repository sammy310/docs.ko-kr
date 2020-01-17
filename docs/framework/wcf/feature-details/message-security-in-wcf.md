---
title: WCF의 메시지 보안
ms.date: 03/30/2017
ms.assetid: a80efb59-591a-4a37-bb3c-8fffa6ca0b7d
ms.openlocfilehash: 32f6659f6ac744ab7af07c23e7e26ea1124d020c
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212066"
---
# <a name="message-security-in-wcf"></a>WCF의 메시지 보안

Windows Communication Foundation (WCF) has two major modes for providing security (`Transport` and `Message`) and a third mode (`TransportWithMessageCredential`) that combines the two. 이 항목에서는 메시지 보안과 메시지 보안을 사용하는 이유에 대해 설명합니다.

## <a name="what-is-message-security"></a>메시지 보안이란?

메시지 보안은 WS-Security 사양을 사용하여 메시지를 보호합니다. The WS-Security specification describes enhancements to SOAP messaging to ensure confidentiality, integrity, and authentication at the SOAP message level (instead of the transport level).

간단하게 말해, 메시지 보안은 보안 자격 증명을 캡슐화하고 모든 메시지와 모든 메시지 보호(서명 또는 암호화)를 클레임한다는 점에서 전송 보안과 다릅니다. 콘텐츠를 수정하여 메시지에 보안을 직접 적용하면 보호된 메시지가 독립적인 보안을 갖출 수 있습니다. 그러면 전송 보안을 사용할 때는 불가능한 시나리오 몇 가지가 가능해집니다.

## <a name="reasons-to-use-message-security"></a>메시지 보안을 사용하는 이유

메시지 수준 보안에서는 모든 보안 정보가 메시지에 캡슐화됩니다. 전송 수준 보안 대신 메시지 수준 보안을 사용하여 메시지를 보호하면 다음과 같은 이점이 있습니다.

- 엔드투엔드 보안. SSL(Secure Sockets Layer)과 같은 보안 전송은 통신이 지점 간에서 이루어지는 경우에만 메시지 보안을 적용합니다. 메시지가 최종 수신자에 도달하기 전에 하나 이상의 SOAP 매개 지점(예: 라우터)으로 라우팅되는 경우, 매개 지점에서 와이어로부터 메시지를 읽고 나면 메시지 자체를 더 이상 보호할 수 없습니다. 또한 클라이언트 인증 정보는 첫 번째 매개 지점에서만 사용할 수 있기 때문에 필요한 경우에는 out-of-band 방식으로 최종 지점에 다시 전송해야 합니다. 이는 전체 경로에서 개별 홉 사이에 SSL 보안을 사용하는 경우에도 적용됩니다. 메시지 보안은 메시지에 직접 작용하며 그 안에 있는 XML을 보호하기 때문에, 메시지가 최종 수신자에 도달할 때까지 사용되는 매개 지점의 수에 관계없이 메시지를 계속 보호합니다. 따라서 진정한 엔드투엔드 보안 시나리오가 가능하게 됩니다.

- 유연성 향상. 메시지 전체가 아닌 메시지의 일부를 서명 또는 암호화할 수 있습니다. 즉, 메시지 중 매개 지점에 전달될 부분을 매개 지점에서 볼 수 있습니다. 발신자가 메시지의 정보 중 일부를 매개 지점에 보이게 하려는 경우 변경을 방지하려면 암호화는 하지 않고 서명만 하면 됩니다. 서명은 메시지의 일부이기 때문에 최종 수신자에서 메시지의 정보가 변경 없이 도착했는지 확인할 수 있습니다. 동작 헤더 값에 따라 메시지를 라우트하는 SOAP 매개 서비스가 있는 시나리오를 생각할 수 있습니다. By default, WCF does not encrypt the Action value but signs it if message security is used. 따라서 모든 매개 지점에서 이 정보를 볼 수 있지만 변경할 수는 없습니다.

- 다중 전송 지원. 명명된 파이프 및 TCP 등의 서로 다른 여러 전송을 통해 보안 프로토콜에 의존하지 않고도 보안 메시지를 보낼 수 있습니다. 전송 수준 보안을 사용하면 모든 보안 정보가 특정 전송 연결 하나로 범위 지정되며 메시지 콘텐츠 자체에서는 사용할 수 없게 됩니다. 메시지 보안은 메시지 전송에 사용되는 전송 방법에 관계없이 메시지를 보호하며 보안 컨텍스트는 메시지 내부에 직접 포함됩니다.

- 광범위한 자격 증명 및 클레임 지원. 메시지 보안은 SOAP 메시지 내에 모든 형식의 클레임을 전송할 수 있는 확장 가능 프레임워크인 WS-Security 사양을 따릅니다. 전송 보안과 달리, 사용할 수 있는 인증 메커니즘 또는 클레임 집합이 전송 기능에 따라 제한되지 않습니다. WCF message security includes multiple types of authentication and claim transmission and can be extended to support additional types as necessary. 그렇기 때문에 예를 들어 메시지 보안 없이는 페더레이션 자격 증명 시나리오를 수행할 수 없습니다. For more information about federation scenarios WCF supports, see [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).

## <a name="how-message-and-transport-security-compare"></a>메시지 보안과 전송 보안 비교

### <a name="pros-and-cons-of-transport-level-security"></a>전송 수준 보안의 장단점

전송 보안에는 다음과 같은 이점이 있습니다.

- 통신하는 당사자가 XML 수준 보안 개념을 이해할 필요가 없습니다. 이를 통해 HTTPS를 사용하여 통신을 보호하는 등의 경우에 상호 운용성을 향상시킬 수 있습니다.

- 일반적으로 성능이 향상되었습니다.

- 하드웨어 액셀러레이터를 사용할 수 있습니다.

- 스트리밍이 가능합니다.

 전송 보안에는 다음과 같은 단점이 있습니다.

- 홉 간에만 적용됩니다.

- 자격 증명 집합이 제한되어 확장할 수 없습니다.

- 전송에 종속됩니다.

### <a name="disadvantages-of-message-level-security"></a>메시지 수준 보안의 단점

메시지 보안에는 다음과 같은 단점이 있습니다.

- 성능

- 메시지 스트리밍을 사용할 수 없습니다.

- XML 수준 보안 메커니즘과 WS-Security 사양 지원을 구현해야 합니다. 이로 인해 상호 운용성이 저하될 수 있습니다.

## <a name="see-also"></a>참조

- [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [전송 보안](../../../../docs/framework/wcf/feature-details/transport-security.md)
- [방법: 전송 보안 및 메시지 자격 증명 사용](../../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)
- [Microsoft Patterns and Practices, Chapter 3: Implementing Transport and Message Layer Security](https://docs.microsoft.com/previous-versions/msp-n-p/ff647370(v=pandp.10))
