---
title: '방법: Windows Forms ListView 컨트롤에 삽입 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
ms.openlocfilehash: 6c87a4cb68baa15b5f670a23fb4e8ef7ce16cf6f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710058"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="93d46-102">방법: Windows Forms ListView 컨트롤에 삽입 표시</span><span class="sxs-lookup"><span data-stu-id="93d46-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="93d46-103">
  <xref:System.Windows.Forms.ListView> 컨트롤에 있는 삽입 표시는 끌어온 항목이 삽입되는 지점을 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="93d46-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="93d46-104">사용자가 다른 두 항목 사이의 지점으로 항목을 끌면 삽입 표시가 항목의 새 예상 위치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93d46-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93d46-105">삽입 표시 기능은 응용 프로그램이 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드를 호출할 때 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93d46-105">The insertion mark feature is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="93d46-106">이전 버전의 운영 체제에서는 삽입 표시와 관련된 코드가 아무 효과도 없으며 삽입 표시가 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93d46-106">On earlier operating systems, any code relating to the insertion mark has no effect and the insertion mark will not appear.</span></span> <span data-ttu-id="93d46-107">자세한 내용은 <xref:System.Windows.Forms.ListViewInsertionMark>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93d46-107">For more information, see <xref:System.Windows.Forms.ListViewInsertionMark>.</span></span>  
  
 <span data-ttu-id="93d46-108">다음 이미지에서는 삽입 표시를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93d46-108">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="93d46-109">![ListView 삽입 표시](./media/listviewinsertion.gif "ListViewInsertion")</span><span class="sxs-lookup"><span data-stu-id="93d46-109">![A ListView Insertion Mark](./media/listviewinsertion.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="93d46-110">다음 코드 예제에서는 이 기능을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93d46-110">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93d46-111">예제</span><span class="sxs-lookup"><span data-stu-id="93d46-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="93d46-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="93d46-112">Compiling the Code</span></span>  
 <span data-ttu-id="93d46-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="93d46-113">This example requires:</span></span>  
  
-   <span data-ttu-id="93d46-114">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="93d46-114">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="93d46-115">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="93d46-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="93d46-116">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93d46-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d46-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="93d46-117">See also</span></span>
- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [<span data-ttu-id="93d46-118">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="93d46-118">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="93d46-119">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="93d46-119">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="93d46-120">연습: Windows Forms에서 끌어서 놓기 작업 수행</span><span class="sxs-lookup"><span data-stu-id="93d46-120">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
