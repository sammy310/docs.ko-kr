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
ms.openlocfilehash: 62e137df53d06f5aedb2701b5727c25e52f35614
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61759887"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="44afb-102">연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="44afb-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="44afb-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스는 MDI(다중 문서 인터페이스) 응용 프로그램을 지원하고 <xref:System.Windows.Forms.MenuStrip> 컨트롤은 메뉴 병합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="44afb-104">MDI 폼은 <xref:System.Windows.Forms.ToolStrip> 컨트롤일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="44afb-105">이 연습에 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Forms.ToolStripPanel> MDI 폼을 사용 하 여 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="44afb-106">폼은 자식 메뉴와 메뉴 병합도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="44afb-107">다음 태스크를이 연습에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-107">The following tasks are illustrated in this walkthrough:</span></span>  
  
- <span data-ttu-id="44afb-108">Windows Forms 프로젝트를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-108">Creating a Windows Forms project.</span></span>  
  
- <span data-ttu-id="44afb-109">양식에 대 한 주 메뉴를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-109">Creating the main menu for your form.</span></span> <span data-ttu-id="44afb-110">메뉴의 실제 이름을 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-110">The actual name of the menu will vary.</span></span>  
  
- <span data-ttu-id="44afb-111">추가 합니다 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>  
  
- <span data-ttu-id="44afb-112">자식 폼을 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-112">Creating a child form.</span></span>  
  
