---
title: '방법: ToolStrip 항목의 간격 및 맞춤 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 805fbac5fe33071006f29692d503e5c57eacd765
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746556"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>방법: Windows Forms에서 ToolStrip 항목의 간격 및 맞춤 변경
<xref:System.Windows.Forms.ToolStrip> 컨트롤은 크기 조정, 서로 상대적인 <xref:System.Windows.Forms.ToolStripItem> 컨트롤의 간격, <xref:System.Windows.Forms.ToolStrip>의 컨트롤 배열 및 <xref:System.Windows.Forms.ToolStrip>에 상대적인 컨트롤 간격 등의 레이아웃 기능을 완벽 하 게 지원 합니다.  
  
 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성의 기본값은 `true`이므로 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성을 `false`로 설정 하지 않으면 컨트롤 크기가 자동으로 조정 됩니다.  
  
### <a name="to-manually-size-a-toolstripitem"></a>수동으로 ToolStripItem 크기를 조정 하려면  
  
1. 연결 된 컨트롤에 대 한 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성을 `false`로 설정 합니다.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. 연결 된 <xref:System.Windows.Forms.ToolStripItem>에 대해 원하는 방식으로 <xref:System.Windows.Forms.ToolStripItem.Size%2A> 속성을 설정 합니다.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>ToolStripItem의 간격을 설정 하려면  
  
1. 연결 된 컨트롤의 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 속성에 원하는 값 (픽셀)을 삽입 합니다.  
  
     <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 속성 값은 왼쪽, 위쪽, 오른쪽 및 아래쪽 순서로 항목과 인접 항목 사이의 간격을 지정 합니다.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>ToolStripItem을 ToolStrip의 오른쪽에 맞추려면  
  
1. 연결 된 컨트롤에 대 한 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemAlignment.Right>로 설정 합니다. 기본적으로 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>는 <xref:System.Windows.Forms.ToolStrip>의 왼쪽에 컨트롤을 맞추는 <xref:System.Windows.Forms.ToolStripItemAlignment.Left>로 설정 됩니다.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>ToolStrip의 ToolStrip 항목을 정렬 하려면  
  
- <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 속성을 원하는 <xref:System.Windows.Forms.ToolStripLayoutStyle> 값으로 설정 합니다.  
  
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
