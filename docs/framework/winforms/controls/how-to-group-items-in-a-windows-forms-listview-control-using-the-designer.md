---
title: '방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 그룹화'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 9249eef281237f61d103a7c865042aafe537dea5
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960223"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="be955-102">방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="be955-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="be955-103">그룹화 기능을 <xref:System.Windows.Forms.ListView> 컨트롤을 사용 하면 그룹의 관련된 항목 집합을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be955-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="be955-104">이러한 그룹은 화면에서 그룹 제목을 포함 하는 행 그룹 머리글에 의해 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be955-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="be955-105">사용할 수 있습니다 <xref:System.Windows.Forms.ListView> 그룹 날짜 또는 기타 논리 그룹으로 항목을 사전순으로 그룹화 하 여 보다 쉽게 긴 목록 이동 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="be955-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="be955-106">다음 이미지에서는 일부 그룹화 된 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be955-106">The following image shows some grouped items:</span></span>

![숫자가 홀수와 짝수 그룹으로 분리 합니다.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

<span data-ttu-id="be955-108">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="be955-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="be955-109">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="be955-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

<span data-ttu-id="be955-110">그룹화를 사용 하려면 먼저 만들어야 이상의 <xref:System.Windows.Forms.ListViewGroup> 디자이너에서 또는 프로그래밍 방식으로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="be955-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="be955-111">그룹을 정의한 후에 항목을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be955-111">Once a group has been defined, you can assign items to it.</span></span>

> [!NOTE]
> <span data-ttu-id="be955-112"><xref:System.Windows.Forms.ListView> 그룹에만 사용할 수 있습니다 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] 응용 프로그램 호출 하는 경우는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="be955-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="be955-113">이전 버전의 운영 체제 그룹 관련 모든 코드가 미치지 않으며 그룹 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be955-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="be955-114">자세한 내용은 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be955-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>
>
> <span data-ttu-id="be955-115">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be955-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="be955-116">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be955-116">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="be955-117">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be955-117">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

### <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="be955-118">추가 하거나 디자이너에서 그룹을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="be955-118">To add or remove groups in the designer</span></span>

1. <span data-ttu-id="be955-119">에 **속성** 창 클릭 합니다 **줄임표** (![The 줄임표 단추 (...)의 Visual Studio 속성 창에서](./media/visual-studio-ellipsis-button.png)) 단추 옆에 <xref:System.Windows.Forms.ListView.Groups%2A> 속성 .</span><span class="sxs-lookup"><span data-stu-id="be955-119">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>

     <span data-ttu-id="be955-120">합니다 **ListViewGroup 컬렉션 편집기** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="be955-120">The **ListViewGroup Collection Editor** appears.</span></span>

2. <span data-ttu-id="be955-121">그룹을 추가 하려면 클릭 합니다 **추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="be955-121">To add a group, click the **Add** button.</span></span> <span data-ttu-id="be955-122">새 그룹의 속성을 같은 설정한 수는 <xref:System.Windows.Forms.ListViewGroup.Header%2A> 고 <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="be955-122">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="be955-123">그룹을 제거 하려면 선택 하 고 클릭 합니다 **제거** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="be955-123">To remove a group, select it and click the **Remove** button.</span></span>

### <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="be955-124">디자이너에서 그룹에 항목을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="be955-124">To assign items to groups in the designer</span></span>

1. <span data-ttu-id="be955-125">에 **속성** 창 클릭 합니다 **줄임표** (![The 줄임표 단추 (...)의 Visual Studio 속성 창에서](./media/visual-studio-ellipsis-button.png)) 단추 옆에 <xref:System.Windows.Forms.ListView.Items%2A> 속성 .</span><span class="sxs-lookup"><span data-stu-id="be955-125">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="be955-126">합니다 **ListViewItem 컬렉션 편집기** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="be955-126">The **ListViewItem Collection Editor** appears.</span></span>

2. <span data-ttu-id="be955-127">새 항목을 추가 하려면 클릭 합니다 **추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="be955-127">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="be955-128">새 항목의 속성을 같은 설정한 수는 <xref:System.Windows.Forms.ListViewItem.Text%2A> 고 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="be955-128">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

3. <span data-ttu-id="be955-129">선택 된 <xref:System.Windows.Forms.ListViewItem.Group%2A> 속성 드롭다운 목록에서 그룹을 선택 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be955-129">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="be955-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="be955-130">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="be955-131">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="be955-131">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="be955-132">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="be955-132">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="be955-133">방법: Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="be955-133">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
