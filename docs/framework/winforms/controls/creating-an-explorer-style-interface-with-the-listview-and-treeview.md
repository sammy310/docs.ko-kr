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
ms.openlocfilehash: d80f8e3bc729689b274af520bc37fda8417b0407
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "69658576"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="bb572-102">연습: 디자이너를 사용하여 ListView 및 TreeView 컨트롤에서 탐색기 스타일 인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="bb572-102">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>

<span data-ttu-id="bb572-103">Visual Studio의 이점 중 하나는 짧은 시간 내에 전문적인 Windows Forms 응용 프로그램을 만드는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-103">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="bb572-104">일반적인 시나리오는 및 <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> 컨트롤을 사용 하 여 windows 운영 체제의 windows 탐색기 기능과 유사한 UI (사용자 인터페이스)를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-104">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="bb572-105">Windows 탐색기는 사용자의 컴퓨터에 있는 파일 및 폴더의 계층 구조를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-105">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="bb572-106">ListView 및 TreeView 컨트롤이 포함 된 폼을 만들려면</span><span class="sxs-lookup"><span data-stu-id="bb572-106">To create the form containing a ListView and TreeView control</span></span>

1. <span data-ttu-id="bb572-107">**파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-107">On the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="bb572-108">**새 프로젝트** 대화 상자에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-108">In the **New Project** dialog box, do the following:</span></span>

    1. <span data-ttu-id="bb572-109">범주에서 **Visual Basic** 또는 **시각적 개체 C#** 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-109">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>

    2. <span data-ttu-id="bb572-110">템플릿 목록에서 **Windows Forms 응용 프로그램**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-110">In the list of templates, choose **Windows Forms Application**.</span></span>

3. <span data-ttu-id="bb572-111">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-111">Click **OK**.</span></span> <span data-ttu-id="bb572-112">새 Windows Forms 프로젝트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-112">A new Windows Forms project is created.</span></span>

4. <span data-ttu-id="bb572-113">폼에 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 추가 하 고 해당 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을로 <xref:System.Windows.Forms.DockStyle.Fill>설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-113">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="bb572-114"><xref:System.Windows.Forms.ImageList> 이라는`imageList1` 를 폼에 추가 하 고 속성 창를 사용 하 여 폴더 이미지와 문서 이미지 등 두 개의 이미지를 순서 대로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-114">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>

6. <span data-ttu-id="bb572-115">이라는 컨트롤 <xref:System.Windows.Forms.TreeView> 을 폼 `treeview1` 에 추가 하 고 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 왼쪽에 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-115">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="bb572-116">속성 창에서 다음을 `treeView1` 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-116">In the Properties window for `treeView1` do the following:</span></span>

    1. <span data-ttu-id="bb572-117"><xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-117">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="bb572-118"><xref:System.Windows.Forms.TreeView.ImageList%2A> 속성을 `imagelist1.`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-118">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>

7. <span data-ttu-id="bb572-119"><xref:System.Windows.Forms.SplitContainer> 이라는 <xref:System.Windows.Forms.ListView> 컨트롤을폼에추가하고컨트롤의오른쪽에배치합니다.`listView1`</span><span class="sxs-lookup"><span data-stu-id="bb572-119">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="bb572-120">속성 창에서 다음을 `listview1` 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-120">In the Properties window for `listview1` do the following:</span></span>

    1. <span data-ttu-id="bb572-121"><xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-121">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="bb572-122"><xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View.Details>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-122">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

    3. <span data-ttu-id="bb572-123">속성에서![](./media/visual-studio-ellipsis-button.png)줄임표 (Visual Studio 속성 창의 줄임표 단추 (...)를 클릭 하 여 ColumnHeader 컬렉션 편집기를**엽니다.** <xref:System.Windows.Forms.ListView.Columns%2A></span><span class="sxs-lookup"><span data-stu-id="bb572-123">Open the ColumnHeader Collection Editor by clicking the ellipses (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="bb572-124">세 개의 열을 추가 하 <xref:System.Windows.Forms.ColumnHeader.Text%2A> 고 속성 `Name`을 `Type`각각, `Last Modified`및로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-124">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="bb572-125">**확인** 을 클릭하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-125">Click **OK** to close the dialog box.</span></span>

    4. <span data-ttu-id="bb572-126"><xref:System.Windows.Forms.ListView.SmallImageList%2A> 속성을 `imageList1.`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-126">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>

8. <span data-ttu-id="bb572-127">노드 및 하위 노드로를 <xref:System.Windows.Forms.TreeView> 채우는 코드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-127">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="bb572-128">이 코드를 `Form1` 클래스에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-128">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. <span data-ttu-id="bb572-129">이전 코드는 System.IO 네임 스페이스를 사용 하므로 폼의 맨 위에 적절 한 using 또는 import 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-129">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. <span data-ttu-id="bb572-130">폼의 생성자 또는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리 메서드의 이전 단계에서 설정 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-130">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="bb572-131">이 코드를 폼 생성자에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-131">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. <span data-ttu-id="bb572-132">`treeview1` `listview1` 에 대 <xref:System.Windows.Forms.TreeView.NodeMouseClick> 한 이벤트를 처리 하 고 노드를 클릭할 때 노드 내용으로 채울 코드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-132">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="bb572-133">이 코드를 `Form1` 클래스에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-133">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     <span data-ttu-id="bb572-134">를 사용 하 C#는 경우 이벤트 처리 방법과 연결 된 <xref:System.Windows.Forms.TreeView.NodeMouseClick> 이벤트가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-134">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="bb572-135">이 코드를 폼 생성자에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-135">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a><span data-ttu-id="bb572-136">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="bb572-136">Testing the Application</span></span>

<span data-ttu-id="bb572-137">이제 폼을 테스트 하 여 예상 대로 동작 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-137">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="bb572-138">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="bb572-138">To test the form</span></span>

- <span data-ttu-id="bb572-139">F5 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-139">Press F5 to run the application.</span></span>

     <span data-ttu-id="bb572-140">왼쪽에 프로젝트 디렉터리를 표시 하는 <xref:System.Windows.Forms.TreeView> 컨트롤을 포함 하는 분할 폼 <xref:System.Windows.Forms.ListView> 과 오른쪽에 세 개의 열이 있는 컨트롤이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-140">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="bb572-141">디렉터리 노드를 선택 <xref:System.Windows.Forms.TreeView> 하 여를 트래버스할 수 <xref:System.Windows.Forms.ListView> 있으며,은 선택한 디렉터리의 콘텐츠로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-141">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bb572-142">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bb572-142">Next Steps</span></span>

<span data-ttu-id="bb572-143">이 응용 프로그램은를 사용 <xref:System.Windows.Forms.TreeView> 하 고 <xref:System.Windows.Forms.ListView> 제어할 수 있는 방법의 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb572-143">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="bb572-144">이러한 컨트롤에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bb572-144">For more information on these controls, see the following topics:</span></span>

- [<span data-ttu-id="bb572-145">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가 (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="bb572-145">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [<span data-ttu-id="bb572-146">방법: ListView 컨트롤에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="bb572-146">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)

- [<span data-ttu-id="bb572-147">방법: TreeView 노드에 바로 가기 메뉴 연결</span><span class="sxs-lookup"><span data-stu-id="bb572-147">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a><span data-ttu-id="bb572-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb572-148">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="bb572-149">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="bb572-149">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="bb572-150">방법: Windows Forms TreeView 컨트롤을 사용 하 여 노드 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="bb572-150">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="bb572-151">방법: Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="bb572-151">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="bb572-152">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="bb572-152">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
