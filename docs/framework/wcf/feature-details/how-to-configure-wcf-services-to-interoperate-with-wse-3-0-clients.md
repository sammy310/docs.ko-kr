---
title: '방법: WSE 3.0 클라이언트와 상호 운용하도록 WCF 서비스 구성'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 5034744059e7ed87d4f8b41c6ae89d1af1bf0f56
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425397"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>방법: WSE 3.0 클라이언트와 상호 운용하도록 WCF 서비스 구성
Windows Communication Foundation (WCF) 서비스는 WCF 서비스가 Ws-addressing 사양의 2004 년 8 월 버전을 사용 하도록 구성 된 경우 Microsoft.NET (WSE) 클라이언트에 대 한 Web Services Enhancements 3.0과 유선 수준으로 호환 됩니다.  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>WCF 서비스가 WSE 3.0 클라이언트와 상호 운용하도록 하려면  
  
1. WCF 서비스에 대 한 사용자 지정 바인딩을 정의 합니다.  
  
     2004년 8월 버전의 WS-Addressing 사양을 메시지 인코딩에 사용하도록 지정하려면 사용자 지정 바인딩을 만들어야 합니다.  
  
    1. 자식 노드를 추가 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 에 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 서비스의 구성 파일입니다.  
  
    2. 추가 하 여 바인딩의 이름을 지정는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 에 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 설정는 `name` 특성입니다.  
  
    3. 인증 모드와 자식을 추가 하 여 WSE 3.0과 호환 되는 메시지 보안을 설정 하는 데 사용 되는 Ws-security 사양 버전 지정 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 에 [ \<바인딩 >](../../../../docs/framework/misc/binding.md)합니다.  
  
         인증 모드를 설정 하려면 설정 합니다 `authenticationMode` 특성을 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)합니다. 인증 모드는 대체로 WSE 3.0의 턴키 보안 어설션에 해당합니다. 다음 표에서 WSE 3.0에서 턴키 보안 어설션이 wcf에서 인증 모드를 매핑합니다.  
  
        |WCF 인증 모드|WSE 3.0 턴키 보안 어설션|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         \* 주요 차이점 중 하나는 `mutualCertificate10Security` 및 `mutualCertificate11Security` 턴키 보안 어설션은 WSE은 SOAP 메시지 보안을 사용 하는 Ws-security 사양 버전이 있습니다. `mutualCertificate10Security`에는 WS-Security 1.0이 사용되는 반면, `mutualCertificate11Security`에는 WS-Security 1.1이 사용됩니다. WCF, Ws-security 사양 버전에 지정 됩니다는 `messageSecurityVersion` 특성을 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)합니다.  
  
         SOAP 메시지 보안에 사용 되는 Ws-security 사양 버전을 설정 하려면 설정 합니다 `messageSecurityVersion` 특성을 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)합니다. WSE 3.0과 상호 운용하려면 `messageSecurityVersion` 특성의 값을 <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>으로 설정합니다.  
  
    4. 2004 년 8 월 버전의 Ws-addressing 사양 추가 하 여 WCF에 의해 사용 되도록 지정는 [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) 설정의 `messageVersion` 해당 값 <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>합니다.  
  
        > [!NOTE]
        >  SOAP 1.2를 사용할 경우에는 `messageVersion` 특성을 <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>로 변경합니다.  
  
2. 서비스에서 사용자 지정 바인딩이 사용되도록 지정합니다.  
  
    1. 설정 합니다 `binding` 특성을 [ \<끝점 >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) 요소를 `customBinding`입니다.  
  
    2. 설정를 `bindingConfiguration` 특성을 [ \<끝점 >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) 요소에 지정 된 값를 `name` 특성을 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 사용자 지정 바인딩입니다.  
  
## <a name="example"></a>예제  
 다음은 `Service.HelloWorldService`에서 사용자 지정 바인딩을 사용하여 WSE 3.0 클라이언트와 상호 운용하도록 지정하는 코드 예제입니다. 사용자 지정 바인딩에서는 교환되는 메시지를 인코딩하는 데 2004년 8월 버전의 WS-Addressing과 WS-Security 1.1을 사용하도록 지정합니다. 메시지 보안은 <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> 인증 모드를 통해 이루어집니다.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        behaviorConfiguration="ServiceBehavior"   
        name="Service.HelloWorldService">  
        <endpoint binding="customBinding" address=""  
          bindingConfiguration="ServiceBinding"  
          contract="Service.IHelloWorld"></endpoint>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="ServiceBinding">  
          <security authenticationMode="AnonymousForCertificate"  
                  messageProtectionOrder="SignBeforeEncrypt"  
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"  
                  requireDerivedKeys="false">  
          </security>  
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">  
        <serviceCredentials>  
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>  
        </serviceCredentials>  
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [방법: 시스템 제공 바인딩 사용자 지정](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
