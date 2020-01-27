---
title: ListView 컨트롤을 사용 하 여 열에 하위 항목 표시
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: 5c6d807410ad4ee0198d6334844bd65b148edff4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745550"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="603ae-102">방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시</span><span class="sxs-lookup"><span data-stu-id="603ae-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="603ae-103">Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤은 자세히 보기의 각 항목에 대 한 추가 텍스트 또는 하위 항목을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="603ae-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="603ae-104">첫 번째 열은 직원 번호와 같은 항목 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="603ae-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="603ae-105">두 번째, 세 번째 및 다음 열에는 첫 번째, 두 번째 및 다음에 연결 된 하위 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="603ae-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="603ae-106">목록 항목에 하위 항목을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="603ae-106">To add subitems to a list item</span></span>  
  
1. <span data-ttu-id="603ae-107">필요한 열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="603ae-107">Add any columns needed.</span></span> <span data-ttu-id="603ae-108">첫 번째 열에는 항목의 <xref:System.Windows.Forms.ListView.Text%2A> 속성이 표시 되므로 하위 항목 보다 하나 이상의 열이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="603ae-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="603ae-109">열 추가에 대 한 자세한 내용은 [방법: Windows Forms ListView 컨트롤에 열 추가](how-to-add-columns-to-the-windows-forms-listview-control.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="603ae-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2. <span data-ttu-id="603ae-110">항목의 <xref:System.Windows.Forms.ListViewItem.SubItems%2A> 속성에서 반환 된 컬렉션의 <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="603ae-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="603ae-111">아래 코드 예제에서는 목록 항목의 직원 이름과 부서를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="603ae-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="603ae-112">참조</span><span class="sxs-lookup"><span data-stu-id="603ae-112">See also</span></span>

- [<span data-ttu-id="603ae-113">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="603ae-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="603ae-114">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="603ae-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="603ae-115">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="603ae-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="603ae-116">방법: Windows Forms ListView 컨트롤의 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="603ae-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="603ae-117">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="603ae-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
