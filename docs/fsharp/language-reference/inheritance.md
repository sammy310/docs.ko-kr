---
title: 상속
description: "' Inherit ' 키워드를 사용 하 여 F # 상속 관계를 지정 하는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223846"
---
# <a name="inheritance"></a><span data-ttu-id="d8f45-103">상속</span><span class="sxs-lookup"><span data-stu-id="d8f45-103">Inheritance</span></span>

<span data-ttu-id="d8f45-104">상속은 개체 지향 프로그래밍에서 "is-a" 관계 또는 구성은을 모델링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="d8f45-105">상속 관계 지정</span><span class="sxs-lookup"><span data-stu-id="d8f45-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="d8f45-106">클래스 선언에서 키워드를 사용 하 여 상속 관계를 지정 `inherit` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="d8f45-107">다음 예제에서는 기본 구문 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="d8f45-108">클래스에는 직접 기본 클래스가 최대 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="d8f45-109">키워드를 사용 하 여 기본 클래스를 지정 하지 않는 경우 `inherit` 클래스는에서 암시적으로 상속 `System.Object` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="d8f45-110">상속된 멤버</span><span class="sxs-lookup"><span data-stu-id="d8f45-110">Inherited Members</span></span>

<span data-ttu-id="d8f45-111">클래스가 다른 클래스에서 상속 하는 경우 파생 클래스의 메서드 및 멤버를 파생 클래스의 직접 멤버인 것 처럼 파생 클래스의 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="d8f45-112">모든 let 바인딩과 생성자 매개 변수는 클래스에 전용 이므로 파생 클래스에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="d8f45-113">키워드는 `base` 파생 클래스에서 사용할 수 있으며 기본 클래스 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="d8f45-114">자체 식별자와 같이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="d8f45-115">가상 메서드 및 재정의</span><span class="sxs-lookup"><span data-stu-id="d8f45-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="d8f45-116">가상 메서드 (및 속성)는 다른 .NET 언어와 비교 하 여 F #에서 약간 다르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="d8f45-117">새 가상 멤버를 선언 하려면 키워드를 사용 `abstract` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="d8f45-118">해당 메서드에 대 한 기본 구현을 제공 하는지 여부에 관계 없이이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="d8f45-119">따라서 기본 클래스에서 가상 메서드의 전체 정의는 다음 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="d8f45-120">파생 된 클래스에서이 가상 메서드의 재정의는 다음 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="d8f45-121">기본 클래스에서 기본 구현을 생략 하면 기본 클래스는 추상 클래스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="d8f45-122">다음 코드 예제에서는 기본 클래스의 새 가상 메서드 선언과 `function1` 파생 클래스에서 재정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="d8f45-123">생성자 및 상속</span><span class="sxs-lookup"><span data-stu-id="d8f45-123">Constructors and Inheritance</span></span>

<span data-ttu-id="d8f45-124">기본 클래스에 대 한 생성자는 파생 클래스에서 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="d8f45-125">기본 클래스 생성자에 대 한 인수는 절의 인수 목록에 표시 `inherit` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="d8f45-126">사용 되는 값은 파생 클래스 생성자에 제공 된 인수에서 결정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="d8f45-127">다음 코드에서는 파생 클래스가 상속 절의 기본 클래스 생성자를 호출 하는 기본 클래스와 파생 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="d8f45-128">여러 생성자의 경우 다음 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="d8f45-129">파생 클래스 생성자의 첫 번째 줄은 절이 `inherit` 고, 필드는 키워드를 사용 하 여 선언 된 명시적 필드로 표시 됩니다 `val` .</span><span class="sxs-lookup"><span data-stu-id="d8f45-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="d8f45-130">자세한 내용은 [명시적 필드: `val` 키워드를](./members/explicit-fields-the-val-keyword.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f45-130">For more information, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="d8f45-131">상속의 대안</span><span class="sxs-lookup"><span data-stu-id="d8f45-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="d8f45-132">형식을 약간만 수정 해야 하는 경우에는 개체 식을 상속 대신 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="d8f45-133">다음 예에서는 새 파생 형식을 만드는 대신 개체 식을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="d8f45-134">개체 식에 대 한 자세한 내용은 [개체 식](object-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f45-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="d8f45-135">개체 계층 구조를 만들 때 상속 대신 구별 된 공용 구조체를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="d8f45-136">또한 구별 된 공용 구조체는 일반적인 전체 형식을 공유 하는 여러 개체의 다양 한 동작을 모델링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="d8f45-137">단일의 구별 된 공용 구조체는 서로 조금씩 변형 된 여러 파생 클래스의 필요성을 없앨 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f45-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="d8f45-138">구별 된 공용 구조체에 대 한 자세한 내용은 [구별 된 공용 구조체](discriminated-unions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f45-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d8f45-139">참조</span><span class="sxs-lookup"><span data-stu-id="d8f45-139">See also</span></span>

- [<span data-ttu-id="d8f45-140">개체 식</span><span class="sxs-lookup"><span data-stu-id="d8f45-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="d8f45-141">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="d8f45-141">F# Language Reference</span></span>](index.md)
