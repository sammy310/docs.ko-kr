---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152751"
---
# \<claimsAuthenticationManager>
들어오는 클레임에 대 한 클레임 인증 관리자를 등록 합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**  
  
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
  
|attribute|Description|  
|---------------|-----------------|  
|type|클래스에서 파생 되는 사용자 지정 형식을 지정 합니다 <xref:System.Security.Claims.ClaimsAuthenticationManager> . 특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조]를 참조 하세요.|  
  
### <a name="child-elements"></a>자식 요소  
 `type`특성이 없거나 특성이 클래스를 참조 하는 경우 `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthenticationManager>` 요소는 자식 요소를 사용 하지 않습니다. 그러나에서 파생 된 클래스는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 자식 구성 요소를 정의할 수 있습니다.  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|서비스 수준 id 설정을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 클래스를 통해 제공 되는 기본 동작은 <xref:System.Security.Claims.ClaimsAuthenticationManager> 들어오는 클레임을 에코 합니다. 특성을 `type` 지정 하지 않거나 특성에서 클래스를 지정 하는 경우 `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthenticationManager>` 요소는 자식 요소를 사용 하지 않습니다. 특성을 지정 `type` 하 여 클래스에서 파생 된 형식을 등록 하 고 <xref:System.Security.Claims.ClaimsAuthenticationManager> 사용자 지정 동작을 구현할 수 있습니다. 파생 클래스 `<claimsAuthenticationManager>` 는 <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> 이러한 요소를 처리 하도록 메서드를 재정의 하 여 요소의 자식 요소를 통해 구성을 지원할 수 있습니다. 자식 요소에 대해 정의 된 스키마는 클래스의 디자이너입니다.  
  
 `<claimsAuthenticationManager>`요소는 속성을 설정 합니다 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> .  
  
## <a name="example"></a>예제  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
