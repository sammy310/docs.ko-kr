---
ms.openlocfilehash: e2d63d85adce64db6e00b62ec17f55ae71ce3052
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803274"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>CellEditEnding 처리기에서 DataGrid.CommitEdit를 호출하면 포커스가 사라집니다.

|   |   |
|---|---|
|세부 정보|<xref:System.Windows.Controls.DataGrid?displayProperty=name>의 <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> 이벤트 처리기 중 하나에서 <xref:System.Windows.Controls.DataGrid.CommitEdit>을 호출하면 <xref:System.Windows.Controls.DataGrid?displayProperty=name>가 포커스를 잃게 됩니다.|
|제안 해결 방법|이 버그는 .NET Framework 4.5.2에서 수정되었으므로 .NET Framework를 업그레이드하여 방지할 수 있습니다. 또는 <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>을 호출한 후에 <xref:System.Windows.Controls.DataGrid?displayProperty=name>을 명시적으로 다시 선택하여 방지할 수 있습니다.|
|범위|가장자리|
|Version|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
