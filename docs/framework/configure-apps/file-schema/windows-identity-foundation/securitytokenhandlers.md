---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: a5af3893ab72d23c2b3814569decfc50431b8e55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793837"
---
# <a name="securitytokenhandlers"></a>\<securityTokenHandlers>
끝점을 사용 하 여 등록 된 보안 토큰 처리기 컬렉션을 지정 합니다.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|name|토큰 처리기 컬렉션의 이름을 지정합니다. 프레임 워크에서 인식 유일한 값은 "ActAs" 및 "OnBehalfOf"입니다. 토큰 처리기 컬렉션은 이러한 이름 중 하나를 사용 하 여 지정 된 경우에 각각 토큰 ActAs 또는 OnBehalfOf를 처리 하는 경우 컬렉션 사용 됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|토큰 처리기 컬렉션에는 보안 토큰 처리기를 추가합니다.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|토큰 처리기 컬렉션에서 모든 보안 토큰 처리기를 지웁니다.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|토큰 처리기 컬렉션에서 보안 토큰 처리기를 제거합니다.|  
|[\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|토큰 처리기 컬렉션에 대 한 구성을 제공합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 서비스 구성에서 하나 이상의 명명 된 보안 토큰 처리기 컬렉션을 지정할 수 있습니다. 사용 하 여 컬렉션의 이름을 지정할 수 있습니다는 `name` 특성입니다. 프레임 워크를 처리 하는 유일한 이름에는 "ActAs" 및 "OnBehalfOf"입니다. 이러한 컬렉션의 처리기가 없는 경우 사용할 보안 토큰 서비스 (STS)에서 기본 처리기를 대신 처리 하는 동안 `ActAs` 고 `OnBehalfOf` 토큰입니다.  
  
 기본적으로 컬렉션 채워집니다 처리기 형식은: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>를 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, 및 <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>합니다. 사용 하 여 컬렉션을 수정할 수는 `<add>`, `<remove>`, 및 `<clear>` 요소입니다. 특정 형식의 단일 처리기만 컬렉션에 있는지를 확인 해야 합니다. 예를 들어에서 처리기를 파생 하는 경우는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 하거나 클래스 처리기 또는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 단일 컬렉션, 하지만 둘 다에서 구성할 수 있습니다.  
  
 사용 된 `<securityTokenHandlerConfiguration>` 컬렉션의 처리기에 대 한 구성 설정을 지정 하는 요소입니다. 이 요소를 통해 지정 된 설정을 재정의 통해 서비스에 지정 된 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다. 일부 처리기 (몇 가지 기본 제공 처리기 형식을 포함)의 자식 요소를 통해 추가 구성을 지원할 수는 `<add>` 요소입니다. 처리기에 지정 된 설정은 컬렉션 또는 서비스에서 지정 된 해당 설정을 재정의 합니다.
