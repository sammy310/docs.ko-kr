---
title: <serviceCertificate> <clientCredentials> 요소
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4fe196ef8737c7abde939e36c2bb7afd5a0d86b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145342"
---
# <a name="servicecertificate-of-clientcredentials-element"></a>\<serviceCertificate >의 \<clientCredentials > 요소
클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<clientCredentials>  
\<serviceCertificate>  
  
## <a name="syntax"></a>구문  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<defaultCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)|서비스 또는 STS가 협상 프로토콜을 통해 인증서를 제공하지 않을 때 사용할 X.509 인증서를 지정합니다.|  
|[\<scopedCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|인증에 대해 범위가 지정된 특정 서비스가 제공하는 X.509 인증서 컬렉션을 나타냅니다. 이 컬렉션은 일반적으로 연합 시나리오에서 보안 토큰 서비스에 대한 서비스 인증서를 지정하는 데 사용됩니다.|  
|[\<authentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)|클라이언트에 사용되는 서비스 인증서의 인증 동작을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|클라이언트가 서비스에 자신을 인증하는 데 사용되는 자격 증명을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 구성 요소는 SSL 인증을 사용하여 서비스에서 표시한 인증서의 유효성을 검사하기 위해 클라이언트에서 사용되는 설정을 지정합니다. 여기에는 메시지 보안을 사용하여 서비스에 보내는 메시지를 암호화하는 데 사용하기 위해 클라이언트에서 명시적으로 구성되는 서비스에 대한 인증서도 포함됩니다.  
  
 특성을 `serviceCertificate` 요소의 특성과 동일 합니다 [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [클라이언트에 보안 설정](../../../../../docs/framework/wcf/securing-clients.md)
- [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
