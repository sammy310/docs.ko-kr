---
title: 개체 변수 선언(Visual Basic)
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
ms.openlocfilehash: 4a3ef3a8254153fa8695ffacd9829ca9316d77a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959980"
---
# <a name="object-variable-declaration-visual-basic"></a><span data-ttu-id="5816e-102">개체 변수 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5816e-102">Object Variable Declaration (Visual Basic)</span></span>
<span data-ttu-id="5816e-103">개체 변수를 선언 하는 일반적인 선언문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-103">You use a normal declaration statement to declare an object variable.</span></span> <span data-ttu-id="5816e-104">지정 데이터 형식에 대 한 `Object` (즉, 합니다 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) 또는 보다 구체적인 클래스는 개체를 만들려는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-104">For the data type, you specify either `Object` (that is, the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) or a more specific class from which the object is to be created.</span></span>  
  
 <span data-ttu-id="5816e-105">변수를 선언 `Object` 으로 선언 하는 것과 같습니다 <xref:System.Object?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-105">Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="5816e-106">특정 개체 클래스를 사용 하 여 변수를 선언 하면 모든 메서드 및 해당 클래스와 상속 된 클래스에 의해 노출 되는 속성 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-106">When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class and the classes from which it inherits.</span></span> <span data-ttu-id="5816e-107">사용 하 여 변수를 선언 하는 경우 <xref:System.Object>의 구성원만 액세스할 수 있습니다 합니다 <xref:System.Object> 클래스를 설정 하지 않으면 `Option Strict Off` 런타임에 바인딩을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-107">If you declare the variable with <xref:System.Object>, it can access only the members of the <xref:System.Object> class, unless you turn `Option Strict Off` to allow late binding.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="5816e-108">선언 구문</span><span class="sxs-lookup"><span data-stu-id="5816e-108">Declaration Syntax</span></span>  
 <span data-ttu-id="5816e-109">개체 변수 선언 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-109">Use the following syntax to declare an object variable:</span></span>  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 <span data-ttu-id="5816e-110">지정할 수도 있습니다 [공용](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`를 [개인](../../../../visual-basic/language-reference/modifiers/private.md), [공유](../../../../visual-basic/language-reference/modifiers/shared.md), 또는 [정적](../../../../visual-basic/language-reference/modifiers/static.md) 선언에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-110">You can also specify [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), or [Static](../../../../visual-basic/language-reference/modifiers/static.md) in the declaration.</span></span> <span data-ttu-id="5816e-111">다음 예제에서는 선언을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-111">The following example declarations are valid:</span></span>  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a><span data-ttu-id="5816e-112">초기 바인딩 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="5816e-112">Late Binding and Early Binding</span></span>  
 <span data-ttu-id="5816e-113">경우에 따라 특정 클래스 알려지지 않은 코드가 실행 될 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-113">Sometimes the specific class is unknown until your code runs.</span></span> <span data-ttu-id="5816e-114">개체 변수를 선언 해야이 경우에 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-114">In this case, you must declare the object variable with the `Object` data type.</span></span> <span data-ttu-id="5816e-115">모든 유형의 개체에 대 한 일반 참조를 만들고 특정 클래스는 런타임에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-115">This creates a general reference to any type of object, and the specific class is assigned at run time.</span></span> <span data-ttu-id="5816e-116">이 이라고 *런타임에 바인딩*합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-116">This is called *late binding*.</span></span> <span data-ttu-id="5816e-117">런타임에 바인딩 추가 실행 시간이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-117">Late binding requires additional execution time.</span></span> <span data-ttu-id="5816e-118">또한 코드를 가장 최근에 할당 된 클래스의 속성과 메서드를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-118">It also limits your code to the methods and properties of the class you have most recently assigned to it.</span></span> <span data-ttu-id="5816e-119">이 코드를 다른 클래스의 멤버에 액세스 하려고 합니다. 런타임 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-119">This can cause run-time errors if your code attempts to access members of a different class.</span></span>  
  
 <span data-ttu-id="5816e-120">컴파일 시간에 특정 클래스를 알고 있는 경우 해당 클래스의 개체 변수를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-120">When you know the specific class at compile time, you should declare the object variable to be of that class.</span></span> <span data-ttu-id="5816e-121">이것을 *초기 바인딩*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-121">This is called *early binding*.</span></span> <span data-ttu-id="5816e-122">초기 바인딩 성능을 개선 하 고 모든 메서드 및 특정 클래스의 속성에 대 한 코드 액세스를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-122">Early binding improves performance and guarantees your code access to all the methods and properties of the specific class.</span></span> <span data-ttu-id="5816e-123">변수 경우 이전 예제에서는 선언에 `objA` 클래스의 개체에만 사용 하 여 <xref:System.Windows.Forms.Label?displayProperty=nameWithType>를 지정 해야 `As System.Windows.Forms.Label` 를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-123">In the preceding example declarations, if variable `objA` uses only objects of class <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, you should specify `As System.Windows.Forms.Label` in its declaration.</span></span>  
  
