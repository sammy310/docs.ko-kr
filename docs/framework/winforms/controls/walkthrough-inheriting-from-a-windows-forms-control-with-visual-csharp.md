---
title: 컨트롤에서 상속
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 713ccf97a73ce9684b9124a121369f22751861d0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740144"
---
# <a name="walkthrough-inherit-from-a-windows-forms-control-with-c"></a><span data-ttu-id="2425c-102">연습: C\#를 사용 하 여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="2425c-102">Walkthrough: Inherit from a Windows Forms Control with C\#</span></span>

<span data-ttu-id="2425c-103">를 C#사용 하면 *상속*을 통해 강력한 사용자 지정 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-103">With C#, you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="2425c-104">상속을 통해 표준 Windows Forms 컨트롤의 모든 고유 기능을 유지하면서 사용자 지정 기능을 통합하는 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="2425c-105">이 연습에서는 `ValueButton`이라는 간단한 상속된 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="2425c-106">이 단추는 표준 Windows Forms <xref:System.Windows.Forms.Button> 컨트롤에서 기능을 상속 하 고 `ButtonValue`이라는 사용자 지정 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="2425c-107">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2425c-107">Create the Project</span></span>

<span data-ttu-id="2425c-108">새 프로젝트를 만들 때는 루트 네임스페이스, 어셈블리 이름 및 프로젝트 이름을 설정하기 위해 이름을 지정하고 기본 구성 요소가 올바른 네임스페이스에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-108">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="2425c-109">ValueButtonLib 컨트롤 라이브러리 및 ValueButton 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="2425c-109">To create the ValueButtonLib control library and the ValueButton control</span></span>

1. <span data-ttu-id="2425c-110">Visual Studio에서 새 **Windows Forms 컨트롤 라이브러리** 프로젝트를 만들고 이름을 **Valuebuttonlib**로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-110">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ValueButtonLib**.</span></span>

     <span data-ttu-id="2425c-111">프로젝트 이름, `ValueButtonLib`는 기본적으로 루트 네임스페이스에도 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-111">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="2425c-112">루트 네임스페이스는 어셈블리에서 구성 요소의 이름을 정규화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-112">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="2425c-113">예를 들어 두 어셈블리에서 `ValueButton`이라는 구성 요소를 제공하면 `ValueButton`을 사용하여 `ValueButtonLib.ValueButton` 구성 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-113">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="2425c-114">자세한 내용은 [네임스페이스](../../../csharp/programming-guide/namespaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2425c-114">For more information, see [Namespaces](../../../csharp/programming-guide/namespaces/index.md).</span></span>

2. <span data-ttu-id="2425c-115">**솔루션 탐색기**에서 **UserControl1.cs**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **이름 바꾸기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-115">In **Solution Explorer**, right-click **UserControl1.cs**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="2425c-116">파일 이름을 **ValueButton.cs**로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-116">Change the file name to **ValueButton.cs**.</span></span> <span data-ttu-id="2425c-117">코드 요소 ' **'에 대한 모든 참조 이름을 변경할지 묻는 메시지가 표시되면** 예`UserControl1` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-117">Click the **Yes** button when you are asked if you want to rename all references to the code element '`UserControl1`'.</span></span>

3. <span data-ttu-id="2425c-118">**솔루션 탐색기**에서 **ValueButton.cs**를 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-118">In **Solution Explorer**, right-click **ValueButton.cs** and select **View Code**.</span></span>

4. <span data-ttu-id="2425c-119">`class` statement 줄을 찾아 `public partial class ValueButton`하 고이 컨트롤이 <xref:System.Windows.Forms.UserControl>에서 상속 되는 형식을 <xref:System.Windows.Forms.Button>로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-119">Locate the `class` statement line, `public partial class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="2425c-120">이렇게 하면 상속 된 컨트롤이 <xref:System.Windows.Forms.Button> 컨트롤의 모든 기능을 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-120">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>

5. <span data-ttu-id="2425c-121">**솔루션 탐색기**에서 **ValueButton.cs** 노드를 열어 디자이너에서 생성한 코드 파일인 **ValueButton.Designer.cs**를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-121">In **Solution Explorer**, open the **ValueButton.cs** node to display the designer-generated code file, **ValueButton.Designer.cs**.</span></span> <span data-ttu-id="2425c-122">**코드 편집기**에서 이 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-122">Open this file in the **Code Editor**.</span></span>

6. <span data-ttu-id="2425c-123">`InitializeComponent` 메서드를 찾고 <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> 속성을 할당 하는 줄을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-123">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="2425c-124">이 속성은 <xref:System.Windows.Forms.Button> 컨트롤에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-124">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>

