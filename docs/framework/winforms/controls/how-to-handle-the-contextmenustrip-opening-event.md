---
title: '방법: ContextMenuStrip Opening 이벤트 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: 3001480959ef90cb31048cbcf70aeff1632979fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941299"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="31bfe-102">방법: ContextMenuStrip Opening 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="31bfe-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="31bfe-103">동작을 사용자 지정할 수 있습니다 하 <xref:System.Windows.Forms.ContextMenuStrip> 처리 하 여 컨트롤을 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="31bfe-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31bfe-104">예제</span><span class="sxs-lookup"><span data-stu-id="31bfe-104">Example</span></span>  
 <span data-ttu-id="31bfe-105">다음 코드 예제에서는 처리 하는 방법에 설명 합니다 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="31bfe-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="31bfe-106">이벤트 처리기를 추가 하는 동적으로 항목을 <xref:System.Windows.Forms.ContextMenuStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bfe-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="31bfe-107">전체 코드 예제를 보려면 [방법: 동적으로 ToolStrip 항목 추가](how-to-add-toolstrip-items-dynamically.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31bfe-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="31bfe-108">설정 된 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> 속성을 `true` 메뉴 열리지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bfe-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31bfe-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="31bfe-109">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="31bfe-110">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="31bfe-110">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
