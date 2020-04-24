---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: a0db10ceb75a470dbf799d717b2059355dd104bb
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646074"
---
# <a name="sessionsecuritytokencache"></a>\<세션보안토큰캐시>
서비스 또는 보안 토큰 처리기 컬렉션으로 세션 토큰에 대한 캐시를 등록합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<캐시>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<세션보안토큰캐시>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|type|클래스에서 파생되는 형식입니다. <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>|  
  
### <a name="child-elements"></a>자식 요소  
 None  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<캐시>](caches.md)|서비스 또는 보안 토큰 처리기 컬렉션에서 사용하는 캐시를 등록합니다.|  
  
## <a name="example"></a>예제  
 다음 XML은 세션 보안 토큰()을<xref:System.IdentityModel.Tokens.SessionSecurityToken>보유하기 위한 사용자 지정 캐시의 구성을 보여 주며 있습니다. 구성은 `ClaimsAwareWebFarm` 샘플에서 가져옵니다. 이 샘플에 대한 자세한 내용은 [WIF 코드 샘플 인덱스](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index)를 참조하십시오.  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
