---
title: <serviceCertificate>of <clientCredentials> 요소
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399678"
---
# <a name="servicecertificate-of-clientcredentials-element"></a>\<serviceCertificate>of \<clientCredentials> 요소
클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<defaultCertificate>](defaultcertificate-element.md)|서비스 또는 STS가 협상 프로토콜을 통해 인증서를 제공하지 않을 때 사용할 X.509 인증서를 지정합니다.|  
|[\<scopedCertificates>](scopedcertificates-element.md)|인증에 대해 범위가 지정된 특정 서비스가 제공하는 X.509 인증서 컬렉션을 나타냅니다. 이 컬렉션은 일반적으로 연합 시나리오에서 보안 토큰 서비스에 대한 서비스 인증서를 지정하는 데 사용됩니다.|  
|[\<authentication>](authentication-of-servicecertificate-element.md)|클라이언트에 사용되는 서비스 인증서의 인증 동작을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|클라이언트가 서비스에 자신을 인증하는 데 사용되는 자격 증명을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 구성 요소는 SSL 인증을 사용하여 서비스에서 표시한 인증서의 유효성을 검사하기 위해 클라이언트에서 사용되는 설정을 지정합니다. 여기에는 메시지 보안을 사용하여 서비스에 보내는 메시지를 암호화하는 데 사용하기 위해 클라이언트에서 명시적으로 구성되는 서비스에 대한 인증서도 포함됩니다.  
  
 요소의 특성은 `serviceCertificate` 의 특성과 동일 합니다 [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md) .  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [보안 동작](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [클라이언트에 보안 설정](../../../wcf/securing-clients.md)
- [인증서 사용](../../../wcf/feature-details/working-with-certificates.md)
- [서비스 및 클라이언트에 보안 설정](../../../wcf/feature-details/securing-services-and-clients.md)
