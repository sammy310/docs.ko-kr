---
title: <basicHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: f1e166bec2254ed6d2c306eaccfa13e9fba1d70d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118055"
---
# <a name="security-of-basichttpbinding"></a>\<보안 >의 \<basicHttpBinding >
보안 기능을 정의 합니다 [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)합니다.  
  
 \<system.ServiceModel>  
\<bindings>  
\<basicHttpBinding>  
\<binding>  
\<security>  
  
## <a name="syntax"></a>구문  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|모드|선택 사항입니다. 사용되는 보안 형식을 지정합니다. 기본값은 `None`입니다. 이 특성은 <xref:System.ServiceModel.BasicHttpSecurityMode> 형식입니다.|  
  
## <a name="mode-attribute"></a>mode 특성  
  
|값|설명|  
|-----------|-----------------|  
|없음|-메시지 전송 하는 동안 보안이 유지 되지 됩니다.|  
|전송|HTTPS 전송을 사용하여 보안이 제공됩니다. SOAP 메시지는 HTTPS를 사용하여 보호됩니다. 이 서비스는 서비스의 X.509 인증서를 사용하여 클라이언트에 인증됩니다. 클라이언트는 제공된 ClientCredentialType을 사용하여 인증됩니다. 참조 된 [ \<전송 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)합니다.|  
|메시지|SOAP 메시지 보안을 사용하여 보안이 제공됩니다. 기본적으로 본문에는 암호화 및 서명이 수행됩니다. 이 바인딩에서는 클라이언트에 out of band 방식으로 서버 인증서가 제공되어야 합니다. 이 바인딩의 유효한 `ClientCredentialType`은 `Certificate`뿐입니다.|  
|TransportWithMessageCredential|전송 보안에 의해 무결성, 기밀성 및 서버 인증이 제공됩니다. 클라이언트 인증은 SOAP 메시지 보안에 의해 제공됩니다. 이 모드는 사용자가 사용자 이름/암호를 사용하여 인증되며 메시지 전송 보호를 위한 기존의 HTTP 배포가 있는 경우에 적합합니다.|  
|TransportCredentialOnly|이 모드는 메시지 무결성 및 기밀성을 제공하지 않으나 http 기반 클라이언트 인증을 제공합니다. 이 모드는 주의해서 사용해야 합니다. 전송 보안 (예: IPSec) 다른 방법으로 제공 되 고 WCF 인프라에서 클라이언트 인증만 제공 하는 환경에서는 사용 해야 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|기본 HTTP 서비스에 대한 전송 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.HttpTransportSecurity>에 해당합니다.|  
|[\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|기본 HTTP 서비스에 대한 메시지 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.BasicHttpMessageSecurity>에 해당합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|바인딩|바인딩 요소를 [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)합니다.|  
  
## <a name="remarks"></a>설명  
 기본적으로 SOAP 메시지의 보안이 유지되지 않고 클라이언트가 인증되지 않습니다. 이 요소를 사용하면 `basicHttpBinding` 요소에 대한 추가 보안 설정을 구성할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [자격 증명 형식 선택](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [바인딩](../../../../../docs/framework/wcf/bindings.md)
- [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
