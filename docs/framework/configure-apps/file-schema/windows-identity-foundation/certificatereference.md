---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152816"
---
# <a name="certificatereference"></a>\<인증서 참조>
인증서 저장소에서 X.509 인증서를 찾고 유효성을 검사하는 데 사용되는 설정을 지정합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.서비스>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<페더레이션구성>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<서비스인증서>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<인증서 참조>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|storeName|X.509 인증서 저장소 이름입니다. 기본값은 "My"입니다. (선택 사항)|  
|storeLocation|X.509 인증서 저장소의 위치를 지정하는 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 값입니다. 기본값은 "로컬Machine"입니다. (선택 사항)|  
|x509FindType|실행할 <xref:System.Security.Cryptography.X509Certificates.X509FindType> 검색 유형을 지정하는 값입니다. 기본값은 "FindBySubject고유이름"입니다. (선택 사항)|  
|findValue|X.509 인증서 저장소에서 검색할 값입니다. (선택 사항)|  
|isChainIncluded|인증서 체인을 사용하여 유효성 검사를 수행할지 여부를 지정합니다. 기본값은 "true"입니다. 유효성 검사는 인증서 체인을 사용하여 수행됩니다. (선택 사항)|  
  
### <a name="child-elements"></a>자식 요소  
 None  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<서비스인증서>](servicecertificate.md)|토큰을 암호화하고 해독하는 데 사용되는 인증서를 구성합니다.|  
  
## <a name="remarks"></a>설명  
 요소는 `<certificateReference>` 인증서 저장소에서 X.509 인증서를 찾고 유효성을 검사하는 데 사용되는 설정을 지정합니다. `<serviceCertificate>` 요소의 자식 요소로 지정하면 토큰을 암호화하고 해독하는 데 사용되는 X.509 인증서의 위치 및 확인 설정을 지정합니다. 합니다 `<certificateReference>` 에서 요소가 표시 되는 <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 클래스입니다.
