---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152569"
---
# <a name="securitytokenhandlerconfiguration"></a>\<보안토큰처리기구성>
토큰 처리기 컬렉션에 대 한 구성을 제공 합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<보안토큰처리기구성>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|저장부트트랩컨텍스트|부트스트랩 토큰을 세션 토큰에 포함할지 여부를 지정합니다. idConfiguration>요소에 특성을 `saveBootstrapContext` 설정 하 여 토큰 처리기 컬렉션에 값을 설정할 수도 있습니다. [ \<](identityconfiguration.md) 토큰 처리기 컬렉션에 설정된 값은 서비스에 설정된 값을 재정의합니다.|  
|최대 클럭스큐|허용되는 <xref:System.TimeSpan> 최대 클럭 기울이기(기울이기)를 지정하는 A입니다. 로그인 세션이 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 허용 되는 최대 클럭 오차를 제어 합니다. 기본값은 5분 "00:05:00"입니다. 값을 지정하는 <xref:System.TimeSpan> 방법에 대한 자세한 내용은 [시간 범위 값을](../windows-workflow-foundation/index.md)참조하십시오. idConfiguration>요소에 특성을 `maximumClockSkew` 설정 하 여 최대 클럭 스큐를 서비스 수준에서 설정할 수도 있습니다. [ \<](identityconfiguration.md) 토큰 처리기 컬렉션에 설정된 값은 서비스에 설정된 값을 재정의합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<청중우리>](audienceuris.md)|이 사용 당사자의 허용 가능한 식별자인 URI 집합을 지정합니다. (선택 사항)|  
|[\<캐시>](caches.md)|세션 토큰 및 토큰 재생 검색에 사용되는 캐시를 등록합니다. 서비스 수준 또는 보안 토큰 처리기 컬렉션에 지정할 수 있습니다. (선택 사항)|  
|[\<인증서 유효성 검사>](certificatevalidation.md)|토큰 처리기가 인증서의 유효성을 검사하는 데 사용하는 설정을 제어합니다. 서비스 수준 또는 보안 토큰 처리기 컬렉션에 지정할 수 있습니다. 특정 처리기가 자체 유효성 검사기로 구성된 경우 이러한 설정이 재정의됩니다. (선택 사항)|  
|[\<발급자이름레지스트리>](issuernameregistry.md)|토큰 처리기 컬렉션의 처리기에서 사용되는 발급자 이름 레지스트리를 구성합니다. (선택 사항)|  
|[\<발행자토큰해결러>](issuertokenresolver.md)|토큰 처리기 컬렉션의 처리기에서 사용되는 발급자 토큰 확인자를 등록합니다. 발급자 토큰 확인기는 들어오는 토큰 및 메시지에 서명 토큰을 해결하는 데 사용됩니다. (선택 사항)|  
|[\<서비스토큰 해결사>](servicetokenresolver.md)|토큰 처리기 컬렉션의 처리기에서 사용되는 서비스 토큰 확인자를 등록합니다. 서비스 토큰 확인기는 들어오는 토큰 및 메시지에서 암호화 토큰을 해결하는 데 사용됩니다. (선택 사항)|  
|[\<토큰 재생 감지>](tokenreplaydetection.md)|토큰 재생 검색을 활성화하고 토큰의 만료 시간을 지정합니다. 서비스 수준 또는 보안 토큰 처리기 컬렉션에 지정할 수 있습니다. (선택 사항)|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<보안토큰처리기>](securitytokenhandlers.md)|끝점에 등록된 보안 토큰 처리기 의 컬렉션을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 섹션에서는 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> 개체에 대한 속성 값을 제공합니다. 이 섹션에서 구성된 설정은 서비스에 구성된 설정을 재정의합니다. 이러한 설정 중 일부는 처리기가 보안 토큰 처리기 컬렉션에 추가될 때 지정된 설정에 의해 재정의될 수 있습니다.  
  
## <a name="example"></a>예제  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