7. <span data-ttu-id="2425c-125">**파일** 메뉴에서 **모두 저장**을 선택하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-125">From the **File** menu, choose **Save All** to save the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2425c-126">비주얼 디자이너는 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-126">A visual designer is no longer available.</span></span> <span data-ttu-id="2425c-127"><xref:System.Windows.Forms.Button> 컨트롤은 자체적으로 그리기를 수행 하므로 디자이너에서 모양을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-127">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="2425c-128">코드에서 수정 되지 않는 한, 시각적 표현은이 클래스에서 상속 하는 클래스 (즉, <xref:System.Windows.Forms.Button>)와 정확 하 게 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-128">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span> <span data-ttu-id="2425c-129">UI 요소가 없는 구성 요소를 디자인 화면에 계속 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-129">You can still add components, which have no UI elements, to the design surface.</span></span>

## <a name="add-a-property-to-your-inherited-control"></a><span data-ttu-id="2425c-130">상속 된 컨트롤에 속성 추가</span><span class="sxs-lookup"><span data-stu-id="2425c-130">Add a Property to Your Inherited Control</span></span>

<span data-ttu-id="2425c-131">상속된 Windows Forms 컨트롤의 한 가지 가능한 용도는 표준 Windows Forms 컨트롤과 모양 및 느낌이 동일하지만 사용자 지정 속성을 노출하는 컨트롤을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-131">One possible use of inherited Windows Forms controls is the creation of controls that are identical in look and feel of standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="2425c-132">이 섹션에서는 `ButtonValue`라는 속성을 컨트롤에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-132">In this section, you will add a property called `ButtonValue` to your control.</span></span>

### <a name="to-add-the-value-property"></a><span data-ttu-id="2425c-133">Value 속성을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="2425c-133">To add the Value property</span></span>

1. <span data-ttu-id="2425c-134">**솔루션 탐색기**에서 **ValueButton.cs**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-134">In **Solution Explorer**, right-click **ValueButton.cs**, and then click **View Code** from the shortcut menu.</span></span>

