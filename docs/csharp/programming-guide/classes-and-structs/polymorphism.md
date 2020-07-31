---
title: 다형성 - C# 프로그래밍 가이드
description: 기본 및 파생 클래스 간의 관계를 설명하는 C#과 같은 개체 지향 프로그래밍 언어의 핵심 개념인 다형성에 대해 알아봅니다.
ms.date: 02/08/2020
helpviewer_keywords:
- C# language, polymorphism
- polymorphism [C#]
ms.assetid: 086af969-29a5-4ce8-a993-0b7d53839dab
ms.openlocfilehash: 59b5f5d2d5a8f274845607aeca370c316670bd68
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925451"
---
# <a name="polymorphism-c-programming-guide"></a><span data-ttu-id="b8722-103">다형성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b8722-103">Polymorphism (C# Programming Guide)</span></span>

<span data-ttu-id="b8722-104">다형성은 흔히 캡슐화와 상속의 뒤를 이어 개체 지향 프로그래밍의 세 번째 특징으로 일컬어집니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-104">Polymorphism is often referred to as the third pillar of object-oriented programming, after encapsulation and inheritance.</span></span> <span data-ttu-id="b8722-105">다형성은 "여러 형태"를 의미하는 그리스어 단어이며 다음과 같은 두 가지 고유한 측면을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-105">Polymorphism is a Greek word that means "many-shaped" and it has two distinct aspects:</span></span>
  
- <span data-ttu-id="b8722-106">런타임에 파생 클래스의 개체가 메서드 매개 변수 및 컬렉션 또는 배열과 같은 위치에서 기본 클래스의 개체로 처리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-106">At run time, objects of a derived class may be treated as objects of a base class in places such as method parameters and collections or arrays.</span></span> <span data-ttu-id="b8722-107">이러한 다형성이 발생하면 개체의 선언된 형식이 더 이상 해당 런타임 형식과 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-107">When this polymorphism occurs, the object's declared type is no longer identical to its run-time type.</span></span>
- <span data-ttu-id="b8722-108">기본 클래스는 [가상](../../language-reference/keywords/virtual.md) *메서드*를 정의 및 구현할 수 있으며, 파생 클래스는 이러한 가상 메서드를 [재정의](../../language-reference/keywords/override.md)할 수 있습니다. 즉, 파생 클래스는 고유한 정의 및 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-108">Base classes may define and implement [virtual](../../language-reference/keywords/virtual.md) *methods*, and derived classes can [override](../../language-reference/keywords/override.md) them, which means they provide their own definition and implementation.</span></span> <span data-ttu-id="b8722-109">런타임에 클라이언트 코드에서 메서드를 호출하면 CLR은 개체의 런타임 형식을 조회하고 가상 메서드의 해당 재정의를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-109">At run-time, when client code calls the method, the CLR looks up the run-time type of the object, and invokes that override of the virtual method.</span></span> <span data-ttu-id="b8722-110">소스 코드에서 기본 클래스에 대해 메서드를 호출하여 메서드의 파생 클래스 버전이 실행되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-110">In your source code you can call a method on a base class, and cause a derived class's version of the method to be executed.</span></span>

<span data-ttu-id="b8722-111">가상 메서드를 사용하면 동일한 방식으로 관련 개체 그룹에 대한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-111">Virtual methods enable you to work with groups of related objects in a uniform way.</span></span> <span data-ttu-id="b8722-112">예를 들어, 사용자가 그리기 화면에서 다양한 종류의 도형을 만들 수 있는 그리기 애플리케이션이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-112">For example, suppose you have a drawing application that enables a user to create various kinds of shapes on a drawing surface.</span></span> <span data-ttu-id="b8722-113">컴파일 타임에는 사용자가 어떤 특정 형식의 도형을 만들지 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-113">You do not know at compile time which specific types of shapes the user will create.</span></span> <span data-ttu-id="b8722-114">그러나 애플리케이션은 만들어지는 다양한 모든 형식의 도형을 추적해야 하며, 사용자의 마우스 작업에 따라 이러한 도형을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-114">However, the application has to keep track of all the various types of shapes that are created, and it has to update them in response to user mouse actions.</span></span> <span data-ttu-id="b8722-115">다음과 같은 기본 두 단계로 다형성을 사용하여 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-115">You can use polymorphism to solve this problem in two basic steps:</span></span>

1. <span data-ttu-id="b8722-116">각 특정 도형 클래스가 공통 기본 클래스에서 파생되는 클래스 계층 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-116">Create a class hierarchy in which each specific shape class derives from a common base class.</span></span>
1. <span data-ttu-id="b8722-117">가상 메서드를 사용하여 기본 클래스 메서드에 대한 단일 호출을 통해 모든 파생 클래스에 대해 적절한 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-117">Use a virtual method to invoke the appropriate method on any derived class through a single call to the base class method.</span></span>

<span data-ttu-id="b8722-118">먼저, `Shape`라는 기본 클래스를 만들고 `Rectangle`, `Circle` 및 `Triangle`과 같은 파생 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-118">First, create a base class called `Shape`, and derived classes such as `Rectangle`, `Circle`, and `Triangle`.</span></span> <span data-ttu-id="b8722-119">`Shape` 클래스에 `Draw`라는 가상 메서드를 제공하고, 각 파생 클래스에서 이를 재정의하여 클래스가 나타내는 특정 도형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-119">Give the `Shape` class a virtual method called `Draw`, and override it in each derived class to draw the particular shape that the class represents.</span></span> <span data-ttu-id="b8722-120">`List<Shape>` 개체를 만들고 이 개체에 `Circle`, `Triangle`및 `Rectangle`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-120">Create a `List<Shape>` object and add a `Circle`, `Triangle`, and `Rectangle` to it.</span></span>

[!code-csharp[Polymorphism overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#PolymorphismOverview)]

<span data-ttu-id="b8722-121">그리기 화면을 업데이트하려면 [foreach](../../language-reference/keywords/foreach-in.md) 루프를 사용하여 목록을 반복하고 목록의 각 `Shape` 개체에 대해 `Draw` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-121">To update the drawing surface, use a [foreach](../../language-reference/keywords/foreach-in.md) loop to iterate through the list and call the `Draw` method on each `Shape` object in the list.</span></span> <span data-ttu-id="b8722-122">목록의 각 개체에 선언된 형식 `Shape`가 있더라도 이는 호출될 런타임 형식(각 파생 클래스에 있는 메서드의 재정의된 버전)입니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-122">Even though each object in the list has a declared type of `Shape`, it's the run-time type (the overridden version of the method in each derived class) that will be invoked.</span></span>

[!code-csharp[Polymorphism overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#UsePolymorphism)]

<span data-ttu-id="b8722-123">C#에서 모든 형식은 사용자 정의 형식을 포함한 모든 형식이 <xref:System.Object>에서 파생되므로 다형 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-123">In C#, every type is polymorphic because all types, including user-defined types, inherit from <xref:System.Object>.</span></span>  

## <a name="polymorphism-overview"></a><span data-ttu-id="b8722-124">다형성 개요</span><span class="sxs-lookup"><span data-stu-id="b8722-124">Polymorphism overview</span></span>

### <a name="virtual-members"></a><span data-ttu-id="b8722-125">가상 멤버</span><span class="sxs-lookup"><span data-stu-id="b8722-125">Virtual members</span></span>

<span data-ttu-id="b8722-126">기본 클래스에서 파생 클래스가 상속되면 파생 클래스는 기본 클래스의 모든 메서드, 필드, 속성 및 이벤트를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-126">When a derived class inherits from a base class, it gains all the methods, fields, properties, and events of the base class.</span></span> <span data-ttu-id="b8722-127">파생 클래스의 디자이너는 가상 메서드의 동작에 대한 다양한 선택 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-127">The designer of the derived class has different choices for the behavior of virtual methods:</span></span>

- <span data-ttu-id="b8722-128">파생 클래스가 기본 클래스의 가상 멤버를 재정의하여 새로운 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-128">The derived class may override virtual members in the base class, defining new behavior.</span></span>
- <span data-ttu-id="b8722-129">파생 클래스가 가장 가까운 기본 클래스 메서드를 재정의하지 않고 상속하여 기존 동작은 보존하되 다른 파생 클래스가 해당 메서드를 재정의할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-129">The derived class inherit the closest base class method without overriding it, preserving the existing behavior but enabling further derived classes to override the method.</span></span>
- <span data-ttu-id="b8722-130">파생 클래스가 기본 클래스 구현을 숨기는 멤버의 새로운 비가상 구현을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-130">The derived class may define new non-virtual implementation of those members that hide the base class implementations.</span></span>

<span data-ttu-id="b8722-131">파생 클래스는 기본 클래스 멤버가 [virtual](../../language-reference/keywords/virtual.md) 또는 [abstract](../../language-reference/keywords/abstract.md)로 선언된 경우에만 기본 클래스 멤버를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-131">A derived class can override a base class member only if the base class member is declared as [virtual](../../language-reference/keywords/virtual.md) or [abstract](../../language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="b8722-132">파생 멤버는 [override](../../language-reference/keywords/override.md) 키워드를 사용하여 메서드가 가상 호출에 참여하도록 되어 있음을 명시적으로 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-132">The derived member must use the [override](../../language-reference/keywords/override.md) keyword to explicitly indicate that the method is intended to participate in virtual invocation.</span></span> <span data-ttu-id="b8722-133">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-133">The following code provides an example:</span></span>

[!code-csharp[Virtual overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#VirtualMethods)]

<span data-ttu-id="b8722-134">필드는 가상일 수 없습니다. 메서드, 속성, 이벤트 및 인덱서만 가상일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-134">Fields cannot be virtual; only methods, properties, events, and indexers can be virtual.</span></span> <span data-ttu-id="b8722-135">파생 클래스가 가상 멤버를 재정의하면 해당 멤버는 해당 클래스의 인스턴스가 기본 클래스의 인스턴스로 액세스되는 경우에도 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-135">When a derived class overrides a virtual member, that member is called even when an instance of that class is being accessed as an instance of the base class.</span></span> <span data-ttu-id="b8722-136">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-136">The following code provides an example:</span></span>

[!code-csharp[Virtual overview example](~/samples/snippets/csharp/objectoriented/Inheritance.cs#SnippetTestVirtualMethods)]

<span data-ttu-id="b8722-137">가상 메서드 및 속성을 통해 파생 클래스는 메서드의 기본 클래스 구현을 사용할 필요 없이 기본 클래스를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-137">Virtual methods and properties enable derived classes to extend a base class without needing to use the base class implementation of a method.</span></span> <span data-ttu-id="b8722-138">자세한 내용은 [Override 및 New 키워드를 사용하여 버전 관리](./versioning-with-the-override-and-new-keywords.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8722-138">For more information, see [Versioning with the Override and New Keywords](./versioning-with-the-override-and-new-keywords.md).</span></span> <span data-ttu-id="b8722-139">인터페이스는 구현이 파생 클래스에 남겨진 메서드 또는 메서드 집합을 정의하는 또 다른 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-139">An interface provides another way to define a method or set of methods whose implementation is left to derived classes.</span></span> <span data-ttu-id="b8722-140">자세한 내용은 [인터페이스](../interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8722-140">For more information, see [Interfaces](../interfaces/index.md).</span></span>

### <a name="hide-base-class-members-with-new-members"></a><span data-ttu-id="b8722-141">새 멤버로 기본 클래스 멤버 숨기기</span><span class="sxs-lookup"><span data-stu-id="b8722-141">Hide base class members with new members</span></span>

<span data-ttu-id="b8722-142">파생 클래스가 기본 클래스의 멤버와 동일한 이름을 갖는 멤버를 갖도록 하려면 [new](../../language-reference/keywords/new-modifier.md) 키워드를 사용하여 기본 클래스 멤버를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-142">If you want your derived class to have a member with the same name as a member in a base class, you can use the [new](../../language-reference/keywords/new-modifier.md) keyword to hide the base class member.</span></span> <span data-ttu-id="b8722-143">`new` 키워드는 바꿀 클래스 멤버의 반환 형식 앞에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-143">The `new` keyword is put before the return type of a class member that is being replaced.</span></span> <span data-ttu-id="b8722-144">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-144">The following code provides an example:</span></span>

[!code-csharp[New method overview example](~/samples/snippets/csharp/objectoriented/Inheritance.cs#NewMethods)]

<span data-ttu-id="b8722-145">파생 클래스의 인스턴스를 기본 클래스의 인스턴스로 캐스팅하여 숨겨진 기본 클래스 멤버를 클라이언트 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-145">Hidden base class members may be accessed from client code by casting the instance of the derived class to an instance of the base class.</span></span> <span data-ttu-id="b8722-146">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="b8722-146">For example:</span></span>

[!code-csharp[New method overview usage](~/samples/snippets/csharp/objectoriented/Inheritance.cs#UseNewMethods)]

### <a name="prevent-derived-classes-from-overriding-virtual-members"></a><span data-ttu-id="b8722-147">파생 클래스가 가상 멤버를 재정의하지 못하도록 설정</span><span class="sxs-lookup"><span data-stu-id="b8722-147">Prevent derived classes from overriding virtual members</span></span>  

<span data-ttu-id="b8722-148">가상 멤버는 가상 멤버와 원래 가상 멤버를 선언한 클래스에서 선언된 클래스의 개수와 관계없이 가상으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-148">Virtual members remain virtual, regardless of how many classes have been declared between the virtual member and the class that originally declared it.</span></span> <span data-ttu-id="b8722-149">클래스 `A`가 가상 멤버를 선언하고, 클래스 `B`가 `A`에서 파생되며, 클래스 `C`가 `B`에서 파생되면 클래스 `C`는 클래스 `B`가 해당 멤버에 대한 재정의를 선언했는지 여부와 관계없이 가상 멤버를 상속하며, 해당 가상 멤버를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-149">If class `A` declares a virtual member, and class `B` derives from `A`, and class `C` derives from `B`, class `C` inherits the virtual member, and may override it, regardless of whether class `B` declared an override for that member.</span></span> <span data-ttu-id="b8722-150">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-150">The following code provides an example:</span></span>

[!code-csharp[Basic hierarchy](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#FirstHierarchy)]

<span data-ttu-id="b8722-151">파생 클래스는 재정의를 [sealed](../../language-reference/keywords/sealed.md)로 선언하여 가상 상속을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-151">A derived class can stop virtual inheritance by declaring an override as [sealed](../../language-reference/keywords/sealed.md).</span></span> <span data-ttu-id="b8722-152">가상 상속을 중지하려면 클래스 멤버 선언에서 `override` 키워드 앞에 `sealed` 키워드를 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-152">Stopping inheritance requires putting the `sealed` keyword before the `override` keyword in the class member declaration.</span></span> <span data-ttu-id="b8722-153">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-153">The following code provides an example:</span></span>

[!code-csharp[A sealed overridden member](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#SealedOverride)]

<span data-ttu-id="b8722-154">앞의 예제에서 `DoWork` 메서드는 `C`에서 파생된 모든 클래스에 대해 더 이상 가상이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-154">In the previous example, the method `DoWork` is no longer virtual to any class derived from `C`.</span></span> <span data-ttu-id="b8722-155">그러나 이 메서드는 `C`의 인스턴스가 형식 `B` 또는 형식 `A`로 캐스팅되더라도 여전히 C의 인스턴스에 대해서는 가상입니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-155">It's still virtual for instances of `C`, even if they're cast to type `B` or type `A`.</span></span> <span data-ttu-id="b8722-156">sealed 메서드는 다음 예제에서처럼 `new` 키워드를 사용하여 파생 클래스로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-156">Sealed methods can be replaced by derived classes by using the `new` keyword, as the following example shows:</span></span>

[!code-csharp[New method declaration](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#NewDeclaration)]

<span data-ttu-id="b8722-157">이 경우 형식 `D` 변수를 사용하여 `D`에 대해 `DoWork`을 호출하면 새 `DoWork`가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-157">In this case, if `DoWork` is called on `D` using a variable of type `D`, the new `DoWork` is called.</span></span> <span data-ttu-id="b8722-158">형식 `C`, `B` 또는 `A` 변수를 사용하여 `D`의 인스턴스에 액세스하면 `DoWork`에 대한 호출은 가상 상속의 규칙을 따라 해당 호출을 클래스 `C`에 대한 `DoWork`의 구현으로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-158">If a variable of type `C`, `B`, or `A` is used to access an instance of `D`, a call to `DoWork` will follow the rules of virtual inheritance, routing those calls to the implementation of `DoWork` on class `C`.</span></span>

### <a name="access-base-class-virtual-members-from-derived-classes"></a><span data-ttu-id="b8722-159">파생 클래스에서 기본 클래스 가상 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="b8722-159">Access base class virtual members from derived classes</span></span>

<span data-ttu-id="b8722-160">메서드 또는 속성을 바꾸었거나 재정의한 파생 클래스는 계속해서 `base` 키워드를 사용하여 기본 클래스에 대한 메서드 또는 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-160">A derived class that has replaced or overridden a method or property can still access the method or property on the base class using the `base` keyword.</span></span> <span data-ttu-id="b8722-161">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-161">The following code provides an example:</span></span>

```csharp
public class Base
{
    public virtual void DoWork() {/*...*/ }
}
public class Derived : Base
{
    public override void DoWork()
    {
        //Perform Derived's work here
        //...
        // Call DoWork on base class
        base.DoWork();
    }
}
```

<span data-ttu-id="b8722-162">자세한 내용은 [base](../../language-reference/keywords/base.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8722-162">For more information, see [base](../../language-reference/keywords/base.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b8722-163">가상 멤버는 `base`를 사용하여 자체 구현에서 해당 멤버의 기본 클래스 구현을 호출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-163">It is recommended that virtual members use `base` to call the base class implementation of that member in their own implementation.</span></span> <span data-ttu-id="b8722-164">기본 클래스 동작이 발생하도록 하면 파생 클래스가 파생 클래스에 대한 동작 구현에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-164">Letting the base class behavior occur enables the derived class to concentrate on implementing behavior specific to the derived class.</span></span> <span data-ttu-id="b8722-165">기본 클래스 구현이 호출되지 않는 경우 해당 동작이 기본 클래스의 동작과 호환되도록 하는 것은 파생 클래스의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="b8722-165">If the base class implementation is not called, it is up to the derived class to make their behavior compatible with the behavior of the base class.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b8722-166">단원 내용</span><span class="sxs-lookup"><span data-stu-id="b8722-166">In this section</span></span>

- [<span data-ttu-id="b8722-167">Override 및 New 키워드를 사용하여 버전 관리</span><span class="sxs-lookup"><span data-stu-id="b8722-167">Versioning with the Override and New Keywords</span></span>](./versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="b8722-168">Override 및 New 키워드를 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="b8722-168">Knowing When to Use Override and New Keywords</span></span>](./knowing-when-to-use-override-and-new-keywords.md)
- [<span data-ttu-id="b8722-169">ToString 메서드 재정의 방법</span><span class="sxs-lookup"><span data-stu-id="b8722-169">How to override the ToString method</span></span>](./how-to-override-the-tostring-method.md)

## <a name="see-also"></a><span data-ttu-id="b8722-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8722-170">See also</span></span>

- [<span data-ttu-id="b8722-171">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b8722-171">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b8722-172">상속</span><span class="sxs-lookup"><span data-stu-id="b8722-172">Inheritance</span></span>](./inheritance.md)
- [<span data-ttu-id="b8722-173">추상/봉인된 클래스 및 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="b8722-173">Abstract and Sealed Classes and Class Members</span></span>](./abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="b8722-174">메서드</span><span class="sxs-lookup"><span data-stu-id="b8722-174">Methods</span></span>](./methods.md)
- [<span data-ttu-id="b8722-175">이벤트</span><span class="sxs-lookup"><span data-stu-id="b8722-175">Events</span></span>](../events/index.md)
- [<span data-ttu-id="b8722-176">속성</span><span class="sxs-lookup"><span data-stu-id="b8722-176">Properties</span></span>](./properties.md)
- [<span data-ttu-id="b8722-177">인덱서</span><span class="sxs-lookup"><span data-stu-id="b8722-177">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="b8722-178">형식</span><span class="sxs-lookup"><span data-stu-id="b8722-178">Types</span></span>](../types/index.md)
