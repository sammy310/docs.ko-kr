---
title: 활성 패턴
description: 활성 패턴을 사용하여 F# 프로그래밍 언어로 입력 데이터를 세분화하는 명명된 파티션을 정의하는 방법을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 898ef201369683bfd49d53e863e86f919f5837fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187067"
---
# <a name="active-patterns"></a>활성 패턴

*활성 패턴을* 사용하면 입력 데이터를 세분화하는 명명된 파티션을 정의할 수 있으므로 구별된 공용 구조체와 마찬가지로 패턴 일치 식에서 이러한 이름을 사용할 수 있습니다. 활성 패턴을 사용하여 각 파티션에 대한 사용자 지정 방식으로 데이터를 분해할 수 있습니다.

## <a name="syntax"></a>구문

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a>설명

이전 구문에서 식별자는 *인수로*표시되는 입력 데이터의 파티션에 대한 이름또는 인수의 모든 값 집합집합의 하위 집합에 대한 이름입니다. 활성 패턴 정의에는 최대 7개의 파티션이 있을 수 있습니다. *식은* 데이터를 분해할 폼을 설명합니다. 활성 패턴 정의를 사용하여 인수로 지정된 값이 속한 명명된 파티션을 결정하는 규칙을 정의할 수 있습니다. (| 및 |) 기호를 *바나나 클립이라고* 하며 이러한 유형의 let 바인딩에 의해 생성된 함수를 *활성 인식기라고*합니다.

예를 들어 인수와 함께 다음 활성 패턴을 고려합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

다음 예제와 같이 패턴 일치 식에서 활성 패턴을 사용할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

이 프로그램의 출력은 다음과 같습니다.

```console
7 is odd
11 is odd
32 is even
```

활성 패턴의 또 다른 용도는 동일한 기본 데이터에 다양한 가능한 표현이 있는 경우와 같이 여러 가지 방법으로 데이터 형식을 분해하는 것입니다. 예를 들어 `Color` 개체를 RGB 표현 또는 HSB 표현으로 분해할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

위의 프로그램의 출력은 다음과 같습니다.

```console
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

이러한 두 가지 활성 패턴을 사용하면 데이터를 적절한 형식으로 분할 및 분해하고 계산에 가장 편리한 형태로 적절한 데이터에 대한 적절한 계산을 수행할 수 있습니다.

결과 패턴 일치 식을 사용하면 매우 읽기 쉬운 편리한 방식으로 데이터를 작성할 수 있으므로 잠재적으로 복잡한 분기 및 데이터 분석 코드가 크게 간소화됩니다.

## <a name="partial-active-patterns"></a>부분 활성 패턴

때로는 입력 공간의 일부만 분할해야 합니다. 이 경우 일부 입력과 일치하지만 다른 입력과 일치하지 않는 부분 패턴 집합을 작성합니다. 항상 값을 생성하지 않는 활성 *패턴을 부분 활성 패턴이라고 합니다.* 옵션 형식인 반환 값이 있습니다. 부분 활성 패턴을 정의하려면 바나나 클립 내부의 패턴 목록 끝에 와일드카드 문자()를\_사용합니다. 다음 코드는 부분 활성 패턴의 사용을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

이전 예제의 출력은 다음과 같습니다.

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

부분 활성 패턴을 사용하는 경우 개별 선택이 분리되거나 상호 배타적일 수 있지만 필요하지는 않습니다. 다음 예제에서는 일부 숫자가 사각형과 64와 같은 큐브이기 때문에 패턴 정사각형과 패턴 큐브가 분리되지 않습니다. 다음 프로그램은 AND 패턴을 사용하여 정사각형 및 큐브 패턴을 결합합니다. 정사각형과 큐브모두인 최대 1000개의 정수와 큐브만 인쇄됩니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

출력은 다음과 같습니다.

```console
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a>매개 변수화된 활성 패턴

활성 패턴은 항상 일치하는 항목에 대해 하나 이상의 인수를 사용하지만 추가 인수도 걸릴 수 있으며, 이 경우 이름 *매개 변수화된 활성 패턴이* 적용됩니다. 추가 인수를 사용하면 일반 패턴을 특수화할 수 있습니다. 예를 들어 문자열을 구문 분석하기 위해 정규식을 사용하는 활성 패턴에는 이전 코드 예제에서 정의된 부분 활성 `Integer` 패턴을 사용하는 다음 코드와 같이 정규식을 추가 매개 변수로 포함되는 경우가 많습니다. 이 예제에서는 다양한 날짜 형식에 정규식을 사용하는 문자열이 주어지므로 일반 ParseRegex 활성 패턴을 사용자 지정합니다. 정수 활성 패턴은 일치하는 문자열을 DateTime 생성자에 전달할 수 있는 정수로 변환하는 데 사용됩니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

이전 코드의 출력은 다음과 같습니다.

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

활성 패턴은 패턴 일치 식에만 국한되지 않고 let-bindings에서도 사용할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

이전 코드의 출력은 다음과 같습니다.

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>참고 항목

- [F # 언어 참조](index.md)
- [일치 식](match-expressions.md)
