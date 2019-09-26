---
title: '방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 그룹화'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: b63bcd9e5e357db350cc2987e09af84eb58bdcff
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "69039407"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="887da-102">방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="887da-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="887da-103"><xref:System.Windows.Forms.ListView> 컨트롤의 그룹화 기능을 사용 하면 관련 항목 집합을 그룹으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="887da-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="887da-104">이러한 그룹은 그룹 제목이 포함 된 가로 그룹 헤더로 화면에 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="887da-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="887da-105">그룹을 사용 <xref:System.Windows.Forms.ListView> 하 여 항목을 사전순으로, 날짜별로 또는 다른 논리적 그룹화로 그룹화 하 여 많은 목록을 보다 쉽게 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="887da-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="887da-106">다음 이미지는 몇 가지 그룹화 된 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="887da-106">The following image shows some grouped items:</span></span>

![짝수와 짝수 그룹으로 구분 된 숫자입니다.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

<span data-ttu-id="887da-108">다음 절차에는 <xref:System.Windows.Forms.ListView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="887da-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="887da-109">이러한 프로젝트 [를 설정 하는 방법에 대 한 자세한 내용은 방법: Windows Forms 응용 프로그램 프로젝트](/visualstudio/ide/step-1-create-a-windows-forms-application-project) [를 만들고 방법: Windows Forms](how-to-add-controls-to-windows-forms.md)에 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="887da-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

<span data-ttu-id="887da-110">그룹화를 사용 하려면 먼저 디자이너에서 또는 프로그래밍 방식으로 <xref:System.Windows.Forms.ListViewGroup> 하나 이상의 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="887da-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="887da-111">그룹을 정의한 후에는 해당 그룹에 항목을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="887da-111">Once a group has been defined, you can assign items to it.</span></span>

> [!NOTE]
> <span data-ttu-id="887da-112"><xref:System.Windows.Forms.ListView>응용 프로그램에서 메서드를 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 호출 하는 경우에만 그룹을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="887da-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="887da-113">이전 버전의 운영 체제 그룹 관련 모든 코드가 미치지 않으며 그룹 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="887da-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="887da-114">자세한 내용은 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="887da-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>

## <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="887da-115">디자이너에서 그룹을 추가 하거나 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="887da-115">To add or remove groups in the designer</span></span>

1. <span data-ttu-id="887da-116">**속성 창에서** <xref:System.Windows.Forms.ListView.Groups%2A> 속성 옆에 있는 **줄임표** 단추![(...)를 클릭 하 여 속성 옆의 Visual Studio](./media/visual-studio-ellipsis-button.png)속성 창에서 줄임표 단추 (...)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="887da-116">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>

     <span data-ttu-id="887da-117">**ListViewGroup 컬렉션 편집기** 가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="887da-117">The **ListViewGroup Collection Editor** appears.</span></span>

2. <span data-ttu-id="887da-118">그룹을 추가 하려면 **추가** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="887da-118">To add a group, click the **Add** button.</span></span> <span data-ttu-id="887da-119">그런 다음 새 그룹의 속성 (예: <xref:System.Windows.Forms.ListViewGroup.Header%2A> 및 <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> 속성)을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="887da-119">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="887da-120">그룹을 제거 하려면 그룹을 선택 하 고 **제거** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="887da-120">To remove a group, select it and click the **Remove** button.</span></span>

## <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="887da-121">디자이너에서 그룹에 항목을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="887da-121">To assign items to groups in the designer</span></span>

1. <span data-ttu-id="887da-122">**속성 창에서** <xref:System.Windows.Forms.ListView.Items%2A> 속성 옆에 있는 **줄임표** 단추![(...)를 클릭 하 여 속성 옆의 Visual Studio](./media/visual-studio-ellipsis-button.png)속성 창에서 줄임표 단추 (...)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="887da-122">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="887da-123">**ListViewItem 컬렉션 편집기** 가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="887da-123">The **ListViewItem Collection Editor** appears.</span></span>

2. <span data-ttu-id="887da-124">새 항목을 추가 하려면 **추가** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="887da-124">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="887da-125">그런 다음 <xref:System.Windows.Forms.ListViewItem.Text%2A> 및 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 속성과 같은 새 항목의 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="887da-125">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

3. <span data-ttu-id="887da-126"><xref:System.Windows.Forms.ListViewItem.Group%2A> 속성을 선택 하 고 드롭다운 목록에서 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="887da-126">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="887da-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="887da-127">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="887da-128">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="887da-128">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="887da-129">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="887da-129">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="887da-130">방법: Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="887da-130">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
