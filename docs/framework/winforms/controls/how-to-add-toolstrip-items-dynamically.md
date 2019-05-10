---
title: '방법: 동적으로 ToolStrip 항목 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- toolbars [Windows Forms], adding items dynamically
- ToolStrip control [Windows Forms]
ms.assetid: 0e8dea56-5f46-408b-914d-7e360341a234
ms.openlocfilehash: 9426c7cb3251dbbd95727b78c57be7a0b71556e2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624024"
---
# <a name="how-to-add-toolstrip-items-dynamically"></a><span data-ttu-id="e4cbf-102">방법: 동적으로 ToolStrip 항목 추가</span><span class="sxs-lookup"><span data-stu-id="e4cbf-102">How to: Add ToolStrip Items Dynamically</span></span>
<span data-ttu-id="e4cbf-103">메뉴가 열릴 때 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 메뉴 항목 컬렉션을 동적으로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4cbf-103">You can dynamically populate the menu item collection of a <xref:System.Windows.Forms.ToolStrip> control when the menu opens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4cbf-104">예제</span><span class="sxs-lookup"><span data-stu-id="e4cbf-104">Example</span></span>  
 <span data-ttu-id="e4cbf-105">다음 코드 예제에서는 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤에 항목을 동적으로 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4cbf-105">The following code example demonstrates how to dynamically add items to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="e4cbf-106">예제에서는 양식에서 세 가지 다른 컨트롤에 대해 같은 <xref:System.Windows.Forms.ContextMenuStrip>을 다시 사용하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4cbf-106">The example also shows how to reuse the same <xref:System.Windows.Forms.ContextMenuStrip> for three different controls on the form.</span></span>  
  
 <span data-ttu-id="e4cbf-107">예제에서 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 이벤트 처리기는 메뉴 항목 컬렉션을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="e4cbf-107">In the example, an <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler populates the menu item collection.</span></span> <span data-ttu-id="e4cbf-108"><xref:System.Windows.Forms.ToolStripDropDown.Opening> 이벤트 처리기는 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> 속성을 검사하고 소스 컨트롤을 설명하는 <xref:System.Windows.Forms.ToolStripItem>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cbf-108">The <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler examines the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> properties and adds a <xref:System.Windows.Forms.ToolStripItem> describing the source control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#40)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e4cbf-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e4cbf-109">Compiling the Code</span></span>  
 <span data-ttu-id="e4cbf-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cbf-110">This example requires:</span></span>  
  
- <span data-ttu-id="e4cbf-111">System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="e4cbf-111">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="e4cbf-112">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cbf-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e4cbf-113">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4cbf-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4cbf-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="e4cbf-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- [<span data-ttu-id="e4cbf-115">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e4cbf-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
