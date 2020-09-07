---
ms.openlocfilehash: 31ada197db36be192317e32a37a353d375d9cc65
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496891"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>VirtualizingStackPanel에서 WPF TreeView 또는 그룹화된 ListBox를 스크롤하면 중단될 수 있습니다.

#### <a name="details"></a>설명

.NET Framework v4.5에서 뷰포트에 여백이 있는 경우 가상화된 스택 패널의 WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName>을 스크롤하면 중단이 발생할 수 있습니다(예: 항목 간 <xref:System.Windows.Controls.TreeView?displayProperty=fullName> 또는 ItemsPresenter 요소). 또한 일부 경우에는 보기에서 다양한 크기의 항목은 여백이 없더라도 불안정해 보일 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework 4.5.1로 업그레이드하여 이 버그를 방지할 수 있습니다. 또는 포함된 모든 항목이 같은 크기인 경우 가상화된 스택 패널 내에서 여백을 보기 컬렉션(예: <xref:System.Windows.Controls.TreeView?displayProperty=fullName>)으로부터 제거할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |주요함|
|버전|4.5|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)`

-->
