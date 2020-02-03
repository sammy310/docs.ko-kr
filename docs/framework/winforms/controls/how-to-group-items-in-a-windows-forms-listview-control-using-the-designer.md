---
title: 디자이너를 사용 하 여 ListView 컨트롤에서 항목 그룹화
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 935d8d75517e1028e686ca229f6ada656f58b01e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736676"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="07689-102">방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="07689-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="07689-103"><xref:System.Windows.Forms.ListView> 컨트롤의 그룹화 기능을 사용 하면 관련 항목 집합을 그룹으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07689-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="07689-104">이러한 그룹은 그룹 제목이 포함 된 가로 그룹 헤더로 화면에 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07689-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="07689-105"><xref:System.Windows.Forms.ListView> 그룹을 사용 하 여 항목을 사전순으로, 날짜별로 또는 다른 논리적 그룹화로 그룹화 하 여 많은 목록을 보다 쉽게 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07689-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="07689-106">다음 이미지는 몇 가지 그룹화 된 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07689-106">The following image shows some grouped items:</span></span>

![짝수와 짝수 그룹으로 구분 된 숫자입니다.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

<span data-ttu-id="07689-108">다음 절차에는 <xref:System.Windows.Forms.ListView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="07689-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="07689-109">이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07689-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

<span data-ttu-id="07689-110">그룹화를 사용 하려면 먼저 디자이너에서 또는 프로그래밍 방식으로 하나 이상의 <xref:System.Windows.Forms.ListViewGroup> 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07689-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="07689-111">그룹을 정의한 후에는 해당 그룹에 항목을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07689-111">Once a group has been defined, you can assign items to it.</span></span>

## <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="07689-112">디자이너에서 그룹을 추가 하거나 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="07689-112">To add or remove groups in the designer</span></span>

1. <span data-ttu-id="07689-113">**속성** 창에서 <xref:System.Windows.Forms.ListView.Groups%2A> 속성 옆의 속성 창 Visual Studio.](./media/visual-studio-ellipsis-button.png)) 단추에 **있는 줄임표 단추** (...)를![클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07689-113">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>

     <span data-ttu-id="07689-114">**ListViewGroup 컬렉션 편집기** 가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="07689-114">The **ListViewGroup Collection Editor** appears.</span></span>

2. <span data-ttu-id="07689-115">그룹을 추가 하려면 **추가** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07689-115">To add a group, click the **Add** button.</span></span> <span data-ttu-id="07689-116">그런 다음 <xref:System.Windows.Forms.ListViewGroup.Header%2A> 및 <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> 속성과 같은 새 그룹의 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07689-116">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="07689-117">그룹을 제거 하려면 그룹을 선택 하 고 **제거** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07689-117">To remove a group, select it and click the **Remove** button.</span></span>

## <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="07689-118">디자이너에서 그룹에 항목을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="07689-118">To assign items to groups in the designer</span></span>

1. <span data-ttu-id="07689-119">**속성** 창에서 <xref:System.Windows.Forms.ListView.Items%2A> 속성 옆의 속성 창 Visual Studio.](./media/visual-studio-ellipsis-button.png)) 단추에 **있는 줄임표 단추** (...)를![클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07689-119">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="07689-120">**ListViewItem 컬렉션 편집기** 가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="07689-120">The **ListViewItem Collection Editor** appears.</span></span>

2. <span data-ttu-id="07689-121">새 항목을 추가 하려면 **추가** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07689-121">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="07689-122">그런 다음 <xref:System.Windows.Forms.ListViewItem.Text%2A> 및 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 속성과 같은 새 항목의 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07689-122">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

3. <span data-ttu-id="07689-123"><xref:System.Windows.Forms.ListViewItem.Group%2A> 속성을 선택 하 고 드롭다운 목록에서 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="07689-123">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="07689-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07689-124">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="07689-125">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="07689-125">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="07689-126">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="07689-126">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="07689-127">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="07689-127">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
