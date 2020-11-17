---
title: 보간된 문자열
description: 'F # 식을 직접 포함할 수 있는 특수 한 형식의 문자열에 대해 알아봅니다.'
ms.date: 11/12/2020
ms.openlocfilehash: a49d4e743306fd9bdabb1e019ec4e6c77e0e1f5a
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688629"
---
# <a name="interpolated-strings"></a>보간된 문자열

보간된 문자열은 F # 식을 포함 하는 데 사용할 수 있는 [문자열](strings.md) 입니다. 값 또는 식의 결과에 따라 문자열 값이 변경 될 수 있는 다양 한 시나리오에서 유용 합니다.

## <a name="syntax"></a>구문

```fsharp
$"string-text {expr}"
$"string-text %format-specifier{expr}"
$"""string-text {"embedded string literal"}"""
```

## <a name="remarks"></a>설명

보간된 문자열을 사용 하면 문자열 리터럴 내에서 "구멍"으로 코드를 작성할 수 있습니다. 기본 예제는 다음과 같습니다.

```fsharp
let name = "Phillip"
let age = 30
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

각 중괄호 쌍 사이에 있는 내용은 `{}` 임의의 F # 식일 수 있습니다.

중괄호 쌍을 이스케이프 하려면 `{}` 다음과 같이 두 가지를 작성 합니다.

```fsharp
let str = $"A pair of braces: {{}}"
// "A pair of braces: {}"
```

## <a name="typed-interpolated-strings"></a>형식화 된 보간된 문자열

보간된 문자열에는 safey 형식을 적용 하는 F # 형식 지정 자가 있을 수도 있습니다.

```fsharp
let name = "Phillip"
let age = 30

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

앞의 예제에서 코드는가 이어야 하는 값을 잘못 전달 `age` `name` 하 고 그 반대의 경우도 마찬가지입니다. 보간된 문자열은 형식 지정자를 사용 하기 때문에이는 미묘한 런타임 버그 대신 컴파일 오류입니다.

[일반 텍스트 서식](plaintext-formatting.md) 에서 적용 되는 모든 형식 지정자는 보간된 문자열 내에서 유효 합니다.

## <a name="verbatim-interpolated-strings"></a>축 자 보간된 문자열

F #은 문자열 리터럴을 포함할 수 있도록 삼중 따옴표를 사용 하 여 축 자 보간된 문자열을 지원 합니다.

```fsharp
let age = 30

printfn $"""Name: {"Phillip"}, Age: %d{age}"""
```

## <a name="aligning-expressions-in-interpolated-strings"></a>보간된 문자열에서 식 맞춤

를 사용 하 여 보간된 문자열 내에 식을 왼쪽으로 맞추거나 오른쪽에 맞추고, 공백 수를 지정할 수 있습니다 `|` . 다음 보간된 문자열은 왼쪽 및 오른쪽 식을 각각 7 개의 공백으로 정렬 합니다.

```fsharp
printfn $"""|{"Left",-7}|{"Right",7}|"""
// |Left   |  Right|
```

## <a name="interpolated-strings-and-formattablestring-formatting"></a>보간된 문자열 및 `FormattableString` 서식 지정

다음에 대 한 규칙을 준수 하는 서식도 적용할 수 있습니다 <xref:System.FormattableString> .

```fsharp
let speedOfLight = 299792.458
printfn $"The speed of light is {speedOfLight:N3} km/s."
// "The speed of light is 299,792.458 km/s."
```

또한 보간된 문자열은 형식 주석을 통해로 typechecked 될 수도 있습니다 <xref:System.FormattableString> .

```fsharp
let frmtStr = $"The speed of light is {speedOfLight:N3} km/s." : FormattableString
// Type: FormattableString
// The speed of light is 299,792.458 km/s.
```

형식 주석은 보간된 문자열 식 자체에 있어야 합니다. F #은 보간된 문자열을으로 암시적으로 변환 하지 않습니다 <xref:System.FormattableString> .

## <a name="see-also"></a>참조

* [문자열](strings.md)
