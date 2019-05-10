---
title: '연습: 디자이너를 사용하여 ListView 및 TreeView 컨트롤에서 탐색기 스타일 인터페이스 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: c8f6e51b5ab8242ba8253a04160c40e59fce0088
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648196"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="c186d-102">연습: 디자이너를 사용하여 ListView 및 TreeView 컨트롤에서 탐색기 스타일 인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="c186d-102">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>
<span data-ttu-id="c186d-103">Visual Studio의 이점 중 하나는 짧은 시간 안에 전문적으로 보이는 Windows Forms 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-103">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="c186d-104">일반적인 시나리오를 사용 하 여 사용자 인터페이스 (UI)를 만드는 것 <xref:System.Windows.Forms.ListView> 및 <xref:System.Windows.Forms.TreeView> 와 비슷한 Windows 운영 체제의 Windows 탐색기 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-104">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="c186d-105">Windows 탐색기는 사용자의 컴퓨터에서 파일 및 폴더의 계층 구조를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-105">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c186d-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c186d-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c186d-108">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c186d-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="c186d-109">ListView 및 TreeView 컨트롤이 포함 된 폼을 만들려면</span><span class="sxs-lookup"><span data-stu-id="c186d-109">To create the form containing a ListView and TreeView control</span></span>  
  
1. <span data-ttu-id="c186d-110">**파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-110">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="c186d-111">에 **새 프로젝트** 대화 상자에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-111">In the **New Project** dialog box, do the following:</span></span>  
  
    1. <span data-ttu-id="c186d-112">범주를 선택 하거나 **Visual Basic** 하거나 **Visual C#** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-112">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>  
  
    2. <span data-ttu-id="c186d-113">템플릿 목록에서 선택 **Windows Forms 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-113">In the list of templates, choose **Windows Forms Application**.</span></span>  
  
3. <span data-ttu-id="c186d-114">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-114">Click **OK**.</span></span> <span data-ttu-id="c186d-115">새 Windows Forms 프로젝트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-115">A new Windows Forms project is created.</span></span>  
  
4. <span data-ttu-id="c186d-116">추가 된 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 폼 및 설정 해당 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>입니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-116">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5. <span data-ttu-id="c186d-117">추가 <xref:System.Windows.Forms.ImageList> 라는 `imageList1` 폼을 사용 하 여 두 개의 이미지를 추가 하려면 속성 창: 폴더 이미지 및 문서 이미지를 지정 된 순서로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-117">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>  
  
6. <span data-ttu-id="c186d-118">추가 <xref:System.Windows.Forms.TreeView> 라는 컨트롤 `treeview1` 폼에 왼쪽에 배치 하 고는 <xref:System.Windows.Forms.SplitContainer> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-118">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="c186d-119">에 대 한 속성 창의 `treeView1` 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-119">In the Properties window for `treeView1` do the following:</span></span>  
  
    1. <span data-ttu-id="c186d-120"><xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-120">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    2. <span data-ttu-id="c186d-121"><xref:System.Windows.Forms.TreeView.ImageList%2A> 속성을 `imagelist1.`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-121">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>  
  
7. <span data-ttu-id="c186d-122">추가 <xref:System.Windows.Forms.ListView> 라는 컨트롤 `listView1` 폼에 오른쪽에 놓습니다는 <xref:System.Windows.Forms.SplitContainer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-122">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="c186d-123">에 대 한 속성 창의 `listview1` 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-123">In the Properties window for `listview1` do the following:</span></span>  
  
    1. <span data-ttu-id="c186d-124"><xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-124">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    2. <span data-ttu-id="c186d-125"><xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View.Details>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-125">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
    3. <span data-ttu-id="c186d-126">줄임표를 클릭 하 여 ColumnHeader 컬렉션 편집기를 엽니다 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton"))에 <xref:System.Windows.Forms.ListView.Columns%2A> 속성**합니다.**</span><span class="sxs-lookup"><span data-stu-id="c186d-126">Open the ColumnHeader Collection Editor by clicking the ellipses (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="c186d-127">세 개의 열을 추가 하 고 설정 자신의 <xref:System.Windows.Forms.ColumnHeader.Text%2A> 속성을 `Name`를 `Type`, 및 `Last Modified`, 각각.</span><span class="sxs-lookup"><span data-stu-id="c186d-127">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="c186d-128">**확인** 을 클릭하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-128">Click **OK** to close the dialog box.</span></span>  
  
    4. <span data-ttu-id="c186d-129"><xref:System.Windows.Forms.ListView.SmallImageList%2A> 속성을 `imageList1.`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-129">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>  
  
