---
title: '연습: Visual Basic을 사용하여 복합 컨트롤 작성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Visual Basic]
- user controls [Visual Basic]
- UserControl class [Windows Forms], walkthroughs
- user controls [Windows Forms], creating with Visual Basic
- controls [Windows Forms], composite controls
- composite controls [Windows Forms], creating
- custom controls [Windows Forms], creating
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
ms.openlocfilehash: cb54ef372e6da551b95f1edf61e3844b9dcba4c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950035"
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-basic"></a><span data-ttu-id="25826-102">연습: Visual Basic을 사용하여 복합 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="25826-102">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>
<span data-ttu-id="25826-103">복합 컨트롤은 사용자 지정 그래픽 인터페이스를 만들고 재사용할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="25826-104">복합 컨트롤은 기본적으로 시각적 표현이 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="25826-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="25826-105">따라서 사용자 입력의 유효성을 검사하고 표시 속성을 수정하거나 작성자가 요구하는 다른 작업을 수행하여 기능을 확장할 수 있는 하나 이상의 Windows Forms 컨트롤, 구성 요소 또는 코드 블록으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="25826-106">복합 컨트롤은 다른 컨트롤과 동일한 방식으로 Windows Forms에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="25826-107">이 연습의 첫 번째 부분에서는 `ctlClock`이라는 간단한 복합 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25826-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="25826-108">두 번째 부분에서는 상속을 통해 `ctlClock`의 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="25826-109">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="25826-109">Creating the Project</span></span>
 <span data-ttu-id="25826-110">새 프로젝트를 만들 때는 이에 대한 이름을 지정하여 루트 네임스페이스, 어셈블리 이름 및 프로젝트 이름을 설정하고 기본 구성 요소가 올바른 네임스페이스에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="25826-111">ctlClockLib 컨트롤 라이브러리 및 ctlClock 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="25826-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="25826-112">**파일** 메뉴에서 **새로 만들기**를 가리키고 **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="25826-112">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="25826-113">Visual Basic 프로젝트 목록에서 **Windows 컨트롤 라이브러리** 프로젝트 템플릿을 선택 하 고 **이름** 상자에를 `ctlClockLib` 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-113">From the list of Visual Basic projects, select the **Windows Control Library** project template, type `ctlClockLib` in the **Name** box, and then click **OK**.</span></span>

     <span data-ttu-id="25826-114">프로젝트 이름, `ctlClockLib`는 기본적으로 루트 네임스페이스에도 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-114">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="25826-115">루트 네임스페이스는 어셈블리에서 구성 요소의 이름을 정규화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-115">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="25826-116">예를 들어 두 어셈블리에서 `ctlClock`이라는 구성 요소를 제공하면 `ctlClockLib.ctlClock.`을 사용하여 `ctlClock` 구성 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-116">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

3. <span data-ttu-id="25826-117">솔루션 탐색기에서 **UserControl1.vb**를 마우스 오른쪽 단추로 클릭한 다음 **이름 바꾸기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-117">In Solution Explorer, right-click **UserControl1.vb**, and then click **Rename**.</span></span> <span data-ttu-id="25826-118">파일 이름을 `ctlClock.vb`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-118">Change the file name to `ctlClock.vb`.</span></span> <span data-ttu-id="25826-119">코드 요소 “UserControl1”에 대한 모든 참조 이름을 변경할지 묻는 메시지가 표시되면 **예** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-119">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    > <span data-ttu-id="25826-120">기본적으로 복합 컨트롤은 시스템에서 제공 하 <xref:System.Windows.Forms.UserControl> 는 클래스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-120">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="25826-121">클래스 <xref:System.Windows.Forms.UserControl> 는 모든 복합 컨트롤에 필요한 기능을 제공 하 고 표준 메서드 및 속성을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-121">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

