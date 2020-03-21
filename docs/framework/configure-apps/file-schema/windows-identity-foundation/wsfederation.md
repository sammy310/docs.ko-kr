---
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 53f3943524c45a43ddb60553b8ff45f19df66b14
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152465"
---
# <a name="wsfederation"></a>\<ws페더레이션>
(WSFAM)에 대한 구성을 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 제공합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.서비스>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<페더레이션구성>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws페더레이션>**  
  
## <a name="syntax"></a>구문  
  
```xml
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation authenticationType=xs:string (URI)  
                  freshness=xs:decimal  
                  homerealm=xs:string (URI)  
                  issuer=xs:string (URI)  
                  persistentCookiesOnPassiveRedirects=xs:boolean  
                  passiveRedirectEnabled=xs:boolean  
                  policy=xs:string (URI)  
                  realm=xs:string (URI)  
                  reply=xs:string (URI)  
                  request=xs:string (URI)  
                  requestPtr=xs:string (URI)  
                  requireHttps=xs:boolean  
                  resource=xs:string (URI)  
                  signInQueryString=xs:string  
                  signOutQueryString=xs:string  
                  signOutReply=xs:string (URL)  
    </wsFederation>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|authenticationType|인증 형식을 지정하는 URI입니다. WS-페더레이션 로그인 요청 wauth 매개 변수를 설정합니다. (선택 사항) 기본값은 wauth 매개 변수가 요청에 포함되지 않도록 지정하는 빈 문자열입니다.|  
|신선도|원하는 최대 인증 요청 나이(분)입니다. WS-Federation 로그인 요청 wfresh 매개 변수를 설정합니다. (선택 사항) 기본값은 0입니다. (선택 사항) **경고:**  .NET Framework 4.5의 다음 릴리스에서는 특성이 `freshness` `xs:string` 형식이고 기본값은 `null`입니다.|  
|홈 영역|인증에 사용할 IDP(IDP)의 홈 영역입니다. WS-Federation 로그인 요청 whr 매개 변수를 설정합니다. (선택 사항) 기본값은 빈 문자열로, whr 매개 변수가 요청에 포함되지 않도록 지정합니다.|  
|발급자|의도한 토큰 발급자의 URI입니다. WS-페더레이션 로그인 요청 및 로그아웃 요청의 기본 URL을 설정합니다.|  
|지속적쿠키온수심재지시|인증 시 영구 쿠키가 발급되는지 여부를 지정합니다. (선택 사항) 기본값은 "false"이며 쿠키는 발급되지 않습니다.|  
|수동다시 지시 가능|WSFAM이 승인되지 않은 요청을 STS로 자동으로 리디렉션할 수 있는지 여부를 지정합니다. (선택 사항) 기본값은 "true"이며 승인되지 않은 요청은 자동으로 리디렉션됩니다.|  
|policy|로그인 요청에 사용할 관련 정책의 위치를 지정하는 URL입니다. 기본값은 빈 문자열입니다. WS-Federation 로그인 요청 wp 매개 변수를 설정합니다. (선택 사항) 기본값은 wp 매개 변수가 요청에 포함되지 않도록 지정하는 빈 문자열입니다.|  
|realm|요청 영역의 URI입니다. (STS(보안 토큰 서비스)에 대한 RP(의존자)를 식별하는 URI입니다. 요청 wtrealm WS-페더레이션 로그인 요청 매개 변수를 설정합니다. 필수 사항입니다.|  
|응답|RP(신뢰 당사자) 애플리케이션이 STS(보안 토큰 서비스)에서 응답을 받을 주소를 식별하는 URL입니다. WS-페더레이션 로그인 요청 wreply 매개 변수를 설정합니다. (선택 사항) 기본값은 wreply 매개 변수가 요청에 포함되지 않도록 지정하는 빈 문자열입니다.|  
|request|토큰 발급 요청입니다. WS-Federation 로그인 요청 wreq 매개 변수를 설정합니다. (선택 사항) 기본값은 wreq 매개 변수가 요청에 포함되지 않도록 지정하는 빈 문자열입니다. 요청에 wreq 또는 wreqptr 매개 변수를 포함하지 않는 것은 STS가 발행할 토큰의 종류를 알고 있음을 의미합니다.|  
|요청Ptr|토큰 발급 요청의 위치를 지정하는 URL입니다. 요청 wreqptr 매개 변수를 설정합니다. (선택 사항) 기본값은 wreqptr 매개 변수가 요청에 포함되지 않도록 지정하는 빈 문자열입니다. 요청에 wreq 또는 wreqptr 매개 변수를 포함하지 않는 것은 STS가 발행할 토큰의 종류를 알고 있음을 의미합니다.|  
|필요https|STS(보안 토큰 서비스)와의 통신이 HTTPS 프로토콜을 사용해야 하는지 여부를 지정합니다. (선택 사항) 기본값은 "true"이며 HTTPS를 사용해야 합니다.|  
|resource|RP(신뢰 당사자)인 액세스될 리소스를 STS(보안 토큰 서비스)에 식별하는 URI입니다. (선택 사항) WS-페더레이션 로그인 요청 wres 매개 변수를 설정합니다. (선택 사항) 기본값은 wres 매개 변수가 요청에 포함되지 않도록 지정하는 빈 문자열입니다. **참고:** wres는 레거시 매개 변수입니다. 대신 `realm` wtrealm 매개 변수를 사용하도록 특성을 지정합니다.|  
|사인인쿼리스트|WS-페더레이션 로그인 요청 URL에서 응용 프로그램 정의 쿼리 매개 변수를 지정하는 확장성 지점을 제공합니다. (선택 사항) 기본값은 요청에 추가 매개 변수를 포함하지 않음을 지정하는 빈 문자열입니다. 매개 변수는 다음과 같은 형식을 `"param1=value1&param2=value2&param3=value3"` 사용하여 쿼리 문자열 조각으로 지정됩니다. **참고:**  구성 파일에서 쿼리 문자열의 '&' 문자는 엔터티 참조를 `&`사용하여 지정해야 합니다.|  
|사인아웃 쿼리 스트링|WS-페더레이션 로그인 요청 URL에서 응용 프로그램 정의 쿼리 매개 변수를 지정하는 확장성 지점을 제공합니다. (선택 사항) 기본값은 요청에 추가 매개 변수를 포함하지 않음을 지정하는 빈 문자열입니다. 매개 변수는 다음과 같은 형식을 `"param1=value1&param2=value2&param3=value3"` 사용하여 쿼리 문자열 조각으로 지정됩니다. **참고:**  구성 파일에서 쿼리 문자열의 '&' 문자는 엔터티 참조를 `&`사용하여 지정해야 합니다.|  
|사인아웃답지|WS-페더레이션 프로토콜을 통해 수동 로그아웃 중에 클라이언트가 STS(보안 토큰 서비스)로 리디렉션되어야 하는 URL을 지정합니다. WS-페더레이션 로그아웃 요청에서 wreply 매개 변수를 설정합니다. (선택 사항) 기본값은 요청에 추가 매개 변수를 포함하지 않음을 지정하는 빈 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 None  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<페더레이션구성>](federationconfiguration.md)|<xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM)을 구성하는 설정을 포함합니다.|  
  
## <a name="remarks"></a>설명  
 이 요소를 `<wsFederation>` 사용하여 WSFAM에 대한 기본 WS-페더레이션 매개 변수 설정 및 기본 동작을 구성할 수 있습니다. 요소 에서 정의된 WS-페더레이션 매개 변수 설정은 `<wsFederation>` 클래스에서 노출되는 등가 속성을 설정합니다. <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 이러한 속성은 WSFAM에서 발급한 모든 요청에 대해 동일하게 유지됩니다. WSFAM에서 노출되는 이벤트에 대한 이벤트 처리기를 추가하여 요청 처리 중에 WS-페더레이션 매개 변수를 동적으로 변경할 수 있습니다. 예를 들어 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> 이벤트입니다. 자세한 내용은 클래스에 대한 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 설명서를 참조하십시오.  
  
 합니다 `<wsFederation>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.Configuration.WSFederationElement> 클래스입니다. 구성 개체 자체는 <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> 클래스로 표시됩니다. 단일 <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> 인스턴스는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> 속성을 통해 액세스되는 개체에 설정되며 WSFAM에 대한 구성을 제공합니다.  
  
## <a name="example"></a>예제  
 다음 XML에는 `<wsFederation>` WSFAM에 대한 설정을 지정하는 요소가 표시됩니다.  
  
> [!WARNING]
> 이 예제에서는 WSFAM이 HTTPS를 사용할 필요가 없습니다. 이는 `requireHttps` `<wsFederation>` 요소의 특성이 설정되어 `false`있기 때문입니다. 이 설정은 보안 위험이 있을 수 있으므로 대부분의 프로덕션 환경에서는 권장되지 않습니다.  
  
```xml
<wsFederation passiveRedirectEnabled="true"
              issuer="http://localhost:15839/wsFederationSTS/Issue"
              realm="http://localhost:50969/"
              reply="http://localhost:50969/"
              requireHttps="false"
              signOutReply="http://localhost:50969/SignedOutPage.html"
              signOutQueryString="Param1=value2&Param2=value2"
              persistentCookiesOnPassiveRedirects="true" />
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