### <a name="advantages-of-early-binding"></a><span data-ttu-id="5816e-124">초기 바인딩의 장점</span><span class="sxs-lookup"><span data-stu-id="5816e-124">Advantages of Early Binding</span></span>  
 <span data-ttu-id="5816e-125">특정 클래스로 개체 변수를 선언 하면 여러 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-125">Declaring an object variable as a specific class gives you several advantages:</span></span>  
  
- <span data-ttu-id="5816e-126">자동 형식 검사</span><span class="sxs-lookup"><span data-stu-id="5816e-126">Automatic type checking</span></span>  
  
- <span data-ttu-id="5816e-127">특정 클래스의 모든 멤버에 대 한 액세스 보장</span><span class="sxs-lookup"><span data-stu-id="5816e-127">Guaranteed access to all members of the specific class</span></span>  
  
- <span data-ttu-id="5816e-128">코드 편집기에서 Microsoft IntelliSense 지원</span><span class="sxs-lookup"><span data-stu-id="5816e-128">Microsoft IntelliSense support in the Code Editor</span></span>  
  
- <span data-ttu-id="5816e-129">코드의 가독성 향상된</span><span class="sxs-lookup"><span data-stu-id="5816e-129">Improved readability of your code</span></span>  
  
- <span data-ttu-id="5816e-130">코드에서 오류를 줄일 수</span><span class="sxs-lookup"><span data-stu-id="5816e-130">Fewer errors in your code</span></span>  
  
- <span data-ttu-id="5816e-131">에 전달 된 오류 컴파일 시간 대신 런타임에</span><span class="sxs-lookup"><span data-stu-id="5816e-131">Errors caught at compile time rather than run time</span></span>  
  
- <span data-ttu-id="5816e-132">빠른 코드 실행</span><span class="sxs-lookup"><span data-stu-id="5816e-132">Faster code execution</span></span>  
  
