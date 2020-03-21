---
title: '방법: 도구 스트립 항목의 간격 및 정렬 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182237"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>방법: Windows Forms에서 ToolStrip 항목의 간격 및 맞춤 변경
컨트롤은 <xref:System.Windows.Forms.ToolStrip> 크기 조정, 서로에 대한 <xref:System.Windows.Forms.ToolStripItem> 컨트롤의 간격, <xref:System.Windows.Forms.ToolStrip>에 대한 컨트롤의 배열 및 <xref:System.Windows.Forms.ToolStrip>에 대한 컨트롤의 간격과 같은 레이아웃 기능을 완벽하게 지원합니다.  
  
 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성의 기본값은 `true`에서 속성을 설정하지 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 않으면 컨트롤의 크기가 자동으로 조정됩니다. `false`  
  
### <a name="to-manually-size-a-toolstripitem"></a>수동으로 도구 스트립 항목의 크기를 조정하려면  
  
1. 연결된 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> `false` 컨트롤에 대한 속성을 설정합니다.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. 연결된 <xref:System.Windows.Forms.ToolStripItem> <xref:System.Windows.Forms.ToolStripItem.Size%2A> 에 대해 원하는 방식으로 속성을 설정합니다.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>도구스트립항목의 간격을 설정하려면  
  
1. 원하는 값을 픽셀 단위로 연관된 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 컨트롤의 속성에 삽입합니다.  
  
     <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 속성값은 항목과 인접 항목 사이의 간격을 왼쪽, 위쪽, 오른쪽 및 아래쪽 순서로 지정합니다.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>도구 스트립의 오른쪽에 ToolStrip항목을 정렬하려면  
  
1. 연결된 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> <xref:System.Windows.Forms.ToolStripItemAlignment.Right> 컨트롤에 대한 속성을 설정합니다. 기본적으로 은의 왼쪽에 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> <xref:System.Windows.Forms.ToolStripItemAlignment.Left> <xref:System.Windows.Forms.ToolStrip>컨트롤을 정렬하는 로 설정됩니다.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>도구 스트립에서 도구 스트립 항목을 정렬하려면  
  
- <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 속성을 원하는 값으로 <xref:System.Windows.Forms.ToolStripLayoutStyle> 설정합니다.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)
- [ToolStrip 기술 요약](toolstrip-technology-summary.md)
