---
title: 인터페이스
description: 'F # 인터페이스가 다른 클래스에서 구현 하는 관련 멤버의 집합을 지정 하는 방법에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 0cef2932045dae401f5aa069107815543457ca4a
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557053"
---
# <a name="interfaces"></a><span data-ttu-id="167bb-103">인터페이스</span><span class="sxs-lookup"><span data-stu-id="167bb-103">Interfaces</span></span>

<span data-ttu-id="167bb-104">*인터페이스* 는 다른 클래스에서 구현 하는 관련 멤버의 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="167bb-105">구문</span><span class="sxs-lookup"><span data-stu-id="167bb-105">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a><span data-ttu-id="167bb-106">설명</span><span class="sxs-lookup"><span data-stu-id="167bb-106">Remarks</span></span>

<span data-ttu-id="167bb-107">인터페이스 선언은 멤버가 구현 되지 않는다는 점을 제외 하 고 클래스 선언과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="167bb-108">대신 모든 멤버는 키워드에 의해 표시 된 대로 추상적 `abstract` 입니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="167bb-109">추상 메서드에는 메서드 본문을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="167bb-110">그러나 키워드와 함께 멤버의 개별 정의를 메서드로 포함 하 여 기본 구현을 제공할 수도 있습니다 `default` .</span><span class="sxs-lookup"><span data-stu-id="167bb-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="167bb-111">이렇게 하려면 다른 .NET 언어의 기본 클래스에서 가상 메서드를 만드는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="167bb-112">이러한 가상 메서드는 인터페이스를 구현 하는 클래스에서 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="167bb-113">인터페이스에 대 한 기본 액세스 가능성은 `public` 입니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="167bb-114">필요에 따라 일반 F # 구문을 사용 하 여 각 메서드 매개 변수에 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="167bb-115">위의 예제에서 `ISprintable` `Print` 메서드에는 이름이 인 형식의 단일 매개 변수가 있습니다 `string` `format` .</span><span class="sxs-lookup"><span data-stu-id="167bb-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="167bb-116">인터페이스를 구현 하는 방법에는 개체 식 사용, 클래스 형식 사용 등 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="167bb-117">두 경우 모두 클래스 형식 또는 개체 식은 인터페이스의 추상 메서드에 대 한 메서드 본문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="167bb-118">구현은 인터페이스를 구현 하는 각 형식에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="167bb-119">따라서 다른 형식에 대 한 인터페이스 메서드는 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="167bb-120">`interface` `end` 간단한 구문을 사용 하는 경우 정의의 시작과 끝을 표시 하는 및 키워드는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="167bb-121">이러한 키워드를 사용 하지 않는 경우 컴파일러는 사용 하는 구문을 분석 하 여 형식이 클래스 인지 또는 인터페이스 인지를 유추 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="167bb-122">멤버를 정의 하거나 다른 클래스 구문을 사용 하는 경우 형식은 클래스로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="167bb-123">.NET 코딩 스타일은 모든 인터페이스를 대문자로 시작 하는 것입니다 `I` .</span><span class="sxs-lookup"><span data-stu-id="167bb-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

<span data-ttu-id="167bb-124">여러 매개 변수를 두 가지 방법으로 지정할 수 있습니다. F # 스타일 및입니다. NET 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-124">You can specify multiple parameters in two ways: F#-style and .NET-style.</span></span> <span data-ttu-id="167bb-125">둘 다 .NET 소비자에 대해 동일한 방식으로 컴파일되지만 f # 스타일은 f # 스타일 매개 변수 응용 프로그램 및를 사용 하도록 합니다. NET 스타일은 F # 호출자가 튜플 인수 응용 프로그램을 사용 하도록 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-125">Both will compile the same way for .NET consumers, but F#-style will force F# callers to use F#-style parameter application and .NET-style will force F# callers to use tupled argument application.</span></span>

```fsharp
type INumeric1 =
    abstract Add: x: int -> y: int -> int

type INumeric2 =
    abstract Add: x: int * y: int -> int
```

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="167bb-126">클래스 형식을 사용 하 여 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="167bb-126">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="167bb-127">`interface`다음 코드에 표시 된 것 처럼 키워드, 인터페이스 이름 및 키워드를 사용 하 여 클래스 형식에서 하나 이상의 인터페이스를 구현 하 고 인터페이스 멤버 정의를 구현할 수 있습니다 `with` .</span><span class="sxs-lookup"><span data-stu-id="167bb-127">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="167bb-128">인터페이스 구현은 상속 되므로 파생 된 클래스는이를 다시 구현할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-128">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="167bb-129">인터페이스 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="167bb-129">Calling Interface Methods</span></span>

