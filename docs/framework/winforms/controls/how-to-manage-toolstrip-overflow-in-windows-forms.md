---
title: '방법: ToolStrip 오버플로 관리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736150"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>방법: Windows Forms의 ToolStrip 오버플로 관리

<xref:System.Windows.Forms.ToolStrip> 컨트롤의 모든 항목이 할당 된 공간에 맞지 않는 경우 <xref:System.Windows.Forms.ToolStrip>에서 오버플로 기능을 사용 하도록 설정 하 고 특정 <xref:System.Windows.Forms.ToolStripItem>s의 오버플로 동작을 결정할 수 있습니다.

양식의 현재 크기에 따라 <xref:System.Windows.Forms.ToolStrip>에 할당 된 것 보다 더 많은 공간이 필요한 <xref:System.Windows.Forms.ToolStripItem>을 추가 하면 <xref:System.Windows.Forms.ToolStrip>에 <xref:System.Windows.Forms.ToolStripOverflowButton> 자동으로 표시 됩니다. <xref:System.Windows.Forms.ToolStripOverflowButton> 나타나고 오버플로 사용 항목이 드롭다운 오버플로 메뉴로 이동 합니다. 이를 통해 <xref:System.Windows.Forms.ToolStrip> 항목이 다른 폼 크기로 적절히 조정 되는 방법을 사용자 지정 하 고 우선 순위를 정할 수 있습니다. <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 및 <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> 속성 및 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 이벤트를 사용 하 여 오버플로에 도달 하는 경우 항목의 모양을 변경할 수도 있습니다. 디자인 타임 또는 런타임에 폼을 확대 하는 경우 주 <xref:System.Windows.Forms.ToolStrip>에 더 많은 <xref:System.Windows.Forms.ToolStripItem>s를 표시할 수 있으며 폼의 크기를 줄일 때까지 <xref:System.Windows.Forms.ToolStripOverflowButton> 사라질 수도 있습니다.

## <a name="to-enable-overflow-on-a-toolstrip-control"></a>ToolStrip 컨트롤에서 오버플로를 사용 하도록 설정 하려면

- <xref:System.Windows.Forms.ToolStrip>에 대해 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 속성이 `false`로 설정 되어 있지 않은지 확인 합니다. 기본값은 `True`입니다.

     <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> `True` (기본값) 이면 <xref:System.Windows.Forms.ToolStripItem>의 내용이 가로 <xref:System.Windows.Forms.ToolStrip>의 너비 또는 세로 <xref:System.Windows.Forms.ToolStrip>높이를 초과할 때 드롭다운 오버플로 메뉴로 <xref:System.Windows.Forms.ToolStripItem> 전송 됩니다.

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>특정 ToolStripItem의 오버플로 동작을 지정 하려면

- <xref:System.Windows.Forms.ToolStripItem>의 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 속성을 원하는 값으로 설정 합니다. 가능성은 `Always`, `Never`및 `AsNeeded`입니다. 기본값은 `AsNeeded`입니다.

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)
- [ToolStrip 기술 요약](toolstrip-technology-summary.md)
