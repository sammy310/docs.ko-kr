---
title: '방법: 마우스 포인터가 ToolStripItem 위에 있는 시점 감지'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 09fd9f2f9b8cc44b6c04b829bf2854bea4aa8cf7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220048"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="edaa3-102">방법: 마우스 포인터가 ToolStripItem 위에 있는 시점 감지</span><span class="sxs-lookup"><span data-stu-id="edaa3-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="edaa3-103">다음 절차를 사용 하 여 마우스 포인터가 위에 있는 시기를 감지 하는 <xref:System.Windows.Forms.ToolStripItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="edaa3-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="edaa3-104">포인터가 toolstripitem을 가리키는 시점 감지 하려면</span><span class="sxs-lookup"><span data-stu-id="edaa3-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="edaa3-105">사용 된 <xref:System.Windows.Forms.ToolStripItem.Selected%2A> 는 항목에 대 한 속성 <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> 는 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="edaa3-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="edaa3-106">동기화 할 필요가 없도록 그러면 합니다 <xref:System.Windows.Forms.ToolStripItem.MouseEnter> 및 <xref:System.Windows.Forms.ToolStripItem.MouseLeave> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="edaa3-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edaa3-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="edaa3-107">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="edaa3-108">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="edaa3-108">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