<span data-ttu-id="167bb-130">인터페이스 메서드는 인터페이스를 통해 인터페이스를 구현 하는 형식의 개체를 통해 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-130">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="167bb-131">따라서 `:>` 이러한 메서드를 호출 하려면 연산자 또는 연산자를 사용 하 여 인터페이스 형식으로 업 캐스트 할 수 있습니다 `upcast` .</span><span class="sxs-lookup"><span data-stu-id="167bb-131">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="167bb-132">형식의 개체가 있을 때 인터페이스 메서드를 호출 하려면 `SomeClass` 다음 코드와 같이 개체를 인터페이스 형식에 업 캐스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-132">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="167bb-133">다른 방법은 다음 예제와 같이 업캐스팅 하 고 인터페이스 메서드를 호출 하는 개체에 대 한 메서드를 선언 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-133">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="167bb-134">개체 식을 사용 하 여 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="167bb-134">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="167bb-135">개체 식은 인터페이스를 구현 하는 간단한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-135">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="167bb-136">명명 된 형식을 만들 필요가 없고 인터페이스 메서드를 지 원하는 개체를 추가 메서드 없이 사용 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-136">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="167bb-137">다음 코드에서는 개체 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-137">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="167bb-138">인터페이스 상속</span><span class="sxs-lookup"><span data-stu-id="167bb-138">Interface Inheritance</span></span>

<span data-ttu-id="167bb-139">인터페이스는 하나 이상의 기본 인터페이스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-139">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="implementing-interfaces-with-default-implementations"></a><span data-ttu-id="167bb-140">기본 구현을 사용 하 여 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="167bb-140">Implementing interfaces with default implementations</span></span>

<span data-ttu-id="167bb-141">C #은 다음과 같이 기본 구현으로 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-141">C# supports defining interfaces with default implementations, like so:</span></span>

```csharp
using System;

namespace CSharp
{
    public interface MyDim
    {
        public int Z => 0;
    }
}
```

<span data-ttu-id="167bb-142">F #에서 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-142">These are directly consumable from F#:</span></span>

```fsharp
open CSharp

// You can implement the interface via a class
type MyType() =
    member _.M() = ()

    interface MyDim

let md = MyType() :> MyDim
printfn $"DIM from C#: %d{md.Z}"

// You can also implement it via an object expression
let md' = { new MyDim }
printfn $"DIM from C# but via Object Expression: %d{md'.Z}"
```

<span data-ttu-id="167bb-143">가상 멤버 재정의와 같이를 사용 하 여 기본 구현을 재정의할 수 있습니다 `override` .</span><span class="sxs-lookup"><span data-stu-id="167bb-143">You can override a default implementation with `override`, like overriding any virtual member.</span></span>

<span data-ttu-id="167bb-144">기본 구현이 없는 인터페이스의 멤버는 여전히 명시적으로 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-144">Any members in an interface that do not have a default implementation must still be explicitly implemented.</span></span>

## <a name="implementing-the-same-interface-at-different-generic-instantiations"></a><span data-ttu-id="167bb-145">서로 다른 제네릭 인스턴스화에 동일한 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="167bb-145">Implementing the same interface at different generic instantiations</span></span>

<span data-ttu-id="167bb-146">F #에서는 다음과 같이 서로 다른 제네릭 인스턴스화에 동일한 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="167bb-146">F# supports implementing the same interface at different generic instantiations like so:</span></span>

```fsharp
type IA<'T> =
    abstract member Get : unit -> 'T

type MyClass() =
    interface IA<int> with
        member x.Get() = 1
    interface IA<string> with
        member x.Get() = "hello"

let mc = MyClass()
let iaInt = mc :> IA<int>
let iaString = mc :> IA<string>

iaInt.Get() // 1
iaString.Get() // "hello"
```

## <a name="see-also"></a><span data-ttu-id="167bb-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="167bb-147">See also</span></span>

- [<span data-ttu-id="167bb-148">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="167bb-148">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="167bb-149">개체 식</span><span class="sxs-lookup"><span data-stu-id="167bb-149">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="167bb-150">클래스</span><span class="sxs-lookup"><span data-stu-id="167bb-150">Classes</span></span>](classes.md)
