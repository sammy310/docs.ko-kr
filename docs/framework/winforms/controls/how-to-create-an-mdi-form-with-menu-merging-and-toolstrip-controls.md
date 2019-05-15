---
title: '방법: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 양식 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: 0edcc27968c55908cda0e881ed66f83323316711
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591311"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="28992-102">방법: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="28992-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="28992-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스는 MDI(다중 문서 인터페이스) 응용 프로그램을 지원하고 <xref:System.Windows.Forms.MenuStrip> 컨트롤은 메뉴 병합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="28992-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="28992-104">MDI 폼은 <xref:System.Windows.Forms.ToolStrip> 컨트롤일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28992-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="28992-105">Visual Studio에서이 기능에 대해 폭넓게 지원이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28992-105">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="28992-106">또한 참조 [연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용 하 여 MDI 폼 만들기](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="28992-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="28992-107">예제</span><span class="sxs-lookup"><span data-stu-id="28992-107">Example</span></span>  
 <span data-ttu-id="28992-108">다음 코드 예제에서는 MDI 폼과 함께 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28992-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="28992-109">폼은 자식 메뉴와 메뉴 병합도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="28992-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="28992-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="28992-110">Compiling the Code</span></span>  
 <span data-ttu-id="28992-111">이 코드 예제에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="28992-111">This code example requires:</span></span>  
  
- <span data-ttu-id="28992-112">System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="28992-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28992-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="28992-113">See also</span></span>

- [<span data-ttu-id="28992-114">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="28992-114">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
