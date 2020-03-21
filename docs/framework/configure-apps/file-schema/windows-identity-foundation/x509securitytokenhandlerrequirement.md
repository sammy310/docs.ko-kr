---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152452"
---
# <a name="x509securitytokenhandlerrequirement"></a>\<x509보안토큰처리기>
클래스 또는 파생 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 클래스에 대한 선택적 구성을 제공합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>추가**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509보안토큰처리기>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
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
|certificateValidationMode|X.509 인증서에 사용할 유효성 검사 모드를 지정하는 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 값입니다. 기본값은 "피어로체인트러스트"입니다.|  
|mapToWindows|들어오는 UPN 클레임을 사용하여 토큰 처리기가 유효성 검사 토큰을 Windows 계정에 매핑할지 여부를 지정합니다. 기본값은 "false"입니다.|  
|revocationMode|X.509 인증서에 사용할 해지 모드를 지정하는 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 값입니다. 기본값은 "온라인"입니다.|  
|trustedStoreLocation|X.509 인증서 저장소를 지정하는 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 값입니다. 기본값은 "로컬Machine"입니다.|  
|인증서유효성 검사자|에서 파생되는 사용자 <xref:System.IdentityModel.Selectors.X509CertificateValidator>지정 형식입니다. 특성이 `certificateValidationMode` "사용자 지정"인 경우 이 유형의 인스턴스가 발급자 인증서 유효성 검사에 사용됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
 None  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<>추가](add.md)|지정된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가합니다.|  
  
## <a name="example"></a>예제  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
