---
title: '방법: 작업 만들기'
description: 이 문서에서는 워크플로 파운데이션에서 두 활동을 만드는 방법을 보여 줍니다. 하나는 코드를 사용 하 여 논리를 구현 하 고 다른 활동을 사용 하 여 정의 하는 것입니다.
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: c7610d8612eb944afa9c23e1bf2abceeb3a6d38b
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190769"
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="bc467-103">방법: 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="bc467-103">How to: Create an Activity</span></span>

<span data-ttu-id="bc467-104">활동은 [!INCLUDE[wf1](../../../includes/wf1-md.md)]에서 동작의 핵심 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-104">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="bc467-105">활동의 실행 논리는 관리 코드에서 구현하거나 다른 활동을 사용하여 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-105">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="bc467-106">이 항목에서는 두 개의 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-106">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="bc467-107">첫 번째 활동은 코드를 사용하여 실행 논리를 구현하는 간단한 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-107">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="bc467-108">두 번째 활동의 구현은 다른 활동을 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-108">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="bc467-109">이러한 활동은 자습서의 다음 단계에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-109">These activities are used in following steps in the tutorial.</span></span>

## <a name="create-the-activity-library-project"></a><span data-ttu-id="bc467-110">활동 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="bc467-110">Create the activity library project</span></span>

1. <span data-ttu-id="bc467-111">Visual Studio를 열고   >  **파일** 메뉴에서 새 **프로젝트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-111">Open Visual Studio and choose **New** > **Project** from the **File** menu.</span></span>

2. <span data-ttu-id="bc467-112">**새 프로젝트** 대화 상자의 **설치 됨** 범주 아래에서 **Visual c #**  >  **워크플로** (또는 **Visual Basic**  >  **워크플로**)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-112">In the **New Project** dialog, under the **Installed** category, select **Visual C#** > **Workflow** (or **Visual Basic** > **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="bc467-113">**워크플로** 템플릿 범주가 표시 되지 않으면 Visual Studio의 **Windows Workflow Foundation** 구성 요소를 설치 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-113">If you don't see the **Workflow** template category, you may need to install the **Windows Workflow Foundation** component of Visual Studio.</span></span> <span data-ttu-id="bc467-114">**새 프로젝트** 대화 상자의 왼쪽에 있는 **Visual Studio 설치 관리자 열기** 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-114">Choose the **Open Visual Studio Installer** link on the left-hand side of the **New Project** dialog.</span></span> <span data-ttu-id="bc467-115">Visual Studio 설치 관리자에서 **개별 구성 요소** 탭을 선택 합니다. 그런 다음 **개발 활동** 범주 아래에서 **Windows Workflow Foundation** 구성 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-115">In Visual Studio Installer, select the **Individual components** tab. Then, under the **Development activities** category, select the **Windows Workflow Foundation** component.</span></span> <span data-ttu-id="bc467-116">**수정** 을 선택 하 여 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-116">Choose **Modify** to install the component.</span></span>

3. <span data-ttu-id="bc467-117">**활동 라이브러리** 프로젝트 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-117">Select the **Activity Library** project template.</span></span> <span data-ttu-id="bc467-118">**이름** 상자에 `NumberGuessWorkflowActivities`를 입력한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-118">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>

4. <span data-ttu-id="bc467-119">**솔루션 탐색기** 에서 **Activity1.xaml** 을 마우스 오른쪽 단추로 클릭하고 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-119">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="bc467-120">**확인** 을 클릭하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-120">Click **OK** to confirm.</span></span>

## <a name="create-the-readint-activity"></a><span data-ttu-id="bc467-121">ReadInt 활동 만들기</span><span class="sxs-lookup"><span data-stu-id="bc467-121">Create the ReadInt activity</span></span>

1. <span data-ttu-id="bc467-122">**프로젝트** 메뉴에서 **새 항목 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-122">Choose **Add New Item** from the **Project** menu.</span></span>

