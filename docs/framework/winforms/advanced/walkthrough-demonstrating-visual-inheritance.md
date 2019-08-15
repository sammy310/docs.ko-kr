---
title: '연습: 시각적 상속 데모'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: 6fd504269ae9afbfd02b58276582a644674e1e0f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040316"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="06232-102">연습: 시각적 상속 데모</span><span class="sxs-lookup"><span data-stu-id="06232-102">Walkthrough: Demonstrating Visual Inheritance</span></span>

<span data-ttu-id="06232-103">시각적 상속을 통해 기본 폼의 컨트롤을 보고 새 컨트롤을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06232-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="06232-104">이 연습에서는 기본 폼을 만들고 클래스 라이브러리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="06232-105">이 클래스 라이브러리를 다른 프로젝트로 가져와 기본 폼에서 상속하는 새 양식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06232-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="06232-106">이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="06232-106">During this walkthrough, you will learn how to:</span></span>

- <span data-ttu-id="06232-107">기본 폼을 포함하는 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06232-107">Create a class library project containing a base form.</span></span>

- <span data-ttu-id="06232-108">기본 폼의 파생 클래스가 수정할 수 있는 속성을 가진 단추를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-108">Add a button with properties that derived classes of the base form can modify.</span></span>

- <span data-ttu-id="06232-109">기본 폼의 상속자가 수정할 수 없는 단추를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-109">Add a button that cannot be modified by inheritors of the base form.</span></span>

- <span data-ttu-id="06232-110">`BaseForm`에서 상속하는 폼을 포함하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06232-110">Create a project containing a form that inherits from `BaseForm`.</span></span>

<span data-ttu-id="06232-111">궁극적으로, 이 연습에서는 상속된 폼의 private 컨트롤과 protected 컨트롤 간의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="06232-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>

> [!CAUTION]
> <span data-ttu-id="06232-112">일부 컨트롤은 기본 폼에서의 시각적 상속을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06232-112">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="06232-113">다음 컨트롤은 이 연습에 설명된 시나리오를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06232-113">The following controls do not support the scenario described in this walkthrough:</span></span>
>
>  <xref:System.Windows.Forms.WebBrowser>
>
>  <xref:System.Windows.Forms.ToolStrip>
>
>  <xref:System.Windows.Forms.ToolStripPanel>
>
>  <xref:System.Windows.Forms.TableLayoutPanel>
>
>  <xref:System.Windows.Forms.FlowLayoutPanel>
>
>  <xref:System.Windows.Forms.DataGridView>
>
>  <span data-ttu-id="06232-114">상속된 폼의 이러한 컨트롤은 사용하는 한정자(`private`, `protected` 또는 `public`)에 관계없이 항상 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="06232-114">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>

## <a name="create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="06232-115">기본 폼을 포함 하는 클래스 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="06232-115">Create a class library project containing a base form</span></span>

1. <span data-ttu-id="06232-116">Visual Studio의 **파일** 메뉴에서 **새** > **프로젝트** 를 선택 하 여 **새 프로젝트** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="06232-116">In Visual Studio, from the **File** menu, choose **New** > **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="06232-117">이라는 `BaseFormLibrary`Windows Forms 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06232-117">Create a Windows Forms application named `BaseFormLibrary`.</span></span>

3. <span data-ttu-id="06232-118">표준 Windows Forms 응용 프로그램 대신 클래스 라이브러리를 만들려면 **솔루션 탐색기**에서 **baseformlibrary** 프로젝트 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-118">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>

4. <span data-ttu-id="06232-119">프로젝트에 대 한 속성에서 **출력 형식을** **Windows 응용 프로그램** 에서 **클래스 라이브러리로**변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-119">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>

5. <span data-ttu-id="06232-120">**파일** 메뉴에서 **모두 저장** 을 선택 하 여 프로젝트 및 파일을 기본 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-120">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>

 <span data-ttu-id="06232-121">다음 두 절차에서는 기본 폼에 단추를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-121">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="06232-122">시각적 상속을 보여 주기 위해 단추의 `Modifiers` 속성을 설정하여 단추에 다양한 액세스 수준을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-122">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>

## <a name="add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="06232-123">기본 폼의 상속 자가 수정할 수 있는 단추를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-123">Add a button that inheritors of the base form can modify</span></span>

1. <span data-ttu-id="06232-124">디자이너에서 **Form1**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="06232-124">Open **Form1** in the designer.</span></span>

