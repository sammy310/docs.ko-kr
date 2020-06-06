---
title: <add>of <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: f6948052c62684faa734b592f5bdfc2e7827a07a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153102"
---
# <a name="add-of-claimtyperequirements-element"></a>\<add>of \<claimTypeRequirements> 요소
페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다. 예를 들어, 서비스는 특정 집합의 클레임 형식이어야 하는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**
  
## <a name="syntax"></a>구문  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|claimType|클레임의 형식을 정의하는 URI입니다. 예를 들어 웹 사이트에서 제품을 구매하려면 사용자는 신용 한도가 충분한 유효한 신용 카드를 제공해야 합니다. 이 경우 클레임 형식은 신용 카드 URI가 됩니다.|  
|isOptional|클레임이 선택적 요소인지 여부를 지정하는 부울 값입니다. 필수 클레임인 경우 이 특성을 `false`로 설정합니다.<br /><br /> 서비스가 특정 정보를 요청하지만 이 정보가 필수 요소가 아닌 경우 이 특성을 사용할 수 있습니다. 예를 들어 사용자에 게 이름, 성 및 주소를 입력 해야 하지만 전화 번호는 선택 사항임을 결정 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|필요한 클레임 형식의 컬렉션을 지정합니다. 각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.<br /><br /> 페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다. 예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다. 이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다. 예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다. 이 요구 사항은 보안 정책에 명시됩니다. 클라이언트가 페더레이션 서비스에서 CardSpace와 같은 자격 증명을 요청하면 요구 사항을 토큰 요청(RequestSecurityToken)으로 가져가서 페더레이션 서비스가 요구 사항을 충족시키는 자격 증명을 발급할 수 있게 합니다.  
  
## <a name="example"></a>예제  
 다음 구성은 두 개의 클레임 형식 요구 사항을 보안 바인딩에 추가합니다.  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="myFederatedBinding">
      <security mode="Message">
        <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">
          <claimTypeRequirements>
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress" />
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"
                 optional="true" />
          </claimTypeRequirements>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
