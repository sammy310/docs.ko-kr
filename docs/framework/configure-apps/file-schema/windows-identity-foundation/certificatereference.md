---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 6c9c77f96ff6032de43d9b5a257bc0796a19b858
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667381"
---
# <a name="certificatereference"></a>\<certificateReference>
찾기 및 인증서 저장소에서 X.509 인증서의 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<serviceCertificate>  
\<certificateReference>  
  
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
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|storeName|X.509 인증서 저장소의 이름입니다. 기본값은 "My"입니다. 선택 사항입니다.|  
|storeLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 인증서 저장소의 위치를 지정 하는 값입니다. 기본값은 "LocalMachine"입니다. 선택 사항입니다.|  
|x509FindType|<xref:System.Security.Cryptography.X509Certificates.X509FindType> 를 실행 해야 하는 검색의 유형을 지정 하는 값입니다. 기본값은 "FindBySubjectDistinguishedName"입니다. 선택 사항입니다.|  
|findValue|X.509 인증서 저장소에서 검색할 값입니다. 선택 사항입니다.|  
|isChainIncluded|인증서 체인을 사용 하 여 유효성 검사를 수행할지 여부를 지정 합니다. 기본값은 "true"; 유효성 검사 인증서 체인을 사용 하 여 수행 됩니다. 선택 사항입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|암호화 및 토큰 암호 해독에 사용 되는 인증서를 구성 합니다.|  
  
## <a name="remarks"></a>설명  
 `<certificateReference>` 요소 찾기 및 인증서 저장소에서 X.509 인증서의 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다. 자식 요소로 지정 된 경우는 `<serviceCertficate>` 요소를 암호화 및 토큰 암호 해독에 사용 되는 X.509 인증서의 위치 및 인증 설정을 지정 합니다. 합니다 `<certificateReference>` 에서 요소가 표시 되는 <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 클래스입니다.
