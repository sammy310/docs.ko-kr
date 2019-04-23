---
title: WSE 3.0 웹 서비스를 WCF로 마이그레이션
ms.date: 03/30/2017
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
ms.openlocfilehash: a691e8f63e34f60f26d1a96a975dbe062bd59c96
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180611"
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>WSE 3.0 웹 서비스를 WCF로 마이그레이션
마이그레이션 WSE 3.0 웹 서비스를 Windows Communication Foundation (WCF)의 이점을 성능 향상된 등 지원 추가 전송, 추가 보안 시나리오 및 WS-* 사양입니다. WSE 3.0에서 WCF로 마이그레이션된 웹 서비스는 최대 200% ~ 400% 성능 향상을 경험할 수 있습니다. WCF에서 지 원하는 전송에 대 한 자세한 내용은 참조 하세요. [전송 선택](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)합니다. WCF를 지 원하는 시나리오의 목록을 참조 하세요 [일반적인 보안 시나리오](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)합니다. WCF에서 지원 되는 사양의 목록을 참조 하세요 [웹 서비스 프로토콜 상호 운용성 가이드](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md)합니다.  
  
 다음 섹션에서는 WSE 3.0 웹 서비스의 특정 기능을 WCF로 마이그레이션하는 방법에 지침을 제공 합니다.  
  
## <a name="general"></a>일반  
 WSE 3.0과 WCF 응용 프로그램에는 유선 수준의 상호 운용성 및 용어의 공통 집합을 포함 합니다. WSE 3.0과 WCF 응용 프로그램은 유선 수준의 상호 운용 가능한 WS-의 집합을 기반으로 * 사양을 모두 지원 합니다. WSE 3.0 또는 WCF 응용 프로그램을 개발 하는 경우 용어, 인증 모드와 WSE의 턴키 보안 어설션 이름과 같은 공통 집합이 있습니다.  
  
 WCF와 ASP.NET 간의 비슷한 점이 많지만 있더라도, WSE 3.0 프로그래밍 모델은 서로 다릅니다. WCF 프로그래밍 모델에 대 한 자세한 내용은 참조 하세요 [기본 프로그래밍 수명 주기](../../../../docs/framework/wcf/basic-programming-lifecycle.md)합니다.  
  
> [!NOTE]
>  WSE 웹 서비스를 WCF로 마이그레이션하려면 합니다 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구는 클라이언트를 생성 하는데 사용할 수 있습니다. 그러나 이 클라이언트에는 WCF 서비스의 시작 지점으로 사용할 수 있는 인터페이스와 클래스도 포함되어 있습니다. 생성되는 인터페이스에는 <xref:System.ServiceModel.OperationContractAttribute> 속성이 <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A>로 설정되어 계약의 멤버에 적용되는 `*` 특성이 있습니다. WSE 클라이언트가이 설정을 사용 하 여 웹 서비스를 호출 하면 예외가 throw 됩니다. **Web.Services3.ResponseProcessingException: WSE910: 응답 메시지를 처리 하는 동안 오류가 발생 했습니다. 내부 예외에서 오류를 찾을 수 있습니다 및**합니다. 이를 완화하려면 <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> 특성의 <xref:System.ServiceModel.OperationContractAttribute> 속성을 `null`처럼 `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`이 아닌 값으로 설정합니다.  
  
## <a name="security"></a>보안  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>정책 파일을 사용하여 WSE 3.0 웹 서비스 보안  
 WCF 서비스 구성 파일을를 사용 하 여 서비스를 보안 할 수 있습니다 하 고 그 메커니즘은 WSE 3.0 정책 파일과 유사 합니다. WSE 3.0에서 정책 파일을 사용하여 웹 서비스를 보호할 때 턴키 보안 어설션 또는 사용자 지정 정책 어설션을 사용합니다. 턴키 보안 어설션을 WCF 보안 바인딩 요소의 인증 모드에 밀접 하 게 매핑됩니다. 뿐만 아니라 WCF 인증 모드와 WSE 3.0 턴키 보안 어설션은 구조가 또는 마찬가지로 안전 하 게 유지 동일한 자격 증명 형식을 사용 하 여 메시지입니다. 예를 들어 합니다 `usernameForCertificate` WSE 3.0에서 턴키 보안 어설션에 매핑되는 `UsernameForCertificate` WCF 인증 모드입니다. 다음 코드 예제에는 최소한의 정책을 사용 하는 방식을 보여 줍니다 합니다 `usernameForCertificate` WSE 3.0에서 턴키 보안 어설션에 매핑되는 `UsernameForCertificate` WCF 사용자 지정 바인딩에 인증 모드입니다.  
  
 **WSE 3.0**  
  
