---
title: '방법: 상태 시스템 워크플로 만들기'
description: 이 문서에서는 StateMachine 활동 및 사용자 지정 활동과 같은 기본 제공 활동을 모두 사용 하는 워크플로를 만듭니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 8a9342c07c15d65df0310c0cb35b4b2c6f2ba686
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419657"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="9cfad-103">방법: 상태 시스템 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="9cfad-103">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="9cfad-104">기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="9cfad-105">이 항목에서는 활동과 같은 기본 제공 활동과 <xref:System.Activities.Statements.StateMachine> 이전 [방법: 활동 만들기](how-to-create-an-activity.md) 항목의 사용자 지정 활동을 모두 사용 하는 워크플로를 만드는 과정을 단계별로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="9cfad-106">이 워크플로는 숫자 추측 게임을 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-106">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9cfad-107">초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="9cfad-108">이 항목을 완료 하려면 먼저 [방법: 작업 만들기](how-to-create-an-activity.md)를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9cfad-109">자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](https://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9cfad-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="9cfad-110">워크플로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9cfad-110">To create the workflow</span></span>  
  
1. <span data-ttu-id="9cfad-111">**솔루션 탐색기** 에서 **NumberGuessWorkflowActivities** 을 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 항목**을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-111">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="9cfad-112">**설치 됨**, **공통 항목** 노드에서 **워크플로**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-112">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="9cfad-113">**워크플로** 목록에서 **작업**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-113">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="9cfad-114">`StateMachineNumberGuessWorkflow` **이름** 상자에를 입력 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-114">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="9cfad-115">**도구 상자** 의 **상태 시스템** 섹션에서 **StateMachine** 활동을 끌어 워크플로 디자인 화면의 **여기에 작업 놓기** 레이블에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-115">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="9cfad-116">워크플로 변수와 인수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9cfad-116">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="9cfad-117">**솔루션 탐색기** 에서 **statemachinenumberguessworkflow.xaml** 를 두 번 클릭 하 여 디자이너에 워크플로를 표시 합니다 (아직 표시 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="9cfad-117">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="9cfad-118">워크플로 디자이너 왼쪽 아래에 있는 **인수** 를 클릭 하 여 **인수** 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-118">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="9cfad-119">**인수 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-119">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="9cfad-120">`MaxNumber` **이름** 상자에를 입력 하 고 **방향** 드롭다운 목록 **에서 시작을** 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32** 를 선택 하 고 enter 키를 눌러 인수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-120">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="9cfad-121">**인수 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-121">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="9cfad-122">`Turns`새로 추가 된 인수 아래에 있는 **이름** 상자에를 입력 `MaxNumber` 하 고 **방향** 드롭다운 목록에서 **바깥쪽** 을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32** 를 선택 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-122">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="9cfad-123">활동 디자이너의 왼쪽 아래에 있는 **인수**를 클릭하여 **인수** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-123">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="9cfad-124">워크플로 디자이너 왼쪽 아래에 있는 **변수** 를 클릭 하 여 **변수** 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-124">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="9cfad-125">**변수 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-125">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="9cfad-126">**변수 만들기** 상자가 표시 되지 않으면 <xref:System.Activities.Statements.StateMachine> workflow designer 화면에서 활동을 클릭 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-126">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="9cfad-127">`Guess` **이름** 상자에를 입력 하 고 **변수 형식** 드롭다운 목록에서 **Int32** 를 선택한 다음 enter 키를 눌러 변수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-127">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="9cfad-128">**변수 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-128">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="9cfad-129">`Target` **이름** 상자에를 입력 하 고 **변수 형식** 드롭다운 목록에서 **Int32** 를 선택한 다음 enter 키를 눌러 변수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-129">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="9cfad-130">활동 디자이너의 왼쪽 아래에 있는 **변수**를 클릭하여 **변수** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-130">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="9cfad-131">워크플로 활동을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="9cfad-131">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="9cfad-132">**State1** 을 클릭 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-132">Click **State1** to select it.</span></span> <span data-ttu-id="9cfad-133">**속성 창**에서 **DisplayName** 을로 변경 합니다 `Initialize Target` .</span><span class="sxs-lookup"><span data-stu-id="9cfad-133">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="9cfad-134">**속성 창이** 표시 되지 않으면 **보기** 메뉴에서 **속성 창** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-134">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2. <span data-ttu-id="9cfad-135">Workflow designer에서 새로 이름이 바뀐 **Initialize Target** 상태를 두 번 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-135">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3. <span data-ttu-id="9cfad-136">**도구 상자** 의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 상태의 **항목** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-136">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="9cfad-137">`Target`To 상자에 **를** 입력 하 고 **c # 식 입력** 또는 **VB 식 입력** 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-137">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="9cfad-138">**도구 상자** 창이 표시되지 않으면 **보기** 메뉴에서 **도구 상자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-138">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4. <span data-ttu-id="9cfad-139">Workflow designer 위쪽의 이동 경로 표시에서 **StateMachine** 을 클릭 하 여 workflow designer의 전체 상태 시스템 뷰로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-139">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5. <span data-ttu-id="9cfad-140">**도구 상자** 의 **상태 시스템** 섹션에서 **state** 활동을 workflow designer로 끌어 **Initialize Target** 상태 위로 가져갑니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-140">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="9cfad-141">새 상태에 있는 경우 네 개의 삼각형이 **Initialize Target** 상태 주위에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-141">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="9cfad-142">**초기화 대상** 상태 바로 아래에 있는 삼각형의 새 상태를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-142">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="9cfad-143">그러면 새 상태가 워크플로에 추가 되 고 **Initialize Target** 상태에서 새 상태로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-143">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6. <span data-ttu-id="9cfad-144">**State1** 을 클릭 하 여 선택 하 고 **DisplayName** 을로 변경한 `Enter Guess` 다음 workflow designer에서 상태를 두 번 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-144">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7. <span data-ttu-id="9cfad-145">**도구 상자** 의 **기본 형식** 섹션에서 **WriteLine** 활동을 끌어 상태의 **항목** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-145">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8. <span data-ttu-id="9cfad-146">**WriteLine**의 **텍스트** 속성 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-146">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="9cfad-147">**도구 상자** 의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 상태의 **종료** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-147">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="9cfad-148">`Turns`To box에 **를** 입력 하 고 `Turns + 1` **c # 식 입력** 또는 **VB 식 입력** 상자에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-148">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="9cfad-149">Workflow designer 위쪽의 이동 경로 표시에서 **StateMachine** 을 클릭 하 여 workflow designer의 전체 상태 시스템 뷰로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-149">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="9cfad-150">**도구 상자**의 **상태 시스템** 섹션에서 나머지 **상태** 활동을 끌어서 enter **guess 상태 위로** 마우스를 이동 하 고 enter guess 상태와 동일한 항목으로 이동 하 여 enter **guess 상태와** **상태** **사이에** 전환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-150">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="9cfad-151">전환의 기본 이름은 **T2**입니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-151">The default name of the transition is **T2**.</span></span> <span data-ttu-id="9cfad-152">Workflow designer에서 전환을 클릭 하 여 선택 하 고 **DisplayName** 을 **Guess**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-152">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="9cfad-153">그런 다음, 선택 된 **상태**를 클릭 하 여 선택 하 고 오른쪽으로 끌어 전체 전환 이름을 표시 하는 데 사용할 공간이 두 상태 중 어느 상태에도 겹치지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-153">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="9cfad-154">이렇게 하면 자습서의 나머지 단계를 보다 쉽게 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-154">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="9cfad-155">Workflow designer에서 새로 이름이 바뀐 **추측 올바른** 전환을 두 번 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-155">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="9cfad-156">**도구 상자** 의 **NumberGuessWorkflowActivities** 섹션에서 **readint** 활동을 끌어 전환의 **트리거** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-156">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="9cfad-157">**Readint** 활동의 **속성 창** 에서 `"EnterGuess"` **BookmarkName** 속성 값 상자에 따옴표를 포함 하 여를 입력 하 고 `Guess` **결과** 속성 값 상자에를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-157">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="9cfad-158">**올바른** 전환의 **조건** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-158">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="9cfad-159">Workflow designer 위쪽의 이동 경로 표시에서 **StateMachine** 을 클릭 하 여 workflow designer의 전체 상태 시스템 뷰로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-159">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9cfad-160">트리거 이벤트를 받고 <xref:System.Activities.Statements.Transition.Condition%2A>이 `True`인 경우 전환이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-160">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="9cfad-161">이 전환의 경우 사용자가 `Guess` 임의로 생성 된와 일치 하는 경우 `Target` 제어가 **상태** 에 전달 되 고 워크플로가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-161">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="9cfad-162">Guess가 정확한 지 여부에 따라 워크플로는 다른 시도에 대 한 상태 **또는 다시** **Enter 추측** 상태로 전환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-162">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="9cfad-163">두 전환은 모두 **Readint** 활동을 통해 사용자의 추측을 수신 하기 위해 대기 하는 동일한 트리거를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-163">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="9cfad-164">이를 공유 전환이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-164">This is called a shared transition.</span></span> <span data-ttu-id="9cfad-165">공유 전환을 만들려면 **추측 올바른** 전환의 시작을 나타내는 원을 클릭 하 고 원하는 상태로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-165">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="9cfad-166">이 경우 전환은 자체 전환 이므로 **추측 올바른** 전환의 시작점을 끌어서 **Enter guess** 상태의 맨 아래에 다시 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-166">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="9cfad-167">전환을 만든 후에는 workflow designer에서 해당 전환을 선택 하 고 **DisplayName** 속성을 **잘못 된 추측**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-167">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9cfad-168">전환 디자이너의 맨 아래에 있는 **공유 트리거 전환 추가** 를 클릭 한 다음 **사용 가능한 상태 드롭다운에서 연결할** 대상 상태를 선택 하 여 전환 디자이너 내에서 공유 전환을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-168">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9cfad-169">전환의 <xref:System.Activities.Statements.Transition.Condition%2A>이 `false`가 되거나 모든 공유 트리거 전환 조건이 `false`가 되는 경우에는 전환이 일어나지 않으며 해당 상태로부터의 모든 전환에 대한 모든 트리거가 다시 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-169">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="9cfad-170">이 자습서에서는 조건이 구성된 방식(추측이 올바른지 또는 잘못되었는지에 따라 특정 동작이 지정됨) 때문에 이러한 상황이 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-170">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="9cfad-171">Workflow designer에서 **잘못 된 Guess** 전환을 두 번 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-171">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="9cfad-172">**트리거** 는 **추측 올바른** 전환에 사용 된 것과 동일한 **readint** 작업으로 이미 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-172">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="9cfad-173">**조건** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-173">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="9cfad-174">**도구 상자** 의 **제어 흐름** 섹션에서 **If** 활동을 끌어 전환의 **작업** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-174">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="9cfad-175">**If** 활동의 **Condition** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-175">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
24. <span data-ttu-id="9cfad-176">**도구 상자** 의 **기본 형식** 섹션에서 두 **WriteLine** **활동을 끌어 해당 활동의** **Then** 섹션에 있고 하나는 **Else** 섹션에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-176">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="9cfad-177">**Then** 섹션에서 **WriteLine** 활동을 클릭 하 여 선택 하 고 **텍스트** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-177">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="9cfad-178">**Else** 섹션에서 **WriteLine** 활동을 클릭 하 여 선택 하 고 **텍스트** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-178">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="9cfad-179">Workflow designer 위쪽의 이동 경로 표시에서 **StateMachine** 을 클릭 하 여 workflow designer의 전체 상태 시스템 뷰로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-179">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="9cfad-180">다음 예제에서는 완료된 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-180">The following example illustrates the completed workflow.</span></span>  
  
     ![완료 된 상태 시스템 워크플로를 보여 주는 그림입니다.](./media/how-to-create-a-state-machine-workflow/complete-state-machine-workflow.jpg)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="9cfad-182">워크플로를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="9cfad-182">To build the workflow</span></span>  
  
1. <span data-ttu-id="9cfad-183">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-183">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="9cfad-184">워크플로를 실행 하는 방법에 대 한 지침은 다음 항목인 [방법: 워크플로 실행](how-to-run-a-workflow.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cfad-184">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="9cfad-185">방법: 워크플로의 다른 스타일로 [워크플로 단계 실행](how-to-run-a-workflow.md) 을 이미 완료 했 고이 단계에서 상태 시스템 워크플로를 사용 하 여 실행 하려는 경우 [방법: 워크플로 실행](how-to-run-a-workflow.md)의 [응용 프로그램을 빌드하고 실행 하려면](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 섹션으로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="9cfad-185">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cfad-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9cfad-186">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="9cfad-187">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="9cfad-187">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="9cfad-188">워크플로 디자인</span><span class="sxs-lookup"><span data-stu-id="9cfad-188">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="9cfad-189">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="9cfad-189">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="9cfad-190">방법: 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="9cfad-190">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="9cfad-191">방법: 워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="9cfad-191">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