2. <span data-ttu-id="2425c-135">`class` 문을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-135">Locate the `class` statement.</span></span> <span data-ttu-id="2425c-136">`{` 바로 뒤에 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-136">Immediately after the `{`, type the following code:</span></span>

    ```csharp
    // Creates the private variable that will store the value of your
    // property.
    private int varValue;
    // Declares the property.
    public int ButtonValue
    {
       // Sets the method for retrieving the value of your property.
       get
       {
          return varValue;
       }
       // Sets the method for setting the value of your property.
       set
       {
          varValue = value;
       }
    }
    ```

     <span data-ttu-id="2425c-137">이 코드는 `ButtonValue` 속성을 저장 및 검색할 메서드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-137">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="2425c-138">`get` 문은 반환된 값을 private 변수 `varValue`에 저장된 값으로 설정하고 `set` 문은 `value` 키워드를 사용하여 private 변수의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-138">The `get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `set` statement sets the value of the private variable by use of the `value` keyword.</span></span>

3. <span data-ttu-id="2425c-139">**파일** 메뉴에서 **모두 저장**을 선택하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-139">From the **File** menu, choose **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="2425c-140">컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="2425c-140">Test the control</span></span>

<span data-ttu-id="2425c-141">컨트롤은 독립 실행형 프로젝트가 아니며 컨테이너에서 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-141">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="2425c-142">컨트롤을 테스트하려면 컨트롤을 실행할 테스트 프로젝트를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-142">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="2425c-143">또한 컨트롤을 빌드(컴파일)하여 컨트롤에서 테스트 프로젝트에 액세스할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-143">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="2425c-144">이 섹션에서는 컨트롤을 테스트하고 Windows Form에서 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-144">In this section, you will build your control and test it in a Windows Form.</span></span>

### <a name="to-build-your-control"></a><span data-ttu-id="2425c-145">컨트롤을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="2425c-145">To build your control</span></span>

<span data-ttu-id="2425c-146">**빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-146">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="2425c-147">컴파일러 오류 또는 경고 없이 빌드에 성공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-147">The build should be successful with no compiler errors or warnings.</span></span>

### <a name="to-create-a-test-project"></a><span data-ttu-id="2425c-148">테스트 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="2425c-148">To create a test project</span></span>

1. <span data-ttu-id="2425c-149">**파일** 메뉴에서 **추가**를 가리킨 후 **새 프로젝트**를 클릭하여 **새 프로젝트 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-149">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="2425c-150">**Windows** 노드를 선택하고 **Visual C#** 노드 아래에서 **Windows Forms 애플리케이션**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-150">Select the **Windows** node, beneath the **Visual C#** node, and click **Windows Forms Application**.</span></span>

3. <span data-ttu-id="2425c-151">**이름** 상자에 **Test**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-151">In the **Name** box, enter **Test**.</span></span>

4. <span data-ttu-id="2425c-152">**솔루션 탐색기**에서 테스트 프로젝트에 대한 **참조** 노드를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **참조 추가**를 선택하면 **참조 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-152">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>

5. <span data-ttu-id="2425c-153">**프로젝트**로 레이블이 지정된 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-153">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="2425c-154">ValueButtonLib 프로젝트가 **프로젝트 이름**아래에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-154">Your ValueButtonLib project will be listed under **Project Name**.</span></span> <span data-ttu-id="2425c-155">프로젝트를 두 번 클릭하여 테스트 프로젝트에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-155">Double-click the project to add the reference to the test project.</span></span>

6. <span data-ttu-id="2425c-156">**솔루션 탐색기**에서 **Test**를 마우스 오른쪽 단추로 클릭한 후 **빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-156">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>

### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="2425c-157">폼에 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="2425c-157">To add your control to the form</span></span>

1. <span data-ttu-id="2425c-158">**솔루션 탐색기**에서 **Form1.cs**를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **뷰 디자이너**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-158">In **Solution Explorer**, right-click **Form1.cs** and choose **View Designer** from the shortcut menu.</span></span>

2. <span data-ttu-id="2425c-159">**도구 상자**에서 **Valuebuttonlib 구성 요소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-159">In the **Toolbox**, select **ValueButtonLib Components**.</span></span> <span data-ttu-id="2425c-160">**ValueButton**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-160">Double-click **ValueButton**.</span></span>

     <span data-ttu-id="2425c-161">**ValueButton**이 폼에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-161">A **ValueButton** appears on the form.</span></span>

3. <span data-ttu-id="2425c-162">**ValueButton**을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-162">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="2425c-163">**속성** 창에서 이 컨트롤의 속성을 점검합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-163">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="2425c-164">추가 속성인 ButtonValue를 제외 하 고는 표준 단추에 의해 노출 되는 속성과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-164">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, ButtonValue.</span></span>

5. <span data-ttu-id="2425c-165">**Buttonvalue** 속성을 **5**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-165">Set the **ButtonValue** property to **5**.</span></span>

6. <span data-ttu-id="2425c-166">**도구 상자**의 **모두 Windows Forms** 탭에서 **레이블** 을 두 번 클릭 하 여 폼에 <xref:System.Windows.Forms.Label> 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-166">In the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>

7. <span data-ttu-id="2425c-167">폼 가운데에 레이블을 다시 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-167">Relocate the label to the center of the form.</span></span>

8. <span data-ttu-id="2425c-168">`valueButton1`을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-168">Double-click `valueButton1`.</span></span>

     <span data-ttu-id="2425c-169">**코드 편집기**에 `valueButton1_Click` 이벤트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-169">The **Code Editor** opens to the `valueButton1_Click` event.</span></span>

9. <span data-ttu-id="2425c-170">다음 코드 행을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-170">Insert the following line of code.</span></span>

    ```csharp
    label1.Text = valueButton1.ButtonValue.ToString();
    ```

10. <span data-ttu-id="2425c-171">**솔루션 탐색기**에서 **Test**를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-171">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>

11. <span data-ttu-id="2425c-172">**디버그** 메뉴에서 **디버깅 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-172">From the **Debug** menu, select **Start Debugging**.</span></span>

     <span data-ttu-id="2425c-173">`Form1`이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-173">`Form1` appears.</span></span>

12. <span data-ttu-id="2425c-174">`valueButton1`을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-174">Click `valueButton1`.</span></span>

     <span data-ttu-id="2425c-175">숫자 '5'가 `label1`에 표시되며 상속된 컨트롤의 `ButtonValue` 속성이 `label1` 메서드를 통해 `valueButton1_Click`에 전달되었음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-175">The numeral '5' is displayed in `label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `label1` through the `valueButton1_Click` method.</span></span> <span data-ttu-id="2425c-176">따라서 `ValueButton` 컨트롤은 표준 Windows Forms 단추의 모든 기능을 상속하지만 추가 사용자 지정 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="2425c-176">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>

## <a name="see-also"></a><span data-ttu-id="2425c-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2425c-177">See also</span></span>

- [<span data-ttu-id="2425c-178">방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시</span><span class="sxs-lookup"><span data-stu-id="2425c-178">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="2425c-179">연습: Visual C#에서 합성 컨트롤 제작</span><span class="sxs-lookup"><span data-stu-id="2425c-179">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
