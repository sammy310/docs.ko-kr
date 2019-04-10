---
title: <security> / <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: acb4d04663d841a9b494153caa180855959c145e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206514"
---
# <a name="security-of-netmsmqbinding"></a>\<보안 >의 \<netMsmqBinding >
MSMQ 바인딩에 대한 보안 설정을 정의합니다. 이 클래스는 전송 또는 SOAP 보안의 사용 여부 그리고 보안이 사용된다면 어떤 인증 모드 및 보호 수준을 사용하는지를 지정합니다.  
  
 \<system.ServiceModel>  
\<bindings>  
\<netMsmqBinding>  
\<binding>  
\<security>  
  
## <a name="syntax"></a>구문  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|모드|무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -None. 이렇게 하면 보안이 해제 합니다.<br />-전송 합니다. 보호 및 인증이 전송에 의해 제공 됩니다. 이는 두 큐 관리자 간의 메시지 보안에 적용됩니다. 응용 프로그램과 큐 관리자 간에는 보안이 제공되지 않습니다. 기존 Msmq 응용 프로그램이 이러한 보안 모드 형식과 동일한 기능입니다.<br />-메시지: 종단 간 응용 프로그램 보안을 지정합니다. 전송 계층에는 보안이 제공되지 않습니다. 이는 다른 표준 바인딩에서 제공하는 보안과 유사합니다.<br />-모두: 전송과 SOAP 메시징 계층에서 보안을 제공합니다. 두 수준 모두에서 동일한 자격 증명이 필요합니다.<br /><br /> 기본값은 Transport입니다. 이 특성은 <xref:System.ServiceModel.NetMsmqSecurityMode> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|SOAP 메시지 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement> 형식입니다.|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|MSMQ 전송의 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|바인딩|바인딩 요소를 [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [바인딩](../../../../../docs/framework/wcf/bindings.md)
- [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
- [WCF의 큐](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
