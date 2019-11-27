---
title: 장기 실행 워크플로를 만들고 실행 하는 방법
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0043c89-2192-43c9-986d-3ecec4dd8c9c
ms.openlocfilehash: 10eb4e2947bed9cea89f1cda05272aa3fa0fadaa
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204889"
---
# <a name="how-to-create-and-run-a-long-running-workflow"></a><span data-ttu-id="9d6e2-102">장기 실행 워크플로를 만들고 실행 하는 방법</span><span class="sxs-lookup"><span data-stu-id="9d6e2-102">How to create and run a long-running workflow</span></span>

<span data-ttu-id="9d6e2-103">WF (Windows Workflow Foundation)의 중앙 기능 중 하나는 유휴 워크플로를 데이터베이스에 유지 하 고 언로드하는 런타임 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-103">One of the central features of Windows Workflow Foundation (WF) is the runtime’s ability to persist and unload idle workflows to a database.</span></span> <span data-ttu-id="9d6e2-104">[방법: 워크플로 실행](how-to-run-a-workflow.md) 의 단계에서는 콘솔 응용 프로그램을 사용 하 여 워크플로를 호스트 하는 기본 사항을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-104">The steps in [How to: Run a Workflow](how-to-run-a-workflow.md) demonstrated the basics of workflow hosting using a console application.</span></span> <span data-ttu-id="9d6e2-105">예제에서는 워크플로 시작 방법, 워크플로 수명 주기 처리기 및 책갈피 다시 시작 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-105">Examples were shown of starting workflows, workflow lifecycle handlers, and resuming bookmarks.</span></span> <span data-ttu-id="9d6e2-106">워크플로 지속성을 효과적으로 보여 주기 위해서는 여러 워크플로 인스턴스의 시작 및 다시 시작을 지원하는 좀 더 복잡한 워크플로 호스트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-106">In order to demonstrate workflow persistence effectively, a more complex workflow host is required that supports starting and resuming multiple workflow instances.</span></span> <span data-ttu-id="9d6e2-107">자습서의 이 단계에서는 여러 워크플로 인스턴스의 시작 및 다시 시작과 워크플로 지속성을 지원하는 Windows Form 호스트 애플리케이션을 만드는 방법을 보여 주고, 이후 자습서 단계에서 설명하는 추적 및 버전 관리 등의 고급 기능에 대한 기본 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-107">This step in the tutorial demonstrates how to create a Windows form host application that supports starting and resuming multiple workflow instances, workflow persistence, and provides a basis for the advanced features such as tracking and versioning that are demonstrated in subsequent tutorial steps.</span></span>

> [!NOTE]
> <span data-ttu-id="9d6e2-108">이 자습서 단계와 이후 단계에서는 [방법: 워크플로 만들기](how-to-create-a-workflow.md)의 세 가지 워크플로 유형을 모두 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-108">This tutorial step and the subsequent steps use all three workflow types from [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span> <span data-ttu-id="9d6e2-109">세 가지 유형을 모두 완료 하지 않은 경우 [Windows Workflow Foundation (WF45)-초보자](https://go.microsoft.com/fwlink/?LinkID=248976)를 위한 자습서에서 완료 된 버전의 단계를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-109">If you did not complete all three types you can download a completed version of the steps from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

