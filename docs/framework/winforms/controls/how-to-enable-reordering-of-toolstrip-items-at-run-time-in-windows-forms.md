---
title: '방법: 런타임에 Windows Forms에서 ToolStrip 항목 다시 정렬 활성화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: daff9d6d351db514d552225853f977775f8e3204
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220410"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>방법: 런타임에 Windows Forms에서 ToolStrip 항목 다시 정렬 활성화
다시 정렬 하려면 사용자가 수행할 수 있습니다 <xref:System.Windows.Forms.ToolStripItem> 컨트롤을 <xref:System.Windows.Forms.ToolStrip>입니다.  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>런타임 시 toolstripitem을 가리키는 재배열을 사용 하도록 설정 하려면  
  
-   <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 속성을 `true`으로 설정합니다. 기본적으로 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 는 `false`합니다.  
  
     런타임 시 사용자를 누르고 ALT 키와 마우스 왼쪽된 단추 끌어서를 <xref:System.Windows.Forms.ToolStripItem> 에서 다른 위치로 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)
- [ToolStrip 기술 요약](toolstrip-technology-summary.md)
