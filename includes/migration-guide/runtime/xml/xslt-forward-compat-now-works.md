---
ms.openlocfilehash: 8c8477ae3719cfcc2060459ba85bcc9e76f11c41
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497660"
---
### <a name="xslt-forward-compat-now-works"></a>XSLT forward compat가 이제 작동합니다.

#### <a name="details"></a>설명

.NET Framework 4에서 XSLT 1.0 이후 버전과의 호환성에 다음과 같은 문제가 있었습니다.<ul><li>버전이 2.0으로 설정되고 인식할 수 없는 XSLT 1.0 구문에서 파서가 발생하면 스타일시트를 로드하지 못했습니다.</li><li>스타일시트 버전이 1.1로 설정된 경우 <code>xsl:sort</code> 구문이 데이터를 정렬하지 못했습니다.</li></ul>.NET Framework 4.5에서 이러한 문제가 해결되었고 XSLT 1.0의 다음 버전과의 호환성 모드는 제대로 작동합니다.

#### <a name="suggestion"></a>제안 해결 방법

대부분의 앱은 영향을 받지 않지만 xsl:sort가 적용되어 일부 경우에 데이터가 다른 방식으로 정렬됩니다. 1\.1 스타일 시트에서 <code>xsl:sort</code>를 사용하는 경우 앱이 정렬되지 않은 데이터 순서에 의존하고 있지 않은지 확인하세요. 앱이 4.0 정렬 동작에 의존하면 스타일 시트에서 <code>xsl:sort</code>를 제거합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Xml.Xsl.XslCompiledTransform`

-->
