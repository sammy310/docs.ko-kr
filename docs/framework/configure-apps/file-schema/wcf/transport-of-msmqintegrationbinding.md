---
title: <msmqIntegrationBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 03e6236d1e89f16a460860f5dffff19b7bed8a0a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169832"
---
# <a name="transport-of-msmqintegrationbinding"></a>\<msmqIntegrationBinding>의 \<transport>

메시지 큐 통합 전송을 위한 보안 설정을 정의합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|메시지가 MSMQ 전송에 의해 인증되는 방법을 지정합니다. 이 특성이 `None`으로 설정되면 `msmqProtectionLevel` 특성 값도 `None`으로 설정되어야 합니다.<br /><br /> 유효한 값은 다음과 같습니다.<br /><br /> -없음: 인증 하지 않습니다.<br />-WindowsDomain:이 인증 메커니즘은 Active Directory를 사용 하 여 메시지와 연결 된 SID에 대 한 x.509 인증서를 가져옵니다. 그런 다음 이 인증서는 사용자에게 큐에 대한 쓰기 권한이 있는지 확인하기 위해 큐의 ACL을 검사하는 데 사용됩니다.<br />-Certificate: 채널은 인증서 저장소에서 인증서를 가져옵니다.<br /><br /> 기본값은 WindowsDomain입니다. 이 특성은 <xref:System.ServiceModel.MsmqAuthenticationMode> 형식입니다.|  
|`msmqEncryptionAlgorithm`|메시지 큐 관리자 간에 메시지를 전송할 때 통신 중에 메시지 암호화에 사용할 알고리즘을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -RC4Stream<br />-AES<br /><br /> 기본값은 RC4Stream입니다. 이 특성은 <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 형식입니다.|  
|`msmqProtectionLevel`|메시지가 MSMQ 전송 수준에서 보호되는 방식을 지정합니다. 암호화는 메시지 무결성을 보장 하는 반면 EncryptAndSign는 메시지 무결성 및 부인 방지를 모두 보장 합니다. 즉, 메시지는 보낸 사람 으로부터 전송 되 고 보낸 사람은 보낸 사람입니다.<br /><br /> -유효한 값은 다음과 같습니다.<br />-없음: 보호 되지 않습니다.<br />-서명: 메시지가 서명 됩니다.<br />-EncryptAndSign: 메시지가 암호화 되 고 서명 됩니다.<br /><br /> 기본값은 Sign입니다. 이 특성은 ProtectionLevel 형식입니다.|  
|`msmqSecureHashAlgorithm`|-시그니처의 일부로 다이제스트를 계산 하는 데 사용할 알고리즘을 지정 합니다. 유효한 값은 다음과 같습니다.<br />-MD5<br />-SHA1<br />-SHA256<br />-SHA512<br /><br /> 기본값은 SHA1입니다. 이 특성은 <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 형식입니다.<br>MD5 및 s h a 1의 충돌 문제로 인해 s h a 1 이상을 권장 합니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|MSMQ 바인딩에 대한 보안 설정을 정의합니다.|  
  
## <a name="remarks"></a>설명  

 이 요소는 메시지 큐 통합 전송을 위한 보안 설정을 캡슐화합니다. 설정은 메시지 큐 통합 및 대기 중인 전송에서 모두 동일합니다. 이 요소를 사용하여 인증 모드, 암호화 알고리즘, 보안 해시 알고리즘 및 보호 수준을 설정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [서비스 및 클라이언트에 보안 설정](../../../wcf/feature-details/securing-services-and-clients.md)
- [바인딩하](../../../wcf/bindings.md)
- [시스템 제공 바인딩 구성](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
