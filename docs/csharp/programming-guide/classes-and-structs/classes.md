---
title: 클래스 - C# 프로그래밍 가이드
description: 클래스 형식 및 이를 만드는 방법을 자세히 알아봅니다.
ms.date: 08/21/2018
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
ms.openlocfilehash: d726ab3a882d2e6913fa69c7b82f1d6db78dd47d
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102049"
---
# <a name="classes-c-programming-guide"></a><span data-ttu-id="34093-103">클래스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="34093-103">Classes (C# Programming Guide)</span></span>

## <a name="reference-types"></a><span data-ttu-id="34093-104">참조 형식</span><span class="sxs-lookup"><span data-stu-id="34093-104">Reference types</span></span>  
<span data-ttu-id="34093-105">[클래스](../../language-reference/keywords/class.md)로 정의된 형식은 *참조 형식*입니다.</span><span class="sxs-lookup"><span data-stu-id="34093-105">A type that is defined as a [class](../../language-reference/keywords/class.md) is a *reference type*.</span></span> <span data-ttu-id="34093-106">런타임에 참조 형식의 변수를 선언하면 [new](../../language-reference/keywords/null.md) 연산자를 사용하여 클래스의 인스턴스를 명시적으로 만들거나 다음 예제와 같이 다른 곳에서 만들어진 호환성 있는 형식의 개체를 할당할 때까지 변수에는 [null](../../language-reference/operators/new-operator.md) 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="34093-106">At run time, when you declare a variable of a reference type, the variable contains the value [null](../../language-reference/keywords/null.md) until you explicitly create an instance of the class by using the [new](../../language-reference/operators/new-operator.md) operator, or assign it an object of a compatible type that may have been created elsewhere, as shown in the following example:</span></span>

```csharp
//Declaring an object of type MyClass.
MyClass mc = new MyClass();

//Declaring another object of the same type, assigning it the value of the first object.
MyClass mc2 = mc;
```

<span data-ttu-id="34093-107">개체가 만들어지면 해당 특정 개체에 대해 관리되는 힙에 충분한 메모리가 할당되고 변수에는 개체 위치에 대한 참조만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="34093-107">When the object is created, enough memory is allocated on the managed heap for that specific object, and the variable holds only a reference to the location of said object.</span></span> <span data-ttu-id="34093-108">관리되는 힙의 형식은 할당될 때, 그리고 *가비지 수집*이라는 CLR의 자동 메모리 관리 기능에 의해 회수될 때 오버헤드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="34093-108">Types on the managed heap require overhead both when they are allocated and when they are reclaimed by the automatic memory management functionality of the CLR, which is known as *garbage collection*.</span></span> <span data-ttu-id="34093-109">그러나 가비지 수집은 고도로 최적화되고 대부분 시나리오에서 성능 문제를 일으키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-109">However, garbage collection is also highly optimized and in most scenarios, it does not create a performance issue.</span></span> <span data-ttu-id="34093-110">가비지 수집에 대한 자세한 내용은 [자동 메모리 관리 및 가비지 수집](../../../standard/garbage-collection/fundamentals.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34093-110">For more information about garbage collection, see [Automatic memory management and garbage collection](../../../standard/garbage-collection/fundamentals.md).</span></span>  
  
## <a name="declaring-classes"></a><span data-ttu-id="34093-111">클래스 선언</span><span class="sxs-lookup"><span data-stu-id="34093-111">Declaring Classes</span></span>

 <span data-ttu-id="34093-112">클래스는 다음 예제와 같이 [class](../../language-reference/keywords/class.md) 키워드 다음에 고유 식별자를 사용하여 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="34093-112">Classes are declared by using the [class](../../language-reference/keywords/class.md) keyword followed by a unique identifier, as shown in the following example:</span></span>

 ```csharp
//[access modifier] - [class] - [identifier]
 public class Customer
 {
    // Fields, properties, methods and events go here...
 }
```

 <span data-ttu-id="34093-113">`class` 키워드는 액세스 수준 뒤에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="34093-113">The `class` keyword is preceded by the access level.</span></span> <span data-ttu-id="34093-114">이 경우 [public](../../language-reference/keywords/public.md)이 사용되므로 누구나 이 클래스의 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-114">Because [public](../../language-reference/keywords/public.md) is used in this case, anyone can create instances of this class.</span></span> <span data-ttu-id="34093-115">클래스 이름은 `class` 키워드 뒤에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="34093-115">The name of the class follows the `class` keyword.</span></span> <span data-ttu-id="34093-116">클래스의 이름은 유효한 C# [식별자 이름](../inside-a-program/identifier-names.md)이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34093-116">The name of the class must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="34093-117">정의의 나머지 부분은 동작과 데이터가 정의되는 클래스 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="34093-117">The remainder of the definition is the class body, where the behavior and data are defined.</span></span> <span data-ttu-id="34093-118">클래스의 필드, 속성, 메서드 및 이벤트를 모두 *클래스 멤버*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="34093-118">Fields, properties, methods, and events on a class are collectively referred to as *class members*.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="34093-119">개체 만들기</span><span class="sxs-lookup"><span data-stu-id="34093-119">Creating objects</span></span>

