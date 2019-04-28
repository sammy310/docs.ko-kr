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
ms.openlocfilehash: f616436671da449e4f7b47c0a5d0c1b576584a1a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941399"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="78330-102">방법: Windows Forms ListView 컨트롤에서 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="78330-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="78330-103">그룹화 기능을 사용 하 여는 <xref:System.Windows.Forms.ListView> 컨트롤 그룹의 관련된 항목 집합을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78330-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="78330-104">이러한 그룹은 화면에서 그룹 제목을 포함 하는 행 그룹 머리글에 의해 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78330-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="78330-105">사용할 수 있습니다 <xref:System.Windows.Forms.ListView> 그룹 날짜 또는 기타 논리 그룹으로 항목을 사전순으로 그룹화 하 여 보다 쉽게 긴 목록 이동 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="78330-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="78330-106">다음 이미지에서는 일부 그룹화 된 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78330-106">The following image shows some grouped items.</span></span>  
  
 <span data-ttu-id="78330-107">![ListView 그룹](./media/listviewgroups.gif "ListViewGroups")</span><span class="sxs-lookup"><span data-stu-id="78330-107">![ListView Groups](./media/listviewgroups.gif "ListViewGroups")</span></span>  
<span data-ttu-id="78330-108">ListView 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="78330-108">ListView grouped items</span></span>  
  
 <span data-ttu-id="78330-109">그룹화를 사용 하려면 먼저 디자이너에서 또는 프로그래밍 방식으로 하나 이상의 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78330-109">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="78330-110">그룹을 정의한 후 할당할 수 있습니다 <xref:System.Windows.Forms.ListView> 그룹 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="78330-110">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="78330-111">이동할 수도 있습니다 항목이 하나의 그룹에서 다른 프로그래밍 방식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="78330-111">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78330-112"><xref:System.Windows.Forms.ListView> 그룹에만 사용할 수 있습니다 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] 응용 프로그램 호출 하는 경우는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="78330-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="78330-113">이전 버전의 운영 체제 그룹 관련 모든 코드가 미치지 않으며 그룹 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78330-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="78330-114">자세한 내용은 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78330-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="78330-115">그룹을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="78330-115">To add groups</span></span>  
  
1. <span data-ttu-id="78330-116"><xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 컬렉션의 <xref:System.Windows.Forms.ListView.Groups%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78330-116">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="78330-117">그룹을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="78330-117">To remove groups</span></span>  
  
1. <span data-ttu-id="78330-118">사용 된 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 또는 <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 메서드의 <xref:System.Windows.Forms.ListView.Groups%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="78330-118">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="78330-119">합니다 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 메서드는 단일 그룹을 제거, <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 메서드 목록에서 모든 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="78330-119">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="78330-120">그룹을 제거 하는 경우에 해당 그룹 내의 항목은 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78330-120">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="78330-121">항목 그룹을 할당 하거나 항목 그룹 사이 이동</span><span class="sxs-lookup"><span data-stu-id="78330-121">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="78330-122">설정 된 <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> 개별 항목의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="78330-122">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="78330-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="78330-123">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="78330-124">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="78330-124">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="78330-125">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="78330-125">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="78330-126">방법: Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="78330-126">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