4. <span data-ttu-id="25826-122">**파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-122">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="adding-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="25826-123">복합 컨트롤에 Windows 컨트롤 및 구성 요소 추가</span><span class="sxs-lookup"><span data-stu-id="25826-123">Adding Windows Controls and Components to the Composite Control</span></span>
 <span data-ttu-id="25826-124">시각적 인터페이스는 복합 컨트롤의 필수적인 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="25826-124">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="25826-125">이 시각적 인터페이스는 하나 이상의 Windows 컨트롤을 디자이너 화면에 추가하여 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-125">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="25826-126">다음 데모에서는 Windows 컨트롤을 복합 컨트롤에 통합하고 기능을 구현하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-126">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="25826-127">복합 컨트롤에 레이블 및 타이머를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="25826-127">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="25826-128">솔루션 탐색기에서 **ctlClock.vb**를 마우스 오른쪽 단추로 클릭한 후 **뷰 디자이너**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-128">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="25826-129">도구 상자에서 **공용 컨트롤** 노드를 확장한 후 **레이블**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-129">In the Toolbox, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="25826-130"><xref:System.Windows.Forms.Label> 이라는`Label1` 컨트롤은 디자이너 화면에서 컨트롤에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-130">A <xref:System.Windows.Forms.Label> control named `Label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="25826-131">디자이너에서 **Label1**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-131">In the designer, click **Label1**.</span></span> <span data-ttu-id="25826-132">속성 창에서 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-132">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="25826-133">속성</span><span class="sxs-lookup"><span data-stu-id="25826-133">Property</span></span>|<span data-ttu-id="25826-134">다음으로 변경</span><span class="sxs-lookup"><span data-stu-id="25826-134">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="25826-135">**이름**</span><span class="sxs-lookup"><span data-stu-id="25826-135">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="25826-136">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="25826-136">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="25826-137">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="25826-137">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="25826-138">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="25826-138">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="25826-139">**도구 상자**에서 **구성 요소** 노드를 확장한 후 **타이머**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-139">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="25826-140">는 <xref:System.Windows.Forms.Timer> 구성 요소 이므로 런타임에 시각적으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-140">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="25826-141">따라서 디자이너 화면에 컨트롤과 함께 나타나지 않으며 구성 요소 디자이너(디자이너 화면 맨 아래 트레이)에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="25826-141">Therefore, it does not appear with the controls on the designer surface, but rather in the Component Designer (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="25826-142">구성 요소 디자이너에서 **Timer1**을 클릭 하 고 속성을로 <xref:System.Windows.Forms.Timer.Interval%2A> 설정 하 `1000` 고 <xref:System.Windows.Forms.Timer.Enabled%2A> 속성을로 `True`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-142">In the Component Designer, click **Timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `True`.</span></span>

     <span data-ttu-id="25826-143">속성 <xref:System.Windows.Forms.Timer.Interval%2A> 은 타이머 구성 요소가 틱 하는 빈도를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-143">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the timer component ticks.</span></span> <span data-ttu-id="25826-144">`Timer1`이 틱할 때마다 `Timer1_Tick` 이벤트에 있는 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-144">Each time `Timer1` ticks, it runs the code in the `Timer1_Tick` event.</span></span> <span data-ttu-id="25826-145">간격은 틱 사이에 시간(밀리초)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="25826-145">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="25826-146">구성 요소 디자이너에서 **Timer1**을 두 번 클릭하여 `ctlClock`에 대한 `Timer1_Tick` 이벤트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-146">In the Component Designer, double-click **Timer1** to go to the `Timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="25826-147">다음 코드 샘플과 비슷하도록 코드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-147">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="25826-148">`Private`에서 `Protected`로 액세스 한정자를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-148">Be sure to change the access modifier from `Private` to `Protected`.</span></span>

    ```vb
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _
        System.EventArgs) Handles Timer1.Tick
        ' Causes the label to display the current time.
        lblDisplay.Text = Format(Now, "hh:mm:ss")
    End Sub
    ```

     <span data-ttu-id="25826-149">이 코드를 통해 `lblDisplay`에 현재 시간이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-149">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="25826-150">`Timer1`의 간격은 `1000`으로 설정되었으므로 이 이벤트는 천 밀리초마다 발생하므로 현재 시간이 1초마다 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-150">Because the interval of `Timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="25826-151">메서드를 재정의 가능하도록 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-151">Modify the method to be overridable.</span></span> <span data-ttu-id="25826-152">자세한 내용은 아래의 “사용자 컨트롤에서 상속” 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25826-152">For more information, see the "Inheriting from a User Control" section below.</span></span>

    ```vb
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _
        e As System.EventArgs) Handles Timer1.Tick
    ```

9. <span data-ttu-id="25826-153">**파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-153">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="adding-properties-to-the-composite-control"></a><span data-ttu-id="25826-154">복합 컨트롤에 속성 추가</span><span class="sxs-lookup"><span data-stu-id="25826-154">Adding Properties to the Composite Control</span></span>
 <span data-ttu-id="25826-155">이제 클록 컨트롤이 <xref:System.Windows.Forms.Label> 컨트롤과 <xref:System.Windows.Forms.Timer> 구성 요소를 캡슐화 하며 각각 고유한 속성 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-155">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="25826-156">이러한 컨트롤의 개별 속성은 이후 컨트롤 사용자가 액세스할 수 없지만 적절한 코드 블록을 작성하여 사용자 지정 속성을 만들고 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-156">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="25826-157">다음 프로시저에서 사용자가 배경 및 텍스트 색을 변경할 수 있도록 컨트롤에 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-157">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="25826-158">복합 컨트롤에 속성을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="25826-158">To add a property to your composite control</span></span>

1. <span data-ttu-id="25826-159">솔루션 탐색기에서 **ctlClock.vb**를 마우스 오른쪽 단추로 클릭한 후 **코드 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-159">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Code**.</span></span>

     <span data-ttu-id="25826-160">컨트롤에 대한 코드 편집기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="25826-160">The Code Editor for your control opens.</span></span>

2. <span data-ttu-id="25826-161">`Public Class ctlClock` 문을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-161">Locate the `Public Class ctlClock` statement.</span></span> <span data-ttu-id="25826-162">아래에 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-162">Beneath it, type the following code.</span></span>

    ```vb
    Private colFColor as Color
    Private colBColor as Color
    ```

     <span data-ttu-id="25826-163">이러한 문은 작성하려는 속성에 대한 값을 저장하는 데 사용할 private 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25826-163">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="25826-164">2단계에서 변수 선언 아래에 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-164">Insert the following code beneath the variable declarations from step 2.</span></span>

    ```vb
    ' Declares the name and type of the property.
    Property ClockBackColor() as Color
        ' Retrieves the value of the private variable colBColor.
        Get
            Return colBColor
        End Get
        ' Stores the selected value in the private variable colBColor, and
        ' updates the background color of the label control lblDisplay.
        Set(ByVal value as Color)
            colBColor = value
            lblDisplay.BackColor = colBColor
        End Set

    End Property
    ' Provides a similar set of instructions for the foreground color.
    Property ClockForeColor() as Color
        Get
            Return colFColor
        End Get
        Set(ByVal value as Color)
            colFColor = value
            lblDisplay.ForeColor = colFColor
        End Set
    End Property
    ```

     <span data-ttu-id="25826-165">위의 코드는 `ClockForeColor` 및 `ClockBackColor`라는 두 사용자 지정 속성을 만들며 이 속성은 이 컨트롤의 후속 사용자가 `Property` 문을 호출하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-165">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control by invoking the `Property` statement.</span></span> <span data-ttu-id="25826-166">`Get` 및 `Set` 문은 속성 값의 저장 및 검색과 속성에 맞는 기능을 구현하는 코드를 위해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-166">The `Get` and `Set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="25826-167">**파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-167">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="testing-the-control"></a><span data-ttu-id="25826-168">컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="25826-168">Testing the Control</span></span>
 <span data-ttu-id="25826-169">컨트롤은 독립 실행형 프로젝트가 아니며 컨테이너에서 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-169">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="25826-170">컨트롤의 런타임 동작을 테스트하고 **UserControl 테스트 컨테이너**로 해당 속성을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-170">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="25826-171">자세한 내용은 [방법: UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)의 런타임 동작을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-171">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="25826-172">컨트롤을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="25826-172">To test your control</span></span>

