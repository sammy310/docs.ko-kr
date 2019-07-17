---
ms.openlocfilehash: df13f6938ebaf8e96bb2825c1495044621f1c31b
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802584"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>사용자 지정 DataAnnotations.ValidationAttribute를 사용할 때 ASP.NET ValidationContext.MemberName은 NULL이 아닙니다.

|   |   |
|---|---|
|세부 정보|.NET Framework 4.7.2 이하 버전에서 사용자 지정 <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>을 사용할 때 <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> 속성이 <code>null</code>를 반환합니다.  .NET Framework 4.8에서는 멤버 이름을 반환합니다.|
|제안|<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> 속성의 기본 동작은 동일하게 유지됩니다.  <code>ValidationContext.MemberName</code> 속성에서 유효한 값을 검색하려면 다음 설정을 앱 구성 파일에 추가합니다.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|범위|알 수 없음|
|버전|4.8|
|Type|런타임|
|영향을 받는 API|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|

