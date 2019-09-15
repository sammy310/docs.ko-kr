---
title: '방법: 여러 버전의 워크플로를 함께 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
ms.openlocfilehash: 820ed324c8095e2f9f2823513a37965099f42c48
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989640"
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a><span data-ttu-id="1cb58-102">방법: 여러 버전의 워크플로를 함께 호스팅</span><span class="sxs-lookup"><span data-stu-id="1cb58-102">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>

<span data-ttu-id="1cb58-103">`WorkflowIdentity`는 워크플로 애플리케이션 개발자에게 이름 및 버전을 워크플로 정의에 연결하는 방법을 제공하며, 이러한 정보는 지속형 워크플로 인스턴스와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-103">`WorkflowIdentity` provides a way for workflow application developers to associate a name and a version with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="1cb58-104">이 ID 정보는 워크플로 애플리케이션 개발자가 여러 버전의 워크플로 정의를 side-by-side로 실행하는 경우와 같은 시나리오를 가능하도록 하는 데 사용될 수 있으며 동적 업데이트와 같은 다른 기능의 토대를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="1cb58-105">자습서의 이 단계에서는 `WorkflowIdentity`를 사용하여 여러 버전의 워크플로를 동시에 호스트하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-105">This step in the tutorial demonstrates how to use `WorkflowIdentity` to host multiple versions of a workflow at the same time.</span></span>

