---
title: '방법: 폼에 ToolStripContainer 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 35d35c9cf9bca2720cb6d02d602d2d7bc6740f25
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715323"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a><span data-ttu-id="966c1-102">방법: 폼에 ToolStripContainer 추가</span><span class="sxs-lookup"><span data-stu-id="966c1-102">How to: Add a ToolStripContainer to a Form</span></span>
<span data-ttu-id="966c1-103">프로그래밍 방식으로 <xref:System.Windows.Forms.ToolStripContainer>를 Windows Form에 추가하고 컨트롤로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="966c1-103">You can programmatically add a <xref:System.Windows.Forms.ToolStripContainer> to a Windows Form and populate it with controls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="966c1-104">예제</span><span class="sxs-lookup"><span data-stu-id="966c1-104">Example</span></span>  
 <span data-ttu-id="966c1-105">다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStripContainer> 및 <xref:System.Windows.Forms.ToolStrip>을 Windows Forms에 추가하는 방법, 항목을 <xref:System.Windows.Forms.ToolStrip>에 추가하는 방법, <xref:System.Windows.Forms.ToolStrip>을 <xref:System.Windows.Forms.ToolStripContainer>의 <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="966c1-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.ToolStripContainer> and a <xref:System.Windows.Forms.ToolStrip> to a Windows Forms, how to add items to the <xref:System.Windows.Forms.ToolStrip>, and how to add the <xref:System.Windows.Forms.ToolStrip> to the <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="966c1-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="966c1-106">Compiling the Code</span></span>  
 <span data-ttu-id="966c1-107">이 코드 예제에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="966c1-107">This code example requires:</span></span>  
  
-   <span data-ttu-id="966c1-108">System.Drawing, System.Text 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="966c1-108">References to the System.Drawing, System.Text, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="966c1-109">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="966c1-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="966c1-110">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="966c1-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="966c1-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="966c1-111">See also</span></span>
- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="966c1-112">ToolStripContainer 컨트롤</span><span class="sxs-lookup"><span data-stu-id="966c1-112">ToolStripContainer Control</span></span>](toolstripcontainer-control.md)
- [<span data-ttu-id="966c1-113">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="966c1-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
