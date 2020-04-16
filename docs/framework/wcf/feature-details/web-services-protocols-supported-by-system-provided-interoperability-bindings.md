---
title: 시스템 제공 상호 운용성 바인딩에서 지원하는 웹 서비스 프로토콜
ms.date: 03/30/2017
helpviewer_keywords:
- WS-protocols
- Web services protocols
- Windows Communication Foundation, Web service protocols
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
ms.openlocfilehash: 25efda74d205a36332a801e91ddc508796f7df5d
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463984"
---
# <a name="web-services-protocols-supported-by-system-provided-interoperability-bindings"></a>시스템 제공 상호 운용성 바인딩에서 지원하는 웹 서비스 프로토콜
WCF(Windows 통신 재단)는 웹 서비스 사양으로 알려진 일련의 사양을 지원하는 웹 서비스와 상호 운용하도록 빌드됩니다. 상호 운용성 모범 사례에 대한 서비스 구성을 간소화하기 위해 WCF는 <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType>상호 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>운용 가능한 시스템 제공 바인딩 세 가지를 소개합니다. 구조화 된 정보 표준 (OASIS) 표준의 발전을 위한 조직과의 상호 운용성을 위해 WCF에는 상호 운용 가능한 시스템 제공 바인딩이 <xref:System.ServiceModel.WS2007HttpBinding?displayProperty=nameWithType>포함됩니다. 메타데이터 게시의 경우 WCF에는 상호 운용 가능한 시스템 제공 바인딩인 [ \<mexHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) 및 [ \<mexHttpsBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)두 개의 바인딩이 포함됩니다. 이 항목에서는 시스템에서 제공하는 상호 운용 가능한 바인딩이 지원하는 사양을 나열합니다.  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>basicHttpBinding, wsHttpBinding, ws2007HttpBinding 및 wsDualHttpBinding Bindings에서 지원하는 웹 서비스 프로토콜  
  
### <a name="all-bindings"></a>모든 바인딩  
 기본HttpBinding>, [ \<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)및 [ \<ws2007httpBinding 바인딩>](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) 바인딩은 다음 프로토콜을 지원합니다. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)  
  
> [!NOTE]
> 메타데이터 게시에 사용하는 바인딩에 대한 자세한 내용은 이 항목의 뒷부분에 나오는 "시스템 제공 메타데이터 바인딩" 단원을 참조하십시오.  
  
