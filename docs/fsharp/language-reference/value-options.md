---
title: 값 옵션
description: 옵션 형식의 구조체 F# 버전인 Value 옵션 형식에 대해 알아봅니다.
ms.date: 12/04/2019
ms.openlocfilehash: 0e9882ab4acdf2757705ef6022516d3572d87ef2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837118"
---
# <a name="value-options"></a>값 옵션

다음 두 가지 경우에 F# 값 옵션 유형이 사용 됩니다.

1. 시나리오는 [ F# 옵션](options.md)에 적합 합니다.
2. 구조체를 사용 하면 시나리오에서 성능상의 이점을 얻을 수 있습니다.

일부 성능 관련 시나리오는 구조체를 사용 하 여 "해결" 됩니다. 참조 형식 대신 사용 하는 경우 복사의 추가 비용을 고려해 야 합니다. 그러나 큰 F# 프로그램은 일반적으로 실행 부하 과다 경로를 통해 전달 되는 많은 선택적 형식을 인스턴스화합니다. 이러한 경우에는 구조체를 통해 프로그램의 수명 동안 전반적인 성능을 향상 시킬 수 있습니다.

## <a name="definition"></a>정의

Value 옵션은 참조 옵션 형식과 비슷한 [구조체로 구분 된 공용 구조체](discriminated-unions.md#struct-discriminated-unions) 로 정의 됩니다. 해당 정의는 다음과 같은 방식으로 생각할 수 있습니다.

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

값 옵션은 구조적 같음 및 비교를 준수 합니다. 주요 차이점은 컴파일된 이름, 형식 이름 및 사례 이름이 모두 값 형식 임을 나타내는 것입니다.

## <a name="using-value-options"></a>값 옵션 사용

값 옵션은 [옵션과](options.md)마찬가지로 사용 됩니다. `ValueSome`은 값이 존재 함을 나타내는 데 사용 되며, `ValueNone` 값이 없을 때 사용 됩니다.

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

[옵션과](options.md)마찬가지로 `ValueOption`을 반환 하는 함수에 대 한 명명 규칙은 `try`에 접두사로 지정 하는 것입니다.

## <a name="value-option-properties-and-methods"></a>Value 옵션 속성 및 메서드

현재 값 옵션에 대 한 속성은 `Value`입니다. 이 속성이 호출 될 때 값이 없는 경우 <xref:System.InvalidOperationException> 발생 합니다.

## <a name="value-option-functions"></a>Value 옵션 함수

Fsharp.core의 `ValueOption` 모듈에는 `Option` 모듈에 해당 하는 기능이 포함 되어 있습니다. `defaultValueArg`와 같이 이름에는 몇 가지 차이점이 있습니다.

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

이는 `Option` 모듈에서 `defaultArg`와 동일 하 게 작동 하지만 대신 값 옵션에서 작동 합니다.

## <a name="see-also"></a>참조

- [Options](options.md)
