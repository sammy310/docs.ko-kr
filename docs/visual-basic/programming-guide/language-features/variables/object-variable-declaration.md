---
title: 개체 변수 선언
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
ms.openlocfilehash: d1964e3768124dde1deeabfada9006ff5a59def0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351811"
---
# <a name="object-variable-declaration-visual-basic"></a><span data-ttu-id="2dd06-102">개체 변수 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2dd06-102">Object Variable Declaration (Visual Basic)</span></span>
<span data-ttu-id="2dd06-103">일반 선언문을 사용 하 여 개체 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-103">You use a normal declaration statement to declare an object variable.</span></span> <span data-ttu-id="2dd06-104">데이터 형식에 대해 `Object` (즉, [개체 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)) 또는 개체를 만들 보다 구체적인 클래스 중 하나를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-104">For the data type, you specify either `Object` (that is, the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) or a more specific class from which the object is to be created.</span></span>  
  
 <span data-ttu-id="2dd06-105">변수를 `Object` 선언 하는 것은 <xref:System.Object?displayProperty=nameWithType>으로 선언 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-105">Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2dd06-106">특정 개체 클래스를 사용 하 여 변수를 선언 하는 경우 해당 클래스와 해당 클래스가 상속 하는 클래스에 의해 노출 된 모든 메서드와 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-106">When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class and the classes from which it inherits.</span></span> <span data-ttu-id="2dd06-107"><xref:System.Object>를 사용 하 여 변수를 선언 하는 경우 런타임에 바인딩을 허용 하도록 `Option Strict Off`를 설정 하지 않으면 <xref:System.Object> 클래스의 멤버에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-107">If you declare the variable with <xref:System.Object>, it can access only the members of the <xref:System.Object> class, unless you turn `Option Strict Off` to allow late binding.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="2dd06-108">선언 구문</span><span class="sxs-lookup"><span data-stu-id="2dd06-108">Declaration Syntax</span></span>  
 <span data-ttu-id="2dd06-109">다음 구문을 사용 하 여 개체 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-109">Use the following syntax to declare an object variable:</span></span>  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 <span data-ttu-id="2dd06-110">선언에 [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)또는 [Static](../../../../visual-basic/language-reference/modifiers/static.md) 을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-110">You can also specify [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), or [Static](../../../../visual-basic/language-reference/modifiers/static.md) in the declaration.</span></span> <span data-ttu-id="2dd06-111">다음은 유효한 예제 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-111">The following example declarations are valid:</span></span>  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a><span data-ttu-id="2dd06-112">런타임에 바인딩 및 초기 바인딩</span><span class="sxs-lookup"><span data-stu-id="2dd06-112">Late Binding and Early Binding</span></span>  
 <span data-ttu-id="2dd06-113">코드를 실행할 때까지 특정 클래스를 알 수 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-113">Sometimes the specific class is unknown until your code runs.</span></span> <span data-ttu-id="2dd06-114">이 경우 `Object` 데이터 형식을 사용 하 여 개체 변수를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-114">In this case, you must declare the object variable with the `Object` data type.</span></span> <span data-ttu-id="2dd06-115">이렇게 하면 모든 개체 형식에 대 한 일반 참조가 만들어지고 런타임에 특정 클래스가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-115">This creates a general reference to any type of object, and the specific class is assigned at run time.</span></span> <span data-ttu-id="2dd06-116">이를 *후기 바인딩*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-116">This is called *late binding*.</span></span> <span data-ttu-id="2dd06-117">런타임에 바인딩에는 추가 실행 시간이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-117">Late binding requires additional execution time.</span></span> <span data-ttu-id="2dd06-118">또한 가장 최근에 할당 된 클래스의 메서드 및 속성으로 코드를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-118">It also limits your code to the methods and properties of the class you have most recently assigned to it.</span></span> <span data-ttu-id="2dd06-119">코드에서 다른 클래스의 멤버에 액세스 하려고 하면 런타임 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-119">This can cause run-time errors if your code attempts to access members of a different class.</span></span>  
  
 <span data-ttu-id="2dd06-120">컴파일 타임에 특정 클래스를 알고 있으면 개체 변수를 해당 클래스로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-120">When you know the specific class at compile time, you should declare the object variable to be of that class.</span></span> <span data-ttu-id="2dd06-121">이것을 *초기 바인딩*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-121">This is called *early binding*.</span></span> <span data-ttu-id="2dd06-122">초기 바인딩은 성능을 향상 시키고 코드에서 특정 클래스의 모든 메서드와 속성에 액세스할 수 있도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-122">Early binding improves performance and guarantees your code access to all the methods and properties of the specific class.</span></span> <span data-ttu-id="2dd06-123">위의 예제 선언에서 변수 `objA` <xref:System.Windows.Forms.Label?displayProperty=nameWithType>클래스의 개체만 사용 하는 경우 해당 선언에서 `As System.Windows.Forms.Label`를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-123">In the preceding example declarations, if variable `objA` uses only objects of class <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, you should specify `As System.Windows.Forms.Label` in its declaration.</span></span>  
  
