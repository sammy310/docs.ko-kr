---
title: '연습: 디자이너를 사용하여 ListView 및 TreeView 컨트롤에서 탐색기 스타일 인터페이스 만들기'
description: 디자이너를 사용 하 여 Windows Forms ListView 및 TreeView 컨트롤을 사용 하 여 탐색기 스타일 인터페이스를 만드는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: 44d4db1ef3da85dbf411498f486882b86a05c140
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174629"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="20deb-103">연습: 디자이너를 사용하여 ListView 및 TreeView 컨트롤에서 탐색기 스타일 인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="20deb-103">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>

<span data-ttu-id="20deb-104">Visual Studio의 이점 중 하나는 짧은 시간 내에 전문적인 Windows Forms 응용 프로그램을 만드는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-104">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="20deb-105">일반적인 시나리오는 및 컨트롤을 사용 하 여 <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> windows 운영 체제의 windows 탐색기 기능과 유사한 UI (사용자 인터페이스)를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-105">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="20deb-106">Windows 탐색기는 사용자의 컴퓨터에 있는 파일 및 폴더의 계층 구조를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-106">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="20deb-107">ListView 및 TreeView 컨트롤이 포함 된 폼을 만들려면</span><span class="sxs-lookup"><span data-stu-id="20deb-107">To create the form containing a ListView and TreeView control</span></span>

1. <span data-ttu-id="20deb-108">**파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-108">On the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="20deb-109">**새 프로젝트** 대화 상자에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-109">In the **New Project** dialog box, do the following:</span></span>

    1. <span data-ttu-id="20deb-110">범주에서 **Visual Basic** 또는 **Visual c #** 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-110">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>

    2. <span data-ttu-id="20deb-111">템플릿 목록에서 **Windows Forms 응용 프로그램**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-111">In the list of templates, choose **Windows Forms Application**.</span></span>

3. <span data-ttu-id="20deb-112">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-112">Click **OK**.</span></span> <span data-ttu-id="20deb-113">새 Windows Forms 프로젝트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-113">A new Windows Forms project is created.</span></span>

4. <span data-ttu-id="20deb-114"><xref:System.Windows.Forms.SplitContainer>폼에 컨트롤을 추가 하 고 해당 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을로 설정 <xref:System.Windows.Forms.DockStyle.Fill> 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-114">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="20deb-115">이라는를 <xref:System.Windows.Forms.ImageList> `imageList1` 폼에 추가 하 고 속성 창를 사용 하 여 폴더 이미지와 문서 이미지 등 두 개의 이미지를 순서 대로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-115">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>

6. <span data-ttu-id="20deb-116"><xref:System.Windows.Forms.TreeView>이라는 컨트롤을 `treeview1` 폼에 추가 하 고 컨트롤의 왼쪽에 위치를 지정 <xref:System.Windows.Forms.SplitContainer> 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-116">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="20deb-117">속성 창에서 `treeView1` 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-117">In the Properties window for `treeView1` do the following:</span></span>

    1. <span data-ttu-id="20deb-118"><xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-118">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="20deb-119"><xref:System.Windows.Forms.TreeView.ImageList%2A> 속성을 `imagelist1.`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-119">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>

