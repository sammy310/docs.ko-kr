---
title: '방법: 순서도 워크플로 만들기'
description: 이 문서에서는 기본 제공 활동과 이전 아티클의 사용자 지정 활동을 모두 사용 하는 워크플로를 만드는 방법을 설명 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: 6b3fa423200f5c5cfece60f07372ce9678fc0072
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419709"
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="da373-103">방법: 순서도 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="da373-103">How to: Create a Flowchart Workflow</span></span>
<span data-ttu-id="da373-104">기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="da373-105">이 항목에서는 활동과 같은 기본 제공 활동과 <xref:System.Activities.Statements.Flowchart> 이전 [방법: 활동 만들기](how-to-create-an-activity.md) 항목의 사용자 지정 활동을 모두 사용 하는 워크플로를 만드는 과정을 단계별로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="da373-106">이 워크플로는 숫자 추측 게임을 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-106">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da373-107">초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="da373-108">이 항목을 완료 하려면 먼저 [방법: 작업 만들기](how-to-create-an-activity.md)를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da373-109">자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](https://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da373-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="da373-110">워크플로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="da373-110">To create the workflow</span></span>  
  
1. <span data-ttu-id="da373-111">**솔루션 탐색기** 에서 **NumberGuessWorkflowActivities** 을 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 항목**을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-111">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="da373-112">**설치 됨**, **공통 항목** 노드에서 **워크플로**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-112">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="da373-113">**워크플로** 목록에서 **작업**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-113">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="da373-114">`FlowchartNumberGuessWorkflow` **이름** 상자에를 입력 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-114">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="da373-115">**도구 상자** 의 **순서도** 섹션에서 **순서도** 활동을 끌어 워크플로 디자인 화면의 **여기에 작업 놓기** 레이블에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-115">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="da373-116">워크플로 변수와 인수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="da373-116">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="da373-117">**솔루션 탐색기** 에서 **flowchartnumberguessworkflow.xaml** 를 두 번 클릭 하 여 디자이너에 워크플로를 표시 합니다 (아직 표시 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="da373-117">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="da373-118">워크플로 디자이너 왼쪽 아래에 있는 **인수** 를 클릭 하 여 **인수** 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-118">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="da373-119">**인수 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-119">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="da373-120">`MaxNumber` **이름** 상자에를 입력 하 고 **방향** 드롭다운 목록 **에서 시작을** 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32** 를 선택 하 고 enter 키를 눌러 인수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-120">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="da373-121">**인수 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-121">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="da373-122">`Turns`새로 추가 된 인수 아래에 있는 **이름** 상자에를 입력 `MaxNumber` 하 고 **방향** 드롭다운 목록에서 **바깥쪽** 을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32** 를 선택 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="da373-122">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="da373-123">활동 디자이너의 왼쪽 아래에 있는 **인수**를 클릭하여 **인수** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-123">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="da373-124">워크플로 디자이너 왼쪽 아래에 있는 **변수** 를 클릭 하 여 **변수** 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-124">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="da373-125">**변수 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-125">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="da373-126">**변수 만들기** 상자가 표시 되지 않으면 <xref:System.Activities.Statements.Flowchart> workflow designer 화면에서 활동을 클릭 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-126">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="da373-127">`Guess` **이름** 상자에를 입력 하 고 **변수 형식** 드롭다운 목록에서 **Int32** 를 선택한 다음 enter 키를 눌러 변수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-127">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="da373-128">**변수 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-128">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="da373-129">`Target` **이름** 상자에를 입력 하 고 **변수 형식** 드롭다운 목록에서 **Int32** 를 선택한 다음 enter 키를 눌러 변수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-129">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="da373-130">활동 디자이너의 왼쪽 아래에 있는 **변수**를 클릭하여 **변수** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-130">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="da373-131">워크플로 활동을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="da373-131">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="da373-132">**도구 상자** 의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 순서도의 맨 위에 있는 **시작** 노드 위로 가져갑니다.</span><span class="sxs-lookup"><span data-stu-id="da373-132">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="da373-133">**Assign** 활동이 **시작** 노드 위에 있으면 3 개의 삼각형이 **시작** 노드 주위에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da373-133">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="da373-134">**시작** 노드 바로 아래에 있는 삼각형에서 **Assign** 활동을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-134">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="da373-135">이렇게 하면 두 항목을 함께 연결 하 고 **할당** 작업을 순서도의 첫 번째 작업으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-135">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="da373-136">시작 노드에 활동을 직접 연결하여 워크플로에서 해당 활동을 시작 활동으로 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-136">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="da373-137">이렇게 하려면 마우스를 **시작** 노드 위로 가져가서 마우스가 **시작** 노드 위에 있을 때 나타나는 사각형 중 하나를 클릭 하 고 연결 하는 줄을 원하는 활동으로 끌어 표시 되는 사각형 중 하나에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-137">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="da373-138">활동을 마우스 오른쪽 단추로 클릭 하 고 **시작 노드로 설정**을 선택 하 여 활동을 시작 활동으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-138">You can also designate an activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2. <span data-ttu-id="da373-139">`Target`To 상자에 **를** 입력 하 고 **c # 식 입력** 또는 **VB 식 입력** 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-139">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="da373-140">**도구 상자** 창이 표시되지 않으면 **보기** 메뉴에서 **도구 상자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-140">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3. <span data-ttu-id="da373-141">**도구 상자**의 **NumberGuessWorkflowActivities** 섹션에서 **prompt** 활동을 끌어 이전 단계의 **assign** 활동 아래에 놓고 **prompt** 활동을 **assign** 활동에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-141">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="da373-142">두 활동을 연결하는 방법에는 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-142">There are three ways to connect the two activities.</span></span> <span data-ttu-id="da373-143">첫 번째 방법은 워크플로에 **프롬프트** 활동을 놓을 때 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="da373-143">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="da373-144">**프롬프트** 활동을 워크플로로 끌어 오면 **assign** 활동 위로 마우스를 가져간 다음 **assign** 활동을 통해 **프롬프트** 활동이 있을 때 표시 되는 네 개의 삼각형 중 하나에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-144">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="da373-145">두 번째 방법은 **프롬프트** 활동을 원하는 위치에 워크플로로 놓는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="da373-145">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="da373-146">그런 다음 **Assign** 활동 위로 마우스를 이동 하 고 표시 되는 사각형 중 하나를 **Prompt** 활동으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="da373-146">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="da373-147">**Assign** 활동의 연결 선이 **Prompt** 활동의 사각형 중 하나에 연결 되도록 마우스를 끌고 마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-147">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="da373-148">세 번째 방법은 첫 번째 방법과 매우 유사 합니다. 단, **도구 상자**에서 **Prompt** 활동을 끄는 대신 워크플로 디자인 화면의 해당 위치에서 해당 활동을 끌어서 **Assign** 활동 위로 가져간 다음 표시 되는 삼각형 중 하나에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-148">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4. <span data-ttu-id="da373-149">**Prompt** 활동의 **속성 창** 에서 `"EnterGuess"` **BookmarkName** 속성 값 상자에 따옴표를 포함 하 여을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-149">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="da373-150">`Guess` **결과** 속성 값 상자에를 입력 하 고 **텍스트** 속성 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-150">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="da373-151">**속성 창이** 표시 되지 않으면 **보기** 메뉴에서 **속성 창** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-151">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5. <span data-ttu-id="da373-152">**도구 상자** 의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 **Prompt** 활동 아래에 오도록 이전 단계에서 설명한 방법 중 하나를 사용 하 여 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-152">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6. <span data-ttu-id="da373-153">`Turns`To box에 **를** 입력 하 고 `Turns + 1` **c # 식 입력** 또는 **VB 식 입력** 상자에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-153">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7. <span data-ttu-id="da373-154">**도구 상자** 의 **순서도** 섹션에서 **Flowdecision 결정** 을 끌어 **Assign** 활동 아래에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-154">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="da373-155">**속성 창의** **Condition** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-155">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. <span data-ttu-id="da373-156">**도구 상자** 에서 다른 **flowdecision 결정** 활동을 끌어 첫 번째 활동 아래에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-156">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="da373-157">위쪽 **Flowdecision 결정** 활동에서 **False** 로 레이블이 지정 된 사각형에서 두 번째 **flowdecision 결정** 활동의 맨 위에 있는 사각형으로 끌어 두 활동을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-157">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="da373-158">**Flowdecision 결정**에 **True** 및 **False** 레이블이 표시 되지 않으면 **flowdecision 결정**위로 마우스를 가져갑니다.</span><span class="sxs-lookup"><span data-stu-id="da373-158">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="da373-159">두 번째 **Flowdecision 결정** 활동을 클릭 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-159">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="da373-160">**속성 창의** **Condition** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-160">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
10. <span data-ttu-id="da373-161">**도구 상자** 의 **기본 형식** 섹션에서 두 **WriteLine** 활동을 끌어 두 **flowdecision 결정** 활동 아래에 나란히 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="da373-161">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="da373-162">최하위 **Flowdecision 결정** 활동의 **진정한** 동작을 가장 왼쪽의 **writeline** 활동에 연결 하 고 **False** 동작을 가장 오른쪽의 **writeline** 활동에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-162">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="da373-163">가장 왼쪽의 **WriteLine** 활동을 클릭 하 여 선택 하 고 **속성 창의** **텍스트** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-163">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="da373-164">**WriteLine** 을 위에 있는 **프롬프트** 활동의 왼쪽에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-164">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="da373-165">가장 오른쪽의 **WriteLine** 활동을 클릭 하 여 선택 하 고 **속성 창의** **텍스트** 속성 값 상자에 다음 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-165">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="da373-166">위의 **Prompt** 활동 오른쪽에 **WriteLine** 활동을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-166">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="da373-167">다음 예제에서는 완료된 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da373-167">The following example illustrates the completed workflow.</span></span>  
  
     ![완료 된 Windows Workflow Foundation 순서도를 표시 하는 다이어그램입니다.](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="da373-169">워크플로를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="da373-169">To build the workflow</span></span>  
  
1. <span data-ttu-id="da373-170">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="da373-170">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="da373-171">워크플로를 실행 하는 방법에 대 한 지침은 다음 항목인 [방법: 워크플로 실행](how-to-run-a-workflow.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da373-171">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="da373-172">[방법:](how-to-run-a-workflow.md) 워크플로의 다른 스타일을 사용 하 여 워크플로 단계 실행을 이미 완료 했 고이 단계에서 순서도 워크플로를 사용 하 여 실행 하려는 경우 [방법: 워크플로 실행](how-to-run-a-workflow.md)의 [응용 프로그램 섹션을 빌드하고 실행](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 하려면로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="da373-172">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da373-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da373-173">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="da373-174">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="da373-174">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="da373-175">워크플로 디자인</span><span class="sxs-lookup"><span data-stu-id="da373-175">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="da373-176">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="da373-176">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="da373-177">방법: 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="da373-177">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="da373-178">방법: 워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="da373-178">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
