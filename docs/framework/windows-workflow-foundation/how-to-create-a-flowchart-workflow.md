---
title: '방법: 순서도 워크플로 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: 10483c747e0f86816db6f03dd8df17472f31f15c
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063763"
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="ac2c8-102">방법: 순서도 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="ac2c8-102">How to: Create a Flowchart Workflow</span></span>
<span data-ttu-id="ac2c8-103">기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="ac2c8-104">이 항목에서는 같은 모두 기본 제공 활동을 사용 하는 워크플로 만드는 방법을 단계별로 합니다 <xref:System.Activities.Statements.Flowchart> 활동 및 사용자 지정 활동을 이전 [방법: 활동 만들기](how-to-create-an-activity.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="ac2c8-105">이 워크플로는 숫자 추측 게임을 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac2c8-106">초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="ac2c8-107">이 항목을 완료 하려면 먼저 마쳐야 [방법: 활동 만들기](how-to-create-an-activity.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac2c8-108">자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](https://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="ac2c8-109">워크플로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ac2c8-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="ac2c8-110">마우스 오른쪽 단추로 클릭 **NumberGuessWorkflowActivities** 에서 **솔루션 탐색기** 선택한 **추가**하십시오 **새 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="ac2c8-111">에 **설치 됨**를 **공통 항목** 노드를 선택 **워크플로**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="ac2c8-112">선택 **활동** 에서 합니다 **워크플로** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="ac2c8-113">형식 `FlowchartNumberGuessWorkflow` 에 **이름** 상자 하 고 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-113">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="ac2c8-114">끌어서를 **순서도** 활동에서는 **순서도** 부분을 **도구 상자** 놓습니다를 **여기에 작업 놓기** 에 레이블는 워크플로 디자인 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-114">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="ac2c8-115">워크플로 변수와 인수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ac2c8-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="ac2c8-116">두 번 클릭 **FlowchartNumberGuessWorkflow.xaml** 에 **솔루션 탐색기** 이미 표시 되지 않으면 워크플로 디자이너에서 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-116">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="ac2c8-117">클릭 **인수** 표시할 워크플로 디자이너 왼쪽 아래에에서는 **인수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="ac2c8-118">클릭 **인수를 만드는**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="ac2c8-119">형식 `MaxNumber` 에 **이름** 상자에서 **에서** 에서 합니다 **방향** 드롭 다운 목록에서 **Int32** 합니다 에서**인수 형식** 드롭 다운 목록 및 다음 인수를 저장 하려면 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="ac2c8-120">클릭 **인수를 만드는**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="ac2c8-121">형식 `Turns` 에 **이름** 새로 추가 된 아래에 있는 상자 `MaxNumber` 인수 **Out** 에서 **방향** 드롭 다운 목록에서  **Int32** 에서 합니다 **인수 형식** 드롭 다운 목록 및 다음 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="ac2c8-122">클릭 **인수** 닫으려면 activity designer의 왼쪽 아래에에서는 **인수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="ac2c8-123">클릭 **변수** 표시할 워크플로 디자이너 왼쪽 아래에에서는 **변수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="ac2c8-124">클릭 **변수를 만듭니다**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="ac2c8-125">없으면 **변수 만들기** 상자가 표시 됩니다을 클릭 합니다 <xref:System.Activities.Statements.Flowchart> 선택 하려면 워크플로 디자이너 화면에 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="ac2c8-126">형식 `Guess` 에 **이름** 상자에서 **Int32** 에서 합니다 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하려면 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="ac2c8-127">클릭 **변수를 만듭니다**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="ac2c8-128">형식 `Target` 에 **이름** 상자에서 **Int32** 에서 합니다 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하려면 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="ac2c8-129">클릭 **변수** 닫으려면 activity designer의 왼쪽 아래에에서는 **변수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="ac2c8-130">워크플로 활동을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="ac2c8-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="ac2c8-131">끌어서를 **할당** 활동에서는 **기본** 부분을 **도구 상자** 위로 가져갑니다를 **시작** 노드 맨 위에 있는 순서도입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="ac2c8-132">경우는 **할당** 를 통해 작업이 **시작** 노드 주위에 삼각형 세 개가 표시 됩니다는 **시작** 노드.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-132">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="ac2c8-133">삭제 합니다 **할당** 활동 바로 아래에 있는 삼각형을 **시작** 노드.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-133">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="ac2c8-134">이 두 항목을 함께 연결 하 고 지정 된 **할당** 순서도의 첫 번째 활동으로 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-134">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac2c8-135">시작 노드에 활동을 직접 연결하여 워크플로에서 해당 활동을 시작 활동으로 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-135">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="ac2c8-136">이 위해 위로 마우스를 이동 합니다 **시작** 노드를 마우스를 위로 가져갈 때 나타나는 사각형 중 하나를 클릭 합니다 **시작** 노드와 끌어서 원하는 활동 아래로 줄 연결 및 중 하나에 놓습니다 표시 되는 사각형입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-136">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="ac2c8-137">It를 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 시작 활동으로 활동을 지정할 수도 있습니다 **시작 노드로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-137">You can also designate an activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2. <span data-ttu-id="ac2c8-138">형식 `Target` 에 **에** 상자 및에 다음 식을 합니다 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-138">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="ac2c8-139">경우는 **도구 상자** 창이 표시 되지 않으면, 선택 **도구 상자** 에서 합니다 **뷰** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-139">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3. <span data-ttu-id="ac2c8-140">끌어서를 **프롬프트** 활동에서는 **NumberGuessWorkflowActivities** 섹션을 **도구 상자**, 아래에 놓습니다를 **할당** 활동 이전 단계와 연결 합니다 **프롬프트** 활동을 합니다 **할당** 활동.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="ac2c8-141">두 활동을 연결하는 방법에는 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-141">There are three ways to connect the two activities.</span></span> <span data-ttu-id="ac2c8-142">첫 번째 방법은 놓을 때 이들을 연결 하는 **프롬프트** 워크플로에서 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-142">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="ac2c8-143">끌 합니다 **프롬프트** 워크플로에 활동 위로 가져간 합니다 **할당** 활동 때 표시 되는 4 개의 삼각형 중 하나에 놓습니다를 **프롬프트** 통해 작업이 합니다 **할당** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-143">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="ac2c8-144">두 번째 방법은 삭제 하는 것을 **프롬프트** 활동을 워크플로의 원하는 위치에 놓으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-144">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="ac2c8-145">그런 다음 위로 마우스를 이동 합니다 **할당** 활동과 아래에 나타나는 사각형 중 하나를 끕니다를 **프롬프트** 활동.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-145">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="ac2c8-146">줄 연결 되도록 마우스를 끌고를 **할당** 활동의 사각형 중 하나에 연결 합니다 **프롬프트** 작업을 선택한 다음 마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-146">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="ac2c8-147">세 번째 방법은 끌어오는 방법 대신 한다는 점을 제외 하는 첫 번째 방법은 매우 비슷합니다는 **프롬프트** 에서 작업을 **도구 상자**, 워크플로 디자인 화면의 해당 위치에서 끌어, 합니다 위로가져간 **할당** 활동 나타나는 삼각형 중 하나에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-147">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4. <span data-ttu-id="ac2c8-148">에 **속성 창** 에 대 한 합니다 **프롬프트** 활동을 입력 `"EnterGuess"` 따옴표를 포함 하 여를 **BookmarkName** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-148">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="ac2c8-149">형식 `Guess` 에 **결과** 속성 값 상자 및에 다음 식을 입력 합니다 **텍스트** 속성 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-149">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="ac2c8-150">경우는 **속성 창** 표시를 선택 하지 않는 **속성 창** 에서 합니다 **뷰** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-150">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5. <span data-ttu-id="ac2c8-151">끌어서는 **할당** 활동에서를 **기본** 부분을 **도구 상자** 는아래에이전단계에서설명한방법중하나를사용하여연결 **프롬프트** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-151">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6. <span data-ttu-id="ac2c8-152">형식 `Turns` 에 **하** 상자 및 `Turns + 1` 에 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-152">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7. <span data-ttu-id="ac2c8-153">끌어서를 **FlowDecision** 에서 **순서도** 부분을 **도구 상자** 아래에 연결 합니다 **할당** 활동.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-153">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="ac2c8-154">에 **속성 창**에 다음 식을 입력 합니다 **조건** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-154">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. <span data-ttu-id="ac2c8-155">다른 끌어 **FlowDecision** 에서 활동을 **도구 상자** 첫 번째 아래에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-155">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="ac2c8-156">레이블이 있는 사각형을 끌어 두 활동을 연결 **False** 위쪽 **FlowDecision** 사각형 위쪽의 두 번째 작업 **FlowDecision**활동입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-156">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="ac2c8-157">표시 되지 않으면 합니다 **True** 및 **False** 레이블의 **FlowDecision**, 위로 마우스를 이동 합니다 **FlowDecision**.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-157">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="ac2c8-158">두 번째 **FlowDecision** 활동을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-158">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="ac2c8-159">에 **속성 창**에 다음 식을 입력 합니다 **조건** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-159">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
10. <span data-ttu-id="ac2c8-160">두 개 **WriteLine** 활동을를 **기본** 섹션을 **도구 상자** 두 아래 나란히 되도록 놓을 **FlowDecision**  활동입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-160">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="ac2c8-161">연결 된 **True** 아래쪽의 작업 **FlowDecision** 가장 왼쪽에 있는 작업 **WriteLine** 활동 및 **False** 작업을를 맨 오른쪽 **WriteLine** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-161">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="ac2c8-162">가장 왼쪽에 있는 클릭 **WriteLine** 활동을 선택한 후에 다음 식을 입력 합니다 **텍스트** 속성 값 상자에 **속성 창**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-162">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="ac2c8-163">연결 된 **WriteLine** 의 왼쪽에는 **프롬프트** 위에 있는 작업.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-163">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="ac2c8-164">맨 오른쪽 클릭 **WriteLine** 활동을 선택한 후에 다음 식을 입력 합니다 **텍스트** 속성 값 상자에 **속성 창**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-164">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="ac2c8-165">연결 합니다 **WriteLine** 활동의 오른쪽에는 **프롬프트** 활동 위에 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-165">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="ac2c8-166">다음 예제에서는 완료된 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-166">The following example illustrates the completed workflow.</span></span>  
  
     ![완료 된 Windows Workflow Foundation 순서도 보여 주는 다이어그램입니다.](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="ac2c8-168">워크플로를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="ac2c8-168">To build the workflow</span></span>  
  
1. <span data-ttu-id="ac2c8-169">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-169">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="ac2c8-170">워크플로 실행 하는 방법에 대 한 지침은 다음 항목을 참조 하십시오 [방법: 워크플로 실행](how-to-run-a-workflow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-170">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="ac2c8-171">이미 완료 하는 경우는 [방법: 워크플로 실행](how-to-run-a-workflow.md) 이 단계에서 순서도 워크플로 사용 하 여 실행 하려는 워크플로의 다른 스타일을 사용 하 여 단계를 건너 뛰 세요 합니다 [빌드 및 응용 프로그램을 실행 하려면](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 부분 [하는 방법: 워크플로 실행](how-to-run-a-workflow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac2c8-171">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2c8-172">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac2c8-172">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="ac2c8-173">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ac2c8-173">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="ac2c8-174">워크플로 디자인</span><span class="sxs-lookup"><span data-stu-id="ac2c8-174">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="ac2c8-175">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="ac2c8-175">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="ac2c8-176">방법: 활동 만들기</span><span class="sxs-lookup"><span data-stu-id="ac2c8-176">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="ac2c8-177">방법: 워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="ac2c8-177">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