<span data-ttu-id="34093-120">클래스와 개체는 바꿔 사용되기도 하지만 서로 다른 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="34093-120">Although they are sometimes used interchangeably, a class and an object are different things.</span></span> <span data-ttu-id="34093-121">클래스는 개체의 형식을 정의하지만 개체 자체는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="34093-121">A class defines a type of object, but it is not an object itself.</span></span> <span data-ttu-id="34093-122">개체는 클래스에 기반을 둔 구체적 엔터티이고 클래스의 인스턴스라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="34093-122">An object is a concrete entity based on a class, and is sometimes referred to as an instance of a class.</span></span>  
  
 <span data-ttu-id="34093-123">개체를 만들려면 다음과 같이 [new](../../language-reference/operators/new-operator.md) 키워드 뒤에 개체의 기반이 되는 클래스의 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34093-123">Objects can be created by using the [new](../../language-reference/operators/new-operator.md) keyword followed by the name of the class that the object will be based on, like this:</span></span>  

 ```csharp
 Customer object1 = new Customer();
 ```

 <span data-ttu-id="34093-124">클래스 인스턴스가 만들어질 때 개체에 대한 참조가 다시 프로그래머에게 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="34093-124">When an instance of a class is created, a reference to the object is passed back to the programmer.</span></span> <span data-ttu-id="34093-125">이전 예제에서 `object1`은 `Customer`에 기반을 둔 개체에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="34093-125">In the previous example, `object1` is a reference to an object that is based on `Customer`.</span></span> <span data-ttu-id="34093-126">이 참조는 새 개체를 참조하지만 개체 데이터 자체를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-126">This reference refers to the new object but does not contain the object data itself.</span></span> <span data-ttu-id="34093-127">실제로 개체를 만들지 않고도 개체 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-127">In fact, you can create an object reference without creating an object at all:</span></span>  

```csharp
 Customer object2;
```

 <span data-ttu-id="34093-128">런타임에는 참조를 통한 개체 액세스 시도에 실패하므로 개체를 참조하지 않는 이와 같은 개체 참조는 만들지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-128">We don't recommend creating object references such as this one that don't refer to an object because trying to access an object through such a reference will fail at run time.</span></span> <span data-ttu-id="34093-129">그러나 새 개체를 만들거나 다음과 같이 기존 개체에 개체를 할당하여 개체를 참조하는 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-129">However, such a reference can be made to refer to an object, either by creating a new object, or by assigning it to an existing object, such as this:</span></span>  

 ```csharp
 Customer object3 = new Customer();
 Customer object4 = object3;
```
  
 <span data-ttu-id="34093-130">이 코드에서는 같은 개체를 참조하는 두 개의 개체 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34093-130">This code creates two object references that both refer to the same object.</span></span> <span data-ttu-id="34093-131">따라서 `object3`을 통해 이루어진 모든 개체 변경 내용은 이후 `object4` 사용 시 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="34093-131">Therefore, any changes to the object made through `object3` are reflected in subsequent uses of `object4`.</span></span> <span data-ttu-id="34093-132">클래스에 기반을 둔 개체는 참조를 통해 참조되므로 클래스를 참조 형식이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="34093-132">Because objects that are based on classes are referred to by reference, classes are known as reference types.</span></span>  
  
## <a name="class-inheritance"></a><span data-ttu-id="34093-133">클래스 상속</span><span class="sxs-lookup"><span data-stu-id="34093-133">Class inheritance</span></span>  

<span data-ttu-id="34093-134">클래스는 개체 지향 프로그래밍의 기본적인 특성인 ‘상속’을 완전히 지원합니다. </span><span class="sxs-lookup"><span data-stu-id="34093-134">Classes fully support *inheritance*, a fundamental characteristic of object-oriented programming.</span></span> <span data-ttu-id="34093-135">클래스를 만들 때 [sealed](../../language-reference/keywords/sealed.md)로 정의되지 않은 기타 인터페이스 또는 클래스에서 상속될 수 있고 기타 클래스는 직접 만든 클래스에서 상속되고 클래스 가상 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-135">When you create a class, you can inherit from any other interface or class that is not defined as [sealed](../../language-reference/keywords/sealed.md), and other classes can inherit from your class and override class virtual methods.</span></span>

<span data-ttu-id="34093-136">상속은 *파생*을 통해 수행합니다. 즉, 클래스는 데이터와 동작을 상속하는 소스 *기본 클래스*를 사용하여 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="34093-136">Inheritance is accomplished by using a *derivation*, which means a class is declared by using a *base class* from which it inherits data and behavior.</span></span> <span data-ttu-id="34093-137">다음과 같이 파생 클래스 이름 뒤에 콜론 및 기본 클래스 이름을 추가하여 기본 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="34093-137">A base class is specified by appending a colon and the name of the base class following the derived class name, like this:</span></span>  

 ```csharp
 public class Manager : Employee
 {
     // Employee fields, properties, methods and events are inherited
     // New Manager fields, properties, methods and events go here...
 }
 ```

