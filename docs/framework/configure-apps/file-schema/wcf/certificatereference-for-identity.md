---
description: '에 대 한 자세한 <certificateReference> 정보: <identity>'
title: <identity>의 경우 <certificateReference>
ms.date: 03/30/2017
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
ms.openlocfilehash: 2c30e7ad035b560d766f3b5592af18210df53aad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639044"
---
# <a name="certificatereference-for-identity"></a>\<identity>의 경우 \<certificateReference>

X.509 인증서 유효성 검사의 설정을 지정합니다. 이 id를 사용 하 여 끝점에 연결 하는 WCF (secure Windows Communication Foundation) 클라이언트는 서버에서 제공 하는 클레임이이 id를 생성 하는 데 사용 된 id 클레임을 포함 하는지 확인 합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<certificateReference findValue="String"
                      isChainIncluded="Boolean"
                      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                      storeLocation="LocalMachine/CurrentUser"
                      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier">
</certificateReference>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|findValue|X.509 인증서 저장소에서 검색할 값을 지정합니다. 이 특성에 포함된 형식은 지정된 `X509FindType` 값의 요구 사항을 충족해야 합니다. 기본값은 빈 문자열입니다.|  
|isChainIncluded|유효성 검사에서 인증서 체인을 사용하는지 여부를 지정하는 부울 값입니다.|  
|storeLocation|클라이언트가 서버 인증서의 유효성을 검사하는 데 사용할 수 있는 인증서 저장소 위치를 지정합니다.<br /><br /> 유효한 값은 다음과 같습니다.<br /><br /> -LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.<br />-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.<br /><br /> 기본값은 LocalMachine입니다.<br /><br /> 이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 형식입니다.|  
|storeName|열려는 X.509 인증서 저장소의 이름을 지정합니다.<br /><br /> 유효한 값은 다음과 같습니다.<br /><br /> -AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.<br />-AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.<br />-CertificateAuthority: 중간 Ca에 대 한 인증서 저장소입니다.<br />-허용 안 함: 해지 된 인증서의 인증서 저장소입니다.<br />-My: 개인 인증서용 인증서 저장소입니다.<br />-Root: 신뢰할 수 있는 루트 Ca 용 인증서 저장소입니다.<br />-개인 사용자: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.<br />-신뢰할 수 있는 게시자: 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.<br /><br /> 기본값은 My입니다.<br /><br /> 이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreName> 형식입니다.|  
|X509FindType|실행할 X.509 검색의 유형을 지정합니다. `findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.<br /><br /> 유효한 값은 다음과 같습니다.<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />- FindByIssuerName<br />- FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />- FindByTimeValid<br />- FindByTimeNotYetValid<br />- FindByTemplateName<br />- FindByApplicationPolicy<br />- FindByCertificatePolicy<br />- FindByExtension<br />- FindByKeyUsage<br />- FindBySubjectKeyIdentifier<br /><br /> 기본값은 FindBySubjectDistinguishedName입니다.<br /><br /> 이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509FindType> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<identity>](identity.md)|한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 설정을 지정합니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Configuration.CertificateReferenceElement>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
