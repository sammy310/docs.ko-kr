---
title: '방법: Windows Forms DataGridView 컨트롤에 개체 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: 02c4f94eddfcf782d7d2323787d9b6a9b18db2d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180260"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="bbbd9-102">방법: Windows Forms DataGridView 컨트롤에 개체 바인딩</span><span class="sxs-lookup"><span data-stu-id="bbbd9-102">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="bbbd9-103">다음 코드 예제에서는 각 개체가 개별 행으로 표시되도록 개체 컬렉션을 <xref:System.Windows.Forms.DataGridView> 컨트롤에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bbbd9-103">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="bbbd9-104">이 예제에서는 콤보 상자 드롭다운 목록에 열거형 값이 포함되도록 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>에서 열거형 형식을 가진 속성을 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bbbd9-104">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbbd9-105">예제</span><span class="sxs-lookup"><span data-stu-id="bbbd9-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bbbd9-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="bbbd9-106">Compiling the Code</span></span>  
 <span data-ttu-id="bbbd9-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbd9-107">This example requires:</span></span>  
  
-   <span data-ttu-id="bbbd9-108">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="bbbd9-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="bbbd9-109">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbd9-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="bbbd9-110">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbd9-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbbd9-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="bbbd9-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="bbbd9-112">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="bbbd9-112">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="bbbd9-113">방법: 개체에 액세스 바인딩된 Windows Forms DataGridView 행</span><span class="sxs-lookup"><span data-stu-id="bbbd9-113">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
