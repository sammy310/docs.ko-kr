---
title: ListView 컨트롤의 항목 그룹화
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
ms.openlocfilehash: 45846751780f433c29b186fe8b9a908f5d295ab3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736631"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="fb7f1-102">방법: Windows Forms ListView 컨트롤에서 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="fb7f1-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="fb7f1-103"><xref:System.Windows.Forms.ListView> 컨트롤의 그룹화 기능을 사용 하면 관련 항목 집합을 그룹으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="fb7f1-104">이러한 그룹은 그룹 제목이 포함 된 가로 그룹 헤더로 화면에 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="fb7f1-105"><xref:System.Windows.Forms.ListView> 그룹을 사용 하 여 항목을 사전순으로, 날짜별로 또는 다른 논리적 그룹화로 그룹화 하 여 많은 목록을 보다 쉽게 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="fb7f1-106">다음 그림은 몇 가지 그룹화 된 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-106">The following image shows some grouped items.</span></span>  
  
 ![홀수 및 심지어 ListView 그룹의 스크린샷](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 <span data-ttu-id="fb7f1-108">그룹화를 사용 하려면 먼저 디자이너에서 또는 프로그래밍 방식으로 하나 이상의 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="fb7f1-109">그룹이 정의 된 후에는 <xref:System.Windows.Forms.ListView> 항목을 그룹에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="fb7f1-110">한 그룹에서 다른 그룹으로 항목을 프로그래밍 방식으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-110">You can also move items from one group to another programmatically.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="fb7f1-111">그룹을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="fb7f1-111">To add groups</span></span>  
  
1. <span data-ttu-id="fb7f1-112"><xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 컬렉션의 <xref:System.Windows.Forms.ListView.Groups%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-112">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="fb7f1-113">그룹을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="fb7f1-113">To remove groups</span></span>  
  
1. <span data-ttu-id="fb7f1-114"><xref:System.Windows.Forms.ListView.Groups%2A> 컬렉션의 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 또는 <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-114">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="fb7f1-115"><xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 메서드는 단일 그룹을 제거 합니다. <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 메서드는 목록에서 모든 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-115">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fb7f1-116">그룹을 제거 해도 해당 그룹 내의 항목은 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-116">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="fb7f1-117">그룹에 항목을 할당 하거나 그룹 간에 항목을 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="fb7f1-117">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="fb7f1-118">개별 항목의 <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-118">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="fb7f1-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb7f1-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="fb7f1-120">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fb7f1-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="fb7f1-121">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="fb7f1-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="fb7f1-122">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="fb7f1-122">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
