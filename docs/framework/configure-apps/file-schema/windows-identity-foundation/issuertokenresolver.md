---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152673"
---
# <a name="issuertokenresolver"></a>\<발행자토큰해결러>
토큰 처리기 컬렉션의 처리기에서 사용되는 발급자 토큰 확인자를 등록합니다. 발급자 토큰 확인기는 들어오는 토큰 및 메시지에 서명 토큰을 해결하는 데 사용됩니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기구성>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<발행자토큰해결러>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
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
|type|발급자 토큰 확인자의 유형을 지정합니다. <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 클래스 또는 클래스에서 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 파생 되는 형식 이어야 합니다. 필수 사항입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 None  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<보안토큰처리기구성>](securitytokenhandlerconfiguration.md)|보안 토큰 처리기 컬렉션에 대 한 구성을 제공 합니다.|  
  
## <a name="remarks"></a>설명  
 발급자 토큰 확인기는 들어오는 토큰 및 메시지에 서명 토큰을 해결하는 데 사용됩니다. 서명을 확인하는 데 사용되는 암호화 자료를 검색하는 데 사용됩니다. 특성을 `type` 지정해야 합니다. 지정된 형식은 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 클래스에서 파생되는 사용자 지정 형식일 수 있습니다.  
  
 일부 토큰 처리기를 사용하면 구성에서 발급자 토큰 확인자 설정을 지정할 수 있습니다. 개별 토큰 처리기의 설정은 보안 토큰 처리기 컬렉션에 지정된 설정을 재정의합니다.  
  
> [!NOTE]
> idConfiguration>요소의 자식 요소로 요소를 지정 하는 데 사용 하지 않습니다. [ \<](identityconfiguration.md) `<issuerTokenResolver>` 요소의 `<securityTokenHandlerConfiguration>` 설정은 요소의 `<identityConfiguration>` 설정을 재정의합니다.  
  
## <a name="example"></a>예제  
 다음 XML은 에서 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>파생된 사용자 지정 클래스를 기반으로 하는 발급자 토큰 확인자의 구성을 보여 주며 있습니다. 토큰 확인프로그램은 클래스에 정의된 사용자 지정 구성 요소()`<AddAudienceKeyPair>`에서 초기화되는 잠재고객 키 쌍의 사전을 유지 관리합니다. 클래스는 이 <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> 요소를 처리하는 메서드를 재정의합니다. 재정의는 다음 예제에 나와 있습니다. 그러나 호출하는 메서드는 간결성을 위해 표시되지 않습니다. 전체 예제는 `CustomToken` 샘플을 참조하십시오.  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a>예제
  
```csharp
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```
  
## <a name="see-also"></a>참고 항목

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
