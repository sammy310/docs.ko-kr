---
title: <cookieHandler>
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
ms.openlocfilehash: 5f5b432830a61adab324b2b6cd2ebe6eeccca7f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189840"
---
# \<cookieHandler>

<xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM)에서 쿠키를 읽고 쓰는 데 사용 하는를 구성 합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cookieHandler>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler name=xs:string  
        path=Path  
        mode="Chunked||Custom||Default"  
        persistentSessionLifetime=xs:string  
        hideFromScript=xs:boolean  
        requireSSL=xs:boolean  
        domain=xs:string  
      <chunkedCookieHandler size=xs:int />  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|name|작성 된 모든 쿠키의 기본 이름을 지정 합니다. 기본값은 "FedAuth"입니다.|  
|path|작성 된 모든 쿠키에 대 한 경로 값을 지정 합니다. 기본값은 "HttpRuntime. AppDomainAppVirtualPath"입니다.|  
|mode|<xref:System.IdentityModel.Services.CookieHandlerMode>SAM에서 사용 하는 쿠키 처리기의 종류를 지정 하는 값 중 하나입니다. 다음 값을 사용할 수 있습니다.<br /><br /> -"Default"-"청크 분할"과 동일 합니다.<br />-"청크 분할"-클래스의 인스턴스를 사용 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 합니다. 이 쿠키 처리기는 개별 쿠키가 설정 된 최대 크기를 초과 하지 않도록 합니다. 이는 잠재적으로 논리 쿠키 하나를 실시간으로 많은 쿠키에 "청크" 하 여이를 수행 합니다.<br />-"Custom" —에서 파생 된 사용자 지정 클래스의 인스턴스를 사용 <xref:System.IdentityModel.Services.CookieHandler> 합니다. 파생 된 클래스는 자식 요소에서 참조 됩니다 `<customCookieHandler>` .<br /><br /> 기본값은 "Default"입니다.|  
|persistentSessionLifetime|영구적 세션의 수명을 지정 합니다. 0이면 임시 세션이 항상 사용됩니다. 기본값은 임시 세션을 지정 하는 "0:0:0"입니다. 최대값은 365 일의 세션을 지정 하는 "365:0:0"입니다. 값은 다음 제한 사항에 따라 지정 해야 합니다. `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />` 여기서 왼쪽 값은 일을 지정 하 고, 중간 값 (있는 경우)은 시간을 지정 하 고, 가장 오른쪽 값 (있는 경우)은 분을 지정 합니다.|  
|requireSsl|작성 된 모든 쿠키에 대해 "보안" 플래그를 내보낼지 여부를 지정 합니다. 이 값을 설정 하면 로그인 세션 쿠키는 HTTPS를 통해서만 사용할 수 있습니다. 기본값은 "true"입니다.|  
|hideFromScript|작성 된 쿠키에 대 한 "HttpOnly" 플래그는 내보내집니다 여부를 제어 합니다. 특정 웹 브라우저는 클라이언트 쪽 스크립트가 쿠키 값에 액세스 하지 못하도록 하 여이 플래그를 적용 합니다. 기본값은 "true"입니다.|  
|도메인|작성 된 모든 쿠키에 대 한 도메인 값입니다. 기본값은 ""입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<chunkedCookieHandler>](chunkedcookiehandler.md)|를 구성 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 합니다. `mode` `<cookieHandler>` 요소의 특성이 "Default" 또는 "청크 분할" 인 경우에만이 요소가 있을 수 있습니다.|  
|[\<customCookieHandler>](customcookiehandler.md)|사용자 지정 쿠키 처리기 형식을 설정 합니다. `mode` `<cookieHandler>` 요소의 특성이 "Custom" 이면이 요소가 있어야 합니다. 특성의 다른 값에 대해서는 사용할 수 없습니다 `mode` . 사용자 지정 형식은 클래스에서 파생 되어야 합니다 <xref:System.IdentityModel.Services.CookieHandler> .|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(Wsfam) 및 (SAM)을 구성 하는 설정을 포함 합니다 <xref:System.IdentityModel.Services.SessionAuthenticationModule> .|  
  
## <a name="remarks"></a>설명  

 는 <xref:System.IdentityModel.Services.CookieHandler> HTTP 프로토콜 수준에서 원시 쿠키를 읽고 쓰는 역할을 담당 합니다. <xref:System.IdentityModel.Services.ChunkedCookieHandler>또는 클래스에서 파생 된 사용자 지정 쿠키 처리기를 구성할 수 있습니다 <xref:System.IdentityModel.Services.CookieHandler> .  
  
 청크 분할 된 쿠키 처리기를 구성 하려면 mode 특성을 "청크 분할" 또는 "기본값"으로 설정 합니다. 기본 청크 크기는 2000 바이트 이지만 선택적으로 자식 요소를 포함 하 여 다른 청크 크기를 지정할 수 있습니다 `<chunkedCookieHandler>` .  
  
 사용자 지정 쿠키 처리기를 구성 하려면 mode 특성을 "Custom"으로 설정 합니다. 또한 `<customCookieHandler>` 사용자 지정 처리기의 형식을 참조 하는 자식 요소를 지정 해야 합니다.  
  
 합니다 `<cookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.CookieHandlerElement> 클래스입니다. 구성에 지정 된 쿠키 처리기는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> 속성에 설정 된 개체의 속성에서 사용할 수 있습니다 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> .  
  
## <a name="example"></a>예제  

 다음 XML에서는 요소를 보여 줍니다 `<cookieHandler>` . 이 예제에서는 특성을 지정 하지 않았기 때문에 `mode` SAM에서 기본 쿠키 처리기를 사용 합니다. 클래스의 인스턴스입니다 <xref:System.IdentityModel.Services.ChunkedCookieHandler> . `<chunkedCookieHandler>`자식 요소가 지정 되지 않았기 때문에 기본 청크 크기가 사용 됩니다. 특성이 설정 되었으므로 HTTPS가 필요 하지 않습니다 `requireSsl` `false` .  
  
> [!WARNING]
> 이 예제에서는 세션 쿠키를 작성 하는 데 HTTPS가 필요 하지 않습니다. 이는 `requireSsl` 요소의 특성이로 설정 되어 있기 때문입니다 `<cookieHandler>` `false` . 이 설정은 보안 위험을 초래할 수 있으므로 대부분의 프로덕션 환경에는 권장 되지 않습니다.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.IdentityModel.Services.CookieHandler>
- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
