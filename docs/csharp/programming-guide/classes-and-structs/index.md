---
title: 클래스 및 구조체 - C# 프로그래밍 가이드
description: C#의 클래스 및 구조(구조체) 사용에 대해 설명합니다.
ms.date: 02/25/2021
helpviewer_keywords:
- structs [C#], about structs
- classes [C#], overview
- C# language, structs
- C# language, objects
- objects [C#]
- C# language, classes
ms.assetid: cc39dbda-8754-423e-b5b1-16a1db0734c0
ms.openlocfilehash: 2d4aa6ce8a8ac6d8c5b9f24ed55221873055018c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258496"
---
# <a name="classes-and-structs-c-programming-guide"></a><span data-ttu-id="82624-103">클래스 및 구조체(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="82624-103">Classes and structs (C# programming guide)</span></span>

<span data-ttu-id="82624-104">클래스 및 구조체는 .NET의 CTS(공용 형식 시스템)의 기본 구문 중 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="82624-104">Classes and structs are two of the basic constructs of the common type system in .NET.</span></span> <span data-ttu-id="82624-105">각각은 기본적으로 하나의 논리 단위에 속하는 데이터 및 동작 집합을 캡슐화하는 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="82624-105">Each is essentially a data structure that encapsulates a set of data and behaviors that belong together as a logical unit.</span></span> <span data-ttu-id="82624-106">데이터 및 동작은 클래스 또는 구조체의 *멤버* 로, 이 항목의 뒷부분에 나오는 것처럼 메서드, 속성 및 이벤트 등을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-106">The data and behaviors are the *members* of the class or struct, and they include its methods, properties, and events, and so on, as listed later in this topic.</span></span>  
  
 <span data-ttu-id="82624-107">클래스 또는 구조체 선언은 런타임에 인스턴스 또는 개체를 만드는 데 사용되는 청사진과도 같습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-107">A class or struct declaration is like a blueprint that is used to create instances or objects at run time.</span></span> <span data-ttu-id="82624-108">`Person`이라고 하는 클래스 또는 구조체를 정의하는 경우 `Person`이 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="82624-108">If you define a class or struct called `Person`, `Person` is the name of the type.</span></span> <span data-ttu-id="82624-109">형식 `Person`의 변수 `p`를 선언하고 초기화하면 `p`는 `Person`의 개체 또는 인스턴스로 지칭됩니다.</span><span class="sxs-lookup"><span data-stu-id="82624-109">If you declare and initialize a variable `p` of type `Person`, `p` is said to be an object or instance of `Person`.</span></span> <span data-ttu-id="82624-110">같은 `Person` 형식의 여러 인스턴스를 만들 수 있으며 각 인스턴스는 속성 및 필드에 서로 다른 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-110">Multiple instances of the same `Person` type can be created, and each instance can have different values in its properties and fields.</span></span>  
  
 <span data-ttu-id="82624-111">클래스는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="82624-111">A class is a reference type.</span></span> <span data-ttu-id="82624-112">클래스의 개체가 만들어지면 개체가 할당되는 변수는 해당 메모리에 대한 참조만 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-112">When an object of the class is created, the variable to which the object is assigned holds only a reference to that memory.</span></span> <span data-ttu-id="82624-113">개체 참조가 새 변수에 할당되면 새 변수는 원래 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82624-113">When the object reference is assigned to a new variable, the new variable refers to the original object.</span></span> <span data-ttu-id="82624-114">모두 동일한 데이터를 참조하므로 한 변수의 변경 내용이 다른 변수에도 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="82624-114">Changes made through one variable are reflected in the other variable because they both refer to the same data.</span></span>
  
 <span data-ttu-id="82624-115">구조체는 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="82624-115">A struct is a value type.</span></span> <span data-ttu-id="82624-116">구조체가 만들어지면 해당 구조체가 할당되는 변수에 구조체의 실제 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="82624-116">When a struct is created, the variable to which the struct is assigned holds the struct's actual data.</span></span> <span data-ttu-id="82624-117">구조체를 새 변수에 할당하면 구조체가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="82624-117">When the struct is assigned to a new variable, it is copied.</span></span> <span data-ttu-id="82624-118">따라서 새 변수와 원래 변수에 동일한 데이터의 두 가지 별도 복사본이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="82624-118">The new variable and the original variable therefore contain two separate copies of the same data.</span></span> <span data-ttu-id="82624-119">한 복사본의 변경 내용은 다른 복사본에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-119">Changes made to one copy do not affect the other copy.</span></span>  
  
 <span data-ttu-id="82624-120">일반적으로 클래스는 좀 더 복잡한 동작이나 클래스 개체를 만든 후 수정하려는 데이터를 모델링하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="82624-120">In general, classes are used to model more complex behavior, or data that is intended to be modified after a class object is created.</span></span> <span data-ttu-id="82624-121">구조체는 구조체를 만든 후에 수정하지 않으려는 데이터를 주로 포함하는 작은 데이터 구조에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-121">Structs are best suited for small data structures that contain primarily data that isn't intended to be modified after the struct is created.</span></span> <span data-ttu-id="82624-122">C# 9부터 레코드 형식은 개체를 만든 후 수정하지 않을 데이터를 주로 포함하는 더 큰 데이터 구조에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-122">Starting in C# 9, record types are available for larger data structures that contain primarily data that isn't intended to be modified after the object is created.</span></span>
  
 <span data-ttu-id="82624-123">자세한 내용은 [클래스](./classes.md), [개체](./objects.md), [구조 형식](../../language-reference/builtin-types/struct.md), [레코드](../../language-reference/builtin-types/record.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-123">For more information, see [Classes](./classes.md), [Objects](./objects.md), [Structure types](../../language-reference/builtin-types/struct.md), and [Records](../../language-reference/builtin-types/record.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="82624-124">예제</span><span class="sxs-lookup"><span data-stu-id="82624-124">Example</span></span>  

 <span data-ttu-id="82624-125">다음 예제에서 `ProgrammingGuide` 네임스페이스의 `CustomClass`에는 세 개의 멤버, 즉 인스턴스 생성자, `Number`라는 속성 및 `Multiply`이라는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-125">In the following example, `CustomClass` in the `ProgrammingGuide` namespace has three members: an instance constructor, a property named `Number`, and a method named `Multiply`.</span></span> <span data-ttu-id="82624-126">`Program` 클래스의 `Main` 메서드는 `CustomClass`의 인스턴스(개체)를 만들고 개체의 메서드 및 속성은 점 표기법을 통해 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="82624-126">The `Main` method in the `Program` class creates an instance (object) of `CustomClass`, and the object's method and property are accessed by using dot notation.</span></span>
  
 [!code-csharp[csProgGuideObjects#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/class1.cs#1)]  
  
## <a name="encapsulation"></a><span data-ttu-id="82624-127">캡슐화</span><span class="sxs-lookup"><span data-stu-id="82624-127">Encapsulation</span></span>  

 <span data-ttu-id="82624-128">*캡슐화* 는 경우에 따라 개체 지향 프로그래밍의 첫 번째 pillar 또는 원리로 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="82624-128">*Encapsulation* is sometimes referred to as the first pillar or principle of object-oriented programming.</span></span> <span data-ttu-id="82624-129">캡슐화의 원리에 따라 클래스 또는 구조체는 클래스 또는 구조체 외부의 코드에 각 멤버가 액세스하는 방법을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-129">According to the principle of encapsulation, a class or struct can specify how accessible each of its members is to code outside of the class or struct.</span></span> <span data-ttu-id="82624-130">코딩 오류 또는 악의적인 악용 가능성을 제한하려면 클래스 또는 어셈블리 외부에서 사용하지 않으려는 메서드 및 변수는 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-130">Methods and variables that are not intended to be used from outside of the class or assembly can be hidden to limit the potential for coding errors or malicious exploits.</span></span>  
  
 <span data-ttu-id="82624-131">클래스에 대한 자세한 내용은 [클래스](./classes.md) 및 [개체](./objects.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-131">For more information about classes, see [Classes](./classes.md) and [Objects](./objects.md).</span></span>  
  
## <a name="members"></a><span data-ttu-id="82624-132">멤버</span><span class="sxs-lookup"><span data-stu-id="82624-132">Members</span></span>  

 <span data-ttu-id="82624-133">모든 메서드, 필드, 상수, 속성 및 이벤트는 형식 내에서 선언되어야 합니다. 이것을 형식의 *멤버* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-133">All methods, fields, constants, properties, and events must be declared within a type; these are called the *members* of the type.</span></span> <span data-ttu-id="82624-134">다른 언어에는 있지만 C#에는 전역 변수 또는 메서드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-134">In C#, there are no global variables or methods as there are in some other languages.</span></span> <span data-ttu-id="82624-135">프로그램의 진입점인 `Main` 메서드까지도 클래스 또는 구조체 내에서 선언되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-135">Even a program's entry point, the `Main` method, must be declared within a class or struct.</span></span> <span data-ttu-id="82624-136">다음은 클래스 또는 구조체에서 선언될 수 있는 모든 다양한 종류의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="82624-136">The following list includes all the various kinds of members that may be declared in a class or struct.</span></span>  
  
- [<span data-ttu-id="82624-137">필드</span><span class="sxs-lookup"><span data-stu-id="82624-137">Fields</span></span>](./fields.md)  
  
- [<span data-ttu-id="82624-138">상수</span><span class="sxs-lookup"><span data-stu-id="82624-138">Constants</span></span>](./constants.md)  
  
- [<span data-ttu-id="82624-139">속성</span><span class="sxs-lookup"><span data-stu-id="82624-139">Properties</span></span>](./properties.md)  
  
- [<span data-ttu-id="82624-140">메서드</span><span class="sxs-lookup"><span data-stu-id="82624-140">Methods</span></span>](./methods.md)  
  
- [<span data-ttu-id="82624-141">생성자</span><span class="sxs-lookup"><span data-stu-id="82624-141">Constructors</span></span>](./constructors.md)  
  
- [<span data-ttu-id="82624-142">이벤트</span><span class="sxs-lookup"><span data-stu-id="82624-142">Events</span></span>](../events/index.md)  
  
- [<span data-ttu-id="82624-143">종료자</span><span class="sxs-lookup"><span data-stu-id="82624-143">Finalizers</span></span>](./destructors.md)  
  
- [<span data-ttu-id="82624-144">인덱서</span><span class="sxs-lookup"><span data-stu-id="82624-144">Indexers</span></span>](../indexers/index.md)  
  
- [<span data-ttu-id="82624-145">연산자</span><span class="sxs-lookup"><span data-stu-id="82624-145">Operators</span></span>](../../language-reference/operators/index.md)  
  
- [<span data-ttu-id="82624-146">중첩 형식</span><span class="sxs-lookup"><span data-stu-id="82624-146">Nested Types</span></span>](./nested-types.md)  
  
## <a name="accessibility"></a><span data-ttu-id="82624-147">액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="82624-147">Accessibility</span></span>  

 <span data-ttu-id="82624-148">일부 메서드 및 속성은 *클라이언트 코드* 라고 하는 클래스 또는 구조체 외부의 코드에서 호출하거나 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-148">Some methods and properties are meant to be called or accessed from code outside your class or struct, known as *client code*.</span></span> <span data-ttu-id="82624-149">다른 메서드 및 속성은 클래스 또는 구조체 자체에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-149">Other methods and properties might be only for use in the class or struct itself.</span></span> <span data-ttu-id="82624-150">의도된 클라이언트 코드에서만 연결될 수 있도록 코드의 액세스 가능성을 제한하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-150">It is important to limit the accessibility of your code so that only the intended client code can reach it.</span></span> <span data-ttu-id="82624-151">형식 및 해당 멤버가 클라이언트 코드에 액세스하는 방법은 액세스 한정자 [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) 및 [private protected](../../language-reference/keywords/private-protected.md)를 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-151">You specify how accessible your types and their members are to client code by using the access modifiers [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) and [private protected](../../language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="82624-152">기본 액세스 가능성은 `private`입니다.</span><span class="sxs-lookup"><span data-stu-id="82624-152">The default accessibility is `private`.</span></span> <span data-ttu-id="82624-153">자세한 내용은 [액세스 한정자](./access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-153">For more information, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="82624-154">상속</span><span class="sxs-lookup"><span data-stu-id="82624-154">Inheritance</span></span>  

 <span data-ttu-id="82624-155">클래스(구조체는 아님)는 상속 개념을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-155">Classes (but not structs) support the concept of inheritance.</span></span> <span data-ttu-id="82624-156">다른 클래스(*기본 클래스*)에서 파생되는 클래스는 생성자와 종료자를 제외하고 기본 클래스의 모든 public, protected 및 internal 멤버를 자동으로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-156">A class that derives from another class (the *base class*) automatically contains all the public, protected, and internal members of the base class except its constructors and finalizers.</span></span> <span data-ttu-id="82624-157">자세한 내용은 [상속](./inheritance.md) 및 [다형성](./polymorphism.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-157">For more information, see [Inheritance](./inheritance.md) and [Polymorphism](./polymorphism.md).</span></span>  
  
 <span data-ttu-id="82624-158">클래스를 [abstract](../../language-reference/keywords/abstract.md)로 선언할 수도 있습니다. 즉, 하나 이상의 해당 메서드에 구현이 없는 상태를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-158">Classes may be declared as [abstract](../../language-reference/keywords/abstract.md), which means that one or more of their methods have no implementation.</span></span> <span data-ttu-id="82624-159">추상 클래스는 직접 인스턴스화할 수 없지만 누락된 구현을 제공하는 다른 클래스에 대한 기본 클래스로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-159">Although abstract classes cannot be instantiated directly, they can serve as base classes for other classes that provide the missing implementation.</span></span> <span data-ttu-id="82624-160">다른 클래스가 이 클래스에서 상속 받지 못하게 하려면 클래스를 [sealed](../../language-reference/keywords/sealed.md)로 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-160">Classes can also be declared as [sealed](../../language-reference/keywords/sealed.md) to prevent other classes from inheriting from them.</span></span> <span data-ttu-id="82624-161">자세한 내용은 [Abstract 및 Sealed 클래스와 클래스 멤버](./abstract-and-sealed-classes-and-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-161">For more information, see [Abstract and Sealed Classes and Class Members](./abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
## <a name="interfaces"></a><span data-ttu-id="82624-162">인터페이스</span><span class="sxs-lookup"><span data-stu-id="82624-162">Interfaces</span></span>  

 <span data-ttu-id="82624-163">클래스 및 구조체는 여러 인터페이스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-163">Classes and structs can inherit multiple interfaces.</span></span> <span data-ttu-id="82624-164">인터페이스에서 상속하는 것은 형식이 해당 인터페이스에 정의된 모든 메서드를 구현한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="82624-164">To inherit from an interface means that the type implements all the methods defined in the interface.</span></span> <span data-ttu-id="82624-165">자세한 내용은 [인터페이스](../interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-165">For more information, see [Interfaces](../interfaces/index.md).</span></span>  
  
## <a name="generic-types"></a><span data-ttu-id="82624-166">제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="82624-166">Generic Types</span></span>  

 <span data-ttu-id="82624-167">하나 이상의 형식 매개 변수를 사용하여 클래스 및 구조체를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-167">Classes and structs can be defined with one or more type parameters.</span></span> <span data-ttu-id="82624-168">클라이언트 코드는 형식의 인스턴스를 만들 때 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-168">Client code supplies the type when it creates an instance of the type.</span></span> <span data-ttu-id="82624-169">예를 들어 <xref:System.Collections.Generic> 네임스페이스의 <xref:System.Collections.Generic.List%601> 클래스는 하나의 형식 매개 변수로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="82624-169">For example The <xref:System.Collections.Generic.List%601> class in the <xref:System.Collections.Generic> namespace is defined with one type parameter.</span></span> <span data-ttu-id="82624-170">클라이언트 코드는 `List<string>` 또는 `List<int>`의 인스턴스를 만들어 목록에 포함될 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-170">Client code creates an instance of a `List<string>` or `List<int>` to specify the type that the list will hold.</span></span> <span data-ttu-id="82624-171">자세한 내용은 [제네릭](../generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-171">For more information, see [Generics](../generics/index.md).</span></span>  
  
## <a name="static-types"></a><span data-ttu-id="82624-172">정적 형식</span><span class="sxs-lookup"><span data-stu-id="82624-172">Static Types</span></span>  

 <span data-ttu-id="82624-173">클래스(구조체는 아님)를 [static](../../language-reference/keywords/static.md)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-173">Classes (but not structs) can be declared as [static](../../language-reference/keywords/static.md).</span></span> <span data-ttu-id="82624-174">static 클래스는 static 멤버만 포함할 수 있고 new 키워드로 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-174">A static class can contain only static members and cannot be instantiated with the new keyword.</span></span> <span data-ttu-id="82624-175">프로그램이 로드될 때 클래스의 단일 복사본만 메모리에 로드되고 해당 멤버는 클래스 이름을 통해 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="82624-175">One copy of the class is loaded into memory when the program loads, and its members are accessed through the class name.</span></span> <span data-ttu-id="82624-176">클래스와 구조체 둘 다 정적 멤버를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-176">Both classes and structs can contain static members.</span></span> <span data-ttu-id="82624-177">자세한 내용은 [static 클래스 및 static 클래스 멤버](./static-classes-and-static-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-177">For more information, see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
## <a name="nested-types"></a><span data-ttu-id="82624-178">중첩 형식</span><span class="sxs-lookup"><span data-stu-id="82624-178">Nested Types</span></span>  

 <span data-ttu-id="82624-179">클래스 또는 구조체는 다른 클래스 또는 구조체 내에 중첩될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-179">A class or struct can be nested within another class or struct.</span></span> <span data-ttu-id="82624-180">자세한 내용은 [중첩 형식](./nested-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-180">For more information, see [Nested Types](./nested-types.md).</span></span>  
  
## <a name="partial-types"></a><span data-ttu-id="82624-181">부분 형식(Partial Type)</span><span class="sxs-lookup"><span data-stu-id="82624-181">Partial Types</span></span>  

 <span data-ttu-id="82624-182">하나의 코드 파일 및 별도 코드 파일의 다른 부분에서 클래스, 구조체 또는 메서드의 부분을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-182">You can define part of a class, struct or method in one code file and another part in a separate code file.</span></span> <span data-ttu-id="82624-183">자세한 내용은 [Partial 클래스 및 메서드](./partial-classes-and-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-183">For more information, see [Partial Classes and Methods](./partial-classes-and-methods.md).</span></span>  
  
## <a name="object-initializers"></a><span data-ttu-id="82624-184">개체 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="82624-184">Object Initializers</span></span>  

 <span data-ttu-id="82624-185">해당 생성자를 명시적으로 호출하지 않고 클래스 또는 구조체 개체, 개체 컬렉션을 인스턴스화하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-185">You can instantiate and initialize class or struct objects, and collections of objects, without explicitly calling their constructor.</span></span> <span data-ttu-id="82624-186">자세한 내용은 [개체 및 컬렉션 이니셜라이저](./object-and-collection-initializers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-186">For more information, see [Object and Collection Initializers](./object-and-collection-initializers.md).</span></span>  
  
## <a name="anonymous-types"></a><span data-ttu-id="82624-187">익명 형식</span><span class="sxs-lookup"><span data-stu-id="82624-187">Anonymous Types</span></span>  

 <span data-ttu-id="82624-188">유지하거나 다른 메서드에 전달할 필요가 없는 데이터 구조로 목록을 채우는 경우처럼 명명된 클래스를 만드는 것이 불편하거나 필요하지 않은 상황에서는 무명 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-188">In situations where it is not convenient or necessary to create a named class, for example when you are populating a list with data structures that you do not have to persist or pass to another method, you use anonymous types.</span></span> <span data-ttu-id="82624-189">자세한 내용은 [무명 형식](./anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-189">For more information, see [Anonymous Types](./anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="82624-190">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="82624-190">Extension Methods</span></span>  

 <span data-ttu-id="82624-191">마치 원래 형식에 속하는 것처럼 해당 메서드를 호출할 수 있는 별도 형식을 만들면 파생 클래스를 만들지 않고도 클래스를 “확장”할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-191">You can "extend" a class without creating a derived class by creating a separate type whose methods can be called as if they belonged to the original type.</span></span> <span data-ttu-id="82624-192">자세한 내용은 [확장 메서드](./extension-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-192">For more information, see [Extension Methods](./extension-methods.md).</span></span>  
  
## <a name="implicitly-typed-local-variables"></a><span data-ttu-id="82624-193">암시적으로 형식화한 지역 변수</span><span class="sxs-lookup"><span data-stu-id="82624-193">Implicitly Typed Local Variables</span></span>  

 <span data-ttu-id="82624-194">클래스 또는 구조체 메서드 내에서 암시적 형식 지정을 사용하여 컴파일러가 컴파일 타임에 올바른 형식을 결정하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-194">Within a class or struct method, you can use implicit typing to instruct the compiler to determine the correct type at compile time.</span></span> <span data-ttu-id="82624-195">자세한 내용은 [암시적으로 형식화된 지역 변수](./implicitly-typed-local-variables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-195">For more information, see [Implicitly Typed Local Variables](./implicitly-typed-local-variables.md).</span></span>  

## <a name="records"></a><span data-ttu-id="82624-196">레코드</span><span class="sxs-lookup"><span data-stu-id="82624-196">Records</span></span>

<span data-ttu-id="82624-197">C# 9에서는 클래스 또는 구조체 대신 만들 수 있는 참조 형식인 `record` 형식을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-197">C# 9 introduces the `record` type, a reference type that you can create instead of a class or a struct.</span></span> <span data-ttu-id="82624-198">레코드는 변경할 수 없는 형식으로 데이터를 캡슐화하기 위한 기본 제공 동작을 포함하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="82624-198">Records are classes with built-in behavior for encapsulating data in immutable types.</span></span> <span data-ttu-id="82624-199">레코드는 다음과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-199">A record provides the following features:</span></span>

* <span data-ttu-id="82624-200">변경할 수 없는 속성을 사용하여 참조 형식을 만드는 간결한 구문</span><span class="sxs-lookup"><span data-stu-id="82624-200">Concise syntax for creating a reference type with immutable properties.</span></span>

* <span data-ttu-id="82624-201">값 같음</span><span class="sxs-lookup"><span data-stu-id="82624-201">Value equality.</span></span>

  <span data-ttu-id="82624-202">레코드 종류의 두 변수는 레코드 종류 정의가 동일한 경우와 모든 필드에 대해 두 레코드의 값이 같은 경우에 같습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-202">Two variables of a record type are equal if the record type definitions are identical, and if for every field, the values in both records are equal.</span></span> <span data-ttu-id="82624-203">이는 참조 같음을 사용하는 클래스와 다릅니다. 후자의 경우 한 클래스 형식의 두 변수가 동일한 개체를 참조하면 두 변수가 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-203">This differs from classes, which use reference equality: two variables of a class type are equal if they refer to the same object.</span></span>

* <span data-ttu-id="82624-204">비파괴적 변형을 위한 간결한 구문</span><span class="sxs-lookup"><span data-stu-id="82624-204">Concise syntax for nondestructive mutation.</span></span>

  <span data-ttu-id="82624-205">`with` 식을 사용하면 기존 인스턴스의 복사본이지만 지정된 속성 값이 변경된 새 레코드 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82624-205">A `with` expression lets you create a new record instance that is a copy of an existing instance but with specified property values changed.</span></span>

* <span data-ttu-id="82624-206">표시를 위한 기본 제공 형식</span><span class="sxs-lookup"><span data-stu-id="82624-206">Built-in formatting for display.</span></span>

  <span data-ttu-id="82624-207">`ToString` 메서드는 레코드 형식 이름과 퍼블릭 속성의 이름 및 값을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="82624-207">The `ToString` method prints out the record type name and the names and values of public properties.</span></span>

* <span data-ttu-id="82624-208">상속 계층 구조 지원</span><span class="sxs-lookup"><span data-stu-id="82624-208">Support for inheritance hierarchies.</span></span>

  <span data-ttu-id="82624-209">레코드는 구조체가 아니라 커버 아래에 있는 클래스이므로 상속이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="82624-209">Inheritance is supported because a record is a class under the covers, not a struct.</span></span>

<span data-ttu-id="82624-210">자세한 내용은 [레코드](../../language-reference/builtin-types/record.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82624-210">For more information, see [Records](../../language-reference/builtin-types/record.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="82624-211">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="82624-211">C# Language Specification</span></span>  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="82624-212">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82624-212">See also</span></span>

- [<span data-ttu-id="82624-213">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="82624-213">C# Programming Guide</span></span>](../index.md)
