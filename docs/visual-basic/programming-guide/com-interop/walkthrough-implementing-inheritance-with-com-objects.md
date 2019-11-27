---
title: '연습: COM 개체를 사용한 상속 구현'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: 209e1005b9f944bf4883e8406031fb17d4d60df1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347993"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="98e33-102">연습: COM 개체를 사용한 상속 구현(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98e33-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>

<span data-ttu-id="98e33-103">이전 버전의 Visual Basic에서 만든 클래스를 비롯 하 여 COM 개체의 `Public` 클래스에서 Visual Basic 클래스를 파생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="98e33-104">COM 개체에서 상속 된 클래스의 속성 및 메서드는 다른 기본 클래스의 속성 및 메서드를 재정의 하거나 오버 로드 하는 것 처럼 재정의 하거나 오버 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="98e33-105">COM 개체 로부터의 상속은 다시 컴파일하지 않으려는 기존 클래스 라이브러리가 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>

<span data-ttu-id="98e33-106">다음 절차에서는 Visual Basic 6.0를 사용 하 여 클래스가 포함 된 COM 개체를 만든 다음이 개체를 기본 클래스로 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="98e33-107">이 연습에서 사용 되는 COM 개체를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="98e33-107">To build the COM object that is used in this walkthrough</span></span>

1. <span data-ttu-id="98e33-108">Visual Basic 6.0에서 새 ActiveX DLL 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="98e33-109">`Project1` 이라는 프로젝트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-109">A project named `Project1` is created.</span></span> <span data-ttu-id="98e33-110">`Class1`이라는 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-110">It has a class named `Class1`.</span></span>

2. <span data-ttu-id="98e33-111">**프로젝트 탐색기**에서 **Project1**를 마우스 오른쪽 단추로 클릭 한 다음 **Project1 속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="98e33-112">**프로젝트 속성** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-112">The **Project Properties** dialog box is displayed.</span></span>

3. <span data-ttu-id="98e33-113">**프로젝트 속성** 대화 상자의 **일반** 탭에서 **프로젝트 이름** 필드에 `ComObject1`를 입력 하 여 프로젝트 이름을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>

4. <span data-ttu-id="98e33-114">**프로젝트 탐색기**에서 `Class1`을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="98e33-115">클래스에 대 한 **속성** 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-115">The **Properties** window for the class is displayed.</span></span>

5. <span data-ttu-id="98e33-116">`Name` 속성을 `MathFunctions`변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-116">Change the `Name` property to `MathFunctions`.</span></span>

6. <span data-ttu-id="98e33-117">**프로젝트 탐색기**에서 `MathFunctions`을 마우스 오른쪽 단추로 클릭 한 다음 **코드 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="98e33-118">**코드 편집기** 가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-118">The **Code Editor** is displayed.</span></span>

7. <span data-ttu-id="98e33-119">속성 값을 보유할 지역 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-119">Add a local variable to hold the property value:</span></span>

    ```vb
    ' Local variable to hold property value
    Private mvarProp1 As Integer
    ```

8. <span data-ttu-id="98e33-120">속성 `Let` 및 속성 `Get` 속성 프로시저를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-120">Add Property `Let` and Property `Get` property procedures:</span></span>

    ```vb
    Public Property Let Prop1(ByVal vData As Integer)
       'Used when assigning a value to the property.
       mvarProp1 = vData
    End Property
    Public Property Get Prop1() As Integer
       'Used when retrieving a property's value.
       Prop1 = mvarProp1
    End Property
    ```

9. <span data-ttu-id="98e33-121">함수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-121">Add a function:</span></span>

    ```vb
    Function AddNumbers(
       ByVal SomeNumber As Integer,
       ByVal AnotherNumber As Integer) As Integer

       AddNumbers = SomeNumber + AnotherNumber
    End Function
    ```

10. <span data-ttu-id="98e33-122">**파일** 메뉴에서 **ComObject1 만들기** 를 클릭 하 여 COM 개체를 만들고 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98e33-123">Visual Basic를 사용 하 여 만든 클래스를 COM 개체로 노출할 수도 있지만이 클래스는 진정한 COM 개체가 아니므로이 연습에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-123">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="98e33-124">자세한 내용은 참조 하세요 [.NET Framework 애플리케이션의 COM 상호 운용성](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>

## <a name="interop-assemblies"></a><span data-ttu-id="98e33-125">Interop 어셈블리</span><span class="sxs-lookup"><span data-stu-id="98e33-125">Interop Assemblies</span></span>

<span data-ttu-id="98e33-126">다음 절차에서는 비관리 코드 (예: COM 개체)와 Visual Studio가 사용 하는 관리 코드 간의 브리지 역할을 하는 interop 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code Visual Studio uses.</span></span> <span data-ttu-id="98e33-127">Visual Basic 생성 하는 interop 어셈블리는 com 개체와 상호 작용 하는 것과 같은 COM 개체 작업에 대 한 세부 정보 (예: *interop 마샬링*)를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-127">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="98e33-128">Visual Basic 응용 프로그램의 참조는 실제 COM 개체가 아닌 interop 어셈블리를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-128">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>

### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="98e33-129">Visual Basic 2005 이상 버전에서 COM 개체를 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="98e33-129">To use a COM object with Visual Basic 2005 and later versions</span></span>

1. <span data-ttu-id="98e33-130">새 Visual Basic Windows 애플리케이션 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-130">Open a new Visual Basic Windows Application project.</span></span>

2. <span data-ttu-id="98e33-131">**프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-131">On the **Project** menu, click **Add Reference**.</span></span>

     <span data-ttu-id="98e33-132">**참조 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-132">The **Add Reference** dialog box is displayed.</span></span>

3. <span data-ttu-id="98e33-133">**COM** 탭의 **구성 요소 이름** 목록에서 `ComObject1`을 두 번 클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>

4. <span data-ttu-id="98e33-134">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-134">On the **Project** menu, click **Add New Item**.</span></span>

     <span data-ttu-id="98e33-135">**새 항목 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-135">The **Add New Item** dialog box is displayed.</span></span>

5. <span data-ttu-id="98e33-136">**템플릿** 창에서 **클래스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-136">In the **Templates** pane, click **Class**.</span></span>

     <span data-ttu-id="98e33-137">기본 파일 이름 `Class1.vb`이 **이름** 필드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="98e33-138">이 필드를 MathClass로 변경 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="98e33-139">그러면 `MathClass`이라는 클래스가 만들어지고 해당 코드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-139">This creates a class named `MathClass`, and displays its code.</span></span>

6. <span data-ttu-id="98e33-140">`MathClass`의 맨 위에 다음 코드를 추가 하 여 COM 클래스에서 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>

     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]