### <a name="advantages-of-early-binding"></a><span data-ttu-id="2dd06-124">초기 바인딩의 장점</span><span class="sxs-lookup"><span data-stu-id="2dd06-124">Advantages of Early Binding</span></span>  
 <span data-ttu-id="2dd06-125">개체 변수를 특정 클래스로 선언 하면 다음과 같은 여러 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-125">Declaring an object variable as a specific class gives you several advantages:</span></span>  
  
- <span data-ttu-id="2dd06-126">자동 형식 검사</span><span class="sxs-lookup"><span data-stu-id="2dd06-126">Automatic type checking</span></span>  
  
- <span data-ttu-id="2dd06-127">특정 클래스의 모든 멤버에 대 한 액세스 보장</span><span class="sxs-lookup"><span data-stu-id="2dd06-127">Guaranteed access to all members of the specific class</span></span>  
  
- <span data-ttu-id="2dd06-128">코드 편집기의 Microsoft IntelliSense 지원</span><span class="sxs-lookup"><span data-stu-id="2dd06-128">Microsoft IntelliSense support in the Code Editor</span></span>  
  
- <span data-ttu-id="2dd06-129">코드 가독성 향상</span><span class="sxs-lookup"><span data-stu-id="2dd06-129">Improved readability of your code</span></span>  
  
- <span data-ttu-id="2dd06-130">코드의 오류 감소</span><span class="sxs-lookup"><span data-stu-id="2dd06-130">Fewer errors in your code</span></span>  
  
- <span data-ttu-id="2dd06-131">런타임 대신 컴파일 시간에 발생 한 오류</span><span class="sxs-lookup"><span data-stu-id="2dd06-131">Errors caught at compile time rather than run time</span></span>  
  
- <span data-ttu-id="2dd06-132">빠른 코드 실행</span><span class="sxs-lookup"><span data-stu-id="2dd06-132">Faster code execution</span></span>  
  
