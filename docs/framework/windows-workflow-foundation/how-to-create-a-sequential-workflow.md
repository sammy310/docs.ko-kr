---
title: '방법: 순차 워크플로 만들기'
description: 이 문서에서는 시퀀스 작업 및 사용자 지정 작업과 같은 기본 제공 활동을 모두 사용 하는 워크플로를 만듭니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: 0c47290d11770a094fb09bcb4dc34aee1e4371a9
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190522"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="6d876-103">방법: 순차 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="6d876-103">How to: Create a Sequential Workflow</span></span>

<span data-ttu-id="6d876-104">기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="6d876-105">이 항목에서는 활동과 같은 기본 제공 활동과 <xref:System.Activities.Statements.Sequence> 이전 [방법: 활동 만들기](how-to-create-an-activity.md) 항목의 사용자 지정 활동을 모두 사용 하는 워크플로를 만드는 과정을 단계별로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="6d876-106">이 워크플로는 숫자 추측 게임을 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-106">The workflow models a number guessing game.</span></span>

> [!NOTE]
> <span data-ttu-id="6d876-107">초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="6d876-108">이 항목을 완료 하려면 먼저 [방법: 작업 만들기](how-to-create-an-activity.md)를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>

## <a name="to-create-the-workflow"></a><span data-ttu-id="6d876-109">워크플로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="6d876-109">To create the workflow</span></span>

1. <span data-ttu-id="6d876-110">**솔루션 탐색기** 에서 **NumberGuessWorkflowActivities** 을 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 항목** 을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>

2. <span data-ttu-id="6d876-111">**설치 됨**, **공통 항목** 노드에서 **워크플로** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="6d876-112">**워크플로** 목록에서 **작업** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-112">Select **Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="6d876-113">`SequentialNumberGuessWorkflow` **이름** 상자에를 입력 하 고 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-113">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>

4. <span data-ttu-id="6d876-114">**도구 상자** 의 **제어 흐름** 섹션에서 **Sequence** 활동을 끌어 워크플로 디자인 화면의 **여기에 작업 놓기** 레이블에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-114">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>

## <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="6d876-115">워크플로 변수와 인수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="6d876-115">To create the workflow variables and arguments</span></span>

