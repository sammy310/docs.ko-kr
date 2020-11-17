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
# <a name="nameof"></a>Nameof

`nameof`이 식은 소스에 있는 거의 모든 F # 구문에 대 한 소스의 이름과 일치 하는 문자열 상수를 생성 합니다.

## <a name="syntax"></a>구문

```fsharp
nameof symbol
nameof<'TGeneric>
```

## <a name="remarks"></a>설명

`nameof` 는 전달 된 기호를 확인 하 여 작동 하 고 소스 코드에 선언 된 대로 해당 기호의 이름을 생성 합니다. 이는 로깅과 같은 다양 한 시나리오에서 유용 하며 소스 코드의 변경 내용에 대해 로깅을 보호 합니다.

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

마지막 줄은 예외를 throw 하 고 `"month"` 오류 메시지에 표시 됩니다.

거의 모든 F # 구문의 이름을 사용할 수 있습니다.

```fsharp
module M =
    let f x = nameof x

printfn $"{(M.f 12)]}"
printfn $"{(nameof M)}"
printfn $"{(nameof M.f)}"
```

`nameof` 은 (는) 첫 번째 클래스 함수가 아니므로 이러한 함수로 사용할 수 없습니다. 즉, 부분적으로 적용할 수 없으며 F # 파이프라인 연산자를 통해 값을 파이프로 전달할 수 없습니다.

## <a name="nameof-on-operators"></a>On 연산자의 nameof 연산자

F #의 연산자는 두 가지 방법, 즉 연산자 텍스트 자체로 사용 하거나 컴파일된 폼을 나타내는 기호로 사용할 수 있습니다. `nameof` 연산자에 대해 원본에서 선언 되는 연산자의 이름이 생성 됩니다. 컴파일된 이름을 가져오려면 원본에서 컴파일된 이름을 사용 합니다.

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

## <a name="nameof-on-generics"></a>제네릭의 name

제네릭 형식 매개 변수의 이름을 가져올 수도 있지만 구문은 다릅니다.

```fsharp
let f<'a> () = nameof<'a>
f() // "a"
```

`nameof<'TGeneric>` 는 호출 사이트에서 대체 되는 형식의 이름이 아니라 source에 정의 된 대로 기호 이름을 사용 합니다.

구문이 다른 이유는 및와 같은 다른 F # 내장 연산자와 정렬 하는 것 `typeof<>` 입니다 `typedefof<>` . 이렇게 하면 제네릭 형식에 대해 작동 하는 연산자와 관련 하 여 F #이 일치 하 고 다른 모든 요소는 소스에서 일치 하지 않습니다.

## <a name="nameof-in-pattern-matching"></a>패턴 일치의 nameof

[ `nameof` 패턴](pattern-matching.md#nameof-pattern) 을 사용 하면 `nameof` 다음과 같이 패턴 일치 식에서를 사용할 수 있습니다.

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```
