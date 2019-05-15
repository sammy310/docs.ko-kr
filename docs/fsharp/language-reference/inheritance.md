---
title: 상속
description: 지정 하는 방법을 알아봅니다 F# '상속' 키워드를 사용 하 여 상속 관계입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 2fad2ddafbc0174903d3d24be3ce5412f7e1f9ed
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641817"
---
# <a name="inheritance"></a><span data-ttu-id="92421-103">상속</span><span class="sxs-lookup"><span data-stu-id="92421-103">Inheritance</span></span>

<span data-ttu-id="92421-104">상속 "은-a" 관계를 모델링 하는 개체 지향 프로그래밍에서 동등 또는 합니다.</span><span class="sxs-lookup"><span data-stu-id="92421-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="92421-105">상속 관계를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="92421-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="92421-106">사용 하 여 상속 관계를 지정 합니다 `inherit` 클래스 선언에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="92421-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="92421-107">기본 구문 형식은 다음 예제에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92421-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="92421-108">클래스는 직접 기본 클래스는 최대 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92421-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="92421-109">기본 클래스를 지정 하지 않으면 사용 하 여 합니다 `inherit` 키워드를 클래스에서 암시적으로 상속 `System.Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="92421-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="92421-110">상속 된 멤버</span><span class="sxs-lookup"><span data-stu-id="92421-110">Inherited Members</span></span>

<span data-ttu-id="92421-111">클래스가 다른 클래스에서 상속 하는 경우 메서드 및 기본 클래스의 멤버는 파생된 클래스의 직접 멤버인 것 처럼 파생된 클래스의 사용자에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92421-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="92421-112">모든 let 바인딩 및 생성자 매개 변수는 클래스에 개인 따라서 파생된 클래스에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92421-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="92421-113">키워드 `base` 기본 클래스 인스턴스를 참조 하는 파생된 클래스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92421-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="92421-114">자체 식별자 처럼 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92421-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="92421-115">가상 메서드 및 재정의</span><span class="sxs-lookup"><span data-stu-id="92421-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="92421-116">가상 메서드 (및 속성)에서 약간 다르게 작동 F# 다른.NET 언어를 비교 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="92421-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="92421-117">새 가상 멤버를 선언 하려면 사용 된 `abstract` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="92421-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="92421-118">해당 메서드에 대 한 기본 구현을 제공 하는 여부에 관계 없이이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="92421-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="92421-119">따라서 기본 클래스에서 가상 메서드의 완료 정의이 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="92421-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="92421-120">및이 가상 메서드를 재정의 하는 파생된 클래스에서이 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="92421-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="92421-121">기본 클래스의 기본 구현은 생략 하면 기본 클래스는 추상 클래스를 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92421-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="92421-122">다음 코드 예제는 새 가상 메서드로 선언 `function1` 기본 클래스 및 파생된 클래스에서 재정의 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="92421-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="92421-123">생성자 및 상속</span><span class="sxs-lookup"><span data-stu-id="92421-123">Constructors and Inheritance</span></span>

<span data-ttu-id="92421-124">기본 클래스의 생성자는 파생된 클래스에서 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92421-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="92421-125">기본 클래스 생성자에 대 한 인수는 인수 목록에 표시 된 `inherit` 절.</span><span class="sxs-lookup"><span data-stu-id="92421-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="92421-126">파생된 클래스 생성자에 제공 된 인수에서 사용 되는 값을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92421-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="92421-127">다음 코드는 파생된 클래스는 상속 절에서 기본 클래스 생성자를 호출 하는 경우 기본 클래스 및 파생된 클래스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="92421-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="92421-128">생성자가 여러 개인 경우 다음 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92421-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="92421-129">파생된 클래스 생성자의 첫 번째 줄은는 `inherit` 절 및 필드를 사용 하 여 선언 된 필드를 명시적으로 표시 된 `val` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="92421-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="92421-130">자세한 내용은 참조 하세요. [명시적 필드: 합니다 `val` 키워드](members/explicit-fields-the-val-keyword.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92421-130">For more information, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="92421-131">상속에 대 한 대안</span><span class="sxs-lookup"><span data-stu-id="92421-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="92421-132">형식의 약간만 수정 하면 필요한 경우에서 상속 하는 대신 개체 식을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="92421-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="92421-133">다음 예제에서는 파생된 형식을 새로 만드는 대신 개체 식의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92421-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="92421-134">개체 식에 대 한 자세한 내용은 참조 하세요. [개체 식](object-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92421-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="92421-135">개체 계층 구조를 만들 때에 상속 하는 대신 구별된 된 공용 구조체를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="92421-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="92421-136">구별 된 공용 구조체는 전체 공용 형식을 공유 하는 다른 개체의 동작을 모델링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92421-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="92421-137">단일 구별 된 공용 구조체 파생된 클래스는 서로 조금씩 여러 필요가 종종 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92421-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="92421-138">구별 된 공용 구조체에 대 한 정보를 참조 하세요 [구별 된 공용 구조체](discriminated-unions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92421-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92421-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="92421-139">See also</span></span>

- [<span data-ttu-id="92421-140">개체 식</span><span class="sxs-lookup"><span data-stu-id="92421-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="92421-141">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="92421-141">F# Language Reference</span></span>](index.md)
