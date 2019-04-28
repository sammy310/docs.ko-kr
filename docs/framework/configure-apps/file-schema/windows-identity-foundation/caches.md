---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: b1d04280ef993297102d446ba5a7db54e8404dd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750789"
---
# <a name="caches"></a>\<caches>
세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<caches>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 세션 토큰에 대 한 캐시를 등록합니다.|  
|[\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 토큰 재생 캐시를 등록합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
|[\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안 토큰 처리기를 제공합니다.|  
  
## <a name="remarks"></a>설명  
 `<caches>` 요소 아래에 있는 서비스 수준에서 지정할 수 있습니다 합니다 `<identityConfiguration>` 요소 또는 보안 토큰 처리기 컬렉션 수준에서는 `<securityTokenHandlerConfiguration>` 요소입니다. 서비스에 지정 된 토큰 처리기 컬렉션의 설정을 무시 합니다.  
  
 합니다 `<caches>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> 클래스입니다. 구성 된 캐시 표시 됩니다는 <xref:System.IdentityModel.Configuration.IdentityModelCaches> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 XML 세션 보안 토큰을 보관 하기 위한 사용자 지정 캐시 구성을 보여 줍니다 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>). 구성에서 가져온 것은 `ClaimsAwareWebFarm` 샘플입니다.  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
