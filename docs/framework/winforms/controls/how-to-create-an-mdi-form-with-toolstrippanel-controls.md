---
title: '방법: ToolStripPanel 컨트롤을 사용하여 MDI 양식 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms [Windows Forms]
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
ms.assetid: d198ef8e-f7c4-4b3f-a7f5-ce858cb90cec
ms.openlocfilehash: 55c2294496800fb8692d3c8215c1c13f7dac9b01
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746984"
---
# <a name="how-to-create-an-mdi-form-with-toolstrippanel-controls"></a><span data-ttu-id="2141d-102">방법: ToolStripPanel 컨트롤을 사용하여 MDI 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="2141d-102">How to: Create an MDI Form with ToolStripPanel Controls</span></span>
<span data-ttu-id="2141d-103">네 면에서 모두 폼을 프레이밍하는 <xref:System.Windows.Forms.ToolStrip> 컨트롤이 있는 MDI(다중 문서 인터페이스) 폼을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2141d-103">You can create a multiple document interface (MDI) form that has <xref:System.Windows.Forms.ToolStrip> controls framing it on all four sides.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2141d-104">예제</span><span class="sxs-lookup"><span data-stu-id="2141d-104">Example</span></span>  
 <span data-ttu-id="2141d-105">다음 코드 예제에서는 도킹된 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 사용하여 <xref:System.Windows.Forms.ToolStrip> 컨트롤 네 개로 MDI 창을 프레이밍하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2141d-105">The following code example demonstrates how to use docked <xref:System.Windows.Forms.ToolStripPanel> controls to frame an MDI window with four <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="2141d-106">예제에서 <xref:System.Windows.Forms.ToolStripPanel.Join%2A> 메서드는 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 일치하는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2141d-106">In the example, the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method attaches the <xref:System.Windows.Forms.ToolStrip> controls to the corresponding <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2141d-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="2141d-107">Compiling the Code</span></span>  
 <span data-ttu-id="2141d-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2141d-108">This example requires:</span></span>  
  
- <span data-ttu-id="2141d-109">System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="2141d-109">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="2141d-110">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2141d-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="2141d-111">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2141d-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2141d-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="2141d-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- <xref:System.Windows.Forms.ToolStripPanel.Join%2A>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="2141d-113">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2141d-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
