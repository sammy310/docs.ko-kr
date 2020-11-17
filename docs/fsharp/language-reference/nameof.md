---
title: Nameof
description: 소스 코드에서 기호 이름을 생성할 수 있도록 하는 메타 프로그래밍 기능인 연산자에 대해 알아봅니다.
ms.date: 11/12/2020
ms.openlocfilehash: 9947d7172d1b73db5c181297ec8b1131382e1f5e
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688642"
---
# <a name="nameof"></a><span data-ttu-id="24ab6-103">Nameof</span><span class="sxs-lookup"><span data-stu-id="24ab6-103">Nameof</span></span>

<span data-ttu-id="24ab6-104">`nameof`이 식은 소스에 있는 거의 모든 F # 구문에 대 한 소스의 이름과 일치 하는 문자열 상수를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-104">The `nameof` expression produces a string constant that matches the name in source for nearly any F# construct in source.</span></span>

## <a name="syntax"></a><span data-ttu-id="24ab6-105">구문</span><span class="sxs-lookup"><span data-stu-id="24ab6-105">Syntax</span></span>

```fsharp
nameof symbol
nameof<'TGeneric>
```

## <a name="remarks"></a><span data-ttu-id="24ab6-106">설명</span><span class="sxs-lookup"><span data-stu-id="24ab6-106">Remarks</span></span>

<span data-ttu-id="24ab6-107">`nameof` 는 전달 된 기호를 확인 하 여 작동 하 고 소스 코드에 선언 된 대로 해당 기호의 이름을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-107">`nameof` works by resolving the symbol passed to it and produces the name of that symbol as it is declared in your source code.</span></span> <span data-ttu-id="24ab6-108">이는 로깅과 같은 다양 한 시나리오에서 유용 하며 소스 코드의 변경 내용에 대해 로깅을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-108">This is useful in various scenarios, such as logging, and protects your logging against changes in source code.</span></span>

```fsharp
let months =
    [
        "January"; "February"; "March"; "April";
        "May"; "June"; "July"; "August"; "September";
        "October"; "November"; "December"
    ]

let lookupMonth month =
    if (month > 12 || month < 1) then
        invalidArg (nameof month) ($"Value passed in was %d{month}.")

    months.[month-1]

printfn "%s" (lookupMonth 12)
printfn "%s" (lookupMonth 1)
printfn "%s" (lookupMonth 13)
```

<span data-ttu-id="24ab6-109">마지막 줄은 예외를 throw 하 고 `"month"` 오류 메시지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-109">The last line will throw an exception and `"month"` will be shown in the error message.</span></span>

<span data-ttu-id="24ab6-110">거의 모든 F # 구문의 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-110">You can take a name of nearly every F# construct:</span></span>

```fsharp
module M =
    let f x = nameof x

printfn $"{(M.f 12)]}"
printfn $"{(nameof M)}"
printfn $"{(nameof M.f)}"
```

<span data-ttu-id="24ab6-111">`nameof` 은 (는) 첫 번째 클래스 함수가 아니므로 이러한 함수로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-111">`nameof` is not a first-class function and cannot be used as such.</span></span> <span data-ttu-id="24ab6-112">즉, 부분적으로 적용할 수 없으며 F # 파이프라인 연산자를 통해 값을 파이프로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-112">That means it cannot be partially applied and values cannot be piped into it via F# pipeline operators.</span></span>

## <a name="nameof-on-operators"></a><span data-ttu-id="24ab6-113">On 연산자의 nameof 연산자</span><span class="sxs-lookup"><span data-stu-id="24ab6-113">Nameof on operators</span></span>

<span data-ttu-id="24ab6-114">F #의 연산자는 두 가지 방법, 즉 연산자 텍스트 자체로 사용 하거나 컴파일된 폼을 나타내는 기호로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-114">Operators in F# can be used in two ways, as an operator text itself, or a symbol representing the compiled form.</span></span> <span data-ttu-id="24ab6-115">`nameof` 연산자에 대해 원본에서 선언 되는 연산자의 이름이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-115">`nameof` on an operator will produce the name of the operator as it is declared in source.</span></span> <span data-ttu-id="24ab6-116">컴파일된 이름을 가져오려면 원본에서 컴파일된 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-116">To get the compiled name, use the compiled name in source:</span></span>

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

## <a name="nameof-on-generics"></a><span data-ttu-id="24ab6-117">제네릭의 name</span><span class="sxs-lookup"><span data-stu-id="24ab6-117">Nameof on generics</span></span>

<span data-ttu-id="24ab6-118">제네릭 형식 매개 변수의 이름을 가져올 수도 있지만 구문은 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-118">You can also take a name of a generic type parameter, but the syntax is different:</span></span>

```fsharp
let f<'a> () = nameof<'a>
f() // "a"
```

<span data-ttu-id="24ab6-119">`nameof<'TGeneric>` 는 호출 사이트에서 대체 되는 형식의 이름이 아니라 source에 정의 된 대로 기호 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-119">`nameof<'TGeneric>` will take the name of the symbol as defined in source, not the name of the type substituted at a call site.</span></span>

<span data-ttu-id="24ab6-120">구문이 다른 이유는 및와 같은 다른 F # 내장 연산자와 정렬 하는 것 `typeof<>` 입니다 `typedefof<>` .</span><span class="sxs-lookup"><span data-stu-id="24ab6-120">The reason why the syntax is different is to align with other F# intrinsic operators like `typeof<>` and `typedefof<>`.</span></span> <span data-ttu-id="24ab6-121">이렇게 하면 제네릭 형식에 대해 작동 하는 연산자와 관련 하 여 F #이 일치 하 고 다른 모든 요소는 소스에서 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-121">This makes F# consistent with respect to operators that act on generic types and anything else in source.</span></span>

## <a name="nameof-in-pattern-matching"></a><span data-ttu-id="24ab6-122">패턴 일치의 nameof</span><span class="sxs-lookup"><span data-stu-id="24ab6-122">Nameof in pattern matching</span></span>

<span data-ttu-id="24ab6-123">[ `nameof` 패턴](pattern-matching.md#nameof-pattern) 을 사용 하면 `nameof` 다음과 같이 패턴 일치 식에서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24ab6-123">The [`nameof` pattern](pattern-matching.md#nameof-pattern) lets you use `nameof` in a pattern match expression like so:</span></span>

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```