1. <span data-ttu-id="25826-173">F5 키를 눌러 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**에서 컨트롤을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-173">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="25826-174">테스트 컨테이너의 속성 눈금에서 `ClockBackColor` 속성을 선택한 후 드롭다운 화살표를 클릭하여 색상표를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-174">In the test container's property grid, select the `ClockBackColor` property, and then click the drop-down arrow to display the color palette.</span></span>

3. <span data-ttu-id="25826-175">클릭하여 색을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-175">Choose a color by clicking it.</span></span>

     <span data-ttu-id="25826-176">컨트롤의 배경색이 선택한 색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="25826-176">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="25826-177">유사한 이벤트 시퀀스를 사용하여 `ClockForeColor` 속성이 예상대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-177">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

5. <span data-ttu-id="25826-178">**닫기**를 클릭하여 **UserControl 테스트 컨테이너**를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-178">Click **Close** to close the **UserControl Test Container**.</span></span>

     <span data-ttu-id="25826-179">이 섹션과 이전 섹션에서는 구성 요소 및 Windows 컨트롤을 코드와 결합하고 패키징하여 복합 컨트롤 형태로 사용자 지정 기능을 제공하는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-179">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="25826-180">복합 컨트롤에 속성을 노출하고 완료한 후에는 컨트롤을 테스트하는 방법도 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-180">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="25826-181">다음 섹션에서는 `ctlClock`을 기본으로 사용하여 상속된 복합 컨트롤을 생성하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="25826-181">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inheriting-from-a-composite-control"></a><span data-ttu-id="25826-182">복합 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="25826-182">Inheriting from a Composite Control</span></span>
 <span data-ttu-id="25826-183">이전 섹션에서는 Windows 컨트롤, 구성 요소 및 코드를 재사용 가능한 복합 컨트롤에 결합하는 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-183">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="25826-184">이제 복합 컨트롤을 다른 컨트롤을 작성하기 위한 기본으로 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-184">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="25826-185">기본 클래스에서 클래스를 파생시키는 과정을 *상속*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-185">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="25826-186">이 섹션에서는 `ctlAlarmClock`이라는 복합 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25826-186">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="25826-187">이 컨트롤은 부모 컨트롤인 `ctlClock`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-187">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="25826-188">부모 메서드를 재정의하고 새 메서드 및 속성을 추가하여 `ctlClock`의 기능을 확장하는 방법을 알아보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-188">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

 <span data-ttu-id="25826-189">상속된 컨트롤을 만드는 첫 번째 단계는 부모에서 파생시키는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="25826-189">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="25826-190">이 작업은 속성, 메서드 및 부모 컨트롤의 그래픽 특성을 모두 포함하는 새 컨트롤을 만들지만 신규 또는 수정된 기능 추가를 위한 기본으로도 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-190">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="25826-191">상속된 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="25826-191">To create the inherited control</span></span>