<span data-ttu-id="34093-138">기본 클래스를 선언하는 클래스는 생성자를 제외하고 기본 클래스의 모든 멤버를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="34093-138">When a class declares a base class, it inherits all the members of the base class except the constructors.</span></span> <span data-ttu-id="34093-139">자세한 내용은 [상속](inheritance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34093-139">For more information, see [Inheritance](inheritance.md).</span></span>
  
<span data-ttu-id="34093-140">C++와 달리 C#의 클래스는 하나의 기본 클래스에서만 직접 상속될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-140">Unlike C++, a class in C# can only directly inherit from one base class.</span></span> <span data-ttu-id="34093-141">그러나 기본 클래스 자체는 다른 클래스에서 상속될 수 있으므로 클래스는 여러 기본 클래스를 간접적으로 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-141">However, because a base class may itself inherit from another class, a class may indirectly inherit multiple base classes.</span></span> <span data-ttu-id="34093-142">게다가 클래스는 두 개 이상의 인터페이스를 직접 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-142">Furthermore, a class can directly implement more than one interface.</span></span> <span data-ttu-id="34093-143">자세한 내용은 [인터페이스](../interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34093-143">For more information, see [Interfaces](../interfaces/index.md).</span></span>  
  
<span data-ttu-id="34093-144">클래스는 [abstract](../../language-reference/keywords/abstract.md)로 선언될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-144">A class can be declared [abstract](../../language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="34093-145">추상 클래스에는 시그니처 정의가 있지만 구현이 없는 추상 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="34093-145">An abstract class contains abstract methods that have a signature definition but no implementation.</span></span> <span data-ttu-id="34093-146">추상 클래스는 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-146">Abstract classes cannot be instantiated.</span></span> <span data-ttu-id="34093-147">추상 클래스는 추상 메서드를 구현하는 파생 클래스를 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-147">They can only be used through derived classes that implement the abstract methods.</span></span> <span data-ttu-id="34093-148">이와 달리 [sealed](../../language-reference/keywords/sealed.md) 클래스에서는 다른 클래스가 파생될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-148">By contrast, a [sealed](../../language-reference/keywords/sealed.md) class does not allow other classes to derive from it.</span></span> <span data-ttu-id="34093-149">자세한 내용은 [Abstract 및 Sealed 클래스와 클래스 멤버](abstract-and-sealed-classes-and-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34093-149">For more information, see [Abstract and Sealed Classes and Class Members](abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
<span data-ttu-id="34093-150">클래스 정의는 여러 소스 파일로 분할될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34093-150">Class definitions can be split between different source files.</span></span> <span data-ttu-id="34093-151">자세한 내용은 [Partial 클래스 및 메서드](partial-classes-and-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34093-151">For more information, see [Partial Classes and Methods](partial-classes-and-methods.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34093-152">예제</span><span class="sxs-lookup"><span data-stu-id="34093-152">Example</span></span>

<span data-ttu-id="34093-153">다음 예제에서는 [자동 구현 속성](auto-implemented-properties.md), 메서드 및 생성자라는 특수 메서드를 포함하는 공용 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="34093-153">The following example defines a public class that contains an [auto-implemented property](auto-implemented-properties.md), a method, and a special method called a constructor.</span></span> <span data-ttu-id="34093-154">자세한 내용은 [속성](properties.md), [메서드](methods.md) 및 [생성자](constructors.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34093-154">For more information, see [Properties](properties.md), [Methods](methods.md), and [Constructors](constructors.md) topics.</span></span> <span data-ttu-id="34093-155">그런 다음, 클래스의 인스턴스는 `new` 키워드를 사용하여 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="34093-155">The instances of the class are then instantiated with the `new` keyword.</span></span>  
  
[!code-csharp[Class Example](~/samples/snippets/csharp/programming-guide/classes-and-structs/class-example.cs)]
  
## <a name="c-language-specification"></a><span data-ttu-id="34093-156">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="34093-156">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="34093-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34093-157">See also</span></span>

- [<span data-ttu-id="34093-158">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="34093-158">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="34093-159">개체 지향 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="34093-159">Object-Oriented Programming</span></span>](../concepts/object-oriented-programming.md)
- [<span data-ttu-id="34093-160">다형성</span><span class="sxs-lookup"><span data-stu-id="34093-160">Polymorphism</span></span>](polymorphism.md)
- [<span data-ttu-id="34093-161">식별자 이름</span><span class="sxs-lookup"><span data-stu-id="34093-161">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="34093-162">멤버</span><span class="sxs-lookup"><span data-stu-id="34093-162">Members</span></span>](members.md)
- [<span data-ttu-id="34093-163">메서드</span><span class="sxs-lookup"><span data-stu-id="34093-163">Methods</span></span>](methods.md)
- [<span data-ttu-id="34093-164">생성자</span><span class="sxs-lookup"><span data-stu-id="34093-164">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="34093-165">종료자</span><span class="sxs-lookup"><span data-stu-id="34093-165">Finalizers</span></span>](destructors.md)
- [<span data-ttu-id="34093-166">개체</span><span class="sxs-lookup"><span data-stu-id="34093-166">Objects</span></span>](objects.md)
