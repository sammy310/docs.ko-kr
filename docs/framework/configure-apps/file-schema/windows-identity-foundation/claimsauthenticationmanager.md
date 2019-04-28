---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: ecf26263bf47e8b4609e7adc208f0a59a2fa795b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667329"
---
# <a name="claimsauthenticationmanager"></a>\<claimsAuthenticationManager>
들어오는 클레임에 대 한 클레임 인증 관리자를 등록합니다.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<claimsAuthenticationManager>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|type|파생 되는 사용자 지정 형식 지정을 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스입니다. 지정 하는 방법에 대 한 자세한 내용은 `type` 특성 [사용자 지정 형식 참조]를 참조 하세요.|  
  
### <a name="child-elements"></a>자식 요소  
 없는 경우 없습니다 `type` 특성을 또는 경우에는 `type` 특성 참조를 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스를 `<claimsAuthenticationManager>` 요소는 자식 요소를 사용 하지 않는; 클래스에서 파생 되는 반면 <xref:System.Security.Claims.ClaimsAuthenticationManager> 자식 구성 요소를 정의할 수 있습니다.  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 기본 동작을 통해 제공 된 <xref:System.Security.Claims.ClaimsAuthenticationManager> 들어오는 클레임을 에코 하는 클래스입니다. 없으면 `type` 특성을 지정 경우는 `type` 특성을 지정 합니다 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 `<claimsAuthenticationManager>` 요소는 자식 요소를 사용 하지 않습니다. 지정할 수 있습니다 합니다 `type` 에서 파생 된 특성 형식을 등록 하는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 사용자 지정 동작을 구현 하는 클래스입니다. 파생된 클래스의 자식 요소를 통해 구성을 지원할 수는 `<claimsAuthenticationManager>` 재정의 하 여 요소를 <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> 이러한 요소를 처리 하는 방법입니다. 자식 요소에 대해 정의 된 스키마 클래스의 디자이너에 게 달려 있습니다.  
  
 합니다 `<claimsAuthenticationManager>` 요소 집합을 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> 속성입니다.  
  
## <a name="example"></a>예제  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