1. <span data-ttu-id="25826-192">솔루션 탐색기에서 **ctlClockLib**를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **사용자 컨트롤**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-192">In Solution Explorer, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="25826-193">**새 항목 추가** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="25826-193">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="25826-194">**상속된 사용자 정의 컨트롤** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-194">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="25826-195">**이름** 상자에 `ctlAlarmClock.vb`를 입력한 다음 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-195">In the **Name** box, type `ctlAlarmClock.vb`, and then click **Add**.</span></span>

     <span data-ttu-id="25826-196">**상속 선택** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="25826-196">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="25826-197">**구성 요소 이름** 아래에서 **ctlClock**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-197">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="25826-198">솔루션 탐색기에서 현재 프로젝트를 찾아봅니다.</span><span class="sxs-lookup"><span data-stu-id="25826-198">In Solution Explorer, browse through the current projects.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25826-199">**ctlAlarmClock.vb**라는 파일이 현재 프로젝트에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-199">A file called **ctlAlarmClock.vb** has been added to the current project.</span></span>

### <a name="adding-the-alarm-properties"></a><span data-ttu-id="25826-200">경보 속성 추가</span><span class="sxs-lookup"><span data-stu-id="25826-200">Adding the Alarm Properties</span></span>
 <span data-ttu-id="25826-201">속성은 복합 컨트롤에 추가된 것과 같은 방식으로 상속된 컨트롤에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-201">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="25826-202">이제 속성 선언 구문을 사용하여 컨트롤에 두 가지 속성, 즉 경보가 꺼지는 날짜와 시간 값을 저장하는 `AlarmTime`과 경보가 설정되는지 여부를 나타내는 `AlarmSet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-202">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="25826-203">복합 컨트롤에 속성을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="25826-203">To add properties to your composite control</span></span>

1. <span data-ttu-id="25826-204">솔루션 탐색기에서 **ctlAlarmClock**을 마우스 오른쪽 단추로 클릭한 후 **코드 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-204">In Solution Explorer, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="25826-205">`Public Class ctlAlarmClock`으로 나타나는 ctlAlarmClock 컨트롤에 대한 클래스 선언을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-205">Locate the class declaration for the ctlAlarmClock control, which appears as `Public Class ctlAlarmClock`.</span></span>  <span data-ttu-id="25826-206">클래스 선언에서 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-206">In the class declaration, insert the following code.</span></span>

    ```vb
    Private dteAlarmTime As Date
    Private blnAlarmSet As Boolean
    ' These properties will be declared as Public to allow future
    ' developers to access them.
    Public Property AlarmTime() As Date
        Get
            Return dteAlarmTime
        End Get
        Set(ByVal value as Date)
            dteAlarmTime = value
        End Set
    End Property
    Public Property AlarmSet() As Boolean
        Get
            Return blnAlarmSet
        End Get
        Set(ByVal value as Boolean)
            blnAlarmSet = value
        End Set
    End Property
    ```

