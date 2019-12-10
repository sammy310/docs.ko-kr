---
title: '방법: Windows Forms ListView 컨트롤에 삽입 표시 나타내기'
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
ms.openlocfilehash: 62d105dc3c0b9aabc3699c12259e1624ac31a3a0
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960434"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="7f04c-102">방법: Windows Forms ListView 컨트롤에 삽입 표시 나타내기</span><span class="sxs-lookup"><span data-stu-id="7f04c-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="7f04c-103"><xref:System.Windows.Forms.ListView> 컨트롤에 있는 삽입 표시는 끌어온 항목이 삽입되는 지점을 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7f04c-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="7f04c-104">사용자가 다른 두 항목 사이의 지점으로 항목을 끌면 삽입 표시가 항목의 새 예상 위치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f04c-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
 <span data-ttu-id="7f04c-105">다음 이미지에서는 삽입 표시를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f04c-105">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="7f04c-106">![ListView 삽입 표시를 보여 주는 스크린샷](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span><span class="sxs-lookup"><span data-stu-id="7f04c-106">![Screenshot that shows a ListView insertion mark.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="7f04c-107">다음 코드 예제에서는 이 기능을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f04c-107">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f04c-108">예제</span><span class="sxs-lookup"><span data-stu-id="7f04c-108">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7f04c-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7f04c-109">Compiling the Code</span></span>  
 <span data-ttu-id="7f04c-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7f04c-110">This example requires:</span></span>  
  
- <span data-ttu-id="7f04c-111">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="7f04c-111">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f04c-112">참조</span><span class="sxs-lookup"><span data-stu-id="7f04c-112">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [<span data-ttu-id="7f04c-113">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7f04c-113">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="7f04c-114">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="7f04c-114">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="7f04c-115">연습: Windows Forms에서 끌어서 놓기 작업 수행</span><span class="sxs-lookup"><span data-stu-id="7f04c-115">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