1. <span data-ttu-id="6d876-116">**솔루션 탐색기** 에서 **sequentialnumberguessworkflow.xaml** 를 두 번 클릭 하 여 디자이너에 워크플로를 표시 합니다 (아직 표시 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="6d876-116">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>

2. <span data-ttu-id="6d876-117">워크플로 디자이너 왼쪽 아래에 있는 **인수** 를 클릭 하 여 **인수** 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>

3. <span data-ttu-id="6d876-118">**인수 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-118">Click **Create Argument**.</span></span>

4. <span data-ttu-id="6d876-119">`MaxNumber` **이름** 상자에를 입력 하 고 **방향** 드롭다운 목록 **에서 시작을** 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32** 를 선택 하 고 enter 키를 눌러 인수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>

5. <span data-ttu-id="6d876-120">**인수 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-120">Click **Create Argument**.</span></span>

6. <span data-ttu-id="6d876-121">`Turns`새로 추가 된 인수 아래에 있는 **이름** 상자에를 입력 `MaxNumber` 하 고 **방향** 드롭다운 목록에서 **바깥쪽** 을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32** 를 선택 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>

7. <span data-ttu-id="6d876-122">활동 디자이너의 왼쪽 아래에 있는 **인수** 를 클릭하여 **인수** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

8. <span data-ttu-id="6d876-123">워크플로 디자이너 왼쪽 아래에 있는 **변수** 를 클릭 하 여 **변수** 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>

9. <span data-ttu-id="6d876-124">**변수 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-124">Click **Create Variable**.</span></span>

    > [!TIP]
    > <span data-ttu-id="6d876-125">**변수 만들기** 상자가 표시 되지 않으면 workflow designer 화면에서 **Sequence** 활동을 클릭 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-125">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>

10. <span data-ttu-id="6d876-126">`Guess` **이름** 상자에를 입력 하 고 **변수 형식** 드롭다운 목록에서 **Int32** 를 선택한 다음 enter 키를 눌러 변수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

11. <span data-ttu-id="6d876-127">**변수 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-127">Click **Create Variable**.</span></span>

12. <span data-ttu-id="6d876-128">`Target` **이름** 상자에를 입력 하 고 **변수 형식** 드롭다운 목록에서 **Int32** 를 선택한 다음 enter 키를 눌러 변수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

13. <span data-ttu-id="6d876-129">활동 디자이너의 왼쪽 아래에 있는 **변수** 를 클릭하여 **변수** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>

## <a name="to-add-the-workflow-activities"></a><span data-ttu-id="6d876-130">워크플로 활동을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="6d876-130">To add the workflow activities</span></span>

1. <span data-ttu-id="6d876-131">**도구 상자** 의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 **시퀀스** 활동에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="6d876-132">`Target`To 상자에 **를** 입력 하 고 **c # 식 입력** 또는 **VB 식 입력** 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-132">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

    ```vb
    New System.Random().Next(1, MaxNumber + 1)
    ```

    ```csharp
    new System.Random().Next(1, MaxNumber + 1)
    ```

    > [!TIP]
    > <span data-ttu-id="6d876-133">**도구 상자** 창이 표시되지 않으면 **보기** 메뉴에서 **도구 상자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-133">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

2. <span data-ttu-id="6d876-134">**도구 상자** 의 **제어 흐름** 섹션에서 **DoWhile** 활동을 끌어 워크플로에서 **Assign** 활동 아래에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-134">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>

3. <span data-ttu-id="6d876-135">**DoWhile** 활동의 **Condition** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-135">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

     <span data-ttu-id="6d876-136"><xref:System.Activities.Statements.DoWhile> 활동은 자식 활동을 실행한 다음 해당 <xref:System.Activities.Statements.DoWhile.Condition%2A>을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-136">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="6d876-137"><xref:System.Activities.Statements.DoWhile.Condition%2A>이 `True`로 확인되면 <xref:System.Activities.Statements.DoWhile>의 활동이 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-137">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="6d876-138">이 예제에서는 사용자의 추측 값을 확인하여 추측이 올바를 때까지 <xref:System.Activities.Statements.DoWhile>이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-138">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>

4. <span data-ttu-id="6d876-139">**도구 상자** 의 **NumberGuessWorkflowActivities** 섹션에서 **Prompt** 활동을 끌어 이전 단계의 **DoWhile** 활동에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-139">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>

5. <span data-ttu-id="6d876-140">**속성 창** 에서 `"EnterGuess"` **프롬프트** 활동의 **BookmarkName** 속성 값 상자에 따옴표를 포함 하 여을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-140">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="6d876-141">`Guess` **결과** 속성 값 상자에를 입력 하 고 **텍스트** 속성 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-141">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>

    ```vb
    "Please enter a number between 1 and " & MaxNumber
    ```

    ```csharp
    "Please enter a number between 1 and " + MaxNumber
    ```

    > [!TIP]
    > <span data-ttu-id="6d876-142">**속성 창이** 표시 되지 않으면 **보기** 메뉴에서 **속성 창** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-142">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

6. <span data-ttu-id="6d876-143">**도구 상자** 의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 **Prompt** 활동 뒤에 **DoWhile** 활동에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-143">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6d876-144">**Assign** 활동을 삭제 하는 경우 workflow Designer가 **Prompt** 활동과 새로 추가 된 **Assign** 활동을 모두 포함 하도록 **Sequence** 활동을 자동으로 추가 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-144">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>

7. <span data-ttu-id="6d876-145">`Turns`To box에 **를** 입력 하 고 `Turns + 1` **c # 식 입력** 또는 **VB 식 입력** 상자에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-145">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

8. <span data-ttu-id="6d876-146">**도구 상자** 의 **제어 흐름** 섹션에서 **If** 활동을 끌어 새로 추가 된 **Assign** 활동 뒤에 오도록 **시퀀스** 활동에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-146">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>

9. <span data-ttu-id="6d876-147">**If** 활동의 **Condition** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-147">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

10. <span data-ttu-id="6d876-148">**도구 상자** 의 **제어 흐름** 섹션에서 다른 **if** 활동을 끌어 첫 번째 **if** 활동의 **Then** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-148">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>

11. <span data-ttu-id="6d876-149">새로 추가 된 **If** 활동의 **Condition** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-149">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>

    ```text
    Guess < Target
    ```

12. <span data-ttu-id="6d876-150">**도구 상자** 의 **기본 형식** 섹션에서 두 **WriteLine** 활동을 끌어 새로 추가 된 **If** 활동의 **Then** 섹션에 있고, 다른 하나는 **Else** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-150">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>

13. <span data-ttu-id="6d876-151">**Then** 섹션에서 **WriteLine** 활동을 클릭 하 여 선택 하 고 **텍스트** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-151">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too low."
    ```

14. <span data-ttu-id="6d876-152">**Else** 섹션에서 **WriteLine** 활동을 클릭 하 여 선택 하 고 **텍스트** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-152">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too high."
    ```

     <span data-ttu-id="6d876-153">다음 예에서는 완료 된 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-153">The following example illustrates the completed workflow:</span></span>

     ![완료 된 순차 워크플로를 보여 주는 스크린샷](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)

## <a name="to-build-the-workflow"></a><span data-ttu-id="6d876-155">워크플로를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="6d876-155">To build the workflow</span></span>

1. <span data-ttu-id="6d876-156">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-156">Press CTRL+SHIFT+B to build the solution.</span></span>

     <span data-ttu-id="6d876-157">워크플로를 실행 하는 방법에 대 한 지침은 다음 항목인 [방법: 워크플로 실행](how-to-run-a-workflow.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d876-157">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="6d876-158">[방법:](how-to-run-a-workflow.md) 워크플로의 다른 스타일을 사용 하 여 워크플로 단계 실행을 이미 완료 했 고이 단계에서 순차 워크플로를 사용 하 여 실행 하려는 경우 [방법: 워크플로 실행](how-to-run-a-workflow.md)의 [응용 프로그램 섹션을 빌드하고 실행](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 하려면로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="6d876-158">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6d876-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d876-159">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="6d876-160">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="6d876-160">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="6d876-161">워크플로 디자인</span><span class="sxs-lookup"><span data-stu-id="6d876-161">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="6d876-162">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="6d876-162">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="6d876-163">방법: 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="6d876-163">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="6d876-164">방법: 워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="6d876-164">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
