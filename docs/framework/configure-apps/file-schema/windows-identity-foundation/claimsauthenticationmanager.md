---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152751"
---
# <a name="claimsauthenticationmanager"></a>\<클레임인증관리자>
들어오는 클레임에 대한 클레임 인증 관리자를 등록합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<클레임인증관리자>**  
  
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
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|type|<xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스에서 파생되는 사용자 지정 형식을 지정합니다. `type` 특성을 지정하는 방법에 대한 자세한 내용은 [사용자 지정 유형 참조]를 참조하십시오.|  
  
### <a name="child-elements"></a>자식 요소  
 특성이 없거나 `type` 특성이 클래스를 `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> 참조하는 경우 `<claimsAuthenticationManager>` 요소는 자식 요소를 사용하지 않습니다. 그러나 파생된 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 자식 구성 요소를 정의할 수 있습니다.  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<ID구성>](identityconfiguration.md)|서비스 수준 ID 설정을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 클래스를 <xref:System.Security.Claims.ClaimsAuthenticationManager> 통해 제공되는 기본 동작은 들어오는 클레임을 에코합니다. 특성이 `type` 지정되지 않았거나 `type` 특성이 클래스를 <xref:System.Security.Claims.ClaimsAuthenticationManager> 지정하는 `<claimsAuthenticationManager>` 경우 요소는 자식 요소를 사용하지 않습니다. 사용자 지정 `type` 동작을 구현하기 위해 클래스에서 파생된 형식을 등록하는 특성을 <xref:System.Security.Claims.ClaimsAuthenticationManager> 지정할 수 있습니다. 파생 클래스는 이러한 요소를 처리하는 `<claimsAuthenticationManager>` 메서드를 <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> 재정의하여 요소의 자식 요소를 통해 구성을 지원할 수 있습니다. 자식 요소에 대해 정의된 스키마는 클래스의 디자이너에게 달려 있습니다.  
  
 `<claimsAuthenticationManager>` 요소는 속성을 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> 설정합니다.  
  
## <a name="example"></a>예제  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
