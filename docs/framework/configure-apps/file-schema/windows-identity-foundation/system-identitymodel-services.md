---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 9728f3caee4dba367e4fc4a3e68213b1055cc3d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793785"
---
# <a name="systemidentitymodelservices"></a>\<system.identityModel.services>
Ws-federation 프로토콜을 사용 하 여 인증에 대 한 구성 섹션입니다.  
  
 \<system.identityModel.services>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|구성 설정이 포함 된 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP 모듈입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
 없음  
  
## <a name="remarks"></a>설명  
 추가 된 `<system.identityModel.services>` SAM 및 WSFAM에 대 한 설정을 제공 하려면 응용 프로그램의 구성 파일 섹션입니다.  
  
> [!IMPORTANT]
>  사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 클레임 인증 관리자 코드에서 클레임 기반 액세스 제어를 제공 하는 클래스 (<xref:System.Security.Claims.ClaimsAuthorizationManager>) 및 권한 부여 결정 하는 데 사용 되는 정책을 통해 구성 됩니다는 `<identityConfiguration>` 암시적 또는 명시적으로 참조 하는 요소는 `<federationConfiguration>` 이 섹션에 있는 요소입니다. 자세한 내용은 참조 하세요. 합니다 **주의** 아래 합니다 [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소.  
  
 `<system.identityModel.services>` 섹션은 표현 된 <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> 클래스입니다. 자식 컬렉션인 `<federationConfiguration>` 섹션에 구성 요소에서 표시 됩니다는 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 XML에 추가 하는 방법을 보여 줍니다는 `<system.identityModel.services>` 구성 파일 섹션입니다. 둘 다에 대 한 섹션 선언을 추가 해야 합니다 `<system.identityModel.services>` 섹션 및 `<system.identityModel>` 섹션입니다. (추가 하는 경우는 `<system.identityModel.services>` 섹션도 추가 해야에 대 한 선언을 합니다 `<system.identityModel>` 기본값 되도록 섹션 `<identityConfiguration>` 필요한 경우 런타임에서 섹션을 만들 수 있습니다.) 선언 섹션에 추가한 후 아래에 있는 페더레이션된 인증 설정을 구성할 수 있습니다는 `<system.identityModel.services>` 요소입니다.  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"   
        issuer="http://localhost:15839/wsFederationSTS/Issue"   
        realm="http://localhost:50969/" reply="http://localhost:50969/"   
        requireHttps="false"   
        signOutReply="http://localhost:50969/SignedOutPage.html"   
        signOutQueryString="Param1=value2&Param2=value2"   
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```
