---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: cebfc2f3598f32f233db6039dfe82076d2ffce46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790483"
---
# <a name="trustedissuers"></a>\<trustedIssuers>
구성 기반 발급자 이름 레지스트리에 사용 되는 신뢰할 수 있는 발급자 인증서의 목록 구성 (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration>  
\<issuerNameRegistry>  
\<trustedIssuers>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|신뢰할 수 있는 발급자의 컬렉션에 인증서를 추가 합니다. 인증서가 지정 된 된 `thumbprint` 특성입니다. 이 특성은 필수 이며 인증서 지 문의 ASN.1 인코딩된 폼을 포함 해야 합니다. `name` 특성은 선택적 이며 인증서에 대 한 친숙 한 이름을 지정 하려면 사용할 수 있습니다.|  
|`<clear>`|신뢰할 수 있는 발급자의 컬렉션에서 모든 인증서를 지웁니다.|  
|`<remove thumbprint=xs:string>`|신뢰할 수 있는 발급자의 컬렉션에서 인증서를 제거합니다. 인증서가 지정 된 된 `thumbprint` 특성입니다. 필수 특성입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|발급자 이름 레지스트리를 구성합니다. **중요:**  `type` 특성을 `<issuerNameRegistry>` 요소를 참조 해야 합니다를 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스를 `<trustedIssuers>` 유효한 요소.|  
  
## <a name="remarks"></a>설명  
 Windows Identity Foundation (WIF)의 단일 구현을 제공 합니다 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 기본적으로 클래스는 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스입니다. 구성 발급자 이름 레지스트리 구성에서 로드 되는 신뢰할 수 있는 발급자 목록을 유지 관리 합니다. 각 발급자 이름은 X.509 인증서 발급자가 생성 한 토큰의 서명을 확인 하는 데 필요한 연결 합니다. 신뢰할 수 있는 발급자 인증서 목록에서 지정 된 `<trustedIssuers>` 요소입니다. 목록의 각 요소는 해당 발급자가 생성 한 토큰의 서명을 확인 하는 데 필요한 X.509 인증서를 사용 하 여 니모닉 발급자 이름을 연결 합니다. 인증서의 인증서 지문 인코딩된 ASN.1를 사용 하 여 지정 되 고 사용 하 여 컬렉션을 추가 하는 신뢰할 수 있는 `<add>` 요소입니다. 지우거 나 목록에서 발급자 (인증서)를 사용 하 여 제거할 수 있습니다 합니다 `<clear>` 고 `<remove>` 요소입니다.  
  
 `type` 특성을 `<issuerNameRegistry>` 요소를 참조 해야 합니다를 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스를 `<trustedIssuers>` 유효한 요소.  
  
## <a name="example"></a>예제  
 다음 XML 기반 구성을 발급자를 지정 하는 방법을 이름 레지스트리를 보여 줍니다.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