> [!NOTE]
> <span data-ttu-id="9d6e2-110">자습서의 전체 버전을 다운로드 하거나 비디오 연습을 보려면 [Windows Workflow Foundation (WF45)-초보자](https://go.microsoft.com/fwlink/?LinkID=248976)를 위한 자습서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-110">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="to-create-the-persistence-database"></a><span data-ttu-id="9d6e2-111">지속성 데이터베이스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9d6e2-111">To create the persistence database</span></span>

1. <span data-ttu-id="9d6e2-112">SQL Server Management Studio를 열고 로컬 서버에 연결 합니다 (예: **.\SQLEXPRESS**).</span><span class="sxs-lookup"><span data-stu-id="9d6e2-112">Open SQL Server Management Studio and connect to the local server, for example **.\SQLEXPRESS**.</span></span> <span data-ttu-id="9d6e2-113">로컬 서버에서 **데이터베이스** 노드를 마우스 오른쪽 단추로 클릭 하 고 **새 데이터베이스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-113">Right-click the **Databases** node on the local server, and select **New Database**.</span></span> <span data-ttu-id="9d6e2-114">새 데이터베이스의 이름을 **WF45GettingStartedTutorial**, 다른 모든 값을 그대로 적용 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-114">Name the new database **WF45GettingStartedTutorial**, accept all other values, and select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9d6e2-115">데이터베이스를 만들기 전에 로컬 서버에 대 한 **Create Database** 권한이 있는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-115">Ensure that you have **Create Database** permission on the local server before creating the database.</span></span>

2. <span data-ttu-id="9d6e2-116">**파일** 메뉴에서 **열기**, **파일** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-116">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="9d6e2-117">다음 폴더를 찾습니다. *C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en*</span><span class="sxs-lookup"><span data-stu-id="9d6e2-117">Browse to the following folder: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en*</span></span>

    <span data-ttu-id="9d6e2-118">다음 두 파일을 선택 하 고 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-118">Select the following two files and click **Open**.</span></span>

    - <span data-ttu-id="9d6e2-119">*Sqlworkflowinstancestorelogic.sql*</span><span class="sxs-lookup"><span data-stu-id="9d6e2-119">*SqlWorkflowInstanceStoreLogic.sql*</span></span>

    - <span data-ttu-id="9d6e2-120">*Sqlworkflowinstancestoreschema.sql*</span><span class="sxs-lookup"><span data-stu-id="9d6e2-120">*SqlWorkflowInstanceStoreSchema.sql*</span></span>

3. <span data-ttu-id="9d6e2-121">**창** 메뉴에서 **sqlworkflowinstancestoreschema.sql** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-121">Choose **SqlWorkflowInstanceStoreSchema.sql** from the **Window** menu.</span></span> <span data-ttu-id="9d6e2-122">**사용 가능한 데이터베이스** 드롭다운에서 **WF45GettingStartedTutorial** 이 선택 되어 있는지 확인 하 고 **쿼리** 메뉴에서 **실행** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-122">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>

4. <span data-ttu-id="9d6e2-123">**창** 메뉴에서 **sqlworkflowinstancestorelogic.sql** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-123">Choose **SqlWorkflowInstanceStoreLogic.sql** from the **Window** menu.</span></span> <span data-ttu-id="9d6e2-124">**사용 가능한 데이터베이스** 드롭다운에서 **WF45GettingStartedTutorial** 이 선택 되어 있는지 확인 하 고 **쿼리** 메뉴에서 **실행** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-124">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>

    > [!WARNING]
    > <span data-ttu-id="9d6e2-125">앞의 두 단계는 올바른 순서대로 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-125">It is important to perform the previous two steps in the correct order.</span></span> <span data-ttu-id="9d6e2-126">쿼리를 순서에 맞지 않게 실행하면 오류가 발생하고 지속성 데이터베이스가 올바르게 구성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-126">If the queries are executed out of order, errors occur and the persistence database is not configured correctly.</span></span>

## <a name="to-add-the-reference-to-the-durableinstancing-assemblies"></a><span data-ttu-id="9d6e2-127">DurableInstancing 어셈블리에 대한 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="9d6e2-127">To add the reference to the DurableInstancing assemblies</span></span>

1. <span data-ttu-id="9d6e2-128">**솔루션 탐색기** 에서 **NumberGuessWorkflowHost** 을 마우스 오른쪽 단추로 클릭 하 고 **참조 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-128">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Add Reference**.</span></span>

2. <span data-ttu-id="9d6e2-129">**참조 추가** 목록에서 **어셈블리** 를 선택 하 고 **어셈블리 검색** 상자에 `DurableInstancing`을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-129">Select **Assemblies** from the **Add Reference** list, and type `DurableInstancing` into the **Search Assemblies** box.</span></span> <span data-ttu-id="9d6e2-130">그러면 어셈블리가 필터링되므로 원하는 참조를 손쉽게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-130">This filters the assemblies and makes the desired references easier to select.</span></span>

3. <span data-ttu-id="9d6e2-131">**검색 결과** 목록에서 **DurableInstancing** 및 **DurableInstancing** 옆의 확인란을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-131">Check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list, and click **OK**.</span></span>

## <a name="to-create-the-workflow-host-form"></a><span data-ttu-id="9d6e2-132">워크플로 호스트 폼을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9d6e2-132">To create the workflow host form</span></span>

> [!NOTE]
> <span data-ttu-id="9d6e2-133">이 절차에서는 폼을 수동으로 추가 및 구성하는 방법을 단계별로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-133">The steps in this procedure describe how to add and configure the form manually.</span></span> <span data-ttu-id="9d6e2-134">필요한 경우 자습서용 솔루션 파일을 다운로드하고 프로젝트에 전체 폼을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-134">If desired, you can download the solution files for the tutorial and add the completed form to the project.</span></span> <span data-ttu-id="9d6e2-135">자습서 파일을 다운로드 하려면 [Windows Workflow Foundation (WF45)-초보자](https://go.microsoft.com/fwlink/?LinkID=248976)를 위한 자습서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-135">To download the tutorial files, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span> <span data-ttu-id="9d6e2-136">파일이 다운로드 되 면 **NumberGuessWorkflowHost** 를 마우스 오른쪽 단추로 클릭 하 고 **참조 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-136">Once the files are downloaded, right-click **NumberGuessWorkflowHost** and choose **Add Reference**.</span></span> <span data-ttu-id="9d6e2-137">**System.object** 와 **Drawing**에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-137">Add a reference to **System.Windows.Forms** and **System.Drawing**.</span></span> <span data-ttu-id="9d6e2-138">이러한 참조는 **추가**, **새 항목** 메뉴에서 새 양식을 추가 하는 경우 자동으로 추가 되지만 양식을 가져올 때 수동으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-138">These references are added automatically if you add a new form from the **Add**, **New Item** menu, but must be added manually when importing a form.</span></span> <span data-ttu-id="9d6e2-139">참조가 추가 되 면 **솔루션 탐색기** 에서 **NumberGuessWorkflowHost** 을 마우스 오른쪽 단추로 클릭 하 고 **추가**, **기존 항목**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-139">Once the references are added, right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Existing Item**.</span></span> <span data-ttu-id="9d6e2-140">프로젝트 파일에서 `Form` 폴더로 이동 하 여 **WorkflowHostForm.cs** (또는 **WorkflowHostForm**)를 선택 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-140">Browse to the `Form` folder in the project files, select **WorkflowHostForm.cs** (or **WorkflowHostForm.vb**), and click **Add**.</span></span> <span data-ttu-id="9d6e2-141">양식을 가져오도록 선택 하는 경우 다음 섹션으로 건너뛰어 [폼의 속성 및 도우미 메서드를 추가할](#to-add-the-properties-and-helper-methods-of-the-form)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-141">If you choose to import the form, then you can skip down to the next section, [To add the properties and helper methods of the form](#to-add-the-properties-and-helper-methods-of-the-form).</span></span>

1. <span data-ttu-id="9d6e2-142">**솔루션 탐색기** 에서 **NumberGuessWorkflowHost** 을 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 항목**을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-142">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **New Item**.</span></span>

2. <span data-ttu-id="9d6e2-143">**설치 된** 템플릿 목록에서 **Windows Form**을 선택 하 고 **이름** 상자에 `WorkflowHostForm`를 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-143">In the **Installed** templates list, choose **Windows Form**, type `WorkflowHostForm` in the **Name** box, and click **Add**.</span></span>

3. <span data-ttu-id="9d6e2-144">폼에 다음 속성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-144">Configure the following properties on the form.</span></span>

    |<span data-ttu-id="9d6e2-145">속성</span><span class="sxs-lookup"><span data-stu-id="9d6e2-145">Property</span></span>|<span data-ttu-id="9d6e2-146">값</span><span class="sxs-lookup"><span data-stu-id="9d6e2-146">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="9d6e2-147">FormBorderStyle</span><span class="sxs-lookup"><span data-stu-id="9d6e2-147">FormBorderStyle</span></span>|<span data-ttu-id="9d6e2-148">FixedSingle</span><span class="sxs-lookup"><span data-stu-id="9d6e2-148">FixedSingle</span></span>|
    |<span data-ttu-id="9d6e2-149">MaximizeBox</span><span class="sxs-lookup"><span data-stu-id="9d6e2-149">MaximizeBox</span></span>|<span data-ttu-id="9d6e2-150">False</span><span class="sxs-lookup"><span data-stu-id="9d6e2-150">False</span></span>|
    |<span data-ttu-id="9d6e2-151">크기</span><span class="sxs-lookup"><span data-stu-id="9d6e2-151">Size</span></span>|<span data-ttu-id="9d6e2-152">400, 420</span><span class="sxs-lookup"><span data-stu-id="9d6e2-152">400, 420</span></span>|

4. <span data-ttu-id="9d6e2-153">폼에 다음 컨트롤을 지정된 순서대로 추가하고 지시된 대로 속성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-153">Add the following controls to the form in the order specified and configure the properties as directed.</span></span>

    |<span data-ttu-id="9d6e2-154">Control</span><span class="sxs-lookup"><span data-stu-id="9d6e2-154">Control</span></span>|<span data-ttu-id="9d6e2-155">속성: 값</span><span class="sxs-lookup"><span data-stu-id="9d6e2-155">Property: Value</span></span>|
    |-------------|---------------------|
    |<span data-ttu-id="9d6e2-156">**Button**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-156">**Button**</span></span>|<span data-ttu-id="9d6e2-157">이름: NewGame</span><span class="sxs-lookup"><span data-stu-id="9d6e2-157">Name: NewGame</span></span><br /><br /> <span data-ttu-id="9d6e2-158">위치: 13, 13</span><span class="sxs-lookup"><span data-stu-id="9d6e2-158">Location: 13, 13</span></span><br /><br /> <span data-ttu-id="9d6e2-159">크기: 75, 23</span><span class="sxs-lookup"><span data-stu-id="9d6e2-159">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="9d6e2-160">텍스트: 새 게임</span><span class="sxs-lookup"><span data-stu-id="9d6e2-160">Text: New Game</span></span>|
    |<span data-ttu-id="9d6e2-161">**레이블**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-161">**Label**</span></span>|<span data-ttu-id="9d6e2-162">위치: 94, 18</span><span class="sxs-lookup"><span data-stu-id="9d6e2-162">Location: 94, 18</span></span><br /><br /> <span data-ttu-id="9d6e2-163">Text: 1에서 사이의 숫자를 추측 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-163">Text: Guess a number from 1 to</span></span>|
    |<span data-ttu-id="9d6e2-164">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-164">**ComboBox**</span></span>|<span data-ttu-id="9d6e2-165">이름: NumberRange</span><span class="sxs-lookup"><span data-stu-id="9d6e2-165">Name: NumberRange</span></span><br /><br /> <span data-ttu-id="9d6e2-166">DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="9d6e2-166">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="9d6e2-167">항목: 10, 100, 1000</span><span class="sxs-lookup"><span data-stu-id="9d6e2-167">Items: 10, 100, 1000</span></span><br /><br /> <span data-ttu-id="9d6e2-168">위치: 228, 12</span><span class="sxs-lookup"><span data-stu-id="9d6e2-168">Location: 228, 12</span></span><br /><br /> <span data-ttu-id="9d6e2-169">크기: 143, 21</span><span class="sxs-lookup"><span data-stu-id="9d6e2-169">Size: 143, 21</span></span>|
    |<span data-ttu-id="9d6e2-170">**레이블**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-170">**Label**</span></span>|<span data-ttu-id="9d6e2-171">위치: 13, 43</span><span class="sxs-lookup"><span data-stu-id="9d6e2-171">Location: 13, 43</span></span><br /><br /> <span data-ttu-id="9d6e2-172">텍스트: 워크플로 유형</span><span class="sxs-lookup"><span data-stu-id="9d6e2-172">Text: Workflow type</span></span>|
    |<span data-ttu-id="9d6e2-173">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-173">**ComboBox**</span></span>|<span data-ttu-id="9d6e2-174">이름: WorkflowType</span><span class="sxs-lookup"><span data-stu-id="9d6e2-174">Name: WorkflowType</span></span><br /><br /> <span data-ttu-id="9d6e2-175">DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="9d6e2-175">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="9d6e2-176">항목: Statemachinenumberguessworkflow.xaml, Flowchartnumberguessworkflow.xaml, Sequentialnumberguessworkflow.xaml</span><span class="sxs-lookup"><span data-stu-id="9d6e2-176">Items: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow</span></span><br /><br /> <span data-ttu-id="9d6e2-177">위치: 94, 40</span><span class="sxs-lookup"><span data-stu-id="9d6e2-177">Location: 94, 40</span></span><br /><br /> <span data-ttu-id="9d6e2-178">크기: 277, 21</span><span class="sxs-lookup"><span data-stu-id="9d6e2-178">Size: 277, 21</span></span>|
    |<span data-ttu-id="9d6e2-179">**레이블**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-179">**Label**</span></span>|<span data-ttu-id="9d6e2-180">이름: WorkflowVersion</span><span class="sxs-lookup"><span data-stu-id="9d6e2-180">Name: WorkflowVersion</span></span><br /><br /> <span data-ttu-id="9d6e2-181">위치: 13, 362</span><span class="sxs-lookup"><span data-stu-id="9d6e2-181">Location: 13, 362</span></span><br /><br /> <span data-ttu-id="9d6e2-182">텍스트: 워크플로 버전</span><span class="sxs-lookup"><span data-stu-id="9d6e2-182">Text: Workflow version</span></span>|
    |<span data-ttu-id="9d6e2-183">**GroupBox**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-183">**GroupBox**</span></span>|<span data-ttu-id="9d6e2-184">위치: 13, 67</span><span class="sxs-lookup"><span data-stu-id="9d6e2-184">Location: 13, 67</span></span><br /><br /> <span data-ttu-id="9d6e2-185">크기: 358, 287</span><span class="sxs-lookup"><span data-stu-id="9d6e2-185">Size: 358, 287</span></span><br /><br /> <span data-ttu-id="9d6e2-186">텍스트: Game</span><span class="sxs-lookup"><span data-stu-id="9d6e2-186">Text: Game</span></span>|

    > [!NOTE]
    > <span data-ttu-id="9d6e2-187">다음 컨트롤을 추가 하는 경우 해당 컨트롤을 GroupBox에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-187">When adding the following controls, put them into the GroupBox.</span></span>

    |<span data-ttu-id="9d6e2-188">Control</span><span class="sxs-lookup"><span data-stu-id="9d6e2-188">Control</span></span>|<span data-ttu-id="9d6e2-189">속성: 값</span><span class="sxs-lookup"><span data-stu-id="9d6e2-189">Property: Value</span></span>|
    |-------------|---------------------|
    |<span data-ttu-id="9d6e2-190">**레이블**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-190">**Label**</span></span>|<span data-ttu-id="9d6e2-191">위치: 7, 20</span><span class="sxs-lookup"><span data-stu-id="9d6e2-191">Location: 7, 20</span></span><br /><br /> <span data-ttu-id="9d6e2-192">텍스트: 워크플로 인스턴스 Id</span><span class="sxs-lookup"><span data-stu-id="9d6e2-192">Text: Workflow Instance Id</span></span>|
    |<span data-ttu-id="9d6e2-193">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-193">**ComboBox**</span></span>|<span data-ttu-id="9d6e2-194">이름: InstanceId</span><span class="sxs-lookup"><span data-stu-id="9d6e2-194">Name: InstanceId</span></span><br /><br /> <span data-ttu-id="9d6e2-195">DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="9d6e2-195">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="9d6e2-196">위치: 121, 17</span><span class="sxs-lookup"><span data-stu-id="9d6e2-196">Location: 121, 17</span></span><br /><br /> <span data-ttu-id="9d6e2-197">크기: 227, 21</span><span class="sxs-lookup"><span data-stu-id="9d6e2-197">Size: 227, 21</span></span>|
    |<span data-ttu-id="9d6e2-198">**레이블**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-198">**Label**</span></span>|<span data-ttu-id="9d6e2-199">위치: 7, 47</span><span class="sxs-lookup"><span data-stu-id="9d6e2-199">Location: 7, 47</span></span><br /><br /> <span data-ttu-id="9d6e2-200">텍스트: Guess</span><span class="sxs-lookup"><span data-stu-id="9d6e2-200">Text: Guess</span></span>|
    |<span data-ttu-id="9d6e2-201">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-201">**TextBox**</span></span>|<span data-ttu-id="9d6e2-202">이름: Guess</span><span class="sxs-lookup"><span data-stu-id="9d6e2-202">Name: Guess</span></span><br /><br /> <span data-ttu-id="9d6e2-203">위치: 50, 44</span><span class="sxs-lookup"><span data-stu-id="9d6e2-203">Location: 50, 44</span></span><br /><br /> <span data-ttu-id="9d6e2-204">크기: 65, 20</span><span class="sxs-lookup"><span data-stu-id="9d6e2-204">Size: 65, 20</span></span>|
    |<span data-ttu-id="9d6e2-205">**Button**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-205">**Button**</span></span>|<span data-ttu-id="9d6e2-206">이름: 이름 추측</span><span class="sxs-lookup"><span data-stu-id="9d6e2-206">Name: EnterGuess</span></span><br /><br /> <span data-ttu-id="9d6e2-207">위치: 121, 42</span><span class="sxs-lookup"><span data-stu-id="9d6e2-207">Location: 121, 42</span></span><br /><br /> <span data-ttu-id="9d6e2-208">크기: 75, 23</span><span class="sxs-lookup"><span data-stu-id="9d6e2-208">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="9d6e2-209">텍스트: Guess를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-209">Text: Enter Guess</span></span>|
    |<span data-ttu-id="9d6e2-210">**Button**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-210">**Button**</span></span>|<span data-ttu-id="9d6e2-211">이름: QuitGame</span><span class="sxs-lookup"><span data-stu-id="9d6e2-211">Name: QuitGame</span></span><br /><br /> <span data-ttu-id="9d6e2-212">위치: 274, 42</span><span class="sxs-lookup"><span data-stu-id="9d6e2-212">Location: 274, 42</span></span><br /><br /> <span data-ttu-id="9d6e2-213">크기: 75, 23</span><span class="sxs-lookup"><span data-stu-id="9d6e2-213">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="9d6e2-214">텍스트: 종료</span><span class="sxs-lookup"><span data-stu-id="9d6e2-214">Text: Quit</span></span>|
    |<span data-ttu-id="9d6e2-215">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-215">**TextBox**</span></span>|<span data-ttu-id="9d6e2-216">이름: WorkflowStatus</span><span class="sxs-lookup"><span data-stu-id="9d6e2-216">Name: WorkflowStatus</span></span><br /><br /> <span data-ttu-id="9d6e2-217">위치: 10, 73</span><span class="sxs-lookup"><span data-stu-id="9d6e2-217">Location: 10, 73</span></span><br /><br /> <span data-ttu-id="9d6e2-218">여러 줄: True</span><span class="sxs-lookup"><span data-stu-id="9d6e2-218">Multiline: True</span></span><br /><br /> <span data-ttu-id="9d6e2-219">ReadOnly: True</span><span class="sxs-lookup"><span data-stu-id="9d6e2-219">ReadOnly: True</span></span><br /><br /> <span data-ttu-id="9d6e2-220">스크롤 막대: 세로</span><span class="sxs-lookup"><span data-stu-id="9d6e2-220">ScrollBars: Vertical</span></span><br /><br /> <span data-ttu-id="9d6e2-221">크기: 338, 208</span><span class="sxs-lookup"><span data-stu-id="9d6e2-221">Size: 338, 208</span></span>|

5. <span data-ttu-id="9d6e2-222">폼의 **Acceptbutton** 속성을 속성 **추측**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-222">Set the **AcceptButton** property of the form to **EnterGuess**.</span></span>

 <span data-ttu-id="9d6e2-223">다음 예제에서는 완성된 폼을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-223">The following example illustrates the completed form.</span></span>

 ![Windows Workflow Foundation 워크플로 호스트 폼의 스크린샷](./media/how-to-create-and-run-a-long-running-workflow/windows-workflow-foundation-workflowhostform.png)

## <a name="to-add-the-properties-and-helper-methods-of-the-form"></a><span data-ttu-id="9d6e2-225">폼의 속성 및 도우미 메서드를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="9d6e2-225">To add the properties and helper methods of the form</span></span>

<span data-ttu-id="9d6e2-226">이 단원의 단계에서는 숫자 추측 워크플로의 실행 및 다시 시작을 지원하도록 폼 UI를 구성하는 속성 및 도우미 메서드를 폼 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-226">The steps in this section add properties and helper methods to the form class that configure the UI of the form to support running and resuming number guess workflows.</span></span>

1. <span data-ttu-id="9d6e2-227">**솔루션 탐색기** 에서 **WorkflowHostForm** 을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-227">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>

2. <span data-ttu-id="9d6e2-228">다음 `using`(또는 `Imports`) 문을 파일의 맨 위에 다른 `using`(또는 `Imports`) 문과 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-228">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.DurableInstancing
    Imports System.Data.SqlClient
    Imports System.IO
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Activities;
    using System.Activities.DurableInstancing;
    using System.Data.SqlClient;
    using System.IO;
    using System.Windows.Forms;
    ```

3. <span data-ttu-id="9d6e2-229">**WorkflowHostForm** 클래스에 다음 멤버 선언을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-229">Add the following member declarations to the **WorkflowHostForm** class.</span></span>

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    Dim store As SqlWorkflowInstanceStore
    Dim workflowStarting As Boolean
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    SqlWorkflowInstanceStore store;
    bool workflowStarting;
    ```

    > [!NOTE]
    > <span data-ttu-id="9d6e2-230">연결 문자열이 다른 경우 해당 데이터베이스를 참조하도록 `connectionString`을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-230">If your connection string is different, update `connectionString` to refer to your database.</span></span>

4. <span data-ttu-id="9d6e2-231">`WorkflowInstanceId` 클래스에 `WorkflowFormHost` 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-231">Add a `WorkflowInstanceId` property to the `WorkflowFormHost` class.</span></span>

    ```vb
    Public ReadOnly Property WorkflowInstanceId() As Guid
        Get
            If InstanceId.SelectedIndex = -1 Then
                Return Guid.Empty
            Else
                Return New Guid(InstanceId.SelectedItem.ToString())
            End If
        End Get
    End Property
    ```

    ```csharp
    public Guid WorkflowInstanceId
    {
        get
        {
            return InstanceId.SelectedIndex == -1 ? Guid.Empty : (Guid)InstanceId.SelectedItem;
        }
    }
    ```

    <span data-ttu-id="9d6e2-232">`InstanceId` 콤보 상자에는 지속형 워크플로 인스턴스 id의 목록이 표시 되 고 `WorkflowInstanceId` 속성은 현재 선택한 워크플로를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-232">The `InstanceId` combo box displays a list of persisted workflow instance ids, and the `WorkflowInstanceId` property returns the currently selected workflow.</span></span>

5. <span data-ttu-id="9d6e2-233">폼의 `Load` 이벤트에 대한 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-233">Add a handler for the form `Load` event.</span></span> <span data-ttu-id="9d6e2-234">처리기를 추가 하려면 폼의 **디자인 뷰로** 전환 하 고 **속성** 창 맨 위에 있는 **이벤트** 아이콘을 클릭 한 다음 **로드**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-234">To add the handler, switch to **Design View** for the form, click the **Events** icon at the top of the **Properties** window, and double-click **Load**.</span></span>

    ```vb
    Private Sub WorkflowHostForm_Load(sender As Object, e As EventArgs) Handles Me.Load

    End Sub
    ```

    ```csharp
    private void WorkflowHostForm_Load(object sender, EventArgs e)
    {

    }
    ```

6. <span data-ttu-id="9d6e2-235">다음 코드를 `WorkflowHostForm_Load`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-235">Add the following code to `WorkflowHostForm_Load`.</span></span>

    ```vb
    ' Initialize the store and configure it so that it can be used for
    ' multiple WorkflowApplication instances.
    store = New SqlWorkflowInstanceStore(connectionString)
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)

    ' Set default ComboBox selections.
    NumberRange.SelectedIndex = 0
    WorkflowType.SelectedIndex = 0

    ListPersistedWorkflows()
    ```

    ```csharp
    // Initialize the store and configure it so that it can be used for
    // multiple WorkflowApplication instances.
    store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);

    // Set default ComboBox selections.
    NumberRange.SelectedIndex = 0;
    WorkflowType.SelectedIndex = 0;

    ListPersistedWorkflows();
    ```

    <span data-ttu-id="9d6e2-236">폼이 로드되면 `SqlWorkflowInstanceStore`가 구성되고 범위 및 워크플로 유형 콤보 상자가 기본값으로 설정되며 지속형 워크플로 인스턴스가 `InstanceId` 콤보 상자에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-236">When the form loads, the `SqlWorkflowInstanceStore` is configured, the range and workflow type combo boxes are set to default values, and the persisted workflow instances are added to the `InstanceId` combo box.</span></span>

7. <span data-ttu-id="9d6e2-237">`SelectedIndexChanged`에 대한 `InstanceId` 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-237">Add a `SelectedIndexChanged` handler for `InstanceId`.</span></span> <span data-ttu-id="9d6e2-238">처리기를 추가 하려면 폼의 **디자인 뷰로** 전환 하 고 `InstanceId` 콤보 상자를 선택한 다음 **속성** 창 맨 위에 있는 **이벤트** 아이콘을 클릭 하 고 **SelectedIndexChanged**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-238">To add the handler, switch to **Design View** for the form, select the `InstanceId` combo box, click the **Events** icon at the top of the **Properties** window, and double-click **SelectedIndexChanged**.</span></span>

    ```vb
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged

    End Sub
    ```

    ```csharp
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)
    {

    }
    ```

8. <span data-ttu-id="9d6e2-239">다음 코드를 `InstanceId_SelectedIndexChanged`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-239">Add the following code to `InstanceId_SelectedIndexChanged`.</span></span> <span data-ttu-id="9d6e2-240">콤보 상자를 사용하여 워크플로를 선택할 때마다 이 처리기에 의해 상태 창이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-240">Whenever the user selects a workflow by using the combo box this handler updates the status window.</span></span>

    ```vb
    If InstanceId.SelectedIndex = -1 Then
        Return
    End If

    ' Clear the status window.
    WorkflowStatus.Clear()

    ' Get the workflow version and display it.
    ' If the workflow is just starting then this info will not
    ' be available in the persistence store so do not try and retrieve it.
    If Not workflowStarting Then
        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        WorkflowVersion.Text = _
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)

        ' Unload the instance.
        instance.Abandon()
    End If
    ```

    ```csharp
    if (InstanceId.SelectedIndex == -1)
    {
        return;
    }

    // Clear the status window.
    WorkflowStatus.Clear();

    // Get the workflow version and display it.
    // If the workflow is just starting then this info will not
    // be available in the persistence store so do not try and retrieve it.
    if (!workflowStarting)
    {
        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);

        WorkflowVersion.Text =
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);

        // Unload the instance.
        instance.Abandon();
    }
    ```

9. <span data-ttu-id="9d6e2-241">폼 클래스에 다음 `ListPersistedWorkflows` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-241">Add the following `ListPersistedWorkflows` method to the form class.</span></span>

    ```vb
    Private Sub ListPersistedWorkflows()
        Using localCon As New SqlConnection(connectionString)
            Dim localCmd As String = _
                "SELECT [InstanceId] FROM [System.Activities.DurableInstancing].[Instances] ORDER BY [CreationTime]"

            Dim cmd As SqlCommand = localCon.CreateCommand()
            cmd.CommandText = localCmd
            localCon.Open()
            Using reader As SqlDataReader = cmd.ExecuteReader(CommandBehavior.CloseConnection)

                While (reader.Read())
                    ' Get the InstanceId of the persisted Workflow.
                    Dim id As Guid = Guid.Parse(reader(0).ToString())
                    InstanceId.Items.Add(id)
                End While
            End Using
        End Using
    End Sub
    ```

    ```csharp
    using (var localCon = new SqlConnection(connectionString))
    {
        string localCmd =
            "SELECT [InstanceId] FROM [System.Activities.DurableInstancing].[Instances] ORDER BY [CreationTime]";

        SqlCommand cmd = localCon.CreateCommand();
        cmd.CommandText = localCmd;
        localCon.Open();
        using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))
        {
            while (reader.Read())
            {
                // Get the InstanceId of the persisted Workflow.
                Guid id = Guid.Parse(reader[0].ToString());
                InstanceId.Items.Add(id);
            }
        }
    }
    ```

    <span data-ttu-id="9d6e2-242">`ListPersistedWorkflows` 인스턴스 저장소에서 지속형 워크플로 인스턴스를 쿼리하고 `cboInstanceId` 콤보 상자에 인스턴스 id를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-242">`ListPersistedWorkflows` queries the instance store for persisted workflow instances, and adds the instance ids to the `cboInstanceId` combo box.</span></span>

10. <span data-ttu-id="9d6e2-243">폼 클래스에 다음 `UpdateStatus` 메서드와 해당 대리자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-243">Add the following `UpdateStatus` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="9d6e2-244">이 메서드는 현재 실행 중인 워크플로의 상태로 폼의 상태 창을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-244">This method updates the status window on the form with the status of the currently running workflow.</span></span>

    ```vb
    Private Delegate Sub UpdateStatusDelegate(msg As String)
    Public Sub UpdateStatus(msg As String)
        ' We may be on a different thread so we need to
        ' make this call using BeginInvoke.
        If InvokeRequired Then
            BeginInvoke(New UpdateStatusDelegate(AddressOf UpdateStatus), msg)
        Else
            If Not msg.EndsWith(vbCrLf) Then
                msg = msg & vbCrLf
            End If

            WorkflowStatus.AppendText(msg)

            ' Ensure that the newly added status is visible.
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length
            WorkflowStatus.ScrollToCaret()
        End If
    End Sub
    ```

    ```csharp
    private delegate void UpdateStatusDelegate(string msg);
    public void UpdateStatus(string msg)
    {
        // We may be on a different thread so we need to
        // make this call using BeginInvoke.
        if (InvokeRequired)
        {
            BeginInvoke(new UpdateStatusDelegate(UpdateStatus), msg);
        }
        else
        {
            if (!msg.EndsWith("\r\n"))
            {
                msg += "\r\n";
            }
            WorkflowStatus.AppendText(msg);

            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length;
            WorkflowStatus.ScrollToCaret();
        }
    }
    ```

11. <span data-ttu-id="9d6e2-245">폼 클래스에 다음 `GameOver` 메서드와 해당 대리자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-245">Add the following `GameOver` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="9d6e2-246">워크플로가 완료 되 면이 메서드는 **InstanceId** 콤보 상자에서 완료 된 워크플로의 인스턴스 id를 제거 하 여 폼 UI를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-246">When a workflow completes, this method updates the form UI by removing the instance id of the completed workflow from the **InstanceId** combo box.</span></span>

    ```vb
    Private Delegate Sub GameOverDelegate()
    Private Sub GameOver()
        If InvokeRequired Then
            BeginInvoke(New GameOverDelegate(AddressOf GameOver))
        Else
            ' Remove this instance from the InstanceId combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem)
            InstanceId.SelectedIndex = -1
        End If
    End Sub
    ```

    ```csharp
    private delegate void GameOverDelegate();
    private void GameOver()
    {
        if (InvokeRequired)
        {
            BeginInvoke(new GameOverDelegate(GameOver));
        }
        else
        {
            // Remove this instance from the combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem);
            InstanceId.SelectedIndex = -1;
        }
    }
    ```

## <a name="to-configure-the-instance-store-workflow-lifecycle-handlers-and-extensions"></a><span data-ttu-id="9d6e2-247">인스턴스 저장소, 워크플로 수명 주기 처리기 및 확장을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="9d6e2-247">To configure the instance store, workflow lifecycle handlers, and extensions</span></span>

1. <span data-ttu-id="9d6e2-248">폼 클래스에 `ConfigureWorkflowApplication` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-248">Add a `ConfigureWorkflowApplication` method to the form class.</span></span>

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)

    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
    }
    ```

    <span data-ttu-id="9d6e2-249">이 메서드는 `WorkflowApplication`을 구성하고, 원하는 확장을 추가하고, 워크플로 수명 주기 이벤트에 대한 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-249">This method configures the `WorkflowApplication`, adds the desired extensions, and adds handlers for the workflow lifecycle events.</span></span>

2. <span data-ttu-id="9d6e2-250">`ConfigureWorkflowApplication`에서 `SqlWorkflowInstanceStore`에 `WorkflowApplication`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-250">In `ConfigureWorkflowApplication`, specify the `SqlWorkflowInstanceStore` for the `WorkflowApplication`.</span></span>

    ```vb
    ' Configure the persistence store.
    wfApp.InstanceStore = store
    ```

    ```csharp
    // Configure the persistence store.
    wfApp.InstanceStore = store;
    ```

3. <span data-ttu-id="9d6e2-251">그런 다음 `StringWriter` 인스턴스를 만들어 `Extensions`의 `WorkflowApplication` 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-251">Next, create a `StringWriter` instance and add it to the `Extensions` collection of the `WorkflowApplication`.</span></span> <span data-ttu-id="9d6e2-252">`StringWriter` 확장에 추가 되 면 모든 `WriteLine` 활동 출력을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-252">When a `StringWriter` is added to the extensions it captures all `WriteLine` activity output.</span></span> <span data-ttu-id="9d6e2-253">워크플로가 유휴 상태가 되면 `WriteLine` 출력이 `StringWriter`에서 추출되어 폼에 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-253">When the workflow becomes idle, the `WriteLine` output can be extracted from the `StringWriter` and displayed on the form.</span></span>

    ```vb
    ' Add a StringWriter to the extensions. This captures the output
    ' from the WriteLine activities so we can display it in the form.
    Dim sw As New StringWriter()
    wfApp.Extensions.Add(sw)
    ```

    ```csharp
    // Add a StringWriter to the extensions. This captures the output
    // from the WriteLine activities so we can display it in the form.
    var sw = new StringWriter();
    wfApp.Extensions.Add(sw);
    ```

4. <span data-ttu-id="9d6e2-254">`Completed` 이벤트에 대한 다음 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-254">Add the following handler for the `Completed` event.</span></span> <span data-ttu-id="9d6e2-255">워크플로가 성공적으로 완료되면 숫자를 추측한 횟수가 상태 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-255">When a workflow successfully completes, the number of turns taken to guess the number is displayed to the status window.</span></span> <span data-ttu-id="9d6e2-256">워크플로가 종료되면 종료 원인이 된 예외에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-256">If the workflow terminates, the exception information that caused the termination is displayed.</span></span> <span data-ttu-id="9d6e2-257">처리기가 끝나면 `GameOver` 메서드가 호출되어 워크플로 목록에서 완료된 워크플로를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-257">At the end of the handler the `GameOver` method is called, which removes the completed workflow from the workflow list.</span></span>

    ```vb
    wfApp.Completed = _
        Sub(e As WorkflowApplicationCompletedEventArgs)
            If e.CompletionState = ActivityInstanceState.Faulted Then
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}{vbCrLf}{e.TerminationException.Message}")
            ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                UpdateStatus("Workflow Canceled.")
            Else
                Dim turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                UpdateStatus($"Congratulations, you guessed the number in {turns} turns.")
            End If
            GameOver()
        End Sub
    ```

    ```csharp
    wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
    {
        if (e.CompletionState == ActivityInstanceState.Faulted)
        {
            UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
        }
        else if (e.CompletionState == ActivityInstanceState.Canceled)
        {
            UpdateStatus("Workflow Canceled.");
        }
        else
        {
            int turns = Convert.ToInt32(e.Outputs["Turns"]);
            UpdateStatus($"Congratulations, you guessed the number in {turns} turns.");
        }
        GameOver();
    };
    ```

5. <span data-ttu-id="9d6e2-258">다음 `Aborted` 및 `OnUnhandledException` 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-258">Add the following `Aborted` and `OnUnhandledException` handlers.</span></span> <span data-ttu-id="9d6e2-259">워크플로 인스턴스가 중단된 경우에는 해당 인스턴스가 종료되지 않으며 나중에 다시 시작할 수 있으므로 `GameOver` 처리기에서 `Aborted` 메서드가 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-259">The `GameOver` method is not called from the `Aborted` handler because when a workflow instance is aborted, it does not terminate, and it is possible to resume the instance at a later time.</span></span>

    ```vb
    wfApp.Aborted = _
        Sub(e As WorkflowApplicationAbortedEventArgs)
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}{vbCrLf}{e.Reason.Message}")
        End Sub

    wfApp.OnUnhandledException = _
        Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}{vbCrLf}{e.UnhandledException.Message}")
            GameOver()
            Return UnhandledExceptionAction.Terminate
        End Function
    ```

    ```csharp
    wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
    {
        UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
    };

    wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
    {
        UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
        GameOver();
        return UnhandledExceptionAction.Terminate;
    };
    ```

6. <span data-ttu-id="9d6e2-260">다음 `PersistableIdle` 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-260">Add the following `PersistableIdle` handler.</span></span> <span data-ttu-id="9d6e2-261">이 처리기는 추가된 `StringWriter` 확장을 검색하고 `WriteLine` 활동에서 출력을 추출하여 상태 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-261">This handler retrieves the `StringWriter` extension that was added, extracts the output from the `WriteLine` activities, and displays it in the status window.</span></span>

    ```vb
    wfApp.PersistableIdle = _
        Function(e As WorkflowApplicationIdleEventArgs)
            ' Send the current WriteLine outputs to the status window.
            Dim writers = e.GetInstanceExtensions(Of StringWriter)()
            For Each writer In writers
                UpdateStatus(writer.ToString())
            Next
            Return PersistableIdleAction.Unload
        End Function
    ```

    ```csharp
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
    {
        // Send the current WriteLine outputs to the status window.
        var writers = e.GetInstanceExtensions<StringWriter>();
        foreach (var writer in writers)
        {
            UpdateStatus(writer.ToString());
        }
        return PersistableIdleAction.Unload;
    };
    ```

    <span data-ttu-id="9d6e2-262"><xref:System.Activities.PersistableIdleAction> 열거형에는 세 개의 값(<xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist> 및 <xref:System.Activities.PersistableIdleAction.Unload>)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-262">The <xref:System.Activities.PersistableIdleAction> enumeration has three values: <xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist>, and <xref:System.Activities.PersistableIdleAction.Unload>.</span></span> <span data-ttu-id="9d6e2-263"><xref:System.Activities.PersistableIdleAction.Persist> 하면 워크플로가 유지 되지만 워크플로를 언로드하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-263"><xref:System.Activities.PersistableIdleAction.Persist> causes the workflow to persist but it does not cause the workflow to unload.</span></span> <span data-ttu-id="9d6e2-264"><xref:System.Activities.PersistableIdleAction.Unload> 하면 워크플로가 유지 되 고 언로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-264"><xref:System.Activities.PersistableIdleAction.Unload> causes the workflow to persist and be unloaded.</span></span>

    <span data-ttu-id="9d6e2-265">다음 예제는 전체 `ConfigureWorkflowApplication` 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-265">The following example is the completed `ConfigureWorkflowApplication` method.</span></span>

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)
        ' Configure the persistence store.
        wfApp.InstanceStore = store

        ' Add a StringWriter to the extensions. This captures the output
        ' from the WriteLine activities so we can display it in the form.
        Dim sw As New StringWriter()
        wfApp.Extensions.Add(sw)

        wfApp.Completed = _
            Sub(e As WorkflowApplicationCompletedEventArgs)
                If e.CompletionState = ActivityInstanceState.Faulted Then
                    UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}{vbCrLf}{e.TerminationException.Message}")
                ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                    UpdateStatus("Workflow Canceled.")
                Else
                    Dim turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                    UpdateStatus($"Congratulations, you guessed the number in {turns} turns.")
                End If
                GameOver()
            End Sub

        wfApp.Aborted = _
            Sub(e As WorkflowApplicationAbortedEventArgs)
                UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}{vbCrLf}{e.Reason.Message}")
            End Sub

        wfApp.OnUnhandledException = _
            Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
                UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}{vbCrLf}{e.UnhandledException.Message}")
                GameOver()
                Return UnhandledExceptionAction.Terminate
            End Function

        wfApp.PersistableIdle = _
            Function(e As WorkflowApplicationIdleEventArgs)
                ' Send the current WriteLine outputs to the status window.
                Dim writers = e.GetInstanceExtensions(Of StringWriter)()
                For Each writer In writers
                    UpdateStatus(writer.ToString())
                Next
                Return PersistableIdleAction.Unload
            End Function
    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
        // Configure the persistence store.
        wfApp.InstanceStore = store;

        // Add a StringWriter to the extensions. This captures the output
        // from the WriteLine activities so we can display it in the form.
        var sw = new StringWriter();
        wfApp.Extensions.Add(sw);

        wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
        {
            if (e.CompletionState == ActivityInstanceState.Faulted)
            {
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
            }
            else if (e.CompletionState == ActivityInstanceState.Canceled)
            {
                UpdateStatus("Workflow Canceled.");
            }
            else
            {
                int turns = Convert.ToInt32(e.Outputs["Turns"]);
                UpdateStatus($"Congratulations, you guessed the number in {turns} turns.");
            }
            GameOver();
        };

        wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
        {
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
        };

        wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
        {
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
            GameOver();
            return UnhandledExceptionAction.Terminate;
        };

        wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
        {
            // Send the current WriteLine outputs to the status window.
            var writers = e.GetInstanceExtensions<StringWriter>();
            foreach (var writer in writers)
            {
                UpdateStatus(writer.ToString());
            }
            return PersistableIdleAction.Unload;
        };
    }
    ```

