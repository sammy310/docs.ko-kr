---
description: '자세한 정보: 방법: 실행 중인 워크플로 인스턴스의 정의 업데이트'
title: '방법: 실행 중인 워크플로 인스턴스의 정의 업데이트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26dfac36-ae23-4909-9867-62495b55fb5e
ms.openlocfilehash: a3b1faa933cb79301946427823ef3e9f114823f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631228"
---
# <a name="how-to-update-the-definition-of-a-running-workflow-instance"></a><span data-ttu-id="02940-103">방법: 실행 중인 워크플로 인스턴스의 정의 업데이트</span><span class="sxs-lookup"><span data-stu-id="02940-103">How to: Update the Definition of a Running Workflow Instance</span></span>

<span data-ttu-id="02940-104">동적 업데이트는 워크플로 애플리케이션 개발자가 지속형 워크플로 인스턴스의 워크플로 정의를 업데이트하기 위한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-104">Dynamic update provides a mechanism for workflow application developers to update the workflow definition of a persisted workflow instance.</span></span> <span data-ttu-id="02940-105">필요한 변경을 통해 버그 수정 또는 새 요구 사항을 구현하거나 예기치 않은 변경 내용을 수용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-105">The required change can be to implement a bug fix, new requirements, or to accommodate unexpected changes.</span></span> <span data-ttu-id="02940-106">이 자습서의 단계에서는 동적 업데이트를 사용 하 여 여러 버전의 워크플로를 함께 `v1` [호스트 하는 방법: 여러 버전의 워크플로](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)를 함께 호스트 하는 데 도입 된 새로운 기능과 일치 하도록 동적 업데이트를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="02940-106">This step in the tutorial demonstrates how to use dynamic update to modify  persisted instances of the `v1` number guessing workflow to match the new functionality introduced in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="02940-107">항목 내용</span><span class="sxs-lookup"><span data-stu-id="02940-107">In this topic</span></span>

- [<span data-ttu-id="02940-108">CreateUpdateMaps 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="02940-108">To create the CreateUpdateMaps project</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_CreateProject)

- [<span data-ttu-id="02940-109">StateMachineNumberGuessWorkflow를 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="02940-109">To update StateMachineNumberGuessWorkflow</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_StateMachine)

- [<span data-ttu-id="02940-110">FlowchartNumberGuessWorkflow를 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="02940-110">To update FlowchartNumberGuessWorkflow</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_Flowchart)

- [<span data-ttu-id="02940-111">SequentialNumberGuessWorkflow를 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="02940-111">To update SequentialNumberGuessWorkflow</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_Sequential)

- [<span data-ttu-id="02940-112">CreateUpdateMaps 응용 프로그램을 빌드하고 실행하려면</span><span class="sxs-lookup"><span data-stu-id="02940-112">To build and run the CreateUpdateMaps application</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_CreateUpdateMaps)

- [<span data-ttu-id="02940-113">업데이트된 워크플로 어셈블리를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="02940-113">To build the updated workflow assembly</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_BuildAssembly)

- [<span data-ttu-id="02940-114">WorkflowVersionMap을 새 버전으로 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="02940-114">To update WorkflowVersionMap with the new versions</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_UpdateWorkflowVersionMap)

- [<span data-ttu-id="02940-115">동적 업데이트를 적용하려면</span><span class="sxs-lookup"><span data-stu-id="02940-115">To apply the dynamic updates</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_ApplyUpdate)

- [<span data-ttu-id="02940-116">업데이트된 워크플로로 응용 프로그램을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="02940-116">To run the application with the updated workflows</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_BuildAndRun)

- [<span data-ttu-id="02940-117">이전 버전의 워크플로를 시작하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="02940-117">To enable starting previous versions of the workflows</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_StartPreviousVersions)

### <a name="to-create-the-createupdatemaps-project"></a><a name="BKMK_CreateProject"></a> <span data-ttu-id="02940-118">CreateUpdateMaps 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="02940-118">To create the CreateUpdateMaps project</span></span>

1. <span data-ttu-id="02940-119">**솔루션 탐색기** 에서 **WF45GettingStartedTutorial** 을 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 프로젝트** 를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-119">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>

2. <span data-ttu-id="02940-120">**설치 됨** 노드에서 **Visual c #**, **windows** (또는 **Visual Basic**, **windows**)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-120">In the **Installed** node, select **Visual C#**, **Windows** (or **Visual Basic**, **Windows**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="02940-121">Visual Studio에서 기본 언어로 구성되어 있는 프로그래밍 언어에 따라 **Visual C#** 또는 **Visual Basic** 노드는 **설치됨** 노드의 **다른 언어** 노드에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-121">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

     <span data-ttu-id="02940-122">.NET Framework 버전 드롭다운 목록에서 **.NET Framework 4.5** 가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-122">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="02940-123">**Windows** 목록에서 **콘솔 응용 프로그램** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-123">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="02940-124">**이름** 상자에 **CreateUpdateMaps** 를 입력 하 고 **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-124">Type **CreateUpdateMaps** into the **Name** box and click **OK**.</span></span>

3. <span data-ttu-id="02940-125">**솔루션 탐색기** 에서 **CreateUpdateMaps** 을 마우스 오른쪽 단추로 클릭 하 고 **참조 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-125">Right-click **CreateUpdateMaps** in **Solution Explorer** and choose **Add Reference**.</span></span>

4. <span data-ttu-id="02940-126">**참조 추가** 목록의 **어셈블리** 노드에서 **프레임 워크** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-126">Select **Framework** from the **Assemblies** node in the **Add Reference** list.</span></span> <span data-ttu-id="02940-127">어셈블리 **검색** 상자에 **system.object** 를 입력 하 여 어셈블리를 필터링 하 고 원하는 참조를 더 쉽게 선택할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-127">Type **System.Activities** into the **Search Assemblies** box to filter the assemblies and make the desired references easier to select.</span></span>

5. <span data-ttu-id="02940-128">**검색 결과** 목록에서 **System. 작업** 옆의 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-128">Check the checkbox beside **System.Activities** from the **Search Results** list.</span></span>

6. <span data-ttu-id="02940-129">**어셈블리 검색** 상자에 **Serialization** 을 입력 하 고 **검색 결과** 목록에서 **system.object** 옆의 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-129">Type **Serialization** into the **Search Assemblies** box, and check the checkbox beside **System.Runtime.Serialization** from the **Search Results** list.</span></span>

7. <span data-ttu-id="02940-130">**어셈블리 검색** 상자에 **system.xaml** 을 입력 하 고 **검색 결과** 목록에서 **system.xaml** 옆의 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-130">Type **System.Xaml** into the **Search Assemblies** box, and check the checkbox beside **System.Xaml** from the **Search Results** list.</span></span>

8. <span data-ttu-id="02940-131">**확인** 을 클릭 하 여 **참조 관리자** 를 닫고 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-131">Click **OK** to close **Reference Manager** and add the references.</span></span>

9. <span data-ttu-id="02940-132">다음 `using`(또는 `Imports`) 문을 파일의 맨 위에 다른 `using`(또는 `Imports`) 문과 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-132">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.Statements
    Imports System.Xaml
    Imports System.Reflection
    Imports System.IO
    Imports System.Activities.XamlIntegration
    Imports System.Activities.DynamicUpdate
    Imports System.Runtime.Serialization
    Imports Microsoft.VisualBasic.Activities
    ```

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    using System.IO;
    using System.Xaml;
    using System.Reflection;
    using System.Activities.XamlIntegration;
    using System.Activities.DynamicUpdate;
    using System.Runtime.Serialization;
    using Microsoft.CSharp.Activities;
    ```

10. <span data-ttu-id="02940-133">`Program`(또는 `Module1`) 클래스에 다음 두 개의 문자열 멤버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-133">Add the following two string members to the `Program` class (or `Module1`).</span></span>

    ```vb
    Const mapPath = "..\..\..\PreviousVersions"
    Const definitionPath = "..\..\..\NumberGuessWorkflowActivities_du"
    ```

    ```csharp
    const string mapPath = @"..\..\..\PreviousVersions";
    const string definitionPath = @"..\..\..\NumberGuessWorkflowActivities_du";
    ```