### <a name="adding-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="25826-207">컨트롤의 그래픽 인터페이스에 추가</span><span class="sxs-lookup"><span data-stu-id="25826-207">Adding to the Graphical Interface of the Control</span></span>
 <span data-ttu-id="25826-208">상속된 컨트롤에는 상속 원본 컨트롤과 동일한 시각적 인터페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-208">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="25826-209">부모 컨트롤과 동일한 구성 요소 컨트롤을 소유하지만, 구체적으로 노출되지 않는 한, 구성 요소 컨트롤의 속성을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-209">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="25826-210">복합 컨트롤에 추가하는 것과 같은 방법으로 상속된 복합 컨트롤의 그래픽 인터페이스에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-210">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="25826-211">알람 시계의 시각적 인터페이스에 계속 추가하려면 경보가 울릴 때 깜박거리는 레이블 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-211">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="25826-212">레이블 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="25826-212">To add the label control</span></span>

1. <span data-ttu-id="25826-213">솔루션 탐색기에서 **ctlAlarmClock**을 마우스 오른쪽 단추로 클릭한 후 **뷰 디자이너**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-213">In Solution Explorer, right-click **ctlAlarmClock**, and click **View Designer**.</span></span>

     <span data-ttu-id="25826-214">`ctlAlarmClock`에 대한 디자이너가 주 창에 열립니다.</span><span class="sxs-lookup"><span data-stu-id="25826-214">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="25826-215">`lblDisplay`(컨트롤의 표시 부분)를 클릭하고 속성 창을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-215">Click `lblDisplay` (the display portion of the control), and view the Properties window.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25826-216">모든 속성이 표시되는 동안 흐리게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-216">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="25826-217">이것은 이러한 속성이 `lblDisplay`의 기본 속성이며 속성 창에서 수정하거나 액세스할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="25826-217">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="25826-218">기본적으로 복합 컨트롤에 포함된 컨트롤은 `Private`이며 해당 속성은 어떤 방법으로도 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-218">By default, controls contained in a composite control are `Private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25826-219">복합 컨트롤의 후속 사용자가 내부 컨트롤에 액세스할 수 있도록 하려면 이를 `Public` 또는 `Protected`로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-219">If you want subsequent users of your composite control to have access to its internal controls, declare them as `Public` or `Protected`.</span></span> <span data-ttu-id="25826-220">이렇게 하면 적절한 코드를 사용하여 복합 컨트롤 내에 포함된 컨트롤의 속성을 설정 및 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-220">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="25826-221">복합 컨트롤에 컨트롤을 추가 합니다. <xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="25826-221">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="25826-222">마우스를 사용 하 여 <xref:System.Windows.Forms.Label> 컨트롤을 표시 상자 바로 아래로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="25826-222">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="25826-223">속성 창에서 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-223">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="25826-224">속성</span><span class="sxs-lookup"><span data-stu-id="25826-224">Property</span></span>|<span data-ttu-id="25826-225">설정</span><span class="sxs-lookup"><span data-stu-id="25826-225">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="25826-226">**이름**</span><span class="sxs-lookup"><span data-stu-id="25826-226">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="25826-227">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="25826-227">**Text**</span></span>|<span data-ttu-id="25826-228">**Alarm!**</span><span class="sxs-lookup"><span data-stu-id="25826-228">**Alarm!**</span></span>|
    |<span data-ttu-id="25826-229">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="25826-229">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="25826-230">**Visible**</span><span class="sxs-lookup"><span data-stu-id="25826-230">**Visible**</span></span>|`False`|

### <a name="adding-the-alarm-functionality"></a><span data-ttu-id="25826-231">경보 기능 추가</span><span class="sxs-lookup"><span data-stu-id="25826-231">Adding the Alarm Functionality</span></span>
 <span data-ttu-id="25826-232">이전 프로시저에서는 복합 컨트롤에서 경보 기능을 설정하는 속성 및 컨트롤을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-232">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="25826-233">이 프로시저에서는 현재 시간을 경보 시간과 비교하여 같으면 알람을 울리고 깜박이는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-233">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to sound and flash an alarm.</span></span> <span data-ttu-id="25826-234">`ctlClock`의 `Timer1_Tick` 메소드를 재정의하고 코드를 더 추가하여 `ctlClock`의 모든 고유 기능을 유지하면서 `ctlAlarmClock`의 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-234">By overriding the `Timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="25826-235">ctlClock의 Timer1_Tick 메서드를 재정의하려면</span><span class="sxs-lookup"><span data-stu-id="25826-235">To override the Timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="25826-236">솔루션 탐색기에서 **ctlAlarmClock.vb**를 마우스 오른쪽 단추로 클릭한 후 **코드 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-236">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Code**.</span></span>

