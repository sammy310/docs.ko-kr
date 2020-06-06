---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: bcd8e00b770517e3faff011b4acee08ebdc5a0df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152738"
---
# \<federationConfiguration>
<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>Ws-federation 프로토콜을 통해 페더레이션된 인증을 사용 하는 경우 (wsfam) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM)을 구성 합니다. <xref:System.Security.Claims.ClaimsAuthorizationManager>또는 클래스를 사용 하 여 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 클레임 기반 액세스 제어를 제공 하는 경우를 구성 합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<federationConfiguration>**  
  
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
  
|attribute|Description|  
|---------------|-----------------|  
|name|이 페더레이션 구성 요소의 이름입니다. 이 특성은 주로 이후 프로토콜에 대 한 확장성 지점을 제공 합니다. 선택 사항입니다.|  
|identityConfigurationName|사용할 요소에 지정 된 id 구성 섹션의 이름입니다 [\<identityConfiguration>](identityconfiguration.md) . 이 특성을 지정 하지 않으면 기본 id 구성 섹션이 사용 됩니다. 선택 사항입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|SAM에서 사용 하는 쿠키 처리기를 구성 합니다. 선택 사항입니다.|  
|[\<serviceCertificate>](servicecertificate.md)|토큰을 암호화 하 고 해독 하는 데 사용 되는 인증서를 구성 합니다. 선택 사항입니다.|  
|[\<wsFederation>](wsfederation.md)|WS-FEDERATION 인증 모듈 (WSFAM)을 구성 합니다. 선택 사항입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|WS-FEDERATION 프로토콜을 사용 하는 인증에 대 한 구성 섹션입니다.|  
  
## <a name="remarks"></a>설명  
 \<federationConfiguration>요소는 다음과 같은 두 가지 시나리오에서 설정을 제공 합니다.  
  
- 수동 웹 응용 프로그램에서 WS-FEDERATION을 사용 하는 경우 요소에는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) 및 (SAM)을 구성 하는 설정이 포함 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 됩니다. 또한 보안 토큰 처리기 및 인증서를 구성 하는 데 사용 되는 id 구성과 클레임 권한 부여 관리자 및 클레임 인증 관리자와 같은 구성 요소를 참조 합니다.  
  
- 또는 클래스를 사용 하 여 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 코드에서 클레임 기반 액세스 제어를 제공 하는 경우 요소는 권한 부여를 결정 하는 데 사용 되는 클레임 권한 부여 관리자 및 정책을 구성 하는 id 구성을 참조 합니다. 이는 수동 웹 시나리오가 아닌 시나리오 에서도 마찬가지입니다. 예를 들어 WCF (Windows Communication Foundation) 응용 프로그램 또는 웹 기반이 아닌 응용 프로그램이 있습니다. 응용 프로그램이 수동 웹 응용 프로그램이 아닌 경우 [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) 요소가 참조 하는 id 구성의 요소 및 자식 정책 요소 (있는 경우) `<federationConfiguration>` 만 적용 됩니다. 다른 특성은 모두 무시됩니다.  
  
 시나리오에 관계 없이 런타임은 기본 페더레이션 구성을 로드 합니다. 동작은 다음과 같이 정의 됩니다.  
  
1. 요소가 없는 경우 `<federationConfiguration>` 런타임은 페더레이션 구성을 만들고 기본값을 채웁니다. 이 기본 페더레이션 구성에서는 기본 id 구성을 참조 합니다.  
  
2. 단일 요소가 있으면 `<federationConfiguration>` 이름이 지정 되었는지 아니면 이름이 지정 되지 않은 경우에 관계 없이 기본 페더레이션 구성입니다. 해당 `identityConfiguration` 특성이 지정 된 경우 명명 된 id 구성이 참조 되 고, 그렇지 않으면 기본 id 구성이 참조 됩니다.  
  
3. 명명 되지 않은 `<federationConfiguration>` 요소가 있으면 기본 페더레이션 구성입니다. 해당 `identityConfiguration` 특성이 지정 된 경우 명명 된 id 구성이 참조 되 고, 그렇지 않으면 기본 id 구성이 참조 됩니다.  
  
4. 명명 된 요소를 여러 개 `<federationConfiguration>` 포함 하 고 명명 되지 않은 `<federationConfiguration>` 요소가 없으면 예외가 throw 됩니다.  
  
 일반적으로 하나의 `<federationConfiguration>` 섹션만 정의 됩니다. 이 섹션은 기본 페더레이션 구성입니다. 고유 하 게 명명 된 여러 요소를 지정할 수 있습니다 `<federationConfiguration>` . 그러나이 경우 명명 되지 않은 요소 이외의 페더레이션 구성을 로드 하려는 경우에는에 대 한 처리기를 제공 해야 합니다. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>이벤트를 처리 하 고 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> 처리기 내의 속성을 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> `<federationConfiguration>` 구성 파일에 있는 해당 요소의 값으로 초기화 된 개체로 설정 합니다.  
  
 합니다 `<federationConfiguration>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> 클래스입니다. 구성 개체 자체는 클래스로 표현 됩니다 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> . 단일 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 인스턴스가 속성에 대해 설정 되 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> 고 응용 프로그램에 대 한 페더레이션된 구성을 제공 합니다.  
  
## <a name="example"></a>예제  
 다음 XML에서는 `<federationConfiguration>` WSFAM에 대 한 설정을 지정 하 고 SAM에서 기본 쿠키 처리기 (클래스의 인스턴스)를 사용 하도록 지정 하는 요소를 보여 줍니다 <xref:System.IdentityModel.Services.ChunkedCookieHandler> .  
  
> [!WARNING]
> 이 예제에서는 HTTPS를 사용 하는 데 쿠키 처리기와 WSFAM이 모두 필요 하지 않습니다. 이는 요소의 특성과의 특성이 이기 때문입니다 `requireHttps` `<wsFederation>` `requireSsl` `<cookieHandlerElement>` `false` . 이러한 설정은 보안 위험을 초래할 수 있으므로 대부분의 프로덕션 환경에는 권장 되지 않습니다.  
  
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
- [\<identityConfiguration>](identityconfiguration.md)
