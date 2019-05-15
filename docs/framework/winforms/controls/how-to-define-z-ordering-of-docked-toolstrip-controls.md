---
title: '방법: 도킹된 ToolStrip 컨트롤의 Z 순서 정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], specifying z-order
- z-order
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
ms.openlocfilehash: 514c9dd1c91adcadf6f5d383ba734886dec3151d
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591908"
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a><span data-ttu-id="a26b1-102">방법: 도킹된 ToolStrip 컨트롤의 Z 순서 정의</span><span class="sxs-lookup"><span data-stu-id="a26b1-102">How to: Define Z-Ordering of Docked ToolStrip Controls</span></span>
<span data-ttu-id="a26b1-103">도킹을 사용하여 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 올바르게 배치하려면 폼의 z 순서에 컨트롤을 올바르게 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26b1-103">To position a <xref:System.Windows.Forms.ToolStrip> control correctly with docking, you must position the control correctly in the form's z-order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a26b1-104">예제</span><span class="sxs-lookup"><span data-stu-id="a26b1-104">Example</span></span>  
 <span data-ttu-id="a26b1-105">다음 코드 예제에서는 z 순서를 지정하여 <xref:System.Windows.Forms.ToolStrip> 컨트롤 및 도킹된 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a26b1-105">The following code example demonstrates how to arrange a <xref:System.Windows.Forms.ToolStrip> control and a docked <xref:System.Windows.Forms.MenuStrip> control by specifying the z-order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 <span data-ttu-id="a26b1-106">z 순서는 <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="a26b1-106">The z-order is determined by the order in which the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip></span></span>  
  
 <span data-ttu-id="a26b1-107">컨트롤이 폼의 <xref:System.Windows.Forms.Control.Controls%2A> 컬렉션에 추가된 순서에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a26b1-107">controls are added to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 <span data-ttu-id="a26b1-108">이러한 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> 메서드 호출 순서를 반대로 바꾸고 레이아웃에 미치는 영향을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a26b1-108">Reverse the order of these calls to the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method and view the effect on the layout.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a26b1-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a26b1-109">Compiling the Code</span></span>  
 <span data-ttu-id="a26b1-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a26b1-110">This example requires:</span></span>  
  
- <span data-ttu-id="a26b1-111">System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="a26b1-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a26b1-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="a26b1-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>
- <xref:System.Windows.Forms.Control.Controls%2A>
- <xref:System.Windows.Forms.Control.Dock%2A>
- [<span data-ttu-id="a26b1-113">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a26b1-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