11. <span data-ttu-id="02940-134">`StartUpdate`(또는 `Program`) 클래스에 다음 `Module1` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-134">Add the following `StartUpdate` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="02940-135">이 메서드는 지정된 xaml 워크플로 정의를 `ActivityBuilder`에 로드한 다음 `DynamicUpdate.PrepareForUpdate`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-135">This method loads up the specified xaml workflow definition into an `ActivityBuilder`, and then calls `DynamicUpdate.PrepareForUpdate`.</span></span> <span data-ttu-id="02940-136">`PrepareForUpdate`는 `ActivityBuilder` 내에 워크플로 정의의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02940-136">`PrepareForUpdate` makes a copy of the workflow definition inside the `ActivityBuilder`.</span></span> <span data-ttu-id="02940-137">워크플로 정의가 수정되면 이 복사본이 수정된 워크플로 정의와 함께 사용되어 업데이트 맵을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02940-137">After the workflow definition is modified, this copy is used along with the modified workflow definition to create the update map.</span></span>

    ```vb
    Private Function StartUpdate(name As String) As ActivityBuilder
        'Create the XamlXmlReaderSettings.
        Dim readerSettings As XamlReaderSettings = New XamlXmlReaderSettings()
        'In the XAML the "local" namespace refers to artifacts that come from
        'the same project as the XAML. When loading XAML if the currently executing
        'assembly is not the same assembly that was referred to as "local" in the XAML
        'LocalAssembly must be set to the assembly containing the artifacts.
        'Assembly.LoadFile requires an absolute path so convert this relative path
        'to an absolute path.
        readerSettings.LocalAssembly = Assembly.LoadFile(
            Path.GetFullPath(Path.Combine(mapPath, "NumberGuessWorkflowActivities_v1.dll")))

        Dim fullPath As String = Path.Combine(definitionPath, name)
        Dim xamlReader As XamlXmlReader = New XamlXmlReader(fullPath, readerSettings)

        'Load the workflow definition into an ActivityBuilder.
        Dim wf As ActivityBuilder = XamlServices.Load(
            ActivityXamlServices.CreateBuilderReader(xamlReader))

        'PrepareForUpdate makes a copy of the workflow definition in the
        'ActivityBuilder that is used for comparison when the update
        'map is created.
        DynamicUpdateServices.PrepareForUpdate(wf)

        Return wf
    End Function
    ```

    ```csharp
    private static ActivityBuilder StartUpdate(string name)
    {
        // Create the XamlXmlReaderSettings.
        XamlXmlReaderSettings readerSettings = new XamlXmlReaderSettings()
        {
            // In the XAML the "local" namespace refers to artifacts that come from
            // the same project as the XAML. When loading XAML if the currently executing
            // assembly is not the same assembly that was referred to as "local" in the XAML
            // LocalAssembly must be set to the assembly containing the artifacts.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            LocalAssembly = Assembly.LoadFile(
                Path.GetFullPath(Path.Combine(mapPath, "NumberGuessWorkflowActivities_v1.dll")))
        };

        string path = Path.Combine(definitionPath, name);
        XamlXmlReader xamlReader = new XamlXmlReader(path, readerSettings);

        // Load the workflow definition into an ActivityBuilder.
        ActivityBuilder wf = XamlServices.Load(
            ActivityXamlServices.CreateBuilderReader(xamlReader))
            as ActivityBuilder;

        // PrepareForUpdate makes a copy of the workflow definition in the
        // ActivityBuilder that is used for comparison when the update
        // map is created.
        DynamicUpdateServices.PrepareForUpdate(wf);

        return wf;
    }
    ```

12. <span data-ttu-id="02940-138">다음에는 `CreateUpdateMethod`(또는 `Program`) 클래스에 다음 `Module1`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-138">Next, add the following `CreateUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="02940-139">그러면 DynamicUpdateServices.CreateUpdateMap을 호출하여 동적 업데이트 맵이 만들어지고 지정된 이름을 사용하여 업데이트 맵이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="02940-139">This creates a dynamic update map by calling DynamicUpdateServices.CreateUpdateMap, and then saves the update map using the specified name.</span></span> <span data-ttu-id="02940-140">이 업데이트 맵에는 `ActivityBuilder`에 포함된 원래 워크플로 정의를 사용하여 시작된 지속형 워크플로 인스턴스가 업데이트된 워크플로 정의를 사용하여 완료될 수 있도록 워크플로 런타임이 이 인스턴스를 업데이트하는 데 필요한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-140">This update map contains the information needed by the workflow runtime to update a persisted workflow instance that was started using the original workflow definition contained in the `ActivityBuilder` so that it completes using the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateUpdateMaps(wf As ActivityBuilder, name As String)
        'Create the UpdateMap.
        Dim map As DynamicUpdateMap =
            DynamicUpdateServices.CreateUpdateMap(wf)

        'Serialize it to a file.
        Dim mapFullPath As String = Path.Combine(mapPath, name)
        Dim sz As DataContractSerializer = New DataContractSerializer(GetType(DynamicUpdateMap))
        Using fs As FileStream = File.Open(mapFullPath, FileMode.Create)
            sz.WriteObject(fs, map)
        End Using
    End Sub
    ```

    ```csharp
    private static void CreateUpdateMaps(ActivityBuilder wf, string name)
    {
        // Create the UpdateMap.
        DynamicUpdateMap map =
            DynamicUpdateServices.CreateUpdateMap(wf);

        // Serialize it to a file.
        string path = Path.Combine(mapPath, name);
        DataContractSerializer sz = new DataContractSerializer(typeof(DynamicUpdateMap));
        using (FileStream fs = System.IO.File.Open(path, FileMode.Create))
        {
            sz.WriteObject(fs, map);
        }
    }
    ```

13. <span data-ttu-id="02940-141">`SaveUpdatedDefinition`(또는 `Program`) 클래스에 다음 `Module1` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-141">Add the following `SaveUpdatedDefinition` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="02940-142">이 메서드는 업데이트 맵이 만들어진 후 업데이트된 워크플로 정의를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-142">This method saves the updated workflow definition once the update map is created.</span></span>

    ```vb
    Private Sub SaveUpdatedDefinition(wf As ActivityBuilder, name As String)
        Dim xamlPath As String = Path.Combine(definitionPath, name)
        Dim sw As StreamWriter = File.CreateText(xamlPath)
        Dim xw As XamlWriter = ActivityXamlServices.CreateBuilderWriter(
            New XamlXmlWriter(sw, New XamlSchemaContext()))
        XamlServices.Save(xw, wf)
        sw.Close()
    End Sub
    ```

    ```csharp
    private static void SaveUpdatedDefinition(ActivityBuilder wf, string name)
    {
        string xamlPath = Path.Combine(definitionPath, name);
        StreamWriter sw = File.CreateText(xamlPath);
        XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(
            new XamlXmlWriter(sw, new XamlSchemaContext()));
        XamlServices.Save(xw, wf);
        sw.Close();
    }
    ```

### <a name="to-update-statemachinenumberguessworkflow"></a><a name="BKMK_StateMachine"></a> <span data-ttu-id="02940-143">Statemachinenumberguessworkflow.xaml를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="02940-143">To update StateMachineNumberGuessWorkflow</span></span>

1. <span data-ttu-id="02940-144">`CreateStateMachineUpdateMap`(또는 `Program`) 클래스에 `Module1`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-144">Add a `CreateStateMachineUpdateMap` to the `Program` class (or `Module1`).</span></span>

    ```vb
    Private Sub CreateStateMachineUpdateMap()

    End Sub
    ```

    ```csharp
    private static void CreateStateMachineUpdateMap()
    {
    }
    ```

2. <span data-ttu-id="02940-145">`StartUpdate`를 호출하고 워크플로의 루트 `StateMachine` 활동에 대한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02940-145">Make a call to `StartUpdate` and then get a reference to the root `StateMachine` activity of the workflow.</span></span>

    ```vb
    Dim wf As ActivityBuilder = StartUpdate("StateMachineNumberGuessWorkflow.xaml")

    'Get a reference to the root StateMachine activity.
    Dim sm As StateMachine = wf.Implementation
    ```

    ```csharp
    ActivityBuilder wf = StartUpdate("StateMachineNumberGuessWorkflow.xaml");

    // Get a reference to the root StateMachine activity.
    StateMachine sm = wf.Implementation as StateMachine;
    ```

3. <span data-ttu-id="02940-146">다음으로, `WriteLine` [방법: 여러 버전의 워크플로를 함께 호스트 하는 방법](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)에 대 한 업데이트와 일치 하도록 사용자의 추측이 너무 많거나 너무 낮은 지 여부를 표시 하는 두 활동의 식을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-146">Next, update the expressions of the two `WriteLine` activities that display whether the user's guess is too high or too low so that they match the updates made in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

    ```vb
    'Update the Text of the two WriteLine activities that write the
    'results of the user's guess. They are contained in the workflow as the
    'Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
    Dim guessLow As Statements.If = sm.States(1).Transitions(1).Action

    'Update the "too low" message.
    Dim tooLow As WriteLine = guessLow.Then
    tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

    'Update the "too high" message.
    Dim tooHigh As WriteLine = guessLow.Else
    tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")
    ```

    ```csharp
    // Update the Text of the two WriteLine activities that write the
    // results of the user's guess. They are contained in the workflow as the
    // Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
    If guessLow = sm.States[1].Transitions[1].Action as If;

    // Update the "too low" message.
    WriteLine tooLow = guessLow.Then as WriteLine;
    tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

    // Update the "too high" message.
    WriteLine tooHigh = guessLow.Else as WriteLine;
    tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");
    ```

4. <span data-ttu-id="02940-147">그런 다음 닫기 메시지를 표시하는 새 `WriteLine` 활동을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-147">Next, add the new `WriteLine` activity that displays the closing message.</span></span>

    ```vb
    'Create the new WriteLine that displays the closing message.
    Dim wl As New WriteLine() With
    {
        .Text = New VisualBasicValue(Of String) _
            ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
    }

    'Add it as the Action for the Guess Correct transition. The Guess Correct
    'transition is the first transition of States[1]. The transitions are listed
    'at the bottom of the State activity designer.
    sm.States(1).Transitions(0).Action = wl
    ```

    ```csharp
    // Create the new WriteLine that displays the closing message.
    WriteLine wl = new WriteLine
    {
        Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
    };

    // Add it as the Action for the Guess Correct transition. The Guess Correct
    // transition is the first transition of States[1]. The transitions are listed
    // at the bottom of the State activity designer.
    sm.States[1].Transitions[0].Action = wl;
    ```

5. <span data-ttu-id="02940-148">워크플로가 업데이트된 후 `CreateUpdateMaps` 및 `SaveUpdatedDefinition`을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-148">After the workflow is updated, call `CreateUpdateMaps` and `SaveUpdatedDefinition`.</span></span> <span data-ttu-id="02940-149">`CreateUpdateMaps`는 `DynamicUpdateMap`을 만들고 저장하며, `SaveUpdatedDefinition`은 업데이트된 워크플로 정의를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-149">`CreateUpdateMaps` creates and saves the `DynamicUpdateMap`, and `SaveUpdatedDefinition` saves the updated workflow definition.</span></span>

    ```vb
    'Create the update map.
    CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map")

    'Save the updated workflow definition.
    SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml")
    ```

    ```csharp
    // Create the update map.
    CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map");

    // Save the updated workflow definition.
    SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml");
    ```

    <span data-ttu-id="02940-150">다음 예제는 전체 `CreateStateMachineUpdateMap` 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="02940-150">The following example is the completed `CreateStateMachineUpdateMap` method.</span></span>

    ```vb
    Private Sub CreateStateMachineUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("StateMachineNumberGuessWorkflow.xaml")

        'Get a reference to the root StateMachine activity.
        Dim sm As StateMachine = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
        Dim guessLow As Statements.If = sm.States(1).Transitions(1).Action

        'Update the "too low" message.
        Dim tooLow As WriteLine = guessLow.Then
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

        'Update the "too high" message.
        Dim tooHigh As WriteLine = guessLow.Else
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Add it as the Action for the Guess Correct transition. The Guess Correct
        'transition is the first transition of States[1]. The transitions are listed
        'at the bottom of the State activity designer.
        sm.States(1).Transitions(0).Action = wl

        'Create the update map.
        CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateStateMachineUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("StateMachineNumberGuessWorkflow.xaml");

        // Get a reference to the root StateMachine activity.
        StateMachine sm = wf.Implementation as StateMachine;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
        If guessLow = sm.States[1].Transitions[1].Action as If;

        // Update the "too low" message.
        WriteLine tooLow = guessLow.Then as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

        // Update the "too high" message.
        WriteLine tooHigh = guessLow.Else as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Create the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Add it as the Action for the Guess Correct transition. The Guess Correct
        // transition is the first transition of States[1]. The transitions are listed
        // at the bottom of the State activity designer.
        sm.States[1].Transitions[0].Action = wl;

        // Create the update map.
        CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map");

        // Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="to-update-flowchartnumberguessworkflow"></a><a name="BKMK_Flowchart"></a> <span data-ttu-id="02940-151">Flowchartnumberguessworkflow.xaml를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="02940-151">To update FlowchartNumberGuessWorkflow</span></span>

