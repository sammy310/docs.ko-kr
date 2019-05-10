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
ms.openlocfilehash: 226e805d0240236899ee0cc290f1060a3b0aa391
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211766"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="a1c36-102">연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="a1c36-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>

<span data-ttu-id="a1c36-103">응용 프로그램을 제공할 수 있습니다 <xref:System.Windows.Forms.ToolStrip> 에서 파생 된 고유한 클래스를 작성 하 여 전문적인 모양 및 동작을 제어 합니다 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>

<span data-ttu-id="a1c36-104">이 연습에 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Forms.ToolStrip> 와 비슷한 복합 컨트롤을 만드는 컨트롤을 **탐색 창** Microsoft® Outlook®에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="a1c36-105">다음 태스크를이 연습에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-105">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="a1c36-106">Windows 컨트롤 라이브러리 프로젝트를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-106">Creating a Windows Control Library project.</span></span>

- <span data-ttu-id="a1c36-107">StackView 컨트롤을 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-107">Designing the StackView Control.</span></span>

- <span data-ttu-id="a1c36-108">사용자 지정 렌더러를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-108">Implementing a Custom Renderer.</span></span>

<span data-ttu-id="a1c36-109">작업을 완료 하는 경우에 전문적인 모양의 Microsoft Office® XP 컨트롤을 사용 하 여 재사용 가능한 사용자 지정 클라이언트 컨트롤을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>

