---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152634"
---
# <a name="samlsecuritytokenrequirement"></a>\<samlSecurity토큰요구 사항>
이러한 클래스 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 중 하나의 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스, 클래스 또는 파생 클래스에 대한 구성을 제공합니다. 클래스로 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 표시됩니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>추가**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurity토큰>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|mapToWindows|들어오는 UPN 클레임을 사용하여 토큰 처리기가 유효성 검사 토큰을 Windows 계정에 매핑할지 여부를 지정합니다. 기본값은 "false"입니다.|  
|발급자인증서 갱신 모드|X.509 인증서에 사용할 해지 모드를 지정하는 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 값입니다. 기본값은 "온라인"입니다.|  
|발급자인증서유효성 검사모드|X.509 인증서에 사용할 유효성 검사 모드를 지정하는 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 값입니다. 기본값은 "피어로체인트러스트"입니다.|  
|발급자인증서신뢰할 수 있는 스토어위치|X.509 인증서 저장소를 지정하는 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 값입니다. 기본값은 "로컬Machine"입니다.|  
|발행자인증서유효성 검사자|에서 파생되는 사용자 <xref:System.IdentityModel.Selectors.X509CertificateValidator>지정 형식입니다. 특성이 `issuerCertificateValidationMode` "사용자 지정"인 경우 이 유형의 인스턴스가 발급자 인증서 유효성 검사에 사용됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<이름 클레임 유형>](nameclaimtype.md)|속성을 지정하는 클레임 유형을 <xref:System.Security.Principal.IIdentity.Name%2A> 설정합니다.|  
|[\<역할 클레임 유형>](roleclaimtype.md)|토큰 처리기의 <xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 메서드에 의해 반환 되는 개체컬렉션에서 역할 형식 클레임을 정의 하는 클레임 형식을 지정 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<>추가](add.md)|지정된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가합니다.|  
  
## <a name="remarks"></a>설명  
 `<samlSecurityTokenRequirement>` 요소는 개체 모델의 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 클래스로 표시되며 또는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>에서 `SamlSecurityTokenRequirement` 속성을 구성하는 데 사용됩니다.  
  
## <a name="example"></a>예제  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
