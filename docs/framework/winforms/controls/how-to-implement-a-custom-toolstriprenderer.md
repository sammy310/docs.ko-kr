---
title: '방법: 사용자 지정 ToolStripRenderer 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: 0d0a0bdba779fad7bd9b19acb2ea09408dea60a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941191"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="e0eaa-102">방법: 사용자 지정 ToolStripRenderer 구현</span><span class="sxs-lookup"><span data-stu-id="e0eaa-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="e0eaa-103"><xref:System.Windows.Forms.ToolStripRenderer>에서 파생된 클래스를 구현하여 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0eaa-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="e0eaa-104">이렇게 하면 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 및 <xref:System.Windows.Forms.ToolStripSystemRenderer> 클래스에서 제공하는 모양과 다른 모양을 유연성 있게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0eaa-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0eaa-105">예제</span><span class="sxs-lookup"><span data-stu-id="e0eaa-105">Example</span></span>  
 <span data-ttu-id="e0eaa-106">다음 코드 예제에서는 사용자 지정 <xref:System.Windows.Forms.ToolStripRenderer> 클래스를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0eaa-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="e0eaa-107">이 예제에서 `GridStrip` 컨트롤은 사용자가 테이블 레이아웃의 타일을 이동하여 이미지를 구성할 수 있게 해주는 슬라이딩 타일 퍼즐을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e0eaa-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="e0eaa-108">사용자 지정 <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolStripButton> 컨트롤을 표 레이아웃에 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="e0eaa-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="e0eaa-109">레이아웃에는 사용자가 끌어서 놓기 작업을 통해 인접한 타일을 밀 수 있는 빈 셀이 하나 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0eaa-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="e0eaa-110">사용자를 이동할 수 있는 타일이 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0eaa-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="e0eaa-111">`GridStripRenderer` 클래스는 `GridStrip` 컨트롤 모양의 세 가지 측면을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0eaa-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
- <span data-ttu-id="e0eaa-112">`GridStrip` 테두리</span><span class="sxs-lookup"><span data-stu-id="e0eaa-112">`GridStrip` border</span></span>  
  
- <span data-ttu-id="e0eaa-113"><xref:System.Windows.Forms.ToolStripButton> 테두리</span><span class="sxs-lookup"><span data-stu-id="e0eaa-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
- <span data-ttu-id="e0eaa-114"><xref:System.Windows.Forms.ToolStripButton> 이미지</span><span class="sxs-lookup"><span data-stu-id="e0eaa-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e0eaa-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e0eaa-115">Compiling the Code</span></span>  
 <span data-ttu-id="e0eaa-116">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e0eaa-116">This example requires:</span></span>  
  
- <span data-ttu-id="e0eaa-117">System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="e0eaa-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="e0eaa-118">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0eaa-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e0eaa-119">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0eaa-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0eaa-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="e0eaa-120">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="e0eaa-121">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e0eaa-121">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