<span data-ttu-id="a1c36-110">이 항목의 코드를 단일 목록으로 복사하려면 [방법: 전문적인 스타일의 ToolStrip 컨트롤 만들기](how-to-create-a-professionally-styled-toolstrip-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1c36-111">전제 조건</span><span class="sxs-lookup"><span data-stu-id="a1c36-111">Prerequisites</span></span>

<span data-ttu-id="a1c36-112">이 연습을 완료 하려면 Visual Studio를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-112">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="a1c36-113">컨트롤 라이브러리 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a1c36-113">Create the control library project</span></span>

1. <span data-ttu-id="a1c36-114">Visual Studio에서 라는 새 Windows 컨트롤 라이브러리 프로젝트를 만들 `StackViewLibrary`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-114">In Visual Studio, create a new Windows Control Library project named `StackViewLibrary`.</span></span>

2. <span data-ttu-id="a1c36-115">**솔루션 탐색기**, 선택한 언어에 따라 "UserControl1.cs" 또는 "UserControl1.vb" 라는 소스 파일을 삭제 하 여 프로젝트의 기본 컨트롤을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-115">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>

     <span data-ttu-id="a1c36-116">자세한 내용은 [방법: 제거, 삭제 및 항목을 제외](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-116">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

3. <span data-ttu-id="a1c36-117">새 <xref:System.Windows.Forms.UserControl> 항목을 **StackViewLibrary** 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-117">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="a1c36-118">새 소스 파일의 기본 이름을 지정 `StackView`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-118">Give the new source file a base name of `StackView`.</span></span>

## <a name="design-the-stackview-control"></a><span data-ttu-id="a1c36-119">StackView 컨트롤 디자인</span><span class="sxs-lookup"><span data-stu-id="a1c36-119">Design the StackView control</span></span>

<span data-ttu-id="a1c36-120">합니다 `StackView` 자식이 하나를 사용 하 여 복합 컨트롤 <xref:System.Windows.Forms.ToolStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-120">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="a1c36-121">복합 컨트롤에 대 한 자세한 내용은 참조 하세요. [종류의 사용자 지정 컨트롤](varieties-of-custom-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-121">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

1. <span data-ttu-id="a1c36-122">**도구 상자**를 끌어를 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 디자인 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-122">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>

2. <span data-ttu-id="a1c36-123">에 **속성** 창에서 <xref:System.Windows.Forms.ToolStrip> 다음 표에 따라 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-123">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>

    |<span data-ttu-id="a1c36-124">속성</span><span class="sxs-lookup"><span data-stu-id="a1c36-124">Property</span></span>|<span data-ttu-id="a1c36-125">값</span><span class="sxs-lookup"><span data-stu-id="a1c36-125">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="a1c36-126">이름</span><span class="sxs-lookup"><span data-stu-id="a1c36-126">Name</span></span>|`stackStrip`|
    |<span data-ttu-id="a1c36-127">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="a1c36-127">CanOverflow</span></span>|`false`|
    |<span data-ttu-id="a1c36-128">도킹</span><span class="sxs-lookup"><span data-stu-id="a1c36-128">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|
    |<span data-ttu-id="a1c36-129">글꼴</span><span class="sxs-lookup"><span data-stu-id="a1c36-129">Font</span></span>|`Tahoma, 10pt, style=Bold`|
    |<span data-ttu-id="a1c36-130">GripStyle</span><span class="sxs-lookup"><span data-stu-id="a1c36-130">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|
    |<span data-ttu-id="a1c36-131">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="a1c36-131">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|
    |<span data-ttu-id="a1c36-132">안쪽 여백</span><span class="sxs-lookup"><span data-stu-id="a1c36-132">Padding</span></span>|`0, 7, 0, 0`|
    |<span data-ttu-id="a1c36-133">RenderMode</span><span class="sxs-lookup"><span data-stu-id="a1c36-133">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|

3. <span data-ttu-id="a1c36-134">Windows Forms 디자이너를 클릭 합니다 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 **추가** 단추를 추가 <xref:System.Windows.Forms.ToolStripButton> 에 `stackStrip` 컨트롤.</span><span class="sxs-lookup"><span data-stu-id="a1c36-134">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>

4. <span data-ttu-id="a1c36-135">에 **속성** 창에서 <xref:System.Windows.Forms.ToolStripButton> 다음 표에 따라 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-135">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>

    |<span data-ttu-id="a1c36-136">속성</span><span class="sxs-lookup"><span data-stu-id="a1c36-136">Property</span></span>|<span data-ttu-id="a1c36-137">값</span><span class="sxs-lookup"><span data-stu-id="a1c36-137">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="a1c36-138">이름</span><span class="sxs-lookup"><span data-stu-id="a1c36-138">Name</span></span>|`mailStackButton`|
    |<span data-ttu-id="a1c36-139">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="a1c36-139">CheckOnClick</span></span>|<span data-ttu-id="a1c36-140">true</span><span class="sxs-lookup"><span data-stu-id="a1c36-140">true</span></span>|
    |<span data-ttu-id="a1c36-141">CheckState</span><span class="sxs-lookup"><span data-stu-id="a1c36-141">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|
    |<span data-ttu-id="a1c36-142">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="a1c36-142">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|
    |<span data-ttu-id="a1c36-143">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="a1c36-143">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|
    |<span data-ttu-id="a1c36-144">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="a1c36-144">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|
    |<span data-ttu-id="a1c36-145">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="a1c36-145">ImageTransparentColor</span></span>|`238, 238, 238`|
    |<span data-ttu-id="a1c36-146">여백</span><span class="sxs-lookup"><span data-stu-id="a1c36-146">Margin</span></span>|`0, 0, 0, 0`|
    |<span data-ttu-id="a1c36-147">안쪽 여백</span><span class="sxs-lookup"><span data-stu-id="a1c36-147">Padding</span></span>|`3, 3, 3, 3`|
    |<span data-ttu-id="a1c36-148">텍스트</span><span class="sxs-lookup"><span data-stu-id="a1c36-148">Text</span></span>|<span data-ttu-id="a1c36-149">**Mail**</span><span class="sxs-lookup"><span data-stu-id="a1c36-149">**Mail**</span></span>|
    |<span data-ttu-id="a1c36-150">TextAlign</span><span class="sxs-lookup"><span data-stu-id="a1c36-150">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|

5. <span data-ttu-id="a1c36-151">세 개 이상에 대 한 7 단계를 반복 <xref:System.Windows.Forms.ToolStripButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-151">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

     <span data-ttu-id="a1c36-152">컨트롤 이름을 `calendarStackButton`하십시오 `contactsStackButton`, 및 `tasksStackButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-152">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="a1c36-153">값을 설정 합니다 <xref:System.Windows.Forms.Control.Text%2A> 속성을 **달력**, **연락처**, 및 **작업**, 각각.</span><span class="sxs-lookup"><span data-stu-id="a1c36-153">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>

## <a name="handle-events"></a><span data-ttu-id="a1c36-154">이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="a1c36-154">Handle events</span></span>

<span data-ttu-id="a1c36-155">두 이벤트를 확인 해야 합니다 `StackView` 컨트롤이 올바르게 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-155">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="a1c36-156">처리는 <xref:System.Windows.Forms.UserControl.Load> 컨트롤을 올바르게 배치 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-156">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="a1c36-157">처리를 <xref:System.Windows.Forms.ToolStripItem.Click> 각각에 대 한 이벤트 <xref:System.Windows.Forms.ToolStripButton> 제공 하는 `StackView` 비슷합니다 상태 동작을 제어를 <xref:System.Windows.Forms.RadioButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-157">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>

1. <span data-ttu-id="a1c36-158">Windows Forms 디자이너에서 선택 된 `StackView` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-158">In the Windows Forms Designer, select the `StackView` control.</span></span>

2. <span data-ttu-id="a1c36-159">**속성** 창에서 **이벤트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-159">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="a1c36-160">Load 이벤트 생성에 두 번 클릭 하 여 `StackView_Load` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-160">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>

4. <span data-ttu-id="a1c36-161">`StackView_Load` 이벤트 처리기에서 다음 코드를 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-161">In the `StackView_Load` event handler, copy and paste the following code.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]

5. <span data-ttu-id="a1c36-162">Windows Forms 디자이너에서 선택 된 `mailStackButton` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-162">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>

6. <span data-ttu-id="a1c36-163">**속성** 창에서 **이벤트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-163">In the **Properties** window, click **Events**.</span></span>

7. <span data-ttu-id="a1c36-164">클릭 이벤트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-164">Double-click the Click event.</span></span>

     <span data-ttu-id="a1c36-165">Windows Forms 디자이너에서 생성 된 `mailStackButton_Click` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-165">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>

8. <span data-ttu-id="a1c36-166">이름 바꾸기는 `mailStackButton_Click` 이벤트 처리기를 `stackButton_Click`입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-166">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>

     <span data-ttu-id="a1c36-167">자세한 내용은 [이름 바꾸기 리팩터링 코드 기호](/visualstudio/ide/reference/rename)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-167">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

9. <span data-ttu-id="a1c36-168">다음 코드를 삽입 합니다 `stackButton_Click` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-168">Insert the following code into the `stackButton_Click` event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]

10. <span data-ttu-id="a1c36-169">Windows Forms 디자이너에서 선택 된 `calendarStackButton` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-169">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>

11. <span data-ttu-id="a1c36-170">에 **속성** 창에서 클릭 이벤트로는 `stackButton_Click` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-170">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>

12. <span data-ttu-id="a1c36-171">10 및 11 for 단계를 반복 합니다 `contactsStackButton` 고 `tasksStackButton` 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-171">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>

## <a name="define-icons"></a><span data-ttu-id="a1c36-172">아이콘 정의</span><span class="sxs-lookup"><span data-stu-id="a1c36-172">Define icons</span></span>

<span data-ttu-id="a1c36-173">각 `StackView` 단추에 연결 된 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-173">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="a1c36-174">편의 위해 각 아이콘으로 표시 됩니다 Base64로 인코딩된 문자열로 전에 deserialize 되는 <xref:System.Drawing.Bitmap> 에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-174">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="a1c36-175">프로덕션 환경에서 리소스로 비트맵 데이터를 저장 하 고 Windows Forms 디자이너에 아이콘이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-175">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="a1c36-176">자세한 내용은 [방법: Windows Forms에 배경 이미지 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-176">For more information, see [How to: Add Background Images to Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>

1. <span data-ttu-id="a1c36-177">코드 편집기에서 다음 코드를 삽입 합니다 `StackView` 클래스 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-177">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="a1c36-178">이 코드에 대 한 비트맵을 초기화 합니다 <xref:System.Windows.Forms.ToolStripButton> 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-178">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]

2. <span data-ttu-id="a1c36-179">호출을 추가 합니다 `InitializeImages` 의 메서드는 `StackView` 클래스 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-179">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="implement-a-custom-renderer"></a><span data-ttu-id="a1c36-180">사용자 지정 렌더러를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-180">Implement a custom renderer</span></span>

<span data-ttu-id="a1c36-181">대부분의 요소를 사용자 지정할 수 있습니다 합니다 `StackView` 컨트롤에서 파생 되는 클래스를 구현 합니다 <xref:System.Windows.Forms.ToolStripRenderer> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-181">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="a1c36-182">이 절차에서는 구현를 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 그립을 사용자 지정 및 그라데이션 배경을 그리는 클래스는 <xref:System.Windows.Forms.ToolStripButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-182">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

1. <span data-ttu-id="a1c36-183">다음 코드를 삽입 합니다 `StackView` 정의 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-183">Insert the following code into the `StackView` control definition.</span></span>

     <span data-ttu-id="a1c36-184">정의 대 한 합니다 `StackRenderer` 클래스를 재정의 하는 <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, 및 <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> 사용자 지정 모양을 생성 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="a1c36-184">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]

2. <span data-ttu-id="a1c36-185">에 `StackView` 컨트롤의 생성자의 새 인스턴스를 만듭니다를 `StackRenderer` 클래스 및이 인스턴스를 할당 합니다 `stackStrip` 컨트롤의 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="a1c36-185">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="test-the-stackview-control"></a><span data-ttu-id="a1c36-186">StackView 컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="a1c36-186">Test the StackView control</span></span>

<span data-ttu-id="a1c36-187">합니다 `StackView` 컨트롤에서 파생 되는 <xref:System.Windows.Forms.UserControl> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-187">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="a1c36-188">따라서 컨트롤을 테스트할 수 있습니다 합니다 **UserControl 테스트 컨테이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-188">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="a1c36-189">자세한 내용은 [방법: UserControl의 런타임 동작 테스트](how-to-test-the-run-time-behavior-of-a-usercontrol.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-189">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

1. <span data-ttu-id="a1c36-190">키를 눌러 **F5** 프로젝트를 빌드하고 시작 합니다 **UserControl 테스트 컨테이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-190">Press **F5** to build the project and start the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="a1c36-191">단추 위로 포인터를 `StackView` 컨트롤을 선택한 상태로의 모양을 확인 하려면 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-191">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a1c36-192">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a1c36-192">Next steps</span></span>

<span data-ttu-id="a1c36-193">이 연습에서는 전문적인 모양의 Office XP 컨트롤을 사용 하 여 재사용 가능한 사용자 지정 클라이언트 컨트롤을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-193">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="a1c36-194">사용할 수는 <xref:System.Windows.Forms.ToolStrip> 다양 한 용도로 다른 컨트롤의 패밀리:</span><span class="sxs-lookup"><span data-stu-id="a1c36-194">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="a1c36-195">사용 하 여 컨트롤에 대 한 바로 가기 메뉴를 만들 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-195">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="a1c36-196">자세한 내용은 [ContextMenu 구성 요소 개요](contextmenu-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-196">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="a1c36-197">자동으로 채워진된 표준 메뉴를 사용 하 여 폼을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-197">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="a1c36-198">자세한 내용은 [연습: 폼에 표준 메뉴 항목 제공](walkthrough-providing-standard-menu-items-to-a-form.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-198">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="a1c36-199">도킹 된 여러 문서 MDI (인터페이스) 양식을 만듭니다 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-199">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="a1c36-200">자세한 내용은 [방법: 메뉴 병합 및 ToolStrip 컨트롤을 사용 하 여 MDI 폼 만들기](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c36-200">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a1c36-201">참고자료</span><span class="sxs-lookup"><span data-stu-id="a1c36-201">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="a1c36-202">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a1c36-202">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="a1c36-203">방법: 폼에 표준 메뉴 항목 제공</span><span class="sxs-lookup"><span data-stu-id="a1c36-203">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