2. <span data-ttu-id="25826-237">`Private blnAlarmSet As Boolean` 문을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-237">Locate the `Private blnAlarmSet As Boolean` statement.</span></span> <span data-ttu-id="25826-238">바로 아래에서 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-238">Immediately beneath it, add the following statement.</span></span>

    ```vb
    Dim blnColorTicker as Boolean
    ```

3. <span data-ttu-id="25826-239">페이지 하단에서 `End Class` 문을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-239">Locate the `End Class` statement at the bottom of the page.</span></span> <span data-ttu-id="25826-240">`End Class` 문 바로 앞에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-240">Just before the `End Class` statement, add the following code.</span></span>

    ```vb
    Protected Overrides Sub Timer1_Tick(ByVal sender As Object, ByVal e _
        As System.EventArgs)
        ' Calls the Timer1_Tick method of ctlClock.
        MyBase.Timer1_Tick(sender, e)
        ' Checks to see if the Alarm is set.
        If AlarmSet = False Then
            Exit Sub
        End If
        ' If the date, hour, and minute of the alarm time are the same as
        ' now, flash and beep an alarm.
        If AlarmTime.Date = Now.Date And AlarmTime.Hour = Now.Hour And _
            AlarmTime.Minute = Now.Minute Then
            ' Sounds an audible beep.
            Beep()
            ' Sets lblAlarmVisible to True, and changes the background color based on the
            ' value of blnColorTicker. The background color of the label will
            ' flash once per tick of the clock.
            lblAlarm.Visible = True
            If blnColorTicker = False Then
                lblAlarm.BackColor = Color.PeachPuff
                blnColorTicker = True
            Else
                lblAlarm.BackColor = Color.Plum
                blnColorTicker = False
            End If
        Else
            ' Once the alarm has sounded for a minute, the label is made
            ' invisible again.
            lblAlarm.Visible = False
        End If
    End Sub
    ```

     <span data-ttu-id="25826-241">이 코드를 추가하려면 여러 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-241">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="25826-242">`Overrides` 문은 기본 컨트롤에서 상속된 메서드 대신, 이 메서드를 사용하도록 컨트롤에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-242">The `Overrides` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="25826-243">이 메서드가 호출되면 `MyBase.Timer1_Tick` 문을 호출하여 이를 재정의하는 메서드를 호출하여 원래 컨트롤에 통합된 모든 기능이 이 컨트롤에서 재현되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-243">When this method is called, it calls the method it overrides by invoking the `MyBase.Timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="25826-244">그런 다음 경보 기능을 통합하는 추가 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-244">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="25826-245">경보가 발생하면 깜박이는 레이블 컨트롤이 나타나고 신호음이 울립니다.</span><span class="sxs-lookup"><span data-stu-id="25826-245">A flashing label control will appear when the alarm occurs, and an audible beep will be heard.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25826-246">상속된 이벤트 처리기를 재정의하므로 `Handles` 키워드로 이벤트를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-246">Because you are overriding an inherited event handler, you do not have to specify the event with the `Handles` keyword.</span></span> <span data-ttu-id="25826-247">이벤트가 이미 후크되었습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-247">The event is already hooked up.</span></span> <span data-ttu-id="25826-248">재정의하는 모든 내용은 처리기의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="25826-248">All you are overriding is the implementation of the handler.</span></span>

     <span data-ttu-id="25826-249">알람 시계 컨트롤이 거의 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-249">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="25826-250">이제 해제하는 방법을 구현하는 것만 남았습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-250">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="25826-251">이를 위해서는 `lblAlarm_Click` 메서드에 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-251">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="25826-252">shutoff 메서드를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="25826-252">To implement the shutoff method</span></span>

1. <span data-ttu-id="25826-253">솔루션 탐색기에서 **ctlAlarmClock.vb**를 마우스 오른쪽 단추로 클릭한 후 **뷰 디자이너**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-253">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="25826-254">디자이너에서 **lblAlarm**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-254">In the designer, double-click **lblAlarm**.</span></span> <span data-ttu-id="25826-255">**코드 편집기**에 `Private Sub lblAlarm_Click` 행이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="25826-255">The **Code Editor** opens to the `Private Sub lblAlarm_Click` line.</span></span>

