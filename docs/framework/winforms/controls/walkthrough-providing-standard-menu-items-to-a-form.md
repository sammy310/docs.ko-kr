---
title: '연습: 폼에 표준 메뉴 항목 제공'
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
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628776"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="90605-102">연습: 폼에 표준 메뉴 항목 제공</span><span class="sxs-lookup"><span data-stu-id="90605-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="90605-103"><xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하여 폼에 표준 메뉴를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90605-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="90605-104">이 연습에서는 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용 하 여 표준 메뉴를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90605-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="90605-105">또한 사용자가 메뉴 항목을 선택 하면 폼이 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="90605-106">이 연습에서는 다음 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90605-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="90605-107">Windows Forms 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="90605-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="90605-108">표준 메뉴 만들기</span><span class="sxs-lookup"><span data-stu-id="90605-108">Creating a standard menu.</span></span>

- <span data-ttu-id="90605-109"><xref:System.Windows.Forms.StatusStrip> 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="90605-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="90605-110">메뉴 항목 선택 항목을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-110">Handling menu item selection.</span></span>

<span data-ttu-id="90605-111">작업이 완료 되 면 <xref:System.Windows.Forms.StatusStrip> 컨트롤에서 메뉴 항목을 선택 하 여 표시 하는 표준 메뉴가 있는 폼을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90605-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="90605-112">이 항목의 코드를 단일 목록으로 복사 하려면 [방법: 폼에 표준 메뉴 항목 제공](how-to-provide-standard-menu-items-to-a-form.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90605-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="90605-113">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="90605-113">Prerequisites</span></span>

<span data-ttu-id="90605-114">이 연습을 완료 하려면 Visual Studio가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="90605-115">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="90605-115">Create the project</span></span>

1. <span data-ttu-id="90605-116">Visual Studio에서 **standardmenuform** (**파일** > **새** > **프로젝트** >  **C# Visual** 또는 **Visual Basic** > **클래식 Desktop** > **응용 프로그램**) 이라는 Windows 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="90605-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="90605-117">Windows Forms 디자이너에서 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="90605-118">표준 메뉴 만들기</span><span class="sxs-lookup"><span data-stu-id="90605-118">Create a standard menu</span></span>

<span data-ttu-id="90605-119">Windows Forms 디자이너은 표준 메뉴 항목으로 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 자동으로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90605-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="90605-120">**도구 상자**에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="90605-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="90605-121"><xref:System.Windows.Forms.MenuStrip> 컨트롤의 디자이너 작업 문자 모양 (![작은 검정색 화살표](./media/designer-actions-glyph.gif))을 클릭 하 고 **표준 항목 삽입**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-121">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="90605-122"><xref:System.Windows.Forms.MenuStrip> 컨트롤이 표준 메뉴 항목으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="90605-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="90605-123">**파일** 메뉴 항목을 클릭 하 여 기본 메뉴 항목 및 해당 아이콘을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="90605-124">StatusStrip 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="90605-124">Create a StatusStrip control</span></span>

<span data-ttu-id="90605-125"><xref:System.Windows.Forms.StatusStrip> 컨트롤을 사용 하 여 Windows Forms 응용 프로그램의 상태를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="90605-126">현재 예제에서 사용자가 선택한 메뉴 항목은 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90605-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="90605-127">**도구 상자**에서 <xref:System.Windows.Forms.StatusStrip> 컨트롤을 폼으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="90605-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="90605-128"><xref:System.Windows.Forms.StatusStrip> 컨트롤은 폼의 아래쪽에 자동으로 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90605-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="90605-129"><xref:System.Windows.Forms.StatusStrip> 컨트롤의 드롭다운 단추를 클릭 하 고 **Statuslabel** 을 선택 하 여 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤을 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="90605-130">항목 선택 처리</span><span class="sxs-lookup"><span data-stu-id="90605-130">Handle item selection</span></span>

<span data-ttu-id="90605-131">사용자가 메뉴 항목을 선택할 때 응답 하는 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="90605-132">표준 메뉴 만들기 섹션에서 만든 **파일** 메뉴 항목을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="90605-133">**속성** 창에서 **이벤트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="90605-134"><xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="90605-135">Windows Forms 디자이너 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트에 대 한 이벤트 처리기를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="90605-136">다음 코드를 이벤트 처리기에 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="90605-137">`UpdateStatus` 유틸리티 메서드 정의를 양식에 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="90605-138">검사점-양식 테스트</span><span class="sxs-lookup"><span data-stu-id="90605-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="90605-139">**F5** 키를 눌러 폼을 컴파일하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="90605-140">**파일** 메뉴 항목을 클릭 하 여 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="90605-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="90605-141">**파일** 메뉴에서 항목 중 하나를 클릭 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="90605-142"><xref:System.Windows.Forms.StatusStrip> 컨트롤은 선택한 항목을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="90605-143">다음 단계</span><span class="sxs-lookup"><span data-stu-id="90605-143">Next steps</span></span>

<span data-ttu-id="90605-144">이 연습에서는 표준 메뉴가 있는 폼을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="90605-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="90605-145">다양 한 용도로 <xref:System.Windows.Forms.ToolStrip> 컨트롤 패밀리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90605-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="90605-146"><xref:System.Windows.Forms.ContextMenuStrip>를 사용 하 여 컨트롤에 대 한 바로 가기 메뉴를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="90605-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="90605-147">자세한 내용은 [ContextMenu 구성 요소 개요](contextmenu-component-overview-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90605-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="90605-148">도킹 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 사용 하 여 MDI (다중 문서 인터페이스) 폼을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="90605-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="90605-149">자세한 내용은 [연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용 하 여 MDI 폼 만들기](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90605-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="90605-150"><xref:System.Windows.Forms.ToolStrip> 컨트롤에 전문적인 모양을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="90605-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="90605-151">자세한 내용은 [방법: 응용 프로그램에 대 한 ToolStrip 렌더러 설정](how-to-set-the-toolstrip-renderer-for-an-application.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90605-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="90605-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90605-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="90605-153">MenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="90605-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
