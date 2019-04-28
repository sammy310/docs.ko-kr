---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 1143717882652fc8a03947327b5f1ea89dde7373
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793811"
---
# <a name="servicetokenresolver"></a>\<serviceTokenResolver>
토큰 처리기 컬렉션의 처리기에서 사용 되는 서비스 토큰 확인자를 등록 합니다. 서비스 토큰 확인자는 들어오는 토큰에 메시지 암호화 토큰을 확인 하는 데 사용 됩니다.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration>  
\<serviceTokenResolver>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
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
|type|서비스 토큰 확인자 형식을 지정합니다. 중 하나는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 형식 또는 형식에서 파생 되는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스입니다. 지정 하는 방법에 대 한 자세한 내용은 `type` 특성 [사용자 지정 형식 참조]를 참조 하세요. 필수 요소.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안 토큰 처리기를 제공합니다.|  
  
## <a name="remarks"></a>설명  
 들어오는 토큰에 메시지 암호화 토큰을 확인 하려면 서비스 토큰 확인자를 사용할 수 있습니다. 들어오는 토큰 암호 해독에 사용 해야 하는 키를 검색 하는 것이 됩니다. 지정 해야 합니다 `type` 특성입니다. 지정 된 형식의 일 수 있습니다 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 또는 사용자 지정 형식에서 파생 되는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스입니다.  
  
 일부 토큰 처리기를 사용 하면 구성에서 서비스 토큰 확인자 설정을 지정할 수 있습니다. 개별 토큰 처리기에 설정 된 보안 토큰 처리기 컬렉션에서 지정 된 재정의합니다.  
  
> [!NOTE]
>  지정 된 `<serviceTokenResolver>` 의 자식 요소로 요소를 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소에 사용 되지 않지만 이전 버전과 호환성을 위해 계속 지원 됩니다. 설정 합니다 `<securityTokenHandlerConfiguration>` 요소에 있는 구성을 재정의 `<identityConfiguration>` 요소입니다.  
  
## <a name="example"></a>예제  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