|범주|프로토콜|사양 및 사용|  
|--------------|--------------|-----------------------------|  
|전송|HTTP 1.1|[HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)<br /><br /> `BasicHttpBinding`, `WSHttpBinding` 및 `WS2007HttpBinding`은 HTTP 및 HTTPS 전송을 사용합니다.|  
|메시징|MTOM|[MTOM](https://www.w3.org/TR/soap12-mtom/)<br /><br /> `basicHttpBinding`, `wsHttpBinding` 및 `ws2007HttpBinding`은 MTOM(Message-Transmission Optimization Mechanism)을 지원합니다. 기본적으로 사용되지 않으며 MTOM을 사용하려면 `messageEncoding` 특성을 `"Mtom"`으로 설정하십시오.<br /><br /> 예:<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|메타데이터|WSDL 1.1|[WSDL 1.1](https://www.w3.org/TR/wsdl/)<br /><br /> WCF는 WSDL(웹 서비스 설명 언어)을 사용하여 서비스를 설명합니다.|  
|메타데이터|WS-Policy|[WS-Policy](https://www.w3.org/Submission/WS-Policy/)<br /><br /> WCF는 WS-Policy 사양을 도메인별 어설션과 함께 사용하여 서비스 요구 사항 및 기능을 설명합니다.|  
|메타데이터|WS-Policy 1.5|[WS-Policy 1.5](https://www.w3.org/TR/2007/CR-ws-policy-20070605/)<br /><br /> WCF는 WS-Policy 사양을 도메인별 어설션과 함께 사용하여 서비스 요구 사항 및 기능을 설명합니다.|  
|메타데이터|WS-PolicyAttachment|[WS-PolicyAttachment](http://specs.xmlsoap.org/ws/2004/09/policy/ws-policyattachment.pdf)<br /><br /> WCF는 WS-PolicyAttachment를 구현하여 WSDL(웹 서비스 설명 언어)의 다양한 범위에서 정책 식을 첨부합니다.|  
|메타데이터|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF는 Ws-MetadataExchange를 구현하여 XML 스키마, WSDL 및 WS 정책을 검색합니다.|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|범주|프로토콜|사양 및 사용|  
|--------------|--------------|-----------------------------|  
|메시징|SOAP 1.1|[SOAP 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)<br /><br /> Basic Profile 1.1에 따라 `basicHttpBinding` 요소는 SOAP 1.1 메시지 프로토콜을 구현합니다.|  
|보안|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)<br /><br /> 기본 보안 프로필에 따라 `basicHttpBinding` 요소는 사용자 이름/암호 및 X.509 기반 보안을 위해 WSS(Web Services Security) SOAP Message Security 1.0 사양을 구현합니다.<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|보안|WSS SOAP Message Security UsernameToken Profile 1.0|[WSS SOAP Message Security UsernameToken Profile 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|보안|WSS SOAP 메시지 보안 X.509 인증서 토큰 프로필 1.0|[WSS SOAP 메시지 보안 X.509 인증서 토큰 프로필 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding, ws2007HttpBinding 및 wsDualHttpBinding  
  
|범주|프로토콜|사양 및 사용|  
|--------------|--------------|-----------------------------|  
|메시징|SOAP 1.2|[주요 내용](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Messaging framework](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Adjuncts (including HTTP binding)](https://www.w3.org/TR/soap12-part2/)|  
|메시징|WS 주소 지정 2005/08|[Web Services Addressing 1.0 - Core](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://www.w3.org/TR/ws-addr-soap/)<br /><br /> `wsHttpBinding`, `ws2007HttpBinding` 및 `wsDualHttpBinding`은 W3C(World Wide Web Consortium) WS-Addressing 권장 사항을 구현하여 비동기 메시징, 메시지 상관 관계 및 전송 중립적 주소 지정 메커니즘을 사용할 수 있습니다.<br /><br /> WS-* 규격에서 WS-Addressing 헤더의 암호화를 허용하지만 WCF는 이를 지원하지 않습니다.|  
|메시징|WS-Addressing 1.0 - Metadata|[WS 주소 지정 1.0 메타데이터](https://www.w3.org/2007/05/addressing/metadata/) 이 프로토콜에 대 한 지원ServiceMetadata 동작에서 정책 버전을 설정 하 여 사용 됩니다-정책 버전 설정 1.2 (기본값), wsdl 설명WS-주소 지정 wsdl을 준수, 정책 버전 설정 1.5, wsdl 설명 ws-addressing 메타 데이터 와 일치 합니다.<br /><br /> WS-* 규격에서 WS-Addressing 헤더의 암호화를 허용하지만 WCF는 이를 지원하지 않습니다.|  
|보안|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)<br /><br /> `securityMode` 특성이 "wsSecurityOverHttp"(기본값)로 설정되어 있고 매개 변수가 `wsSecurity` 자식 요소를 사용하여 구성되어 있을 경우 사용합니다.<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|보안|WSS 비누 메시지 보안 사용자 이름토큰 프로필 1.1|[WSS SOAP Message Security UsernameToken Profile 1.0](https://www.oasis-open.org/committees/download.php/16782/wss-v1.1-spec-os-UsernameTokenProfile.pdf)<br /><br /> `wsSecurity` 요소의 `authenticationMode` 특성이 "Username"으로 설정된 경우 사용합니다.<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|보안|WSS SOAP Message Security X.509 Certificate Token Profile 1.1|[WSS SOAP Message Security X.509 Certificate Token Profile 1.1](https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf)<br /><br /> `wsSecurity` 요소의 `authenticationMode` 특성이 "Username", "Certificate" 또는 "None"으로 설정된 경우 메시지 보호를 위해 사용합니다. 또한 `wsSecurity` 요소의 `authenticationMode` 특성이 "Certificate"으로 설정된 경우 클라이언트 인증을 위해 이를 사용합니다.<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|보안|WSS SOAP Message Security Kerberos Token Profile 1.1|[WSS SOAP 메시지 보안 Kerberos 토큰 프로필 1.1](https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf)<br /><br /> `wsSecurity` 요소의 `authenticationMode` 특성이 "Windows"로 설정된 경우 인증 및 메시지 보호를 위해 사용합니다.<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|보안|WS-SecureConversation|[WS-SecureConversation](http://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)<br /><br /> `security/@mode` 특성이 "Message"로 설정되어 있고 `message/@establishSecurityContext` 특성이 "true"(기본값)로 설정된 경우 보안 세션을 제공하기 위해 사용합니다.|  
|보안|WS-Trust|[WS 트러스트](http://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf)<br /><br /> WS-SecureConversation에 의해 사용됩니다(위 참조).|  
|신뢰할 수 있는 메시징|WS-ReliableMessaging|[WS-ReliableMessaging](http://specs.xmlsoap.org/ws/2005/02/rm/ws-reliablemessaging.pdf)<br /><br /> `reliableSession` 사용을 위해 바인딩을 구성할 때 사용합니다.<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|트랜잭션|WS-AtomicTransaction|[WS-AtomicTransaction](http://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf)<br /><br /> 트랜잭션 관리자간 통신에 사용합니다. WCF 클라이언트와 서비스는 항상 로컬 트랜잭션 관리자를 사용합니다.|  
|트랜잭션|WS-Coordination|[WS-Coordination](https://docs.microsoft.com/previous-versions/ms951231(v=msdn.10))<br /><br /> `flowTransactions` 특성이 "Allowed" 또는 "Required"로 설정된 경우 트랜잭션 컨텍스트 이동을 위해 사용합니다.<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding 및 ws2007FederationHttpBinding  
 wsFederationHttpBinding>및 [ \<ws2007페더레이션>](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) 요소는 타사에서 클라이언트를 인증하는 데 사용되는 토큰을 발급하는 페더레이션 시나리오에 대한 지원을 제공하기 위해 도입됩니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) `wsHttpBinding`에서 사용하는 프로토콜과 함께 `wsFederationHttpBinding`에서 사용합니다.  
  
- 토큰 발급에 대한 `WS-Trust`입니다.  
  
- 가장 일반적으로 발급되는 토큰 형식에 대한 WSS SAML(Security Assertions Markup Language) Token Profile 1.0 및 1.1입니다.  
  
 예:  
  
```xml  
<wsFederationHttpBinding>  
  <binding name="myBinding">  
     <security mode="Message">  
       <message issuedKeyType="Symmetric"
                issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
         <issuerMetadata address =
         'http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex'/>  
       </message>  
     </security>  
  </binding>  
</wsFederationHttpBinding>  
```  
  
 자세한 내용은 [페더레이션](../../../../docs/framework/wcf/feature-details/federation.md) 을 참조하십시오.  
  
## <a name="system-provided-metadata-bindings"></a>시스템 제공 메타데이터 바인딩  
 다음 표에서는 <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType> 클래스에 의해 노출된, 시스템에서 제공하는 상호 운용 가능 메타데이터 바인딩에서 지원하는 프로토콜에 대해 설명합니다.  
  
### <a name="mexhttpbinding"></a>mexHttpBinding  
 mexHttpBinding>바인딩은 다음 프로토콜을 지원합니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) 이 바인딩 사용에 대한 자세한 내용은 [메타데이터 게시](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)를 참조하십시오.  
  
|범주|프로토콜|사양 및 사용|  
|--------------|--------------|-----------------------------|  
|전송|HTTP 1.1|[HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)|  
|메시징|SOAP 1.2|[주요 내용](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Messaging framework](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Adjuncts (including HTTP binding)](https://www.w3.org/TR/soap12-part2/)|  
|메시징|WS 주소 지정 2005/08|[Web Services Addressing 1.0 - Core](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://www.w3.org/TR/ws-addr-soap/)|  
|메타데이터|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF는 Ws-MetadataExchange를 구현하여 XML 스키마, WSDL 및 WS 정책을 검색합니다.|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 mexHttps바인딩>다음 프로토콜을 지원합니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md) 이 바인딩 사용에 대한 자세한 내용은 [메타데이터 게시](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)를 참조하십시오.  
  
|범주|프로토콜|사양 및 사용|  
|--------------|--------------|-----------------------------|  
|전송|HTTP 1.1|[HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)<br /><br /> 전송 보안을 사용합니다.|  
|메시징|SOAP 1.2|[주요 내용](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Messaging framework](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Adjuncts (including HTTP binding)](https://www.w3.org/TR/soap12-part2/)|  
|메시징|WS 주소 지정 2005/08|[Web Services Addressing 1.0 - Core](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://www.w3.org/TR/ws-addr-soap/)|  
|메타데이터|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF는 Ws-MetadataExchange를 구현하여 XML 스키마, WSDL 및 WS 정책을 검색합니다.|  
  
## <a name="see-also"></a>참조

- [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)
- [\<기본Http바인딩>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)
- [\<wsHttp바인딩>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
- [\<wsDualHttp바인딩>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)
- [\<멕스Https바인딩>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)
- [\<멕스Http바인딩>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)
