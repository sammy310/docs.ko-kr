---
title: '방법: ToolStrip 텍스트 및 이미지의 모양 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
ms.openlocfilehash: 7816e138e44554683c201895ece1f886ace8bfa6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746600"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a>방법: Windows Forms에서 ToolStrip 텍스트 및 이미지의 모양 변경
텍스트 및 이미지가 <xref:System.Windows.Forms.ToolStripItem>에 표시 되는지 여부와 서로 상대적 <xref:System.Windows.Forms.ToolStrip>으로 정렬 되는 방법을 제어할 수 있습니다.  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a>ToolStripItem에 표시 되는 항목을 정의 하려면  
  
- <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 원하는 값으로 설정 합니다. 이러한 가능성은 `Image`, `ImageAndText`, `None`및 `Text`입니다. 기본값은 `ImageAndText`입니다.  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a>ToolStripItem에서 텍스트를 맞추려면  
  
- <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> 속성을 원하는 값으로 설정 합니다. 가능한 것은 왼쪽, 가운데 및 오른쪽의 위쪽, 가운데 및 아래쪽 조합입니다. 기본값은 `MiddleCenter`입니다.  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a>ToolStripItem에서 이미지를 맞추려면  
  
- <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> 속성을 원하는 값으로 설정 합니다. 가능한 것은 왼쪽, 가운데 및 오른쪽의 위쪽, 가운데 및 아래쪽 조합입니다. 기본값은 `MiddleLeft`입니다.  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a>ToolStripItem 텍스트 및 이미지가 서로를 기준으로 표시 되는 방법을 정의 하려면  
  
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> 속성을 원하는 값으로 설정 합니다. 가능성은 `ImageAboveText`, `ImageBeforeText`를 `Overlay`합니다 `TextAboveImage`, 및 `TextBeforeImage`합니다. 기본값은 `ImageBeforeText`입니다.  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.ToolStrip>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)
- [ToolStrip 기술 요약](toolstrip-technology-summary.md)
