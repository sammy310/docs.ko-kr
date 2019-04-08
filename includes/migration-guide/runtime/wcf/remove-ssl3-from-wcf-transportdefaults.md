---
ms.openlocfilehash: 37d771305bb0a4a38eeac9713e8667d158962174
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "57788894"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a>WCF TransportDefaults에서 Ssl3 제거

|   |   |
|---|---|
|세부 정보|전송 보안 및 자격 증명 유형의 인증서를 지원하는 NetTcp를 사용할 경우 SSL 3 프로토콜은 더 이상 보안 연결을 협상하는 데 사용되는 기본 프로토콜이 아닙니다. 대부분의 경우 TLS 1.0이 항상 NetTcp에 대한 프로토콜 목록에 포함되어 있으므로 기존 앱에는 영향을 주지 않습니다. 모든 기존 클라이언트에서는 TLS 1.0 이상을 사용하여 연결을 협상할 수 있습니다.|
|제안 해결 방법|Ssl3이 필요한 경우 다음 구성 메커니즘 중 하나를 사용하여 협상된 프로토콜 목록에 Ssl3을 추가합니다.<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[\<netTcpBinding>의 \<transport>](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li>[&lt;customBinding&gt;의 &lt;sslStreamSecurity&gt; 섹션](~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</li></ul>|
|범위|Microsoft Edge|
|버전|4.6.2|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|

