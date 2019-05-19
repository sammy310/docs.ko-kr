---
title: '연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
ms.openlocfilehash: 39adcbd6d915f8b086df7e425efbe08ae8680a45
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882457"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="ded39-102">연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅</span><span class="sxs-lookup"><span data-stu-id="ded39-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="ded39-103">사용자 지정 컨트롤을 만들려면 확인할 수 있습니다 종종 해당 디자인 타임 동작을 디버그 하는 데 필요한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="ded39-104">사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 제작 하는 경우 특히 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="ded39-105">세부 정보를 참조 하세요. [연습: Visual Studio 디자인 타임 기능을 활용 하는 컨트롤을 Forms는 Windows 만들기](creating-a-wf-control-design-time-features.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="ded39-106">다른.NET Framework 클래스를 디버그할 때 처럼 Visual Studio를 사용 하 여 사용자 지정 컨트롤을 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="ded39-107">차이점은 사용자 지정 컨트롤의 코드를 실행 하는 Visual Studio의 개별 인스턴스를 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>

<span data-ttu-id="ded39-108">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="ded39-109">사용자 지정 컨트롤을 호스트 하는 Windows Forms 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="ded39-109">Creating a Windows Forms project to host your custom control</span></span>

- <span data-ttu-id="ded39-110">컨트롤 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="ded39-110">Creating a control library project</span></span>

- <span data-ttu-id="ded39-111">사용자 지정 컨트롤에 속성 추가</span><span class="sxs-lookup"><span data-stu-id="ded39-111">Adding a property to your custom control</span></span>

- <span data-ttu-id="ded39-112">호스트 형식에 사용자 지정 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="ded39-112">Adding your custom control to the host form</span></span>

- <span data-ttu-id="ded39-113">디자인 타임 디버깅에 대 한 프로젝트 설정</span><span class="sxs-lookup"><span data-stu-id="ded39-113">Setting up the project for design-time debugging</span></span>

- <span data-ttu-id="ded39-114">디자인 타임에 사용자 지정 컨트롤 디버깅</span><span class="sxs-lookup"><span data-stu-id="ded39-114">Debugging your custom control at design time</span></span>

<span data-ttu-id="ded39-115">작업을 완료 하는 경우에 사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하는 데 필요한 작업을 이해를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="ded39-116">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-116">Create the project</span></span>

<span data-ttu-id="ded39-117">첫 번째 단계는 응용 프로그램 프로젝트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-117">The first step is to create the application project.</span></span> <span data-ttu-id="ded39-118">사용자 지정 컨트롤을 호스팅하는 응용 프로그램을 빌드하려면이 프로젝트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-118">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="ded39-119">Visual Studio에서 "DebuggingExample" 라는 Windows 응용 프로그램 프로젝트를 만듭니다 (**파일** > **새로 만들기** > **프로젝트**  >  **시각적 C#**  하거나 **Visual Basic** > **클래식 바탕 화면** > **Windows Forms응용프로그램**).</span><span class="sxs-lookup"><span data-stu-id="ded39-119">In Visual Studio, create a Windows Application project called "DebuggingExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="ded39-120">컨트롤 라이브러리 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ded39-120">Create the control library project</span></span>

1. <span data-ttu-id="ded39-121">추가 된 **Windows 컨트롤 라이브러리** 프로젝트를 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-121">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="ded39-122">새 **UserControl** DebugControlLibrary 프로젝트 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-122">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="ded39-123">자세한 내용은 [방법: 새 프로젝트 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-123">For details, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span> <span data-ttu-id="ded39-124">새 소스 파일 "DebugControl"의 기본 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-124">Give the new source file a base name of "DebugControl".</span></span>

3. <span data-ttu-id="ded39-125">사용 하는 **솔루션 탐색기**, 프로젝트의 기본 컨트롤의 기본 이름 사용 하 여 코드 파일을 삭제 하 여 삭제 "`UserControl1`".</span><span class="sxs-lookup"><span data-stu-id="ded39-125">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="ded39-126">자세한 내용은 [방법: 제거, 삭제 및 항목을 제외](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-126">For details, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

4. <span data-ttu-id="ded39-127">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-127">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="ded39-128">검사점</span><span class="sxs-lookup"><span data-stu-id="ded39-128">Checkpoint</span></span>

<span data-ttu-id="ded39-129">이 시점에서 사용자 지정 컨트롤을 볼 수는 합니다 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-129">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="ded39-130">진행률을 확인 하 라는 새 탭을 찾습니다 **DebugControlLibrary 구성 요소** 클릭 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-130">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="ded39-131">열리는 컨트롤으로 나열 표시 됩니다 **DebugControl** 그 옆에 있는 기본 아이콘을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-131">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="ded39-132">사용자 지정 컨트롤에 속성 추가</span><span class="sxs-lookup"><span data-stu-id="ded39-132">Add a property to your custom control</span></span>

<span data-ttu-id="ded39-133">디자인 타임에 사용자 지정 컨트롤의 코드 실행 되 고 있는지를 보여 주기 위해 속성을 추가 하 고 속성을 구현 하는 코드에 중단점을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-133">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="ded39-134">오픈 **DebugControl** 에 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-134">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="ded39-135">클래스 정의에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-135">Add the following code to the class definition:</span></span>

    ```vb
    Private demoStringValue As String = Nothing
    <BrowsableAttribute(true)>
    Public Property DemoString() As String

        Get
            Return Me.demoStringValue
        End Get

        Set(ByVal value As String)
            Me.demoStringValue = value
        End Set

    End Property
    ```

    ```csharp
    private string demoStringValue = null;
    [Browsable(true)]
    public string DemoString
    {
        get
        {
            return this.demoStringValue;
        }
        set
        {
            demoStringValue = value;
        }
    }
    ```

2. <span data-ttu-id="ded39-136">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-136">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="ded39-137">호스트 폼에 사용자 지정 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="ded39-137">Add your custom control to the host form</span></span>

<span data-ttu-id="ded39-138">사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하려면 호스트 양식의 사용자 지정 컨트롤 클래스의 인스턴스를 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-138">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="ded39-139">"DebuggingExample" 프로젝트에서의 Form1을 엽니다는 **Windows Forms 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-139">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="ded39-140">에 **도구 상자**를 엽니다는 **DebugControlLibrary 구성 요소** 끌어서 탭을 **DebugControl** 폼에 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ded39-140">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="ded39-141">찾을 합니다 `DemoString` 에서 사용자 지정 속성을 **속성** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-141">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="ded39-142">참고 다른 속성과 마찬가지로 해당 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-142">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="ded39-143">또한를 `DemoString` 속성을 선택 하면 속성의 설명 문자열의 맨 아래에 표시 되는 **속성** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-143">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="ded39-144">디자인 타임 디버깅에 대 한 프로젝트 설정</span><span class="sxs-lookup"><span data-stu-id="ded39-144">Set up the project for design-time debugging</span></span>

<span data-ttu-id="ded39-145">사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하려면 사용자 지정 컨트롤의 코드를 실행 하는 Visual Studio의 개별 인스턴스를 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-145">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="ded39-146">마우스 오른쪽 단추로 클릭 합니다 **DebugControlLibrary** 프로젝트에 **솔루션 탐색기** 선택한 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-146">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="ded39-147">에 **DebugControlLibrary** 속성 시트를 선택 합니다 **디버그** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-147">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="ded39-148">에 **시작 작업** 섹션에서 **시작 외부 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-148">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="ded39-149">해야 줄임표 하므로 Visual Studio의 개별 인스턴스를 디버깅 (![의 줄임표 단추 (...)의 Visual Studio 속성 창에서](./media/visual-studio-ellipsis-button.png)) 클릭 하 여 Visual Studio IDE에 대 한 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-149">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="ded39-150">실행 파일의 이름은 **devenv.exe**, 되며 해당 경로 %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe 기본 위치에 설치한 경우.</span><span class="sxs-lookup"><span data-stu-id="ded39-150">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>

3. <span data-ttu-id="ded39-151">**확인** 을 클릭하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-151">Click **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="ded39-152">마우스 오른쪽 단추로 클릭 합니다 **DebugControlLibrary** 프로젝트를 마우스 **시작 프로젝트로 설정** 디버깅이 구성을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-152">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="ded39-153">디자인 타임에 사용자 지정 컨트롤 디버그</span><span class="sxs-lookup"><span data-stu-id="ded39-153">Debug your custom control at design time</span></span>

<span data-ttu-id="ded39-154">이제 디자인 모드로 실행 될 때 사용자 지정 컨트롤을 디버그할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-154">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="ded39-155">디버깅 세션을 시작 하면 Visual Studio의 새 인스턴스를 만들어지고 "DebuggingExample" 솔루션을 로드 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-155">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="ded39-156">Form1에서 열면 합니다 **Forms 디자이너**, 사용자 지정 컨트롤 인스턴스에 만들어지고 실행이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-156">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="ded39-157">열기를 **DebugControl** 소스 파일을 **코드 편집기** 중단점을 설정 하 고는 `Set` 의 접근자는 `DemoString` 속성.</span><span class="sxs-lookup"><span data-stu-id="ded39-157">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="ded39-158">F5 키를 눌러 디버깅 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-158">Press F5 to start the debugging session.</span></span> <span data-ttu-id="ded39-159">Visual Studio의 새 인스턴스를 만들어짐을 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-159">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="ded39-160">두 가지 방법으로 인스턴스를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-160">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="ded39-161">디버깅 인스턴스 라는 단어가 포함 **실행** 제목 표시줄에 있는</span><span class="sxs-lookup"><span data-stu-id="ded39-161">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="ded39-162">디버깅 인스턴스를 **시작** 단추를 해당 **디버그** 사용 하지 않도록 설정 하는 도구 모음</span><span class="sxs-lookup"><span data-stu-id="ded39-162">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

     <span data-ttu-id="ded39-163">중단점은 디버깅 인스턴스에서 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-163">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="ded39-164">Visual Studio의 새 인스턴스를 "DebuggingExample" 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-164">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="ded39-165">선택 하 여 솔루션을 쉽게 찾을 수 있습니다 **최근에 사용한 프로젝트** 에서 합니다 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="ded39-165">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="ded39-166">"DebuggingExample.sln" 솔루션 파일을 최근에 사용 된 파일으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-166">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="ded39-167">Form1을 엽니다는 **Forms 디자이너** 선택 합니다 **DebugControl** 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-167">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="ded39-168">`DemoString` 속성 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-168">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="ded39-169">변경 내용을 커밋하면, Visual Studio의 디버깅 인스턴스 포커스를 획득 하 고 실행이 중단점에서 중지 되는 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-169">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="ded39-170">속성 접근자를 통해 단일 단계 수와 마찬가지로 다른 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-170">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="ded39-171">Visual Studio의 호스트 인스턴스를 해제 하거나 클릭 하 여 마쳤으면 디버깅 세션을 종료할 수 있습니다 합니다 **디버깅 중지** 디버깅 인스턴스에서 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-171">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ded39-172">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ded39-172">Next steps</span></span>

<span data-ttu-id="ded39-173">이제는 사용자 지정 컨트롤 디자인 타임에 디버그할 수 있는 Visual Studio IDE를 사용 하 여 컨트롤의 상호 작용을 확장 하기 위한 많은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-173">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="ded39-174">사용할 수는 <xref:System.ComponentModel.Component.DesignMode%2A> 의 속성을 <xref:System.ComponentModel.Component> 디자인 타임에만 실행 하는 코드를 작성 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-174">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="ded39-175">자세한 내용은 <xref:System.ComponentModel.Component.DesignMode%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ded39-175">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="ded39-176">일부의 특성이 컨트롤의 디자이너를 사용 하 여 사용자 지정 컨트롤의 상호 작용을 조작 하는 속성에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-176">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="ded39-177">이러한 특성을 찾을 수 있습니다는 <xref:System.ComponentModel?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-177">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="ded39-178">사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-178">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="ded39-179">Visual Studio에서 노출 하는 확장 가능한 디자이너 인프라를 사용 하 여 디자인 환경을 완전히 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-179">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="ded39-180">세부 정보를 참조 하세요. [연습: Visual Studio 디자인 타임 기능을 활용 하는 컨트롤을 Forms는 Windows 만들기](creating-a-wf-control-design-time-features.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ded39-180">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ded39-181">참고자료</span><span class="sxs-lookup"><span data-stu-id="ded39-181">See also</span></span>

- [<span data-ttu-id="ded39-182">연습: Visual Studio 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="ded39-182">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
- <span data-ttu-id="ded39-183">[방법: 디자인 타임 서비스에 액세스](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ded39-183">[How to: Access Design-Time Services](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span></span>
- <span data-ttu-id="ded39-184">[방법: Windows Forms에서 디자인 타임 지원 액세스](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ded39-184">[How to: Access Design-Time Support in Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span></span>
