---
ms.openlocfilehash: 7002c74594993ac6bf28643ef3271da356190c66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622067"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>사용자 지정 DataAnnotations.ValidationAttribute를 사용할 때 ASP.NET ValidationContext.MemberName은 NULL이 아닙니다.

#### <a name="details"></a>설명

.NET Framework 4.7.2 이하 버전에서 사용자 지정 <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>을 사용할 때 <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> 속성이 `null`를 반환합니다. 2019년 10월 업데이트 이전의 .NET Framework 4.8 버전에서는 멤버 이름을 반환합니다. .NET Framework 4.8의 [.NET Framework 2019년 10월 품질 롤업 미리 보기](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/)부터 기본적으로 `null`을 반환하지만 대신 멤버 이름을 반환하도록 옵트인할 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework 4.8 이상 버전의 [.NET Framework 2019년 10월 품질 롤업 미리 보기](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/)에서 이 속성이 멤버 이름을 반환하려면 *web.config* 파일에 다음 설정을 추가합니다.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>2019년 10월 업데이트 이전의 .NET Framework 4.8 버전에서는 *web.config* 파일에 이를 추가하면 이전 동작이 복원되고 속성이 `null`을 반환합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |알 수 없음|
|버전|4.8|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
