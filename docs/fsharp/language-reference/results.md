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
# <a name="results"></a>결과

`Result<'T,'TFailure>`형식을 사용 하 여 작성할 수 있는 오류 허용 코드를 작성할 수 있습니다.

## <a name="syntax"></a>구문

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> =
    | Ok of ResultValue:'T
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a>설명

에 [`Result`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-resultmodule.html) 대 한 기본 제공 조합 기 모듈을 참조 하세요 `Result` . 형식의 매개 변수로 변환됩니다.

결과 형식은 [구조체 구별 된 공용 구조체](discriminated-unions.md#struct-discriminated-unions)입니다. 구조적 같음 의미 체계가 여기에 적용 됩니다.

`Result`형식은 일반적으로 F # 커뮤니티 내에서 [철도 지향 프로그래밍](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) 이 라고도 하는 monadic 오류 처리에 사용 됩니다.  다음은이 방법을 보여 주는 간단한 예제입니다.

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

여기에서 볼 수 있듯이 모두를 강제로 반환 하는 경우 다양 한 유효성 검사 함수를 함께 연결 하는 것이 매우 쉽습니다 `Result` .  이를 통해 이러한 기능을 필요에 따라 구성 가능한 작은 부분으로 나눌 수 있습니다.  또한 유효성 검사의 끝에 [패턴 일치](pattern-matching.md) 를 사용 하는 것이 추가 된 값을 가지 며,이 *로 인해 더* 높은 수준의 프로그램 정확성이 적용 됩니다.

## <a name="see-also"></a>참고 항목

- [구별된 공용 구조체](discriminated-unions.md)
- [패턴 일치](pattern-matching.md)
