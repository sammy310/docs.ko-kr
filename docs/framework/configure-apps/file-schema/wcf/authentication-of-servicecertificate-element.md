---
title: <authentication> <serviceCertificate> 요소
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: b96d53312d672eebd67de82f69cd9a0a2b5bd22e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117771"
---
# <a name="authentication-of-servicecertificate-element"></a>\<인증 >의 \<serviceCertificate > 요소
SSL/TLS 협상을 사용하여 가져온 서비스 인증서를 인증하기 위해 클라이언트 프록시에서 사용하는 설정을 지정합니다.  
  
 \<system.ServiceModel>  
\<behaviors>  
endpointBehaviors 섹션  
\<behavior>  
\<clientCredentials>  
\<serviceCertificate>  
\<authentication>  
  
## <a name="syntax"></a>구문  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|customCertificateValidatorType|문자열. 사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.|  
|certificateValidationMode|자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다. `Custom`으로 설정되면 customCertificateValidator도 지정해야 합니다. 기본값은 `ChainTrust`입니다.|  
|revocationMode|CRL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다. 기본값은 `Online`입니다.|  
|trustedStoreLocation|시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다. 서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다. 에 대 한 유효성 검사를 수행 합니다 **신뢰할 수 있는 사용자** 지정한 저장소 위치에 저장 합니다. 기본값은 `CurrentUser`입니다.|  
  
## <a name="customcertificatevalidator-attribute"></a>customCertificateValidator 특성  
  
|값|설명|  
|-----------|-----------------|  
|문자열|형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.|  
  
## <a name="certificatevalidationmode-attribute"></a>certificateValidationMode 특성  
  
|값|설명|  
|-----------|-----------------|  
|열거형|다음 값 중 하나입니다. None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.<br /><br /> 자세한 내용은 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.|  
  
## <a name="revocationmode-attribute"></a>revocationMode 특성  
  
|값|설명|  
|-----------|-----------------|  
|열거형|다음 값 중 하나입니다. NoCheck, Online, 오프 라인입니다.<br /><br /> 자세한 내용은 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.|  
  
## <a name="trustedstorelocation-attribute"></a>trustedStoreLocation 특성  
  
|값|설명|  
|-----------|-----------------|  
|열거형|다음 값 중 하나입니다. LocalMachine 또는 CurrentUser입니다. 기본값은 CurrentUser입니다. 시스템 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 LocalMachine에 있습니다. 사용자 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 CurrentUser에 있습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 구성 요소의 `certificateValidationMode` 특성은 인증서를 인증하는 데 사용되는 신뢰 수준을 지정합니다. 기본적으로 수준은 `ChainTrust`로 설정되며 이는 각 인증서가 체인 맨 위의 신뢰할 수 있는 인증 기관에서 종료되는 인증서 계층 구조에 있어야 함을 지정합니다. 이 모드가 가장 안전한 모드입니다. 또한 값을 `PeerOrChainTrust`로 설정할 수 있으며, 이는 자체 발급된 인증서(신뢰 피어)가 신뢰 체인에 있는 인증서와 함께 수락됨을 지정합니다. 자체 발급 인증서를 신뢰할 수 있는 기관에서 구입할 필요 없기 때문에 클라이언트 및 서비스를 개발 및 디버깅하는 경우 이 값이 사용됩니다. 클라이언트를 배포하는 경우 `ChainTrust` 값을 대신 사용합니다. 또한 값을 `Custom` 또는 `None`으로 설정할 수 있습니다. `Custom` 값을 사용하려면 `customCertificateValidator` 특성을 인증서의 유효성을 검사하는 데 사용된 어셈블리 및 형식으로 설정해야 합니다. 사용자 지정 유효성 검사기를 직접 만들려면 추상 X509CertificateValidator 클래스에서 상속해야 합니다. 자세한 내용은 [방법: 사용자 지정 인증서 유효성 검사기를 사용 하는 서비스 만들기](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)합니다.  
  
 `revocationMode` 특성은 해지를 위해 인증서를 검사하는 방법을 지정합니다. 기본값은 `online`이며, 이는 인증서가 해지를 위해 자동으로 검사됨을 나타냅니다. 자세한 내용은 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 작업을 수행합니다. 도메인 이름이 끝점과 통신할 때 사용 하도록 클라이언트에 대 한 서비스 인증서를 먼저 지정 `www.contoso.com` HTTP 프로토콜을 통해. 그런 다음 인증 중에 사용되는 해지 모드 및 저장소 위치를 지정합니다.  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
     <add targetUri="http://www.contoso.com"
          findValue="www.contoso.com"
          storeLocation="LocalMachine"
          storeName="Root"
          x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)
- [클라이언트에 보안 설정](../../../../../docs/framework/wcf/securing-clients.md)
- [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
