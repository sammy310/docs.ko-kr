---
title: 목록보기 컨트롤의 항목 그룹화
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: a1754d10de2bbb5895ae861cd17f4af1f18810e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141993"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="93df2-102">방법: Windows Forms ListView 컨트롤에서 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="93df2-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="93df2-103"><xref:System.Windows.Forms.ListView> 컨트롤의 그룹화 기능을 사용하면 관련 항목 집합을 그룹으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df2-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="93df2-104">이러한 그룹은 화면에서 그룹 제목이 포함된 가로 그룹 헤더로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="93df2-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="93df2-105">그룹을 사용하여 <xref:System.Windows.Forms.ListView> 항목을 사전순, 날짜 또는 다른 논리적 그룹화하여 항목을 더 쉽게 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df2-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="93df2-106">다음 이미지는 일부 그룹화된 항목을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df2-106">The following image shows some grouped items.</span></span>  
  
 ![홀수 및 짝수 ListView 그룹의 스크린샷입니다.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  

 <span data-ttu-id="93df2-108">그룹화를 사용하려면 먼저 디자이너 또는 프로그래밍 방식으로 하나 이상의 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93df2-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="93df2-109">그룹이 정의된 후 그룹에 항목을 할당할 <xref:System.Windows.Forms.ListView> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df2-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="93df2-110">한 그룹에서 다른 그룹으로 프로그래밍 방식으로 항목을 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df2-110">You can also move items from one group to another programmatically.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="93df2-111">그룹을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="93df2-111">To add groups</span></span>  
  
1. <span data-ttu-id="93df2-112"><xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 컬렉션의 <xref:System.Windows.Forms.ListView.Groups%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93df2-112">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="93df2-113">그룹을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="93df2-113">To remove groups</span></span>  
  
1. <span data-ttu-id="93df2-114">컬렉션의 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 또는 메서드를 <xref:System.Windows.Forms.ListView.Groups%2A> 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93df2-114">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="93df2-115">메서드는 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 단일 그룹을 제거합니다. 메서드는 <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 목록에서 모든 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="93df2-115">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="93df2-116">그룹을 제거해도 해당 그룹 내의 항목이 제거되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93df2-116">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="93df2-117">그룹에 항목을 할당하거나 그룹 간에 항목을 이동하려면</span><span class="sxs-lookup"><span data-stu-id="93df2-117">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="93df2-118">개별 <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> 항목의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="93df2-118">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="93df2-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93df2-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="93df2-120">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="93df2-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="93df2-121">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="93df2-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="93df2-122">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="93df2-122">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