## <a name="to-enable-starting-and-resuming-multiple-workflow-types"></a><span data-ttu-id="9d6e2-266">여러 워크플로 유형을 시작 및 다시 시작할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9d6e2-266">To enable starting and resuming multiple workflow types</span></span>

<span data-ttu-id="9d6e2-267">워크플로 인스턴스를 다시 시작하려면 호스트에서 워크플로 정의를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-267">In order to resume a workflow instance, the host has to provide the workflow definition.</span></span> <span data-ttu-id="9d6e2-268">이 자습서에는 세 가지 워크플로 유형이 있으며 이후 자습서 단계에서는 이러한 유형의 여러 버전을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-268">In this tutorial there are three workflow types, and subsequent tutorial steps introduce multiple versions of these types.</span></span> <span data-ttu-id="9d6e2-269">`WorkflowIdentity`는 호스트 응용 프로그램에서 식별 정보를 지속형 워크플로 인스턴스와 연결 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-269">`WorkflowIdentity` provides a way for a host application to associate identifying information with a persisted workflow instance.</span></span> <span data-ttu-id="9d6e2-270">이 단원의 단계에서는 유틸리티 클래스를 만들어 지속형 워크플로 인스턴스의 워크플로 ID를 해당 워크플로 정의에 쉽게 매핑할 수 있도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-270">The steps in this section demonstrate how to create a utility class to assist with mapping the workflow identity from a persisted workflow instance to the corresponding workflow definition.</span></span> <span data-ttu-id="9d6e2-271">`WorkflowIdentity` 및 버전 관리에 대 한 자세한 내용은 [WorkflowIdentity 및 버전 관리 사용](using-workflowidentity-and-versioning.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-271">For more information about `WorkflowIdentity` and versioning, see [Using WorkflowIdentity and Versioning](using-workflowidentity-and-versioning.md).</span></span>

1. <span data-ttu-id="9d6e2-272">**솔루션 탐색기** 에서 **NumberGuessWorkflowHost** 을 마우스 오른쪽 단추로 클릭 하 고 **추가**, **클래스**를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-272">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="9d6e2-273">**이름** 상자에 `WorkflowVersionMap`을 입력 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-273">Type `WorkflowVersionMap` into the **Name** box and click **Add**.</span></span>

2. <span data-ttu-id="9d6e2-274">다음 `using` 또는 `Imports` 문을 파일의 맨 위에 다른 `using` 또는 `Imports` 문과 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-274">Add the following `using` or `Imports` statements at the top of the file with the other `using` or `Imports` statements.</span></span>

    ```vb
    Imports System.Activities
    Imports NumberGuessWorkflowActivities
    ```

    ```csharp
    using System.Activities;
    using NumberGuessWorkflowActivities;
    ```

3. <span data-ttu-id="9d6e2-275">`WorkflowVersionMap` 클래스 선언을 다음 선언으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-275">Replace the `WorkflowVersionMap` class declaration with the following declaration.</span></span>

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        ' Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            ' Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())
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

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());
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

    <span data-ttu-id="9d6e2-276">`WorkflowVersionMap`에는이 자습서의 세 가지 워크플로 정의에 매핑되는 세 개의 워크플로 id가 포함 되어 있으며 워크플로가 시작 되 고 다시 시작 될 때 다음 섹션에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-276">`WorkflowVersionMap` contains three workflow identities that map to the three workflow definitions from this tutorial and is used in the following sections when workflows are started and resumed.</span></span>

