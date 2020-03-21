---
title: '연습: Visual C#에서 합성 컨트롤 제작'
ms.date: 03/30/2017
dev_langs:
- CSharp
helpviewer_keywords:
- custom controls [C#]
- user controls [Windows Forms], creating with Visual C#
- UserControl class [Windows Forms], walkthroughs
- user controls [C#]
- custom controls [Windows Forms], creating
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3ad9aad026a1a6a1266845736d7651db77fd5d5c
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546726"
---
# <a name="walkthrough-author-a-composite-control-with-c"></a><span data-ttu-id="06065-102">연습: C를 사용하여 복합 컨트롤 작성\#</span><span class="sxs-lookup"><span data-stu-id="06065-102">Walkthrough: Author a Composite Control with C\#</span></span>

<span data-ttu-id="06065-103">복합 컨트롤은 사용자 지정 그래픽 인터페이스를 만들고 재사용할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="06065-104">복합 컨트롤은 기본적으로 시각적 표현이 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="06065-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="06065-105">따라서 사용자 입력의 유효성을 검사하고 표시 속성을 수정하거나 작성자가 요구하는 다른 작업을 수행하여 기능을 확장할 수 있는 하나 이상의 Windows Forms 컨트롤, 구성 요소 또는 코드 블록으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="06065-106">복합 컨트롤은 다른 컨트롤과 동일한 방식으로 Windows Forms에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="06065-107">이 연습의 첫 번째 부분에서는 `ctlClock`이라는 간단한 복합 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06065-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="06065-108">두 번째 부분에서는 상속을 통해 `ctlClock`의 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="06065-109">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="06065-109">Create the Project</span></span>

<span data-ttu-id="06065-110">새 프로젝트를 만들 때는 이에 대한 이름을 지정하여 루트 네임스페이스, 어셈블리 이름 및 프로젝트 이름을 설정하고 기본 구성 요소가 올바른 네임스페이스에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="06065-111">ctlClockLib 컨트롤 라이브러리 및 ctlClock 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="06065-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="06065-112">비주얼 스튜디오에서 새 **Windows 양식 제어 라이브러리** 프로젝트를 만들고 **ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="06065-112">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ctlClockLib**.</span></span>

     <span data-ttu-id="06065-113">프로젝트 이름, `ctlClockLib`는 기본적으로 루트 네임스페이스에도 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-113">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="06065-114">루트 네임스페이스는 어셈블리에서 구성 요소의 이름을 정규화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-114">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="06065-115">예를 들어 두 어셈블리에서 `ctlClock`이라는 구성 요소를 제공하면 `ctlClockLib.ctlClock.`을 사용하여 `ctlClock` 구성 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-115">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

2. <span data-ttu-id="06065-116">**솔루션 탐색기에서**UserControl1.cs **마우스**오른쪽 단추로 클릭한 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06065-116">In **Solution Explorer**, right-click **UserControl1.cs**, and then click **Rename**.</span></span> <span data-ttu-id="06065-117">파일 이름을 `ctlClock.cs`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-117">Change the file name to `ctlClock.cs`.</span></span> <span data-ttu-id="06065-118">코드 요소 "UserControl1"에 대한 모든 참조의 이름을 바꿀지 묻는 메시지가 표시되면 **예** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-118">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    > <span data-ttu-id="06065-119">기본적으로 복합 컨트롤은 시스템에서 제공하는 <xref:System.Windows.Forms.UserControl> 클래스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-119">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="06065-120">클래스는 <xref:System.Windows.Forms.UserControl> 모든 복합 컨트롤에 필요한 기능을 제공 하며 표준 메서드 및 속성을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-120">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

3. <span data-ttu-id="06065-121">**파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-121">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="06065-122">복합 컨트롤에 Windows 컨트롤 및 구성 요소 추가</span><span class="sxs-lookup"><span data-stu-id="06065-122">Add Windows Controls and Components to the Composite Control</span></span>

<span data-ttu-id="06065-123">시각적 인터페이스는 복합 컨트롤의 필수적인 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="06065-123">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="06065-124">이 시각적 인터페이스는 하나 이상의 Windows 컨트롤을 디자이너 화면에 추가하여 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-124">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="06065-125">다음 데모에서는 Windows 컨트롤을 복합 컨트롤에 통합하고 기능을 구현하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-125">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="06065-126">복합 컨트롤에 레이블 및 타이머를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="06065-126">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="06065-127">**솔루션 탐색기에서**ctlClock.cs **마우스**오른쪽 단추로 클릭한 다음 디자이너 **보기를**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-127">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="06065-128">도구 **상자에서**공통 **컨트롤** 노드를 확장한 다음 **레이블을**두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-128">In the **Toolbox**, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="06065-129">명명된 <xref:System.Windows.Forms.Label> `label1` 컨트롤이 디자이너 표면의 컨트롤에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-129">A <xref:System.Windows.Forms.Label> control named `label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="06065-130">디자이너에서 **label1을**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-130">In the designer, click **label1**.</span></span> <span data-ttu-id="06065-131">속성 창에서 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-131">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="06065-132">속성</span><span class="sxs-lookup"><span data-stu-id="06065-132">Property</span></span>|<span data-ttu-id="06065-133">다음으로 변경</span><span class="sxs-lookup"><span data-stu-id="06065-133">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="06065-134">**이름**</span><span class="sxs-lookup"><span data-stu-id="06065-134">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="06065-135">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="06065-135">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="06065-136">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="06065-136">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="06065-137">**글꼴 크기**</span><span class="sxs-lookup"><span data-stu-id="06065-137">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="06065-138">**도구 상자**에서 **구성 요소** 노드를 확장한 후 **타이머**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-138">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="06065-139">a는 <xref:System.Windows.Forms.Timer> 구성 요소이므로 런타임에 시각적 표현이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-139">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="06065-140">따라서 디자이너 표면의 컨트롤이 아니라 **구성 요소 디자이너(디자이너** 표면 의 맨 아래에 있는 트레이)에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="06065-140">Therefore, it does not appear with the controls on the designer surface, but rather in the **Component Designer** (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="06065-141">구성 **요소 디자이너에서** **timer1을**클릭한 <xref:System.Windows.Forms.Timer.Interval%2A> 다음 `1000` 속성과 <xref:System.Windows.Forms.Timer.Enabled%2A> `true`속성을 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-141">In the **Component Designer**, click **timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>

     <span data-ttu-id="06065-142">속성은 <xref:System.Windows.Forms.Timer.Interval%2A> <xref:System.Windows.Forms.Timer> 구성 요소가 체크하는 빈도를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-142">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the <xref:System.Windows.Forms.Timer> component ticks.</span></span> <span data-ttu-id="06065-143">`timer1`이 틱할 때마다 `timer1_Tick` 이벤트에 있는 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-143">Each time `timer1` ticks, it runs the code in the `timer1_Tick` event.</span></span> <span data-ttu-id="06065-144">간격은 틱 사이에 시간(밀리초)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06065-144">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="06065-145">구성 **요소 디자이너에서** **타이머 1을** 두 번 `timer1_Tick` 클릭하여 `ctlClock`에 대한 이벤트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-145">In the **Component Designer**, double-click **timer1** to go to the `timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="06065-146">다음 코드 샘플과 비슷하도록 코드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-146">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="06065-147">`private`에서 `protected`로 액세스 한정자를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-147">Be sure to change the access modifier from `private` to `protected`.</span></span>

    ```csharp
    protected void timer1_Tick(object sender, System.EventArgs e)
    {
        // Causes the label to display the current time.
        lblDisplay.Text = DateTime.Now.ToLongTimeString();
    }
    ```

     <span data-ttu-id="06065-148">이 코드를 통해 `lblDisplay`에 현재 시간이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-148">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="06065-149">`timer1`의 간격은 `1000`으로 설정되었으므로 이 이벤트는 천 밀리초마다 발생하므로 현재 시간이 1초마다 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-149">Because the interval of `timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="06065-150">메서드를 `virtual` 키워드로 재정의 가능하도록 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-150">Modify the method to be overridable with the `virtual` keyword.</span></span> <span data-ttu-id="06065-151">자세한 내용은 아래의 “사용자 컨트롤에서 상속” 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06065-151">For more information, see the  "Inheriting from a User Control" section below.</span></span>

    ```csharp
    protected virtual void timer1_Tick(object sender, System.EventArgs e)
    ```

9. <span data-ttu-id="06065-152">**파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-152">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-properties-to-the-composite-control"></a><span data-ttu-id="06065-153">복합 컨트롤에 속성 추가</span><span class="sxs-lookup"><span data-stu-id="06065-153">Add Properties to the Composite Control</span></span>

<span data-ttu-id="06065-154">이제 클럭 컨트롤이 <xref:System.Windows.Forms.Label> 컨트롤과 <xref:System.Windows.Forms.Timer> 구성 요소를 캡슐화하고 각 컨트롤에는 고유한 속성 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-154">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="06065-155">이러한 컨트롤의 개별 속성은 이후 컨트롤 사용자가 액세스할 수 없지만 적절한 코드 블록을 작성하여 사용자 지정 속성을 만들고 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-155">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="06065-156">다음 프로시저에서 사용자가 배경 및 텍스트 색을 변경할 수 있도록 컨트롤에 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-156">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="06065-157">복합 컨트롤에 속성을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="06065-157">To add a property to your composite control</span></span>

1. <span data-ttu-id="06065-158">**솔루션 탐색기에서**ctlClock.cs **마우스**오른쪽 단추로 클릭한 다음 코드 **보기를**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-158">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Code**.</span></span>

     <span data-ttu-id="06065-159">컨트롤의 **코드 편집기가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="06065-159">The **Code Editor** for your control opens.</span></span>

2. <span data-ttu-id="06065-160">`public partial class ctlClock` 문을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-160">Locate the `public partial class ctlClock` statement.</span></span> <span data-ttu-id="06065-161">여는 중괄호 (`{)` 아래에 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-161">Beneath the opening brace (`{)`, type the following code.</span></span>

    ```csharp
    private Color colFColor;
    private Color colBColor;
    ```

     <span data-ttu-id="06065-162">이러한 문은 작성하려는 속성에 대한 값을 저장하는 데 사용할 private 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06065-162">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="06065-163">2단계에서 변수 선언 아래에 다음 코드를 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-163">Enter or paste the following code beneath the variable declarations from step 2.</span></span>

    ```csharp
    // Declares the name and type of the property.
    public Color ClockBackColor
    {
        // Retrieves the value of the private variable colBColor.
        get
        {
            return colBColor;
        }
        // Stores the selected value in the private variable colBColor, and
        // updates the background color of the label control lblDisplay.
        set
        {
            colBColor = value;
            lblDisplay.BackColor = colBColor;
        }
    }
    // Provides a similar set of instructions for the foreground color.
    public Color ClockForeColor
    {
        get
        {
            return colFColor;
        }
        set
        {
            colFColor = value;
            lblDisplay.ForeColor = colFColor;
        }
    }
    ```

     <span data-ttu-id="06065-164">위의 코드는 `ClockForeColor` 및 `ClockBackColor`라는 두 사용자 지정 속성을 만들며 이 속성은 이 컨트롤의 후속 사용자에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-164">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control.</span></span> <span data-ttu-id="06065-165">`get` 및 `set` 문은 속성 값의 스토리지 및 검색과 속성에 맞는 기능을 구현하는 코드를 위해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-165">The `get` and `set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="06065-166">**파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-166">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="06065-167">컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="06065-167">Test the Control</span></span>

<span data-ttu-id="06065-168">컨트롤은 독립 실행형 애플리케이션이 아니며 컨테이너에서 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-168">Controls are not stand-alone applications; they must be hosted in a container.</span></span> <span data-ttu-id="06065-169">컨트롤의 런타임 동작을 테스트하고 **UserControl 테스트 컨테이너**로 해당 속성을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-169">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="06065-170">자세한 내용은 [방법: UserControl의 런타임 동작 테스트](how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06065-170">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="06065-171">컨트롤을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="06065-171">To test your control</span></span>

1. <span data-ttu-id="06065-172">**F5를** 눌러 프로젝트를 빌드하고 **UserControl 테스트 컨테이너에서**컨트롤을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-172">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="06065-173">테스트 컨테이너의 속성 눈금에서 `ClockBackColor` 속성을 찾은 후 해당 속성을 선택하여 색상표를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-173">In the test container's property grid, locate the `ClockBackColor` property, and then select the property to display the color palette.</span></span>

3. <span data-ttu-id="06065-174">클릭하여 색을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-174">Choose a color by clicking it.</span></span>

   <span data-ttu-id="06065-175">컨트롤의 배경색이 선택한 색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="06065-175">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="06065-176">유사한 이벤트 시퀀스를 사용하여 `ClockForeColor` 속성이 예상대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-176">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

   <span data-ttu-id="06065-177">이 섹션과 이전 섹션에서는 구성 요소 및 Windows 컨트롤을 코드와 결합하고 패키징하여 복합 컨트롤 형태로 사용자 지정 기능을 제공하는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-177">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="06065-178">복합 컨트롤에 속성을 노출하고 완료한 후에는 컨트롤을 테스트하는 방법도 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-178">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="06065-179">다음 섹션에서는 `ctlClock`을 기본으로 사용하여 상속된 복합 컨트롤을 생성하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="06065-179">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inherit-from-a-composite-control"></a><span data-ttu-id="06065-180">복합 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="06065-180">Inherit from a Composite Control</span></span>

<span data-ttu-id="06065-181">이전 섹션에서는 Windows 컨트롤, 구성 요소 및 코드를 재사용 가능한 복합 컨트롤에 결합하는 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-181">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="06065-182">이제 복합 컨트롤을 다른 컨트롤을 작성하기 위한 기본으로 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-182">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="06065-183">기본 클래스에서 클래스를 파생시키는 과정을 *상속*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-183">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="06065-184">이 섹션에서는 `ctlAlarmClock`이라는 복합 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06065-184">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="06065-185">이 컨트롤은 부모 컨트롤인 `ctlClock`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-185">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="06065-186">부모 메서드를 재정의하고 새 메서드 및 속성을 추가하여 `ctlClock`의 기능을 확장하는 방법을 알아보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-186">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

<span data-ttu-id="06065-187">상속된 컨트롤을 만드는 첫 번째 단계는 부모에서 파생시키는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="06065-187">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="06065-188">이 작업은 속성, 메서드 및 부모 컨트롤의 그래픽 특성을 모두 포함하는 새 컨트롤을 만들지만 신규 또는 수정된 기능 추가를 위한 기본으로도 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-188">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="06065-189">상속된 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="06065-189">To create the inherited control</span></span>

1. <span data-ttu-id="06065-190">**솔루션 탐색기에서** **ctlClockLib을**마우스 오른쪽 단추로 클릭하고 **추가**지점을 클릭한 다음 **사용자 컨트롤을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06065-190">In **Solution Explorer**, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="06065-191">**새 항목 추가** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="06065-191">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="06065-192">**상속된 사용자 정의 컨트롤** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-192">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="06065-193">**이름** 상자에 `ctlAlarmClock.cs`를 입력한 다음 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-193">In the **Name** box, type `ctlAlarmClock.cs`, and then click **Add**.</span></span>

     <span data-ttu-id="06065-194">**상속 선택** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="06065-194">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="06065-195">**구성 요소 이름** 아래에서 **ctlClock**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-195">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="06065-196">**솔루션 탐색기에서**현재 프로젝트를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-196">In **Solution Explorer**, browse through the current projects.</span></span>

    > [!NOTE]
    > <span data-ttu-id="06065-197">**ctlAlarmClock.cs**라는 파일이 현재 프로젝트에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-197">A file called **ctlAlarmClock.cs** has been added to the current project.</span></span>

### <a name="add-the-alarm-properties"></a><span data-ttu-id="06065-198">경보 속성 추가</span><span class="sxs-lookup"><span data-stu-id="06065-198">Add the Alarm Properties</span></span>

<span data-ttu-id="06065-199">속성은 복합 컨트롤에 추가된 것과 같은 방식으로 상속된 컨트롤에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-199">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="06065-200">이제 속성 선언 구문을 사용하여 컨트롤에 두 가지 속성, 즉 경보가 꺼지는 날짜와 시간 값을 저장하는 `AlarmTime`과 경보가 설정되는지 여부를 나타내는 `AlarmSet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-200">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="06065-201">복합 컨트롤에 속성을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="06065-201">To add properties to your composite control</span></span>

1. <span data-ttu-id="06065-202">**솔루션 탐색기에서** **ctlAlarmClock을**마우스 오른쪽 단추로 클릭한 다음 **코드 보기를**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-202">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="06065-203">`public class` 문을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-203">Locate the `public class` statement.</span></span> <span data-ttu-id="06065-204">컨트롤은 `ctlClockLib.ctlClock`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-204">Note that your control inherits from `ctlClockLib.ctlClock`.</span></span> <span data-ttu-id="06065-205">여는 중괄호 (`{)` 문 아래에 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-205">Beneath the opening brace (`{)` statement, type the following code.</span></span>

    ```csharp
    private DateTime dteAlarmTime;
    private bool blnAlarmSet;
    // These properties will be declared as public to allow future
    // developers to access them.
    public DateTime AlarmTime
    {
        get
        {
            return dteAlarmTime;
        }
        set
        {
            dteAlarmTime = value;
        }
    }
    public bool AlarmSet
    {
        get
        {
            return blnAlarmSet;
        }
        set
        {
            blnAlarmSet = value;
        }
    }
    ```

### <a name="add-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="06065-206">컨트롤의 그래픽 인터페이스에 추가</span><span class="sxs-lookup"><span data-stu-id="06065-206">Add to the Graphical Interface of the Control</span></span>

<span data-ttu-id="06065-207">상속된 컨트롤에는 상속 원본 컨트롤과 동일한 시각적 인터페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-207">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="06065-208">부모 컨트롤과 동일한 구성 요소 컨트롤을 소유하지만, 구체적으로 노출되지 않는 한, 구성 요소 컨트롤의 속성을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-208">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="06065-209">복합 컨트롤에 추가하는 것과 같은 방법으로 상속된 복합 컨트롤의 그래픽 인터페이스에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-209">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="06065-210">알람 시계의 시각적 인터페이스에 계속 추가하려면 경보가 울릴 때 깜박거리는 레이블 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-210">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="06065-211">레이블 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="06065-211">To add the label control</span></span>

1. <span data-ttu-id="06065-212">**솔루션 탐색기에서** **ctlAlarmClock을**마우스 오른쪽 단추로 클릭한 다음 **디자이너 보기를**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-212">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Designer**.</span></span>

     <span data-ttu-id="06065-213">`ctlAlarmClock`에 대한 디자이너가 주 창에 열립니다.</span><span class="sxs-lookup"><span data-stu-id="06065-213">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="06065-214">컨트롤의 표시 부분을 클릭하고 속성 창을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-214">Click the display portion of the control, and view the Properties window.</span></span>

    > [!NOTE]
    > <span data-ttu-id="06065-215">모든 속성이 표시되는 동안 흐리게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-215">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="06065-216">이것은 이러한 속성이 `lblDisplay`의 기본 속성이며 속성 창에서 수정하거나 액세스할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06065-216">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="06065-217">기본적으로 복합 컨트롤에 포함된 컨트롤은 `private`이며 해당 속성은 어떤 방법으로도 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-217">By default, controls contained in a composite control are `private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    > <span data-ttu-id="06065-218">복합 컨트롤의 후속 사용자가 내부 컨트롤에 액세스할 수 있도록 하려면 이를 `public` 또는 `protected`로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-218">If you want subsequent users of your composite control to have access to its internal controls, declare them as `public` or `protected`.</span></span> <span data-ttu-id="06065-219">이렇게 하면 적절한 코드를 사용하여 복합 컨트롤 내에 포함된 컨트롤의 속성을 설정 및 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-219">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="06065-220">복합 <xref:System.Windows.Forms.Label> 컨트롤에 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-220">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="06065-221">마우스를 사용하여 컨트롤을 <xref:System.Windows.Forms.Label> 표시 상자 바로 아래로 끕습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-221">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="06065-222">속성 창에서 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-222">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="06065-223">속성</span><span class="sxs-lookup"><span data-stu-id="06065-223">Property</span></span>|<span data-ttu-id="06065-224">설정</span><span class="sxs-lookup"><span data-stu-id="06065-224">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="06065-225">**이름**</span><span class="sxs-lookup"><span data-stu-id="06065-225">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="06065-226">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="06065-226">**Text**</span></span>|<span data-ttu-id="06065-227">**경보!**</span><span class="sxs-lookup"><span data-stu-id="06065-227">**Alarm!**</span></span>|
    |<span data-ttu-id="06065-228">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="06065-228">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="06065-229">**표시**</span><span class="sxs-lookup"><span data-stu-id="06065-229">**Visible**</span></span>|`false`|

### <a name="add-the-alarm-functionality"></a><span data-ttu-id="06065-230">알람 기능 추가</span><span class="sxs-lookup"><span data-stu-id="06065-230">Add the Alarm Functionality</span></span>

<span data-ttu-id="06065-231">이전 프로시저에서는 복합 컨트롤에서 경보 기능을 설정하는 속성 및 컨트롤을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-231">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="06065-232">이 프로시저에서는 현재 시간을 경보 시간과 비교하여 같으면 깜박이는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-232">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to flash an alarm.</span></span> <span data-ttu-id="06065-233">`ctlClock`의 `timer1_Tick` 메소드를 재정의하고 코드를 더 추가하여 `ctlClock`의 모든 고유 기능을 유지하면서 `ctlAlarmClock`의 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-233">By overriding the `timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="06065-234">ctlClock의 timer1_Tick 메서드를 재정의하려면</span><span class="sxs-lookup"><span data-stu-id="06065-234">To override the timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="06065-235">**코드 편집기**에서 `private bool blnAlarmSet;` 문을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-235">In the **Code Editor**, locate the `private bool blnAlarmSet;` statement.</span></span> <span data-ttu-id="06065-236">바로 아래에서 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-236">Immediately beneath it, add the following statement.</span></span>

    ```csharp
    private bool blnColorTicker;
    ```

2. <span data-ttu-id="06065-237">**코드 편집기**에서 클래스 끝에 있는 닫는 중괄호 (`})`를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-237">In the **Code Editor**, locate the closing brace (`})` at the end of the class.</span></span> <span data-ttu-id="06065-238">중괄호 바로 앞에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-238">Just before the brace, add the following code.</span></span>

    ```csharp
    protected override void timer1_Tick(object sender, System.EventArgs e)
    {
        // Calls the Timer1_Tick method of ctlClock.
        base.timer1_Tick(sender, e);
        // Checks to see if the alarm is set.
        if (AlarmSet == false)
            return;
        else
            // If the date, hour, and minute of the alarm time are the same as
            // the current time, flash an alarm.
        {
            if (AlarmTime.Date == DateTime.Now.Date && AlarmTime.Hour ==
                DateTime.Now.Hour && AlarmTime.Minute == DateTime.Now.Minute)
            {
                // Sets lblAlarmVisible to true, and changes the background color based on
                // the value of blnColorTicker. The background color of the label
                // will flash once per tick of the clock.
                lblAlarm.Visible = true;
                if (blnColorTicker == false)
                {
                    lblAlarm.BackColor = Color.Red;
                    blnColorTicker = true;
                }
                else
                {
                    lblAlarm.BackColor = Color.Blue;
                    blnColorTicker = false;
                }
            }
            else
            {
                // Once the alarm has sounded for a minute, the label is made
                // invisible again.
                lblAlarm.Visible = false;
            }
        }
    }
    ```

     <span data-ttu-id="06065-239">이 코드를 추가하려면 여러 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-239">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="06065-240">`override` 문은 기본 컨트롤에서 상속된 메서드 대신, 이 메서드를 사용하도록 컨트롤에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-240">The `override` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="06065-241">이 메서드가 호출되면 `base.timer1_Tick` 문을 호출하여 이를 재정의하는 메서드를 호출하여 원래 컨트롤에 통합된 모든 기능이 이 컨트롤에서 재현되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-241">When this method is called, it calls the method it overrides by invoking the `base.timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="06065-242">그런 다음 경보 기능을 통합하는 추가 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-242">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="06065-243">경보가 발생하면 깜박이는 레이블 컨트롤이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="06065-243">A flashing label control will appear when the alarm occurs.</span></span>

     <span data-ttu-id="06065-244">알람 시계 컨트롤이 거의 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-244">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="06065-245">이제 해제하는 방법을 구현하는 것만 남았습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-245">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="06065-246">이를 위해서는 `lblAlarm_Click` 메서드에 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-246">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="06065-247">shutoff 메서드를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="06065-247">To implement the shutoff method</span></span>

1. <span data-ttu-id="06065-248">**솔루션 탐색기에서**ctlAlarmClock.cs **마우스**오른쪽 단추를 클릭한 다음 디자이너 **보기를**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-248">In **Solution Explorer**, right-click **ctlAlarmClock.cs**, and then click **View Designer**.</span></span>

     <span data-ttu-id="06065-249">디자이너가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="06065-249">The designer opens.</span></span>

2. <span data-ttu-id="06065-250">단추를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-250">Add a button to the control.</span></span> <span data-ttu-id="06065-251">단추의 속성을 다음과 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-251">Set the properties of the button as follows.</span></span>

    |<span data-ttu-id="06065-252">속성</span><span class="sxs-lookup"><span data-stu-id="06065-252">Property</span></span>|<span data-ttu-id="06065-253">값</span><span class="sxs-lookup"><span data-stu-id="06065-253">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="06065-254">**이름**</span><span class="sxs-lookup"><span data-stu-id="06065-254">**Name**</span></span>|`btnAlarmOff`|
    |<span data-ttu-id="06065-255">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="06065-255">**Text**</span></span>|<span data-ttu-id="06065-256">**경보 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="06065-256">**Disable Alarm**</span></span>|

3. <span data-ttu-id="06065-257">디자이너에서 **btnAlarmOff**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-257">In the designer, double-click **btnAlarmOff**.</span></span>

     <span data-ttu-id="06065-258">**코드 편집기**에 `private void btnAlarmOff_Click` 행이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="06065-258">The **Code Editor** opens to the `private void btnAlarmOff_Click` line.</span></span>

4. <span data-ttu-id="06065-259">이 메서드를 다음 코드와 비슷하도록 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-259">Modify this method so that it resembles the following code.</span></span>

    ```csharp
    private void btnAlarmOff_Click(object sender, System.EventArgs e)
    {
        // Turns off the alarm.
        AlarmSet = false;
        // Hides the flashing label.
        lblAlarm.Visible = false;
    }
    ```

5. <span data-ttu-id="06065-260">**파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-260">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="use-the-inherited-control-on-a-form"></a><span data-ttu-id="06065-261">양식에서 상속된 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="06065-261">Use the Inherited Control on a Form</span></span>

<span data-ttu-id="06065-262">기본 클래스 컨트롤을 테스트한 것과 동일한 방식으로 상속된 **F5** 컨트롤을 테스트할 수 `ctlClock`있습니다. **UserControl Test Container**</span><span class="sxs-lookup"><span data-stu-id="06065-262">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="06065-263">자세한 내용은 [방법: UserControl의 런타임 동작 테스트](how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06065-263">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="06065-264">사용할 컨트롤을 배치하려면 폼에서 컨트롤을 호스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-264">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="06065-265">표준 복합 컨트롤과 마찬가지로 상속된 복합 컨트롤은 독립 실행형으로 사용할 수 없으며 폼 또는 다른 컨테이너에서 호스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-265">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="06065-266">`ctlAlarmClock`은 보다 심도 있는 기능을 포함하므로 테스트하려면 추가 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-266">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="06065-267">이 프로시저에서는 `ctlAlarmClock`의 기능을 테스트하는 간단한 프로그램을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-267">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="06065-268">`ctlAlarmClock`의 `AlarmTime` 속성을 설정하고 표시하는 코드를 작성하고 고유한 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-268">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="06065-269">컨트롤을 빌드하고 테스트 폼에 추가하려면</span><span class="sxs-lookup"><span data-stu-id="06065-269">To build and add your control to a test form</span></span>

1. <span data-ttu-id="06065-270">**솔루션 탐색기에서** **ctlClockLib을**마우스 오른쪽 단추로 클릭한 다음 **빌드를**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-270">In **Solution Explorer**, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="06065-271">솔루션에 새 **Windows Forms 응용 프로그램** 프로젝트를 추가하고 **테스트**이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-271">Add a new **Windows Forms Application** project to the solution, and name it **Test**.</span></span>

3. <span data-ttu-id="06065-272">**솔루션 탐색기에서**테스트 프로젝트의 **참조** 노드를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-272">In **Solution Explorer**, right-click the **References** node for your test project.</span></span> <span data-ttu-id="06065-273">**참조 추가** 대화 상자를 표시하려면 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-273">Click **Add Reference** to display the **Add Reference** dialog box.</span></span> <span data-ttu-id="06065-274">**프로젝트**로 레이블이 지정된 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-274">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="06065-275">`ctlClockLib` 프로젝트가 **프로젝트 이름** 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-275">Your `ctlClockLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="06065-276">프로젝트를 두 번 클릭하여 테스트 프로젝트에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-276">Double-click the project to add the reference to the test project.</span></span>

4. <span data-ttu-id="06065-277">**솔루션 탐색기에서**테스트를 마우스 오른쪽 단추로 **클릭한**다음 **빌드를**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-277">In **Solution Explorer**, right-click **Test**, and then click **Build**.</span></span>

5. <span data-ttu-id="06065-278">**도구 상자**에서 **ctlClockLib 구성 요소** 노드를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-278">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

6. <span data-ttu-id="06065-279">**ctlAlarmClock**을 두 번 클릭하여 `ctlAlarmClock`의 복사본을 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-279">Double-click **ctlAlarmClock** to add a copy of `ctlAlarmClock` to your form.</span></span>

7. <span data-ttu-id="06065-280">도구 **상자에서** **DateTimePicker를** 찾아 두 번 <xref:System.Windows.Forms.DateTimePicker> 클릭하여 양식에 컨트롤을 추가한 다음 <xref:System.Windows.Forms.Label> **레이블을**두 번 클릭하여 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-280">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

8. <span data-ttu-id="06065-281">마우스를 사용하여 폼의 편리한 위치에 컨트롤을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-281">Use the mouse to position the controls in a convenient place on the form.</span></span>

9. <span data-ttu-id="06065-282">다음 방식으로 이러한 컨트롤의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-282">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="06065-283">제어</span><span class="sxs-lookup"><span data-stu-id="06065-283">Control</span></span>|<span data-ttu-id="06065-284">속성</span><span class="sxs-lookup"><span data-stu-id="06065-284">Property</span></span>|<span data-ttu-id="06065-285">값</span><span class="sxs-lookup"><span data-stu-id="06065-285">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="06065-286">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="06065-286">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="06065-287">**이름**</span><span class="sxs-lookup"><span data-stu-id="06065-287">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="06065-288">**이름**</span><span class="sxs-lookup"><span data-stu-id="06065-288">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="06065-289">**형식**</span><span class="sxs-lookup"><span data-stu-id="06065-289">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

10. <span data-ttu-id="06065-290">디자이너에서 **dtpTest**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-290">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="06065-291">**코드 편집기**에 `private void dtpTest_ValueChanged`가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="06065-291">The **Code Editor** opens to `private void dtpTest_ValueChanged`.</span></span>

11. <span data-ttu-id="06065-292">다음과 비슷하도록 코드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-292">Modify the code so that it resembles the following.</span></span>

    ```csharp
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)
    {
        ctlAlarmClock1.AlarmTime = dtpTest.Value;
        ctlAlarmClock1.AlarmSet = true;
        lblTest.Text = "Alarm Time is " +
            ctlAlarmClock1.AlarmTime.ToShortTimeString();
    }
    ```

12. <span data-ttu-id="06065-293">**솔루션 탐색기에서** **테스트를**마우스 오른쪽 단추로 클릭한 다음 **시작 프로젝트로 설정 을**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-293">In **Solution Explorer**, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

13. <span data-ttu-id="06065-294">**디버그** 메뉴에서 **디버깅 시작을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06065-294">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="06065-295">테스트 프로그램이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-295">The test program starts.</span></span> <span data-ttu-id="06065-296">현재 시간은 `ctlAlarmClock` 컨트롤에서 업데이트되고 시작 시간은 컨트롤에 <xref:System.Windows.Forms.DateTimePicker> 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-296">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

14. <span data-ttu-id="06065-297">시간의 <xref:System.Windows.Forms.DateTimePicker> 분이 표시되는 위치를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-297">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

15. <span data-ttu-id="06065-298">키보드를 사용하여 `ctlAlarmClock`으로 표시된 현재 시간보다 1분 큰 값(분)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-298">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="06065-299">경보 설정 시간이 `lblTest`에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06065-299">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="06065-300">표시된 시간이 경보 설정 시간에 도달할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="06065-300">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="06065-301">표시된 시간이 경보 설정 시간에 도달하면 `lblAlarm`이 깜박입니다.</span><span class="sxs-lookup"><span data-stu-id="06065-301">When the displayed time reaches the time to which the alarm is set, the `lblAlarm` will flash.</span></span>

16. <span data-ttu-id="06065-302">`btnAlarmOff`을 클릭하여 경보를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="06065-302">Turn off the alarm by clicking `btnAlarmOff`.</span></span> <span data-ttu-id="06065-303">이제 경보를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-303">You may now reset the alarm.</span></span>

<span data-ttu-id="06065-304">이 문서에서는 여러 가지 주요 개념을 다루었습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-304">This article has covered a number of key concepts.</span></span> <span data-ttu-id="06065-305">컨트롤 및 구성 요소를 복합 컨트롤 컨테이너에 결합하여 복합 컨트롤을 만드는 방법을 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-305">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="06065-306">컨트롤에 속성을 추가하고 사용자 지정 기능을 작성하는 코드를 작성하는 방법도 알아봤습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-306">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="06065-307">마지막 섹션에서는 상속성을 통해 지정된 복합 컨트롤의 기능을 확장하고 해당 메서드를 재정의하여 호스트 메서드의 기능을 수정해보았습니다.</span><span class="sxs-lookup"><span data-stu-id="06065-307">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="06065-308">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06065-308">See also</span></span>

- [<span data-ttu-id="06065-309">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="06065-309">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="06065-310">방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시</span><span class="sxs-lookup"><span data-stu-id="06065-310">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="06065-311">연습: Visual C#을 사용하여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="06065-311">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
