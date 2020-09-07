---
ms.openlocfilehash: bca76daca6e9c424377a80aa56e1a5ff191be5ca
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497861"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>사용자 지정 DataTemplate를 사용하는 경우 일시적으로 ItemsControls에서(예: ListBox 및 DataGrid) 하위 항목으로 스크롤할 수 없습니다.

#### <a name="details"></a>설명

일부 인스턴스에서 .NET Framework 4.5의 버그는 사용자 지정 DataTemplates를 사용할 때 ItemsControls(예: <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> 등)가 아래 항목으로 스크롤되지 않게 합니다. 스크롤이 두 번째 시도되는 경우(스크롤 백업 후) 그때에는 작동합니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework 4.5.2에서 이 문제가 수정되어 해당 버전(또는 이후 버전)의 .NET Framework로 업그레이드하여 해결할 수 있습니다. 또는 사용자가 이러한 컬렉션의 마지막 항목까지 스크롤 막대를 끌 수 있지만 성공하려면 두 번 시도해야 할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.5|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
