---
title: '연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 양식 만들기'
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
ms.openlocfilehash: 5853760231cbece27805923c009d83e16c9b0a5e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211554"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="e0b67-102">연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="e0b67-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="e0b67-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스는 MDI(다중 문서 인터페이스) 애플리케이션을 지원하고 <xref:System.Windows.Forms.MenuStrip> 컨트롤은 메뉴 병합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="e0b67-104">MDI 폼은 <xref:System.Windows.Forms.ToolStrip> 컨트롤일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="e0b67-105">이 연습에 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Forms.ToolStripPanel> MDI 폼을 사용 하 여 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="e0b67-106">폼은 자식 메뉴와 메뉴 병합도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="e0b67-107">다음 태스크를이 연습에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="e0b67-108">Windows Forms 프로젝트를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="e0b67-109">양식에 대 한 주 메뉴를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-109">Creating the main menu for your form.</span></span> <span data-ttu-id="e0b67-110">메뉴의 실제 이름을 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="e0b67-111">추가 합니다 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="e0b67-112">자식 폼을 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-112">Creating a child form.</span></span>

- <span data-ttu-id="e0b67-113">정렬 <xref:System.Windows.Forms.ToolStripPanel> z 순서를 기준으로 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="e0b67-114">메뉴 병합 및 이동 가능한 지 원하는 MDI 폼 작업을 완료 하면 더 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="e0b67-115">이 항목의 코드를 단일 목록으로 복사하려면 [방법: 메뉴 병합 및 ToolStrip 컨트롤을 사용 하 여 MDI 폼 만들기](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e0b67-116">전제 조건</span><span class="sxs-lookup"><span data-stu-id="e0b67-116">Prerequisites</span></span>

<span data-ttu-id="e0b67-117">이 연습을 완료 하려면 Visual Studio를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="e0b67-118">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-118">Create the project</span></span>

1. <span data-ttu-id="e0b67-119">Visual Studio에서 라는 Windows 응용 프로그램 프로젝트를 만듭니다 **MdiForm** (**파일** > **New** > **프로젝트**  >  **시각적 C#**  하거나 **Visual Basic** > **클래식 데스크톱**  >   **Windows Forms 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="e0b67-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="e0b67-120">Windows Forms 디자이너에서 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="e0b67-121">속성 창에서 값을 설정 합니다 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 에 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="e0b67-122">주 메뉴 만들기</span><span class="sxs-lookup"><span data-stu-id="e0b67-122">Create the main menu</span></span>

<span data-ttu-id="e0b67-123">MDI 부모 폼 주 메뉴를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="e0b67-124">주 메뉴에 항목 이라는 하나의 메뉴 **창을**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="e0b67-125">사용 하 여 합니다 **창을** 메뉴 항목을 자식 폼을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="e0b67-126">자식 폼의 메뉴 항목은 주 메뉴에 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="e0b67-127">**도구 상자**를 끌어를 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="e0b67-128">추가 <xref:System.Windows.Forms.ToolStripMenuItem> 에 <xref:System.Windows.Forms.MenuStrip> 제어 하 고 이름을 **창**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="e0b67-129"><xref:System.Windows.Forms.MenuStrip> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="e0b67-130">속성 창에서 값을 설정 합니다 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성을 `ToolStripMenuItem1`입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="e0b67-131">하위 항목을 추가 합니다 **창을** 메뉴 항목을 선택한 후 이름을 하위 항목 **새로 만들기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="e0b67-132">속성 창에서 클릭 **이벤트**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="e0b67-133">두 번 클릭 하 여 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="e0b67-134">Windows Forms 디자이너에 대 한 이벤트 처리기가 생성 된 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="e0b67-135">이벤트 처리기에 다음 코드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="e0b67-136">ToolStripPanel 컨트롤을 도구 상자에 추가</span><span class="sxs-lookup"><span data-stu-id="e0b67-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="e0b67-137">사용 하는 경우 <xref:System.Windows.Forms.MenuStrip> 있어야 하는 MDI 폼을 사용 하 여 컨트롤을 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="e0b67-138">추가 해야 합니다는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 합니다 **도구 상자** Windows Forms 디자이너에서 MDI 폼을 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="e0b67-139">열기는 **도구 상자**를 클릭 하 고는 **모든 Windows Forms** 탭을 사용할 수 있는 Windows Forms 컨트롤을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="e0b67-140">바로 가기 메뉴를 열고 마우스 오른쪽 단추로 클릭 **선택 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="e0b67-141">에 **도구 상자 항목 선택** 대화 상자에서 아래쪽으로 스크롤하여 합니다 **이름** 열을 찾을 때까지 **ToolStripPanel**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="e0b67-142">확인란을 선택 **ToolStripPanel**를 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="e0b67-143">합니다 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤에 표시 합니다 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="e0b67-144">자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="e0b67-144">Create a child form</span></span>

<span data-ttu-id="e0b67-145">이 절차에서는 자체는 별도 자식 폼 클래스를 정의 합니다 <xref:System.Windows.Forms.MenuStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="e0b67-146">이 폼에 대 한 메뉴 항목은 부모 폼의 설정과 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="e0b67-147">라는 새 폼을 추가 `ChildForm` 프로젝트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="e0b67-148">자세한 내용은 [방법: Windows Forms 프로젝트에 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-148">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="e0b67-149">**도구 상자**를 끌어를 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 자식 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="e0b67-150">클릭 합니다 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 스마트 태그 문자 모양 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))를 선택한 후 **항목 편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-150">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="e0b67-151">에 **항목 컬렉션 편집기** 대화 상자에서 새 <xref:System.Windows.Forms.ToolStripMenuItem> 라는 **ChildMenuItem** 자식 메뉴.</span><span class="sxs-lookup"><span data-stu-id="e0b67-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="e0b67-152">자세한 내용은 [ToolStrip 항목 컬렉션 편집기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-152">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="e0b67-153">형식 테스트</span><span class="sxs-lookup"><span data-stu-id="e0b67-153">Test the form</span></span>

1. <span data-ttu-id="e0b67-154">키를 눌러 **F5** 컴파일 및 폼을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="e0b67-155">클릭 합니다 **창을** 메뉴 항목 메뉴를 연 마우스 클릭 **새로 만들기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="e0b67-156">새 자식 폼을 폼의 MDI 클라이언트 영역에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="e0b67-157">자식 폼의 메뉴가 주 메뉴와 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="e0b67-158">자식 폼을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-158">Close the child form.</span></span>

     <span data-ttu-id="e0b67-159">자식 폼의 메뉴가 주 메뉴에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="e0b67-160">클릭 **새로 만들기** 여러 번입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-160">Click **New** several times.</span></span>

     <span data-ttu-id="e0b67-161">자식 폼이 자동으로 나열 합니다 **창** 때문에 메뉴 항목는 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="e0b67-162">ToolStrip 지원 추가</span><span class="sxs-lookup"><span data-stu-id="e0b67-162">Add ToolStrip support</span></span>

<span data-ttu-id="e0b67-163">이 절차에서는 추가 4 <xref:System.Windows.Forms.ToolStrip> MDI 부모 폼에 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="e0b67-164">각 <xref:System.Windows.Forms.ToolStrip> 컨트롤 내에 추가 되는 <xref:System.Windows.Forms.ToolStripPanel> 폼의 가장자리에 도킹 된 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="e0b67-165">**도구 상자**를 끌어를 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="e0b67-166">사용 하 여는 <xref:System.Windows.Forms.ToolStripPanel> 선택 컨트롤을 두 번 클릭 합니다 <xref:System.Windows.Forms.ToolStrip> 에서 제어를 **도구 상자**.</span><span class="sxs-lookup"><span data-stu-id="e0b67-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="e0b67-167">A <xref:System.Windows.Forms.ToolStrip> 컨트롤에서 만드는 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="e0b67-168"><xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="e0b67-169">속성 창에서 컨트롤의 값을 변경 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Left>입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="e0b67-170"><xref:System.Windows.Forms.ToolStripPanel> 주 메뉴 아래 폼의 왼쪽에 도킹을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="e0b67-171">MDI 클라이언트 영역에 맞게 조정 된 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="e0b67-172">1 ~ 4 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="e0b67-173">새 도킹 <xref:System.Windows.Forms.ToolStripPanel> 폼의 맨 위에 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="e0b67-174">합니다 <xref:System.Windows.Forms.ToolStripPanel> 주 메뉴 아래 하지만 첫 번째 오른쪽이 컨트롤이 도킹 되 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="e0b67-175">이 단계에서는 올바른 배치에 z-순서의 중요성을 보여 줍니다 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="e0b67-176">두 개 이상에 대해 1 ~ 4 단계를 반복 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="e0b67-177">새 도킹 <xref:System.Windows.Forms.ToolStripPanel> 오른쪽 아래 폼의 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="e0b67-178">ToolStripPanel 컨트롤 Z 순서로 정렬</span><span class="sxs-lookup"><span data-stu-id="e0b67-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="e0b67-179">도킹 된 위치의 <xref:System.Windows.Forms.ToolStripPanel> MDI 폼의 컨트롤로 z-순서에서 컨트롤의 위치에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="e0b67-180">문서 개요 창에서 컨트롤의 z 순서를 쉽게 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="e0b67-181">에 **보기** 메뉴에서 클릭 **다른 Windows**를 클릭 하 고 **문서 개요**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="e0b67-182">배열에 <xref:System.Windows.Forms.ToolStripPanel> 이전 절차에서 컨트롤 표준이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="e0b67-183">즉, z-순서가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="e0b67-184">문서 개요 창 컨트롤의 z 순서를 변경 하려면 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="e0b67-185">문서 개요 창에서 선택 **ToolStripPanel4**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="e0b67-186">아래쪽 화살표 단추를 클릭까지 반복 해 서 **ToolStripPanel4** 목록의 맨 아래에 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="e0b67-187">합니다 **ToolStripPanel4** 컨트롤 다른 컨트롤 아래에 있는 폼의 아래쪽에 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="e0b67-188">선택 **ToolStripPanel2**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="e0b67-189">컨트롤의 세 번째 위치 목록에서 아래쪽 화살표 단추를 한 번을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="e0b67-190">합니다 **ToolStripPanel2** 컨트롤 주 메뉴 아래 및 위의 다른 컨트롤을 폼의 위쪽에 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="e0b67-191">다양 한 컨트롤을 선택 합니다 **문서 개요** 창 z-순서에서 다른 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="e0b67-192">Z 순서 도킹 된 컨트롤의 배치에 미치는 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="e0b67-193">CTRL + Z를 사용 하 여 또는 **실행 취소** 에 **편집** 변경 내용을 취소 하는 메뉴입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="e0b67-194">검사점-폼 테스트</span><span class="sxs-lookup"><span data-stu-id="e0b67-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="e0b67-195">키를 눌러 **F5** 컴파일 및 폼을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="e0b67-196">그립을 클릭 한 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 폼에 컨트롤을 다른 위치로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="e0b67-197">끌어 놓을 수 있습니다는 <xref:System.Windows.Forms.ToolStrip> 간에 제어 <xref:System.Windows.Forms.ToolStripPanel> 다른 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e0b67-198">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e0b67-198">Next steps</span></span>

<span data-ttu-id="e0b67-199">사용 하 여 MDI 부모 폼이 연습에서는 만든 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 메뉴 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="e0b67-200">사용할 수는 <xref:System.Windows.Forms.ToolStrip> 다양 한 용도로 다른 컨트롤의 패밀리:</span><span class="sxs-lookup"><span data-stu-id="e0b67-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="e0b67-201">사용 하 여 컨트롤에 대 한 바로 가기 메뉴를 만들 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="e0b67-202">자세한 내용은 [ContextMenu 구성 요소 개요](contextmenu-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="e0b67-203">자동으로 채워진된 표준 메뉴를 사용 하 여 폼을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="e0b67-204">자세한 내용은 [연습: 폼에 표준 메뉴 항목 제공](walkthrough-providing-standard-menu-items-to-a-form.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="e0b67-205">제공에 <xref:System.Windows.Forms.ToolStrip> 전문적인 모양 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="e0b67-206">자세한 내용은 [방법: 응용 프로그램에 대 한 ToolStrip 렌더러 설정](how-to-set-the-toolstrip-renderer-for-an-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b67-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0b67-207">참고자료</span><span class="sxs-lookup"><span data-stu-id="e0b67-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="e0b67-208">방법: MDI 부모 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="e0b67-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="e0b67-209">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="e0b67-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="e0b67-210">방법: MDI 드롭 다운 메뉴에 MenuStrip 삽입</span><span class="sxs-lookup"><span data-stu-id="e0b67-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="e0b67-211">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e0b67-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
