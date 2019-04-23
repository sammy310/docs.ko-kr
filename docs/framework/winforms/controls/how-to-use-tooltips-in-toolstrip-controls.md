---
title: '방법: ToolStrip 컨트롤에서 도구 설명 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: ffaf859fafc87131de525f7bf2f52db421a208c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317001"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>방법: ToolStrip 컨트롤에서 도구 설명 사용
표시할 수 있습니다는 <xref:System.Windows.Forms.ToolTip> 에 대 한 합니다 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 설정 하 여 원하는 컨트롤 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 속성을 `true`입니다.  
  
### <a name="to-display-a-tooltip"></a>도구 설명이 표시  
  
-   설정 된 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 컨트롤의 속성 `true`합니다.  
  
     기본값인 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> 은 `true`, 및 기본값인 <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> 는 `false`합니다.  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>도구 설명 텍스트를 ToolStripButton의 ToolTipText 속성을 사용 하도록  
  
1. 설정 된 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 하는 단추의 속성 `true`합니다.  
  
2. 설정 된 <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> 하는 단추의 속성 `false`합니다.  
  
     합니다 `AutoToolTip` 속성은 `true` 에 대해 기본적으로 <xref:System.Windows.Forms.ToolStripButton>를 <xref:System.Windows.Forms.ToolStripDropDownButton>, 및 <xref:System.Windows.Forms.ToolStripSplitButton>합니다.  
  
     A <xref:System.Windows.Forms.ToolStripButton> 사용 하 여 해당 `Text` 속성에 대 한는 <xref:System.Windows.Forms.ToolTip> 기본적으로는 텍스트입니다. 이 절차의 사용자 지정 텍스트를 표시 하는 <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>합니다.  
  
> [!NOTE]
>  설정 하는 경우 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 하 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> 또는 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, 텍스트가 없는 단추를 나타나지만 도구 설명도 표시 됩니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
