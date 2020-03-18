---
ms.openlocfilehash: 735278848cb7399e414a128afc650a0a1f882337
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857507"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>모든 자식 컨트롤에 영향을 주는 TextBlock 컨트롤의 부모 IsEnabled 속성 변경

|   |   |
|---|---|
|세부 정보|.NET Framework 4.6.2부터 <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> 컨트롤의 부모 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 속성을 변경하면 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 컨트롤의 모든 자식 컨트롤(예: 하이퍼링크 및 단추)에 영향이 있습니다. .NET Framework 4.6.1 및 이전 버전에서 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 내부의 컨트롤은 항상 <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> 부모의 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 속성 상태를 반영하지 않습니다.|
|제안 해결 방법|없음 이 변경은 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 컨트롤 내부에 있는 컨트롤의 정상적인 동작을 따릅니다.|
|범위|사소함|
|Version|4.6.2|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
