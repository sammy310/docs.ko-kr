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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a8572c1e70e36faf3a179de7a69e88e9cf1e781b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460619"
---
# <a name="walkthrough-debug-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="0ed88-102">연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버그</span><span class="sxs-lookup"><span data-stu-id="0ed88-102">Walkthrough: Debug Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="0ed88-103">사용자 지정 컨트롤을 만들 때 디자인 타임 동작을 디버깅 해야 하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="0ed88-104">이는 사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 제작 하는 경우 특히 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="0ed88-105">자세한 내용은 [연습: Visual Studio 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기](creating-a-wf-control-design-time-features.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed88-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="0ed88-106">다른 .NET Framework 클래스를 디버그 하는 것 처럼 Visual Studio를 사용 하 여 사용자 지정 컨트롤을 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="0ed88-107">차이점은 사용자 지정 컨트롤의 코드를 실행 하는 Visual Studio의 개별 인스턴스를 디버깅할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="0ed88-108">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-108">Create the project</span></span>

<span data-ttu-id="0ed88-109">첫 번째 단계에서는 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-109">The first step is to create the application project.</span></span> <span data-ttu-id="0ed88-110">이 프로젝트를 사용 하 여 사용자 지정 컨트롤을 호스트 하는 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-110">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="0ed88-111">Visual Studio에서 Windows 응용 프로그램 프로젝트를 만들고 이름을 **DebuggingExample**로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-111">In Visual Studio, create a Windows Application project, and name it **DebuggingExample**.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="0ed88-112">컨트롤 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="0ed88-112">Create the control library project</span></span>

1. <span data-ttu-id="0ed88-113">**Windows 컨트롤 라이브러리** 프로젝트를 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-113">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="0ed88-114">DebugControlLibrary 프로젝트에 새 **UserControl** 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-114">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="0ed88-115">**Debugcontrol**로 이름을로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-115">Name it **DebugControl**.</span></span>

3. <span data-ttu-id="0ed88-116">**솔루션 탐색기**에서 기본 이름이 UserControl1 인 코드 파일을 삭제 하 여 프로젝트의 기본 컨트롤을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-116">In **Solution Explorer**, delete the project's default control by deleting the code file with a base name of UserControl1.</span></span>

4. <span data-ttu-id="0ed88-117">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-117">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="0ed88-118">검사점</span><span class="sxs-lookup"><span data-stu-id="0ed88-118">Checkpoint</span></span>

<span data-ttu-id="0ed88-119">이 시점에서 **도구 상자**에 사용자 지정 컨트롤을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-119">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="0ed88-120">진행 상황을 확인 하려면 **Debugcontrollibrary 구성 요소** 라는 새 탭을 찾고 클릭 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-120">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="0ed88-121">열리면 컨트롤이 표시 되 고 기본 아이콘 옆에는 **Debugcontrol** 이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-121">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="0ed88-122">사용자 지정 컨트롤에 속성 추가</span><span class="sxs-lookup"><span data-stu-id="0ed88-122">Add a property to your custom control</span></span>

<span data-ttu-id="0ed88-123">디자인 타임에 사용자 지정 컨트롤의 코드가 실행 되 고 있음을 보여 주기 위해 속성을 추가 하 고 속성을 구현 하는 코드에서 중단점을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-123">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="0ed88-124">**코드 편집기**에서 **debugcontrol** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-124">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="0ed88-125">클래스 정의에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-125">Add the following code to the class definition:</span></span>

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

2. <span data-ttu-id="0ed88-126">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-126">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="0ed88-127">호스트 폼에 사용자 지정 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="0ed88-127">Add your custom control to the host form</span></span>

<span data-ttu-id="0ed88-128">사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하려면 호스트 폼에 사용자 지정 컨트롤 클래스의 인스턴스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-128">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="0ed88-129">"DebuggingExample" 프로젝트의 **Windows Forms 디자이너**에서 Form1을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-129">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="0ed88-130">**도구 상자**에서 **Debugcontrollibrary 구성 요소** 탭을 열고 **debugcontrol** 인스턴스를 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-130">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="0ed88-131">**속성** 창에서 `DemoString` 사용자 지정 속성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-131">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="0ed88-132">다른 속성과 같이 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-132">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="0ed88-133">또한 `DemoString` 속성이 선택 된 경우 속성의 설명 문자열이 **속성** 창의 맨 아래에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-133">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="0ed88-134">디자인 타임 디버깅을 위한 프로젝트 설정</span><span class="sxs-lookup"><span data-stu-id="0ed88-134">Set up the project for design-time debugging</span></span>

