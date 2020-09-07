---
ms.openlocfilehash: 25ce391f917bd270d4d9a75f608e4a8ec763d15c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496491"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a>Items.Clear는 SelectedItems에서 중복 항목을 제거하지 않습니다.

#### <a name="details"></a>설명

선택기(다중 항목 선택 가능)의 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> 컬렉션에 중복 항목이 있을 경우 동일한 항목이 두 번 이상 나타납니다.  데이터 소스에서 해당 항목을 제거하면(예: Items.Clear를 호출하여) <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> 컬렉션에서 제거할 수 없으며, 첫 번째 인스턴스만 제거됩니다. 또한 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>에 더 이상 데이터 소소에 없는 항목이 있기 때문에, <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>(예: SelectedItems.Clear())을 계속 사용하면 <xref:System.ArgumentException?displayProperty=fullName>과 같은 문제가 발생할 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

가능한 경우 .NET Framework 4.6.2로 업그레이드하세요.

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.5|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.MultiSelector.SelectedItems`

-->
