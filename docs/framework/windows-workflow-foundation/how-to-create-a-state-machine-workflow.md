---
title: '방법: 상태 시스템 워크플로 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: e93f84f0bacf7ac205294c12c55afcab8d7319b7
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989818"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="1d170-102">방법: 상태 시스템 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="1d170-102">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="1d170-103">기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="1d170-104">이 항목에서는 <xref:System.Activities.Statements.StateMachine> 활동과 같은 기본 제공 활동과 이전 [의 사용자 지정 활동을 모두 사용 하는 워크플로를 만드는 방법을 단계별로 설명 합니다. 활동](how-to-create-an-activity.md) 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="1d170-105">이 워크플로는 숫자 추측 게임을 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d170-106">초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="1d170-107">이 항목을 완료 하려면 먼저 다음 작업을 수행 [합니다. 활동](how-to-create-an-activity.md)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d170-108">자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](https://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d170-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="1d170-109">워크플로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1d170-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="1d170-110">**솔루션 탐색기** 에서 **NumberGuessWorkflowActivities** 을 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 항목**을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="1d170-111">**설치 됨**, **공통 항목** 노드에서 **워크플로**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="1d170-112">**워크플로** 목록에서 **작업** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="1d170-113">**이름** 상자에 `StateMachineNumberGuessWorkflow`을 입력 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="1d170-114">**도구 상자** 의 **상태 시스템** 섹션에서 **StateMachine** 활동을 끌어 워크플로 디자인 화면의 **여기에 작업 놓기** 레이블에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="1d170-115">워크플로 변수와 인수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1d170-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="1d170-116">**솔루션 탐색기** 에서 **statemachinenumberguessworkflow.xaml** 를 두 번 클릭 하 여 디자이너에 워크플로를 표시 합니다 (아직 표시 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="1d170-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="1d170-117">워크플로 디자이너 왼쪽 아래에 있는 **인수** 를 클릭 하 여 **인수** 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="1d170-118">**인수 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="1d170-119">**이름** 상자에 `MaxNumber`를 입력 하 고 **방향** 드롭다운 목록 **에서 시작을 선택한 다음** **인수 형식** 드롭다운 목록에서 **Int32** 를 선택 하 고 enter 키를 눌러 인수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="1d170-120">**인수 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="1d170-121">새로 추가 된 `MaxNumber` 인수 아래에 있는 **이름** 상자에 `Turns`을 입력 하 고 **방향** 드롭다운 목록에서 **바깥쪽** 을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32** 를 선택 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="1d170-122">활동 디자이너 왼쪽 아래에 있는 **인수** 를 클릭 하 여 **인수** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="1d170-123">워크플로 디자이너 왼쪽 아래에 있는 **변수** 를 클릭 하 여 **변수** 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="1d170-124">**변수 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="1d170-125">**변수 만들기** 상자가 표시 되지 않으면 workflow designer 화면에서 <xref:System.Activities.Statements.StateMachine> 활동을 클릭 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="1d170-126">**이름** 상자에 `Guess`를 입력 하 고 **변수 형식** 드롭다운 목록에서 **Int32** 를 선택한 다음 enter 키를 눌러 변수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="1d170-127">**변수 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="1d170-128">**이름** 상자에 `Target`를 입력 하 고 **변수 형식** 드롭다운 목록에서 **Int32** 를 선택한 다음 enter 키를 눌러 변수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="1d170-129">활동 디자이너의 왼쪽 아래에 있는 **변수** 를 클릭 하 여 **변수** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="1d170-130">워크플로 활동을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="1d170-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="1d170-131">**State1** 을 클릭 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-131">Click **State1** to select it.</span></span> <span data-ttu-id="1d170-132">**속성 창**에서 **DisplayName** 을 `Initialize Target`로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="1d170-133">**속성 창이** 표시 되지 않으면 **보기** 메뉴에서 **속성 창** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2. <span data-ttu-id="1d170-134">Workflow designer에서 새로 이름이 바뀐 **Initialize Target** 상태를 두 번 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3. <span data-ttu-id="1d170-135">**도구 상자** 의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 상태의 **항목** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="1d170-136">**To** 상자에 `Target`를 입력 하 고  **C# 식 입력** 또는 **VB 식 입력** 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="1d170-137">**도구 상자** 창이 표시 되지 않으면 **보기** 메뉴에서 **도구 상자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4. <span data-ttu-id="1d170-138">Workflow designer 위쪽의 이동 경로 표시에서 **StateMachine** 을 클릭 하 여 workflow designer의 전체 상태 시스템 뷰로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5. <span data-ttu-id="1d170-139">**도구 상자** 의 **상태 시스템** 섹션에서 **state** 활동을 workflow designer로 끌어 **Initialize Target** 상태 위로 가져갑니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="1d170-140">새 상태에 있는 경우 네 개의 삼각형이 **Initialize Target** 상태 주위에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="1d170-141">**초기화 대상** 상태 바로 아래에 있는 삼각형의 새 상태를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="1d170-142">그러면 새 상태가 워크플로에 추가 되 고 **Initialize Target** 상태에서 새 상태로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6. <span data-ttu-id="1d170-143">**State1** 을 클릭 하 여 선택 하 고 **DisplayName** 을 `Enter Guess`로 변경한 다음 workflow designer에서 상태를 두 번 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7. <span data-ttu-id="1d170-144">**도구 상자** 의 **기본 형식** 섹션에서 **WriteLine** 활동을 끌어 상태의 **항목** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8. <span data-ttu-id="1d170-145">**WriteLine**의 **텍스트** 속성 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="1d170-146">**도구 상자** 의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 상태의 **종료** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="1d170-147">To 상자에 `Turns` **을** 입력 하 고  **C# 식 입력** 또는 **VB 식 입력** 상자에 `Turns + 1` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="1d170-148">Workflow designer 위쪽의 이동 경로 표시에서 **StateMachine** 을 클릭 하 여 workflow designer의 전체 상태 시스템 뷰로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="1d170-149">**도구 상자**의 **상태 시스템** 섹션에서 나머지 **상태** 활동을 끌어서 enter **guess 상태 위로** 마우스를 이동 하 고 enter guess 상태와 동일한 항목으로 이동 하 여 enter **guess 상태와** **상태** **사이에** 전환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="1d170-150">전환의 기본 이름은 **T2**입니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="1d170-151">Workflow designer에서 전환을 클릭 하 여 선택 하 고 **DisplayName** 을 **Guess**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="1d170-152">그런 다음, 선택 된 **상태**를 클릭 하 여 선택 하 고 오른쪽으로 끌어 전체 전환 이름을 표시 하는 데 사용할 공간이 두 상태 중 어느 상태에도 겹치지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="1d170-153">이렇게 하면 자습서의 나머지 단계를 보다 쉽게 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="1d170-154">Workflow designer에서 새로 이름이 바뀐 **추측 올바른** 전환을 두 번 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="1d170-155">**도구 상자** 의 **NumberGuessWorkflowActivities** 섹션에서 **readint** 활동을 끌어 전환의 **트리거** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="1d170-156">**Readint** 활동의 **속성 창** 에서 **BookmarkName** 속성 값 상자에 따옴표를 포함 하 `"EnterGuess"`을 입력 하 고 **결과** 속성 값 상자에 `Guess`을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="1d170-157">**올바른** 전환의 **조건** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="1d170-158">Workflow designer 위쪽의 이동 경로 표시에서 **StateMachine** 을 클릭 하 여 workflow designer의 전체 상태 시스템 뷰로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1d170-159">트리거 이벤트를 받고 <xref:System.Activities.Statements.Transition.Condition%2A>이 `True`인 경우 전환이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="1d170-160">이 전환의 경우 사용자의 `Guess` 무작위로 생성 된 `Target`와 일치 하는 경우 제어가 **상태** 에 전달 되 고 워크플로가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="1d170-161">Guess가 정확한 지 여부에 따라 워크플로는 다른 시도에 대 한 상태 **또는 다시** **Enter 추측** 상태로 전환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="1d170-162">두 전환은 모두 **Readint** 활동을 통해 사용자의 추측을 수신 하기 위해 대기 하는 동일한 트리거를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="1d170-163">이를 공유 전환이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-163">This is called a shared transition.</span></span> <span data-ttu-id="1d170-164">공유 전환을 만들려면 **추측 올바른** 전환의 시작을 나타내는 원을 클릭 하 고 원하는 상태로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="1d170-165">이 경우 전환은 자체 전환 이므로 **추측 올바른** 전환의 시작점을 끌어서 **Enter guess** 상태의 맨 아래에 다시 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="1d170-166">전환을 만든 후에는 workflow designer에서 해당 전환을 선택 하 고 **DisplayName** 속성을 **잘못 된 추측**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1d170-167">전환 디자이너의 맨 아래에 있는 **공유 트리거 전환 추가** 를 클릭 한 다음 **사용 가능한 상태 드롭다운에서 연결할** 대상 상태를 선택 하 여 전환 디자이너 내에서 공유 전환을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1d170-168">전환의 <xref:System.Activities.Statements.Transition.Condition%2A>이 `false`가 되거나 모든 공유 트리거 전환 조건이 `false`가 되는 경우에는 전환이 일어나지 않으며 해당 상태로부터의 모든 전환에 대한 모든 트리거가 다시 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="1d170-169">이 자습서에서는 조건이 구성된 방식(추측이 올바른지 또는 잘못되었는지에 따라 특정 동작이 지정됨) 때문에 이러한 상황이 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="1d170-170">Workflow designer에서 **잘못 된 Guess** 전환을 두 번 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="1d170-171">**트리거** 는 **추측 올바른** 전환에 사용 된 것과 동일한 **readint** 작업으로 이미 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="1d170-172">**조건** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="1d170-173">**도구 상자** 의 **제어 흐름** 섹션에서 **If** 활동을 끌어 전환의 **작업** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="1d170-174">**If** 활동의 **Condition** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
24. <span data-ttu-id="1d170-175">**도구 상자** 의 **기본 형식** 섹션에서 두 **WriteLine** **활동을 끌어 해당 활동의** **Then** 섹션에 있고 하나는 **Else** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="1d170-176">**Then** 섹션에서 **WriteLine** 활동을 클릭 하 여 선택 하 고 **텍스트** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="1d170-177">**Else** 섹션에서 **WriteLine** 활동을 클릭 하 여 선택 하 고 **텍스트** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="1d170-178">Workflow designer 위쪽의 이동 경로 표시에서 **StateMachine** 을 클릭 하 여 workflow designer의 전체 상태 시스템 뷰로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="1d170-179">다음 예제에서는 완료된 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-179">The following example illustrates the completed workflow.</span></span>  
  
     ![완료 된 상태 시스템 워크플로를 보여 주는 그림입니다.](./media/how-to-create-a-state-machine-workflow/complete-state-machine-workflow.jpg)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="1d170-181">워크플로를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="1d170-181">To build the workflow</span></span>  
  