```xml  
<policies>  
  <policy name="MyPolicy">  
    <usernameForCertificate messageProtectionOrder="SignBeforeEncrypt"  
                            requireDeriveKeys="true"/>  
  </policy>  
</policies>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <security authenticationMode="UserNameForCertificate"   
              messageProtectionOrder="SignBeforeEncrypt"  
              requireDerivedKeys="true"/>  
  </binding>  
</customBinding>  
```  
  
 WCF는 정책 파일에 지정 된 WSE 3.0 웹 서비스의 보안 설정을 마이그레이션하려면 사용자 지정 바인딩을 구성 파일에서 만들고 턴키 보안 어설션을 해당 인증 모드로 설정 해야 합니다. 또한 WSE 3.0 클라이언트가 서비스와 통신할 때 August 2004 WS-Addressing 사양을 사용하도록 사용자 지정 바인딩을 구성해야 합니다. 마이그레이션된 WCF 서비스가 WSE 3.0 클라이언트와 통신 하지 않아도 보안 패리티만 유지를 사용자 지정 바인딩을 만드는 대신 적절 한 보안 설정을 사용 하 여 WCF 시스템 정의 바인딩을 사용 하는 것이 좋습니다.  
  
 다음 표에서 WSE 3.0 정책 파일 및 WCF에 해당 하는 사용자 지정 바인딩 간의 매핑을 나열합니다.  
  
