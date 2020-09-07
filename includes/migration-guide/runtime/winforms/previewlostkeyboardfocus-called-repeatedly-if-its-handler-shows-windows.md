---
ms.openlocfilehash: c4a3d903894027a01d32ca132d1233da9d9c3ee5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496468"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>PreviewLostKeyboardFocus는 처리기가 Windows Forms 메시지 상자를 표시하는 경우 반복적으로 호출됩니다.

#### <a name="details"></a>설명

.NET Framework 4.5부터 <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> 처리기에서 <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>를 호출하면 메시지 상자가 닫힐 때 처리기가 다시 발생하여 잠재적으로 메시지 상자의 무한 루프를 발생시킵니다.

#### <a name="suggestion"></a>제안 해결 방법

이 문제는 다음 두 가지 옵션으로 해결할 수 있습니다.<ol><li>이것은 <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> 대신 <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType>를 호출하여 방지할 수 있습니다.</li><li>이것은 <xref:System.Windows.UIElement.LostKeyboardFocus> 이벤트 처리기에서 메시지 박스를 표시하여 방지할 수 있습니다(<xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName> 이벤트 처리기와 반대).</li></ol>

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType>

<!--

#### Affected APIs

- `E:System.Windows.ContentElement.PreviewLostKeyboardFocus`
- `E:System.Windows.IInputElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement3D.PreviewLostKeyboardFocus`

-->