3. <span data-ttu-id="25826-256">이 메서드를 다음 코드와 비슷하도록 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-256">Modify this method so that it resembles the following code.</span></span>

    ```vb
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _
     System.EventArgs) Handles lblAlarm.Click
        ' Turns off the alarm.
        AlarmSet = False
        ' Hides the flashing label.
        lblAlarm.Visible = False
    End Sub
    ```

4. <span data-ttu-id="25826-257">**파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-257">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="using-the-inherited-control-on-a-form"></a><span data-ttu-id="25826-258">폼에서 상속된 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="25826-258">Using the Inherited Control on a Form</span></span>
 <span data-ttu-id="25826-259">기본 클래스 컨트롤을 테스트 한 것과 같은 방법으로 상속 된 컨트롤을 `ctlClock`테스트할 수 있습니다. F5 키를 눌러 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**에서 컨트롤을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-259">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="25826-260">자세한 내용은 [방법: UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)의 런타임 동작을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-260">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

 <span data-ttu-id="25826-261">사용할 컨트롤을 배치하려면 폼에서 컨트롤을 호스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-261">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="25826-262">표준 복합 컨트롤과 마찬가지로 상속된 복합 컨트롤은 독립 실행형으로 사용할 수 없으며 폼 또는 다른 컨테이너에서 호스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-262">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="25826-263">`ctlAlarmClock`은 보다 심도 있는 기능을 포함하므로 테스트하려면 추가 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-263">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="25826-264">이 프로시저에서는 `ctlAlarmClock`의 기능을 테스트하는 간단한 프로그램을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-264">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="25826-265">`ctlAlarmClock`의 `AlarmTime` 속성을 설정하고 표시하는 코드를 작성하고 고유한 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-265">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="25826-266">컨트롤을 빌드하고 테스트 폼에 추가하려면</span><span class="sxs-lookup"><span data-stu-id="25826-266">To build and add your control to a test form</span></span>

1. <span data-ttu-id="25826-267">솔루션 탐색기에서 **ctlClockLib**를 마우스 오른쪽 단추로 클릭한 후 **빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-267">In Solution Explorer, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="25826-268">**파일** 메뉴에서 **추가**를 가리킨 다음 **새 프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-268">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>

3. <span data-ttu-id="25826-269">솔루션에 새 **Windows 애플리케이션** 프로젝트를 추가하고 이름을 `Test`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-269">Add a new **Windows Application** project to the solution, and name it `Test`.</span></span>

     <span data-ttu-id="25826-270">**Test** 프로젝트가 솔루션 탐색기에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-270">The **Test** project is added to Solution Explorer.</span></span>

4. <span data-ttu-id="25826-271">솔루션 탐색기에서 `Test` 프로젝트 노드를 마우스 오른쪽 단추로 클릭한 다음 **참조 추가**를 클릭하면 **참조 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-271">In Solution Explorer, right-click the `Test` project node, and then click **Add Reference** to display the **Add Reference** dialog box.</span></span>

5. <span data-ttu-id="25826-272">**프로젝트**로 레이블이 지정된 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-272">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="25826-273">**ctlClockLib** 프로젝트가 **프로젝트 이름** 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-273">The project **ctlClockLib** will be listed under **Project Name**.</span></span> <span data-ttu-id="25826-274">**ctlClockLib**을 두 번 클릭하여 테스트 프로젝트에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-274">Double-click **ctlClockLib** to add the reference to the test project.</span></span>

6. <span data-ttu-id="25826-275">솔루션 탐색기에서 **Test**를 마우스 오른쪽 단추로 클릭한 후 **빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-275">In Solution Explorer, right-click **Test**, and then click **Build**.</span></span>

7. <span data-ttu-id="25826-276">**도구 상자**에서 **ctlClockLib 구성 요소** 노드를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-276">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

8. <span data-ttu-id="25826-277">**ctlAlarmClock**을 두 번 클릭하여 `ctlAlarmClock`의 인스턴스를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-277">Double-click **ctlAlarmClock** to add an instance of `ctlAlarmClock` to your form.</span></span>

9. <span data-ttu-id="25826-278">**도구 상자**에서 **DateTimePicker** <xref:System.Windows.Forms.DateTimePicker> 를 찾아 두 번 클릭 하 여 <xref:System.Windows.Forms.Label> 폼에 컨트롤을 추가한 다음 **레이블을**두 번 클릭 하 여 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-278">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

