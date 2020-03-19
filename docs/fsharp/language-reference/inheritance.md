---
title: 상속
description: "'상속' 키워드를 사용하여 F# 상속 관계를 지정하는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401132"
---
# <a name="inheritance"></a><span data-ttu-id="f985b-103">상속</span><span class="sxs-lookup"><span data-stu-id="f985b-103">Inheritance</span></span>

<span data-ttu-id="f985b-104">상속은 개체 지향 프로그래밍에서 "is-a" 관계 또는 하위 타이핑을 모델링하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="f985b-105">상속 관계 지정</span><span class="sxs-lookup"><span data-stu-id="f985b-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="f985b-106">클래스 선언에서 키워드를 `inherit` 사용 하 여 상속 관계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="f985b-107">기본 구문 형태는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="f985b-108">클래스는 하나의 직접 기본 클래스를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="f985b-109">`inherit` 키워드를 사용하여 기본 클래스를 지정하지 않으면 클래스가 암시적으로 `System.Object`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="f985b-110">상속된 멤버</span><span class="sxs-lookup"><span data-stu-id="f985b-110">Inherited Members</span></span>

<span data-ttu-id="f985b-111">클래스가 다른 클래스에서 상속되는 경우 파생 클래스의 메서드 및 멤버는 파생 클래스의 직접 멤버인 것처럼 파생 클래스의 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="f985b-112">let 바인딩 및 생성자 매개 변수는 클래스에 대한 전용이므로 파생 클래스에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="f985b-113">키워드는 `base` 파생 클래스에서 사용할 수 있으며 기본 클래스 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="f985b-114">자체 식별자처럼 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="f985b-115">가상 메서드 및 재정의</span><span class="sxs-lookup"><span data-stu-id="f985b-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="f985b-116">가상 메서드(및 속성)는 다른 .NET 언어와 비교하여 F#에서 다소 다르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="f985b-117">새 가상 멤버를 선언하려면 `abstract` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="f985b-118">해당 메서드에 대 한 기본 구현을 제공 하는지 여부에 관계 없이이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="f985b-119">따라서 기본 클래스의 가상 메서드에 대한 완전한 정의는 다음 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="f985b-120">파생 클래스에서 이 가상 메서드의 재정의는 다음 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="f985b-121">기본 클래스에서 기본 구현을 생략하면 기본 클래스가 추상 클래스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="f985b-122">다음 코드 예제에서는 기본 클래스에서 새 `function1` 가상 메서드의 선언 및 파생 된 클래스에서 재정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="f985b-123">생성자 및 상속</span><span class="sxs-lookup"><span data-stu-id="f985b-123">Constructors and Inheritance</span></span>

<span data-ttu-id="f985b-124">기본 클래스에 대 한 생성자는 파생 된 클래스에서 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="f985b-125">기본 클래스 생성자의 인수는 `inherit` 절의 인수 목록에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="f985b-126">사용되는 값은 파생 된 클래스 생성자에 제공 된 인수에서 결정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="f985b-127">다음 코드는 파생 된 클래스상속 절에서 base 클래스 생성자 호출 하는 base 클래스와 파생 된 클래스를 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="f985b-128">여러 생성자의 경우 다음 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="f985b-129">파생된 클래스 생성자의 첫 번째 줄은 `inherit` 절이며 필드는 `val` 키워드로 선언된 명시적 필드로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="f985b-130">자세한 내용은 [명시적 필드: `val` 키워드](./members/explicit-fields-the-val-keyword.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f985b-130">For more information, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="f985b-131">상속에 대한 대안</span><span class="sxs-lookup"><span data-stu-id="f985b-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="f985b-132">형식을 약간 수정해야 하는 경우 상속 대신 개체 식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="f985b-133">다음 예제에서는 새 파생 된 형식을 만드는 대신 개체 식을 사용 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="f985b-134">개체 표현식에 대한 자세한 내용은 [개체 표현식을](object-expressions.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f985b-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="f985b-135">개체 계층구조를 만들 때 상속 대신 구별된 공용 구조체를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="f985b-136">구별된 공용 구조체는 공통 전체 형식을 공유하는 다양한 개체의 다양한 동작을 모델링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="f985b-137">단일 구별 된 공용 구조체는 종종 서로의 사소한 변형인 파생 클래스의 수가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f985b-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="f985b-138">차별된 공용 구조체에 대한 자세한 내용은 [차별 조합을](discriminated-unions.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f985b-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f985b-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f985b-139">See also</span></span>

- [<span data-ttu-id="f985b-140">개체 식</span><span class="sxs-lookup"><span data-stu-id="f985b-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="f985b-141">F # 언어 참조</span><span class="sxs-lookup"><span data-stu-id="f985b-141">F# Language Reference</span></span>](index.md)
