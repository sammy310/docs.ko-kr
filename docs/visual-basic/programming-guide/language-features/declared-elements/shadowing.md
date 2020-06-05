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
ms.openlocfilehash: 7d76e2e7398c2f954ff4274f77ffa350efbd3617
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410749"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="0dcf8-102">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="0dcf8-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="0dcf8-103">두 프로그래밍 요소가 동일한 이름을 공유 하는 경우 그 중 하나는 다른 *요소를 숨기 거 나 숨길*수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="0dcf8-104">이러한 경우에는 숨겨진 요소를 참조할 수 없습니다. 대신, 코드에서 요소 이름을 사용 하는 경우 Visual Basic 컴파일러에서 해당 요소 이름을 숨기는 요소로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="0dcf8-105">용도</span><span class="sxs-lookup"><span data-stu-id="0dcf8-105">Purpose</span></span>  
 <span data-ttu-id="0dcf8-106">숨김의 주요 목적은 클래스 멤버의 정의를 보호 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="0dcf8-107">기본 클래스는 이미 정의한 것과 동일한 이름으로 요소를 만드는 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="0dcf8-108">이 경우 `Shadows` 한정자는 클래스를 통해 참조가 새 기본 클래스 요소가 아닌 사용자가 정의한 멤버로 확인 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="0dcf8-109">섀도잉 유형</span><span class="sxs-lookup"><span data-stu-id="0dcf8-109">Types of Shadowing</span></span>  
 <span data-ttu-id="0dcf8-110">요소는 서로 다른 두 가지 방법으로 다른 요소를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="0dcf8-111">섀도잉 요소는 숨겨진 요소를 포함 하는 영역의 하위 영역 내에서 선언할 수 있으며,이 경우 *범위를 통해*숨김은 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="0dcf8-112">또는 파생 클래스에서 기본 클래스의 멤버를 다시 정의할 수 있습니다 .이 경우에는 *상속이 상속을 통해*수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="0dcf8-113">범위를 통한 숨김</span><span class="sxs-lookup"><span data-stu-id="0dcf8-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="0dcf8-114">동일한 모듈, 클래스 또는 구조체의 프로그래밍 요소가 같은 이름을 갖지만 범위를 다르게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="0dcf8-115">두 요소가 이러한 방식으로 선언 되 고 코드가 공유 하는 이름을 참조 하는 경우 범위가 좁은 요소가 다른 요소 (블록 범위는 가장 좁은)를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="0dcf8-116">예를 들어 모듈은 `Public` 라는 변수를 정의할 수 `temp` 있으며 모듈 내의 프로시저는 라는 지역 변수를 선언할 수 있습니다 `temp` .</span><span class="sxs-lookup"><span data-stu-id="0dcf8-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="0dcf8-117">`temp`프로시저 외부에서에 대 한 참조는 변수에 액세스 하는 반면 프로시저 내에서에 대 한 참조는 지역 변수에 액세스 `temp` `Public` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="0dcf8-118">이 경우 프로시저 변수는 `temp` 모듈 변수를 숨깁니다 `temp` .</span><span class="sxs-lookup"><span data-stu-id="0dcf8-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="0dcf8-119">다음 그림에서는 라는 두 개의 변수를 보여 줍니다 `temp` .</span><span class="sxs-lookup"><span data-stu-id="0dcf8-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="0dcf8-120">지역 변수는 `temp` `temp` 자체 프로시저 내에서 액세스할 때 멤버 변수를 숨깁니다 `p` .</span><span class="sxs-lookup"><span data-stu-id="0dcf8-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="0dcf8-121">그러나 키워드는 `MyClass` 숨김을 무시 하 고 멤버 변수에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![범위를 통해 숨김을 보여 주는 그래픽입니다.](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="0dcf8-123">범위를 통한 섀도잉 예제는 [방법: 변수와 이름이 같은 변수 숨기기](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="0dcf8-124">상속을 통한 숨김</span><span class="sxs-lookup"><span data-stu-id="0dcf8-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="0dcf8-125">파생 클래스가 기본 클래스에서 상속 된 프로그래밍 요소를 다시 정의 하는 경우 다시 정의 하는 요소는 원래 요소를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="0dcf8-126">모든 형식의 선언 된 요소 또는 오버 로드 된 요소 집합을 다른 형식으로 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="0dcf8-127">예를 들어 `Integer` 변수는 프로시저를 숨길 수 있습니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="0dcf8-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="0dcf8-128">다른 프로시저를 사용 하 여 프로시저를 숨기는 경우 다른 매개 변수 목록과 다른 반환 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="0dcf8-129">다음 그림은 `b` `d` 에서 상속 되는 기본 클래스 및 파생 클래스를 보여 줍니다 `b` .</span><span class="sxs-lookup"><span data-stu-id="0dcf8-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="0dcf8-130">기본 클래스는 이라는 프로시저를 정의 `proc` 하 고 파생 클래스는 이름이 같은 다른 프로시저를 사용 하 여 해당 프로시저를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="0dcf8-131">첫 번째 `Call` 문은 파생 클래스의 숨김에 액세스 합니다 `proc` .</span><span class="sxs-lookup"><span data-stu-id="0dcf8-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="0dcf8-132">그러나 키워드는 `MyBase` 숨김을 무시 하 고 기본 클래스의 숨겨진 프로시저에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![상속을 통한 숨기기 그래픽 다이어그램](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="0dcf8-134">상속을 통한 숨김 예제는 [방법: 변수와 이름이 같은 변수 숨기기](how-to-hide-a-variable-with-the-same-name-as-your-variable.md) 및 [방법: 상속 된 변수 숨기기](how-to-hide-an-inherited-variable.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="0dcf8-135">숨김 및 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="0dcf8-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="0dcf8-136">숨김 요소는 파생 클래스를 사용 하 여 코드에서 항상 액세스할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="0dcf8-137">예를 들어, 선언할 수 있습니다 `Private` .</span><span class="sxs-lookup"><span data-stu-id="0dcf8-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="0dcf8-138">이러한 경우에는 숨김은 발생 하지 않으며, 숨김이 없는 경우 컴파일러는 동일한 요소에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="0dcf8-139">이 요소는 숨기는 클래스에서 뒤로 derivational 가장 적은 수의 액세스 가능한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="0dcf8-140">숨겨진 요소가 프로시저인 경우 동일한 이름, 매개 변수 목록 및 반환 형식을 사용 하 여 가장 가까운 액세스 가능한 버전으로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="0dcf8-141">다음 예제에서는 세 클래스의 상속 계층 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="0dcf8-142">각 클래스는 `Sub` 프로시저 `display` 를 정의 하 고, 각 파생 클래스는 `display` 기본 클래스의 프로시저를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
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
  
 <span data-ttu-id="0dcf8-143">위의 예제에서 파생 클래스는 프로시저를 `secondClass` `display` 사용 하 여 숨겨집니다 `Private` .</span><span class="sxs-lookup"><span data-stu-id="0dcf8-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="0dcf8-144">에서 모듈이 호출 되 면 호출 하는 `callDisplay` `display` `secondClass` 코드가 외부에 `secondClass` 있으므로 private 프로시저에 액세스할 수 없습니다 `display` .</span><span class="sxs-lookup"><span data-stu-id="0dcf8-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="0dcf8-145">숨김은 무효화 되 고 컴파일러는 기본 클래스 프로시저에 대 한 참조를 확인 합니다 `display` .</span><span class="sxs-lookup"><span data-stu-id="0dcf8-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="0dcf8-146">그러나 추가 파생 클래스는 `thirdClass` `display` 를로 선언 `Public` 하므로의 코드에서 `callDisplay` 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="0dcf8-147">숨김 및 재정의</span><span class="sxs-lookup"><span data-stu-id="0dcf8-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="0dcf8-148">숨김과 재정의를 혼동 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="0dcf8-149">파생 클래스가 기본 클래스에서 상속 하는 경우와 선언 된 요소를 다른 요소와 모두 재정의 하는 경우 둘 다 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="0dcf8-150">하지만 둘 사이에는 상당한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-150">But there are significant differences between the two.</span></span> <span data-ttu-id="0dcf8-151">비교는 [숨김과 재정의 간의 차이점](differences-between-shadowing-and-overriding.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-151">For a comparison, see [Differences Between Shadowing and Overriding](differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="0dcf8-152">숨김 및 오버 로드</span><span class="sxs-lookup"><span data-stu-id="0dcf8-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="0dcf8-153">파생 클래스에서 둘 이상의 요소를 사용 하 여 동일한 기본 클래스 요소를 숨기는 경우에는 숨기는 요소가 해당 요소의 오버 로드 된 버전이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="0dcf8-154">자세한 내용은 [Procedure Overloading](../procedures/procedure-overloading.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-154">For more information, see [Procedure Overloading](../procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="0dcf8-155">숨겨진 요소에 액세스</span><span class="sxs-lookup"><span data-stu-id="0dcf8-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="0dcf8-156">파생 클래스에서 요소에 액세스 하는 경우 일반적으로 키워드를 사용 하 여 요소 이름을 정규화 함으로써 파생 클래스의 현재 인스턴스를 통해이 작업을 수행 `Me` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="0dcf8-157">파생 클래스가 기본 클래스의 요소를 숨기는 경우 키워드를 사용 하 여 기본 클래스 요소를 한정 하 여 해당 요소에 액세스할 수 있습니다 `MyBase` .</span><span class="sxs-lookup"><span data-stu-id="0dcf8-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="0dcf8-158">숨겨진 요소에 액세스 하는 예제는 [방법: 파생 클래스에 의해 숨겨진 변수에 액세스](how-to-access-a-variable-hidden-by-a-derived-class.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="0dcf8-159">개체 변수의 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="0dcf8-160">개체 변수를 만드는 방법은 파생 클래스가 숨기는 요소 또는 숨겨진 요소에 액세스 하는지 여부에도 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="0dcf8-161">다음 예제에서는 파생 된 클래스에서 두 개의 개체를 만들지만 한 개체가 기본 클래스로 선언 되 고 다른 개체가 파생 클래스로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
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
  
 <span data-ttu-id="0dcf8-162">앞의 예제에서 변수는 `basObj` 기본 클래스로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="0dcf8-163">개체를 할당 `dervCls` 하는 것은 확대 변환을 구성 하므로 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="0dcf8-164">그러나 기본 클래스는 파생 클래스에 있는 변수의 숨김 버전에 액세스할 수 없으므로 `z` 컴파일러가 `basObj.z` 원래 기본 클래스 값으로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dcf8-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dcf8-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0dcf8-165">See also</span></span>

- [<span data-ttu-id="0dcf8-166">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="0dcf8-166">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="0dcf8-167">Visual Basic의 범위</span><span class="sxs-lookup"><span data-stu-id="0dcf8-167">Scope in Visual Basic</span></span>](scope.md)
- [<span data-ttu-id="0dcf8-168">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="0dcf8-168">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="0dcf8-169">Overloads</span><span class="sxs-lookup"><span data-stu-id="0dcf8-169">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
- [<span data-ttu-id="0dcf8-170">재정의</span><span class="sxs-lookup"><span data-stu-id="0dcf8-170">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
- [<span data-ttu-id="0dcf8-171">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="0dcf8-171">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="0dcf8-172">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="0dcf8-172">Inheritance Basics</span></span>](../objects-and-classes/inheritance-basics.md)