2. <span data-ttu-id="06232-125">**도구 상자**의 **모두 Windows Forms** 탭에서 **단추** 를 두 번 클릭 하 여 단추를 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-125">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="06232-126">마우스를 사용하여 단추를 배치하고 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-126">Use the mouse to position and resize the button.</span></span>

3. <span data-ttu-id="06232-127">속성 창에서 단추의 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-127">In the Properties window, set the following properties of the button:</span></span>

    - <span data-ttu-id="06232-128">**텍스트** 속성을 **Hello**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-128">Set the **Text** property to **Say Hello**.</span></span>

    - <span data-ttu-id="06232-129">**(Name)** 속성을 **btnProtected**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-129">Set the **(Name)** property to **btnProtected**.</span></span>

    - <span data-ttu-id="06232-130">**한정자** 속성을 **Protected**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-130">Set the **Modifiers** property to **Protected**.</span></span> <span data-ttu-id="06232-131">이렇게 하면 **Form1** 에서 상속 하는 폼이 **btnProtected**의 속성을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06232-131">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>

4. <span data-ttu-id="06232-132">**Hello** 단추를 두 번 클릭 하 여 **click** 이벤트에 대 한 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-132">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>

5. <span data-ttu-id="06232-133">다음 코드 줄을 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-133">Add the following line of code to the event handler:</span></span>

    ```vb
    MessageBox.Show("Hello, World!")
    ```

    ```csharp
    MessageBox.Show("Hello, World!");
    ```

## <a name="add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="06232-134">기본 폼의 상속 자가 수정할 수 없는 단추를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-134">Add a button that cannot be modified by inheritors of the base form</span></span>

1. <span data-ttu-id="06232-135">코드 편집기 위쪽의 form1.vb [ **design], Form1.cs [design] 또는 [design]** 탭을 클릭 하거나 F7 키를 눌러 디자인 뷰로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-135">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>

2. <span data-ttu-id="06232-136">두 번째 단추를 추가하고 해당 속성을 다음과 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-136">Add a second button and set its properties as follows:</span></span>

    - <span data-ttu-id="06232-137">**텍스트** 속성을 **안녕히**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-137">Set the **Text** property to **Say Goodbye**.</span></span>

    - <span data-ttu-id="06232-138">**(Name)** 속성을 **btnPrivate**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-138">Set the **(Name)** property to **btnPrivate**.</span></span>

    - <span data-ttu-id="06232-139">**한정자** 속성을 **Private**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-139">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="06232-140">이렇게 하면 **Form1** 에서 상속 하는 폼이 **btnPrivate**의 속성을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06232-140">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>

3. <span data-ttu-id="06232-141">예 단추를 두 번 클릭 하 여 **click** 이벤트에 대 한 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-141">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="06232-142">다음 코드 줄을 이벤트 프로시저에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-142">Place the following line of code in the event procedure:</span></span>

    ```vb
    MessageBox.Show("Goodbye!")
    ```

    ```csharp
    MessageBox.Show("Goodbye!");
    ```

4. <span data-ttu-id="06232-143">**빌드** 메뉴에서 **BaseForm library 빌드** 를 선택 하 여 클래스 라이브러리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-143">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>

     <span data-ttu-id="06232-144">라이브러리가 빌드되고 나면 방금 만든 폼에서 상속하는 새 프로젝트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06232-144">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>

## <a name="create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="06232-145">기본 폼에서 상속 되는 폼을 포함 하는 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="06232-145">Create a project containing a form that inherits from the base form</span></span>

1. <span data-ttu-id="06232-146">**파일** 메뉴에서 **추가** 를 선택 하 고 **새 프로젝트** 를 선택 하 여 **새 프로젝트 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="06232-146">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="06232-147">이라는 `InheritanceTest`Windows Forms 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06232-147">Create a Windows Forms application named `InheritanceTest`.</span></span>

## <a name="add-an-inherited-form"></a><span data-ttu-id="06232-148">상속 된 폼 추가</span><span class="sxs-lookup"><span data-stu-id="06232-148">Add an inherited form</span></span>

1. <span data-ttu-id="06232-149">**솔루션 탐색기**에서 **InheritanceTest** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가**를 선택한 다음 **새 항목**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-149">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select **New Item**.</span></span>

2. <span data-ttu-id="06232-150">**새 항목 추가** 대화 상자에서 범주 목록이 있는 경우 **Windows Forms** 범주를 선택 하 고 **상속 된 양식** 서식 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-150">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>

3. <span data-ttu-id="06232-151">의 `Form2` 기본 이름을 그대로 두고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-151">Leave the default name of `Form2` and then click **Add**.</span></span>

