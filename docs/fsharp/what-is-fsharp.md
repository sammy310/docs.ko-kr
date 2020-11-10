---
title: F#이란?
description: 'F # 프로그래밍 언어 및 F # 프로그래밍에 대해 알아봅니다. 다양 한 데이터 형식, 함수 및이를 함께 활용 하는 방법에 대해 알아봅니다.'
ms.date: 08/03/2018
ms.openlocfilehash: 37dc2f472d65a046e4bf67e672e2a96f4d4afded
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439656"
---
# <a name="what-is-f"></a><span data-ttu-id="6dab5-104">F 란?\#</span><span class="sxs-lookup"><span data-stu-id="6dab5-104">What is F\#</span></span>

<span data-ttu-id="6dab5-105">F #은 올바른 코드와 유지 관리 가능 코드를 쉽게 작성할 수 있도록 하는 함수형 프로그래밍 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="6dab5-106">F # 프로그래밍에는 기본적으로 형식 유추 및 일반화 된 형식 및 함수를 정의 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="6dab5-107">이렇게 하면 포커스가 문제 도메인에 그대로 유지 되 고 프로그래밍의 세부 정보가 아닌 데이터를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name = $"Hello, {name}! Isn't F# great?"

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="6dab5-108">F #에는 다음을 비롯 한 다양 한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="6dab5-109">간단한 구문</span><span class="sxs-lookup"><span data-stu-id="6dab5-109">Lightweight syntax</span></span>
* <span data-ttu-id="6dab5-110">기본적으로 변경할 수 없음</span><span class="sxs-lookup"><span data-stu-id="6dab5-110">Immutable by default</span></span>
* <span data-ttu-id="6dab5-111">형식 유추 및 자동 일반화</span><span class="sxs-lookup"><span data-stu-id="6dab5-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="6dab5-112">첫 번째 클래스 함수</span><span class="sxs-lookup"><span data-stu-id="6dab5-112">First-class functions</span></span>
* <span data-ttu-id="6dab5-113">강력한 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6dab5-113">Powerful data types</span></span>
* <span data-ttu-id="6dab5-114">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="6dab5-114">Pattern matching</span></span>
* <span data-ttu-id="6dab5-115">비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="6dab5-115">Async programming</span></span>

<span data-ttu-id="6dab5-116">전체 기능 집합은 [F # 언어 참조](./language-reference/index.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-116">A full set of features are documented in the [F# language reference](./language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="6dab5-117">다양 한 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6dab5-117">Rich data types</span></span>

<span data-ttu-id="6dab5-118">[레코드](./language-reference/records.md) 및 [구분 된 공용 구조체](./language-reference/discriminated-unions.md) 와 같은 데이터 형식을 사용 하면 복잡 한 데이터와 도메인을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-118">Data types such as [Records](./language-reference/records.md) and [Discriminated Unions](./language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

<span data-ttu-id="6dab5-119">F # 레코드 및 구분 된 공용 구조체는 null이 아니고 변경할 수 없으며 기본적으로 비교할 수 있으므로 매우 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="6dab5-120">함수 및 패턴 일치를 사용 하 여 정확성 적용</span><span class="sxs-lookup"><span data-stu-id="6dab5-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="6dab5-121">F # 함수는 쉽게 선언 하 고 효과적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="6dab5-122">[패턴 일치](./language-reference/pattern-matching.md)와 함께 사용 하는 경우 컴파일러에 의해 정확성이 적용 되는 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-122">When combined with [pattern matching](./language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

<span data-ttu-id="6dab5-123">F # 함수는 first 클래스 이기도 합니다. 즉, 매개 변수로 전달 되 고 다른 함수에서 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="6dab5-124">개체에 대 한 작업을 정의 하는 함수</span><span class="sxs-lookup"><span data-stu-id="6dab5-124">Functions to define operations on objects</span></span>

<span data-ttu-id="6dab5-125">F #에는 데이터와 기능을 혼합 해야 하는 경우 유용한 데이터 유형인 개체에 대 한 완전 한 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="6dab5-126">F # 함수는 개체를 조작 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-126">F# functions are used to manipulate objects.</span></span>

```fsharp
type Set<'T when 'T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

<span data-ttu-id="6dab5-127">F #에서는 개체 지향 코드를 작성 하는 대신 함수에서 조작할 수 있는 다른 데이터 형식으로 개체를 처리 하는 코드를 작성 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="6dab5-128">[제네릭 인터페이스](./language-reference/interfaces.md), [개체 식](./language-reference/object-expressions.md)및 [멤버](./language-reference/members/index.md) 의 적절 한 사용과 같은 기능은 큰 F # 프로그램에서 일반적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dab5-128">Features such as [generic interfaces](./language-reference/interfaces.md), [object expressions](./language-reference/object-expressions.md), and judicious use of [members](./language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6dab5-129">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6dab5-129">Next steps</span></span>

<span data-ttu-id="6dab5-130">더 큰 F # 기능 집합에 대 한 자세한 내용은 [f # 둘러보기](tour.md)를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="6dab5-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>