2. <span data-ttu-id="bc467-123">설치 된   >  **공통 항목** 노드에서 **워크플로** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-123">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="bc467-124">**워크플로** 목록에서 **코드 작업** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-124">Select **Code Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="bc467-125">**이름** 상자에 `ReadInt`를 입력한 다음 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-125">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>

4. <span data-ttu-id="bc467-126">기존 `ReadInt` 정의를 다음 정의로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-126">Replace the existing `ReadInt` definition with the following definition.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > <span data-ttu-id="bc467-127">`ReadInt` 활동은 코드 활동 템플릿의 기본값인 <xref:System.Activities.NativeActivity%601> 대신 <xref:System.Activities.CodeActivity>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-127">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="bc467-128">활동이 <xref:System.Activities.CodeActivity%601> 인수를 통해 노출되는 단일 결과를 제공하는 경우 <xref:System.Activities.Activity%601.Result%2A>를 사용할 수 있지만 <xref:System.Activities.CodeActivity%601>는 책갈피 사용을 지원하지 않으므로 <xref:System.Activities.NativeActivity%601>가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-128"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>

## <a name="create-the-prompt-activity"></a><span data-ttu-id="bc467-129">프롬프트 활동 만들기</span><span class="sxs-lookup"><span data-stu-id="bc467-129">Create the Prompt activity</span></span>

1. <span data-ttu-id="bc467-130">**Ctrl** + **Shift** + **B** 를 눌러 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-130">Press **Ctrl**+**Shift**+**B** to build the project.</span></span> <span data-ttu-id="bc467-131">프로젝트를 빌드하면 이 프로젝트의 `ReadInt` 활동을 사용하여 이 단계의 사용자 지정 활동을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-131">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>

2. <span data-ttu-id="bc467-132">**프로젝트** 메뉴에서 **새 항목 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-132">Choose **Add New Item** from the **Project** menu.</span></span>

3. <span data-ttu-id="bc467-133">설치 된   >  **공통 항목** 노드에서 **워크플로** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-133">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="bc467-134">**워크플로** 목록에서 **작업** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-134">Select **Activity** from the **Workflow** list.</span></span>

4. <span data-ttu-id="bc467-135">**이름** 상자에 `Prompt`를 입력한 다음 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-135">Type `Prompt` into the **Name** box and then click **Add**.</span></span>

5. <span data-ttu-id="bc467-136">**솔루션 탐색기** 의 xaml을 두 번 클릭 하 여 디자이너에 표시 합니다 (아직 표시 되지 않은 경우) **.**</span><span class="sxs-lookup"><span data-stu-id="bc467-136">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>

6. <span data-ttu-id="bc467-137">활동 디자이너의 왼쪽 아래에 있는 **인수** 를 클릭하여 **인수** 창을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-137">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>

7. <span data-ttu-id="bc467-138">**인수 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-138">Click **Create Argument**.</span></span>

8. <span data-ttu-id="bc467-139">`BookmarkName` **이름** 상자에를 입력 하 고 **방향** 드롭다운 목록 **에서 시작을** 선택한 다음 **인수 형식** 드롭다운 목록에서 **문자열** 을 선택 하 고 **enter** 키를 눌러 인수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-139">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

9. <span data-ttu-id="bc467-140">**인수 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-140">Click **Create Argument**.</span></span>

10. <span data-ttu-id="bc467-141">`Result`새로 추가 된 인수 아래에 있는 **이름** 상자에를 입력 `BookmarkName` 하 고 **방향** 드롭다운 목록에서 **바깥쪽** 을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32** 를 선택 하 고 **enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-141">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press **Enter**.</span></span>

11. <span data-ttu-id="bc467-142">**인수 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-142">Click **Create Argument**.</span></span>

12. <span data-ttu-id="bc467-143">`Text` **이름** 상자에를 입력 하 고 **방향** 드롭다운 목록 **에서 시작을** 선택한 다음 **인수 형식** 드롭다운 목록에서 **문자열** 을 선택 하 고 **enter** 키를 눌러 인수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-143">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

     <span data-ttu-id="bc467-144">이 세 가지 인수는 다음 단계에서 <xref:System.Activities.Statements.WriteLine> 활동에 추가되는 `ReadInt` 및 `Prompt` 활동의 해당 인수에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-144">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>

