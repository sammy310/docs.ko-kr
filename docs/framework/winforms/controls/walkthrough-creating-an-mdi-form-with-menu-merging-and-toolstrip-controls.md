---
title: '연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: e0343b98cb71521b35418e70550a93e0bfe20fa8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628789"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="7f09a-102">연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="7f09a-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="7f09a-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스는 MDI(다중 문서 인터페이스) 애플리케이션을 지원하고 <xref:System.Windows.Forms.MenuStrip> 컨트롤은 메뉴 병합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="7f09a-104">MDI 폼은 <xref:System.Windows.Forms.ToolStrip> 컨트롤일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="7f09a-105">이 연습에서는 MDI 폼을 사용 하 여 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="7f09a-106">폼은 자식 메뉴와 메뉴 병합도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="7f09a-107">이 연습에서는 다음 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="7f09a-108">Windows Forms 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="7f09a-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="7f09a-109">폼에 대 한 주 메뉴 만들기</span><span class="sxs-lookup"><span data-stu-id="7f09a-109">Creating the main menu for your form.</span></span> <span data-ttu-id="7f09a-110">메뉴의 실제 이름은 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="7f09a-111">**도구 상자**에 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="7f09a-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="7f09a-112">자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="7f09a-112">Creating a child form.</span></span>