10. <span data-ttu-id="25826-279">마우스를 사용하여 폼의 편리한 위치에 컨트롤을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-279">Use the mouse to position the controls in a convenient place on the form.</span></span>

11. <span data-ttu-id="25826-280">다음 방식으로 이러한 컨트롤의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-280">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="25826-281">컨트롤</span><span class="sxs-lookup"><span data-stu-id="25826-281">Control</span></span>|<span data-ttu-id="25826-282">속성</span><span class="sxs-lookup"><span data-stu-id="25826-282">Property</span></span>|<span data-ttu-id="25826-283">값</span><span class="sxs-lookup"><span data-stu-id="25826-283">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="25826-284">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="25826-284">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="25826-285">**이름**</span><span class="sxs-lookup"><span data-stu-id="25826-285">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="25826-286">**이름**</span><span class="sxs-lookup"><span data-stu-id="25826-286">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="25826-287">**Format**</span><span class="sxs-lookup"><span data-stu-id="25826-287">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

12. <span data-ttu-id="25826-288">디자이너에서 **dtpTest**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-288">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="25826-289">**코드 편집기**에 `Private Sub dtpTest_ValueChanged`가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="25826-289">The **Code Editor** opens to `Private Sub dtpTest_ValueChanged`.</span></span>

13. <span data-ttu-id="25826-290">다음과 비슷하도록 코드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-290">Modify the code so that it resembles the following.</span></span>

    ```vb
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _
        System.EventArgs) Handles dtpTest.ValueChanged
        ctlAlarmClock1.AlarmTime = dtpTest.Value
        ctlAlarmClock1.AlarmSet = True
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _
            "hh:mm")
    End Sub
    ```

14. <span data-ttu-id="25826-291">솔루션 탐색기에서 **Test**를 마우스 오른쪽 단추로 클릭한 다음 **시작 프로젝트로 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-291">In Solution Explorer, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

15. <span data-ttu-id="25826-292">**디버그** 메뉴에서 **디버깅 시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-292">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="25826-293">테스트 프로그램이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-293">The test program starts.</span></span> <span data-ttu-id="25826-294">`ctlAlarmClock` 컨트롤에서 현재 시간을 업데이트 하 고 시작 시간이 <xref:System.Windows.Forms.DateTimePicker> 컨트롤에 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-294">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

16. <span data-ttu-id="25826-295">시간의 분 <xref:System.Windows.Forms.DateTimePicker> 이 표시 되는 위치를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-295">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

17. <span data-ttu-id="25826-296">키보드를 사용하여 `ctlAlarmClock`으로 표시된 현재 시간보다 1분 큰 값(분)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-296">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="25826-297">경보 설정 시간이 `lblTest`에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="25826-297">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="25826-298">표시된 시간이 경보 설정 시간에 도달할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="25826-298">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="25826-299">표시된 시간이 경보 설정 시간에 도달하면 신호음이 울리고 `lblAlarm`이 깜박입니다.</span><span class="sxs-lookup"><span data-stu-id="25826-299">When the displayed time reaches the time to which the alarm is set, the beep will sound and `lblAlarm` will flash.</span></span>

18. <span data-ttu-id="25826-300">`lblAlarm`을 클릭하여 경보를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="25826-300">Turn off the alarm by clicking `lblAlarm`.</span></span> <span data-ttu-id="25826-301">이제 경보를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-301">You may now reset the alarm.</span></span>

     <span data-ttu-id="25826-302">이 연습에서 여러 가지 주요 개념을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-302">This walkthrough has covered a number of key concepts.</span></span> <span data-ttu-id="25826-303">컨트롤 및 구성 요소를 복합 컨트롤 컨테이너에 결합하여 복합 컨트롤을 만드는 방법을 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-303">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="25826-304">컨트롤에 속성을 추가하고 사용자 지정 기능을 작성하는 코드를 작성하는 방법도 알아봤습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-304">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="25826-305">마지막 섹션에서는 상속성을 통해 지정된 복합 컨트롤의 기능을 확장하고 해당 메서드를 재정의하여 호스트 메서드의 기능을 수정해보았습니다.</span><span class="sxs-lookup"><span data-stu-id="25826-305">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="25826-306">참고자료</span><span class="sxs-lookup"><span data-stu-id="25826-306">See also</span></span>

- [<span data-ttu-id="25826-307">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="25826-307">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="25826-308">방법: 복합 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="25826-308">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="25826-309">방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시</span><span class="sxs-lookup"><span data-stu-id="25826-309">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