8. <span data-ttu-id="c186d-130">채우는 코드를 구현 합니다 <xref:System.Windows.Forms.TreeView> 노드 및 하위 노드를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-130">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="c186d-131">이 코드를 추가 하 여 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-131">Add this code to the `Form1` class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. <span data-ttu-id="c186d-132">System.IO 네임 스페이스를 사용 하는 이전 코드를 적절 한 사용 하 여 추가 되거나 폼의 맨 위에 있는 문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-132">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="c186d-133">폼의 생성자에서 이전 단계에서 설정 메서드를 호출 하거나 <xref:System.Windows.Forms.Form.Load> 이벤트 처리 메서드.</span><span class="sxs-lookup"><span data-stu-id="c186d-133">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="c186d-134">폼 생성자에이 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-134">Add this code to the form constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. <span data-ttu-id="c186d-135">처리를 <xref:System.Windows.Forms.TreeView.NodeMouseClick> 이벤트에 대 한 `treeview1` **를** 채우는 코드를 구현 하 고 `listview1` 노드를 클릭할 때 노드 콘텐츠를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-135">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="c186d-136">이 코드를 추가 하 여 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-136">Add this code to the `Form1` class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     <span data-ttu-id="c186d-137">C#을 사용 하는 경우 했는지 확인 합니다 <xref:System.Windows.Forms.TreeView.NodeMouseClick> 해당 이벤트 처리 메서드를 사용 하 여 연결 된 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-137">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="c186d-138">폼 생성자에이 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-138">Add this code to the form constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="c186d-139">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="c186d-139">Testing the Application</span></span>  
 <span data-ttu-id="c186d-140">이제 예상 대로 작동 되도록 폼을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-140">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="c186d-141">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="c186d-141">To test the form</span></span>  
  
- <span data-ttu-id="c186d-142">F5 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-142">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="c186d-143">포함 된 분할 폼 표시 됩니다는 <xref:System.Windows.Forms.TreeView> 왼쪽에 프로젝트 디렉터리를 표시 하는 컨트롤 및 <xref:System.Windows.Forms.ListView> 오른쪽에 있는 세 개의 열을 사용 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-143">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="c186d-144">이동할 수는 <xref:System.Windows.Forms.TreeView> directory 노드를 선택 하 여 및 <xref:System.Windows.Forms.ListView> 선택한 디렉터리의 내용으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-144">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c186d-145">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c186d-145">Next Steps</span></span>  
 <span data-ttu-id="c186d-146">이 응용 프로그램 사용할 수 있습니다 하는 방법의 예를 제공 <xref:System.Windows.Forms.TreeView> 고 <xref:System.Windows.Forms.ListView> 함께 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-146">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="c186d-147">이러한 컨트롤에 대 한 자세한 내용은 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c186d-147">For more information on these controls, see the following topics:</span></span>  
  
- [<span data-ttu-id="c186d-148">방법: TreeView 또는 ListView 컨트롤 (Windows Forms)에 사용자 지정 정보 추가</span><span class="sxs-lookup"><span data-stu-id="c186d-148">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
- [<span data-ttu-id="c186d-149">방법: ListView 컨트롤에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="c186d-149">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)  
  
- [<span data-ttu-id="c186d-150">방법: TreeView 노드에 바로 가기 메뉴 연결</span><span class="sxs-lookup"><span data-stu-id="c186d-150">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## <a name="see-also"></a><span data-ttu-id="c186d-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="c186d-151">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="c186d-152">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c186d-152">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="c186d-153">방법: 추가 하 고 Windows Forms TreeView 컨트롤을 사용 하 여 노드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c186d-153">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="c186d-154">방법: Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="c186d-154">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="c186d-155">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="c186d-155">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