## <a name="to-start-a-new-workflow"></a><span data-ttu-id="9d6e2-277">새 워크플로를 시작하려면</span><span class="sxs-lookup"><span data-stu-id="9d6e2-277">To start a new workflow</span></span>

1. <span data-ttu-id="9d6e2-278">`Click`에 대한 `NewGame` 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-278">Add a `Click` handler for `NewGame`.</span></span> <span data-ttu-id="9d6e2-279">처리기를 추가 하려면 폼의 **디자인 뷰로** 전환 하 고 `NewGame`를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-279">To add the handler, switch to **Design View** for the form, and double-click `NewGame`.</span></span> <span data-ttu-id="9d6e2-280">`NewGame_Click` 처리기가 추가되고 폼의 뷰가 코드 뷰로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-280">A `NewGame_Click` handler is added and the view switches to code view for the form.</span></span> <span data-ttu-id="9d6e2-281">이 단추를 클릭할 때마다 새 워크플로가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-281">Whenever the user clicks this button a new workflow is started.</span></span>

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click

    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="9d6e2-282">click 처리기에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-282">Add the following code to the click handler.</span></span> <span data-ttu-id="9d6e2-283">이 코드는 인수 이름으로 키가 지정된 워크플로 입력 인수 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-283">This code creates a dictionary of input arguments for the workflow, keyed by argument name.</span></span> <span data-ttu-id="9d6e2-284">이 사전에는 범위 콤보 상자에서 검색된 임의 생성 숫자의 범위를 포함하는 항목이 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-284">This dictionary has one entry that contains the range of the randomly generated number retrieved from the range combo box.</span></span>

    ```vb
    Dim inputs As New Dictionary(Of String, Object)()
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))
    ```

    ```csharp
    var inputs = new Dictionary<string, object>();
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));
    ```

