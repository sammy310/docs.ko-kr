---
title: 인터페이스
description: 'F # 인터페이스가 다른 클래스에서 구현 하는 관련 멤버의 집합을 지정 하는 방법에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 36272b52fcff83e8e8a54ccc4e6ecd1252a91819
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558129"
---
# <a name="interfaces"></a><span data-ttu-id="3f40b-103">인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f40b-103">Interfaces</span></span>

<span data-ttu-id="3f40b-104">*인터페이스* 는 다른 클래스에서 구현 하는 관련 멤버의 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="3f40b-105">구문</span><span class="sxs-lookup"><span data-stu-id="3f40b-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="3f40b-106">설명</span><span class="sxs-lookup"><span data-stu-id="3f40b-106">Remarks</span></span>

<span data-ttu-id="3f40b-107">인터페이스 선언은 멤버가 구현 되지 않는다는 점을 제외 하 고 클래스 선언과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="3f40b-108">대신 모든 멤버는 키워드에 의해 표시 된 대로 추상적 `abstract` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="3f40b-109">추상 메서드에는 메서드 본문을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="3f40b-110">그러나 키워드와 함께 멤버의 개별 정의를 메서드로 포함 하 여 기본 구현을 제공할 수도 있습니다 `default` .</span><span class="sxs-lookup"><span data-stu-id="3f40b-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="3f40b-111">이렇게 하려면 다른 .NET 언어의 기본 클래스에서 가상 메서드를 만드는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="3f40b-112">이러한 가상 메서드는 인터페이스를 구현 하는 클래스에서 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="3f40b-113">인터페이스에 대 한 기본 액세스 가능성은 `public` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="3f40b-114">필요에 따라 일반 F # 구문을 사용 하 여 각 메서드 매개 변수에 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="3f40b-115">위의 예제에서 `ISprintable` `Print` 메서드에는 이름이 인 형식의 단일 매개 변수가 있습니다 `string` `format` .</span><span class="sxs-lookup"><span data-stu-id="3f40b-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="3f40b-116">인터페이스를 구현 하는 방법에는 개체 식 사용, 클래스 형식 사용 등 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="3f40b-117">두 경우 모두 클래스 형식 또는 개체 식은 인터페이스의 추상 메서드에 대 한 메서드 본문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="3f40b-118">구현은 인터페이스를 구현 하는 각 형식에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="3f40b-119">따라서 다른 형식에 대 한 인터페이스 메서드는 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="3f40b-120">`interface` `end` 간단한 구문을 사용 하는 경우 정의의 시작과 끝을 표시 하는 및 키워드는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="3f40b-121">이러한 키워드를 사용 하지 않는 경우 컴파일러는 사용 하는 구문을 분석 하 여 형식이 클래스 인지 또는 인터페이스 인지를 유추 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="3f40b-122">멤버를 정의 하거나 다른 클래스 구문을 사용 하는 경우 형식은 클래스로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="3f40b-123">.NET 코딩 스타일은 모든 인터페이스를 대문자로 시작 하는 것입니다 `I` .</span><span class="sxs-lookup"><span data-stu-id="3f40b-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

<span data-ttu-id="3f40b-124">여러 매개 변수를 두 가지 방법으로 지정할 수 있습니다. F # 스타일 및입니다. NET 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-124">You can specify multiple parameters in two ways: F#-style and .NET-style.</span></span> <span data-ttu-id="3f40b-125">둘 다 .NET 소비자에 대해 동일한 방식으로 컴파일되지만 f # 스타일은 f # 스타일 매개 변수 응용 프로그램 및를 사용 하도록 합니다. NET 스타일은 F # 호출자가 튜플 인수 응용 프로그램을 사용 하도록 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-125">Both will compile the same way for .NET consumers, but F#-style will force F# callers to use F#-style parameter application and .NET-style will force F# callers to use tupled argument application.</span></span>

```fsharp
type INumeric1 =
    abstract Add: x: int -> y: int -> int

type INumeric2 =
    abstract Add: x: int * y: int -> int
```

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="3f40b-126">클래스 형식을 사용 하 여 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="3f40b-126">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="3f40b-127">`interface`다음 코드에 표시 된 것 처럼 키워드, 인터페이스 이름 및 키워드를 사용 하 여 클래스 형식에서 하나 이상의 인터페이스를 구현 하 고 인터페이스 멤버 정의를 구현할 수 있습니다 `with` .</span><span class="sxs-lookup"><span data-stu-id="3f40b-127">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="3f40b-128">인터페이스 구현은 상속 되므로 파생 된 클래스는이를 다시 구현할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-128">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="3f40b-129">인터페이스 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="3f40b-129">Calling Interface Methods</span></span>

<span data-ttu-id="3f40b-130">인터페이스 메서드는 인터페이스를 통해 인터페이스를 구현 하는 형식의 개체를 통해 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-130">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="3f40b-131">따라서 `:>` 이러한 메서드를 호출 하려면 연산자 또는 연산자를 사용 하 여 인터페이스 형식으로 업 캐스트 할 수 있습니다 `upcast` .</span><span class="sxs-lookup"><span data-stu-id="3f40b-131">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="3f40b-132">형식의 개체가 있을 때 인터페이스 메서드를 호출 하려면 `SomeClass` 다음 코드와 같이 개체를 인터페이스 형식에 업 캐스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-132">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="3f40b-133">다른 방법은 다음 예제와 같이 업캐스팅 하 고 인터페이스 메서드를 호출 하는 개체에 대 한 메서드를 선언 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-133">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="3f40b-134">개체 식을 사용 하 여 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="3f40b-134">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="3f40b-135">개체 식은 인터페이스를 구현 하는 간단한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-135">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="3f40b-136">명명 된 형식을 만들 필요가 없고 인터페이스 메서드를 지 원하는 개체를 추가 메서드 없이 사용 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-136">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="3f40b-137">다음 코드에서는 개체 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-137">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="3f40b-138">인터페이스 상속</span><span class="sxs-lookup"><span data-stu-id="3f40b-138">Interface Inheritance</span></span>

<span data-ttu-id="3f40b-139">인터페이스는 하나 이상의 기본 인터페이스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f40b-139">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="3f40b-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f40b-140">See also</span></span>

- [<span data-ttu-id="3f40b-141">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="3f40b-141">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="3f40b-142">개체 식</span><span class="sxs-lookup"><span data-stu-id="3f40b-142">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="3f40b-143">클래스</span><span class="sxs-lookup"><span data-stu-id="3f40b-143">Classes</span></span>](classes.md)
