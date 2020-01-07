---
title: 웹 서비스 프로토콜 상호 운용성 가이드
ms.date: 03/30/2017
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
ms.openlocfilehash: 1b949880b3ebbaf121b79a958d17cf5708affcf3
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636148"
---
# <a name="web-services-protocols-interoperability-guide"></a>웹 서비스 프로토콜 상호 운용성 가이드

WCF (Windows Communication Foundation)는 수많은 웹 서비스 프로토콜을 구현 합니다. 이러한 프로토콜의 대부분에는 구현자가 결정하는 여러 가지 옵션과 확장 지점이 포함되어 있습니다. 이 항목에서는 WCF에서 구현 하는 웹 서비스 프로토콜의 목록을 제공 합니다. 이 단원의 다른 항목에서는 지원되는 각 프로토콜의 구현에 대해 자세히 설명합니다.

## <a name="web-services-protocols-implemented-by-wcf"></a>WCF에서 구현 하는 웹 서비스 프로토콜

WCF는 계약 기능을 통해 채널 및 웹 서비스 응용 프로그램 프로토콜을 통해 WS (웹 서비스) 인프라 프로토콜을 지원 합니다. 애플리케이션 프로토콜의 상호 운용은 XSD(XML 스키마 설명 언어) 1.0과 WSDL(웹 서비스 기술 언어) 1.1을 통해 가능합니다.

인프라 프로토콜 상호 운용성은 WS-* 사양에서 제공됩니다. WCF 채널은 다양 한 WS\* 인프라 프로토콜에 대 한 지원을 제공 합니다. WCF 채널은 바인딩 요소를 사용 하 여 구성 됩니다. 다음 표에는 다양 한 WCF 바인딩 요소에서 구현 하는 WS\* 인프라 프로토콜의 전체 목록이 포함 되어 있습니다.

<xref:System.ServiceModel.Channels.HttpTransportBindingElement>는 다음 표의 사양을 지원합니다.

