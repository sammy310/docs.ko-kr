---
description: 다음에 대해 자세히 알아보세요. <add>
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: c79fb66fb4e87f15c2bf7f2c02e57f473c7262a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681866"
---
# \<add>

지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|type|추가할 토큰 처리기의 CLR 형식 이름입니다. 특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)를 참조 하세요.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>클래스, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 또는 이러한 클래스 중 하나의 파생 클래스에 대 한 구성을 제공 합니다.|  
|[\<sessionTokenRequirement>](sessiontokenrequirement.md)|클래스 또는 파생 클래스에 대 한 구성을 제공 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 합니다.|  
|[\<userNameSecurityTokenHandlerRequirement>](usernamesecuritytokenhandlerrequirement.md)|클래스 또는 파생 클래스에 대 한 구성을 제공 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 합니다.|  
|[\<x509SecurityTokenHandlerRequirement>](x509securitytokenhandlerrequirement.md)|클래스 또는 파생 클래스에 대 한 선택적 구성을 제공 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.|  
  
## <a name="remarks"></a>설명  

 `<add>`요소는 토큰 처리기에 대 한 구성을 지정 하는 단일 자식 요소를 사용할 수 있습니다. 이는 요소의 특성을 통해 참조 되는 처리기 클래스가 `type` 이 기능을 지원 하는지 여부에 따라 달라 집니다 `<add>` . 이 기능을 제공 하는 토큰 처리기 클래스는 개체를 사용 하는 생성자를 노출 해야 합니다 <xref:System.Xml.XmlElement> .  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 몇 가지 기본 제공 보안 토큰 처리기 클래스는이 기능을 제공 합니다. 이러한 클래스는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> ,,, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 및 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 입니다.  
  
> [!IMPORTANT]
> 토큰 처리기 컬렉션에는 지정 된 형식의 단일 처리기만 포함 될 수 있습니다. 예를 들어, 클래스에서 파생 된 처리기를 컬렉션에 추가 하려는 경우 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 먼저 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 컬렉션에서 기본적으로 제공 되는을 제거 해야 합니다. 요소를 사용 하 여 [\<remove>](remove.md) 컬렉션에서 단일 처리기를 제거 하거나 요소를 사용 하 여 [\<clear>](clear.md) 컬렉션에서 모든 처리기를 제거할 수 있습니다.  
  
 처리기에 지정 된 설정은 요소 아래의 토큰 처리기 컬렉션에 지정 된 설정이 [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) 며 요소 아래에서 서비스 수준에 지정 된 설정과 동일 하 게 재정의 [\<identityConfiguration>](identityconfiguration.md) 됩니다.  
  
## <a name="example"></a>예제  

 다음 XML에서는 `<add>` 및 요소를 사용 하 여 `<remove>` 기본 세션 토큰 처리기를 사용자 지정 세션 토큰 처리기로 바꾸는 방법을 보여 줍니다. XML은 샘플에서 가져옵니다 `ClaimsAwareWebFarm` .  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