4. <span data-ttu-id="06232-152">**상속 선택** 대화 상자의 **baseformlibrary** 프로젝트에서 상속할 폼으로 **Form1** 을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-152">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>

     <span data-ttu-id="06232-153">그러면 **Baseformlibrary**의 폼에서 파생 되는 **InheritanceTest** 프로젝트에 폼이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="06232-153">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>

5. <span data-ttu-id="06232-154">디자이너에서 상속 된 폼 (**Form2**)을 두 번 클릭 하 여 엽니다 (아직 열려 있지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="06232-154">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>

     <span data-ttu-id="06232-155">디자이너에서 상속 된 단추에는 기호 (</span><span class="sxs-lookup"><span data-stu-id="06232-155">In the designer, the inherited buttons have a symbol (</span></span>![Visual Basic 상속 기호의 스크린샷](./media/walkthrough-demonstrating-visual-inheritance/visual-basic-inheritance-glyph.gif)<span data-ttu-id="06232-157">)를 위쪽 모퉁이에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-157">) in their upper corner, indicating they are inherited.</span></span>

6. <span data-ttu-id="06232-158">**Hello** 단추를 선택 하 고 크기 조정 핸들을 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-158">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="06232-159">이 단추는 protected이므로 상속자가 이동하고, 크기를 조정하고, 캡션을 변경하고, 기타 수정 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06232-159">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>

7. <span data-ttu-id="06232-160">비공개 **라고** 하는 단추를 선택 하 고 크기 조정 핸들이 없다는 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-160">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="06232-161">또한 **속성** 창에서이 단추의 속성은 수정할 수 없음을 나타내기 위해 회색으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06232-161">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>

8. <span data-ttu-id="06232-162">시각적 개체 C#를 사용 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="06232-162">If you are using Visual C#:</span></span>

    1. <span data-ttu-id="06232-163">**솔루션 탐색기**에서 **InheritanceTest** 프로젝트의 **Form1** 을 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-163">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="06232-164">표시 되는 메시지 상자에서 **확인** 을 클릭 하 여 삭제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-164">In the message box that appears, click **OK** to confirm the deletion.</span></span>

    2. <span data-ttu-id="06232-165">Program.cs 파일을 열고 `Application.Run(new Form1());` 줄을 `Application.Run(new Form2());`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-165">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>

9. <span data-ttu-id="06232-166">**솔루션 탐색기**에서 **InheritanceTest** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-166">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>

10. <span data-ttu-id="06232-167">**솔루션 탐색기**에서 **InheritanceTest** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-167">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>

11. <span data-ttu-id="06232-168">**InheritanceTest** 속성 페이지에서 **시작 개체** 를 상속 된 폼 (**Form2**)으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-168">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>

12. <span data-ttu-id="06232-169">**F5** 키를 눌러 응용 프로그램을 실행 하 고 상속 된 폼의 동작을 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-169">Press **F5** to run the application, and observe the behavior of the inherited form.</span></span>

## <a name="next-steps"></a><span data-ttu-id="06232-170">다음 단계</span><span class="sxs-lookup"><span data-stu-id="06232-170">Next steps</span></span>

<span data-ttu-id="06232-171">사용자 정의 컨트롤의 상속도 거의 동일한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-171">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="06232-172">새 클래스 라이브러리 프로젝트를 열고 사용자 정의 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-172">Open a new class library project and add a user control.</span></span> <span data-ttu-id="06232-173">구성 요소 컨트롤을 배치하고 프로젝트를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-173">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="06232-174">다른 새 클래스 라이브러리 프로젝트를 열고 컴파일된 클래스 라이브러리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-174">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="06232-175">또한 상속 **선택기**를 사용 하 여 **새 항목 추가** 대화 상자를 통해 상속 된 컨트롤을 프로젝트에 추가 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="06232-175">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="06232-176">사용자 정의 컨트롤을 추가 하 고 `Inherits` (`:` Visual C#) 문을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-176">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="06232-177">자세한 내용은 [방법: Windows Forms](how-to-inherit-windows-forms.md)를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="06232-177">For more information, see [How to: Inherit Windows Forms](how-to-inherit-windows-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="06232-178">참고자료</span><span class="sxs-lookup"><span data-stu-id="06232-178">See also</span></span>

- [<span data-ttu-id="06232-179">방법: Windows Forms 상속</span><span class="sxs-lookup"><span data-stu-id="06232-179">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="06232-180">Windows Forms 시각적 개체 상속</span><span class="sxs-lookup"><span data-stu-id="06232-180">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="06232-181">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06232-181">Windows Forms</span></span>](../index.md)
