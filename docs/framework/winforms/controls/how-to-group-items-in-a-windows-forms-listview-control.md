---
title: '방법: Windows Forms ListView 컨트롤에서 항목 그룹화'
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
ms.openlocfilehash: b4cd2b9ed23f377912270d33b1415ad39c9e80c0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966625"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="eb723-102">방법: Windows Forms ListView 컨트롤에서 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="eb723-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="eb723-103"><xref:System.Windows.Forms.ListView> 컨트롤의 그룹화 기능을 사용 하면 관련 항목 집합을 그룹으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="eb723-104">이러한 그룹은 그룹 제목이 포함 된 가로 그룹 헤더로 화면에 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="eb723-105">그룹을 사용 <xref:System.Windows.Forms.ListView> 하 여 항목을 사전순으로, 날짜별로 또는 다른 논리적 그룹화로 그룹화 하 여 많은 목록을 보다 쉽게 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="eb723-106">다음 그림은 몇 가지 그룹화 된 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-106">The following image shows some grouped items.</span></span>  
  
 ![홀수 및 심지어 ListView 그룹의 스크린샷](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 <span data-ttu-id="eb723-108">그룹화를 사용 하려면 먼저 디자이너에서 또는 프로그래밍 방식으로 하나 이상의 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="eb723-109">그룹이 정의 된 후에는 항목을 그룹에 <xref:System.Windows.Forms.ListView> 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="eb723-110">한 그룹에서 다른 그룹으로 항목을 프로그래밍 방식으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-110">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb723-111"><xref:System.Windows.Forms.ListView>응용 프로그램에서 메서드를 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 호출 하는 경우에만 그룹을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-111"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="eb723-112">이전 버전의 운영 체제 그룹 관련 모든 코드가 미치지 않으며 그룹 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-112">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="eb723-113">자세한 내용은 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb723-113">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="eb723-114">그룹을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="eb723-114">To add groups</span></span>  
  
1. <span data-ttu-id="eb723-115"><xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 컬렉션의 <xref:System.Windows.Forms.ListView.Groups%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-115">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="eb723-116">그룹을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="eb723-116">To remove groups</span></span>  
  
1. <span data-ttu-id="eb723-117">컬렉션의 <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 또는메서드를사용합니다<xref:System.Windows.Forms.ListView.Groups%2A> .</span><span class="sxs-lookup"><span data-stu-id="eb723-117">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="eb723-118">메서드 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 는 단일 그룹을 제거 합니다. <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 메서드는 목록에서 모든 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-118">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="eb723-119">그룹을 제거 해도 해당 그룹 내의 항목은 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-119">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="eb723-120">그룹에 항목을 할당 하거나 그룹 간에 항목을 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="eb723-120">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="eb723-121">개별 항목 <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> 의 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb723-121">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="eb723-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="eb723-122">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="eb723-123">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="eb723-123">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="eb723-124">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="eb723-124">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="eb723-125">방법: Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="eb723-125">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
