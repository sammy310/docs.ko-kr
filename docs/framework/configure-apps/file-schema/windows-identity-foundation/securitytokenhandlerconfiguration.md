---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 29e18cdda9e18addef4f0f32fd30e9abf6af78fc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360409"
---
# <a name="securitytokenhandlerconfiguration"></a>\<securityTokenHandlerConfiguration>
토큰 처리기 컬렉션에 대 한 구성을 제공합니다.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration>  
  
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
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|saveBootstrapContext|세션 토큰에 부트스트랩 토큰을 포함시킬지 여부를 지정 합니다. 값을 설정할 수도 있습니다 토큰 처리기 컬렉션에 대해 설정 하 여 합니다 `saveBootstrapContext` 특성을 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다. 토큰 처리기 컬렉션에 대해 설정 된 값에는 서비스에서 설정한 값 보다 우선 합니다.|  
|maximumClockSkew|<xref:System.TimeSpan> 허용 된 최대 클럭 오차를 지정 하는 합니다. 로그인 세션이 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 허용 되는 최대 클럭 오차를 제어 합니다. 기본값은 5 분 "00: 05:00"입니다. 지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> 값을 참조 하세요 [Timespan 값](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다. 최대 클럭 오차 설정할 수도 있습니다 서비스 수준에서 설정 하 여 합니다 `maximumClockSkew` 특성을 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다. 토큰 처리기 컬렉션에 대해 설정 된 값에는 서비스에서 설정한 값 보다 우선 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<audienceUris>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|이 신뢰 당사자의 식별자를 허용 되는 Uri 집합을 지정 합니다. 선택 사항입니다.|  
|[\<caches>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다. 서비스 수준 또는 보안 토큰 처리기 컬렉션을 지정할 수 있습니다. 선택 사항입니다.|  
|[\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|토큰 처리기 인증서의 유효성을 검사 하는 데 사용 되는 설정을 제어 합니다. 서비스 수준 또는 보안 토큰 처리기 컬렉션을 지정할 수 있습니다. 특정 처리기를 자체 유효성 검사기를 사용 하 여 구성 된 경우이 설정은 무시 됩니다. 선택 사항입니다.|  
|[\<issuerNameRegistry>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|토큰 처리기 컬렉션의 처리기에서 사용 되는 발급자 이름 레지스트리를 구성 합니다. 선택 사항입니다.|  
|[\<issuerTokenResolver>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|토큰 처리기 컬렉션의 처리기에서 사용 되는 발급자 토큰 확인자를 등록 합니다. 발급자 토큰 확인자는 들어오는 토큰 및 메시지에 서명 토큰을 확인 하는 데 사용 됩니다. 선택 사항입니다.|  
|[\<serviceTokenResolver>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|토큰 처리기 컬렉션의 처리기에서 사용 되는 서비스 토큰 확인자를 등록 합니다. 서비스 토큰 확인자는 들어오는 토큰에 메시지 암호화 토큰을 확인 하는 데 사용 됩니다. 선택 사항입니다.|  
|[\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|토큰 재생 검색을 사용 하도록 설정 하 고 토큰에 대 한 만료 시간을 지정 합니다. 서비스 수준 또는 보안 토큰 처리기 컬렉션을 지정할 수 있습니다. 선택 사항입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|끝점을 사용 하 여 등록 된 보안 토큰 처리기 컬렉션을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 이 섹션에서는 속성 값을 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> 개체입니다. 이 섹션에 구성 된 설정 서비스에서 구성한 설정을 재정의 합니다. 이러한 설정 중 일부 처리기는 보안 토큰 처리기 컬렉션에 추가 되 면 지정 된 설정으로 재정의 수 있습니다.  
  
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