3. <span data-ttu-id="9d6e2-285">다음으로는 워크플로를 시작하는 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-285">Next, add the following code that starts the workflow.</span></span> <span data-ttu-id="9d6e2-286">선택된 워크플로 유형에 해당하는 `WorkflowIdentity` 및 워크플로 정의는 `WorkflowVersionMap` 도우미 클래스를 사용하여 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-286">The `WorkflowIdentity` and workflow definition corresponding to the type of workflow selected are retrieved using the `WorkflowVersionMap` helper class.</span></span> <span data-ttu-id="9d6e2-287">그런 다음 워크플로 정의, `WorkflowApplication` 및 입력 인수 사전을 사용하여 새 `WorkflowIdentity` 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-287">Next, a new `WorkflowApplication` instance is created using the workflow definition, `WorkflowIdentity`, and dictionary of input arguments.</span></span>

    ```vb
    Dim identity As WorkflowIdentity = Nothing
    Select Case WorkflowType.SelectedItem.ToString()
        Case "SequentialNumberGuessWorkflow"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity

        Case "StateMachineNumberGuessWorkflow"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

        Case "FlowchartNumberGuessWorkflow"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
    End Select

    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

    Dim wfApp = New WorkflowApplication(wf, inputs, identity)
    ```

    ```csharp
    WorkflowIdentity identity = null;
    switch (WorkflowType.SelectedItem.ToString())
    {
        case "SequentialNumberGuessWorkflow":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
            break;

        case "StateMachineNumberGuessWorkflow":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
            break;

        case "FlowchartNumberGuessWorkflow":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
            break;
    };

    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

    WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);
    ```

