---
title: 패턴 일치
description: 패턴을 사용 하는 방법을 알아봅니다 F# 논리 구조를 사용 하 여 데이터를 비교 하려면 데이터를 구성 부분으로 분해 하거나 데이터에서 정보를 추출 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: bb6b41f6d15612e4a65abd4a3d5d7291d84a8f3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795462"
---
# <a name="pattern-matching"></a>패턴 일치

패턴은 입력된 데이터를 변환 하는 것에 대 한 규칙입니다. 전체에서 사용 되는 F# 논리적 구조체 또는 구조체를 사용 하 여 데이터를 비교 하는 언어 구성 요소에 데이터를 분해 또는 다양 한 방법으로 데이터에서 정보를 추출 합니다.

## <a name="remarks"></a>설명

패턴은 같은 여러 가지 언어 구문에 사용 되는 `match` 식입니다. 함수에 대 한 인수를 처리 하는 경우 사용할 `let` 바인딩, 람다 식에 연결 된 예외 처리기는 `try...with` 식입니다. 자세한 내용은 [일치 식](match-expressions.md)를 [let 바인딩](functions/let-bindings.md), [람다 식: 합니다 `fun` 키워드](functions/lambda-expressions-the-fun-keyword.md), 및 [예외: 합니다 `try...with` 식](exception-handling/the-try-with-expression.md)합니다.

예를 들어를 `match` 식을 *패턴* 파이프 기호 뒤에 오는 됩니다.

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

각 패턴은 어떤 방식으로든에서 입력을 변환 하기 위한 규칙에 따라 작동 합니다. 에 `match` 식에서는 각 패턴은 입력된 데이터의 패턴을 사용 하 여 호환 되는지 확인 하려면 다시 검사 합니다. 일치 하는 항목이 있으면 결과 식에서 실행 됩니다. 일치 하는 항목이 없는 경우 다음 번 패턴 규칙 테스트 됩니다. 선택적 요소인 when *조건을* 부분에 설명 되어 [일치 식](match-expressions.md)합니다.

지원 되는 패턴은 다음 표에 표시 됩니다. 런타임 시 각 테이블에 나열 된 순서로 다음 패턴에 대 한 입력을 테스트 및 패턴은 재귀적으로 적용된에서 처음부터 마지막 코드에 왼쪽에서 오른쪽 패턴에 대해 각 줄에 나타나는 대로 합니다.

