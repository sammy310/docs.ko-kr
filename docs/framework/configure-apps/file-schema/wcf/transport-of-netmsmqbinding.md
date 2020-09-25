---
title: <netMsmqBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 84a5437de851ecdb96d0463ec574186ba5f91d9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203880"
---
# <a name="transport-of-netmsmqbinding"></a>\<netMsmqBinding>의 \<transport>

전송 보안 설정을 정의합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|msmqAuthenticationMode|메시지가 MSMQ 전송에 의해 인증되는 방법을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -없음: 인증 하지 않습니다.<br />-WindowsDomain:이 인증 메커니즘은 Active Directory를 사용 하 여 메시지와 연결 된 보안 식별자에 대 한 x.509 인증서를 검색 합니다. 그런 다음 이 인증서는 사용자에게 큐에 대한 쓰기 권한이 있는지 확인하기 위해 큐의 ACL을 검사하는 데 사용됩니다.<br />-Certificate: 채널은 인증서 저장소에서 인증서를 검색 합니다.<br /><br /> 기본값은 `WindowsDomain`입니다.<br /><br /> 이 특성이 `None`으로 설정되면 `msmqProtectionLevel` 특성도 `None`으로 설정해야 합니다. 이 특성은 <xref:System.ServiceModel.MsmqAuthenticationMode> 형식입니다.|  
|msmqEncryptionAlgorithm|메시지 큐 관리자 간에 메시지를 전송할 때 통신 중에 메시지 암호화에 사용할 알고리즘을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -RC4Stream<br />-AES<br />-기본값은 `RC4Stream` 입니다. 이 특성은 <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 형식입니다.|  
|msmqProtectionLevel|메시지가 MSMQ 전송 수준에서 보호되는 방식을 지정합니다. 암호화는 메시지 무결성을 보장하지만 서명 및 암호화는 메시지 무결성 및 부인 없음을 보장합니다. 즉, 메시지는 보낸 사람이 보낸 메시지 이며 보낸 사람이 보낸 메시지입니다. 유효한 값은 다음과 같습니다.<br /><br /> -없음: 보호 되지 않습니다.<br />-서명: 메시지가 서명 됩니다.<br />-EncryptAndSign: 메시지가 암호화 되 고 서명 됩니다.<br />-기본값은 `Sign` 입니다.|  
|msmqSecureHashAlgorithm|메시지 다이제스트를 계산하는 데 사용할 해시 알고리즘을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -MD5<br />-SHA1<br />-SHA256<br />-SHA512<br /><br /> 기본값은 `SHA1`입니다. 이 특성은 <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 형식입니다.<br>MD5 및 s h a 1의 충돌 문제로 인해 s h a 1 이상을 권장 합니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|대기 중인 전송에 대한 전송 보안 설정을 정의합니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [WCF의 큐](../../../wcf/feature-details/queues-in-wcf.md)
- [서비스 및 클라이언트에 보안 설정](../../../wcf/feature-details/securing-services-and-clients.md)
- [바인딩하](../../../wcf/bindings.md)
- [시스템 제공 바인딩 구성](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