|WSE 3.0 턴키 보안 어설션|WCF 사용자 지정 바인딩 구성|  
|----------------------------------------|--------------------------------------|  
|\<usernameOverTransportSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate10Security / >|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<usernameForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<anonymousForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<kerberosSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate11Security / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Wcf에서 사용자 지정 바인딩을 만드는 방법에 대 한 자세한 내용은 참조 하세요. [사용자 지정 바인딩을](../../../../docs/framework/wcf/extending/custom-bindings.md)합니다.  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>응용 프로그램 코드를 사용하여 보안된 WSE 3.0 웹 서비스  
 WSE 3.0 또는 WCF를 사용 하는지 여부를 보안 요구 사항은 구성 대신 응용 프로그램 코드에서 지정할 수 있습니다. WSE 3.0에서 보안 요구 사항을 지정하려면 `Policy` 클래스에서 파생되는 클래스를 만든 다음 `Add` 메서드를 호출하여 요구 사항을 추가합니다. 코드에서 보안 요구 사항을 지정 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 정책 파일을 사용 하지 않고 웹 서비스를 보호](https://go.microsoft.com/fwlink/?LinkId=73747)합니다. WCF, 보안 요구 사항을 코드에서를 지정 하려면의 인스턴스를 만듭니다는 <xref:System.ServiceModel.Channels.BindingElementCollection> 클래스의 인스턴스를 추가 및는 <xref:System.ServiceModel.Channels.SecurityBindingElement> 에 <xref:System.ServiceModel.Channels.BindingElementCollection>. 보안 어설션 요구 사항은 <xref:System.ServiceModel.Channels.SecurityBindingElement> 클래스의 정적 인증 모드 도우미 메서드를 사용하여 설정됩니다. WCF를 사용 하 여 코드에서 보안 요구 사항을 지정 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md) 고 [방법: 지정된 된 인증 모드에 대 한 SecurityBindingElement 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)합니다.  
  
### <a name="wse-30-custom-policy-assertion"></a>WSE 3.0 사용자 지정 정책 어설션  
 WSE 3.0에는 SOAP 메시지를 보안하는 사용자 지정 정책 어설션과 SPAO 메시지를 보안하지 않는 사용자 지정 정책 어설션이 있습니다. WSE 3.0에서 파생 되는 SOAP 메시지 보안 정책 어설션을 `SecurityPolicyAssertion` 클래스 이며 WCF에서 같은 개념을 <xref:System.ServiceModel.Channels.SecurityBindingElement> 클래스입니다.  
  
 중요 한 참고 사항은 WSE 3.0 턴키 보안 어설션을 WCF 인증 모드의 하위 집합입니다. WSE 3.0에서 사용자 지정 정책 어설션을 만든 경우 해당 하는 WCF 인증 모드 있을 수 있습니다. 예를 들어 WSE 3.0에서 `UsernameOverTransport` 턴키 보안 어설션에 해당하는 CertificateOverTransport 보안 어설션을 제공하지는 않지만 클라이언트 인증을 위해 X.509 인증서를 사용합니다. 이 시나리오에 대 한 사용자 고유의 사용자 지정 정책 어설션을 정의한 경우 WCF 마이그레이션이 간단해 합니다. WCF 활용 정적 인증 모드 도우미 메서드는 WCF 구성를 수행할 수 있도록이 시나리오에서는 인증 모드를 정의<xref:System.ServiceModel.Channels.SecurityBindingElement>합니다.  
  
 SOAP 메시지를 보호 하는 사용자 지정 정책 어설션을에 해당 하는 WCF 인증 모드를 없는 경우에서 클래스를 파생 <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 또는 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>WCF 클래스 및 해당 바인딩 요소를 지정 합니다. 자세한 내용은 참조 하세요. [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)합니다.  
  
 참조는 SOAP 메시지를 보호 하지 않습니다 하는 사용자 지정 정책 어설션을 변환할 [필터링](../../../../docs/framework/wcf/feature-details/filtering.md) 및 샘플 [사용자 지정 메시지 인터셉터](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)합니다.  
  
### <a name="wse-30-custom-security-token"></a>WSE 3.0 사용자 지정 보안 토큰  
 사용자 지정 토큰을 만드는 WCF 프로그래밍 모델은 WSE 3.0과 다릅니다. WSE에서 사용자 지정 토큰을 만드는 방법에 대 한 자세한 내용은 참조 하세요. [Creating Custom Security Tokens](https://go.microsoft.com/fwlink/?LinkID=73750)합니다. Wcf에서 사용자 지정 토큰을 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 사용자 지정 토큰 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)합니다.  
  
### <a name="wse-30-custom-token-manager"></a>WSE 3.0 사용자 지정 토큰 관리자  
 사용자 지정 토큰 관리자를 만들기 위한 프로그래밍 모델은 WSE 3.0 WCF의 다른 합니다. 사용자 지정 토큰 관리자 및 사용자 지정 보안 토큰에 필요한 기타 구성 요소를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 사용자 지정 토큰 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)합니다.  
  
> [!NOTE]
>  사용자 지정을 만든 경우 `UsernameToken` 보안 토큰 관리자, WCF 사용자 지정 보안 토큰 관리자를 만드는 것 보다 인증 논리를 지정 하려면 간단한 메커니즘을 제공 합니다. 자세한 내용은 참조 하세요. [방법: 사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용 하 여](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)입니다.  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>MTOM 인코딩된 SOAP 메시지를 사용하는 WSE 3.0 웹 서비스  
 WSE 3 응용 프로그램을 같은 WCF 응용 프로그램 MTOM 메시지 인코딩을 구성에서 지정할 수 있습니다. 이 설정을 마이그레이션하려면 추가 합니다 [ \<mtomMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) 바인딩에 서비스에 대 한 합니다. 다음 코드 예제에서는 MTOM 인코딩을 지정 하는 방법을 WSE 3.0의 WCF에서이 해당 하는 서비스 하는 방법을 보여 줍니다.  
  
 **WSE 3.0**  
  
```xml  
<messaging>  
    <mtom clientMode="On"/>  
</messaging>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <mtomMessageEncoding/>  
  </binding>  
</customBinding>  
```  
  
## <a name="messaging"></a>메시징  
  
### <a name="wse-30-applications-that-use-the-wse-messaging-api"></a>WSE 메시징 API를 사용하는 WSE 3.0 응용 프로그램  
 WSE 메시징 API를 사용하여 클라이언트와 웹 서비스 간에 전달되는 XML에 직접 액세스할 수 있으면 "POX"(Plain Old XML)를 사용하도록 응용 프로그램을 변환할 수 있습니다. POX에 대 한 자세한 내용은 참조 하세요. [POX 응용 프로그램과 상호 운용](../../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md)합니다. WSE 메시징 API에 대 한 자세한 내용은 참조 하세요. [Sending and 받는 SOAP 메시지를 사용 하 여 WSE 메시징 API](https://go.microsoft.com/fwlink/?LinkID=73755)합니다.  
  
## <a name="transports"></a>전송  
  
### <a name="tcp"></a>TCP  
 기본적으로 WSE 3.0 클라이언트와 웹 서비스는 TCP 전송을 사용 하 여 SOAP 메시지를 보내는 WCF 클라이언트 및 웹 서비스 상호 운용 되지 않는 합니다. 이러한 비호환성은 성능상의 이유와 TCP 프로토콜에 사용된 프레이밍의 차이로 인한 것입니다. 그러나 WCF 샘플에는 WSE 3.0과 상호 운용 하는 사용자 지정 TCP 세션을 구현 하는 방법을 자세히 설명 합니다. 이 샘플에 대 한 세부 정보를 참조 하세요. [전송 합니다. WSE 3.0 TCP 상호 운용성](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md)합니다.  
  
 WCF 응용 프로그램에서 TCP 전송을 있는지를 지정 하려면 사용 합니다 [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)합니다.  
  
### <a name="custom-transport"></a>사용자 지정 전송  
 WCF에서 WSE 3.0 사용자 지정 전송에 해당 하는이 채널 확장 합니다. 채널 확장 만들기에 대 한 자세한 내용은 참조 하세요 [채널 계층 확장](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [기본 프로그래밍 수명 주기](../../../../docs/framework/wcf/basic-programming-lifecycle.md)
- [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)
- [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [방법: 지정된 된 인증 모드에 대 한 SecurityBindingElement 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
