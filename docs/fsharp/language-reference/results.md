---
title: 결과
description: "F # ' Result ' 유형을 사용 하 여 오류를 방지 하는 코드를 작성 하는 방법을 알아봅니다."
ms.date: 08/13/2020
ms.openlocfilehash: d69e6ddc37bcf5cb5fc28644d59a11a822b83faa
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656920"
---
# <a name="results"></a><span data-ttu-id="6a3fd-103">결과</span><span class="sxs-lookup"><span data-stu-id="6a3fd-103">Results</span></span>

<span data-ttu-id="6a3fd-104">`Result<'T,'TFailure>`형식을 사용 하 여 작성할 수 있는 오류 허용 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a3fd-104">The `Result<'T,'TFailure>` type lets you write error-tolerant code that can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="6a3fd-105">구문</span><span class="sxs-lookup"><span data-stu-id="6a3fd-105">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> =
    | Ok of ResultValue:'T
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="6a3fd-106">설명</span><span class="sxs-lookup"><span data-stu-id="6a3fd-106">Remarks</span></span>

<span data-ttu-id="6a3fd-107">에 [`Result`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-resultmodule.html) 대 한 기본 제공 조합 기 모듈을 참조 하세요 `Result` .</span><span class="sxs-lookup"><span data-stu-id="6a3fd-107">See the [`Result`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-resultmodule.html) module for the built-in combinators for the `Result`.</span></span> <span data-ttu-id="6a3fd-108">형식의 매개 변수로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a3fd-108">type.</span></span>

<span data-ttu-id="6a3fd-109">결과 형식은 [구조체 구별 된 공용 구조체](discriminated-unions.md#struct-discriminated-unions)입니다.</span><span class="sxs-lookup"><span data-stu-id="6a3fd-109">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions).</span></span> <span data-ttu-id="6a3fd-110">구조적 같음 의미 체계가 여기에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a3fd-110">Structural equality semantics apply here.</span></span>

<span data-ttu-id="6a3fd-111">`Result`형식은 일반적으로 F # 커뮤니티 내에서 [철도 지향 프로그래밍](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) 이 라고도 하는 monadic 오류 처리에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a3fd-111">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="6a3fd-112">다음은이 방법을 보여 주는 간단한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6a3fd-112">The following trivial example demonstrates this approach.</span></span>

```fsharp
// Define a simple type which has fields that can be validated
type Request =
    { Name: string
      Email: string }

// Define some logic for what defines a valid name.
//
// Generates a Result which is an Ok if the name validates;
// otherwise, it generates a Result which is an Error.
let validateName req =
    match req.Name with
    | null -> Error "No name found."
    | "" -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | "" -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> Ok req

let validateRequest reqResult =
    reqResult
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() =
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (Ok req1)
    match res1 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (Ok req2)
    match res2 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

<span data-ttu-id="6a3fd-113">여기에서 볼 수 있듯이 모두를 강제로 반환 하는 경우 다양 한 유효성 검사 함수를 함께 연결 하는 것이 매우 쉽습니다 `Result` .</span><span class="sxs-lookup"><span data-stu-id="6a3fd-113">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="6a3fd-114">이를 통해 이러한 기능을 필요에 따라 구성 가능한 작은 부분으로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a3fd-114">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="6a3fd-115">또한 유효성 검사의 끝에 [패턴 일치](pattern-matching.md) 를 사용 하는 것이 추가 된 값을 가지 며,이 *로 인해 더* 높은 수준의 프로그램 정확성이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a3fd-115">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a3fd-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a3fd-116">See also</span></span>

- [<span data-ttu-id="6a3fd-117">구별된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="6a3fd-117">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="6a3fd-118">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="6a3fd-118">Pattern Matching</span></span>](pattern-matching.md)
