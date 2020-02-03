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
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="48adf-102">방법: Windows Forms에서 런타임에 ToolStrip 항목 다시 정렬 활성화</span><span class="sxs-lookup"><span data-stu-id="48adf-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="48adf-103">사용자가 <xref:System.Windows.Forms.ToolStrip>에서 <xref:System.Windows.Forms.ToolStripItem> 컨트롤을 다시 정렬할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48adf-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="48adf-104">런타임에 ToolStripItem을 재배치 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="48adf-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
- <span data-ttu-id="48adf-105"><xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="48adf-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="48adf-106">기본적으로 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="48adf-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="48adf-107">런타임에 사용자는 ALT 키를 누르고 마우스 왼쪽 단추를 클릭 하 여 <xref:System.Windows.Forms.ToolStripItem>를 <xref:System.Windows.Forms.ToolStrip>의 다른 위치로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="48adf-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="48adf-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48adf-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [<span data-ttu-id="48adf-109">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="48adf-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="48adf-110">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="48adf-110">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="48adf-111">ToolStrip 기술 요약</span><span class="sxs-lookup"><span data-stu-id="48adf-111">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
