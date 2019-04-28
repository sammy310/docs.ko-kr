---
title: F#이란
description: F# 프로그래밍 언어와 F# 프로그래밍이 어떤 것인지 알아봅니다. 풍부한 데이터 유형과 기능, 이들이 함께 어울리는 방법을 알아봅니다.
ms.date: 08/03/2018
ms.openlocfilehash: ea82147e4e6d3c980fb224eeafd805c7ed53f8f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756340"
---
# <a name="what-is-f"></a><span data-ttu-id="7da3d-104">F\#이란</span><span class="sxs-lookup"><span data-stu-id="7da3d-104">What is F\#</span></span>

<span data-ttu-id="7da3d-105">F#은 정확하고 유지 보수가 쉬운 코드를 만들 수 있는 함수형 프로그래밍 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="7da3d-106">F# 프로그래밍은 주로 자동으로 형식이 유추되고 일반화되는 형식 및 함수를 정의하는 것을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="7da3d-107">따라서 프로그래밍의 세부 사항보다는 문제 도메인에 집중하고 데이터를 조작하는 데 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

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

<span data-ttu-id="7da3d-108">F#은 다음과 같은 다양한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="7da3d-109">간단한 구문</span><span class="sxs-lookup"><span data-stu-id="7da3d-109">Lightweight syntax</span></span>
* <span data-ttu-id="7da3d-110">기본적으로 변경 불가능</span><span class="sxs-lookup"><span data-stu-id="7da3d-110">Immutable by default</span></span>
* <span data-ttu-id="7da3d-111">타입 추론 및 자동화된 일반화</span><span class="sxs-lookup"><span data-stu-id="7da3d-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="7da3d-112">일급 함수</span><span class="sxs-lookup"><span data-stu-id="7da3d-112">First-class functions</span></span>
* <span data-ttu-id="7da3d-113">강력한 데이터 타입</span><span class="sxs-lookup"><span data-stu-id="7da3d-113">Powerful data types</span></span>
* <span data-ttu-id="7da3d-114">패턴 매칭</span><span class="sxs-lookup"><span data-stu-id="7da3d-114">Pattern matching</span></span>
* <span data-ttu-id="7da3d-115">비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="7da3d-115">Async programming</span></span>

<span data-ttu-id="7da3d-116">전체 기능은 [F# 언어 참조](language-reference/index.md)에 문서화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-116">A full set of features are documented in the [F# language reference](language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="7da3d-117">다양한 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7da3d-117">Rich data types</span></span>

<span data-ttu-id="7da3d-118">[Records](language-reference/records.md) 및 [Discriminated Unions](language-reference/discriminated-unions.md)와 같은 데이터 타입을 사용하면 복잡한 데이터와 도메인을 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-118">Data types such as [Records](language-reference/records.md) and [Discriminated Unions](language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

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

<span data-ttu-id="7da3d-119">F# Record와 Discriminated Union는 기본적으로 null이 아니며 변경 불가능하고 비교할 수 있으므로 아주 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="7da3d-120">함수 및 패턴 매칭을 통한 정확성 강화</span><span class="sxs-lookup"><span data-stu-id="7da3d-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="7da3d-121">F#함수 선언 하기 쉽고 강력한 실제로입니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="7da3d-122">함께 사용 하면 [패턴 일치](language-reference/pattern-matching.md), 인 정확성 컴파일러에 의해 적용 되는 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-122">When combined with [pattern matching](language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

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

<span data-ttu-id="7da3d-123">F#함수는 첫 번째 클래스를 매개 변수로 전달 되 고 다른 함수에서 반환 된 수를 의미 합니다. 또한입니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="7da3d-124">객체에 대한 연산을 정의하는 함수</span><span class="sxs-lookup"><span data-stu-id="7da3d-124">Functions to define operations on objects</span></span>

<span data-ttu-id="7da3d-125">F#은 객체를 완벽하게 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="7da3d-126">객체는 데이터와 함수를 혼합해야 할 때 유용한 데이터 타입입니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-126">F# functions are used to manipulate objects.</span></span>

```fsharp
type Set<[<EqualityConditionOn>] ‘T when ‘T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

<span data-ttu-id="7da3d-127">F#에서는 객체 지향적 코드를 작성하는 것 보다 함수를 조작하는 데 필요한 다른 데이터 타입으로 객체를 처리하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="7da3d-128">[제네릭 인터페이스](language-reference/interfaces.md), [객체 식](language-reference/object-expressions.md) 및 [멤버](language-reference/members/index.md)의 현명한 사용과 같은 기능은 더 큰 F# 프로그램에서 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="7da3d-128">Features such as [generic interfaces](language-reference/interfaces.md), [object expressions](language-reference/object-expressions.md), and judicious use of [members](language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7da3d-129">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7da3d-129">Next steps</span></span>

<span data-ttu-id="7da3d-130">더 많은 F# 기능 집합은 [F# 둘러보기](tour.md)를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="7da3d-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>