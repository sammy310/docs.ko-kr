---
ms.openlocfilehash: 395463225e3c1f1d168dd019ea75966ad54e5a8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621261"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>모든 자식 컨트롤에 영향을 주는 TextBlock 컨트롤의 부모 IsEnabled 속성 변경

#### <a name="details"></a>세부 정보

.NET Framework 4.6.2부터 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 컨트롤의 부모 <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> 속성을 변경하면 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 컨트롤의 모든 자식 컨트롤(예: 하이퍼링크 및 단추)에 영향이 있습니다. .NET Framework 4.6.1 및 이전 버전에서 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 내부의 컨트롤은 항상 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 부모의 <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> 속성 상태를 반영하지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

없음 이 변경은 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 컨트롤 내부에 있는 컨트롤의 정상적인 동작을 따릅니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.6.2|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