## <a name="access-to-object-variable-members"></a><span data-ttu-id="5816e-133">개체 변수 멤버에 대 한 액세스</span><span class="sxs-lookup"><span data-stu-id="5816e-133">Access to Object Variable Members</span></span>  
 <span data-ttu-id="5816e-134">때 `Option Strict` 꺼져 `On`, 메서드 및 속성 선언 된 클래스의 개체 변수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-134">When `Option Strict` is turned `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="5816e-135">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-135">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="5816e-136">이 예제에서 `p` 는 <xref:System.Object> 클래스 자체의 멤버만 사용할 수 있으므로 `Left` 속성을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-136">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="5816e-137">반면, `q` 형식으로 선언된 <xref:System.Windows.Forms.Label>는 <xref:System.Windows.Forms.Label> 네임스페이스에 있는 <xref:System.Windows.Forms> 클래스의 모든 메서드와 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-137">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="flexibility-of-object-variables"></a><span data-ttu-id="5816e-138">개체 변수의 유연성</span><span class="sxs-lookup"><span data-stu-id="5816e-138">Flexibility of Object Variables</span></span>  
 <span data-ttu-id="5816e-139">상속 계층 구조의 개체를 사용할 때는 다양 한 개체 변수를 선언 하는 데 사용 하는 클래스를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-139">When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables.</span></span> <span data-ttu-id="5816e-140">이 선택 하는 경우 클래스의 멤버에 대 한 액세스에 대 한 개체 할당의 유연 하 게를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-140">In making this choice, you must balance flexibility of object assignment against access to members of a class.</span></span> <span data-ttu-id="5816e-141">예를 들어을 발생 시키는 상속 계층 구조는 <xref:System.Windows.Forms.Form?displayProperty=nameWithType> 클래스:</span><span class="sxs-lookup"><span data-stu-id="5816e-141">For example, consider the inheritance hierarchy that leads to the <xref:System.Windows.Forms.Form?displayProperty=nameWithType> class:</span></span>  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 <span data-ttu-id="5816e-142">응용 프로그램 폼 클래스를 정의 하는 가정 `specialForm`, 클래스에서 상속 하는 <xref:System.Windows.Forms.Form>합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-142">Suppose your application defines a form class called `specialForm`, which inherits from class <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="5816e-143">특히 참조 하는 개체 변수를 선언할 수 있습니다 `specialForm`다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-143">You can declare an object variable that refers specifically to `specialForm`, as the following example shows.</span></span>  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 <span data-ttu-id="5816e-144">앞의 예제에서 선언과 변수를 제한 `nextForm` 클래스의 개체에 `specialForm`, 되지만 모든 메서드 및 속성을 `specialForm` 수 `nextForm`는 모든 클래스의 모든 멤버 뿐 아니라 `specialForm` 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-144">The declaration in the preceding example limits the variable `nextForm` to objects of class `specialForm`, but it also makes all the methods and properties of `specialForm` available to `nextForm`, as well as all the members of all the classes from which `specialForm` inherits.</span></span>  
  
 <span data-ttu-id="5816e-145">형식으로 선언 하 여 보다 일반적인 개체 변수를 만들 수 있습니다 <xref:System.Windows.Forms.Form>다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-145">You can make an object variable more general by declaring it to be of type <xref:System.Windows.Forms.Form>, as the following example shows.</span></span>  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="5816e-146">앞의 예제에서 선언과 사용 하면 응용 프로그램의 어떠한 부분도 할당 `anyForm`합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-146">The declaration in the preceding example lets you assign any form in your application to `anyForm`.</span></span> <span data-ttu-id="5816e-147">그러나 있지만 `anyForm` 클래스의 모든 멤버에 액세스할 수 있습니다 <xref:System.Windows.Forms.Form>에서 추가 메서드 또는 같은 특정 폼에 정의 된 속성 중 하나를 사용할 수 없습니다 `specialForm`합니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-147">However, although `anyForm` can access all the members of class <xref:System.Windows.Forms.Form>, it cannot use any of the additional methods or properties defined for specific forms such as `specialForm`.</span></span>  
  
 <span data-ttu-id="5816e-148">기본 클래스의 모든 멤버는 파생된 클래스를 사용할 수 있지만 파생된 클래스의 추가 멤버는 기본 클래스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5816e-148">All the members of a base class are available to derived classes, but the additional members of a derived class are unavailable to the base class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5816e-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="5816e-149">See also</span></span>

- [<span data-ttu-id="5816e-150">개체 변수</span><span class="sxs-lookup"><span data-stu-id="5816e-150">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="5816e-151">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="5816e-151">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="5816e-152">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="5816e-152">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="5816e-153">방법: 개체 변수를 선언 하 고 Visual Basic의 개체를 할당</span><span class="sxs-lookup"><span data-stu-id="5816e-153">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="5816e-154">방법: 개체의 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="5816e-154">How to: Access Members of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [<span data-ttu-id="5816e-155">New 연산자</span><span class="sxs-lookup"><span data-stu-id="5816e-155">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="5816e-156">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="5816e-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="5816e-157">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="5816e-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
