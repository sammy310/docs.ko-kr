---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152582"
---
# <a name="servicetokenresolver"></a>\<서비스토큰해결러>
토큰 처리기 컬렉션의 처리기에서 사용되는 서비스 토큰 확인자를 등록합니다. 서비스 토큰 확인기는 들어오는 토큰 및 메시지에서 암호화 토큰을 해결하는 데 사용됩니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기구성>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<서비스토큰 해결사>**  
  
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
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|type|서비스 토큰 확인자의 유형을 지정합니다. <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스에서 파생되는 형식 또는 형식입니다. <xref:System.IdentityModel.Selectors.SecurityTokenResolver> `type` 특성을 지정하는 방법에 대한 자세한 내용은 [사용자 지정 유형 참조]를 참조하십시오. 필수 사항입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 None  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<보안토큰처리기구성>](securitytokenhandlerconfiguration.md)|보안 토큰 처리기 컬렉션에 대 한 구성을 제공 합니다.|  
  
## <a name="remarks"></a>설명  
 서비스 토큰 확인자를 사용하여 들어오는 토큰 및 메시지에서 암호화 토큰을 확인할 수 있습니다. 들어오는 토큰의 암호를 해독하는 데 사용해야 하는 키를 검색하는 데 사용됩니다. 특성을 `type` 지정해야 합니다. 지정된 형식은 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스에서 파생되는 사용자 지정 형식일 수 있습니다.  
  
 일부 토큰 처리기를 사용하면 구성에서 서비스 토큰 확인자 설정을 지정할 수 있습니다. 개별 토큰 처리기의 설정은 보안 토큰 처리기 컬렉션에 지정된 설정을 재정의합니다.  
  
> [!NOTE]
> idConfiguration>요소의 자식 요소로 요소를 지정 하는 데 사용 하지 않습니다. [ \<](identityconfiguration.md) `<serviceTokenResolver>` 요소의 `<securityTokenHandlerConfiguration>` 설정은 요소의 `<identityConfiguration>` 설정을 재정의합니다.  
  
## <a name="example"></a>예제  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