1. <span data-ttu-id="1d170-182">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="1d170-183">워크플로를 실행 하는 방법에 대 한 지침은 다음 항목을 참조 하십시오. 방법: [ 워크플로를 실행 합니다](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="1d170-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="1d170-184">[를 이미 완료 한 경우 방법: 워크플로의 다른 스타일을 사용 하 여 워크플로](how-to-run-a-workflow.md) 단계를 실행 하 고이 단계에서 상태 시스템 워크플로를 사용 하 여 실행 하려는 경우에는 다음을 수행 하는 방법 [의 [응용 프로그램을 빌드하고 실행 하려면](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 섹션으로 건너뜁니다. ](how-to-run-a-workflow.md)워크플로를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-184">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d170-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d170-185">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="1d170-186">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="1d170-186">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="1d170-187">워크플로 디자인</span><span class="sxs-lookup"><span data-stu-id="1d170-187">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="1d170-188">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="1d170-188">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- <span data-ttu-id="1d170-189">[방법: 활동](how-to-create-an-activity.md) 만들기</span><span class="sxs-lookup"><span data-stu-id="1d170-189">[How to: Create an Activity](how-to-create-an-activity.md)</span></span>
- <span data-ttu-id="1d170-190">[방법: 워크플로](how-to-run-a-workflow.md)를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d170-190">[How to: Run a Workflow](how-to-run-a-workflow.md)</span></span>
