---
title: <ws2007FederationHttpBinding>의 <security> 요소
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: b85c54c6507313522286e0c66504cfd0c8afb2b0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738728"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a>\<ws2007FederationHttpBinding의 \<security > 요소 >
[\<ws2007FederationHttpBinding >](ws2007federationhttpbinding.md) 요소의 보안 설정을 정의 합니다.  
  
[ **\<configuration>** ](../configuration-element.md)\
[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; \
&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**보안 >**  
  
## <a name="syntax"></a>구문  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`mode`|(선택 사항) 적용 되는 보안 유형을 지정 합니다. 기본값은 `Message`여야 합니다. 이 특성은 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 형식입니다.|  
  
## <a name="mode-attribute"></a>mode 특성  
  
|값|설명|  
|-----------|-----------------|  
|없음|SOAP 메시지는 전송 중에는 안전 하지 않습니다.|  
|메시지|SOAP 메시지 보안을 사용 하 여 무결성, 기밀성, 서버 인증 및 클라이언트 인증을 제공 합니다. 기본적으로 본문은 암호화 되 고 서명 됩니다. 인증서를 사용하여 서비스를 구성해야 합니다. 클라이언트 인증은 보안 토큰 서비스에 의해 클라이언트에 발급 된 토큰을 기반으로 합니다.|  
|TransportWithMessageCredential|HTTPS를 사용하여 무결성, 기밀성 및 서버 인증을 제공합니다. 인증서를 사용하여 서비스를 구성해야 합니다. 클라이언트 인증은 SOAP 메시지 보안을 통해 제공 되며 보안 토큰 서비스가 클라이언트에 발급 한 토큰을 기반으로 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<message >](message-of-ws2007httpbinding.md)|메시지 수준 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 형식입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<binding >](bindings.md)|[\<wsDualHttpBinding >](wsdualhttpbinding.md)의 모든 바인딩 기능을 정의 합니다.|  
  
## <a name="see-also"></a>참조

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [방법: WSFederationHttpBinding 만들기](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [서비스 및 클라이언트에 보안 설정](../../../wcf/feature-details/securing-services-and-clients.md)
- [자격 증명 형식 선택](../../../wcf/feature-details/selecting-a-credential-type.md)
- [바인딩](../../../wcf/bindings.md)
- [시스템 제공 바인딩 구성](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding >](bindings.md)
