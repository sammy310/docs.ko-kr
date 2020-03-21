---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152506"
---
# <a name="systemidentitymodelservices"></a>\<system.identityModel.서비스>
WS-페더레이션 프로토콜을 사용하여 인증하기 위한 구성 섹션입니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel.서비스>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 None  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<페더레이션구성>](federationconfiguration.md)|(WSFAM) <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP 모듈을 구성하는 설정이 포함되어 있습니다.|  
  
### <a name="parent-elements"></a>부모 요소  
 None  
  
## <a name="remarks"></a>설명  
 SAM `<system.identityModel.services>` 및 WSFAM에 대한 설정을 제공하기 위해 응용 프로그램의 구성 파일에 섹션을 추가합니다.  
  
> [!IMPORTANT]
> <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 또는 클래스를 사용하여 코드에서 클레임 기반 액세스 제어를 제공하는 경우<xref:System.Security.Claims.ClaimsAuthorizationManager>권한 부여 결정을 내리는 데 사용되는 클레임 권한 `<identityConfiguration>` 부여 관리자() 및 정책은 `<federationConfiguration>` 이 섹션의 요소에서 암시적으로 또는 명시적으로 참조되는 요소를 통해 구성됩니다. 자세한 내용은 [ \<페더레이션구성>](federationconfiguration.md) 요소 아래의 **비고를** 참조하십시오.  
  
 섹션은 `<system.identityModel.services>` <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> 클래스로 표시됩니다. 섹션에 구성된 `<federationConfiguration>` 자식 요소의 컬렉션은 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> 클래스로 표시됩니다.  
  
## <a name="example"></a>예제  
 다음 XML에서는 구성 파일에 `<system.identityModel.services>` 섹션을 추가하는 방법을 보여 주며, 섹션을 추가하는 방법을 보여 주시면 됩니다. 먼저 `<system.identityModel.services>` 단면과 단면 모두에 대해 `<system.identityModel>` 단면 선언을 추가해야 합니다. 섹션을 추가할 `<system.identityModel.services>` 때 필요한 경우 런타임으로 기본 `<system.identityModel>` `<identityConfiguration>` 섹션을 만들 수 있도록 섹션에 대한 선언을 추가해야 합니다. 섹션 선언이 추가된 후 요소 아래에 페더레이션 인증 `<system.identityModel.services>` 설정을 구성할 수 있습니다.  
  
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