> [!NOTE]
> <span data-ttu-id="1cb58-106">자습서의 전체 버전을 다운로드 하거나 비디오 연습을 보려면 [Windows Workflow Foundation (WF45)-초보자](https://go.microsoft.com/fwlink/?LinkID=248976)를 위한 자습서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1cb58-106">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="1cb58-107">항목 내용</span><span class="sxs-lookup"><span data-stu-id="1cb58-107">In this topic</span></span>

<span data-ttu-id="1cb58-108">자습서의 이 단계에서는 추가 정보를 제공하도록 워크플로의 `WriteLine` 활동을 수정하고 새 `WriteLine` 활동을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-108">In this step of the tutorial, the `WriteLine` activities in the workflow are modified to provide additional information, and a new `WriteLine` activity is added.</span></span> <span data-ttu-id="1cb58-109">원래 워크플로와 업데이트된 워크플로를 모두 동시에 실행할 수 있도록 원래 워크플로 어셈블리의 복사본을 저장하고 호스트 애플리케이션을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-109">A copy of the original workflow assembly is stored, and the host application is updated so that it can run both the original and the updated workflows at the same time.</span></span>

- [<span data-ttu-id="1cb58-110">NumberGuessWorkflowActivities 프로젝트의 복사본을 만들려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-110">To make a copy of the NumberGuessWorkflowActivities project</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)

- [<span data-ttu-id="1cb58-111">워크플로를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-111">To update the workflows</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)

  - [<span data-ttu-id="1cb58-112">StateMachine 워크플로를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-112">To update the StateMachine workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)

  - [<span data-ttu-id="1cb58-113">순서도 워크플로를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-113">To update the Flowchart workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)

  - [<span data-ttu-id="1cb58-114">순차 워크플로를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-114">To update the Sequential workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)

- [<span data-ttu-id="1cb58-115">이전 워크플로 버전을 포함 하도록 WorkflowVersionMap을 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-115">To update WorkflowVersionMap to include the previous workflow versions</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)

- [<span data-ttu-id="1cb58-116">응용 프로그램을 빌드하고 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-116">To build and run the application</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)

> [!NOTE]
> <span data-ttu-id="1cb58-117">이 항목의 단계를 수행하기 전에 애플리케이션을 실행하고 각 유형의 여러 워크플로를 시작한 후 각 워크플로마다 한두 개의 숫자를 추측하세요.</span><span class="sxs-lookup"><span data-stu-id="1cb58-117">Before following the steps in this topic, run the application, start several workflows of each type, and making one or two guesses for each one.</span></span> <span data-ttu-id="1cb58-118">이러한 지속형 워크플로는이 단계와 다음 단계 [에서 사용 됩니다. 실행 중인 워크플로 인스턴스의](how-to-update-the-definition-of-a-running-workflow-instance.md)정의를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-118">These persisted workflows are used in this step and the following step, [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1cb58-119">초보자를 위한 자습서의 각 단계는 이전 단계를 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-119">Each step in the Getting Started tutorial depends on the previous steps.</span></span> <span data-ttu-id="1cb58-120">이전 단계를 완료 하지 않은 경우 [Windows Workflow Foundation (WF45)-초보자](https://go.microsoft.com/fwlink/?LinkID=248976)를 위한 자습서에서 자습서의 전체 버전을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-120">If you did not complete the previous steps you can download a completed version of the tutorial from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

### <a name="BKMK_BackupCopy"></a><span data-ttu-id="1cb58-121">NumberGuessWorkflowActivities 프로젝트의 복사본을 만들려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-121">To make a copy of the NumberGuessWorkflowActivities project</span></span>

1. <span data-ttu-id="1cb58-122">Visual Studio 2012에서 **WF45GettingStartedTutorial** 솔루션을 엽니다 (열려 있지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="1cb58-122">Open the **WF45GettingStartedTutorial** solution in Visual Studio 2012 if it is not open.</span></span>

2. <span data-ttu-id="1cb58-123">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-123">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="1cb58-124">**WF45GettingStartedTutorial** 솔루션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-124">Close the **WF45GettingStartedTutorial** solution.</span></span>

4. <span data-ttu-id="1cb58-125">Windows 탐색기를 열고 및 자습서 솔루션 파일과 프로젝트 폴더가 있는 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-125">Open Windows Explorer and navigate to the folder where the tutorial solution file and the project folders are located.</span></span>

5. <span data-ttu-id="1cb58-126">**NumberGuessWorkflowHost** 및 **NumberGuessWorkflowActivities**와 동일한 폴더에 **PreviousVersions** 라는 새 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-126">Create a new folder named **PreviousVersions** in the same folder as **NumberGuessWorkflowHost** and **NumberGuessWorkflowActivities**.</span></span> <span data-ttu-id="1cb58-127">이 폴더는 이후 자습서 단계에서 사용되는 다른 버전의 워크플로가 포함된 어셈블리를 포함하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-127">This folder is used to contain the assemblies that contain the different versions of the workflows used in the subsequent tutorial steps.</span></span>

6. <span data-ttu-id="1cb58-128">**NumberGuessWorkflowActivities\bin\debug** 폴더 (또는 프로젝트 설정에 따라 **bin\release** )로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-128">Navigate to the **NumberGuessWorkflowActivities\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="1cb58-129">**NumberGuessWorkflowActivities** 을 복사 하 여 **PreviousVersions** 폴더에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-129">Copy **NumberGuessWorkflowActivities.dll** and paste it into the **PreviousVersions** folder.</span></span>

7. <span data-ttu-id="1cb58-130">**PreviousVersions** 폴더의 **NumberGuessWorkflowActivities** 를 **NumberGuessWorkflowActivities_v1**로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-130">Rename **NumberGuessWorkflowActivities.dll** in the **PreviousVersions** folder to **NumberGuessWorkflowActivities_v1.dll**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1cb58-131">이 항목의 단계에서는 여러 버전의 워크플로를 포함하는 데 사용되는 어셈블리를 관리하는 한 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-131">The steps in this topic demonstrate one way to manage the assemblies used to contain multiple versions of the workflows.</span></span> <span data-ttu-id="1cb58-132">어셈블리에 강력한 이름을 지정하거나 어셈블리를 전역 어셈블리 캐시에 등록하는 등의 다른 방법을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-132">Other methods such as strong naming the assemblies and registering them in the global assembly cache could also be used.</span></span>

8. <span data-ttu-id="1cb58-133">**NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**및 새로 추가 된 **PreviousVersions** 폴더와 동일한 폴더에 **NumberGuessWorkflowActivities_du** 라는 새 폴더를 만들고 모든 파일을 복사 합니다. **NumberGuessWorkflowActivities** 폴더의 하위 폴더를 새 **NumberGuessWorkflowActivities_du** 폴더로 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-133">Create a new folder named **NumberGuessWorkflowActivities_du** in the same folder as **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, and the newly added **PreviousVersions** folder, and copy all of the files and subfolders from the **NumberGuessWorkflowActivities** folder into the new **NumberGuessWorkflowActivities_du** folder.</span></span> <span data-ttu-id="1cb58-134">활동의 초기 버전에 대 한 프로젝트의이 백업 복사본은 다음 [방법으로 사용 됩니다. 실행 중인 워크플로 인스턴스의](how-to-update-the-definition-of-a-running-workflow-instance.md)정의를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-134">This backup copy of the project for the initial version of the activities is used in [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>

9. <span data-ttu-id="1cb58-135">Visual Studio 2012에서 **WF45GettingStartedTutorial** 솔루션을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-135">Re-open the **WF45GettingStartedTutorial** solution in Visual Studio 2012.</span></span>

### <a name="BKMK_UpdateWorkflows"></a><span data-ttu-id="1cb58-136">워크플로를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-136">To update the workflows</span></span>

<span data-ttu-id="1cb58-137">이 단원에서는 워크플로 정의를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-137">In this section, the workflow definitions are updated.</span></span> <span data-ttu-id="1cb58-138">즉, 사용자의 추측에 대한 피드백을 제공하는 두 개의 `WriteLine` 활동을 업데이트하고, 숫자가 추측된 후 게임에 대한 추가 정보를 제공하는 새로운 `WriteLine` 활동을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-138">The two `WriteLine` activities that give feedback on the user's guess are updated, and a new `WriteLine` activity is added that provides additional information about the game once the number is guessed.</span></span>

#### <a name="BKMK_UpdateStateMachine"></a><span data-ttu-id="1cb58-139">StateMachine 워크플로를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-139">To update the StateMachine workflow</span></span>

1. <span data-ttu-id="1cb58-140">**솔루션 탐색기**의 **NumberGuessWorkflowActivities** 프로젝트에서 **statemachinenumberguessworkflow.xaml**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-140">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **StateMachineNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="1cb58-141">상태 시스템의 **추측 잘못** 된 전환을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-141">Double-click the **Guess Incorrect** transition on the state machine.</span></span>

3. <span data-ttu-id="1cb58-142">`Text` 활동에서 맨 왼쪽 `WriteLine`의 `If`를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-142">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

4. <span data-ttu-id="1cb58-143">`Text` 활동에서 맨 오른쪽 `WriteLine`의 `If`를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-143">Update the `Text` of the right-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

5. <span data-ttu-id="1cb58-144">Workflow designer 위쪽의 이동 경로 표시에서 **StateMachine** 을 클릭 하 여 workflow designer의 전체 상태 시스템 뷰로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-144">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>

6. <span data-ttu-id="1cb58-145">상태 시스템에서 **추측 올바른** 전환을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-145">Double-click the **Guess Correct** transition on the state machine.</span></span>

7. <span data-ttu-id="1cb58-146">**도구 상자** 의 **기본 형식** 섹션에서 **WriteLine** 활동을 끌어 전환의 **작업 활동 삭제** 레이블에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-146">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the **Drop Action activity here** label of the transition.</span></span>

8. <span data-ttu-id="1cb58-147">`Text` 속성 상자에 다음 식을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-147">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="BKMK_UpdateFlowchart"></a><span data-ttu-id="1cb58-148">순서도 워크플로를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-148">To update the Flowchart workflow</span></span>

1. <span data-ttu-id="1cb58-149">**솔루션 탐색기**의 **NumberGuessWorkflowActivities** 프로젝트에서 **flowchartnumberguessworkflow.xaml**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-149">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **FlowchartNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="1cb58-150">맨 왼쪽 `Text` 활동의 `WriteLine`를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-150">Update the `Text` of the left-most `WriteLine` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. <span data-ttu-id="1cb58-151">맨 오른쪽 `Text` 활동의 `WriteLine`를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-151">Update the `Text` of the right-most `WriteLine` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. <span data-ttu-id="1cb58-152">**도구 상자** `True` 의 **기본 형식** 섹션에서 **WriteLine** 활동을 끌어 맨 위에 `FlowDecision`있는 동작의 드롭 지점에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the drop point of the `True` action of the topmost `FlowDecision`.</span></span> <span data-ttu-id="1cb58-153">`WriteLine` 활동이 순서도에 추가되고 `True`의 `FlowDecision` 동작에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-153">The `WriteLine` activity is added to the flowchart and linked to the `True` action of the `FlowDecision`.</span></span>

5. <span data-ttu-id="1cb58-154">`Text` 속성 상자에 다음 식을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-154">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="BKMK_UpdateSequential"></a><span data-ttu-id="1cb58-155">순차 워크플로를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-155">To update the Sequential workflow</span></span>

1. <span data-ttu-id="1cb58-156">**솔루션 탐색기**의 **NumberGuessWorkflowActivities** 프로젝트에서 **sequentialnumberguessworkflow.xaml**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-156">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **SequentialNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="1cb58-157">`Text` 활동에서 맨 왼쪽 `WriteLine`의 `If`를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-157">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. <span data-ttu-id="1cb58-158">`Text` 활동에서 맨 오른쪽 `WriteLine` 활동의 `If`를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-158">Update the `Text` of the right-most `WriteLine` activity in the `If` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. <span data-ttu-id="1cb58-159">**도구 상자** 의 **기본 형식** 섹션에서 **writeline** 활동을 끌어 **DoWhile** 활동 뒤에 놓습니다. 그러면 **writeline** 이 루트 `Sequence` 활동의 최종 활동이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-159">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it after the **DoWhile** activity so that the **WriteLine** is the final activity in the root `Sequence` activity.</span></span>

5. <span data-ttu-id="1cb58-160">`Text` 속성 상자에 다음 식을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-160">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

### <a name="BKMK_UpdateWorkflowVersionMap"></a><span data-ttu-id="1cb58-161">이전 워크플로 버전을 포함 하도록 WorkflowVersionMap을 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-161">To update WorkflowVersionMap to include the previous workflow versions</span></span>

1. <span data-ttu-id="1cb58-162">**NumberGuessWorkflowHost** 프로젝트에서 **WorkflowVersionMap.cs** (또는 **workflowversionmap .vb**)를 두 번 클릭 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-162">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>

2. <span data-ttu-id="1cb58-163">다음 `using`(또는 `Imports`) 문을 파일의 맨 위에 다른 `using`(또는 `Imports`) 문과 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-163">Add the following `using` (or `Imports`) statements to the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Reflection
    Imports System.IO
    ```

    ```csharp
    using System.Reflection;
    using System.IO;
    ```

3. <span data-ttu-id="1cb58-164">세 개의 기존 워크플로 ID 선언 바로 아래에 세 개의 새 워크플로 ID를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-164">Add three new workflow identities just below the three existing workflow identity declarations.</span></span> <span data-ttu-id="1cb58-165">이러한 새 `v1` 워크플로 ID는 업데이트가 수행되기 전에 시작된 워크플로에 올바른 워크플로 정의를 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-165">These new `v1` workflow identities will be used provide the correct workflow definition to workflows started before the updates were made.</span></span>

    ```vb
    'Current version identities.
    Public StateMachineNumberGuessIdentity As WorkflowIdentity
    Public FlowchartNumberGuessIdentity As WorkflowIdentity
    Public SequentialNumberGuessIdentity As WorkflowIdentity

    'v1 Identities.
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity
    ```

    ```csharp
    // Current version identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity;
    static public WorkflowIdentity FlowchartNumberGuessIdentity;
    static public WorkflowIdentity SequentialNumberGuessIdentity;

    // v1 identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;
    ```

4. <span data-ttu-id="1cb58-166">`WorkflowVersionMap` 생성자에서 현재 워크플로 ID 세 개의 `Version` 속성을 `2.0.0.0`으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-166">In the `WorkflowVersionMap` constructor, update the `Version` property of the three current workflow identities to `2.0.0.0`.</span></span>

    ```vb
    'Add the current workflow version identities.
    StateMachineNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    FlowchartNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    SequentialNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
    map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
    map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())
    ```

    ```csharp
    // Add the current workflow version identities.
    StateMachineNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    FlowchartNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    SequentialNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
    map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
    map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());
    ```

    <span data-ttu-id="1cb58-167">사전에 현재 버전의 워크플로를 추가하는 코드에서는 프로젝트에서 참조되는 현재 버전을 사용하므로 워크플로 정의를 초기화하는 코드를 업데이트할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-167">The code in that adds the current versions of the workflows to the dictionary uses the current versions that are referenced in the project, so the code that initializes the workflow definitions does not need to be updated.</span></span>

5. <span data-ttu-id="1cb58-168">생성자에서 사전에 현재 버전을 추가하는 코드 바로 뒤에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-168">Add the following code in the constructor just after the code that adds the current versions to the dictionary.</span></span>

    ```vb
    'Initialize the previous workflow version identities.
    StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }

    FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }

    SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }
    ```

    ```csharp
    // Initialize the previous workflow version identities.
    StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };

    FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };

    SequentialNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };
    ```

    <span data-ttu-id="1cb58-169">이러한 워크플로 ID는 해당 워크플로 정의의 초기 버전과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-169">These workflow identities are associated with the initial versions of the corresponding workflow definitions.</span></span>

6. <span data-ttu-id="1cb58-170">다음에는 워크플로 정의의 초기 버전이 포함된 어셈블리를 로드하고 해당 워크플로 정의를 만들어 사전에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-170">Next, load the assembly that contains the initial version of the workflow definitions, and create and add the corresponding workflow definitions to the dictionary.</span></span>

    ```vb
    'Add the previous version workflow identities to the dictionary along with
    'the corresponding workflow definitions loaded from the v1 assembly.
    'Assembly.LoadFile requires an absolute path so convert this relative path
    'to an absolute path.
    Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)
    Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)

    map.Add(StateMachineNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

    map.Add(SequentialNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

    map.Add(FlowchartNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
    ```

    ```csharp
    // Add the previous version workflow identities to the dictionary along with
    // the corresponding workflow definitions loaded from the v1 assembly.
    // Assembly.LoadFile requires an absolute path so convert this relative path
    // to an absolute path.
    string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);
    Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);

    map.Add(StateMachineNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

    map.Add(SequentialNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

    map.Add(FlowchartNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
    ```

    <span data-ttu-id="1cb58-171">다음 예제에서는 업데이트된 전체 `WorkflowVersionMap` 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-171">The following example is the complete listing for the updated `WorkflowVersionMap` class.</span></span>

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        'Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        'v1 Identities.
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            'Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())

            'Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            'Add the previous version workflow identities to the dictionary along with
            'the corresponding workflow definitions loaded from the v1 assembly.
            'Assembly.LoadFile requires an absolute path so convert this relative path
            'to an absolute path.
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
        End Sub

        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity
            Return map(identity)
        End Function

        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String
            Return identity.ToString()
        End Function
    End Module
    ```

    ```csharp
    public static class WorkflowVersionMap
    {
        static Dictionary<WorkflowIdentity, Activity> map;

        // Current version identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity;
        static public WorkflowIdentity FlowchartNumberGuessIdentity;
        static public WorkflowIdentity SequentialNumberGuessIdentity;

        // v1 identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());

            // Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            // Add the previous version workflow identities to the dictionary along with
            // the corresponding workflow definitions loaded from the v1 assembly.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
        }

        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)
        {
            return map[identity];
        }

        public static string GetIdentityDescription(WorkflowIdentity identity)
        {
            return identity.ToString();
        }
    }
    ```

### <a name="BKMK_BuildAndRun"></a> <span data-ttu-id="1cb58-172">응용 프로그램을 빌드하고 실행하려면</span><span class="sxs-lookup"><span data-stu-id="1cb58-172">To build and run the application</span></span>

1. <span data-ttu-id="1cb58-173">Ctrl+Shift+B를 눌러 애플리케이션을 빌드하고 Ctrl+F5를 눌러 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-173">Press CTRL+SHIFT+B to build the application, and then CTRL+F5 to start.</span></span>

2. <span data-ttu-id="1cb58-174">**새 게임**을 클릭 하 여 새 워크플로를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-174">Start a new workflow by clicking **New Game**.</span></span> <span data-ttu-id="1cb58-175">워크플로의 버전이 상태 창에 표시되고 연결된 `WorkflowIdentity`에서 업데이트된 버전이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-175">The version of the workflow is displayed under the status window and reflects the updated version from the associated `WorkflowIdentity`.</span></span> <span data-ttu-id="1cb58-176">완료 시 워크플로 추적 파일을 볼 수 있도록 `InstanceId`를 적어 두고 게임이 완료될 때까지 추측 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-176">Make a note of the `InstanceId` so you can view the tracking file for the workflow when it completes, and then enter guesses until the game is complete.</span></span> <span data-ttu-id="1cb58-177">상태 창에 표시된 정보에 사용자의 추측 값이 나타나는 방식은 `WriteLine` 활동에 대한 업데이트에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-177">Note how the user's guess is displayed in the information displayed in the status window based on the updates to the `WriteLine` activities.</span></span>

    ```console
    Please enter a number between 1 and 10
    5 is too high.
    Please enter a number between 1 and 10
    3 is too high.
    Please enter a number between 1 and 10
    1 is too low.
    Please enter a number between 1 and 10
    Congratulations, you guessed the number in 4 turns.
    ```

    > [!NOTE]
    > <span data-ttu-id="1cb58-178">`WriteLine` 활동에서 업데이트된 텍스트는 표시되지만 이 항목에서 추가된 최종 `WriteLine` 활동의 출력은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-178">The updated text from the `WriteLine` activities is displayed, but the output of the final `WriteLine` activity that was added in this topic is not.</span></span> <span data-ttu-id="1cb58-179">상태 창은 `PersistableIdle` 처리기에 의해 업데이트되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-179">That is because the status window is updated by the `PersistableIdle` handler.</span></span> <span data-ttu-id="1cb58-180">워크플로는 완료 및 최종 활동 후에도 유휴 상태가 되지 않으므로 `PersistableIdle` 처리기가 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-180">Because the workflow completes and does not go idle after the final activity, the `PersistableIdle` handler is not called.</span></span> <span data-ttu-id="1cb58-181">그러나 `Completed` 처리기에 의해 유사한 메시지가 상태 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-181">However, a similar message is displayed in the status window by the `Completed` handler.</span></span> <span data-ttu-id="1cb58-182">필요한 경우 `Completed`에서 텍스트를 추출하여 상태 창에 표시하도록 `StringWriter` 처리기에 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-182">If desired, code could be added to the `Completed` handler to extract the text from the `StringWriter` and display it to the status window.</span></span>

3. <span data-ttu-id="1cb58-183">Windows 탐색기를 열고 **NumberGuessWorkflowHost\bin\debug** 폴더 (또는 프로젝트 설정에 따라 **bin\release** )로 이동 하 여 완료 된 워크플로에 해당 하는 메모장을 사용 하 여 추적 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-183">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="1cb58-184">을 적어 `InstanceId`둔 경우 Windows 탐색기에서 **수정한 날짜** 정보를 사용 하 여 올바른 추적 파일을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-184">If you did not make a note of the `InstanceId`, you can identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span>

    ```console
    Please enter a number between 1 and 10
    5 is too high.
    Please enter a number between 1 and 10
    3 is too high.
    Please enter a number between 1 and 10
    1 is too low.
    Please enter a number between 1 and 10
    2 is correct. You guessed it in 4 turns.
    ```

    <span data-ttu-id="1cb58-185">이 항목에서 추가된 `WriteLine`의 출력을 포함하여 업데이트된 `WriteLine` 출력이 추적 파일 내에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-185">The updated `WriteLine` output is contained within the tracking file, including the output of the `WriteLine` that was added in this topic.</span></span>

4. <span data-ttu-id="1cb58-186">다시 숫자 추측 애플리케이션으로 전환하고 업데이트를 수행하기 전에 시작된 워크플로 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-186">Switch back to the number guessing application and select one of the workflows that was started before the updates were made.</span></span> <span data-ttu-id="1cb58-187">상태 창 아래에 표시된 버전 정보를 확인하여 현재 선택된 워크플로의 버전을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-187">You can identify the version of the currently selected workflow by looking at the version information that is displayed below the status window.</span></span> <span data-ttu-id="1cb58-188">몇 개의 추측 값을 입력한 후, 상태 업데이트가 이전 버전의 `WriteLine` 활동 출력과 일치하며 사용자의 추측 값을 포함하지 않음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-188">Enter some guesses and note that the status updates match the `WriteLine` activity output from the previous version, and do not include the user's guess.</span></span> <span data-ttu-id="1cb58-189">이는 이러한 워크플로가 `WriteLine` 업데이트가 없는 이전 워크플로 정의를 사용하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-189">That is because these workflows are using the previous workflow definition that does not have the `WriteLine` updates.</span></span>

    <span data-ttu-id="1cb58-190">다음 단계 [에서 방법: 실행 중인 워크플로 인스턴스의](how-to-update-the-definition-of-a-running-workflow-instance.md)정의를 업데이트 합니다. 실행 중인 `v1` 워크플로 인스턴스는 새 기능 `v2` 을 인스턴스로 포함 하도록 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb58-190">In the next step, [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md), the running `v1` workflow instances are updated so they contain the new functionality as the `v2` instances.</span></span>
