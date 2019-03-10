---
title: '방법: Windows Forms DataGridView 컨트롤에서 열 조작'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGridView control [Windows Forms], manipulating columns
- columns [Windows Forms], manipulating
- data grids [Windows Forms], manipulating columns
ms.assetid: d8cfe6b3-bbab-4182-bec2-0517d9f1eaf6
ms.openlocfilehash: 95d41093178c56c999ecfe515a380927513e715d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722453"
---
# <a name="how-to-manipulate-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="95a3d-102">방법: Windows Forms DataGridView 컨트롤에서 열 조작</span><span class="sxs-lookup"><span data-stu-id="95a3d-102">How to: Manipulate Columns in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="95a3d-103">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridViewColumn> 클래스의 속성을 사용하여 <xref:System.Windows.Forms.DataGridView> 열을 조작하는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95a3d-103">The following code example shows the various ways to manipulate <xref:System.Windows.Forms.DataGridView> columns using properties of the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>

## <a name="example"></a><span data-ttu-id="95a3d-104">예제</span><span class="sxs-lookup"><span data-stu-id="95a3d-104">Example</span></span>

[!code-cpp[System.Windows.Forms.DataGridView.ButtonDemos#100](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CPP/DataGridViewColumnDemo.cpp#100)]
[!code-csharp[System.Windows.Forms.DataGridView.ButtonDemos#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CS/DataGridViewColumnDemo.cs#100)]
[!code-vb[System.Windows.Forms.DataGridView.ButtonDemos#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/VB/datagridviewcolumndemo.vb#100)]

## <a name="compiling-the-code"></a><span data-ttu-id="95a3d-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="95a3d-105">Compiling the Code</span></span>

<span data-ttu-id="95a3d-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="95a3d-106">This example requires:</span></span>

- <span data-ttu-id="95a3d-107">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="95a3d-107">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>

<span data-ttu-id="95a3d-108">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="95a3d-108">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="95a3d-109">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95a3d-109">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>

## <a name="see-also"></a><span data-ttu-id="95a3d-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="95a3d-110">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewBand>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="95a3d-111">Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="95a3d-111">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
