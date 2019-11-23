---
title: <message>의 <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 75101744-eed8-4d61-91f4-5fc4473a21f2
ms.openlocfilehash: aef03634ed6156d3a7e052ccdbde35fdfda99cc3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736735"
---
# <a name="message-of-wsdualhttpbinding"></a>\<메시지 > \<wsDualHttpBinding >
[\<wsDualHttpBinding >](wsdualhttpbinding.md)에 대 한 메시지 수준 보안을 정의 합니다.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;[ **\<system.servicemodel >를**](system-servicemodel.md) &nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsDualHttpBinding >** ](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**security >** ](security-of-wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**메시지 >**  
  
## <a name="syntax"></a>구문  
  
```xml  
<message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
         negotiateServiceCredential="Boolean"
         algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
</message>
```  
  
## <a name="type"></a>형식  
 <xref:System.ServiceModel.MessageSecurityOverHttp>  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|Description|  
|---------------|-----------------|  
|algorithmSuite|(선택 사항) 메시지 암호화 및 키 래핑 알고리즘을 설정합니다. 알고리즘과 키 크기는 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 클래스로 결정됩니다. 이러한 알고리즘은 WS-SecurityPolicy(Security Policy Language) 사양에 지정된 알고리즘에 매핑됩니다.<br /><br /> 다음은 사용 가능한 값입니다. 기본값은 `Basic256`입니다.|  
|clientCredentialType|(선택 사항) 보안 모드를 사용하여 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식이 `Message`임을 지정합니다. 다음은 사용 가능한 값입니다. 기본값은 `Windows`입니다.<br /><br /> 이 특성은 <xref:System.ServiceModel.MessageCredentialType> 형식입니다.|  
|negotiateServiceCredential|(선택 사항) 서비스 자격 증명이 클라이언트에서 out of band 방식으로 제공되는지 아니면 협상 프로세스를 통해 서비스에서 클라이언트로 전달되는지를 지정하는 부울 값입니다. 이러한 협상이 이루어진 후에는 일반적인 메시지 교환이 수행됩니다.<br /><br /> `clientCredentialType` 특성이 없음, 사용자 이름 또는 인증서와 같은 경우이 특성을 `false`로 설정 하면 서비스 인증서를 대역 외 클라이언트에서 사용할 수 있고 클라이언트에서 [\<serviceCredentials >](servicecredentials.md) 서비스 동작의 서비스 인증서 ( [\<serviceCertificate >](servicecertificate-of-servicecredentials.md)사용)를 지정 해야 함을 의미 합니다. 이 모드는 WS-Trust 및 WS-SecureConversation을 구현하는 SOAP 스택과 상호 운용될 수 있습니다.<br /><br /> `ClientCredentialType` 특성이 `Windows`로 설정된 경우 이 특성을 `false`로 설정하면 Kerberos 기반 인증이 지정됩니다. 이것은 클라이언트와 서비스가 동일한 Kerberos 도메인에 속해야 함을 의미합니다. 이 모드는 Kerberos 토큰 프로필(OASIS WSS TC에서 정의) 그리고 WS-Trust 및 WS-SecureConversation을 구현하는 SOAP 스택과 상호 운용될 수 있습니다. 이 특성이 `true`일 경우 SOAP 메시지를 통한 SPNego 교환을 터널링하는 .NET SOAP 협상이 수행됩니다.<br /><br /> 기본값은 `true`입니다.|  
  
## <a name="algorithmsuite-attribute"></a>algorithmSuite 특성  
  
|값|Description|  
|-----------|-----------------|  
|Basic128|Aes128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.|  
|Basic192|Aes192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.|  
|Basic256|Aes256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.|  
|Basic256Rsa15|메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.|  
|Basic192Rsa15|메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.|  
|TripleDes|TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.|  
|Basic128Rsa15|메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.|  
|TripleDesRsa15|TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.|  
|Basic128Sha256|메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.|  
|Basic192Sha256|메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.|  
|Basic256Sha256|메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.|  
|TripleDesSha256|메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.|  
|Basic128Sha256Rsa15|메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.|  
|Basic192Sha256Rsa15|메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.|  
|Basic256Sha256Rsa15|메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.|  
|TripleDesSha256Rsa15|메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType 특성  
  
|값|Description|  
|-----------|-----------------|  
|없음|이를 통해 서비스와 익명 클라이언트가 상호 작용할 수 있습니다. 서비스 쪽에서는 서비스가 클라이언트 자격 증명을 요구하지 않음을 의미하고 클라이언트 쪽에서는 클라이언트가 클라이언트 자격 증명을 제공하지 않음을 의미합니다.|  
|Windows|Windows 자격 증명의 인증된 컨텍스트에서 SOAP 교환을 수행할 수 있습니다. `negotiateServiceCredential` 특성이 `true`로 설정되면 SSPI 협상 또는 Kerberos(상호 운용 가능 표준)가 수행됩니다.|  
|UserName|서비스에서 UserName 자격 증명을 사용하여 클라이언트를 인증하도록 요구할 수 있습니다. WCF에서는 암호 다이제스트를 보내거나 암호를 사용 하 고 메시지 보안에 이러한 키를 사용 하 여 키를 파생 없습니다. 따라서 WCF는 사용자 이름 자격 증명을 사용할 때 전송에 보안을 적용 합니다. 이 자격 증명 모드에서는 상호 운용이 가능한 교환 또는 `negotiateServiceCredential` 특성을 기반으로 하는 상호 운용이 불가능한 협상이 수행됩니다.|  
|인증서|서비스에서 인증서를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다. 메시지 보안 모드가 사용되고 `negotiateServiceCredential` 특성이 `false`로 설정되면 서비스 인증서를 사용하여 클라이언트를 구축해야 합니다.|  
|IssuedToken|일반적으로 보안 토큰 서비스가 발급하는 사용자 지정 토큰을 지정합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 None.  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<security>](security-of-wsdualhttpbinding.md)|[\<wsDualHttpBinding >](wsdualhttpbinding.md)의 보안 기능을 정의 합니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSDualHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>
- <xref:System.ServiceModel.MessageSecurityOverHttp>
- [서비스 및 클라이언트에 보안 설정](../../../wcf/feature-details/securing-services-and-clients.md)
- [바인딩](../../../wcf/bindings.md)
- [시스템 제공 바인딩 구성](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
