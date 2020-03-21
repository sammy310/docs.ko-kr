---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: bcd8e00b770517e3faff011b4acee08ebdc5a0df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152738"
---
# <a name="federationconfiguration"></a>\<federationConfiguration>
WS-페더레이션 프로토콜을 통해 페더레이션 인증을 사용하는 경우 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM)을 구성합니다. 클레임 기반 <xref:System.Security.Claims.ClaimsAuthorizationManager> 액세스 제어를 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 제공 하도록 또는 클래스를 사용 하는 경우를 구성 합니다. <xref:System.IdentityModel.Services.ClaimsPrincipalPermission>  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.서비스>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<페더레이션구성>**  
  
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
  
|attribute|Description|  
|---------------|-----------------|  
|name|이 페더레이션 구성 요소의 이름입니다. 이 특성은 주로 향후 프로토콜에 대한 확장성 지점을 제공합니다. (선택 사항)|  
|ID구성 이름|[ \<idConfiguration에](identityconfiguration.md) 지정된 ID 구성 섹션의 이름은 사용할 구성 요소구성>. 이 특성을 지정하지 않으면 기본 ID 구성 섹션이 사용됩니다. (선택 사항)|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<쿠키핸들러>](cookiehandler.md)|SAM에서 사용하는 쿠키 처리기를 구성합니다. (선택 사항)|  
|[\<서비스인증서>](servicecertificate.md)|토큰을 암호화하고 해독하는 데 사용되는 인증서를 구성합니다. (선택 사항)|  
|[\<ws페더레이션>](wsfederation.md)|WS-페더레이션 인증 모듈(WSFAM)을 구성합니다. (선택 사항)|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<system.identityModel.서비스>](system-identitymodel-services.md)|WS-페더레이션 프로토콜을 사용하여 인증하기 위한 구성 섹션입니다.|  
  
## <a name="remarks"></a>설명  
 \<페더레이션구성> 요소는 다음과 같은 두 가지 시나리오에서 설정을 제공합니다.  
  
- 수동 웹 응용 프로그램에서 WS-페더레이션을 사용하는 경우 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 요소에는 (SFAM) 및 (SAM)을 구성하는 설정이 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 포함되어 있습니다. 또한 보안 토큰 처리기 및 인증서및 클레임 권한 부여 관리자 및 클레임 인증 관리자와 같은 구성 요소를 구성하는 데 사용할 ID 구성을 참조합니다.  
  
- <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 클래스를 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 사용하여 코드에서 클레임 기반 액세스 제어를 제공하는 경우 요소는 권한 부여 결정을 내리는 데 사용되는 클레임 권한 부여 관리자 및 정책을 구성하는 ID 구성을 참조합니다. 수동 웹 시나리오가 아닌 시나리오에서도 마찬가지입니다. 예를 들어 WCF(Windows 통신 재단) 응용 프로그램 또는 웹 기반이 아닌 응용 프로그램입니다. 응용 프로그램이 수동 웹 응용 프로그램이 아닌 경우 element에서 `<federationConfiguration>` [ \<](claimsauthorizationmanager.md) 참조하는 ID 구성의 클레임AuthorizationManager>요소(및 해당 자식 정책 요소)가 적용되는 유일한 설정입니다. 다른 특성은 모두 무시됩니다.  
  
 시나리오에 관계없이 런타임은 기본 페더레이션 구성을 로드합니다. 동작은 다음과 같이 정의됩니다.  
  
1. 요소가 없는 `<federationConfiguration>` 경우 런타임은 페더레이션 구성을 만들고 기본값으로 채웁니다. 이 기본 페더레이션 구성은 기본 ID 구성을 참조합니다.  
  
2. 단일 `<federationConfiguration>` 요소가 있는 경우 명명 또는 이름 없는 여부에 관계없이 기본 페더레이션 구성입니다. 해당 `identityConfiguration` 특성을 지정하면 명명된 ID 구성이 참조됩니다. 그렇지 않으면 기본 ID 구성이 참조됩니다.  
  
3. 명명되지 `<federationConfiguration>` 않은 요소가 있으면 기본 페더레이션 구성입니다. 해당 `identityConfiguration` 특성을 지정하면 명명된 ID 구성이 참조됩니다. 그렇지 않으면 기본 ID 구성이 참조됩니다.  
  
4. 명명된 `<federationConfiguration>` 요소가 여러 개 있고 `<federationConfiguration>` 명명되지 않은 요소가 없는 경우 예외가 throw됩니다.  
  
 일반적으로 단일 `<federationConfiguration>` 섹션만 정의됩니다. 이 섹션은 기본 페더레이션 구성입니다. 고유한 이름의 `<federationConfiguration>` 여러 요소를 지정할 수 있습니다. 그러나 이 경우 명명되지 않은 구성이 아닌 페더레이션 구성을 로드하려면 에 대한 처리기를 제공해야 합니다. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>처리기 내부의 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> 속성을 구성 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 파일의 적절한 `<federationConfiguration>` 요소의 값으로 초기화된 개체로 설정합니다.  
  
 합니다 `<federationConfiguration>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> 클래스입니다. 구성 개체 자체는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 클래스로 표시됩니다. 단일 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 인스턴스는 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> 속성에 설정되며 응용 프로그램에 대한 페더레이션 구성을 제공합니다.  
  
## <a name="example"></a>예제  
 다음 XML은 `<federationConfiguration>` WSFAM에 대한 설정을 지정하고 SAM에서 기본 쿠키 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 처리기(클래스의 인스턴스)를 사용할 수 있도록 지정하는 요소를 보여 주며.  
  
> [!WARNING]
> 이 예제에서는 HTTPS를 사용할 때 쿠키 처리기나 WSFAM이 필요하지 않습니다. `requireHttps` 이는 `<wsFederation>` 요소의 특성과 의 `requireSsl` `<cookieHandlerElement>` 특성이 다음과 `false`기 때문입니다. 이러한 설정은 보안 위험이 있을 수 있기 때문에 대부분의 프로덕션 환경에서는 권장되지 않습니다.  
  
```xml  
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
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [\<ID구성>](identityconfiguration.md)
