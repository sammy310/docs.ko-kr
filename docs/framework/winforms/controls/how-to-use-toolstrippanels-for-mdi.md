---
title: '방법: MDI에 ToolStripPanels 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], using ToolStripPanels [Windows Forms]
- ToolStripPanel control [Windows Forms], using for MDI
- toolbars [Windows Forms], using for MDI
ms.assetid: d6b884fc-0846-465f-83c3-5dc0fe93b00f
ms.openlocfilehash: a543b9e292f29e54b45327ae77a81676c992f103
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722063"
---
# <a name="how-to-use-toolstrippanels-for-mdi"></a><span data-ttu-id="83737-102">방법: MDI에 ToolStripPanels 사용</span><span class="sxs-lookup"><span data-stu-id="83737-102">How to: Use ToolStripPanels for MDI</span></span>
<span data-ttu-id="83737-103"><xref:System.Windows.Forms.ToolStripPanel>에서는 <xref:System.Windows.Forms.ToolStripPanel.Join%2A> 메서드를 사용하여 MDI(다중 문서 인터페이스) 응용 프로그램에 대한 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="83737-103">The <xref:System.Windows.Forms.ToolStripPanel> provides flexibility for multiple-document interface (MDI) applications by using the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83737-104">예제</span><span class="sxs-lookup"><span data-stu-id="83737-104">Example</span></span>  
 <span data-ttu-id="83737-105">다음 코드 예제에서는 MDI에 대해 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83737-105">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls for MDI.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="83737-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="83737-106">Compiling the Code</span></span>  
 <span data-ttu-id="83737-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83737-107">This example requires:</span></span>  
  
-   <span data-ttu-id="83737-108">System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="83737-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="83737-109">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83737-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="83737-110">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83737-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83737-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="83737-111">See also</span></span>
- <xref:System.Windows.Forms.ToolStripPanel>
- [<span data-ttu-id="83737-112">방법: ToolStripPanels 조인</span><span class="sxs-lookup"><span data-stu-id="83737-112">How to: Join ToolStripPanels</span></span>](how-to-join-toolstrippanels.md)
