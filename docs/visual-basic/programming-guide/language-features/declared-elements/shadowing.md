---
title: 섀도잉
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
ms.openlocfilehash: 20a33478f622fca6d3183772f53dcb3e72f79409
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266887"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="03800-102">시각적 기본의 그림자</span><span class="sxs-lookup"><span data-stu-id="03800-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="03800-103">두 프로그래밍 요소가 같은 이름을 공유하면 그 중 하나가 숨기거나 다른 하나는 *그림자로*숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="03800-104">이러한 경우 그림자 요소를 참조할 수 없습니다. 대신 코드에서 요소 이름을 사용하는 경우 Visual Basic 컴파일러는 이를 섀도잉 요소로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="03800-105">목적</span><span class="sxs-lookup"><span data-stu-id="03800-105">Purpose</span></span>  
 <span data-ttu-id="03800-106">그림자의 주요 목적은 반원의 정의를 보호하는 것이다.</span><span class="sxs-lookup"><span data-stu-id="03800-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="03800-107">기본 클래스는 이미 정의된 것과 이름이 같은 요소를 만드는 변경작업을 겪을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="03800-108">이 경우 `Shadows` 수정자는 클래스를 통해 참조를 사용하여 새 기본 클래스 요소 대신 정의한 멤버로 해결하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="03800-109">그림자의 종류</span><span class="sxs-lookup"><span data-stu-id="03800-109">Types of Shadowing</span></span>  
 <span data-ttu-id="03800-110">요소는 두 가지 방법으로 다른 요소의 그림자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="03800-111">그림자 요소는 그림자 요소가 포함된 영역의 하위 영역 내에서 선언할 수 있으며, 이 경우 그림자는 *범위를 통해*수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="03800-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="03800-112">또는 파생 클래스는 기본 클래스의 멤버를 재정의할 수 있으며, 이 경우 그림자는 *상속을 통해*수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="03800-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="03800-113">범위를 통해 그림자</span><span class="sxs-lookup"><span data-stu-id="03800-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="03800-114">동일한 모듈, 클래스 또는 구조의 프로그래밍 요소는 이름이 같지만 범위가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="03800-115">이러한 방식으로 두 요소가 선언되고 코드가 공유하는 이름을 참조하면 범위가 좁은 요소가 다른 요소의 그림자를 지정합니다(블록 범위는 가장 좁습니다).</span><span class="sxs-lookup"><span data-stu-id="03800-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="03800-116">예를 들어 모듈은 명명된 `Public` `temp`변수를 정의할 수 있으며 모듈 내의 `temp`프로시저도 명명된 로컬 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="03800-117">프로시저 내에서 참조는 `temp` 로컬 변수에 `temp` 액세스하는 반면 프로시저 외부에서 참조는 변수에 액세스합니다. `Public`</span><span class="sxs-lookup"><span data-stu-id="03800-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="03800-118">이 경우 프로시저 `temp` 변수는 모듈 `temp`변수를 숨김시게 합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="03800-119">다음 그림에서는 두 변수(모두 `temp`명명된 변수)를 보여 주십니다.</span><span class="sxs-lookup"><span data-stu-id="03800-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="03800-120">로컬 변수는 `temp` 자체 프로시저 내에서 액세스할 때 멤버 변수를 `temp` 숨바히게 합니다. `p`</span><span class="sxs-lookup"><span data-stu-id="03800-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="03800-121">그러나 키워드는 `MyClass` 그림자를 우회하고 멤버 변수에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![범위를 통해 그림자를 표시하는 그래픽입니다.](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="03800-123">범위를 통해 그림자의 예는 [참조 방법: 변수와 같은 이름의 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="03800-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="03800-124">상속을 통해 그림자</span><span class="sxs-lookup"><span data-stu-id="03800-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="03800-125">파생 클래스가 기본 클래스에서 상속된 프로그래밍 요소를 재정의하는 경우 재정의 요소는 원래 요소의 그림자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="03800-126">모든 유형의 선언된 요소 또는 오버로드된 요소 집합을 다른 유형과 함께 섀도우할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="03800-127">예를 들어 `Integer` 변수는 프로시저를 숨는 다. `Function`</span><span class="sxs-lookup"><span data-stu-id="03800-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="03800-128">다른 프로시저를 사용하여 프로시저를 섀도우하는 경우 다른 매개 변수 목록과 다른 반환 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="03800-129">다음 그림에서는 기본 `b` 클래스와 `b`에서 `d` 상속하는 파생 클래스를 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="03800-130">기본 클래스는 명명된 `proc`프로시저를 정의하고 파생된 클래스는 동일한 이름의 다른 프로시저로 그 를 숨는다.</span><span class="sxs-lookup"><span data-stu-id="03800-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="03800-131">첫 `Call` 번째 문은 파생 `proc` 클래스의 그림자에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="03800-132">그러나 키워드는 `MyBase` 그림자를 우회하고 기본 클래스의 그림자 프로시저에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![상속을 통한 숨기기 그래픽 다이어그램](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="03800-134">상속을 통해 그림자를 드리는 예제의 경우 [방법: 변수와 동일한 이름의 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) 및 [방법: 상속된 변수 숨기기.](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)</span><span class="sxs-lookup"><span data-stu-id="03800-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="03800-135">그림자 및 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="03800-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="03800-136">파생 된 클래스를 사용 하 여 코드에서 항상 액세스할 수 있는 그림자 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="03800-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="03800-137">예를 들어 선언될 `Private`수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="03800-138">이러한 경우 그림자가 지정되고 컴파일러가 그림자가 없는 경우 와 동일한 요소에 대한 참조를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="03800-139">이 요소는 그림자 클래스에서 뒤로 가장 적은 파생 단계로 액세스할 수 있는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="03800-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="03800-140">그림자 요소가 프로시저인 경우 해상도는 이름이 나, 매개 변수 목록 및 반환 형식이 있는 가장 가까운 액세스 가능한 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="03800-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="03800-141">다음 예제에서는 세 클래스의 상속 계층 구조를 보여 주다.</span><span class="sxs-lookup"><span data-stu-id="03800-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="03800-142">각 클래스는 `Sub` 프로시저를 `display`정의하고 각 파생 `display` 클래스는 해당 기본 클래스의 프로시저를 섀도우합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```vb  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="03800-143">앞의 예제에서 파생된 클래스 `secondClass` 그림자는 `display` `Private` 프로시저를 통해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03800-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="03800-144">모듈에서 `callDisplay` `display` `secondClass`호출할 때 호출 `secondClass` 코드가 외부에 있으므로 `display` 개인 프로시저에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="03800-145">그림자가 숨김이 무산되고 컴파일러가 기본 `display` 클래스 프로시저에 대한 참조를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="03800-146">그러나 파생된 클래스는 `thirdClass` `display` `Public`로 선언하므로 의 `callDisplay` 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="03800-147">그림자 및 재정의</span><span class="sxs-lookup"><span data-stu-id="03800-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="03800-148">그림자를 재정의와 혼동하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="03800-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="03800-149">파생 된 클래스가 기본 클래스에서 상속 될 때 사용 되며 둘 다 다른 선언 된 요소를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="03800-150">그러나 둘 사이에는 상당한 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-150">But there are significant differences between the two.</span></span> <span data-ttu-id="03800-151">비교를 위해 [그림자와 재정의 간의 차이점을](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="03800-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="03800-152">그림자 및 오버로드</span><span class="sxs-lookup"><span data-stu-id="03800-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="03800-153">파생 클래스에서 두 개 이상의 요소로 동일한 기본 클래스 요소를 섀도우하면 그림자 요소가 해당 요소의 오버로드된 버전이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03800-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="03800-154">자세한 내용은 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03800-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="03800-155">그림자 요소에 액세스</span><span class="sxs-lookup"><span data-stu-id="03800-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="03800-156">파생 클래스에서 요소에 액세스하는 경우 일반적으로 `Me` 해당 파생 클래스의 현재 인스턴스를 통해 키워드로 요소 이름을 한정합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="03800-157">파생 클래스가 기본 클래스의 요소를 그림자로 지정하는 경우 `MyBase` 키워드로 한정하여 기본 클래스 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="03800-158">그림자 요소에 액세스하는 예제는 파생 [클래스에 의해 숨겨진 변수에 액세스하는 방법을](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="03800-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="03800-159">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="03800-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="03800-160">개체 변수를 만드는 방법은 파생 된 클래스가 그림자 요소 또는 그림자 요소에 액세스하는지 여부에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03800-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="03800-161">다음 예제에서는 파생 된 클래스에서 두 개의 개체를 만듭니다하지만 한 개체는 기본 클래스로 선언 되 고 다른 개체는 파생 된 클래스로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03800-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```vb  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="03800-162">앞의 예제에서 변수는 `basObj` 기본 클래스로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="03800-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="03800-163">개체에 `dervCls` 개체를 할당하는 것은 확대 변환을 구성하므로 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="03800-164">그러나 기본 클래스는 파생 된 클래스에서 `z` 변수의 그림자 버전에 액세스할 수 `basObj.z` 없으므로 컴파일러는 원래 기본 클래스 값으로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03800-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03800-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03800-165">See also</span></span>

- [<span data-ttu-id="03800-166">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="03800-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="03800-167">Visual Basic의 범위</span><span class="sxs-lookup"><span data-stu-id="03800-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="03800-168">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="03800-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="03800-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="03800-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="03800-170">재정의</span><span class="sxs-lookup"><span data-stu-id="03800-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="03800-171">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="03800-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="03800-172">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="03800-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