4. <span data-ttu-id="9d6e2-288">그런 다음 워크플로 목록에 워크플로를 추가하고 폼에 워크플로 버전 정보를 표시하는 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-288">Next, add the following code which adds the workflow to the workflow list and displays the workflow's version information on the form.</span></span>

    ```vb
    ' Add the workflow to the list and display the version information.
    workflowStarting = True
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
    WorkflowVersion.Text = identity.ToString()
    workflowStarting = False
    ```

    ```csharp
    // Add the workflow to the list and display the version information.
    workflowStarting = true;
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
    WorkflowVersion.Text = identity.ToString();
    workflowStarting = false;
    ```

5. <span data-ttu-id="9d6e2-289">`ConfigureWorkflowApplication`을 호출하여 이 `WorkflowApplication` 인스턴스의 인스턴스 저장소, 확장명 및 워크플로 수명 주기 처리기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-289">Call `ConfigureWorkflowApplication` to configure the instance store, extensions, and workflow lifecycle handlers for this `WorkflowApplication` instance.</span></span>

    ```vb
    ' Configure the instance store, extensions, and
    ' workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)
    ```

    ```csharp
    // Configure the instance store, extensions, and
    // workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp);
    ```

6. <span data-ttu-id="9d6e2-290">마지막으로 `Run`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-290">Finally, call `Run`.</span></span>

    ```vb
    ' Start the workflow.
    wfApp.Run()
    ```

    ```csharp
    // Start the workflow.
    wfApp.Run();
    ```

     <span data-ttu-id="9d6e2-291">다음 예제는 전체 `NewGame_Click` 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-291">The following example is the completed `NewGame_Click` handler.</span></span>

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click
        ' Start a new workflow.
        Dim inputs As New Dictionary(Of String, Object)()
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))

        Dim identity As WorkflowIdentity = Nothing
        Select Case WorkflowType.SelectedItem.ToString()
            Case "SequentialNumberGuessWorkflow"
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity

            Case "StateMachineNumberGuessWorkflow"
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

            Case "FlowchartNumberGuessWorkflow"
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
        End Select

        Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

        Dim wfApp = New WorkflowApplication(wf, inputs, identity)

        ' Add the workflow to the list and display the version information.
        workflowStarting = True
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
        WorkflowVersion.Text = identity.ToString()
        workflowStarting = False

        ' Configure the instance store, extensions, and
        ' workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp)

        ' Start the workflow.
        wfApp.Run()
    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {
        var inputs = new Dictionary<string, object>();
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));

        WorkflowIdentity identity = null;
        switch (WorkflowType.SelectedItem.ToString())
        {
            case "SequentialNumberGuessWorkflow":
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
                break;

            case "StateMachineNumberGuessWorkflow":
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
                break;

            case "FlowchartNumberGuessWorkflow":
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
                break;
        };

        Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

        var wfApp = new WorkflowApplication(wf, inputs, identity);

        // Add the workflow to the list and display the version information.
        workflowStarting = true;
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
        WorkflowVersion.Text = identity.ToString();
        workflowStarting = false;

        // Configure the instance store, extensions, and
        // workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp);

        // Start the workflow.
        wfApp.Run();
    }
    ```

## <a name="to-resume-a-workflow"></a><span data-ttu-id="9d6e2-292">워크플로를 다시 시작하려면</span><span class="sxs-lookup"><span data-stu-id="9d6e2-292">To resume a workflow</span></span>

1. <span data-ttu-id="9d6e2-293">`Click`에 대한 `EnterGuess` 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-293">Add a `Click` handler for `EnterGuess`.</span></span> <span data-ttu-id="9d6e2-294">처리기를 추가 하려면 폼의 **디자인 뷰로** 전환 하 고 `EnterGuess`를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-294">To add the handler, switch to **Design View** for the form, and double-click `EnterGuess`.</span></span> <span data-ttu-id="9d6e2-295">이 단추를 클릭할 때마다 워크플로가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-295">Whenever the user clicks this button a workflow is resumed.</span></span>

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click

    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="9d6e2-296">워크플로 목록에 워크플로가 선택되어 있고 사용자의 추측이 올바른지 확인하는 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-296">Add the following code to ensure that a workflow is selected in the workflow list, and that the user's guess is valid.</span></span>

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim userGuess As Integer
    If Not Int32.TryParse(Guess.Text, userGuess) Then
        MessageBox.Show("Please enter an integer.")
        Guess.SelectAll()
        Guess.Focus()
        Return
    End If
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    int guess;
    if (!Int32.TryParse(Guess.Text, out guess))
    {
        MessageBox.Show("Please enter an integer.");
        Guess.SelectAll();
        Guess.Focus();
        return;
    }
    ```

