---
title: '연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: fb58d7c8-b702-4478-ad31-b00cae118882
ms.openlocfilehash: 378d7b0c67791e6c48e9859e0546594df3ccc85e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931015"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic"></a><span data-ttu-id="b32f7-102">연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="b32f7-102">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>
<span data-ttu-id="b32f7-103">Visual Basic를 사용 하 여 *상속*을 통해 강력한 사용자 지정 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-103">With Visual Basic, you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="b32f7-104">상속을 통해 표준 Windows Forms 컨트롤의 모든 고유 기능을 유지하면서 사용자 지정 기능을 통합하는 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="b32f7-105">이 연습에서는 `ValueButton`이라는 간단한 상속된 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="b32f7-106">이 단추는 표준 Windows Forms <xref:System.Windows.Forms.Button> 컨트롤에서 기능을 상속 하 고 라는 `ButtonValue`사용자 지정 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="b32f7-107">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="b32f7-107">Creating the Project</span></span>
 <span data-ttu-id="b32f7-108">새 프로젝트를 만들 때는 루트 네임스페이스, 어셈블리 이름 및 프로젝트 이름을 설정하기 위해 이름을 지정하고 기본 구성 요소가 올바른 네임스페이스에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-108">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="b32f7-109">ValueButtonLib 컨트롤 라이브러리 및 ValueButton 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b32f7-109">To create the ValueButtonLib control library and the ValueButton control</span></span>