- <span data-ttu-id="44afb-113">정렬 <xref:System.Windows.Forms.ToolStripPanel> z 순서를 기준으로 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>  
  
 <span data-ttu-id="44afb-114">메뉴 병합 및 이동 가능한 지 원하는 MDI 폼 작업을 완료 하면 더 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="44afb-115">이 항목의 코드를 단일 목록으로 복사하려면 [방법: 메뉴 병합 및 ToolStrip 컨트롤을 사용 하 여 MDI 폼 만들기](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44afb-116">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="44afb-117">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="44afb-118">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44afb-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="44afb-119">전제 조건</span><span class="sxs-lookup"><span data-stu-id="44afb-119">Prerequisites</span></span>  
 <span data-ttu-id="44afb-120">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-120">In order to complete this walkthrough, you will need:</span></span>  
  
- <span data-ttu-id="44afb-121">만들고 Visual Studio를 설치한 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 실행 하는 일을 할 수 있는 충분 한 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-121">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="44afb-122">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="44afb-122">Creating the Project</span></span>  
 <span data-ttu-id="44afb-123">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-123">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="44afb-124">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="44afb-124">To create the project</span></span>  
  
1. <span data-ttu-id="44afb-125">라는 Windows 응용 프로그램 프로젝트를 만듭니다 **MdiForm** (**파일** > **New** > **프로젝트**  >  **Visual C#** 하거나 **Visual Basic** > **클래식 바탕 화면** > **Windows Forms 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="44afb-125">Create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="44afb-126">Windows Forms 디자이너에서 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-126">In the Windows Forms Designer, select the form.</span></span>  
  
3. <span data-ttu-id="44afb-127">속성 창에서 값을 설정 합니다 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 에 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-127">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>  
  
## <a name="creating-the-main-menu"></a><span data-ttu-id="44afb-128">주 메뉴 만들기</span><span class="sxs-lookup"><span data-stu-id="44afb-128">Creating the Main Menu</span></span>  
 <span data-ttu-id="44afb-129">MDI 부모 폼 주 메뉴를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-129">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="44afb-130">주 메뉴에 항목 이라는 하나의 메뉴 **창을**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-130">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="44afb-131">사용 하 여 합니다 **창을** 메뉴 항목을 자식 폼을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-131">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="44afb-132">자식 폼의 메뉴 항목은 주 메뉴에 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-132">Menu items from child forms are merged into the main menu.</span></span>  
  
#### <a name="to-create-the-main-menu"></a><span data-ttu-id="44afb-133">주 메뉴를 만들려면</span><span class="sxs-lookup"><span data-stu-id="44afb-133">To create the Main menu</span></span>  
  
1. <span data-ttu-id="44afb-134">**도구 상자**를 끌어를 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>  
  
2. <span data-ttu-id="44afb-135">추가 <xref:System.Windows.Forms.ToolStripMenuItem> 에 <xref:System.Windows.Forms.MenuStrip> 제어 하 고 이름을 **창**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-135">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>  
  
3. <span data-ttu-id="44afb-136"><xref:System.Windows.Forms.MenuStrip> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-136">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
4. <span data-ttu-id="44afb-137">속성 창에서 값을 설정 합니다 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성을 `ToolStripMenuItem1`입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-137">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>  
  
5. <span data-ttu-id="44afb-138">하위 항목을 추가 합니다 **창을** 메뉴 항목을 선택한 후 이름을 하위 항목 **새로 만들기**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-138">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>  
  
6. <span data-ttu-id="44afb-139">속성 창에서 클릭 **이벤트**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-139">In the Properties window, click **Events**.</span></span>  
  
7. <span data-ttu-id="44afb-140">두 번 클릭 하 여 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-140">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
     <span data-ttu-id="44afb-141">Windows Forms 디자이너에 대 한 이벤트 처리기가 생성 된 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-141">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
8. <span data-ttu-id="44afb-142">이벤트 처리기에 다음 코드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-142">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="44afb-143">ToolStripPanel 컨트롤을 도구 상자에 추가</span><span class="sxs-lookup"><span data-stu-id="44afb-143">Adding the ToolStripPanel Control to the Toolbox</span></span>  
 <span data-ttu-id="44afb-144">사용 하는 경우 <xref:System.Windows.Forms.MenuStrip> 있어야 하는 MDI 폼을 사용 하 여 컨트롤을 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-144">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="44afb-145">추가 해야 합니다는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 합니다 **도구 상자** Windows Forms 디자이너에서 MDI 폼을 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-145">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="44afb-146">도구 상자에 ToolStripPanel 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="44afb-146">To add the ToolStripPanel control to the Toolbox</span></span>  
  
1. <span data-ttu-id="44afb-147">열기는 **도구 상자**를 클릭 하 고는 **모든 Windows Forms** 탭을 사용할 수 있는 Windows Forms 컨트롤을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-147">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>  
  
2. <span data-ttu-id="44afb-148">바로 가기 메뉴를 열고 마우스 오른쪽 단추로 클릭 **선택 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-148">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>  
  
3. <span data-ttu-id="44afb-149">에 **도구 상자 항목 선택** 대화 상자에서 아래쪽으로 스크롤하여 합니다 **이름** 열을 찾을 때까지 **ToolStripPanel**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-149">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>  
  
4. <span data-ttu-id="44afb-150">확인란을 선택 **ToolStripPanel**를 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-150">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="44afb-151">합니다 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤에 표시 합니다 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-151">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>  
  
## <a name="creating-a-child-form"></a><span data-ttu-id="44afb-152">자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="44afb-152">Creating a Child Form</span></span>  
 <span data-ttu-id="44afb-153">이 절차에서는 자체는 별도 자식 폼 클래스를 정의 합니다 <xref:System.Windows.Forms.MenuStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-153">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="44afb-154">이 폼에 대 한 메뉴 항목은 부모 폼의 설정과 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-154">The menu items for this form are merged with those of the parent form.</span></span>  
  
#### <a name="to-define-a-child-form"></a><span data-ttu-id="44afb-155">자식 폼을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="44afb-155">To define a child form</span></span>  
  
1. <span data-ttu-id="44afb-156">라는 새 폼을 추가 `ChildForm` 프로젝트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-156">Add a new form named `ChildForm` to the project.</span></span>  
  
     <span data-ttu-id="44afb-157">자세한 내용은 [방법: Windows Forms 프로젝트에 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-157">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="44afb-158">**도구 상자**를 끌어를 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 자식 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-158">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>  
  
3. <span data-ttu-id="44afb-159">클릭 합니다 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 스마트 태그 문자 모양 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))를 선택한 후 **항목 편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-159">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>  
  
4. <span data-ttu-id="44afb-160">에 **항목 컬렉션 편집기** 대화 상자에서 새 <xref:System.Windows.Forms.ToolStripMenuItem> 라는 **ChildMenuItem** 자식 메뉴.</span><span class="sxs-lookup"><span data-stu-id="44afb-160">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>  
  
     <span data-ttu-id="44afb-161">자세한 내용은 [ToolStrip 항목 컬렉션 편집기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-161">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>  
  
## <a name="testing-the-form"></a><span data-ttu-id="44afb-162">형식 테스트</span><span class="sxs-lookup"><span data-stu-id="44afb-162">Testing the Form</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="44afb-163">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="44afb-163">To test your form</span></span>  
  
1. <span data-ttu-id="44afb-164">F5 키를 눌러 컴파일하고 폼을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-164">Press F5 to compile and run your form.</span></span>  
  
2. <span data-ttu-id="44afb-165">클릭 합니다 **창을** 메뉴 항목 메뉴를 연 마우스 클릭 **새로 만들기**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-165">Click the **Window** menu item to open the menu, and then click **New**.</span></span>  
  
     <span data-ttu-id="44afb-166">새 자식 폼을 폼의 MDI 클라이언트 영역에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-166">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="44afb-167">자식 폼의 메뉴가 주 메뉴와 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-167">The child form's menu is merged with the main menu.</span></span>  
  
3. <span data-ttu-id="44afb-168">자식 폼을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-168">Close the child form.</span></span>  
  
     <span data-ttu-id="44afb-169">자식 폼의 메뉴가 주 메뉴에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-169">The child form's menu is removed from the main menu.</span></span>  
  
4. <span data-ttu-id="44afb-170">클릭 **새로 만들기** 여러 번입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-170">Click **New** several times.</span></span>  
  
     <span data-ttu-id="44afb-171">자식 폼이 자동으로 나열 합니다 **창** 때문에 메뉴 항목는 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-171">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>  
  
## <a name="adding-toolstrip-support"></a><span data-ttu-id="44afb-172">ToolStrip 지원 추가</span><span class="sxs-lookup"><span data-stu-id="44afb-172">Adding ToolStrip Support</span></span>  
 <span data-ttu-id="44afb-173">이 절차에서는 추가 4 <xref:System.Windows.Forms.ToolStrip> MDI 부모 폼에 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-173">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="44afb-174">각 <xref:System.Windows.Forms.ToolStrip> 컨트롤 내에 추가 되는 <xref:System.Windows.Forms.ToolStripPanel> 폼의 가장자리에 도킹 된 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-174">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a><span data-ttu-id="44afb-175">ToolStrip 컨트롤을 MDI 부모 폼에 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="44afb-175">To add ToolStrip controls to the MDI parent form</span></span>  
  
1. <span data-ttu-id="44afb-176">**도구 상자**를 끌어를 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-176">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>  
  
2. <span data-ttu-id="44afb-177">사용 하 여는 <xref:System.Windows.Forms.ToolStripPanel> 선택 컨트롤을 두 번 클릭 합니다 <xref:System.Windows.Forms.ToolStrip> 에서 제어를 **도구 상자**.</span><span class="sxs-lookup"><span data-stu-id="44afb-177">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>  
  
     <span data-ttu-id="44afb-178">A <xref:System.Windows.Forms.ToolStrip> 컨트롤에서 만드는 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-178">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
3. <span data-ttu-id="44afb-179"><xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-179">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
4. <span data-ttu-id="44afb-180">속성 창에서 컨트롤의 값을 변경 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Left>입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-180">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>  
  
     <span data-ttu-id="44afb-181"><xref:System.Windows.Forms.ToolStripPanel> 주 메뉴 아래 폼의 왼쪽에 도킹을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-181">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="44afb-182">MDI 클라이언트 영역에 맞게 조정 된 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-182">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
5. <span data-ttu-id="44afb-183">1 ~ 4 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-183">Repeat steps 1 through 4.</span></span>  
  
     <span data-ttu-id="44afb-184">새 도킹 <xref:System.Windows.Forms.ToolStripPanel> 폼의 맨 위에 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-184">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>  
  
     <span data-ttu-id="44afb-185">합니다 <xref:System.Windows.Forms.ToolStripPanel> 주 메뉴 아래 하지만 첫 번째 오른쪽이 컨트롤이 도킹 되 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-185">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="44afb-186">이 단계에서는 올바른 배치에 z-순서의 중요성을 보여 줍니다 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-186">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
6. <span data-ttu-id="44afb-187">두 개 이상에 대해 1 ~ 4 단계를 반복 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-187">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
     <span data-ttu-id="44afb-188">새 도킹 <xref:System.Windows.Forms.ToolStripPanel> 오른쪽 아래 폼의 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-188">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="44afb-189">ToolStripPanel 컨트롤 Z 순서로 정렬</span><span class="sxs-lookup"><span data-stu-id="44afb-189">Arranging ToolStripPanel Controls by Z-order</span></span>  
 <span data-ttu-id="44afb-190">도킹 된 위치의 <xref:System.Windows.Forms.ToolStripPanel> MDI 폼의 컨트롤로 z-순서에서 컨트롤의 위치에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-190">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="44afb-191">문서 개요 창에서 컨트롤의 z 순서를 쉽게 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-191">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="44afb-192">Z 순서에 따라 ToolStripPanel 컨트롤을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="44afb-192">To arrange ToolStripPanel controls by Z-order</span></span>  
  
1. <span data-ttu-id="44afb-193">에 **보기** 메뉴에서 클릭 **다른 Windows**를 클릭 하 고 **문서 개요**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-193">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>  
  
     <span data-ttu-id="44afb-194">배열에 <xref:System.Windows.Forms.ToolStripPanel> 이전 절차에서 컨트롤 표준이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-194">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="44afb-195">즉, z-순서가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-195">This is because the z-order is not correct.</span></span> <span data-ttu-id="44afb-196">문서 개요 창 컨트롤의 z 순서를 변경 하려면 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-196">Use the Document Outline window to change the z-order of the controls.</span></span>  
  
2. <span data-ttu-id="44afb-197">문서 개요 창에서 선택 **ToolStripPanel4**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-197">In the Document Outline window, select **ToolStripPanel4**.</span></span>  
  
3. <span data-ttu-id="44afb-198">아래쪽 화살표 단추를 클릭까지 반복 해 서 **ToolStripPanel4** 목록의 맨 아래에 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-198">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>  
  
     <span data-ttu-id="44afb-199">합니다 **ToolStripPanel4** 컨트롤 다른 컨트롤 아래에 있는 폼의 아래쪽에 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-199">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>  
  
4. <span data-ttu-id="44afb-200">선택 **ToolStripPanel2**합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-200">Select **ToolStripPanel2**.</span></span>  
  
5. <span data-ttu-id="44afb-201">컨트롤의 세 번째 위치 목록에서 아래쪽 화살표 단추를 한 번을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-201">Click the down-arrow button one time to position the control third in the list.</span></span>  
  
     <span data-ttu-id="44afb-202">합니다 **ToolStripPanel2** 컨트롤 주 메뉴 아래 및 위의 다른 컨트롤을 폼의 위쪽에 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-202">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>  
  
6. <span data-ttu-id="44afb-203">다양 한 컨트롤을 선택 합니다 **문서 개요** 창 z-순서에서 다른 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-203">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="44afb-204">Z 순서 도킹 된 컨트롤의 배치에 미치는 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-204">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="44afb-205">CTRL + Z를 사용 하 여 또는 **실행 취소** 에 **편집** 변경 내용을 취소 하는 메뉴입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-205">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="44afb-206">검사점</span><span class="sxs-lookup"><span data-stu-id="44afb-206">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="44afb-207">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="44afb-207">To test your form</span></span>  
  
1. <span data-ttu-id="44afb-208">F5 키를 눌러 컴파일하고 폼을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-208">Press F5 to compile and run your form.</span></span>  
  
2. <span data-ttu-id="44afb-209">그립을 클릭 한 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 폼에 컨트롤을 다른 위치로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-209">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>  
  
     <span data-ttu-id="44afb-210">끌어 놓을 수 있습니다는 <xref:System.Windows.Forms.ToolStrip> 간에 제어 <xref:System.Windows.Forms.ToolStripPanel> 다른 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-210">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="44afb-211">다음 단계</span><span class="sxs-lookup"><span data-stu-id="44afb-211">Next Steps</span></span>  
 <span data-ttu-id="44afb-212">사용 하 여 MDI 부모 폼이 연습에서는 만든 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 메뉴 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-212">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="44afb-213">사용할 수는 <xref:System.Windows.Forms.ToolStrip> 다양 한 용도로 다른 컨트롤의 패밀리:</span><span class="sxs-lookup"><span data-stu-id="44afb-213">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
- <span data-ttu-id="44afb-214">사용 하 여 컨트롤에 대 한 바로 가기 메뉴를 만들 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-214">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="44afb-215">자세한 내용은 [ContextMenu 구성 요소 개요](contextmenu-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-215">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
- <span data-ttu-id="44afb-216">자동으로 채워진된 표준 메뉴를 사용 하 여 폼을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-216">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="44afb-217">자세한 내용은 [연습: 폼에 표준 메뉴 항목 제공](walkthrough-providing-standard-menu-items-to-a-form.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-217">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
- <span data-ttu-id="44afb-218">제공에 <xref:System.Windows.Forms.ToolStrip> 전문적인 모양 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-218">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="44afb-219">자세한 내용은 [방법: 응용 프로그램에 대 한 ToolStrip 렌더러 설정](how-to-set-the-toolstrip-renderer-for-an-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44afb-219">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44afb-220">참고자료</span><span class="sxs-lookup"><span data-stu-id="44afb-220">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="44afb-221">방법: MDI 부모 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="44afb-221">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="44afb-222">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="44afb-222">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="44afb-223">방법: MDI 드롭 다운 메뉴에 MenuStrip 삽입</span><span class="sxs-lookup"><span data-stu-id="44afb-223">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="44afb-224">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="44afb-224">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