3. <span data-ttu-id="9d6e2-297">그런 다음 지속형 워크플로 인스턴스의 `WorkflowApplicationInstance`를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-297">Next, retrieve the `WorkflowApplicationInstance` of the persisted workflow instance.</span></span> <span data-ttu-id="9d6e2-298">`WorkflowApplicationInstance`는 워크플로 정의와 아직 연결되지 않은 지속형 워크플로 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-298">A `WorkflowApplicationInstance` represents a persisted workflow instance that has not yet been associated with a workflow definition.</span></span> <span data-ttu-id="9d6e2-299">`DefinitionIdentity`의 `WorkflowApplicationInstance`에는 지속형 워크플로 인스턴스의 `WorkflowIdentity`가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-299">The `DefinitionIdentity` of the `WorkflowApplicationInstance` contains the `WorkflowIdentity` of the persisted workflow instance.</span></span> <span data-ttu-id="9d6e2-300">이 자습서에서는 `WorkflowVersionMap`를 올바른 워크플로 정의에 매핑하기 위해 `WorkflowIdentity` 유틸리티 클래스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-300">In this tutorial, the `WorkflowVersionMap` utility class is used to map the `WorkflowIdentity` to the correct workflow definition.</span></span> <span data-ttu-id="9d6e2-301">워크플로 정의가 검색되면 올바른 워크플로 정의를 사용하여 `WorkflowApplication`이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-301">Once the workflow definition is retrieved, a `WorkflowApplication` is created, using the correct workflow definition.</span></span>

    ```vb
    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    ' Use the persisted WorkflowIdentity to retrieve the correct workflow
    ' definition from the dictionary.
    Dim wf As Activity = _
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    ' Associate the WorkflowApplication with the correct definition
    Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)
    ```

    ```csharp
    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf =
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);
    ```

4. <span data-ttu-id="9d6e2-302">`WorkflowApplication`이 만들어진 후 `ConfigureWorkflowApplication`을 호출하여 인스턴스 저장소, 워크플로 수명 주기 처리기 및 확장을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-302">Once the `WorkflowApplication` is created, configure the instance store, workflow lifecycle handlers, and extensions by calling `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="9d6e2-303">이러한 단계는 새 `WorkflowApplication`이 만들어질 때마다 수행되어야 하며, 워크플로 인스턴스가 `WorkflowApplication`에 로드되기 전에 수행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-303">These steps must be done every time a new `WorkflowApplication` is created, and they must be done before the workflow instance is loaded into the `WorkflowApplication`.</span></span> <span data-ttu-id="9d6e2-304">워크플로가 로드된 후에는 사용자의 추측과 함께 워크플로가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-304">After the workflow is loaded, it is resumed with the user's guess.</span></span>

    ```vb
    ' Configure the extensions and lifecycle handlers.
    ' Do this before the instance is loaded. Once the instance is
    ' loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp)

    ' Load the workflow.
    wfApp.Load(instance)

    ' Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", userGuess)
    ```

    ```csharp
    // Configure the extensions and lifecycle handlers.
    // Do this before the instance is loaded. Once the instance is
    // loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", guess);
    ```