13. <span data-ttu-id="bc467-145">활동 디자이너의 왼쪽 아래에 있는 **인수** 를 클릭하여 **인수** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-145">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

14. <span data-ttu-id="bc467-146">**도구 상자** 의 **제어 흐름** 섹션에서 **Sequence** 활동을 끌어 **Prompt** 활동 디자이너의 여기에 **작업 놓기** 레이블에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-146">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>

    > [!TIP]
    > <span data-ttu-id="bc467-147">**도구 상자** 창이 표시되지 않으면 **보기** 메뉴에서 **도구 상자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-147">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

15. <span data-ttu-id="bc467-148">**도구 상자** 의 **기본 형식** 섹션에서 **WriteLine** 활동을 끌어 **Sequence** 활동의 여기에 **작업 놓기** 레이블에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-148">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>

16. <span data-ttu-id="bc467-149">    `Text` **속성** 창에서 **c # 식 입력** 또는 **VB 식 입력** 상자에 입력 하 여 WriteLine 활동의 text 인수를 Prompt 활동의 text 인수에 바인딩한 다음 **tab** 키를 두 번 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-149">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the **Tab** key two times.</span></span> <span data-ttu-id="bc467-150">그러면 IntelliSense 목록 멤버 창이 사라지고 속성에서 선택 항목을 이동하여 속성 값이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-150">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="bc467-151">이 속성은 `Text` 활동 자체에서 **c # 식 입력** 또는 **VB 식 입력** 상자를 입력 하 여 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-151">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>

    > [!TIP]
    > <span data-ttu-id="bc467-152">**속성 창이** 표시 되지 않으면 **보기** 메뉴에서 **속성 창** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-152">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

17. <span data-ttu-id="bc467-153">**도구 상자** 의 **NumberGuessWorkflowActivities** 섹션에서 **Readint** 활동을 끌어 **Sequence** 활동에 놓으면 **WriteLine** 활동을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-153">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>

18. <span data-ttu-id="bc467-154">속성 창에서 BookmarkName 인수 오른쪽의 VB 식 입력 상자에를 입력 하 여 **Readint** 활동의 **BookmarkName** 인수를 **Prompt** 활동의 **BookmarkName** 인수에 바인딩한 `BookmarkName` 다음  **tab** 키를 두 번 눌러 IntelliSense 목록 멤버 창을 닫고 속성을 저장 합니다. </span><span class="sxs-lookup"><span data-stu-id="bc467-154">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the **Tab** key two times to close the IntelliSense list members window and save the property.</span></span>

19. <span data-ttu-id="bc467-155">   속성 창에서 Result 인수 오른쪽의 VB 식 입력 상자에를 입력 하 여 **Readint** 활동의 result 인수를 Prompt 활동의 result 인수에 바인딩한 `Result` 다음  **tab** 키를 두 번 누릅니다. </span><span class="sxs-lookup"><span data-stu-id="bc467-155">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the **Tab** key two times.</span></span>

20. <span data-ttu-id="bc467-156">**Ctrl** + **Shift** + **B** 를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="bc467-156">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc467-157">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bc467-157">Next steps</span></span>

<span data-ttu-id="bc467-158">이러한 활동을 사용 하 여 워크플로를 만드는 방법에 대 한 지침은 자습서의 다음 단계인 [방법: 워크플로 만들기](how-to-create-a-workflow.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc467-158">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bc467-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc467-159">See also</span></span>

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [<span data-ttu-id="bc467-160">사용자 지정 활동 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="bc467-160">Designing and Implementing Custom Activities</span></span>](designing-and-implementing-custom-activities.md)
- [<span data-ttu-id="bc467-161">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="bc467-161">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="bc467-162">방법: 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="bc467-162">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="bc467-163">사용자 지정 활동 디자이너에서 ExpressionTextBox 사용</span><span class="sxs-lookup"><span data-stu-id="bc467-163">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