1. <span data-ttu-id="b32f7-110">**파일** 메뉴에서 **새로 만들기**를 가리키고 **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-110">On the **File** menu, point to **New** and then click **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="b32f7-111">Visual Basic 프로젝트 목록에서 **Windows Forms 컨트롤 라이브러리** 프로젝트 템플릿을 선택 하 고 **이름** 상자에을 `ValueButtonLib` 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-111">Select the **Windows Forms Control Library** project template from the list of Visual Basic projects, and type `ValueButtonLib` in the **Name** box.</span></span>

     <span data-ttu-id="b32f7-112">프로젝트 이름, `ValueButtonLib`는 기본적으로 루트 네임스페이스에도 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-112">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="b32f7-113">루트 네임스페이스는 어셈블리에서 구성 요소의 이름을 정규화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-113">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="b32f7-114">예를 들어 두 어셈블리에서 `ValueButton`이라는 구성 요소를 제공하면 `ValueButtonLib.ValueButton`을 사용하여 `ValueButton` 구성 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-114">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="b32f7-115">자세한 내용은 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b32f7-115">For more information, see [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>

3. <span data-ttu-id="b32f7-116">**솔루션 탐색기**에서 **UserControl1.vb**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **이름 바꾸기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-116">In **Solution Explorer**, right-click **UserControl1.vb**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="b32f7-117">파일 이름을 `ValueButton.vb`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-117">Change the file name to `ValueButton.vb`.</span></span> <span data-ttu-id="b32f7-118">코드 요소 'UserControl1'에 대한 모든 참조 이름을 변경할지 묻는 메시지가 표시되면 **예** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-118">Click the **Yes** button when you are asked if you want to rename all references to the code element 'UserControl1'.</span></span>

4. <span data-ttu-id="b32f7-119">**솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>

5. <span data-ttu-id="b32f7-120">**ValueButton.vb** 노드를 열어 디자이너에서 생성한 코드 파일인 **ValueButton.Designer.vb**를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-120">Open the **ValueButton.vb** node to display the designer-generated code file, **ValueButton.Designer.vb**.</span></span> <span data-ttu-id="b32f7-121">**코드 편집기**에서 이 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-121">Open this file in the **Code Editor**.</span></span>

6. <span data-ttu-id="b32f7-122">문을 찾은 다음이 컨트롤이 상속 <xref:System.Windows.Forms.UserControl> 되는 형식을로 <xref:System.Windows.Forms.Button>변경 합니다. `Partial Public Class ValueButton` `Class`</span><span class="sxs-lookup"><span data-stu-id="b32f7-122">Locate the `Class` statement, `Partial Public Class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="b32f7-123">이렇게 하면 상속 된 컨트롤이 <xref:System.Windows.Forms.Button> 컨트롤의 모든 기능을 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-123">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>

7. <span data-ttu-id="b32f7-124">메서드를 `InitializeComponent` 찾아 <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> 속성을 할당 하는 줄을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-124">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="b32f7-125">이 속성은 <xref:System.Windows.Forms.Button> 컨트롤에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-125">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>

8. <span data-ttu-id="b32f7-126">**파일** 메뉴에서 **모두 저장**을 선택하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-126">From the **File** menu, choose **Save All** to save the project.</span></span>

     <span data-ttu-id="b32f7-127">비주얼 디자이너는 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-127">Note that a visual designer is no longer available.</span></span> <span data-ttu-id="b32f7-128">컨트롤은 <xref:System.Windows.Forms.Button> 자체적으로 그리기를 수행 하므로 디자이너에서 모양을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-128">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="b32f7-129">시각적 표시는 코드에서 수정 되지 않는 한, 상속 된 클래스 (즉, <xref:System.Windows.Forms.Button>)와 정확히 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-129">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span>

> [!NOTE]
> <span data-ttu-id="b32f7-130">UI 요소가 없는 구성 요소를 디자인 화면에 계속 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-130">You can still add components, which have no UI elements, to the design surface.</span></span>

## <a name="adding-a-property-to-your-inherited-control"></a><span data-ttu-id="b32f7-131">상속된 컨트롤에 속성 추가</span><span class="sxs-lookup"><span data-stu-id="b32f7-131">Adding a Property to Your Inherited Control</span></span>
 <span data-ttu-id="b32f7-132">상속된 Windows Forms 컨트롤의 한 가지 가능한 용도는 표준 Windows Forms 컨트롤과 모양 및 동작(모양 및 느낌)이 동일하지만 사용자 지정 속성을 노출하는 컨트롤을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-132">One possible use of inherited Windows Forms controls is the creation of controls that are identical in appearance and behavior (look and feel) to standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="b32f7-133">이 섹션에서는 `ButtonValue`라는 속성을 컨트롤에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-133">In this section, you will add a property called `ButtonValue` to your control.</span></span>

### <a name="to-add-the-value-property"></a><span data-ttu-id="b32f7-134">Value 속성을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="b32f7-134">To add the Value property</span></span>

1. <span data-ttu-id="b32f7-135">**솔루션 탐색기**에서 **ValueButton.vb**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-135">In **Solution Explorer**, right-click **ValueButton.vb**, and then click **View Code** from the shortcut menu.</span></span>

2. <span data-ttu-id="b32f7-136">`Public Class ValueButton` 문을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-136">Locate the `Public Class ValueButton` statement.</span></span> <span data-ttu-id="b32f7-137">이 문 바로 아래에 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-137">Immediately beneath this statement, type the following code:</span></span>

    ```vb
    ' Creates the private variable that will store the value of your
    ' property.
    Private varValue as integer
    ' Declares the property.
    Property ButtonValue() as Integer
    ' Sets the method for retrieving the value of your property.
       Get
          Return varValue
       End Get
    ' Sets the method for setting the value of your property.
       Set(ByVal Value as Integer)
          varValue = Value
       End Set
    End Property
    ```

     <span data-ttu-id="b32f7-138">이 코드는 `ButtonValue` 속성을 저장 및 검색할 메서드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-138">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="b32f7-139">`Get` 문은 반환된 값을 private 변수 `varValue`에 저장된 값으로 설정하고 `Set` 문은 `Value` 키워드를 사용하여 private 변수의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-139">The `Get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `Set` statement sets the value of the private variable by use of the `Value` keyword.</span></span>

3. <span data-ttu-id="b32f7-140">**파일** 메뉴에서 **모두 저장**을 선택하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-140">From the **File** menu, choose **Save All** to save the project.</span></span>

## <a name="testing-your-control"></a><span data-ttu-id="b32f7-141">컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="b32f7-141">Testing Your Control</span></span>
 <span data-ttu-id="b32f7-142">컨트롤은 독립 실행형 프로젝트가 아니며 컨테이너에서 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-142">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="b32f7-143">컨트롤을 테스트하려면 컨트롤을 실행할 테스트 프로젝트를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-143">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="b32f7-144">또한 컨트롤을 빌드(컴파일)하여 컨트롤에서 테스트 프로젝트에 액세스할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-144">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="b32f7-145">이 섹션에서는 컨트롤을 테스트하고 Windows Form에서 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-145">In this section, you will build your control and test it in a Windows Form.</span></span>

### <a name="to-build-your-control"></a><span data-ttu-id="b32f7-146">컨트롤을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="b32f7-146">To build your control</span></span>

1. <span data-ttu-id="b32f7-147">**빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-147">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="b32f7-148">컴파일러 오류 또는 경고 없이 빌드에 성공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-148">The build should be successful with no compiler errors or warnings.</span></span>

### <a name="to-create-a-test-project"></a><span data-ttu-id="b32f7-149">테스트 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b32f7-149">To create a test project</span></span>

1. <span data-ttu-id="b32f7-150">**파일** 메뉴에서 **추가**를 가리킨 후 **새 프로젝트**를 클릭하여 **새 프로젝트 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-150">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="b32f7-151">Visual Basic 프로젝트 노드를 선택 하 **Windows Forms 응용 프로그램**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-151">Select the Visual Basic projects node, and click **Windows Forms Application**.</span></span>

3. <span data-ttu-id="b32f7-152">**이름** 상자에 `Test`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-152">In the **Name** box, type `Test`.</span></span>

4. <span data-ttu-id="b32f7-153">**솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-153">In **Solution Explorer**, click the **Show All Files** button.</span></span>

5. <span data-ttu-id="b32f7-154">**솔루션 탐색기**에서 테스트 프로젝트에 대한 **참조** 노드를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **참조 추가**를 선택하면 **참조 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-154">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>

6. <span data-ttu-id="b32f7-155">**프로젝트** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-155">Click the **Projects** tab.</span></span>

7. <span data-ttu-id="b32f7-156">**프로젝트**로 레이블이 지정된 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-156">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="b32f7-157">`ValueButtonLib` 프로젝트가 **프로젝트 이름** 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-157">Your `ValueButtonLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="b32f7-158">프로젝트를 두 번 클릭하여 테스트 프로젝트에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-158">Double-click the project to add the reference to the test project.</span></span>

8. <span data-ttu-id="b32f7-159">**솔루션 탐색기**에서 **Test**를 마우스 오른쪽 단추로 클릭한 후 **빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-159">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>

### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="b32f7-160">폼에 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="b32f7-160">To add your control to the form</span></span>

1. <span data-ttu-id="b32f7-161">**솔루션 탐색기**에서 **Form1.vb**를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **뷰 디자이너**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-161">In **Solution Explorer**, right-click **Form1.vb** and choose **View Designer** from the shortcut menu.</span></span>

2. <span data-ttu-id="b32f7-162">**도구 상자**에서 **ValueButtonLib 구성 요소**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-162">In the **Toolbox**, click **ValueButtonLib Components**.</span></span> <span data-ttu-id="b32f7-163">**ValueButton**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-163">Double-click **ValueButton**.</span></span>

     <span data-ttu-id="b32f7-164">**ValueButton**이 폼에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-164">A **ValueButton** appears on the form.</span></span>

3. <span data-ttu-id="b32f7-165">**ValueButton**을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-165">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="b32f7-166">**속성** 창에서 이 컨트롤의 속성을 점검합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-166">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="b32f7-167">`ButtonValue`라는 추가 속성이 있는 것을 제외하고, 표준 단추에 노출된 속성과 동일한 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-167">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, `ButtonValue`.</span></span>

5. <span data-ttu-id="b32f7-168">`ButtonValue` 속성을 `5`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-168">Set the `ButtonValue` property to `5`.</span></span>

6. <span data-ttu-id="b32f7-169">**도구 상자**의 **모두 Windows Forms** 탭에서 <xref:System.Windows.Forms.Label> **레이블** 을 두 번 클릭 하 여 컨트롤을 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-169">On the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>

7. <span data-ttu-id="b32f7-170">폼 가운데에 레이블을 다시 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-170">Relocate the label to the center of the form.</span></span>

8. <span data-ttu-id="b32f7-171">`ValueButton1`을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-171">Double-click `ValueButton1`.</span></span>

     <span data-ttu-id="b32f7-172">**코드 편집기**에 `ValueButton1_Click` 이벤트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-172">The **Code Editor** opens to the `ValueButton1_Click` event.</span></span>

9. <span data-ttu-id="b32f7-173">다음 코드 행을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-173">Type the following line of code.</span></span>

    ```vb
    Label1.Text = CStr(ValueButton1.ButtonValue)
    ```

10. <span data-ttu-id="b32f7-174">**솔루션 탐색기**에서 **Test**를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-174">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>

11. <span data-ttu-id="b32f7-175">**디버그** 메뉴에서 **디버깅 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-175">From the **Debug** menu, select **Start Debugging**.</span></span>

     <span data-ttu-id="b32f7-176">`Form1`이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-176">`Form1` appears.</span></span>

12. <span data-ttu-id="b32f7-177">`Valuebutton1`을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-177">Click `Valuebutton1`.</span></span>

     <span data-ttu-id="b32f7-178">숫자 '5'가 `Label1`에 표시되며 상속된 컨트롤의 `ButtonValue` 속성이 `ValueButton1_Click` 메서드를 통해 `Label1`에 전달되었음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-178">The numeral '5' is displayed in `Label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `Label1` through the `ValueButton1_Click` method.</span></span> <span data-ttu-id="b32f7-179">따라서 `ValueButton` 컨트롤은 표준 Windows Forms 단추의 모든 기능을 상속하지만 추가 사용자 지정 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="b32f7-179">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>

## <a name="see-also"></a><span data-ttu-id="b32f7-180">참고자료</span><span class="sxs-lookup"><span data-stu-id="b32f7-180">See also</span></span>

- [<span data-ttu-id="b32f7-181">연습: Visual Basic를 사용 하 여 복합 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="b32f7-181">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="b32f7-182">방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시</span><span class="sxs-lookup"><span data-stu-id="b32f7-182">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="b32f7-183">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="b32f7-183">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="b32f7-184">상속 기본 사항(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b32f7-184">Inheritance basics (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