1. <span data-ttu-id="02940-152">`CreateFlowchartUpdateMethod`(또는 `Program`) 클래스에 다음 `Module1`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-152">Add the following `CreateFlowchartUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="02940-153">이 메서드는 `CreateStateMachineUpdateMap`과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-153">This method is similar to `CreateStateMachineUpdateMap`.</span></span> <span data-ttu-id="02940-154">이 메서드는 먼저 `StartUpdate`를 호출하고 순서도 워크플로 정의를 업데이트한 다음 업데이트 맵과 업데이트된 워크플로 정의를 저장하는 것으로 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-154">It starts with a call to `StartUpdate`, updates the flowchart workflow definition, and finishes by saving the update map and the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateFlowchartUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("FlowchartNumberGuessWorkflow.xaml")

        'Get a reference to the root Flowchart activity.
        Dim fc As Flowchart = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'True and False action of the "Guess < Target" FlowDecision, which is
        'Nodes[4].
        Dim guessLow As FlowDecision = fc.Nodes(4)

        'Update the "too low" message.
        Dim trueStep As FlowStep = guessLow.True
        Dim tooLow As WriteLine = trueStep.Action
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

        'Update the "too high" message.
        Dim falseStep As FlowStep = guessLow.False
        Dim tooHigh As WriteLine = falseStep.Action
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Create a FlowStep to hold the WriteLine.
        Dim closingStep As New FlowStep() With
        {
            .Action = wl
        }

        'Add this new FlowStep to the True action of the
        '"Guess = Guess" FlowDecision
        Dim guessCorrect As FlowDecision = fc.Nodes(3)
        guessCorrect.True = closingStep

        'Add the new FlowStep to the Nodes collection.
        'If closingStep was replacing an existing node then
        'we would need to remove that Step from the collection.
        'In this example there was no existing True step to remove.
        fc.Nodes.Add(closingStep)

        'Create the update map.
        CreateUpdateMaps(wf, "FlowchartNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "FlowchartNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateFlowchartUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("FlowchartNumberGuessWorkflow.xaml");

        // Get a reference to the root Flowchart activity.
        Flowchart fc = wf.Implementation as Flowchart;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // True and False action of the "Guess < Target" FlowDecision, which is
        // Nodes[4].
        FlowDecision guessLow = fc.Nodes[4] as FlowDecision;

        // Update the "too low" message.
        FlowStep trueStep = guessLow.True as FlowStep;
        WriteLine tooLow = trueStep.Action as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

        // Update the "too high" message.
        FlowStep falseStep = guessLow.False as FlowStep;
        WriteLine tooHigh = falseStep.Action as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Add the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Create a FlowStep to hold the WriteLine.
        FlowStep closingStep = new FlowStep
        {
            Action = wl
        };

        // Add this new FlowStep to the True action of the
        // "Guess == Guess" FlowDecision
        FlowDecision guessCorrect = fc.Nodes[3] as FlowDecision;
        guessCorrect.True = closingStep;

        // Add the new FlowStep to the Nodes collection.
        // If closingStep was replacing an existing node then
        // we would need to remove that Step from the collection.
        // In this example there was no existing True step to remove.
        fc.Nodes.Add(closingStep);

        // Create the update map.
        CreateUpdateMaps(wf, "FlowchartNumberGuessWorkflow.map");

        //  Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "FlowchartNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="to-update-sequentialnumberguessworkflow"></a><a name="BKMK_Sequential"></a> <span data-ttu-id="02940-155">Sequentialnumberguessworkflow.xaml를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="02940-155">To update SequentialNumberGuessWorkflow</span></span>

1. <span data-ttu-id="02940-156">`CreateSequentialUpdateMethod`(또는 `Program`) 클래스에 다음 `Module1`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-156">Add the following `CreateSequentialUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="02940-157">이 메서드는 다른 두 개의 메서드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-157">This method is similar to the other two methods.</span></span> <span data-ttu-id="02940-158">이 메서드는 먼저 `StartUpdate`를 호출하고 순차 워크플로 정의를 업데이트한 다음 업데이트 맵과 업데이트된 워크플로 정의를 저장하는 것으로 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-158">It starts with a call to `StartUpdate`, updates the sequential workflow definition, and finishes by saving the update map and the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateSequentialUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("SequentialNumberGuessWorkflow.xaml")

        'Get a reference to the root activity in the workflow.
        Dim rootSequence As Sequence = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'Then and Else action of the "Guess < Target" If activity.
        'Sequence[1]->DoWhile->Body->Sequence[2]->If->Then->If
        Dim gameLoop As Statements.DoWhile = rootSequence.Activities(1)
        Dim gameBody As Sequence = gameLoop.Body
        Dim guessCorrect As Statements.If = gameBody.Activities(2)
        Dim guessLow As Statements.If = guessCorrect.Then
        Dim tooLow As WriteLine = guessLow.Then
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")
        Dim tooHigh As WriteLine = guessLow.Else
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Insert it as the third activity in the root sequence
        rootSequence.Activities.Insert(2, wl)

        'Create the update map.
        CreateUpdateMaps(wf, "SequentialNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "SequentialNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateSequentialUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("SequentialNumberGuessWorkflow.xaml");

        // Get a reference to the root activity in the workflow.
        Sequence rootSequence = wf.Implementation as Sequence;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // Then and Else action of the "Guess < Target" If activity.
        // Sequence[1]->DoWhile->Body->Sequence[2]->If->Then->If
        DoWhile gameLoop = rootSequence.Activities[1] as DoWhile;
        Sequence gameBody = gameLoop.Body as Sequence;
        If guessCorrect = gameBody.Activities[2] as If;
        If guessLow = guessCorrect.Then as If;
        WriteLine tooLow = guessLow.Then as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");
        WriteLine tooHigh = guessLow.Else as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Add the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Insert it as the third activity in the root sequence
        rootSequence.Activities.Insert(2, wl);

        // Create the update map.
        CreateUpdateMaps(wf, "SequentialNumberGuessWorkflow.map");

        // Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "SequentialNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="to-build-and-run-the-createupdatemaps-application"></a><a name="BKMK_CreateUpdateMaps"></a> <span data-ttu-id="02940-159">CreateUpdateMaps 응용 프로그램을 빌드하고 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="02940-159">To build and run the CreateUpdateMaps application</span></span>

1. <span data-ttu-id="02940-160">`Main` 메서드를 업데이트하고 다음 세 개의 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-160">Update the `Main` method and add the following three method calls.</span></span> <span data-ttu-id="02940-161">이러한 메서드는 다음 단원에서 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="02940-161">These methods are added in the following sections.</span></span> <span data-ttu-id="02940-162">각 메서드는 해당 숫자 추측 워크플로를 업데이트하고 업데이트를 설명하는 `DynamicUpdateMap`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02940-162">Each method updates the corresponding number guess workflow and creates a `DynamicUpdateMap` that describes the updates.</span></span>

    ```vb
    Sub Main()
        'Create the update maps for the changes needed to the v1 activities
        'so they match the v2 activities.
        CreateSequentialUpdateMap()
        CreateFlowchartUpdateMap()
        CreateStateMachineUpdateMap()
    End Sub
    ```

    ```csharp
    static void Main(string[] args)
    {
        // Create the update maps for the changes needed to the v1 activities
        // so they match the v2 activities.
        CreateSequentialUpdateMap();
        CreateFlowchartUpdateMap();
        CreateStateMachineUpdateMap();
    }
    ```

2. <span data-ttu-id="02940-163">**솔루션 탐색기** 에서 **CreateUpdateMaps** 을 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-163">Right-click **CreateUpdateMaps** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

3. <span data-ttu-id="02940-164">Ctrl+Shift+B를 눌러 솔루션을 빌드하고 Ctrl+F5를 눌러 `CreateUpdateMaps` 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-164">Press CTRL+SHIFT+B to build the solution, and then CTRL+F5 to run the `CreateUpdateMaps` application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02940-165">`CreateUpdateMaps`응용 프로그램은 실행 하는 동안 상태 정보를 표시 하지 않지만 **NumberGuessWorkflowActivities_du** 폴더 및 **PreviousVersions** 폴더를 살펴보면 업데이트 된 워크플로 정의 파일 및 업데이트 맵이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02940-165">The `CreateUpdateMaps` application does not display any status information while running, but if you look in the **NumberGuessWorkflowActivities_du** folder and the **PreviousVersions** folder you will see the updated workflow definition files and the update maps.</span></span>

    <span data-ttu-id="02940-166">업데이트 맵이 만들어지고 워크플로 정의가 업데이트된 후 다음 단계는 업데이트된 정의를 포함하는 업데이트된 워크플로 어셈블리를 빌드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="02940-166">Once the update maps are created and the workflow definitions updated, the next step is to build an updated workflow assembly containing the updated definitions.</span></span>

### <a name="to-build-the-updated-workflow-assembly"></a><a name="BKMK_BuildAssembly"></a> <span data-ttu-id="02940-167">업데이트 된 워크플로 어셈블리를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="02940-167">To build the updated workflow assembly</span></span>

1. <span data-ttu-id="02940-168">Visual Studio 2012의 두 번째 인스턴스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="02940-168">Open a second instance of Visual Studio 2012.</span></span>

2. <span data-ttu-id="02940-169">**파일** 메뉴에서 **열기**, **프로젝트/솔루션** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-169">Choose **Open**, **Project/Solution** from the **File** menu.</span></span>

3. <span data-ttu-id="02940-170">[방법: 여러 버전의 워크플로를 함께 호스트 하는 방법](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)에서 만든 **NumberGuessWorkflowActivities_du** 폴더로 이동 하 고 **NumberGuessWorkflowActivities** (또는 **.vbproj**)를 선택한 다음 **열기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-170">Navigate to the **NumberGuessWorkflowActivities_du** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), select **NumberGuessWorkflowActivities.csproj** (or **vbproj**), and click **Open**.</span></span>

4. <span data-ttu-id="02940-171">**솔루션 탐색기** 에서 **sequentialnumberguessworkflow.xaml** 를 마우스 오른쪽 단추로 클릭 하 고 **프로젝트에서 제외** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-171">In **Solution Explorer**, right click **SequentialNumberGuessWorkflow.xaml** and choose **Exclude From Project**.</span></span> <span data-ttu-id="02940-172">**Flowchartnumberguessworkflow.xaml** 및 **statemachinenumberguessworkflow.xaml** 에 대해 동일한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-172">Do the same thing for **FlowchartNumberGuessWorkflow.xaml** and **StateMachineNumberGuessWorkflow.xaml**.</span></span> <span data-ttu-id="02940-173">이 단계에서는 프로젝트에서 이전 버전의 워크플로 정의를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-173">This step removes the previous versions of the workflow definitions from the project.</span></span>

5. <span data-ttu-id="02940-174">**프로젝트** 메뉴에서 **기존 항목 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-174">Choose **Add Existing Item** from the **Project** menu.</span></span>

6. <span data-ttu-id="02940-175">[방법: 여러 버전의 워크플로를 함께 호스트 하는 방법](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)에서 만든 **NumberGuessWorkflowActivities_du** 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-175">Navigate to the **NumberGuessWorkflowActivities_du** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

7. <span data-ttu-id="02940-176">**Xaml 파일 (.xaml;)을 선택 \* \* 합니다. xoml)** **의 파일 형식** 드롭다운 목록에서</span><span class="sxs-lookup"><span data-stu-id="02940-176">Choose **XAML Files (\*.xaml;\*.xoml)** from the **Files of type** drop-down list.</span></span>

8. <span data-ttu-id="02940-177">**SequentialNumberGuessWorkflow_du .xaml**, **FlowchartNumberGuessWorkflow_du** 및 **StateMachineNumberGuessWorkflow_du** 를 선택 하 고 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-177">Select **SequentialNumberGuessWorkflow_du.xaml**, **FlowchartNumberGuessWorkflow_du.xaml**, and **StateMachineNumberGuessWorkflow_du.xaml** and click **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02940-178">한 번에 여러 개의 항목을 선택하려면 Ctrl 키를 누른 상태로 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="02940-178">CTRL+Click to select multiple items at a time.</span></span>

    <span data-ttu-id="02940-179">이 단계에서는 프로젝트에 업데이트된 버전의 워크플로 정의를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-179">This step adds the updated versions of the workflow definitions to the project.</span></span>

9. <span data-ttu-id="02940-180">Ctrl+Shift+B를 눌러 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-180">Press CTRL+SHIFT+B to build the project.</span></span>

10. <span data-ttu-id="02940-181">**파일** 메뉴에서 **솔루션 닫기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-181">Choose **Close Solution** from the **File** menu.</span></span> <span data-ttu-id="02940-182">프로젝트에 대 한 솔루션 파일이 필요 하지 않으므로 **아니요** 를 클릭 하 여 솔루션 파일을 저장 하지 않고 Visual Studio를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-182">A solution file for the project is not required, so click **No** to close Visual Studio without saving a solution file.</span></span> <span data-ttu-id="02940-183">**파일** 메뉴에서 **끝내기** 를 선택 하 여 Visual Studio를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-183">Choose **Exit** from the **File** menu to close Visual Studio.</span></span>

11. <span data-ttu-id="02940-184">Windows 탐색기를 열고 **NumberGuessWorkflowActivities_du \bin\debug** 폴더 (또는 프로젝트 설정에 따라 **bin\Release** )로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-184">Open Windows Explorer and navigate to the **NumberGuessWorkflowActivities_du\bin\Debug** folder (or **bin\Release** depending on your project settings).</span></span>

12. <span data-ttu-id="02940-185">**NumberGuessWorkflowActivities.dll** 이름을 **NumberGuessWorkflowActivities_v15.dll** 로 바꾸고 [방법: 여러 버전의 워크플로를 함께 호스트 하는 방법](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)에서 만든 **PreviousVersions** 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-185">Rename **NumberGuessWorkflowActivities.dll** to **NumberGuessWorkflowActivities_v15.dll**, and copy it to the **PreviousVersions** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

### <a name="to-update-workflowversionmap-with-the-new-versions"></a><a name="BKMK_UpdateWorkflowVersionMap"></a> <span data-ttu-id="02940-186">새 버전으로 WorkflowVersionMap을 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="02940-186">To update WorkflowVersionMap with the new versions</span></span>

1. <span data-ttu-id="02940-187">Visual Studio 2012의 초기 인스턴스로 다시 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-187">Switch back to the initial instance of Visual Studio 2012.</span></span>

2. <span data-ttu-id="02940-188">**NumberGuessWorkflowHost** 프로젝트에서 **WorkflowVersionMap.cs** (또는 **workflowversionmap .vb**)를 두 번 클릭 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="02940-188">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>

3. <span data-ttu-id="02940-189">여섯 개의 기존 워크플로 ID 선언 바로 아래에 세 개의 새 워크플로 ID를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-189">Add three new workflow identities just below the six existing workflow identity declarations.</span></span> <span data-ttu-id="02940-190">이 자습서에서는 `1.5.0.0`이 동적 업데이트 ID의 `WorkflowIdentity.Version`으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="02940-190">In this tutorial, `1.5.0.0` is used as the `WorkflowIdentity.Version` for the dynamic update identities.</span></span> <span data-ttu-id="02940-191">이러한 새 `v15` 워크플로 ID는 동적으로 업데이트된 지속형 워크플로 인스턴스에 대한 올바른 워크플로 정의를 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="02940-191">These new `v15` workflow identities will be used provide the correct workflow definition for the dynamically updated persisted workflow instances.</span></span>

    ```vb
    'Current version identities.
    Public StateMachineNumberGuessIdentity As WorkflowIdentity
    Public FlowchartNumberGuessIdentity As WorkflowIdentity
    Public SequentialNumberGuessIdentity As WorkflowIdentity

    'v1 identities.
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

    'v1.5 (Dynamic Update) identities.
    Public StateMachineNumberGuessIdentity_v15 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v15 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v15 As WorkflowIdentity
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

    // v1.5 (Dynamic Update) identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v15;
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v15;
    static public WorkflowIdentity SequentialNumberGuessIdentity_v15;
    ```

4. <span data-ttu-id="02940-192">생성자의 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-192">Add the following code at the end of the constructor.</span></span> <span data-ttu-id="02940-193">이 코드는 동적 업데이트 워크플로 ID를 초기화하고 해당 워크플로 정의를 로드한 후 워크플로 버전 사전에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-193">This code initializes the dynamic update workflow identities, loads the corresponding workflow definitions, and adds them to the workflow version dictionary.</span></span>

    ```vb
    'Initialize the dynamic update workflow identities.
    StateMachineNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    FlowchartNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    SequentialNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    'Add the dynamic update workflow identities to the dictionary along with
    'the corresponding workflow definitions loaded from the v15 assembly.
    'Assembly.LoadFile requires an absolute path so convert this relative path
    'to an absolute path.
    Dim v15AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll"
    v15AssemblyPath = Path.GetFullPath(v15AssemblyPath)
    Dim v15Assembly As Assembly = Assembly.LoadFile(v15AssemblyPath)

    map.Add(StateMachineNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

    map.Add(SequentialNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

    map.Add(FlowchartNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
    ```

    ```csharp
    // Initialize the dynamic update workflow identities.
    StateMachineNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    FlowchartNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    SequentialNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    // Add the dynamic update workflow identities to the dictionary along with
    // the corresponding workflow definitions loaded from the v15 assembly.
    // Assembly.LoadFile requires an absolute path so convert this relative path
    // to an absolute path.
    string v15AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll";
    v15AssemblyPath = Path.GetFullPath(v15AssemblyPath);
    Assembly v15Assembly = Assembly.LoadFile(v15AssemblyPath);

    map.Add(StateMachineNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

    map.Add(SequentialNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

    map.Add(FlowchartNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
    ```

     <span data-ttu-id="02940-194">다음 예제는 전체 `WorkflowVersionMap` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="02940-194">The following example is the completed `WorkflowVersionMap` class.</span></span>

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        'Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        'v1 identities.
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

        'v1.5 (Dynamic Update) identities.
        Public StateMachineNumberGuessIdentity_v15 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v15 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v15 As WorkflowIdentity

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

            'Initialize the dynamic update workflow identities.
            StateMachineNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            FlowchartNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            SequentialNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            'Add the dynamic update workflow identities to the dictionary along with
            'the corresponding workflow definitions loaded from the v15 assembly.
            'Assembly.LoadFile requires an absolute path so convert this relative path
            'to an absolute path.
            Dim v15AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll"
            v15AssemblyPath = Path.GetFullPath(v15AssemblyPath)
            Dim v15Assembly As Assembly = Assembly.LoadFile(v15AssemblyPath)

            map.Add(StateMachineNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

            map.Add(SequentialNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

            map.Add(FlowchartNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
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

        // v1.5 (Dynamic Update) identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v15;
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v15;
        static public WorkflowIdentity SequentialNumberGuessIdentity_v15;

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

            // Initialize the dynamic update workflow identities.
            StateMachineNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            FlowchartNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            SequentialNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            // Add the dynamic update workflow identities to the dictionary along with
            // the corresponding workflow definitions loaded from the v15 assembly.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            string v15AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll";
            v15AssemblyPath = Path.GetFullPath(v15AssemblyPath);
            Assembly v15Assembly = Assembly.LoadFile(v15AssemblyPath);

            map.Add(StateMachineNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

            map.Add(SequentialNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

            map.Add(FlowchartNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
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

5. <span data-ttu-id="02940-195">Ctrl+Shift+B를 눌러 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-195">Press CTRL+SHIFT+B to build the project.</span></span>

### <a name="to-apply-the-dynamic-updates"></a><a name="BKMK_ApplyUpdate"></a> <span data-ttu-id="02940-196">동적 업데이트를 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="02940-196">To apply the dynamic updates</span></span>

1. <span data-ttu-id="02940-197">**솔루션 탐색기** 에서 **WF45GettingStartedTutorial** 을 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 프로젝트** 를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-197">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>

2. <span data-ttu-id="02940-198">**설치 됨** 노드에서 **Visual c #**, **windows** (또는 **Visual Basic**, **windows**)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-198">In the **Installed** node, select **Visual C#**, **Windows** (or **Visual Basic**, **Windows**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="02940-199">Visual Studio에서 기본 언어로 구성되어 있는 프로그래밍 언어에 따라 **Visual C#** 또는 **Visual Basic** 노드는 **설치됨** 노드의 **다른 언어** 노드에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-199">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

    <span data-ttu-id="02940-200">.NET Framework 버전 드롭다운 목록에서 **.NET Framework 4.5** 가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-200">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="02940-201">**Windows** 목록에서 **콘솔 응용 프로그램** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-201">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="02940-202">**이름** 상자에 **ApplyDynamicUpdate** 를 입력 하 고 **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-202">Type **ApplyDynamicUpdate** into the **Name** box and click **OK**.</span></span>

3. <span data-ttu-id="02940-203">**솔루션 탐색기** 에서 **ApplyDynamicUpdate** 을 마우스 오른쪽 단추로 클릭 하 고 **참조 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-203">Right-click **ApplyDynamicUpdate** in **Solution Explorer** and choose **Add Reference**.</span></span>

4. <span data-ttu-id="02940-204">**솔루션** 을 클릭 하 고 **NumberGuessWorkflowHost** 옆의 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-204">Click **Solution** and check the box next to **NumberGuessWorkflowHost**.</span></span> <span data-ttu-id="02940-205">이 참조는 `ApplyDynamicUpdate`에서 `NumberGuessWorkflowHost.WorkflowVersionMap` 클래스를 사용하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-205">This reference is needed so that `ApplyDynamicUpdate` can use the `NumberGuessWorkflowHost.WorkflowVersionMap` class.</span></span>

5. <span data-ttu-id="02940-206">**참조 추가** 목록의 **어셈블리** 노드에서 **프레임 워크** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-206">Select **Framework** from the **Assemblies** node in the **Add Reference** list.</span></span> <span data-ttu-id="02940-207">**어셈블리 검색** 상자에 **system.object** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-207">Type **System.Activities** into the **Search Assemblies** box.</span></span> <span data-ttu-id="02940-208">그러면 어셈블리가 필터링되므로 원하는 참조를 손쉽게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-208">This will filter the assemblies and make the desired references easier to select.</span></span>

6. <span data-ttu-id="02940-209">**검색 결과** 목록에서 **System. 작업** 옆의 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-209">Check the checkbox beside **System.Activities** from the **Search Results** list.</span></span>

7. <span data-ttu-id="02940-210">**어셈블리 검색** 상자에 **Serialization** 을 입력 하 고 **검색 결과** 목록에서 **system.object** 옆의 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-210">Type **Serialization** into the **Search Assemblies** box, and check the checkbox beside **System.Runtime.Serialization** from the **Search Results** list.</span></span>

8. <span data-ttu-id="02940-211">**어셈블리 검색** 상자에 **DurableInstancing** 를 입력 하 고 **검색 결과** 목록에서 **DurableInstancing** 및 **DurableInstancing** 옆에 있는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-211">Type **DurableInstancing** into the **Search Assemblies** box, and check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list.</span></span>

9. <span data-ttu-id="02940-212">**확인** 을 클릭 하 여 **참조 관리자** 를 닫고 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-212">Click **OK** to close **Reference Manager** and add the references.</span></span>

10. <span data-ttu-id="02940-213">솔루션 탐색기에서 **ApplyDynamicUpdate** 을 마우스 오른쪽 단추로 클릭 하 고 **추가**, **클래스** 를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-213">Right-click **ApplyDynamicUpdate** in Solution Explorer and choose **Add**, **Class**.</span></span> <span data-ttu-id="02940-214">`DynamicUpdateInfo` **이름** 상자에를 입력 하 고 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-214">Type `DynamicUpdateInfo` into the **Name** box and click **Add**.</span></span>

11. <span data-ttu-id="02940-215">`DynamicUpdateInfo` 클래스에 다음 두 개의 멤버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-215">Add the following two members to the `DynamicUpdateInfo` class.</span></span> <span data-ttu-id="02940-216">다음 예제는 전체 `DynamicUpdateInfo` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="02940-216">The following example is the completed `DynamicUpdateInfo` class.</span></span> <span data-ttu-id="02940-217">이 클래스에는 워크플로 인스턴스가 업데이트될 때 사용되는 업데이트 맵 및 새 워크플로 ID에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-217">This class contains information on the update map and new workflow identity used when a workflow instance is updated.</span></span>

    ```vb
    Public Class DynamicUpdateInfo
        Public updateMap As DynamicUpdateMap
        Public newIdentity As WorkflowIdentity
    End Class
    ```

    ```csharp
    class DynamicUpdateInfo
    {
        public DynamicUpdateMap updateMap;
        public WorkflowIdentity newIdentity;
    }
    ```

12. <span data-ttu-id="02940-218">다음 `using`(또는 `Imports`) 문을 파일의 맨 위에 다른 `using`(또는 `Imports`) 문과 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-218">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.DynamicUpdate
    ```

    ```csharp
    using System.Activities;
    using System.Activities.DynamicUpdate;
    ```

13. <span data-ttu-id="02940-219">솔루션 탐색기에서 **Program.cs** **(또는 module1.vb**)를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-219">Double-click **Program.cs** (or **Module1.vb**) in Solution Explorer.</span></span>

14. <span data-ttu-id="02940-220">다음 `using`(또는 `Imports`) 문을 파일의 맨 위에 다른 `using`(또는 `Imports`) 문과 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-220">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports NumberGuessWorkflowHost
    Imports System.Data.SqlClient
    Imports System.Activities.DynamicUpdate
    Imports System.IO
    Imports System.Runtime.Serialization
    Imports System.Activities
    Imports System.Activities.DurableInstancing
    ```

    ```csharp
    using NumberGuessWorkflowHost;
    using System.Data;
    using System.Data.SqlClient;
    using System.Activities;
    using System.Activities.DynamicUpdate;
    using System.IO;
    using System.Runtime.Serialization;
    using System.Activities.DurableInstancing;
    ```

15. <span data-ttu-id="02940-221">`Program`(또는 `Module1`) 클래스에 다음 연결 문자열 멤버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-221">Add the following connection string member to the `Program` class (or `Module1`).</span></span>

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    ```

    > [!NOTE]
    > <span data-ttu-id="02940-222">SQL Server 에디션에 따라 연결 문자열 서버 이름이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-222">Depending on your edition of SQL Server, the connection string server name may be different.</span></span>

16. <span data-ttu-id="02940-223">`GetIDs`(또는 `Program`) 클래스에 다음 `Module1` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-223">Add the following `GetIDs` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="02940-224">이 메서드는 지속형 워크플로 인스턴스 ID의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-224">This method returns a list of persisted workflow instance ids.</span></span>

    ```vb
    Function GetIds() As IList(Of Guid)
        Dim Ids As New List(Of Guid)
        Dim localCmd = _
            String.Format("Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]")
        Using localCon = New SqlConnection(connectionString)
            Dim cmd As SqlCommand = localCon.CreateCommand()
            cmd.CommandText = localCmd
            localCon.Open()
            Using reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)
                While reader.Read()
                    'Get the InstanceId of the persisted Workflow
                    Dim id As Guid = Guid.Parse(reader(0).ToString())

                    'Add it to the list.
                    Ids.Add(id)
                End While
            End Using
        End Using

        Return Ids
    End Function
    ```

    ```csharp
    static IList<Guid> GetIds()
    {
        List<Guid> Ids = new List<Guid>();
        string localCmd = string.Format("Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]");
        using (SqlConnection localCon = new SqlConnection(connectionString))
        {
            SqlCommand cmd = localCon.CreateCommand();
            cmd.CommandText = localCmd;
            localCon.Open();
            using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))
            {
                while (reader.Read())
                {
                    // Get the InstanceId of the persisted Workflow
                    Guid id = Guid.Parse(reader[0].ToString());

                    // Add it to the list.
                    Ids.Add(id);
                }
            }
        }

        return Ids;
    }
    ```

17. <span data-ttu-id="02940-225">`LoadMap`(또는 `Program`) 클래스에 다음 `Module1` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-225">Add the following `LoadMap` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="02940-226">이 메서드는 `v1` 워크플로 ID를 해당 지속형 워크플로 인스턴스를 업데이트하는 데 사용되는 업데이트 맵과 새 워크플로 ID에 매핑하는 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02940-226">This method creates a dictionary that maps `v1` workflow identities to the update maps and new workflow identities used to update the corresponding persisted workflow instances.</span></span>

    ```vb
    Function LoadMap(mapName As String) As DynamicUpdateMap
        Dim mapPath As String = Path.Combine("..\..\..\PreviousVersions", mapName)

        Dim map As DynamicUpdateMap
        Using fs As FileStream = File.Open(mapPath, FileMode.Open)
            Dim serializer As DataContractSerializer = New DataContractSerializer(GetType(DynamicUpdateMap))
            Dim updateMap = serializer.ReadObject(fs)
            If updateMap Is Nothing Then
                Throw New ApplicationException("DynamicUpdateMap is null.")
            End If

            map = updateMap
        End Using

        Return map
    End Function
    ```

    ```csharp
    static DynamicUpdateMap LoadMap(string mapName)
    {
        string path = Path.Combine(@"..\..\..\PreviousVersions", mapName);

        DynamicUpdateMap map;
        using (FileStream fs = File.Open(path, FileMode.Open))
        {
            DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));
            object updateMap = serializer.ReadObject(fs);
            if (updateMap == null)
            {
                throw new ApplicationException("DynamicUpdateMap is null.");
            }

            map = updateMap as DynamicUpdateMap;
        }

        return map;
    }
    ```

18. <span data-ttu-id="02940-227">`LoadMaps`(또는 `Program`) 클래스에 다음 `Module1` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-227">Add the following `LoadMaps` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="02940-228">이 메서드는 세 개의 업데이트 맵을 로드하고 `v1` 워크플로 ID를 업데이트 맵에 매핑하는 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02940-228">This method loads the three update maps and creates a dictionary that maps `v1` workflow identities to the update maps.</span></span>

    ```vb
    Function LoadMaps() As IDictionary(Of WorkflowIdentity, DynamicUpdateInfo)
        'There are 3 update maps to describe the changes to update v1 workflows,
        'one for reach of the 3 workflow types in the tutorial.
        Dim maps = New Dictionary(Of WorkflowIdentity, DynamicUpdateInfo)()

        Dim sequentialMap As DynamicUpdateMap = LoadMap("SequentialNumberGuessWorkflow.map")
        Dim sequentialInfo = New DynamicUpdateInfo With
        {
            .updateMap = sequentialMap,
            .newIdentity = WorkflowVersionMap.SequentialNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.SequentialNumberGuessIdentity_v1, sequentialInfo)

        Dim stateMap As DynamicUpdateMap = LoadMap("StateMachineNumberGuessWorkflow.map")
        Dim stateInfo = New DynamicUpdateInfo With
        {
            .updateMap = stateMap,
            .newIdentity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.StateMachineNumberGuessIdentity_v1, stateInfo)

        Dim flowchartMap As DynamicUpdateMap = LoadMap("FlowchartNumberGuessWorkflow.map")
        Dim flowchartInfo = New DynamicUpdateInfo With
        {
            .updateMap = flowchartMap,
            .newIdentity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.FlowchartNumberGuessIdentity_v1, flowchartInfo)

        Return maps
    End Function
    ```

    ```csharp
    static IDictionary<WorkflowIdentity, DynamicUpdateInfo> LoadMaps()
    {
        // There are 3 update maps to describe the changes to update v1 workflows,
        // one for reach of the 3 workflow types in the tutorial.
        Dictionary<WorkflowIdentity, DynamicUpdateInfo> maps =
            new Dictionary<WorkflowIdentity, DynamicUpdateInfo>();

        DynamicUpdateMap sequentialMap = LoadMap("SequentialNumberGuessWorkflow.map");
        DynamicUpdateInfo sequentialInfo = new DynamicUpdateInfo
        {
            updateMap = sequentialMap,
            newIdentity = WorkflowVersionMap.SequentialNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.SequentialNumberGuessIdentity_v1, sequentialInfo);

        DynamicUpdateMap stateMap = LoadMap("StateMachineNumberGuessWorkflow.map");
        DynamicUpdateInfo stateInfo = new DynamicUpdateInfo
        {
            updateMap = stateMap,
            newIdentity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.StateMachineNumberGuessIdentity_v1, stateInfo);

        DynamicUpdateMap flowchartMap = LoadMap("FlowchartNumberGuessWorkflow.map");
        DynamicUpdateInfo flowchartInfo = new DynamicUpdateInfo
        {
            updateMap = flowchartMap,
            newIdentity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.FlowchartNumberGuessIdentity_v1, flowchartInfo);

        return maps;
    }
    ```

19. <span data-ttu-id="02940-229">다음 코드를 `Main`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-229">Add the following code to `Main`.</span></span> <span data-ttu-id="02940-230">이 코드는 지속형 워크플로 인스턴스를 반복하고 각 `WorkflowIdentity`를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-230">This code iterates the persisted workflow instances and examines each `WorkflowIdentity`.</span></span> <span data-ttu-id="02940-231">`WorkflowIdentity`가 `v1` 워크플로 인스턴스에 매핑되면 업데이트된 워크플로 정의와 업데이트된 워크플로 ID로 `WorkflowApplication`이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="02940-231">If the `WorkflowIdentity` maps to a `v1` workflow instance, a `WorkflowApplication` is configured with the updated workflow definition and an updated workflow identity.</span></span> <span data-ttu-id="02940-232">그런 다음 해당 인스턴스와 업데이트 맵을 사용하여 `WorkflowApplication.Load`가 호출되고 동적 업데이트 맵이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="02940-232">Next, `WorkflowApplication.Load` is called with the instance and the update map, which applies the dynamic update map.</span></span> <span data-ttu-id="02940-233">업데이트가 적용된 후 업데이트된 인스턴스는 `Unload`에 대한 호출을 통해 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="02940-233">Once the update is applied, the updated instance is persisted with a call to `Unload`.</span></span>

    ```vb
    Dim store = New SqlWorkflowInstanceStore(connectionString)
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)

    Dim updateMaps As IDictionary(Of WorkflowIdentity, DynamicUpdateInfo) = LoadMaps()

    For Each id As Guid In GetIds()
        'Get a proxy to the instance.
        Dim instance As WorkflowApplicationInstance = WorkflowApplication.GetInstance(id, store)

        Console.WriteLine("Inspecting: {0}", instance.DefinitionIdentity)

        'Only update v1 workflows.
        If Not instance.DefinitionIdentity Is Nothing AndAlso _
            instance.DefinitionIdentity.Version.Equals(New Version(1, 0, 0, 0)) Then

            Dim info As DynamicUpdateInfo = updateMaps(instance.DefinitionIdentity)

            'Associate the persisted WorkflowApplicationInstance with
            'a WorkflowApplication that is configured with the updated
            'definition and updated WorkflowIdentity.
            Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(info.newIdentity)
            Dim wfApp = New WorkflowApplication(wf, info.newIdentity)

            'Apply the Dynamic Update.
            wfApp.Load(instance, info.updateMap)

            'Persist the updated instance.
            wfApp.Unload()

            Console.WriteLine("Updated to: {0}", info.newIdentity)
        Else
            'Not updating this instance, so unload it.
            instance.Abandon()
        End If
    Next
    ```

    ```csharp
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);

    IDictionary<WorkflowIdentity, DynamicUpdateInfo> updateMaps = LoadMaps();

    foreach (Guid id in GetIds())
    {
        // Get a proxy to the instance.
        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(id, store);

        Console.WriteLine("Inspecting: {0}", instance.DefinitionIdentity);

        // Only update v1 workflows.
        if (instance.DefinitionIdentity != null &&
            instance.DefinitionIdentity.Version.Equals(new Version(1, 0, 0, 0)))
        {
            DynamicUpdateInfo info = updateMaps[instance.DefinitionIdentity];

            // Associate the persisted WorkflowApplicationInstance with
            // a WorkflowApplication that is configured with the updated
            // definition and updated WorkflowIdentity.
            Activity wf = WorkflowVersionMap.GetWorkflowDefinition(info.newIdentity);
            WorkflowApplication wfApp =
                new WorkflowApplication(wf, info.newIdentity);

            // Apply the Dynamic Update.
            wfApp.Load(instance, info.updateMap);

            // Persist the updated instance.
            wfApp.Unload();

            Console.WriteLine("Updated to: {0}", info.newIdentity);
        }
        else
        {
            // Not updating this instance, so unload it.
            instance.Abandon();
        }
    }
    ```

20. <span data-ttu-id="02940-234">**솔루션 탐색기** 에서 **ApplyDynamicUpdate** 을 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-234">Right-click **ApplyDynamicUpdate** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

21. <span data-ttu-id="02940-235">Ctrl+Shift+B를 눌러 솔루션을 빌드하고 Ctrl+F5를 눌러 `ApplyDynamicUpdate` 애플리케이션을 실행한 다음 지속형 워크플로 인스턴스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-235">Press CTRL+SHIFT+B to build the solution, and then press CTRL+F5 to run the `ApplyDynamicUpdate` application and update the persisted workflow instances.</span></span> <span data-ttu-id="02940-236">다음과 비슷한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="02940-236">You should see output similar to the following.</span></span> <span data-ttu-id="02940-237">버전 1.0.0.0 워크플로는 버전 1.5.0.0으로 업데이트되는 반면에 버전 2.0.0.0 워크플로는 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-237">The version 1.0.0.0 workflows are updated to version 1.5.0.0, while the version 2.0.0.0 workflows are not updated.</span></span>

    <span data-ttu-id="02940-238">**검사 중: Statemachinenumberguessworkflow.xaml; 버전 = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-238">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="02940-239">**다음으로 업데이트 됨: Statemachinenumberguessworkflow.xaml; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-239">**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="02940-240">**검사 중: Statemachinenumberguessworkflow.xaml; 버전 = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-240">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="02940-241">**다음으로 업데이트 됨: Statemachinenumberguessworkflow.xaml; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-241">**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="02940-242">**검사 중: Flowchartnumberguessworkflow.xaml; 버전 = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-242">**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="02940-243">**다음으로 업데이트 됨: Flowchartnumberguessworkflow.xaml; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-243">**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="02940-244">**검사 중: Flowchartnumberguessworkflow.xaml; 버전 = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-244">**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="02940-245">**다음으로 업데이트 됨: Flowchartnumberguessworkflow.xaml; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-245">**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="02940-246">**검사 중: Sequentialnumberguessworkflow.xaml; 버전 = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-246">**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="02940-247">**다음으로 업데이트 됨: Sequentialnumberguessworkflow.xaml; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-247">**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="02940-248">**검사 중: Sequentialnumberguessworkflow.xaml; 버전 = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-248">**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="02940-249">**다음으로 업데이트 됨: Sequentialnumberguessworkflow.xaml; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-249">**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="02940-250">**검사 중: Sequentialnumberguessworkflow.xaml; 버전 = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-250">**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="02940-251">**다음으로 업데이트 됨: Sequentialnumberguessworkflow.xaml; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-251">**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="02940-252">**검사 중: Statemachinenumberguessworkflow.xaml; 버전 = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-252">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="02940-253">**다음으로 업데이트 됨: Statemachinenumberguessworkflow.xaml; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-253">**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="02940-254">**검사 중: Flowchartnumberguessworkflow.xaml; 버전 = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-254">**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="02940-255">**다음으로 업데이트 됨: Flowchartnumberguessworkflow.xaml; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-255">**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="02940-256">**검사 중: Statemachinenumberguessworkflow.xaml; Version = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-256">**Inspecting: StateMachineNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="02940-257">**검사 중: Statemachinenumberguessworkflow.xaml; Version = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-257">**Inspecting: StateMachineNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="02940-258">**검사 중: Flowchartnumberguessworkflow.xaml; Version = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-258">**Inspecting: FlowchartNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="02940-259">**검사 중: Flowchartnumberguessworkflow.xaml; Version = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-259">**Inspecting: FlowchartNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="02940-260">**검사 중: Sequentialnumberguessworkflow.xaml; Version = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-260">**Inspecting: SequentialNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="02940-261">**검사 중: Sequentialnumberguessworkflow.xaml; Version = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="02940-261">**Inspecting: SequentialNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="02940-262">**계속 하려면 아무 키나 누르십시오.**</span><span class="sxs-lookup"><span data-stu-id="02940-262">**Press any key to continue . . .**</span></span>

### <a name="to-run-the-application-with-the-updated-workflows"></a><a name="BKMK_BuildAndRun"></a> <span data-ttu-id="02940-263">업데이트 된 워크플로를 사용 하 여 응용 프로그램을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="02940-263">To run the application with the updated workflows</span></span>

1. <span data-ttu-id="02940-264">**솔루션 탐색기** 에서 **NumberGuessWorkflowHost** 을 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-264">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

2. <span data-ttu-id="02940-265">Ctrl+F5를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-265">Press CTRL+F5 to run the application.</span></span>

3. <span data-ttu-id="02940-266">**새 게임** 을 클릭 하 여 새 워크플로를 시작 하 고 워크플로가 워크플로 임을 나타내는 상태 창 아래의 버전 정보를 확인 합니다 `v2` .</span><span class="sxs-lookup"><span data-stu-id="02940-266">Click **New Game** to start a new workflow and note the version information below the status window that indicates the workflow is a `v2` workflow.</span></span>

4. <span data-ttu-id="02940-267">`v1` [방법: 여러 버전의 워크플로를 함께 호스트 하는 방법](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) 항목의 시작 부분에서 시작 하는 워크플로 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-267">Select one of the `v1` workflows you started at the beginning of the [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) topic.</span></span> <span data-ttu-id="02940-268">상태 창 아래의 버전 정보는 워크플로가 버전 **1.5.0.0** 워크플로 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="02940-268">Note that the version information under the status window indicates that the workflow is a version **1.5.0.0** workflow.</span></span> <span data-ttu-id="02940-269">추측 값이 너무 높거나 너무 낮은지 여부 외에도 이전 추측 값에 대해 표시된 정보가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-269">Note that there is no information indicated about previous guesses other than whether they were too high or too low.</span></span>

    <span data-ttu-id="02940-270">**1에서 10 사이의 숫자를 입력 하십시오.**</span><span class="sxs-lookup"><span data-stu-id="02940-270">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="02940-271">**Your guess is too low.**</span><span class="sxs-lookup"><span data-stu-id="02940-271">**Your guess is too low.**</span></span>

5. <span data-ttu-id="02940-272">`InstanceId`를 적어 두고 워크플로가 완료될 때까지 추측 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-272">Make a note of the `InstanceId` and then enter guesses until the workflow completes.</span></span> <span data-ttu-id="02940-273">`WriteLine` 활동은 동적 업데이트에 의해 업데이트되었으므로 상태 창에는 추측 내용에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="02940-273">The status window displays information about the content of the guess because the `WriteLine` activities were updated by the dynamic update.</span></span>

    <span data-ttu-id="02940-274">**1에서 10 사이의 숫자를 입력 하십시오.**</span><span class="sxs-lookup"><span data-stu-id="02940-274">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="02940-275">**추측이 너무 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="02940-275">**Your guess is too low.**</span></span>\
    <span data-ttu-id="02940-276">**1에서 10 사이의 숫자를 입력 하십시오.**</span><span class="sxs-lookup"><span data-stu-id="02940-276">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="02940-277">**5가 너무 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="02940-277">**5 is too low.**</span></span>\
    <span data-ttu-id="02940-278">**1에서 10 사이의 숫자를 입력 하십시오.**</span><span class="sxs-lookup"><span data-stu-id="02940-278">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="02940-279">**7이 너무 높습니다.**</span><span class="sxs-lookup"><span data-stu-id="02940-279">**7 is too high.**</span></span>\
    <span data-ttu-id="02940-280">**1에서 10 사이의 숫자를 입력 하십시오.**</span><span class="sxs-lookup"><span data-stu-id="02940-280">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="02940-281">**Congratulations, you guessed the number in 4 turns.**</span><span class="sxs-lookup"><span data-stu-id="02940-281">**Congratulations, you guessed the number in 4 turns.**</span></span>

6. <span data-ttu-id="02940-282">Windows 탐색기를 열고 **NumberGuessWorkflowHost\bin\debug** 폴더 (또는 프로젝트 설정에 따라 **bin\release** )로 이동 하 여 완료 된 워크플로에 해당 하는 메모장을 사용 하 여 추적 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="02940-282">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="02940-283">을 적어 서 확인 하지 않은 경우 `InstanceId` Windows 탐색기에서 **수정한 날짜** 정보를 사용 하 여 올바른 추적 파일을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-283">If you did not make a note of the `InstanceId` you may be able to identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span> <span data-ttu-id="02940-284">추적 정보의 마지막 줄에는 새로 추가된 `WriteLine` 활동의 출력이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="02940-284">The last line of the tracking information contains the output of the newly added `WriteLine` activity.</span></span>

    <span data-ttu-id="02940-285">**1에서 10 사이의 숫자를 입력 하십시오.**</span><span class="sxs-lookup"><span data-stu-id="02940-285">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="02940-286">**추측이 너무 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="02940-286">**Your guess is too low.**</span></span>\
    <span data-ttu-id="02940-287">**1에서 10 사이의 숫자를 입력 하십시오.**</span><span class="sxs-lookup"><span data-stu-id="02940-287">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="02940-288">**5가 너무 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="02940-288">**5 is too low.**</span></span>\
    <span data-ttu-id="02940-289">**1에서 10 사이의 숫자를 입력 하십시오.**</span><span class="sxs-lookup"><span data-stu-id="02940-289">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="02940-290">**7이 너무 높습니다.**</span><span class="sxs-lookup"><span data-stu-id="02940-290">**7 is too high.**</span></span>\
    <span data-ttu-id="02940-291">**1에서 10 사이의 숫자를 입력 하십시오.**</span><span class="sxs-lookup"><span data-stu-id="02940-291">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="02940-292">**6이 올바릅니다. 4 개의 전환으로 추측 했습니다.**</span><span class="sxs-lookup"><span data-stu-id="02940-292">**6 is correct. You guessed it in 4 turns.**</span></span>

### <a name="to-enable-starting-previous-versions-of-the-workflows"></a><a name="BKMK_StartPreviousVersions"></a> <span data-ttu-id="02940-293">이전 버전의 워크플로를 시작 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="02940-293">To enable starting previous versions of the workflows</span></span>

<span data-ttu-id="02940-294">업데이트할 워크플로가 모두 실행된 경우 이전 버전의 워크플로를 시작하도록 `NumberGuessWorkflowHost` 애플리케이션을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-294">If you run out of workflows to update, you can modify the `NumberGuessWorkflowHost` application to enable starting previous versions of the workflows.</span></span>

1. <span data-ttu-id="02940-295">**솔루션 탐색기** 에서 **WorkflowHostForm** 를 두 번 클릭 하 고 **WorkflowType** 콤보 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-295">Double-click **WorkflowHostForm** in **Solution Explorer**, and select the **WorkflowType** combo box.</span></span>

2. <span data-ttu-id="02940-296">**속성** 창에서 **항목** 속성을 선택 하 고 줄임표 단추를 클릭 하 여 **항목** 컬렉션을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-296">In the **Properties** window, select the **Items** property and click the ellipsis button to edit the **Items** collection.</span></span>

3. <span data-ttu-id="02940-297">이 컬렉션에 다음 세 가지 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-297">Add the following three items to the collection.</span></span>

    ```
    StateMachineNumberGuessWorkflow v1
    FlowchartNumberGuessWorkflow v1
    SequentialNumberGuessWorkflow v1
    ```

    <span data-ttu-id="02940-298">완료된 `Items` 컬렉션에는 여섯 개의 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="02940-298">The completed `Items` collection will have six items.</span></span>

    ```
    StateMachineNumberGuessWorkflow
    FlowchartNumberGuessWorkflow
    SequentialNumberGuessWorkflow
    StateMachineNumberGuessWorkflow v1
    FlowchartNumberGuessWorkflow v1
    SequentialNumberGuessWorkflow v1
    ```

4. <span data-ttu-id="02940-299">**솔루션 탐색기** 에서 **WorkflowHostForm** 를 두 번 클릭 하 고 **코드 보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-299">Double-click **WorkflowHostForm** in **Solution Explorer**, and select **View Code**.</span></span>

5. <span data-ttu-id="02940-300">`switch`처리기에서 (또는) 문에 세 개의 새 사례를 추가 `Select Case` 하 여 `NewGame_Click` **WorkflowType** 콤보 상자의 새 항목을 일치 하는 워크플로 id에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-300">Add three new cases to the `switch` (or `Select Case`) statement in the `NewGame_Click` handler to map the new items in the **WorkflowType** combo box to the matching workflow identities.</span></span>

    ```vb
    Case "SequentialNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1

    Case "StateMachineNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1

    Case "FlowchartNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1
    ```

    ```csharp
    case "SequentialNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1;
        break;

    case "StateMachineNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1;
        break;

    case "FlowchartNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1;
        break;
    ```

    <span data-ttu-id="02940-301">다음 예제에는 전체 `switch`(또는 `Select Case`) 문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-301">The following example contains the complete `switch` (or `Select Case`) statement.</span></span>

    ```vb
    Select Case WorkflowType.SelectedItem.ToString()
        Case "SequentialNumberGuessWorkflow"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity

        Case "StateMachineNumberGuessWorkflow"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

        Case "FlowchartNumberGuessWorkflow"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity

        Case "SequentialNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1

        Case "StateMachineNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1

        Case "FlowchartNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1
    End Select
    ```

    ```csharp
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

        case "SequentialNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1;
            break;

        case "StateMachineNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1;
            break;

        case "FlowchartNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1;
            break;
    };
    ```

6. <span data-ttu-id="02940-302">Ctrl+F5를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-302">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="02940-303">이제 현재 버전뿐 아니라 `v1` 버전의 워크플로도 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02940-303">You can now start the `v1` versions of the workflow as well as the current versions.</span></span> <span data-ttu-id="02940-304">이러한 새 인스턴스를 동적으로 업데이트 하려면 **ApplyDynamicUpdate** 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="02940-304">To dynamically update these new instances, run the **ApplyDynamicUpdate** application.</span></span>