7. <span data-ttu-id="20deb-120"><xref:System.Windows.Forms.ListView>이라는 컨트롤을 `listView1` 폼에 추가 하 고 컨트롤의 오른쪽에 배치 합니다 <xref:System.Windows.Forms.SplitContainer> .</span><span class="sxs-lookup"><span data-stu-id="20deb-120">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="20deb-121">속성 창에서 `listview1` 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-121">In the Properties window for `listview1` do the following:</span></span>

    1. <span data-ttu-id="20deb-122"><xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-122">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="20deb-123"><xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View.Details>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-123">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

    3. <span data-ttu-id="20deb-124">![ ](./media/visual-studio-ellipsis-button.png) 속성에서 줄임표 (Visual Studio 속성 창의 줄임표 단추 (...) <xref:System.Windows.Forms.ListView.Columns%2A> **.** 를 클릭 하 여 ColumnHeader 컬렉션 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-124">Open the ColumnHeader Collection Editor by clicking the ellipses (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="20deb-125">세 개의 열을 추가 하 고 <xref:System.Windows.Forms.ColumnHeader.Text%2A> 속성을 `Name` 각각, 및로 설정 `Type` `Last Modified` 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-125">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="20deb-126">**확인** 을 클릭하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-126">Click **OK** to close the dialog box.</span></span>

    4. <span data-ttu-id="20deb-127"><xref:System.Windows.Forms.ListView.SmallImageList%2A> 속성을 `imageList1.`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-127">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>

8. <span data-ttu-id="20deb-128">노드 및 하위 노드로를 채우는 코드를 구현 합니다 <xref:System.Windows.Forms.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="20deb-128">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="20deb-129">이 코드를 클래스에 추가 `Form1` 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-129">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. <span data-ttu-id="20deb-130">이전 코드는 System.IO 네임 스페이스를 사용 하므로 폼의 맨 위에 적절 한 using 또는 import 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-130">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. <span data-ttu-id="20deb-131">폼의 생성자 또는 이벤트 처리 메서드의 이전 단계에서 설정 메서드를 호출 <xref:System.Windows.Forms.Form.Load> 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-131">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="20deb-132">이 코드를 폼 생성자에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-132">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. <span data-ttu-id="20deb-133"><xref:System.Windows.Forms.TreeView.NodeMouseClick>에 대 한 이벤트 `treeview1` **를 처리** 하 고 `listview1` 노드를 클릭할 때 노드 내용으로 채울 코드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-133">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="20deb-134">이 코드를 클래스에 추가 `Form1` 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-134">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     <span data-ttu-id="20deb-135">C #을 사용 하는 경우 이벤트 <xref:System.Windows.Forms.TreeView.NodeMouseClick> 처리 메서드와 연결 된 이벤트가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-135">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="20deb-136">이 코드를 폼 생성자에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-136">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a><span data-ttu-id="20deb-137">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="20deb-137">Testing the Application</span></span>

<span data-ttu-id="20deb-138">이제 폼을 테스트 하 여 예상 대로 동작 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-138">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="20deb-139">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="20deb-139">To test the form</span></span>

- <span data-ttu-id="20deb-140">F5 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-140">Press F5 to run the application.</span></span>

     <span data-ttu-id="20deb-141">왼쪽에 프로젝트 디렉터리를 표시 하는 컨트롤을 포함 하는 분할 폼 <xref:System.Windows.Forms.TreeView> 과 <xref:System.Windows.Forms.ListView> 오른쪽에 세 개의 열이 있는 컨트롤이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-141">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="20deb-142"><xref:System.Windows.Forms.TreeView>디렉터리 노드를 선택 하 여를 트래버스할 수 있으며,은 <xref:System.Windows.Forms.ListView> 선택한 디렉터리의 콘텐츠로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-142">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="20deb-143">다음 단계</span><span class="sxs-lookup"><span data-stu-id="20deb-143">Next Steps</span></span>

<span data-ttu-id="20deb-144">이 응용 프로그램은를 사용 하 고 제어할 수 있는 방법의 예를 제공 <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.ListView> 합니다.</span><span class="sxs-lookup"><span data-stu-id="20deb-144">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="20deb-145">이러한 컨트롤에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="20deb-145">For more information on these controls, see the following topics:</span></span>

- [<span data-ttu-id="20deb-146">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="20deb-146">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [<span data-ttu-id="20deb-147">방법: ListView 컨트롤에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="20deb-147">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)

- [<span data-ttu-id="20deb-148">방법: TreeView 노드에 바로 가기 메뉴 연결</span><span class="sxs-lookup"><span data-stu-id="20deb-148">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a><span data-ttu-id="20deb-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20deb-149">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="20deb-150">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="20deb-150">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="20deb-151">방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="20deb-151">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="20deb-152">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="20deb-152">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="20deb-153">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="20deb-153">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
