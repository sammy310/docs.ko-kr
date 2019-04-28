---
title: <serviceCredentials>의 <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
ms.openlocfilehash: 086b700b94198aa36e61289178ebbed75d33da98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670315"
---
# <a name="servicecertificate-of-servicecredentials"></a>\<serviceCertificate >의 \<serviceCredentials >
메시지 보안 모드를 사용하는 클라이언트에 대한 서비스를 인증하는 데 사용할 X.509 인증서를 지정합니다.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceCredentials>  
\<serviceCertificate>  
  
## <a name="syntax"></a>구문  
  
```xml  
<serviceCertificate findValue="String"
                    storeLocation="LocalMachine/CurrentUser"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`findValue`|X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다. 이 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다. 기본값은 빈 문자열입니다.|  
|`storeLocation`|클라이언트가 서버 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소 위치를 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.<br />-CurrentUser: 현재 사용자에 게 할당 하는 인증서 저장소입니다.<br /><br /> 기본값은 LocalMachine입니다.|  
|`storeName`|열려는 X.509 인증서 저장소의 이름을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.<br />-   AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.<br />-CertificatAuthority: 중간 Ca (인증 기관) 용 인증서 저장소입니다.<br />-허용 되지 않습니다. 해지 된 인증서용 인증서 저장소입니다.<br />-내: 개인 인증서용 인증서 저장소입니다.<br />-   Root: 신뢰할 수 있는 루트 Ca (인증 기관) 용 인증서 저장소입니다.<br />-TrustedPeople: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.<br />-   TrustedPublisher: 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.<br /><br /> 기본값은 My입니다.|  
|`x509FindType`|실행할 X.509 검색의 유형을 정의합니다. 유효한 값은 다음과 같습니다.<br /><br /> -   FindByThumbprint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> `findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.<br /><br /> 기본값은 FindBySubjectDistinguishedName입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<serviceCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 확인 관련 설정을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 요소를 사용하여 메시지 보안 모드를 사용하는 클라이언트에 대한 서비스를 인증하는 데 사용할 X.509 인증서를 지정합니다. 주기적으로 갱신되는 인증서를 사용하는 경우 지문이 변경됩니다. 이러한 경우 인증서를 동일한 주체 이름으로 다시 발급할 수 있기 때문에 주체 이름으로 `x509FindType`을 사용합니다.  
  
 요소를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 클라이언트 자격 증명 값 지정](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>
- [방법: 클라이언트 자격 증명 값 지정](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)
- [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
