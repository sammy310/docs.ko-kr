---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 0718f789ff4d99fb4e2651a9a704da4248cd5f49
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158437"
---
# \<claimsAuthorizationManager>

들어오는 클레임에 대 한 클레임 권한 부여 관리자를 등록 합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthorizationManager>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|type|클래스에서 파생 되는 사용자 지정 형식 <xref:System.Security.Claims.ClaimsAuthorizationManager> 입니다. 특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조](../windows-workflow-foundation/index.md)를 참조 하세요.|  
  
### <a name="child-elements"></a>자식 요소  

 `type`특성이 없거나 특성이 클래스를 참조 하는 경우 `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthorizationManager>` 요소는 자식 요소를 사용 하지 않습니다. 그러나에서 파생 된 클래스는 <xref:System.Security.Claims.ClaimsAuthorizationManager> 자식 구성 요소를 정의할 수 있습니다.  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|서비스 수준 id 설정을 지정 합니다.|  
  
## <a name="remarks"></a>설명  

 클래스를 통해 제공 되는 기본 동작은 <xref:System.Security.Claims.ClaimsAuthorizationManager> 항상 들어오는 클레임을 승인 합니다. 특성을 `type` 지정 하지 않거나 특성에서 클래스를 지정 하는 경우 `type` <xref:System.Security.Claims.ClaimsAuthorizationManager> `<claimsAuthorizationManager>` 요소는 자식 요소를 사용 하지 않습니다. 특성을 지정 `type` 하 여 클래스에서 파생 된 형식을 등록 하 고 <xref:System.Security.Claims.ClaimsAuthorizationManager> 사용자 지정 동작을 구현할 수 있습니다. 파생 클래스 `<claimsAuthorizationManager>` 는 <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> 이러한 요소를 처리 하도록 메서드를 재정의 하 여 요소의 자식 요소를 통해 구성을 지원할 수 있습니다. 자식 요소에 대해 정의 된 스키마는 클래스의 디자이너입니다.  
  
> [!IMPORTANT]
> 또는 클래스를 사용 하 여 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 코드에서 클레임 기반 액세스 제어를 제공 하는 경우 요소에서 참조 하는 id 구성은 `<federationConfiguration>` 권한 부여 관리자와 권한 부여 결정을 내리는 데 사용 되는 정책을 구성 합니다. 이는 Windows Communication Foundation (WCF) 응용 프로그램 또는 웹 기반이 아닌 응용 프로그램 등 수동 웹 시나리오가 아닌 시나리오 에서도 마찬가지입니다. 응용 프로그램이 수동 웹 응용 프로그램이 아닌 경우 참조 되는 `<claimsAuthorizationManager>` id 구성의 요소 및 자식 정책 요소 (있는 경우)만 적용 됩니다. 다른 모든 설정은 무시 됩니다. 자세한 내용은 요소를 참조 하세요 [\<federationConfiguration>](federationconfiguration.md) .  
  
 이 요소는 속성을 설정 합니다 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> .  
  
## <a name="example"></a>예제  

 다음 XML은 리소스 작업 쌍으로 구성 된 정책을 구현 하는 클레임 권한 부여 관리자에 대 한 구성을 보여 줍니다. 각각은 요청자에 게 리소스에 대 한 작업을 수행 하기 위해 소유 해야 하는 클레임의 부울 조합을 지정 합니다. 이 정책을 사용할 수 있는 클레임 권한 부여 관리자를 구현 하는 코드는 샘플에서 찾을 수 있습니다 `ClaimsBasedAuthorization` .  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