## <a name="access-to-object-variable-members"></a><span data-ttu-id="2dd06-133">개체 변수 멤버에 대 한 액세스</span><span class="sxs-lookup"><span data-stu-id="2dd06-133">Access to Object Variable Members</span></span>  
 <span data-ttu-id="2dd06-134">`Option Strict` `On`설정 된 경우 개체 변수는 선언 된 클래스의 메서드와 속성에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-134">When `Option Strict` is turned `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="2dd06-135">다음 예제에서는 이것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-135">The following example illustrates this.</span></span>  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 <span data-ttu-id="2dd06-136">이 예제에서 `p` 는 <xref:System.Object> 클래스 자체의 멤버만 사용할 수 있으므로 `Left` 속성을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-136">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="2dd06-137">반면, `q` 형식으로 선언된 <xref:System.Windows.Forms.Label>는 <xref:System.Windows.Forms.Label> 네임스페이스에 있는 <xref:System.Windows.Forms> 클래스의 모든 메서드와 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-137">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="flexibility-of-object-variables"></a><span data-ttu-id="2dd06-138">개체 변수의 유연성</span><span class="sxs-lookup"><span data-stu-id="2dd06-138">Flexibility of Object Variables</span></span>  
 <span data-ttu-id="2dd06-139">상속 계층 구조에서 개체를 작업할 때 개체 변수를 선언 하는 데 사용할 클래스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-139">When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables.</span></span> <span data-ttu-id="2dd06-140">이 옵션을 선택 하는 경우 클래스 멤버에 대 한 액세스에 대해 개체 할당의 유연성을 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-140">In making this choice, you must balance flexibility of object assignment against access to members of a class.</span></span> <span data-ttu-id="2dd06-141">예를 들어 <xref:System.Windows.Forms.Form?displayProperty=nameWithType> 클래스로 이어지는 상속 계층 구조를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-141">For example, consider the inheritance hierarchy that leads to the <xref:System.Windows.Forms.Form?displayProperty=nameWithType> class:</span></span>  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 <span data-ttu-id="2dd06-142">응용 프로그램이 <xref:System.Windows.Forms.Form>클래스에서 상속 되는 `specialForm`이라는 폼 클래스를 정의 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-142">Suppose your application defines a form class called `specialForm`, which inherits from class <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="2dd06-143">다음 예제와 같이 `specialForm`에 대해 구체적으로 참조 하는 개체 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-143">You can declare an object variable that refers specifically to `specialForm`, as the following example shows.</span></span>  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 <span data-ttu-id="2dd06-144">위의 예제에서 선언은 변수 `nextForm` `specialForm`클래스의 개체로 제한 하지만 `specialForm`가 상속 하는 모든 클래스의 모든 멤버 뿐만 아니라 `specialForm`의 모든 메서드 및 속성을 `nextForm`에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-144">The declaration in the preceding example limits the variable `nextForm` to objects of class `specialForm`, but it also makes all the methods and properties of `specialForm` available to `nextForm`, as well as all the members of all the classes from which `specialForm` inherits.</span></span>  
  
 <span data-ttu-id="2dd06-145">다음 예제와 같이 개체 변수를 <xref:System.Windows.Forms.Form>형식으로 선언 하 여 보다 일반적인 개체 변수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-145">You can make an object variable more general by declaring it to be of type <xref:System.Windows.Forms.Form>, as the following example shows.</span></span>  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="2dd06-146">위의 예제에서 선언을 사용 하면 응용 프로그램의 모든 폼을 `anyForm`에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-146">The declaration in the preceding example lets you assign any form in your application to `anyForm`.</span></span> <span data-ttu-id="2dd06-147">그러나 `anyForm` <xref:System.Windows.Forms.Form>클래스의 모든 멤버에 액세스할 수 있지만 `specialForm`와 같은 특정 양식에 대해 정의 된 추가 메서드 또는 속성은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-147">However, although `anyForm` can access all the members of class <xref:System.Windows.Forms.Form>, it cannot use any of the additional methods or properties defined for specific forms such as `specialForm`.</span></span>  
  
 <span data-ttu-id="2dd06-148">기본 클래스의 모든 멤버를 파생 클래스에서 사용할 수 있지만 기본 클래스에서 파생 클래스의 추가 멤버를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd06-148">All the members of a base class are available to derived classes, but the additional members of a derived class are unavailable to the base class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd06-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2dd06-149">See also</span></span>

- [<span data-ttu-id="2dd06-150">개체 변수</span><span class="sxs-lookup"><span data-stu-id="2dd06-150">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="2dd06-151">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="2dd06-151">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="2dd06-152">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="2dd06-152">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="2dd06-153">방법: 개체 변수를 선언 하 고 개체를에 할당 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2dd06-153">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="2dd06-154">방법: 개체의 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="2dd06-154">How to: Access Members of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [<span data-ttu-id="2dd06-155">New 연산자</span><span class="sxs-lookup"><span data-stu-id="2dd06-155">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="2dd06-156">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="2dd06-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="2dd06-157">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="2dd06-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
