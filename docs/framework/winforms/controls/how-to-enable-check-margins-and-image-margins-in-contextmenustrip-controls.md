---
title: '방법: ContextMenuStrip 컨트롤에서 선택 여백 및 이미지 여백 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ShowCheckMargin property [Windows Forms]
- ShowImageMargin property [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: eb584e71-59da-4012-aaca-dbe1c7c7a156
ms.openlocfilehash: bf8440704a7e457d0c987c933cc26e0e12e9565f
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591696"
---
# <a name="how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls"></a><span data-ttu-id="49560-102">방법: ContextMenuStrip 컨트롤에서 선택 여백 및 이미지 여백 사용</span><span class="sxs-lookup"><span data-stu-id="49560-102">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>
<span data-ttu-id="49560-103">확인 표시와 사용자 지정 이미지를 사용하여 <xref:System.Windows.Forms.MenuStrip> 컨트롤에서 <xref:System.Windows.Forms.ToolStripMenuItem> 개체를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49560-103">You can customize the <xref:System.Windows.Forms.ToolStripMenuItem> objects in your <xref:System.Windows.Forms.MenuStrip> control with check marks and custom images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49560-104">예제</span><span class="sxs-lookup"><span data-stu-id="49560-104">Example</span></span>  
 <span data-ttu-id="49560-105">다음 코드 예제에서는 확인 표시와 사용자 지정 이미지가 있는 메뉴 항목을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="49560-105">The following code example demonstrates how to create menu items that have check marks and custom images.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
 <span data-ttu-id="49560-106"><xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A?displayProperty=nameWithType> 속성을 설정하여 확인 표시와 사용자 지정 이미지가 메뉴 항목에 표시되는 시점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49560-106">Set the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A?displayProperty=nameWithType> properties to specify when check marks and custom images appear in your menu items.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="49560-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="49560-107">Compiling the Code</span></span>  
 <span data-ttu-id="49560-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="49560-108">This example requires:</span></span>  
  
- <span data-ttu-id="49560-109">System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="49560-109">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49560-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="49560-110">See also</span></span>

- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDownMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="49560-111">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="49560-111">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
