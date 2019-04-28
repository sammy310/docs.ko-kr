---
title: <knownCertificates>의 <add>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 3eb5bf74f909e6036154b7f5f7c6181b09fefbff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704702"
---
# <a name="add-of-knowncertificates"></a>\<추가 >의 \<knownCertificates >
알려진 인증서 컬렉션에 X.509 인증서를 추가합니다.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceCredentials>  
\<issuedTokenAuthentication>  
\<knownCertificates>  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|findValue|문자열. 검색할 값입니다.|  
|storeLocation|열거형입니다. 검색할 두 저장소 위치 중 하나입니다.|  
|storeName|열거형입니다. 검색할 시스템 저장소 중 하나입니다.|  
|x509FindType|열거형입니다. 검색할 인증서 필드 중 하나입니다.|  
  
## <a name="findvalue-attribute"></a>findValue 특성  
  
|값|설명|  
|-----------|-----------------|  
|문자열|이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다. 예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.|  
  
## <a name="x509findtype-attribute"></a>x509FindType 특성  
  
|값|설명|  
|-----------|-----------------|  
|열거형|값은 다음과 같습니다. FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, findbysubjectkeyidentifier가 있습니다.|  
  
## <a name="storelocation-attribute"></a>storeLocation 특성  
  
|값|설명|  
|-----------|-----------------|  
|열거형|CurrentUser 또는 LocalMachine입니다.|  
  
## <a name="storename-attribute"></a>storeName 특성  
  
|값|설명|  
|-----------|-----------------|  
|열거형|값은 다음과 같습니다. AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, 루트, TrustedPeople 및 TrustedPublisher 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|보안 토큰의 유효성을 검사하기 위해 STS(보안 토큰 서비스)에서 제공하는 X.509 인증서 컬렉션을 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 발급된 토큰 시나리오에는 3단계가 있습니다. 첫 번째 단계에서는 서비스에 액세스 하려는 클라이언트 라고 한 *보안 토큰 서비스*합니다. 보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML(Security Assertions Markup Language) 토큰이라는 클라이언트 토큰을 발급합니다. 클라이언트는 토큰을 통해 서비스에 반환됩니다. 서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다. 토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.  
  
 합니다 [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) 요소는 이러한 보안 토큰 서비스 인증서에 대 한 리포지토리입니다. 인증서를 추가 하려면 사용 합니다 [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)합니다. 삽입 된 [ \<추가 > 요소 \<knownCertificates > 요소](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) 다음 예와에서 같이 각 인증서에 대 한 합니다.  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다. 이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.  
  
 이 구성 요소를 사용 하 여 자세한 정보 뿐만 아니라 페더레이션된 서비스에 의해 인증 되어야 클라이언트에 대 한 필수 조건, 참조 [방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)합니다. 페더레이션된 시나리오에 대 한 자세한 내용은 참조 하세요. [페더레이션 및 발급 된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 모든 STS 인증서에 대해 리포지토리에 인증서를 추가합니다.  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)
- [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
