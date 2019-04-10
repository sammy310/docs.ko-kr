---
title: '방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시'
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
ms.openlocfilehash: defa8aa736927c9076eb2410d6d914a8f7550d03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183720"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="d048b-102">방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시</span><span class="sxs-lookup"><span data-stu-id="d048b-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="d048b-103">Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤 추가 텍스트 또는 세부 정보 뷰에서 각 항목에 대 한 하위 항목을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d048b-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="d048b-104">첫 번째 열에는 예를 들어 직원 번호 항목 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d048b-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="d048b-105">두 번째, 두 번째, 첫 번째, 세 번째 및 이후의 열에 표시 하 고 후속 관련 된 하위 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="d048b-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="d048b-106">목록 항목에 하위 항목을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="d048b-106">To add subitems to a list item</span></span>  
  
1.  <span data-ttu-id="d048b-107">필요한 열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d048b-107">Add any columns needed.</span></span> <span data-ttu-id="d048b-108">첫 번째 열이 항목의 표시 되므로 <xref:System.Windows.Forms.ListView.Text%2A> 속성을 하나 이상의 열 하위 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d048b-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="d048b-109">열을 추가 하는 방법은 참조 하세요. [방법: 열에는 Windows Forms ListView 컨트롤 추가](how-to-add-columns-to-the-windows-forms-listview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d048b-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2.  <span data-ttu-id="d048b-110">호출을 <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> 에서 반환 된 컬렉션의 메서드는 <xref:System.Windows.Forms.ListViewItem.SubItems%2A> 항목의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d048b-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="d048b-111">아래 코드 예제에는 목록 항목에 대 한 부서와 직원 이름을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d048b-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="d048b-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="d048b-112">See also</span></span>

- [<span data-ttu-id="d048b-113">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d048b-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="d048b-114">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="d048b-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="d048b-115">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="d048b-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="d048b-116">방법: Windows Forms ListView 컨트롤에 대한 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="d048b-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="d048b-117">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d048b-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