<span data-ttu-id="0ed88-135">사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하려면 사용자 지정 컨트롤의 코드를 실행 하는 Visual Studio의 개별 인스턴스를 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-135">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="0ed88-136">**솔루션 탐색기** 에서 **debugcontrollibrary** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-136">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="0ed88-137">**Debugcontrollibrary** 속성 시트에서 **디버그** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-137">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="0ed88-138">**시작 작업** 섹션에서 **시작 외부 프로그램**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-138">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="0ed88-139">Visual studio의 개별 인스턴스를 디버깅 하 게 되므로 visual studio IDE를 찾아보려면 줄임표 (![속성 창 Visual Studio](./media/visual-studio-ellipsis-button.png)) 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-139">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="0ed88-140">실행 파일의 이름은 **devenv.exe입니다.** 를 기본 위치에 설치한 경우 해당 경로는 *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\\\<edition > \Common7\IDE*입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-140">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\\\<edition>\Common7\IDE*.</span></span>

3. <span data-ttu-id="0ed88-141">**확인**을 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-141">Select **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="0ed88-142">**Debugcontrollibrary** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정** 을 선택 하 여이 디버깅 구성을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-142">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="0ed88-143">디자인 타임에 사용자 지정 컨트롤 디버그</span><span class="sxs-lookup"><span data-stu-id="0ed88-143">Debug your custom control at design time</span></span>

<span data-ttu-id="0ed88-144">이제 디자인 모드에서 실행 되는 사용자 지정 컨트롤을 디버그할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-144">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="0ed88-145">디버깅 세션을 시작 하면 Visual Studio의 새 인스턴스가 생성 되 고이를 사용 하 여 "DebuggingExample" 솔루션을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-145">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="0ed88-146">**폼 디자이너**에서 Form1을 열면 사용자 지정 컨트롤의 인스턴스가 만들어지고 실행이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-146">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="0ed88-147">**코드 편집기** 에서 **debugcontrol** 원본 파일을 열고 `DemoString` 속성의 `Set` 접근자에 중단점을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-147">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="0ed88-148">**F5** 키를 눌러 디버깅 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-148">Press **F5** to start the debugging session.</span></span> <span data-ttu-id="0ed88-149">Visual Studio의 새 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-149">A new instance of Visual Studio is created.</span></span> <span data-ttu-id="0ed88-150">두 가지 방법으로 인스턴스를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-150">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="0ed88-151">디버깅 인스턴스의 제목 표시줄에는 **실행 중인** 단어가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-151">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="0ed88-152">디버깅 인스턴스의 **디버그** 도구 모음에 있는 **시작** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-152">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

   <span data-ttu-id="0ed88-153">중단점은 디버깅 인스턴스에 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-153">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="0ed88-154">Visual Studio의 새 인스턴스에서 "DebuggingExample" 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-154">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="0ed88-155">**파일** 메뉴에서 **최근 프로젝트** 를 선택 하 여 솔루션을 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-155">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="0ed88-156">"DebuggingExample" 솔루션 파일이 가장 최근에 사용 된 파일로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-156">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="0ed88-157">**폼 디자이너** 에서 Form1을 열고 **debugcontrol** 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-157">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="0ed88-158">`DemoString` 속성 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-158">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="0ed88-159">변경 내용을 커밋하는 경우 Visual Studio의 디버깅 인스턴스는 포커스를 획득 하 고 중단점에서 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-159">When you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="0ed88-160">다른 코드와 마찬가지로 속성 접근자를 한 단계씩 실행 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-160">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="0ed88-161">디버깅을 중지 하려면 Visual Studio의 호스팅된 인스턴스를 종료 하거나 디버깅 인스턴스에서 **디버깅 중지** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-161">To stop debugging, exit the hosted instance of Visual Studio or select the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0ed88-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0ed88-162">Next steps</span></span>

<span data-ttu-id="0ed88-163">이제 디자인 타임에 사용자 지정 컨트롤을 디버그할 수 있으므로 Visual Studio IDE와의 상호 작용을 확장 하는 여러 가지 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-163">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="0ed88-164"><xref:System.ComponentModel.Component> 클래스의 <xref:System.ComponentModel.Component.DesignMode%2A> 속성을 사용 하 여 디자인 타임에만 실행 되는 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-164">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="0ed88-165">자세한 내용은 <xref:System.ComponentModel.Component.DesignMode%2A>를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ed88-165">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="0ed88-166">사용자 지정 컨트롤의 속성에 적용 하 여 디자이너와의 사용자 지정 컨트롤의 상호 작용을 조작할 수 있는 몇 가지 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-166">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="0ed88-167">이러한 특성은 <xref:System.ComponentModel?displayProperty=nameWithType> 네임 스페이스에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-167">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="0ed88-168">사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-168">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="0ed88-169">이를 통해 Visual Studio에서 제공 하는 확장 가능한 디자이너 인프라를 사용 하 여 디자인 환경을 완벽 하 게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-169">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="0ed88-170">자세한 내용은 [연습: Visual Studio 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기](creating-a-wf-control-design-time-features.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed88-170">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ed88-171">참조</span><span class="sxs-lookup"><span data-stu-id="0ed88-171">See also</span></span>

- [<span data-ttu-id="0ed88-172">연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="0ed88-172">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
