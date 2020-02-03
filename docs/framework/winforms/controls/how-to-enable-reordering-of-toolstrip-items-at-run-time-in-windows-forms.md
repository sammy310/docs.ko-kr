---
title: '방법: 런타임에 ToolStrip 항목 다시 정렬 활성화'
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
ms.openlocfilehash: 44b52bf997819f090569d08eb395d8af18f61370
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745482"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>방법: Windows Forms에서 런타임에 ToolStrip 항목 다시 정렬 활성화
사용자가 <xref:System.Windows.Forms.ToolStrip>에서 <xref:System.Windows.Forms.ToolStripItem> 컨트롤을 다시 정렬할 수 있도록 설정할 수 있습니다.  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>런타임에 ToolStripItem을 재배치 하도록 설정 하려면  
  
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 속성을 `true`로 설정합니다. 기본적으로 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 는 `false`합니다.  
  
     런타임에 사용자는 ALT 키를 누르고 마우스 왼쪽 단추를 클릭 하 여 <xref:System.Windows.Forms.ToolStripItem>를 <xref:System.Windows.Forms.ToolStrip>의 다른 위치로 끕니다.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)
- [ToolStrip 기술 요약](toolstrip-technology-summary.md)
