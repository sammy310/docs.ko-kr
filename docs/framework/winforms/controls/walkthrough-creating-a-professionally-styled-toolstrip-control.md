---
title: '연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 526cb509d780abdbf3db6e15504616de19daae83
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336553"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="a6642-102">연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="a6642-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="a6642-103">응용 프로그램을 제공할 수 있습니다 <xref:System.Windows.Forms.ToolStrip> 에서 파생 된 고유한 클래스를 작성 하 여 전문적인 모양 및 동작을 제어 합니다 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="a6642-104">이 연습에 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Forms.ToolStrip> 와 비슷한 복합 컨트롤을 만드는 컨트롤을 **탐색 창** Microsoft® Outlook®에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="a6642-105">다음 태스크를이 연습에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-105">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="a6642-106">Windows 컨트롤 라이브러리 프로젝트를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-106">Creating a Windows Control Library project.</span></span>  
  
-   <span data-ttu-id="a6642-107">StackView 컨트롤을 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-107">Designing the StackView Control.</span></span>  
  
-   <span data-ttu-id="a6642-108">사용자 지정 렌더러를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-108">Implementing a Custom Renderer.</span></span>  
  
 <span data-ttu-id="a6642-109">작업을 완료 하는 경우에 전문적인 모양의 Microsoft Office® XP 컨트롤을 사용 하 여 재사용 가능한 사용자 지정 클라이언트 컨트롤을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>  
  
 <span data-ttu-id="a6642-110">이 항목의 코드를 단일 목록으로 복사하려면 [방법: 전문적인 스타일의 ToolStrip 컨트롤 만들기](how-to-create-a-professionally-styled-toolstrip-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6642-111">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-111">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a6642-112">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-112">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a6642-113">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6642-113">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a6642-114">전제 조건</span><span class="sxs-lookup"><span data-stu-id="a6642-114">Prerequisites</span></span>  
 <span data-ttu-id="a6642-115">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-115">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="a6642-116">만들고 Visual Studio를 설치한 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 실행 하는 일을 할 수 있는 충분 한 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-116">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-a-windows-control-library-project"></a><span data-ttu-id="a6642-117">Windows 컨트롤 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a6642-117">Creating a Windows Control Library Project</span></span>  
 <span data-ttu-id="a6642-118">첫 번째 단계에서는 컨트롤 라이브러리 프로젝트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-118">The first step is to create the control library project.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="a6642-119">컨트롤 라이브러리 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a6642-119">To create the control library project</span></span>  
  
1. <span data-ttu-id="a6642-120">라는 새 Windows 컨트롤 라이브러리 프로젝트를 만듭니다 `StackViewLibrary`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-120">Create a new Windows Control Library project named `StackViewLibrary`.</span></span>  
  
2. <span data-ttu-id="a6642-121">**솔루션 탐색기**, 선택한 언어에 따라 "UserControl1.cs" 또는 "UserControl1.vb" 라는 소스 파일을 삭제 하 여 프로젝트의 기본 컨트롤을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-121">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>  
  
     <span data-ttu-id="a6642-122">자세한 내용은 [방법: 제거, 삭제 및 항목을 제외](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-122">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>  
  
3. <span data-ttu-id="a6642-123">새 <xref:System.Windows.Forms.UserControl> 항목을 **StackViewLibrary** 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-123">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="a6642-124">새 소스 파일의 기본 이름을 지정 `StackView`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-124">Give the new source file a base name of `StackView`.</span></span>  
  
## <a name="designing-the-stackview-control"></a><span data-ttu-id="a6642-125">StackView 컨트롤 디자인</span><span class="sxs-lookup"><span data-stu-id="a6642-125">Designing the StackView Control</span></span>  
 <span data-ttu-id="a6642-126">합니다 `StackView` 자식이 하나를 사용 하 여 복합 컨트롤 <xref:System.Windows.Forms.ToolStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-126">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="a6642-127">복합 컨트롤에 대 한 자세한 내용은 참조 하세요. [종류의 사용자 지정 컨트롤](varieties-of-custom-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-127">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>  
  
#### <a name="to-design-the-stackview-control"></a><span data-ttu-id="a6642-128">StackView 컨트롤을 디자인 하려면</span><span class="sxs-lookup"><span data-stu-id="a6642-128">To design the StackView control</span></span>  
  
1. <span data-ttu-id="a6642-129">**도구 상자**를 끌어를 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 디자인 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>  
  
2. <span data-ttu-id="a6642-130">에 **속성** 창에서 <xref:System.Windows.Forms.ToolStrip> 다음 표에 따라 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-130">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="a6642-131">속성</span><span class="sxs-lookup"><span data-stu-id="a6642-131">Property</span></span>|<span data-ttu-id="a6642-132">값</span><span class="sxs-lookup"><span data-stu-id="a6642-132">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="a6642-133">이름</span><span class="sxs-lookup"><span data-stu-id="a6642-133">Name</span></span>|`stackStrip`|  
    |<span data-ttu-id="a6642-134">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="a6642-134">CanOverflow</span></span>|`false`|  
    |<span data-ttu-id="a6642-135">도킹</span><span class="sxs-lookup"><span data-stu-id="a6642-135">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |<span data-ttu-id="a6642-136">글꼴</span><span class="sxs-lookup"><span data-stu-id="a6642-136">Font</span></span>|`Tahoma, 10pt, style=Bold`|  
    |<span data-ttu-id="a6642-137">GripStyle</span><span class="sxs-lookup"><span data-stu-id="a6642-137">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |<span data-ttu-id="a6642-138">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="a6642-138">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |<span data-ttu-id="a6642-139">안쪽 여백</span><span class="sxs-lookup"><span data-stu-id="a6642-139">Padding</span></span>|`0, 7, 0, 0`|  
    |<span data-ttu-id="a6642-140">RenderMode</span><span class="sxs-lookup"><span data-stu-id="a6642-140">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3. <span data-ttu-id="a6642-141">Windows Forms 디자이너를 클릭 합니다 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 **추가** 단추를 추가 <xref:System.Windows.Forms.ToolStripButton> 에 `stackStrip` 컨트롤.</span><span class="sxs-lookup"><span data-stu-id="a6642-141">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>  
  
4. <span data-ttu-id="a6642-142">에 **속성** 창에서 <xref:System.Windows.Forms.ToolStripButton> 다음 표에 따라 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-142">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="a6642-143">속성</span><span class="sxs-lookup"><span data-stu-id="a6642-143">Property</span></span>|<span data-ttu-id="a6642-144">값</span><span class="sxs-lookup"><span data-stu-id="a6642-144">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="a6642-145">이름</span><span class="sxs-lookup"><span data-stu-id="a6642-145">Name</span></span>|`mailStackButton`|  
    |<span data-ttu-id="a6642-146">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="a6642-146">CheckOnClick</span></span>|<span data-ttu-id="a6642-147">true</span><span class="sxs-lookup"><span data-stu-id="a6642-147">true</span></span>|  
    |<span data-ttu-id="a6642-148">CheckState</span><span class="sxs-lookup"><span data-stu-id="a6642-148">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|  
    |<span data-ttu-id="a6642-149">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="a6642-149">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |<span data-ttu-id="a6642-150">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="a6642-150">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |<span data-ttu-id="a6642-151">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="a6642-151">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |<span data-ttu-id="a6642-152">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="a6642-152">ImageTransparentColor</span></span>|`238, 238, 238`|  
    |<span data-ttu-id="a6642-153">여백</span><span class="sxs-lookup"><span data-stu-id="a6642-153">Margin</span></span>|`0, 0, 0, 0`|  
    |<span data-ttu-id="a6642-154">안쪽 여백</span><span class="sxs-lookup"><span data-stu-id="a6642-154">Padding</span></span>|`3, 3, 3, 3`|  
    |<span data-ttu-id="a6642-155">텍스트</span><span class="sxs-lookup"><span data-stu-id="a6642-155">Text</span></span>|**<span data-ttu-id="a6642-156">메일</span><span class="sxs-lookup"><span data-stu-id="a6642-156">Mail</span></span>**|  
    |<span data-ttu-id="a6642-157">TextAlign</span><span class="sxs-lookup"><span data-stu-id="a6642-157">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5. <span data-ttu-id="a6642-158">세 개 이상에 대 한 7 단계를 반복 <xref:System.Windows.Forms.ToolStripButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-158">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
     <span data-ttu-id="a6642-159">컨트롤 이름을 `calendarStackButton`하십시오 `contactsStackButton`, 및 `tasksStackButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-159">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="a6642-160">값을 설정 합니다 <xref:System.Windows.Forms.Control.Text%2A> 속성을 **달력**, **연락처**, 및 **작업**, 각각.</span><span class="sxs-lookup"><span data-stu-id="a6642-160">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>  
  
## <a name="handling-events"></a><span data-ttu-id="a6642-161">이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="a6642-161">Handling Events</span></span>  
 <span data-ttu-id="a6642-162">두 이벤트를 확인 해야 합니다 `StackView` 컨트롤이 올바르게 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-162">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="a6642-163">처리는 <xref:System.Windows.Forms.UserControl.Load> 컨트롤을 올바르게 배치 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-163">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="a6642-164">처리를 <xref:System.Windows.Forms.ToolStripItem.Click> 각각에 대 한 이벤트 <xref:System.Windows.Forms.ToolStripButton> 제공 하는 `StackView` 비슷합니다 상태 동작을 제어를 <xref:System.Windows.Forms.RadioButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-164">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>  
  
#### <a name="to-handle-events"></a><span data-ttu-id="a6642-165">이벤트를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="a6642-165">To handle events</span></span>  
  
1. <span data-ttu-id="a6642-166">Windows Forms 디자이너에서 선택 된 `StackView` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-166">In the Windows Forms Designer, select the `StackView` control.</span></span>  
  
2. <span data-ttu-id="a6642-167">**속성** 창에서 **이벤트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-167">In the **Properties** window, click **Events**.</span></span>  
  
3. <span data-ttu-id="a6642-168">Load 이벤트 생성에 두 번 클릭 하 여 `StackView_Load` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-168">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>  
  
4. <span data-ttu-id="a6642-169">`StackView_Load` 이벤트 처리기에서 다음 코드를 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-169">In the `StackView_Load` event handler, copy and paste the following code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5. <span data-ttu-id="a6642-170">Windows Forms 디자이너에서 선택 된 `mailStackButton` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-170">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>  
  
6. <span data-ttu-id="a6642-171">**속성** 창에서 **이벤트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-171">In the **Properties** window, click **Events**.</span></span>  
  
7. <span data-ttu-id="a6642-172">클릭 이벤트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-172">Double-click the Click event.</span></span>  
  
     <span data-ttu-id="a6642-173">Windows Forms 디자이너에서 생성 된 `mailStackButton_Click` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-173">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>  
  
8. <span data-ttu-id="a6642-174">이름 바꾸기는 `mailStackButton_Click` 이벤트 처리기를 `stackButton_Click`입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-174">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>  
  
     <span data-ttu-id="a6642-175">자세한 내용은 [이름 바꾸기 리팩터링 코드 기호](/visualstudio/ide/reference/rename)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-175">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>  
  
9. <span data-ttu-id="a6642-176">다음 코드를 삽입 합니다 `stackButton_Click` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-176">Insert the following code into the `stackButton_Click` event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. <span data-ttu-id="a6642-177">Windows Forms 디자이너에서 선택 된 `calendarStackButton` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-177">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>  
  
11. <span data-ttu-id="a6642-178">에 **속성** 창에서 클릭 이벤트로는 `stackButton_Click` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-178">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>  
  
12. <span data-ttu-id="a6642-179">10 및 11 for 단계를 반복 합니다 `contactsStackButton` 고 `tasksStackButton` 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-179">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>  
  
## <a name="defining-icons"></a><span data-ttu-id="a6642-180">정의 아이콘</span><span class="sxs-lookup"><span data-stu-id="a6642-180">Defining Icons</span></span>  
 <span data-ttu-id="a6642-181">각 `StackView` 단추에 연결 된 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-181">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="a6642-182">편의 위해 각 아이콘으로 표시 됩니다 Base64로 인코딩된 문자열로 전에 deserialize 되는 <xref:System.Drawing.Bitmap> 에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-182">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="a6642-183">프로덕션 환경에서 리소스로 비트맵 데이터를 저장 하 고 Windows Forms 디자이너에 아이콘이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-183">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="a6642-184">자세한 내용은 [방법: Windows Forms에 배경 이미지 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-184">For more information, see [How to: Add Background Images to Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>  
  
#### <a name="to-define-icons"></a><span data-ttu-id="a6642-185">아이콘을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="a6642-185">To define icons</span></span>  
  
1. <span data-ttu-id="a6642-186">코드 편집기에서 다음 코드를 삽입 합니다 `StackView` 클래스 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-186">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="a6642-187">이 코드에 대 한 비트맵을 초기화 합니다 <xref:System.Windows.Forms.ToolStripButton> 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-187">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2. <span data-ttu-id="a6642-188">호출을 추가 합니다 `InitializeImages` 의 메서드는 `StackView` 클래스 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-188">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a><span data-ttu-id="a6642-189">사용자 지정 렌더러 구현</span><span class="sxs-lookup"><span data-stu-id="a6642-189">Implementing a Custom Renderer</span></span>  
 <span data-ttu-id="a6642-190">대부분의 요소를 사용자 지정할 수 있습니다 합니다 `StackView` 컨트롤에서 파생 되는 클래스를 구현 합니다 <xref:System.Windows.Forms.ToolStripRenderer> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-190">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="a6642-191">이 절차에서는 구현를 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 그립을 사용자 지정 및 그라데이션 배경을 그리는 클래스는 <xref:System.Windows.Forms.ToolStripButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-191">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
#### <a name="to-implement-a-custom-renderer"></a><span data-ttu-id="a6642-192">사용자 지정 렌더러를 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="a6642-192">To implement a custom renderer</span></span>  
  
1. <span data-ttu-id="a6642-193">다음 코드를 삽입 합니다 `StackView` 정의 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-193">Insert the following code into the `StackView` control definition.</span></span>  
  
     <span data-ttu-id="a6642-194">정의 대 한 합니다 `StackRenderer` 클래스를 재정의 하는 <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, 및 <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> 사용자 지정 모양을 생성 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="a6642-194">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2. <span data-ttu-id="a6642-195">에 `StackView` 컨트롤의 생성자의 새 인스턴스를 만듭니다를 `StackRenderer` 클래스 및이 인스턴스를 할당 합니다 `stackStrip` 컨트롤의 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="a6642-195">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a><span data-ttu-id="a6642-196">StackView 컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="a6642-196">Testing the StackView Control</span></span>  
 <span data-ttu-id="a6642-197">합니다 `StackView` 컨트롤에서 파생 되는 <xref:System.Windows.Forms.UserControl> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-197">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="a6642-198">따라서 컨트롤을 테스트할 수 있습니다 합니다 **UserControl 테스트 컨테이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-198">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="a6642-199">자세한 내용은 [방법: UserControl의 런타임 동작 테스트](how-to-test-the-run-time-behavior-of-a-usercontrol.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-199">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-the-stackview-control"></a><span data-ttu-id="a6642-200">StackView 컨트롤을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="a6642-200">To test the StackView control</span></span>  
  
1. <span data-ttu-id="a6642-201">F5 키를 눌러 프로젝트를 빌드하고 시작 합니다 **UserControl 테스트 컨테이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-201">Press F5 to build the project and start the **UserControl Test Container**.</span></span>  
  
2. <span data-ttu-id="a6642-202">단추 위로 포인터를 `StackView` 컨트롤을 선택한 상태로의 모양을 확인 하려면 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-202">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a6642-203">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a6642-203">Next Steps</span></span>  
 <span data-ttu-id="a6642-204">이 연습에서는 전문적인 모양의 Office XP 컨트롤을 사용 하 여 재사용 가능한 사용자 지정 클라이언트 컨트롤을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-204">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="a6642-205">사용할 수는 <xref:System.Windows.Forms.ToolStrip> 다양 한 용도로 다른 컨트롤의 패밀리:</span><span class="sxs-lookup"><span data-stu-id="a6642-205">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="a6642-206">사용 하 여 컨트롤에 대 한 바로 가기 메뉴를 만들 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-206">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="a6642-207">자세한 내용은 [ContextMenu 구성 요소 개요](contextmenu-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-207">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="a6642-208">자동으로 채워진된 표준 메뉴를 사용 하 여 폼을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-208">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="a6642-209">자세한 내용은 [연습: 폼에 표준 메뉴 항목 제공](walkthrough-providing-standard-menu-items-to-a-form.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-209">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="a6642-210">도킹 된 여러 문서 MDI (인터페이스) 양식을 만듭니다 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-210">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="a6642-211">자세한 내용은 [방법: 메뉴 병합 및 ToolStrip 컨트롤을 사용 하 여 MDI 폼 만들기](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6642-211">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6642-212">참고자료</span><span class="sxs-lookup"><span data-stu-id="a6642-212">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="a6642-213">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a6642-213">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="a6642-214">방법: 양식에 표준 메뉴 항목 제공</span><span class="sxs-lookup"><span data-stu-id="a6642-214">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
