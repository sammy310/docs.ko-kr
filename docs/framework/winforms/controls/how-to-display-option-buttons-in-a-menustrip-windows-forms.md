---
title: '방법: MenuStrip에 옵션 단추 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: f3010e71396ce562e9dbdefd4b75b36f3a81ffb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735519"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>방법: MenuStrip에 옵션 단추 표시(Windows Forms)

라디오 단추 라고도 하는 옵션 단추는 사용자가 한 번에 하나만 선택할 수 있다는 점만 제외 하 고 확인란과 비슷합니다. 기본적으로 <xref:System.Windows.Forms.ToolStripMenuItem> 클래스는 옵션 단추 동작을 제공 하지 않지만, 클래스는 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 메뉴 항목에 대 한 옵션 단추 동작을 구현 하기 위해 사용자 지정할 수 있는 확인란 동작을 제공 합니다.

메뉴 항목의 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 속성이 `true`되 면 사용자는 항목을 클릭 하 여 확인 표시를 설정/해제할 수 있습니다. <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성은 항목의 현재 상태를 나타냅니다. 기본 옵션 단추 동작을 구현 하려면 항목을 선택 하는 경우 이전에 선택한 항목에 대 한 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성을 `false`으로 설정 해야 합니다.

다음 절차에서는 <xref:System.Windows.Forms.ToolStripMenuItem> 클래스를 상속 하는 클래스에서이 기능과 추가 기능을 구현 하는 방법을 설명 합니다. `ToolStripRadioButtonMenuItem` 클래스는 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> 및 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>와 같은 멤버를 재정의 하 여 옵션 단추의 선택 동작과 모양을 제공 합니다. 또한이 클래스는 부모 항목을 선택 하지 않으면 하위 메뉴의 옵션을 사용할 수 없도록 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 재정의 합니다.

## <a name="to-implement-option-button-selection-behavior"></a>옵션-단추 선택 동작을 구현 하려면

1. `true` <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 속성을 초기화 하 여 항목을 선택할 수 있도록 합니다.

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. 새 항목이 선택 될 때 이전에 선택한 항목의 선택을 취소 하려면 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> 메서드를 재정의 합니다.

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. 이미 선택 된 항목을 클릭 하면 선택 영역이 지워지지 않도록 <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> 메서드를 재정의 합니다.

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a>옵션 단추 항목의 모양을 수정 하려면

1. <xref:System.Windows.Forms.RadioButtonRenderer> 클래스를 사용 하 여 기본 확인 표시를 옵션 단추로 바꾸도록 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 메서드를 재정의 합니다.

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>및 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> 메서드를 재정의 하 여 마우스 상태를 추적 하 고 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 메서드가 올바른 옵션 단추 상태를 그리는지 확인 합니다.

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>부모 항목을 선택 하지 않은 경우 하위 메뉴에서 옵션을 사용 하지 않으려면

1. <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 재정의 하 여 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 값이 `true`이 고 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 값이 `false`인 부모 항목이 있을 때 항목이 비활성화 되도록 합니다.

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. 부모 항목의 <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> 이벤트를 구독 하도록 <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> 메서드를 재정의 합니다.

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. 부모 항목 <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> 이벤트에 대 한 처리기에서 항목을 무효화 하 여 새 활성화 상태로 표시를 업데이트 합니다.

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a>예

다음 코드 예제에서는 `ToolStripRadioButtonMenuItem` 클래스 전체를 제공 하 고 <xref:System.Windows.Forms.Form> 클래스와 `Program` 클래스를 제공 하 여 옵션 단추 동작을 보여 줍니다.

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

- System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [MenuStrip 컨트롤](menustrip-control-windows-forms.md)
- [방법: 사용자 지정 ToolStripRenderer 구현](how-to-implement-a-custom-toolstriprenderer.md)