- <span data-ttu-id="7f09a-113"><xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 z 순서로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="7f09a-114">작업이 완료 되 면 메뉴 병합 및 이동 가능한 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 지 원하는 MDI 폼을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="7f09a-115">이 항목의 코드를 단일 목록으로 복사 하려면 [방법: 메뉴 병합 및 ToolStrip 컨트롤을 사용 하 여 MDI 폼 만들기](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f09a-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7f09a-116">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f09a-116">Prerequisites</span></span>

<span data-ttu-id="7f09a-117">이 연습을 완료 하려면 Visual Studio가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="7f09a-118">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="7f09a-118">Create the project</span></span>

1. <span data-ttu-id="7f09a-119">Visual Studio에서 **system.windows.forms.toolstrip.mdiform** (**File** > **New** > **project** >  **C# Visual** 또는 **Visual Basic** > **클래식 Desktop** > **응용 프로그램**) 라는 Windows 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="7f09a-120">Windows Forms 디자이너에서 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="7f09a-121">속성 창에서 <xref:System.Windows.Forms.Form.IsMdiContainer%2A>의 값을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="7f09a-122">주 메뉴 만들기</span><span class="sxs-lookup"><span data-stu-id="7f09a-122">Create the main menu</span></span>

<span data-ttu-id="7f09a-123">부모 MDI 폼에는 주 메뉴가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="7f09a-124">주 메뉴에는 **창**이라는 하나의 메뉴 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="7f09a-125">**창** 메뉴 항목을 사용 하 여 자식 폼을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="7f09a-126">자식 폼의 메뉴 항목이 주 메뉴에 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="7f09a-127">**도구 상자**에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="7f09a-128"><xref:System.Windows.Forms.MenuStrip> 컨트롤에 <xref:System.Windows.Forms.ToolStripMenuItem>을 추가 하 고 이름을 **창**에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="7f09a-129"><xref:System.Windows.Forms.MenuStrip> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="7f09a-130">속성 창에서 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성의 값을 `ToolStripMenuItem1`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="7f09a-131">**창** 메뉴 항목에 하위 항목을 추가한 다음 하위 항목의 이름을 **New**로 지정한 다음</span><span class="sxs-lookup"><span data-stu-id="7f09a-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="7f09a-132">속성 창에서 **이벤트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="7f09a-133"><xref:System.Windows.Forms.ToolStripItem.Click> 이벤트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="7f09a-134">Windows Forms 디자이너 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트에 대 한 이벤트 처리기를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="7f09a-135">다음 코드를 이벤트 처리기에 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="7f09a-136">도구 상자에 ToolStripPanel 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="7f09a-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="7f09a-137">MDI 폼에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용 하는 경우 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="7f09a-138"><xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 **도구 상자** 에 추가 하 여 WINDOWS FORMS 디자이너에서 MDI 폼을 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="7f09a-139">**도구 상자**를 연 다음 **모든 Windows Forms** 탭을 클릭 하 여 사용할 수 있는 Windows Forms 컨트롤을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="7f09a-140">마우스 오른쪽 단추를 클릭 하 여 바로 가기 메뉴를 열고 **항목 선택**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="7f09a-141">**도구 상자 항목 선택** 대화 상자에서 **ToolStripPanel**를 찾을 때까지 **이름** 열을 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="7f09a-142">**ToolStripPanel**확인란을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="7f09a-143"><xref:System.Windows.Forms.ToolStripPanel> 컨트롤이 **도구 상자**에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="7f09a-144">자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="7f09a-144">Create a child form</span></span>

<span data-ttu-id="7f09a-145">이 절차에서는 자체 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 포함 하는 별도의 자식 폼 클래스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="7f09a-146">이 폼에 대 한 메뉴 항목은 부모 폼의 메뉴 항목과 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="7f09a-147">`ChildForm` 라는 새 폼을 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="7f09a-148">자세한 내용은 [방법: 프로젝트에 Windows Forms 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f09a-148">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="7f09a-149">**도구 상자**에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 자식 폼으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="7f09a-150"><xref:System.Windows.Forms.MenuStrip> 컨트롤의 디자이너 작업 문자 모양 (![작은 검정색 화살표](./media/designer-actions-glyph.gif))을 클릭 한 다음 **항목 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-150">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="7f09a-151">**항목 컬렉션 편집기** 대화 상자에서 **childmenuitem** 이라는 새 <xref:System.Windows.Forms.ToolStripMenuItem>를 자식 메뉴에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="7f09a-152">자세한 내용은 [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f09a-152">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="7f09a-153">양식 테스트</span><span class="sxs-lookup"><span data-stu-id="7f09a-153">Test the form</span></span>

1. <span data-ttu-id="7f09a-154">**F5** 키를 눌러 폼을 컴파일하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="7f09a-155">**창** 메뉴 항목을 클릭 하 여 메뉴를 열고 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="7f09a-156">새 자식 폼이 폼의 MDI 클라이언트 영역에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="7f09a-157">자식 폼의 메뉴가 주 메뉴와 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="7f09a-158">자식 폼을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-158">Close the child form.</span></span>

     <span data-ttu-id="7f09a-159">자식 폼의 메뉴가 주 메뉴에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="7f09a-160">**새로 만들기** 를 여러 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-160">Click **New** several times.</span></span>

     <span data-ttu-id="7f09a-161">자식 폼은 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성이 할당 되기 때문에 **창** 메뉴 항목에 자동으로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="7f09a-162">ToolStrip 지원 추가</span><span class="sxs-lookup"><span data-stu-id="7f09a-162">Add ToolStrip support</span></span>

<span data-ttu-id="7f09a-163">이 절차에서는 MDI 부모 폼에 4 개의 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="7f09a-164">각 <xref:System.Windows.Forms.ToolStrip> 컨트롤은 폼의 가장자리에 도킹 된 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤 내에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="7f09a-165">**도구 상자**에서 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="7f09a-166"><xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 선택 하 고 **도구 상자**에서 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="7f09a-167"><xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="7f09a-168"><xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="7f09a-169">속성 창에서 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성 값을 <xref:System.Windows.Forms.DockStyle.Left>로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="7f09a-170"><xref:System.Windows.Forms.ToolStripPanel> 컨트롤은 폼의 왼쪽에 주 메뉴 아래에 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="7f09a-171">MDI 클라이언트 영역의 크기는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤에 맞게 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="7f09a-172">1-4 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="7f09a-173">새 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼의 맨 위에 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="7f09a-174"><xref:System.Windows.Forms.ToolStripPanel> 컨트롤은 주 메뉴 아래에 도킹 되지만 첫 번째 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤의 오른쪽에 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="7f09a-175">이 단계에서는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤의 올바른 위치 지정에서 z 순서에 대 한 중요성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="7f09a-176">두 개 이상의 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤에 대해 1 ~ 4 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="7f09a-177">새 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼의 오른쪽 및 아래쪽에 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="7f09a-178">ToolStripPanel 컨트롤을 Z 순서로 정렬</span><span class="sxs-lookup"><span data-stu-id="7f09a-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="7f09a-179">MDI 폼에서 도킹 된 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤의 위치는 z 순서에서 컨트롤의 위치에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="7f09a-180">문서 개요 창에서 컨트롤의 z 순서를 쉽게 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="7f09a-181">**보기** 메뉴에서 **다른 창**을 클릭 한 다음 **문서 개요**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="7f09a-182">이전 절차에서 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 정렬 하는 것은 표준이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="7f09a-183">이는 z 순서가 올바르지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="7f09a-184">문서 개요 창을 사용 하 여 컨트롤의 z 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="7f09a-185">문서 개요 창에서 **ToolStripPanel4**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="7f09a-186">목록 맨 아래에 **ToolStripPanel4** 가 표시 될 때까지 아래쪽 화살표 단추를 반복 해 서 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="7f09a-187">**ToolStripPanel4** 컨트롤은 폼의 아래쪽에 다른 컨트롤 아래에 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="7f09a-188">**ToolStripPanel2**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="7f09a-189">아래쪽 화살표 단추를 한 번 클릭 하 여 목록에서 세 번째 컨트롤을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="7f09a-190">**ToolStripPanel2** 컨트롤은 폼의 맨 위, 주 메뉴 및 기타 컨트롤의 위쪽에 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="7f09a-191">**문서 개요** 창에서 다양 한 컨트롤을 선택 하 고 z 순서에서 다른 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="7f09a-192">도킹 된 컨트롤의 배치에 대 한 z 순서의 효과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="7f09a-193">**편집** 메뉴에서 CTRL + Z 또는 **undo** 를 사용 하 여 변경 내용을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="7f09a-194">검사점-양식 테스트</span><span class="sxs-lookup"><span data-stu-id="7f09a-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="7f09a-195">**F5** 키를 눌러 폼을 컴파일하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="7f09a-196"><xref:System.Windows.Forms.ToolStrip> 컨트롤의 그립을 클릭 하 고 컨트롤을 폼의 다른 위치로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="7f09a-197"><xref:System.Windows.Forms.ToolStripPanel> 컨트롤 간에 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 끌어 놓을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7f09a-198">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7f09a-198">Next steps</span></span>

<span data-ttu-id="7f09a-199">이 연습에서는 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 메뉴 병합을 사용 하 여 MDI 부모 폼을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="7f09a-200">다양 한 용도로 <xref:System.Windows.Forms.ToolStrip> 컨트롤 패밀리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="7f09a-201"><xref:System.Windows.Forms.ContextMenuStrip>를 사용 하 여 컨트롤에 대 한 바로 가기 메뉴를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="7f09a-202">자세한 내용은 [ContextMenu 구성 요소 개요](contextmenu-component-overview-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f09a-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="7f09a-203">자동으로 채워진 표준 메뉴가 있는 폼을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="7f09a-204">자세한 내용은 [연습: 폼에 표준 메뉴 항목 제공](walkthrough-providing-standard-menu-items-to-a-form.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f09a-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="7f09a-205"><xref:System.Windows.Forms.ToolStrip> 컨트롤에 전문적인 모양을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f09a-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="7f09a-206">자세한 내용은 [방법: 응용 프로그램에 대 한 ToolStrip 렌더러 설정](how-to-set-the-toolstrip-renderer-for-an-application.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f09a-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7f09a-207">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f09a-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="7f09a-208">방법: MDI 상위 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="7f09a-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="7f09a-209">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="7f09a-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="7f09a-210">방법: MDI 드롭다운 메뉴에 MenuStrip 삽입</span><span class="sxs-lookup"><span data-stu-id="7f09a-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="7f09a-211">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7f09a-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