|이름|설명|예제|
|----|-----------|-------|
|상수 패턴|모든 숫자, 문자 또는 문자열 리터럴, 열거형 상수, 또는 정의 된 리터럴 식별자|`1.0`, `"test"`, `30`, `Color.Red`|
|식별자 패턴|구별된 된 공용 구조체, 예외 레이블 또는 활성 패턴 case의 case 값|`Some(x)`<br /><br />`Failure(msg)`|
|변수 패턴|*identifier*|`a`|
|`as` 패턴|*패턴* 으로 *식별자*|`(a, b) as tuple1`|
|또는 패턴|*pattern1* &#124; *pattern2*|<code>([h] &#124; [h; _])</code>|
|및 패턴|*pattern1* &amp; *pattern2*|`(a, b) & (_, "test")`|
|Cons 패턴|*identifier* :: *list-identifier*|`h :: t`|
|목록 패턴|[ *pattern_1*; ... ; *pattern_n* ]|`[ a; b; c ]`|
|배열 패턴|[&#124; *pattern_1*;...; *pattern_n* &#124;]|<code>[&#124; a; b; c &#124;]</code>|
|범위 패턴|( *pattern* )|`( a )`|
|튜플 패턴|( *pattern_1*, ... , *pattern_n* )|`( a, b )`|
|레코드 패턴|{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }|`{ Name = name; }`|
|와일드 카드 패턴|_|`_`|
|형식 주석이 함께 포함 된 패턴|*패턴* : *형식*|`a : int`|
|형식 테스트 패턴|:? *형식* [로 *식별자* ]|`:? System.DateTime as dt`|
|Null 패턴|null|`null`|

## <a name="constant-patterns"></a>상수 패턴

상수 패턴은 숫자, 문자 및 문자열 리터럴, 열거형 상수 (열거형 형식의 이름 포함)입니다. `match` 상수 패턴만 있는 식을 다른 언어의 case 문과 비교해 볼 수 있습니다. 입력은 리터럴 값과 비교 하 고 값이 같으면 패턴이 일치 합니다. 리터럴의 형식을 입력의 형식과 호환 되어야 합니다.

다음 예에서는 리터럴 패턴의 사용을 보여 줍니다 및 변수 패턴과 OR 패턴도 사용 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

리터럴 패턴의 또 다른 예로 열거형 상수에 기반을 패턴입니다. 열거형 상수를 사용 하는 경우에 열거형 형식 이름을 지정 해야 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a>식별자 패턴

패턴이 유효한 식별자를 형성 하는 문자 문자열인 경우 식별자의 형식 패턴 일치 하는 방법을 결정 합니다. 식별자는 단일 문자 보다 긴를 대문자로 시작 하는 경우 컴파일러는 식별자 패턴과 일치 여부를 확인 하려고 합니다. 이 패턴의 식별자는 리터럴 특성는 구별 된 공용 구조체 케이스, 예외 식별자 또는 활성 패턴 케이스로 표시 된 값을 수 있습니다. 일치 하는 식별자가 없는 경우 검색이 실패 하 고 패턴 규칙 인 변수 패턴을 입력으로 비교 됩니다.

구별 된 공용 구조체 패턴 간단한 명명 된 case 또는 수는 값 또는 여러 값이 포함 된 튜플을 가질 수 있습니다. 값의 경우 값에 대 한 식별자를 지정 해야 합니다. 튜플의 경우 튜플 패턴에는 튜플의 각 요소에 대 한 식별자 또는 하나에 대 한 필드 이름 포함 하는 식별자를 제공 해야 합니다 또는 이상의 명명 된 공용 구조체 필드입니다. 예제를 보려면이 섹션의 코드 예제를 참조 하세요.

합니다 `option` 이라는 두 케이스가 있는 구별된 된 공용 구조체 유형이 `Some` 고 `None`합니다. 한 가지 경우 (`Some`)에 값은 있지만 다른 (`None`) 명명 된 사례 뿐입니다. 따라서 `Some` 연관 된 값에 대 한 변수를 보유 해야 합니다 `Some` 있지만 `None` 자체적으로 표시 되어야 합니다. 다음 코드에서 변수 `var1` 일치를 통해 얻은 값이 지정 되는 `Some` 사례입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

다음 예제에서는 `PersonName` 구별 된 공용 구조체에 문자열 및 문자 이름의 수 있는 형식을 나타내는 노드가 혼합 되어 있습니다. 구별 된 공용 구조체의 경우가 `FirstOnly`, `LastOnly`, 및 `FirstLast`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

명명 된 필드가 있는 구별 된 공용 구조체, 등호 (=) 사용 하 여 명명된 된 필드의 값을 추출 합니다. 예를 들어, 다음과 같은 선언 사용 하 여 구별된 된 공용 구조체를 것이 좋습니다.

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

패턴 일치 식에서 명명된 된 필드를 다음과 같이 사용할 수 있습니다.

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

명명된 된 필드의 사용은 선택 사항 이므로 이전 예제에서는 둘 다 `Circle(r)` 고 `Circle(radius = r)` 효과 동일 합니다.

세미콜론 (;)를 사용 하 여 여러 필드를 지정 하는 경우를 구분 기호로 사용 합니다.

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

활성 패턴을 사용 하 여 더 복잡 한 사용자 지정 패턴 일치를 정의할 수 있습니다. 활성 패턴에 대 한 자세한 내용은 참조 하세요. [활성 패턴](active-patterns.md)합니다.

식별자가 예외가 있는 경우는 예외 처리기의 컨텍스트에서 일치 하는 패턴에 사용 됩니다. 예외 처리의 패턴 일치에 대 한 자세한 내용은 참조 하세요. [예외: 합니다 `try...with` 식](exception-handling/the-try-with-expression.md)합니다.

## <a name="variable-patterns"></a>변수 패턴

변수 패턴은 오른쪽의 실행 식에 사용할 수 있는 되는 변수 이름에 일치 하는 값을 할당 합니다 `->` 기호입니다. 변수 패턴 만으로도 모든 입력을 일치 하지만 변수 패턴 튜플과 배열 변수를 분해할 수 같은 더 복잡 한 구조체를 사용 하므로 다른 패턴 내에 나타나는 경우가 많습니다.

다음 예제에서는 튜플 패턴 내에서 변수 패턴을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a>as 패턴

합니다 `as` 패턴은 있는 패턴을 `as` 절이 추가 합니다. `as` 절의 실행 식에 사용할 수 있는 이름에 일치 하는 값을 바인딩하는 `match` 식 또는 경우에이 패턴은 사용 하는 위치를 `let` 바인딩, 로컬 범위에 대 한 바인딩으로 이름이 추가 됩니다.

다음 예제에서는 `as` 패턴입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a>또는 패턴

OR 패턴에는 입력된 데이터에는 여러 패턴에 일치 시킬 수 있고 결과적으로 동일한 코드를 실행 하려는 경우 사용 됩니다. OR 패턴의 양쪽 모두의 형식이 호환 되어야 합니다.

다음 예제에서는 OR 패턴을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a>및 패턴

AND 패턴 입력이 두 가지 패턴 일치는 필요 합니다. AND 패턴의 양쪽 모두의 형식이 호환 되어야 합니다.

다음과 같습니다 `detectZeroTuple` 에서처럼 합니다 [튜플 패턴](https://msdn.microsoft.com/library/#tuple) 섹션의 뒷부분에 나오는이 항목에서는 있지만 여기에는 둘 다 `var1` 및 `var2` AND 패턴을 사용 하 여 가져온 값으로.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a>Cons 패턴

Cons 패턴의 첫 번째 요소로 분해 하는 합니다 *헤드*, 및 나머지 요소를 포함 하는 목록을 합니다 *비상*.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a>목록 패턴

목록 패턴 목록을 요소의 수를 분해할 수 있습니다. 목록 패턴 자체에 특정 수의 요소를 이루어진 목록만 일치 시킬 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a>배열 패턴

배열 패턴은 목록 패턴과 비슷하며 및 특정 길이의 배열을 분해를 사용할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a>범위 패턴

패턴을 원하는 대로 결합할 주위의 괄호를 그룹화 할 수 있습니다. 다음 예제에서는 괄호는 여 AND 패턴과 cons 패턴 사이의 결합 관계를 제어 하려면 사용 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a>튜플 패턴

튜플 패턴은 튜플 형식의 입력을 일치 및 패턴 일치는 튜플의 각 위치에 대 한 변수를 사용 하 여 해당 구성 요소로 분해할 수 있습니다.

다음 예제에서는 튜플 패턴을 보여 줍니다 및 리터럴 패턴, 변수 패턴 및 와일드 카드 패턴을 사용 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a>레코드 패턴

레코드 패턴은 필드의 값을 추출 하는 레코드를 분해 하기 위해 사용 됩니다. 패턴을 레코드의 모든 필드를 참조할 필요가 없습니다. 생략된 한 필드는 방금 일치에 참여 하지 않습니다 하 고 추출 되지 않습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a>와일드 카드 패턴

와일드 카드 패턴은 밑줄 표현 (`_`) 문자 및 입력 변수에 할당 대신 삭제 되는 점을 제외 하 고, 변수 패턴과 마찬가지로 모든 입력을 일치 합니다. 와일드 카드 패턴은 대개 다른 패턴 내 자리 표시자로 오른쪽의 식에 필요 하지 않은 값을 `->` 기호입니다. 와일드 카드 패턴 일치 하지 않는 입력을 일치 하도록 패턴 목록의 끝에도 자주 사용 됩니다. 이 항목의 많은 코드 예제에서 와일드 카드 패턴을 보여 줍니다. 앞의 코드에 대 한 예를 참조 하세요.

## <a name="patterns-that-have-type-annotations"></a>형식 주석이 함께 포함 하는 패턴

패턴 형식 주석을 포함할 수 있습니다. 이러한 다른 형식 주석과 마찬가지로 동작 및 다른 형식 주석과 마찬가지로 유추 합니다. 패턴에서 형식 주석을 주위의 괄호 필요 합니다. 다음 코드 형식 주석이 있는 패턴을 보여줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a>형식 테스트 패턴

형식 테스트 패턴 일치 형식에 대해 입력이 됩니다. 입력 형식이 일치 하는 (또는 파생된 형식의) 패턴을 일치 하는 지정 된 형식 성공 합니다.

다음 예제에서는 형식 테스트 패턴을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a>Null 패턴

Null 패턴은 null 값을 허용 하는 형식을 사용 하 여 작업할 때 나타날 수 있는 null 값을 찾습니다. Null 패턴은.NET Framework 코드와 상호 작용할 때 자주 사용 됩니다. 예를 들어,.NET API의 반환 값에 대 한 입력 수를 `match` 식입니다. 반환 값이 null 인지 그리고 반환된 된 값의 기타 특성에 따라 프로그램 흐름을 제어할 수 있습니다. Null 패턴은 전파 프로그램의 나머지 부분에서 null 값을 방지 하기 위해 사용할 수 있습니다.

다음 예제에서는 null 패턴과 변수 패턴을 사용합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a>참고자료

- [일치 식](match-expressions.md)
- [활성 패턴](active-patterns.md)
- [F# 언어 참조](index.md)