5. <span data-ttu-id="9d6e2-305">마지막으로, Guess 텍스트 상자를 지우고 다른 값을 추측할 수 있도록 폼을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-305">Finally, clear the guess textbox and prepare the form to accept another guess.</span></span>

    ```vb
    ' Clear the Guess textbox.
    Guess.Clear()
    Guess.Focus()
    ```

    ```csharp
    // Clear the Guess textbox.
    Guess.Clear();
    Guess.Focus();
    ```

    <span data-ttu-id="9d6e2-306">다음 예제는 전체 `EnterGuess_Click` 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-306">The following example is the completed `EnterGuess_Click` handler.</span></span>

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click
        If WorkflowInstanceId = Guid.Empty Then
            MessageBox.Show("Please select a workflow.")
            Return
        End If

        Dim userGuess As Integer
        If Not Int32.TryParse(Guess.Text, userGuess) Then
            MessageBox.Show("Please enter an integer.")
            Guess.SelectAll()
            Guess.Focus()
            Return
        End If

        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        ' Use the persisted WorkflowIdentity to retrieve the correct workflow
        ' definition from the dictionary.
        Dim wf As Activity = _
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

        ' Associate the WorkflowApplication with the correct definition
        Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)

        ' Configure the extensions and lifecycle handlers.
        ' Do this before the instance is loaded. Once the instance is
        ' loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp)

        ' Load the workflow.
        wfApp.Load(instance)

        ' Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", userGuess)

        ' Clear the Guess textbox.
        Guess.Clear()
        Guess.Focus()
    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {
        if (WorkflowInstanceId == Guid.Empty)
        {
            MessageBox.Show("Please select a workflow.");
            return;
        }

        int guess;
        if (!Int32.TryParse(Guess.Text, out guess))
        {
            MessageBox.Show("Please enter an integer.");
            Guess.SelectAll();
            Guess.Focus();
            return;
        }

        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(WorkflowInstanceId, store);

        // Use the persisted WorkflowIdentity to retrieve the correct workflow
        // definition from the dictionary.
        Activity wf =
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

        // Associate the WorkflowApplication with the correct definition
        var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);

        // Configure the extensions and lifecycle handlers.
        // Do this before the instance is loaded. Once the instance is
        // loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp);

        // Load the workflow.
        wfApp.Load(instance);

        // Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", guess);

        // Clear the Guess textbox.
        Guess.Clear();
        Guess.Focus();
    }
    ```

## <a name="to-terminate-a-workflow"></a><span data-ttu-id="9d6e2-307">워크플로를 종료하려면</span><span class="sxs-lookup"><span data-stu-id="9d6e2-307">To terminate a workflow</span></span>

1. <span data-ttu-id="9d6e2-308">`Click`에 대한 `QuitGame` 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-308">Add a `Click` handler for `QuitGame`.</span></span> <span data-ttu-id="9d6e2-309">처리기를 추가 하려면 폼의 **디자인 뷰로** 전환 하 고 `QuitGame`를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-309">To add the handler, switch to **Design View** for the form, and double-click `QuitGame`.</span></span> <span data-ttu-id="9d6e2-310">이 단추를 클릭할 때마다 현재 선택된 워크플로가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-310">Whenever the user clicks this button the currently selected workflow is terminated.</span></span>

    ```vb
    Private Sub QuitGame_Click(sender As Object, e As EventArgs) Handles QuitGame.Click

    End Sub
    ```

    ```csharp
    private void QuitGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="9d6e2-311">`QuitGame_Click` 처리기에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-311">Add the following code to the `QuitGame_Click` handler.</span></span> <span data-ttu-id="9d6e2-312">이 코드는 먼저 워크플로 목록에서 워크플로가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-312">This code first checks to ensure that a workflow is selected in the workflow list.</span></span> <span data-ttu-id="9d6e2-313">다음에는 지속형 인스턴스를 `WorkflowApplicationInstance`에 로드하고, `DefinitionIdentity`를 사용하여 올바른 워크플로 정의를 결정한 다음, `WorkflowApplication`을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-313">Then it loads the persisted instance into a `WorkflowApplicationInstance`, uses the `DefinitionIdentity` to determine the correct workflow definition, and then initializes the `WorkflowApplication`.</span></span> <span data-ttu-id="9d6e2-314">그런 다음 `ConfigureWorkflowApplication`을 호출하여 확장 및 워크플로 수명 주기 처리기가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-314">Next the extensions and workflow lifecycle handlers are configured with a call to `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="9d6e2-315">구성이 완료되면 `WorkflowApplication`이 로드되고 `Terminate`가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-315">Once the `WorkflowApplication` is configured, it is loaded, and then `Terminate` is called.</span></span>

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    ' Use the persisted WorkflowIdentity to retrieve the correct workflow
    ' definition from the dictionary.
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    ' Associate the WorkflowApplication with the correct definition.
    Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)

    ' Configure the extensions and lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)

    ' Load the workflow.
    wfApp.Load(instance)

    ' Terminate the workflow.
    wfApp.Terminate("User resigns.")
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);

    // Configure the extensions and lifecycle handlers
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Terminate the workflow.
    wfApp.Terminate("User resigns.");
    ```

## <a name="to-build-and-run-the-application"></a><span data-ttu-id="9d6e2-316">애플리케이션을 빌드하고 실행하려면</span><span class="sxs-lookup"><span data-stu-id="9d6e2-316">To build and run the application</span></span>

1. <span data-ttu-id="9d6e2-317">**솔루션 탐색기** 에서 **Program.cs** (또는 module1.vb)를 두 번 클릭 하 여 코드를 표시 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="9d6e2-317">Double-click **Program.cs** (or **Module1.vb**) in **Solution Explorer** to display the code.</span></span>

2. <span data-ttu-id="9d6e2-318">다음 `using`(또는 `Imports`) 문을 파일의 맨 위에 다른 `using`(또는 `Imports`) 문과 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-318">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Windows.Forms;
    ```

3. <span data-ttu-id="9d6e2-319">[방법: 워크플로 실행](how-to-run-a-workflow.md)에서 기존 워크플로 호스팅 코드를 제거 하거나 주석으로 처리 하 고 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-319">Remove or comment out the existing workflow hosting code from [How to: Run a Workflow](how-to-run-a-workflow.md), and replace it with the following code.</span></span>

    ```vb
    Sub Main()
        Application.EnableVisualStyles()
        Application.Run(New WorkflowHostForm())
    End Sub
    ```

    ```csharp
    static void Main(string[] args)
    {
        Application.EnableVisualStyles();
        Application.Run(new WorkflowHostForm());
    }
    ```

4. <span data-ttu-id="9d6e2-320">**솔루션 탐색기** 에서 **NumberGuessWorkflowHost** 을 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-320">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Properties**.</span></span> <span data-ttu-id="9d6e2-321">**응용 프로그램** 탭에서 **출력 형식**에 대 한 **Windows 응용 프로그램** 을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-321">In the **Application** tab, specify **Windows Application** for the **Output type**.</span></span> <span data-ttu-id="9d6e2-322">이 단계는 선택적이지만 이 단계를 수행하지 않으면 폼뿐만 아니라 콘솔 창도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-322">This step is optional, but if it is not followed the console window is displayed in addition to the form.</span></span>

5. <span data-ttu-id="9d6e2-323">Ctrl+Shift+B를 눌러 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-323">Press Ctrl+Shift+B to build the application.</span></span>

6. <span data-ttu-id="9d6e2-324">**NumberGuessWorkflowHost** 가 시작 응용 프로그램으로 설정 되어 있는지 확인 하 고 Ctrl + F5를 눌러 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-324">Ensure that **NumberGuessWorkflowHost** is set as the startup application, and press Ctrl+F5 to start the application.</span></span>

7. <span data-ttu-id="9d6e2-325">추측 게임의 범위와 시작할 워크플로 유형을 선택 하 고 **새 게임**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-325">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="9d6e2-326">**추측 상자에** guess를 입력 하 고 **이동** 을 클릭 하 여 추측을 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-326">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="9d6e2-327">`WriteLine` 활동의 출력이 폼에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-327">Note that the output from the `WriteLine` activities is displayed on the form.</span></span>

8. <span data-ttu-id="9d6e2-328">여러 워크플로 유형 및 숫자 범위를 사용 하 여 여러 워크플로를 시작 하 고, 몇 가지 추측을 입력 하 고, **워크플로 인스턴스 Id** 목록에서 선택 하 여 워크플로 사이를 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-328">Start several workflows using different workflow types and number ranges, enter some guesses, and switch between the workflows by selecting from the **Workflow Instance Id** list.</span></span>

    <span data-ttu-id="9d6e2-329">새 워크플로로 전환할 경우 이전 추측 값 및 워크플로 진행률이 상태 창에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-329">Note that when you switch to a new workflow, the previous guesses and progress of the workflow are not displayed in the status window.</span></span> <span data-ttu-id="9d6e2-330">상태를 사용할 수 없는 것은 상태가 캡처 및 저장되지 않았기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-330">The reason the status is not available is because it is not captured and saved anywhere.</span></span> <span data-ttu-id="9d6e2-331">자습서의 다음 단계인 [방법: 사용자 지정 추적 참가자 만들기](how-to-create-a-custom-tracking-participant.md)에서이 정보를 저장 하는 사용자 지정 추적 참가자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9d6e2-331">In the next step of the tutorial, [How to: Create a Custom Tracking Participant](how-to-create-a-custom-tracking-participant.md), you create a custom tracking participant that saves this information.</span></span>
