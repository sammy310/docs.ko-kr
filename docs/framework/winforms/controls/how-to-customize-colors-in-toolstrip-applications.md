---
title: '방법: ToolStrip 애플리케이션에서 색 사용자 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: 4d051085bdba41b9784d3dd7f921189c1300daf0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074913"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="7b221-102">방법: ToolStrip 애플리케이션에서 색 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7b221-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="7b221-103">사용자 지정 색을 사용하기 위한 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 클래스를 사용하여 <xref:System.Windows.Forms.ToolStrip> 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b221-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b221-104">예제</span><span class="sxs-lookup"><span data-stu-id="7b221-104">Example</span></span>  
 <span data-ttu-id="7b221-105">다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>를 사용하여 런타임에 사용자 지정 색을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b221-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7b221-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7b221-106">Compiling the Code</span></span>  
 <span data-ttu-id="7b221-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7b221-107">This example requires:</span></span>  
  
-   <span data-ttu-id="7b221-108">System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="7b221-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7b221-109">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b221-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7b221-110">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b221-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b221-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="7b221-111">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