|사양/문서|링크|
|-----------------------------|----------|
|HTTP 1.1|[RFC 2616](https://www.rfc-editor.org/rfc/rfc2616.txt)|
|SOAP 1.1 HTTP 바인딩|[SOAP (Simple Object Access Protocol) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), 섹션 7|
|SOAP 1.2 HTTP 바인딩|[SOAP 버전 1.2 Part 2: Adjuncts (Second Edition)](https://www.w3.org/TR/soap12-part2/), Section 7|

<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> 및 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>는 다음 표의 사양을 지원합니다.

|사양/문서|링크|
|-----------------------------|----------|
|XML|[XML(Extensible Markup Language) (XML) 1.0 (4 번째 버전)](https://www.w3.org/TR/REC-xml/)|
|SOAP 1.1|[SOAP (Simple Object Access Protocol) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)|
|SOAP 1.2 Core|[SOAP 버전 1.2 1 부: 메시징 프레임 워크 (두 번째 버전)](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)|
|WS-Addressing 2004/08|[웹 서비스 주소 지정 (WS-ADDRESSING)](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)|
|W3C Web Services Addressing 1.0 - Core|[웹 서비스 주소 지정 1.0-Core](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509/)|
|W3C Web Services Addressing 1.0 - SOAP 바인딩|[웹 서비스 주소 지정 1.0-SOAP 바인딩](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509/)|
|W3C Web Services Addressing 1.0 - WSDL 바인딩*|[웹 서비스 주소 지정 1.0-WSDL 바인딩](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)|
|W3C Web Services Addressing 1.0 Metadata|[웹 서비스 주소 지정 1.0-메타 데이터](https://www.w3.org/TR/ws-addr-metadata/)|
|WSDL SOAP1.1 바인딩|[WSDL (웹 서비스 기술 언어) 1.1](https://www.w3.org/TR/wsdl/)|
|WSDL SOAP1.2 바인딩|[SOAP 1.2 용 WSDL 1.1 바인딩 확장](https://www.w3.org/Submission/wsdl11soap12/)|

<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>는 다음 표의 사양을 지원합니다.

|사양/문서|링크|
|-----------------------------|----------|
|XOP|[XML-이진 최적화 패키징](https://www.w3.org/TR/xop10/)|
|MTOM + SOAP1.2 바인딩|[SOAP 메시지 전송 최적화 메커니즘](https://www.w3.org/TR/soap12-mtom/)|
|MTOM SOAP 1.1 바인딩|[MTOM 1.0에 대 한 SOAP 1.1 바인딩](https://www.w3.org/Submission/soap11mtom10/)|
|MTOM WS-PolicyAssertions|[MTOM Serialization 정책 어설션 (MTOMPolicy)](https://www.w3.org/Submission/WS-MTOMPolicy/)|

<xref:System.ServiceModel.Channels.SecurityBindingElement>는 다음 표의 사양을 지원합니다.

|사양/문서|링크|
|-----------------------------|----------|
|WSS: SOAP Message Security 1.0|[Web Services Security: SOAP 메시지 보안 1.0](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)|
|WSS: Username Token Profile 1.0|[Web Services Security UsernameToken Profile 1.0](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf)<br /><br /> Password/@Type= PasswordText 필요 (기본값)|
|WSS: X.509 Token Profile 1.0|[Web Services Security x.509 인증서 토큰 프로필](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf)|
|WSS: SAML 1.1 Token Profile 1.0|[Web Services Security: SAML 토큰 프로필](https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf)|
|WSS: SOAP Message Security 1.1|[Web Services Security: SOAP 메시지 보안 1.1](https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf)|
|WSS Username Token Profile 1.1|[Web Services Security UsernameToken Profile 1.1](https://www.oasis-open.org/committees/download.php/16782/wss-v1.1-spec-os-UsernameTokenProfile.pdf)<br /><br /> 암호 기반 키 파생을 구현하지 않음<br /><br /> Password/@Type= PasswordText 필요 (기본값)|
|WSS: X509 Token Profile 1.1|[Web Services Security x.509 Certificate Token Profile 1.1](https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf)|
|WSS: Kerberos Token Profile 1.1|[Web Services Security Kerberos 토큰 프로필 1.1](https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf)|
|WSS: SAML 1.1 Token Profile 1.1|[Web Services Security SAML 토큰 프로필 1.1](https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf)|
|WS-Secure Conversation|[웹 서비스 보안 대화 언어](https://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)|
|WS-Trust 1.4|[웹 서비스 신뢰 언어](https://docs.oasis-open.org/ws-sx/ws-trust/200802)|
|WS-SecurityPolicy 2005/07|[웹 서비스 보안 대화 언어](https://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)<br /><br /> OASIS WS-SX Technical Committee에 제출된 오류에 따라 수정됨<br /><br /> [ws-federation 메시지](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html)|
|WS-ReliableMessaging 1.1|[Reliable Messaging 프로토콜 버전 1.1](reliable-messaging-protocol-version-1-1.md)|

<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>는 다음 표의 사양을 지원합니다.

|사양/문서|링크|
|-----------------------------|----------|
|WS-Coordination|[웹 서비스 조정](https://docs.microsoft.com/previous-versions/ms951231(v=msdn.10))|
|WS-AtomicTransaction|[웹 서비스 원자성 트랜잭션](https://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf)|

<xref:System.ServiceModel.Description.MetadataExporter>, <xref:System.ServiceModel.Description.MetadataImporter>, <xref:System.ServiceModel.Description.WsdlExporter>, <xref:System.ServiceModel.Description.WsdlImporter> 및 <xref:System.ServiceModel.Description.MetadataResolver> 클래스는 다음과 같은 메타데이터 사양을 지원합니다.

- [XML 스키마 파트 1: 구조 두 번째 버전](https://www.w3.org/TR/xmlschema-1/)

- [XML 스키마 파트 2: 데이터 형식 Second Edition](https://www.w3.org/TR/xmlschema-2/)

- [WSDL 1.1](https://www.w3.org/TR/wsdl/)

- [WS 정책 1.2](https://www.w3.org/Submission/2006/SUBM-WS-Policy-20060425/)

- [WS 정책 1.5](https://www.w3.org/TR/ws-policy/)

- [WS-Ws-policyattachment 1.2](https://www.w3.org/Submission/2006/SUBM-WS-PolicyAttachment-20060425/)

- [WS-MetadataExchange 1.1](https://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)

- [메타 데이터 검색에 대 한 WS Transfer 가져오기](https://www.w3.org/Submission/2006/SUBM-WS-Transfer-20060315/)

또한 다음과 같은 상호 운용성 프로필은 WCF에서 구현 됩니다.

- [기본 프로필 1.1](http://www.ws-i.org/Profiles/BasicProfile-1.1-2004-08-24.html)

- [단순 SOAP 바인딩 1.0](http://www.ws-i.org/Profiles/SimpleSoapBindingProfile-1.0-2004-08-24.html)

- [기본 보안 프로필 1.0 작업 초안](http://www.ws-i.org/Profiles/BasicSecurityProfile-1.0-2006-03-29.html)

## <a name="see-also"></a>참조

- [시스템 제공 상호 운용성 바인딩에서 지원하는 웹 서비스 프로토콜](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [메시징 프로토콜](messaging-protocols.md)
- [데이터 계약 스키마 참조](data-contract-schema-reference.md)
- [WSDL 및 정책](wsdl-and-policy.md)
- [보안 프로토콜](security-protocols.md)
- [Reliable Messaging 프로토콜 버전 1.0](reliable-messaging-protocol-version-1-0.md)
- [Reliable Messaging 프로토콜 버전 1.1](reliable-messaging-protocol-version-1-1.md)
- [트랜잭션 프로토콜](transaction-protocols.md)
- [컨텍스트 교환 프로토콜](context-exchange-protocol.md)
