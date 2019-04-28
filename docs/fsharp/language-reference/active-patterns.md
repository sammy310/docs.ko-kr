---
title: 활성 패턴
description: 활성 패턴을 사용 하 여 입력된 데이터를 분할 하는 명명 된 파티션을 정의 하는 방법을 알아봅니다는 F# 프로그래밍 언어입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 0f1f57de425836738201d2d8f84ab67a0df142ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772753"
---
# <a name="active-patterns"></a>활성 패턴

*활성 패턴* 이러한 이름을 사용 하 여 패턴 일치 구별된 된 공용 구조체에 대 한 것 처럼 식에에서는 입력된 데이터를 분할 하는 명명 된 파티션을 정의할 수 있게 합니다. 활성 패턴을 사용하여 각 파티션에 대한 사용자 지정 방식으로 데이터를 분해할 수 있습니다.

## <a name="syntax"></a>구문

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a>설명

이전 구문에서 식별자에 의해 표현 되는 입력된 데이터의 파티션에 대 한 이름 *인수*, 또는 즉, 인수의 모든 값의 집합의 하위 집합에 대 한 이름입니다. 활성 패턴 정의에 최대 7 개의 파티션이 있을 수 있습니다. 합니다 *식* 데이터를 분해 하는 형식에 설명 합니다. 인수에 속하는 지정 된 값의 명명 된 파티션을 확인 하는 것에 대 한 규칙을 정의 하는 활성 패턴 정의 사용할 수 있습니다. (| 및 |) 기호 라고 *바나나 클립* let 바인딩이 형식에 의해 생성 함수를 호출 하 고는 *활성 인식기*합니다.

예를 들어 인수를 사용 하 여 활성 패턴을 고려 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

다음 예제와 같이 식에서 일치 하는 패턴의 활성 패턴을 사용할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

이 프로그램의 출력은 다음과 같습니다.

```
7 is odd
11 is odd
32 is even
```

활성 패턴의 또 다른 용도 동일한 기본 데이터의 여러 가지 가능한 표현 사이 있을 때와 같은 여러 가지 방법으로 데이터 형식을 분해 하는 것입니다. 예를 들어, 한 `Color` 는 RGB 표현 또는 HSB 표현으로 개체를 분해할 수 없습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

위 프로그램의 출력은 다음과 같습니다.

```
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

조합 활성 패턴을 사용 하 여 이러한 두 가지 파티션 수만 적절 한 형태로 데이터를 분해 하 고 적절 한 데이터는 계산을 위한 가장 편리한 폼에 대해 적절 한 계산을 수행 합니다.

결과 패턴 일치 식을 사용 데이터를 읽을 수 있는 매우를 크게 간소화 잠재적으로 복잡 한 분기 및 코드를 분석 하는 데이터는 편리한 방식으로 기록 합니다.

## <a name="partial-active-patterns"></a>부분 활성 패턴

때로는 일부만 입력 공간 분할 해야 합니다. 이런 경우는 일부 입력와 일치 하지만 다른 입력에 맞게 실패 부분 패턴 집합을 작성 합니다. 값을 생성 하지 않을 수 있는 활성 패턴 이라고 *부분 활성 패턴*; 옵션 형식으로 반환 값을 갖습니다. 와일드 카드 문자를 사용 하면 부분 활성 패턴을 정의 하려면 (\_) 바나나 클립 내 패턴의 목록 끝에 있습니다. 다음 코드 부분 활성 패턴의 사용을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

이전 예제의 출력은 아래와 같습니다.

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

부분 활성 패턴을 사용 하는 경우 때때로 개별 선택 비연속 또는 함께 사용할 수 없습니다 있지만 될 필요 합니다. 다음 예제에서 패턴 사각형 및 패턴 큐브는 아닙니다이 일부 숫자 사각형 및 64와 같은 큐브. 다음 프로그램 사각형 및 정육면체 패턴을 결합 하는 AND 패턴을 사용 합니다. 최대 1000 모두 사각형 및 큐브 뿐만 큐브만 되는 모든 정수 출력. 

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

출력은 다음과 같습니다.

```
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

## <a name="parameterized-active-patterns"></a>매개 변수가 있는 활성 패턴

활성 패턴은 항상 일치 하는 항목에 대 한 하나 이상의 인수를 사용 하지만 경우 이름 인수를 추가로 걸릴 수 있습니다 *매개 변수가 있는 활성 패턴* 적용 됩니다. 추가 인수는 특수화 되어야 하는 일반적인 패턴을 허용 합니다. 종종 문자열을 구문 분석할 정규식을 사용 하는 활성 패턴 또한 부분 활성 패턴을 사용 하는 다음 코드와 같이 추가 매개 변수로 정규식을 포함 하는 예를 들어 `Integer` 이전 코드 예제에서 정의 합니다. 이 예제에서는 다양 한 날짜 형식에 대 한 정규식을 사용 하는 문자열은 일반 ParseRegex 활성 패턴에 맞게 제공 됩니다. 정수 활성 패턴 일치 하는 문자열을 DateTime 생성자에 전달할 수 있는 정수로 변환 됩니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

이전 코드의 출력은 다음과 같습니다.

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

활성 패턴 패턴 일치 식에만 제한 되지 않습니다., let 바인딩에서 사용할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

이전 코드의 출력은 다음과 같습니다.

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [일치 식](match-expressions.md)
