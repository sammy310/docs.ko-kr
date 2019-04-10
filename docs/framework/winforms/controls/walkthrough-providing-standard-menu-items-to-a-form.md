---
title: '연습: 양식에 표준 메뉴 항목 제공'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: b4957a3f2efcb31594806a188e3d3bb10c2dac09
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296396"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="afce5-102">연습: 양식에 표준 메뉴 항목 제공</span><span class="sxs-lookup"><span data-stu-id="afce5-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="afce5-103"><xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하여 폼에 표준 메뉴를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="afce5-104">이 연습에 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.MenuStrip> 표준 메뉴를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="afce5-105">사용자가 메뉴 항목을 선택 하는 경우에 폼 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="afce5-106">다음 태스크를이 연습에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="afce5-107">Windows Forms 프로젝트를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-107">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="afce5-108">표준 메뉴를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-108">Creating a standard menu.</span></span>  
  
-   <span data-ttu-id="afce5-109">만들기는 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
-   <span data-ttu-id="afce5-110">메뉴 항목 선택을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="afce5-111">메뉴 항목 선택 항목을 표시 하는 표준 메뉴를 사용 하 여 폼을 완료 하면 더는 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="afce5-112">이 항목의 코드를 단일 목록으로 복사하려면 [방법: 폼에 표준 메뉴 항목 제공](how-to-provide-standard-menu-items-to-a-form.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afce5-113">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="afce5-114">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="afce5-115">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="afce5-115">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="afce5-116">전제 조건</span><span class="sxs-lookup"><span data-stu-id="afce5-116">Prerequisites</span></span>  
 <span data-ttu-id="afce5-117">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-117">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="afce5-118">만들고 Visual Studio를 설치한 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 실행 하는 일을 할 수 있는 충분 한 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="afce5-119">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="afce5-119">Creating the Project</span></span>  
 <span data-ttu-id="afce5-120">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="afce5-121">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="afce5-121">To create the project</span></span>  
  
1. <span data-ttu-id="afce5-122">라는 Windows 응용 프로그램 프로젝트를 만듭니다 **StandardMenuForm** (**파일** > **New** > **프로젝트**  >  **Visual C#** 하거나 **Visual Basic** > **클래식 데스크톱** > **Windows Forms 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="afce5-122">Create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="afce5-123">Windows Forms 디자이너에서 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-123">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="afce5-124">표준 메뉴 만들기</span><span class="sxs-lookup"><span data-stu-id="afce5-124">Creating a Standard Menu</span></span>  
 <span data-ttu-id="afce5-125">Windows Forms 디자이너를 자동으로 채울 수는 <xref:System.Windows.Forms.MenuStrip> 표준 메뉴 항목을 사용 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-125">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="afce5-126">표준 메뉴를 만들려면</span><span class="sxs-lookup"><span data-stu-id="afce5-126">To create a standard menu</span></span>  
  
1. <span data-ttu-id="afce5-127">**도구 상자**를 끌어를 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2. <span data-ttu-id="afce5-128">클릭 합니다 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 스마트 태그 문자 모양 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 선택한 **표준 항목 삽입**합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-128">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="afce5-129"><xref:System.Windows.Forms.MenuStrip> 컨트롤이 표준 메뉴 항목으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-129">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3. <span data-ttu-id="afce5-130">클릭 합니다 **파일** 메뉴 항목을 해당 기본 메뉴 항목 및 해당 아이콘을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afce5-130">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="afce5-131">StatusStrip 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="afce5-131">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="afce5-132">사용 된 <xref:System.Windows.Forms.StatusStrip> Windows Forms 응용 프로그램에 대 한 상태를 표시 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-132">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="afce5-133">현재 예제에서는 사용자가 선택한 메뉴 항목에 표시 됩니다는 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-133">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="afce5-134">StatusStrip 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="afce5-134">To create a StatusStrip control</span></span>  
  
1. <span data-ttu-id="afce5-135">**도구 상자**를 끌어를 <xref:System.Windows.Forms.StatusStrip> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="afce5-136"><xref:System.Windows.Forms.StatusStrip> 컨트롤은 자동으로 폼의 아래쪽에 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-136">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2. <span data-ttu-id="afce5-137">클릭 합니다 <xref:System.Windows.Forms.StatusStrip> 컨트롤의 드롭다운 단추를 선택 **statuslabel은** 추가할를 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤을 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-137">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="afce5-138">처리 항목 선택</span><span class="sxs-lookup"><span data-stu-id="afce5-138">Handling Item Selection</span></span>  
 <span data-ttu-id="afce5-139">처리는 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 메뉴 항목을 선택할 때 응답할 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-139">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="afce5-140">항목 선택을 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="afce5-140">To handle item selection</span></span>  
  
1. <span data-ttu-id="afce5-141">클릭 합니다 **파일** 만들기에서 만든 메뉴 항목을 표준 메뉴 섹션.</span><span class="sxs-lookup"><span data-stu-id="afce5-141">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2. <span data-ttu-id="afce5-142">**속성** 창에서 **이벤트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-142">In the **Properties** window, click **Events**.</span></span>  
  
3. <span data-ttu-id="afce5-143">두 번 클릭 하 여 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-143">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="afce5-144">Windows Forms 디자이너에 대 한 이벤트 처리기가 생성 된 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-144">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4. <span data-ttu-id="afce5-145">이벤트 처리기에 다음 코드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-145">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5. <span data-ttu-id="afce5-146">삽입 된 `UpdateStatus` 폼에 유틸리티 메서드 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-146">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="afce5-147">검사점</span><span class="sxs-lookup"><span data-stu-id="afce5-147">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="afce5-148">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="afce5-148">To test your form</span></span>  
  
1. <span data-ttu-id="afce5-149">F5 키를 눌러 컴파일하고 폼을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-149">Press F5 to compile and run your form.</span></span>  
  
2. <span data-ttu-id="afce5-150">클릭 합니다 **파일** 메뉴 항목 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-150">Click the **File** menu item to open the menu.</span></span>  
  
3. <span data-ttu-id="afce5-151">에 **파일** 메뉴 선택 항목 중 하나를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-151">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="afce5-152"><xref:System.Windows.Forms.StatusStrip> 컨트롤 선택한 항목을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-152">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="afce5-153">다음 단계</span><span class="sxs-lookup"><span data-stu-id="afce5-153">Next Steps</span></span>  
 <span data-ttu-id="afce5-154">이 연습에서는 표준 메뉴가 있는 폼을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-154">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="afce5-155">사용할 수는 <xref:System.Windows.Forms.ToolStrip> 다양 한 용도로 다른 컨트롤의 패밀리:</span><span class="sxs-lookup"><span data-stu-id="afce5-155">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="afce5-156">사용 하 여 컨트롤에 대 한 바로 가기 메뉴를 만들 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-156">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="afce5-157">자세한 내용은 [ContextMenu 구성 요소 개요](contextmenu-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-157">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="afce5-158">도킹 된 여러 문서 MDI (인터페이스) 양식을 만듭니다 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-158">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="afce5-159">자세한 내용은 [연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용 하 여 MDI 폼 만들기](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-159">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
-   <span data-ttu-id="afce5-160">제공에 <xref:System.Windows.Forms.ToolStrip> 전문적인 모양 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-160">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="afce5-161">자세한 내용은 [방법: 응용 프로그램에 대 한 ToolStrip 렌더러 설정](how-to-set-the-toolstrip-renderer-for-an-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afce5-161">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afce5-162">참고자료</span><span class="sxs-lookup"><span data-stu-id="afce5-162">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="afce5-163">MenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="afce5-163">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
