---
title: '방법: 상태 시스템 워크플로 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 654621ab7dd74c26a7fddbd985559a713c0e9df3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59294810"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="10bcb-102">방법: 상태 시스템 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="10bcb-102">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="10bcb-103">기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="10bcb-104">이 항목에서는 같은 모두 기본 제공 활동을 사용 하는 워크플로 만드는 방법을 단계별로 합니다 <xref:System.Activities.Statements.StateMachine> 활동 및 사용자 지정 활동을 이전 [방법: 활동 만들기](how-to-create-an-activity.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="10bcb-105">이 워크플로는 숫자 추측 게임을 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10bcb-106">초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="10bcb-107">이 항목을 완료 하려면 먼저 마쳐야 [방법: 활동 만들기](how-to-create-an-activity.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10bcb-108">자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](https://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10bcb-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="10bcb-109">워크플로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="10bcb-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="10bcb-110">마우스 오른쪽 단추로 클릭 **NumberGuessWorkflowActivities** 에서 **솔루션 탐색기** 선택한 **추가**하십시오 **새 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="10bcb-111">에 **설치 됨**를 **공통 항목** 노드를 선택 **워크플로**합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="10bcb-112">선택 **활동** 에서 합니다 **워크플로** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="10bcb-113">형식 `StateMachineNumberGuessWorkflow` 에 **이름** 상자 하 고 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="10bcb-114">끌어서를 **StateMachine** 활동에서는 **상태 시스템** 부분을 **도구 상자** 놓습니다를 **여기에 작업 놓기** 에 레이블 워크플로 디자인 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="10bcb-115">워크플로 변수와 인수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="10bcb-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="10bcb-116">두 번 클릭 **StateMachineNumberGuessWorkflow.xaml** 에 **솔루션 탐색기** 이미 표시 되지 않으면 워크플로 디자이너에서 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="10bcb-117">클릭 **인수** 표시할 워크플로 디자이너 왼쪽 아래에에서는 **인수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="10bcb-118">클릭 **인수를 만드는**합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="10bcb-119">형식 `MaxNumber` 에 **이름** 상자에서 **에서** 에서 합니다 **방향** 드롭 다운 목록에서 **Int32** 합니다 에서**인수 형식** 드롭 다운 목록 및 다음 인수를 저장 하려면 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="10bcb-120">클릭 **인수를 만드는**합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="10bcb-121">형식 `Turns` 에 **이름** 새로 추가 된 아래에 있는 상자 `MaxNumber` 인수 **Out** 에서 **방향** 드롭 다운 목록에서  **Int32** 에서 합니다 **인수 형식** 드롭 다운 목록 및 다음 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="10bcb-122">클릭 **인수** 닫으려면 activity designer의 왼쪽 아래에에서는 **인수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="10bcb-123">클릭 **변수** 표시할 워크플로 디자이너 왼쪽 아래에에서는 **변수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="10bcb-124">클릭 **변수를 만듭니다**합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="10bcb-125">없으면 **변수 만들기** 상자가 표시 됩니다을 클릭 합니다 <xref:System.Activities.Statements.StateMachine> 선택 하려면 워크플로 디자이너 화면에 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="10bcb-126">형식 `Guess` 에 **이름** 상자에서 **Int32** 에서 합니다 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하려면 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="10bcb-127">클릭 **변수를 만듭니다**합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="10bcb-128">형식 `Target` 에 **이름** 상자에서 **Int32** 에서 합니다 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하려면 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="10bcb-129">클릭 **변수** 닫으려면 activity designer의 왼쪽 아래에에서는 **변수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="10bcb-130">워크플로 활동을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="10bcb-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="10bcb-131">클릭 **State1** 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-131">Click **State1** to select it.</span></span> <span data-ttu-id="10bcb-132">에 **속성 창**를 변경 합니다 **DisplayName** 를 `Initialize Target`.</span><span class="sxs-lookup"><span data-stu-id="10bcb-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="10bcb-133">경우는 **속성 창** 표시를 선택 하지 않는 **속성 창** 에서 합니다 **뷰** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="10bcb-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2. <span data-ttu-id="10bcb-134">이름을 새로 바꾼 두 번 클릭 **Initialize Target** 확장 하는 데 워크플로 디자이너의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3. <span data-ttu-id="10bcb-135">끌어서는 **할당** 활동에서를 **기본형** 섹션을 **도구 상자** 놓습니다를 **항목** 상태 섹션.</span><span class="sxs-lookup"><span data-stu-id="10bcb-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="10bcb-136">형식 `Target` 에 **에** 상자 및에 다음 식을 합니다 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="10bcb-137">경우는 **도구 상자** 창이 표시 되지 않으면, 선택 **도구 상자** 에서 합니다 **뷰** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="10bcb-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4. <span data-ttu-id="10bcb-138">전체 반환 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 있는 이동 경로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5. <span data-ttu-id="10bcb-139">끌어서를 **상태** 활동에서는 **상태 시스템** 부분을 **도구 상자** 워크플로 디자이너로 위로 가져갑니다는 **Initialize Target** 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="10bcb-140">주위에 삼각형 네 개가 표시 됩니다는 참고 합니다 **Initialize Target** 상태 위에 새 상태가 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="10bcb-141">바로 아래에 있는 삼각형에 새 상태를 삭제 합니다 **Initialize Target** 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="10bcb-142">이 새 상태가 워크플로에 배치 및의 전환이 만들어집니다 합니다 **Initialize Target** 새 상태로 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6. <span data-ttu-id="10bcb-143">클릭 **State1** 선택, 변경 합니다 **DisplayName** 에 `Enter Guess`를 차례로 확장 하는 데 워크플로 디자이너의 상태를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7. <span data-ttu-id="10bcb-144">끌어서를 **WriteLine** 활동에서를 **기본형** 섹션을 **도구 상자** 놓습니다를 **항목** 상태 섹션.</span><span class="sxs-lookup"><span data-stu-id="10bcb-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8. <span data-ttu-id="10bcb-145">에 다음 식을 입력 합니다 **텍스트** 의 속성 상자를 **WriteLine**합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="10bcb-146">끌어서를 **할당** 활동에서는 **기본** 부분을 **도구 상자** 끌어다 놓으십시오를 **종료** 상태 섹션.</span><span class="sxs-lookup"><span data-stu-id="10bcb-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="10bcb-147">형식 `Turns` 에 **하** 상자 및 `Turns + 1` 에 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="10bcb-148">전체 반환 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 있는 이동 경로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="10bcb-149">끌어서를 **FinalState** 활동에서를 **상태 시스템** 섹션을 **도구 상자**, 위로 가져갑니다를 **Enter Guess** 상태를 놓습니다 오른쪽에 나타나는 삼각형에는 **Enter Guess** 상태 간의 전환을 만들어지도록 **Enter Guess** 하 고 **FinalState**합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="10bcb-150">전환의 기본 이름은 **T2**합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="10bcb-151">선택 하 고 설정 워크플로 디자이너에서 전환을 클릭 해당 **DisplayName** 하 **Guess Correct**합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="10bcb-152">그런 다음을 선택 합니다 **FinalState**, 두 상태 중 어느 쪽도 겹치지 않고 표시할 전체 전환 이름 위한 공간을 확보 되도록 오른쪽에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="10bcb-153">이렇게 하면 자습서의 나머지 단계를 보다 쉽게 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="10bcb-154">이름을 새로 바꾼 두 번 클릭 **Guess Correct** 확장 하는 데 워크플로 디자이너에서 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="10bcb-155">끌어서를 **ReadInt** 활동에서는 **NumberGuessWorkflowActivities** 부분을 **도구 상자** 놓습니다를 **트리거** 섹션 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="10bcb-156">에 **속성 창** 에 대 한 합니다 **ReadInt** 활동을 입력 `"EnterGuess"` 따옴표를 포함 하 여를 **BookmarkName** 속성 값 상자 및 형식 `Guess`에 **결과** 속성 값 상자</span><span class="sxs-lookup"><span data-stu-id="10bcb-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="10bcb-157">에 다음 식을 입력 합니다 **Guess Correct** 전환 **조건** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="10bcb-158">전체 반환 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 있는 이동 경로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10bcb-159">트리거 이벤트를 받고 <xref:System.Activities.Statements.Transition.Condition%2A>이 `True`인 경우 전환이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="10bcb-160">이 전환의 경우 사용자의 `Guess` 임의로 생성 된 일치 `Target`, 컨트롤을 전달 하는 다음을 **FinalState** 되 고 워크플로가 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="10bcb-161">추측이 올바른지 여부에 따라 워크플로의 전환 해야 하는 **FinalState** 또는 다시 합니다 **Enter Guess** 다른 시도 대 한 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="10bcb-162">두 전환 모두 사용자의 추측을 통해 받을 때까지 기다리는 동일한 트리거를 공유 합니다 **ReadInt** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="10bcb-163">이를 공유 전환이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-163">This is called a shared transition.</span></span> <span data-ttu-id="10bcb-164">공유 전환을 만들려면의 시작을 나타내는 원을 클릭 합니다 **Guess Correct** 전환 하 고 원하는 상태로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="10bcb-165">이 경우에 전환은 자체 전환, 따라서의 시작점을 끌어 합니다 **Guess Correct** 전환 하 고 맨 아래에 다시 놓습니다 합니다 **Enter Guess** 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="10bcb-166">전환을 만든 후 워크플로 디자이너에서 선택 하 고 설정 해당 **DisplayName** 속성을 **Guess Incorrect**합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10bcb-167">공유 전환을 만들 수도 있습니다에서 전환 디자이너 내에서 클릭 하 여 **공유 트리거 전환 추가** 아래쪽의 전환 디자이너, 한 다음 원하는 대상 상태를 선택 하 여  **연결에 사용할 상태** 드롭 다운 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10bcb-168">전환의 <xref:System.Activities.Statements.Transition.Condition%2A>이 `false`가 되거나 모든 공유 트리거 전환 조건이 `false`가 되는 경우에는 전환이 일어나지 않으며 해당 상태로부터의 모든 전환에 대한 모든 트리거가 다시 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="10bcb-169">이 자습서에서는 조건이 구성된 방식(추측이 올바른지 또는 잘못되었는지에 따라 특정 동작이 지정됨) 때문에 이러한 상황이 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="10bcb-170">두 번 클릭 합니다 **Guess Incorrect** 확장 하는 데 워크플로 디자이너에서 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="10bcb-171">합니다 **트리거** 동일 하 게 이미 설정 되어 **ReadInt** 활동에서 사용 하는 **Guess Correct** 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="10bcb-172">에 다음 식을 입력 합니다 **조건을** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="10bcb-173">끌어서는 **경우** 활동에서를 **제어 흐름** 섹션을 **도구 상자** 놓습니다를 **작업** 전환의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="10bcb-174">에 다음 식을 입력 합니다 **하는 경우** 활동의 **조건** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
24. <span data-ttu-id="10bcb-175">두 개 **WriteLine** 활동에서는 **기본** 부분을 **도구 상자** 되도록 하나에 놓을 **다음** 섹션 합니다 **하는 경우** 활동을 하나는 **Else** 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="10bcb-176">클릭는 **WriteLine** 활동에는 **다음** 섹션을 선택 하 고에 다음 식을 입력 합니다 **텍스트** 속성 값 상자.</span><span class="sxs-lookup"><span data-stu-id="10bcb-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="10bcb-177">클릭는 **WriteLine** 활동에는 **Else** 섹션을 선택 하 고에 다음 식을 입력 합니다 **텍스트** 속성 값 상자.</span><span class="sxs-lookup"><span data-stu-id="10bcb-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="10bcb-178">전체 반환 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 있는 이동 경로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="10bcb-179">다음 예제에서는 완료된 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-179">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="10bcb-180">![완료 된 상태 시스템 워크플로](./media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span><span class="sxs-lookup"><span data-stu-id="10bcb-180">![Completed State Machine Workflow](./media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="10bcb-181">워크플로를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="10bcb-181">To build the workflow</span></span>  
  
1. <span data-ttu-id="10bcb-182">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="10bcb-183">워크플로 실행 하는 방법에 대 한 지침은 다음 항목을 참조 하십시오 [방법: 워크플로 실행](how-to-run-a-workflow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="10bcb-184">이미 완료 하는 경우는 [방법: 워크플로 실행](how-to-run-a-workflow.md) 이 단계에서 상태 시스템 워크플로 사용 하 여 실행 하려는 워크플로의 다른 스타일을 사용 하 여 단계를 건너 뛰 세요 합니다 [빌드 및 응용 프로그램을 실행 하려면](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 부분 [하는 방법: 워크플로 실행](how-to-run-a-workflow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10bcb-184">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10bcb-185">참고자료</span><span class="sxs-lookup"><span data-stu-id="10bcb-185">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="10bcb-186">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="10bcb-186">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="10bcb-187">워크플로 디자인</span><span class="sxs-lookup"><span data-stu-id="10bcb-187">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="10bcb-188">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="10bcb-188">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="10bcb-189">방법: 활동 만들기</span><span class="sxs-lookup"><span data-stu-id="10bcb-189">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="10bcb-190">방법: 워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="10bcb-190">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
