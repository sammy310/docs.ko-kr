---
title: <cookieHandler>
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
ms.openlocfilehash: dc0613bb727f9ed061c3b5d494bdc279515b56e9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369018"
---
# <a name="cookiehandler"></a>\<cookieHandler>
구성 된 <xref:System.IdentityModel.Services.CookieHandler> 는 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) 읽기 및 쓰기 쿠키를 사용 하 여 합니다.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler>  
  
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
  
|특성|설명|  
|---------------|-----------------|  
|name|작성 된 쿠키에 대 한 기본 이름을 지정 합니다. 기본값은 "FedAuth"입니다.|  
|path|작성 된 쿠키의 경로 값을 지정 합니다. 기본값은 "HttpRuntime.AppDomainAppVirtualPath".|  
|모드|중 하나는 <xref:System.IdentityModel.Services.CookieHandlerMode> SAM에서 사용 되는 쿠키 처리기의 종류를 지정 하는 값입니다. 다음 값을 사용할 수 있습니다.<br /><br /> -"Default"-"Chunked"와 동일 합니다.<br />-"청크"-의 인스턴스를 사용 하 여 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 클래스. 이 쿠키 처리기 개별 쿠키 설정 된 최대 크기를 초과 하지 않는 것을 확인 합니다. 잠재적으로 "청크" 하나의 논리 쿠키 실시간 쿠키 수로 하 여이 작업을 수행 합니다.<br />-"Custom"-에서 파생 된 사용자 지정 클래스의 인스턴스를 사용 하 여 <xref:System.IdentityModel.Services.CookieHandler>입니다. 파생된 클래스에서 참조 되는 `<customCookieHandler>` 자식 요소입니다.<br /><br /> 기본값은 "Default"입니다.|  
|persistentSessionLifetime|영구 세션의 수명을 지정합니다. 0 이면 임시 세션이 항상 사용 됩니다. 기본값은 "0:0:0" 임시 세션을 지정 합니다. 최대 값은 "365:0:0" 세션 365 일을 지정 합니다. 다음 제한에 따라 값을 지정 해야 합니다. `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, 여기서 왼쪽 값을 지정 일, 시간을 지정 하는 중간 값 (있는 경우) 및 (있는 경우)에 오른쪽 값을 분 수를 지정 합니다.|  
|requireSsl|작성 된 쿠키에 대 한 "Secure" 플래그는 내보내집니다 여부를 지정 합니다. 이 값을 설정 하는 경우 로그인 세션 쿠키를만 제공 됩니다 HTTPS를 통해. 기본값은 "true"입니다.|  
|hideFromScript|작성 된 쿠키에 대 한 "HttpOnly" 플래그는 내보내집니다 여부를 제어 합니다. 특정 웹 브라우저는 쿠키 값에 액세스 하지 못하도록 클라이언트 쪽 스크립트를 유지 하 여이 플래그를 인식 합니다. 기본값은 "true"입니다.|  
|도메인|작성 된 쿠키의 도메인 값입니다. 기본값은 ""입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<chunkedCookieHandler>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|구성 된 <xref:System.IdentityModel.Services.ChunkedCookieHandler>합니다. 이 요소를 사용할 수만 있습니다 경우는 `mode` 특성을 `<cookieHandler>` 요소는 "Default" 또는 "청크"입니다.|  
|[\<customCookieHandler>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|사용자 지정 쿠키 처리기 형식을 설정합니다. 이 요소가 있어야 하는 경우는 `mode` 특성을 `<cookieHandler>` 요소는 "Custom"입니다. 다른 모든 값에 있을 수 없습니다는 `mode` 특성입니다. 사용자 지정 형식에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|구성 설정이 포함 된 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>설명  
 <xref:System.IdentityModel.Services.CookieHandler> 는 읽기 및 쓰기 원시 쿠키는 http 프로토콜 수준에 대해 책임이 있습니다. 구성할 수 있습니다는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 에서 파생 된 사용자 지정 쿠키 처리기를 또는 <xref:System.IdentityModel.Services.CookieHandler> 클래스.  
  
 청크 분할된 쿠키 처리기를 구성 하려면 "이 Chunked" 또는 "Default" 모드 특성을 설정 합니다. 기본 청크 크기 2000 바이트 이지만 다른 청크 크기를 포함 하 여 필요에 따라 지정할 수 있습니다는 `<chunkedCookieHandler>` 자식 요소입니다.  
  
 사용자 지정 쿠키 처리기를 구성 하려면 mode 특성을 "Custom"를 설정 합니다. 도 지정 해야 합니다는 `<customCookieHandler>` 사용자 지정 처리기의 유형을 참조 하는 자식 요소입니다.  
  
 합니다 `<cookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.CookieHandlerElement> 클래스입니다. 구성에 지정 된 쿠키 처리기에서 사용할 수는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> 의 속성을 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 설정 하는 개체는 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> 속성.  
  
## <a name="example"></a>예제  
 에서는 다음 XML `<cookieHandler>` 요소입니다. 이 예제에서는 때문에 `mode` 특성을 지정 하지 않으면 기본 쿠키 처리기 SAM에서 사용 됩니다. 인스턴스는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 클래스입니다. 때문에 `<chunkedCookieHandler>` 자식 요소를 지정 하지 않으면 기본 청크 크기 사용 됩니다. HTTPS 됩니다 필요 하기 때문에 합니다 `requireSsl` 특성이 설정 되어 `false`입니다.  
  
> [!WARNING]
>  이 예제에서는 HTTPS는 세션 쿠키를 작성할 필요가 없습니다. 왜냐하면를 `requireSsl` 특성을 `<cookieHandler>` 로 설정 된 `false`. 보안 위험이 있습니다 대로 대부분의 프로덕션 환경에 대 한이 설정은 없습니다 좋습니다.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>참고자료
- <xref:System.IdentityModel.Services.CookieHandler>
- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
