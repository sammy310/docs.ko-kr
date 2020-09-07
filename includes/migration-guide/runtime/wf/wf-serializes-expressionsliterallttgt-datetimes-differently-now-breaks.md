---
ms.openlocfilehash: 06424c4fa40343a881356c20003300f65e93efbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496716"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>WF가 Expressions.Literal&lt;T&gt; DateTimes를 직렬화합니다(사용자 지정 XAML 파서 중단).

#### <a name="details"></a>설명

연결된 <xref:System.Windows.Markup.ValueSerializer> 개체는 두 번째 및 <xref:System.DateTime.Millisecond?displayProperty=fullName> 구성 요소가 0이 아니고(<xref:System.DateTime?displayProperty=fullName> 값의 경우) <xref:System.DateTime.Kind> 속성이 지정되지 않은 <xref:System.DateTime?displayProperty=fullName> 또는 <xref:System.DateTimeOffset?displayProperty=fullName> 개체를 문자열 대신에 속성 요소 구문으로 변환합니다. 이 변경은 <xref:System.DateTime?displayProperty=fullName> 및 <xref:System.DateTimeOffset?displayProperty=fullName> 값이 라운드트립되는 것을 허용합니다. 입력 XAML이 특성 구문에 있다고 가정하는 사용자 지정 XAML 파서가 올바르게 작동하지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

이 변경은 <xref:System.DateTime?displayProperty=fullName> 및 <xref:System.DateTimeOffset?displayProperty=fullName> 값이 라운드트립되는 것을 허용합니다. 입력 XAML이 특성 구문에 있다고 가정하는 사용자 지정 XAML 파서가 올바르게 작동하지 않습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