7. <span data-ttu-id="98e33-141">`MathClass`에 다음 코드를 추가 하 여 기본 클래스의 공용 메서드를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]

8. <span data-ttu-id="98e33-142">`MathClass`에 다음 코드를 추가 하 여 상속 된 클래스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]

<span data-ttu-id="98e33-143">새 클래스는 COM 개체의 기본 클래스 속성을 상속 하 고, 메서드를 오버 로드 하 고, 클래스를 확장 하는 새 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>

### <a name="to-test-the-inherited-class"></a><span data-ttu-id="98e33-144">상속 된 클래스를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="98e33-144">To test the inherited class</span></span>

1. <span data-ttu-id="98e33-145">시작 폼에 단추를 추가 하 고 두 번 클릭 하 여 해당 코드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-145">Add a button to your startup form, and then double-click it to view its code.</span></span>

2. <span data-ttu-id="98e33-146">단추의 `Click` 이벤트 처리기 프로시저에서 `MathClass`의 인스턴스를 만들고 오버 로드 된 메서드를 호출 하는 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>

     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]

3. <span data-ttu-id="98e33-147">F5 키를 눌러 프로젝트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-147">Run the project by pressing F5.</span></span>

<span data-ttu-id="98e33-148">폼의 단추를 클릭 하면 `Short` 데이터 형식 번호를 사용 하 여 `AddNumbers` 메서드를 먼저 호출 하 고 Visual Basic 기본 클래스에서 적절 한 메서드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="98e33-149">`AddNumbers`에 대 한 두 번째 호출은 `MathClass`에서 오버 로드 메서드로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="98e33-150">세 번째 호출은 클래스를 확장 하는 `SubtractNumbers` 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="98e33-151">기본 클래스의 속성이 설정 되 고 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-151">The property in the base class is set, and the value is displayed.</span></span>

## <a name="next-steps"></a><span data-ttu-id="98e33-152">다음 단계</span><span class="sxs-lookup"><span data-stu-id="98e33-152">Next Steps</span></span>

<span data-ttu-id="98e33-153">오버 로드 된 `AddNumbers` 함수가 COM 개체의 기본 클래스에서 상속 된 메서드와 동일한 데이터 형식으로 표시 되는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="98e33-154">이는 Visual Basic 6.0에서 기본 클래스 메서드의 인수와 매개 변수가 16 비트 정수로 정의 되어 있지만 이후 버전의 Visual Basic에서 `Short` 형식의 16 비트 정수로 노출 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="98e33-155">새 함수는 32 비트 정수를 허용 하 고 기본 클래스 함수를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>

<span data-ttu-id="98e33-156">COM 개체를 사용 하는 경우 매개 변수의 크기 및 데이터 형식을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="98e33-157">예를 들어 Visual Basic 6.0 컬렉션 개체를 인수로 허용 하는 COM 개체를 사용 하는 경우 Visual Basic의 이후 버전에서 컬렉션을 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>

<span data-ttu-id="98e33-158">COM 클래스에서 상속 된 속성 및 메서드를 재정의할 수 있습니다. 즉, 기본 COM 클래스에서 상속 된 속성이 나 메서드를 대체 하는 로컬 속성 또는 메서드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="98e33-159">상속 된 COM 속성을 재정의 하는 규칙은 다음과 같은 예외를 제외 하 고 다른 속성 및 메서드를 재정의 하는 규칙과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>

- <span data-ttu-id="98e33-160">COM 클래스에서 상속 된 속성 또는 메서드를 재정의 하는 경우 상속 된 다른 모든 속성과 메서드를 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>

- <span data-ttu-id="98e33-161">`ByRef` 매개 변수를 사용 하는 속성은 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98e33-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>

## <a name="see-also"></a><span data-ttu-id="98e33-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98e33-162">See also</span></span>

- [<span data-ttu-id="98e33-163">.NET Framework 애플리케이션의 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="98e33-163">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="98e33-164">Inherits 문</span><span class="sxs-lookup"><span data-stu-id="98e33-164">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="98e33-165">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="98e33-165">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
