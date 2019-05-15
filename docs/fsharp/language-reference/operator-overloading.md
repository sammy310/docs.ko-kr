---
title: 연산자 오버로드
description: 전역 수준에서 클래스 또는 레코드 형식에 산술 연산자를 오버 로드 하는 방법을 알아봅니다 F#입니다.
ms.date: 05/16/2016
ms.openlocfilehash: f4b63818cbdc44d214dca6446162ec9a8922f601
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645356"
---
# <a name="operator-overloading"></a>연산자 오버로드

이 항목에는 전역 수준에서 클래스 또는 레코드 형식에 산술 연산자를 오버 로드 하는 방법을 설명 합니다.

## <a name="syntax"></a>구문

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a>설명

위 구문에는 *연산자 기호* 중 하나인 `+`, `-`, `*`, `/`, `=`등. 합니다 *매개 변수 목록을* 연산자에 대 한 일반적인 구문에 나타나는 순서로 피연산자를 지정 합니다. 합니다 *메서드 본문* 결과 값을 생성 합니다.

연산자에 대 한 연산자 오버 로드는 정적 이어야 합니다. 같은 단항 연산자의 연산자 오버 로드 `+` 및 `-`, 물결표를 사용 해야 합니다 (`~`)에 *연산자 기호* 에서처럼 연산자는 단항 연산자, 이항 연산자가 아니라,을 나타내기 위해 합니다 다음 선언입니다.

```fsharp
static member (~-) (v : Vector)
```

다음 코드에서는 연산자가 두 개뿐인 벡터 클래스를 보여 줍니다. 그 중 하나는 단항 빼기 연산자이고 다른 하나는 스칼라 값을 곱하기 위한 연산자입니다. 예제에서는 두 개의 오버 로드가 스칼라 곱하기 연산자 벡터와 스칼라 나타나는 순서에 관계 없이 작동 해야 하기 때문에 필요 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a>새 운영자 만들기

모든 표준 연산자를 오버 로드할 수 있지만 새 연산자 특정 문자의 시퀀스를 만들 수도 있습니다. 연산자 문자는 허용 `!`, `%`, `&`, `*`, `+`를 `-`, `.`를 `/`, `<`를 `=`, `>`, `?`, `@`, `^`합니다 `|`, 및 `~`합니다. `~` 문자는 연산자 단항 만드는 특별 한 의미가 및 연산자 문자 시퀀스의 일부가 아닙니다. 일부 연산자는 단항을 만들 수 있습니다.

사용할 정확한 문자 시퀀스에 따라 특정 우선 순위 및 결합성에 연산자 해야 합니다. 결합성 왼쪽 또는 오른쪽에서 왼쪽으로 하거나 유지할 수 있습니다 하 고의 우선 순위가 동일한 연산자에 괄호가 없는 순서로 표시 될 때마다 사용 됩니다.

연산자 문자 `.` 예를 들어, 동일한 우선 순위 및 결합성 일반 곱으로 포함 하는 곱하기의 고유한 버전을 정의 하려는 경우 등의연산자만들수있도록우선순위,영향을주지않습니다`.*`.

연산자만 `?` 하 고 `?<-` 로 시작할 수 `?`입니다.

모든 연산자의 우선 순위를 보여 주는 테이블이 F# 에서 찾을 수 있습니다 [기호 및 연산자 참조](symbol-and-operator-reference/index.md)합니다.

## <a name="overloaded-operator-names"></a>오버 로드 된 연산자 이름

경우는 F# 컴파일러 컴파일합니다 연산자 식 연산자에 대 한 컴파일러에서 생성 된 이름을 가진 메서드를 생성 합니다. 이 MSIL (Microsoft intermediate language) 방법의 경우에 리플렉션 및 IntelliSense에 표시 되는 이름입니다. 일반적으로에서 이러한 이름을 사용할 필요가 없습니다 F# 코드입니다.

다음 표에서 표준 연산자를 보여 줍니다. 하 고 해당 이름을 생성 했습니다.

|연산자|생성 된 이름|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|

여기에 나열 되지 않는 연산자의 다른 조합을 연산자로 사용할 수 있고 다음 테이블에서 개별 문자에 대 한 이름을 연결 하 여 구성 된 이름입니다. 예를 들어, +! 가 `op_PlusBang`합니다.

|연산자 문자|이름|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a>접두사 및 중 위 연산자

*접두사* 연산자는 하나 이상의 피연산자는 함수와 비슷하게 앞에 배치 해야 합니다. *위* 연산자는 두 피연산자 사이 배치 해야 합니다.

전위 연산자와 특정 연산자만 사용할 수 있습니다. 일부 연산자는 항상 전위 연산자, 중 위 또는 접두사 수 다른 및 나머지 연산자는 언제나 중 위 `!`를 제외한 `!=`로 시작하는 연산자와 `~` 연산자 또는 `~` 연산자의 반복적인 시퀀스는 항상 전위 연산자입니다. 연산자 `+`, `-`, `+.`, `-.`를 `&`를 `&&`를 `%`, 및 `%%` 전위 연산자 또는 연산자 중 위 일 수 있습니다. 추가 하 여 이러한 연산자의 전위 버전 중 위에서와 구분을 `~` 전위 연산자 정의 될 때 시작 부분에 있습니다. `~` 정의 될 때에 연산자를 사용 하는 경우 사용 되지 않습니다.

## <a name="example"></a>예제

다음 코드는 분수 형식을 구현 하는 오버 로드 된 연산자의 사용을 보여 줍니다. 분수는 분자와 분모 표시 됩니다. 함수 `hcf` 분수를 줄이기 위해 사용 되는 가장 큰 공통 인수를 확인 하는 데 사용 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

**출력:**

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a>전역 수준에서 연산자

또한 전역 수준에서 연산자를 정의할 수 있습니다. 다음 코드는 운영자 정의 `+?`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

위 코드의 출력은 `12`합니다.

규칙에 대 한 범위 지정 하기 때문에이 방식으로 일반 산술 연산자를 재정의할 수 있습니다 F# 는 새로 정의 된 연산자 보다 우선 기본 제공 연산자를 지정 합니다.

키워드 `inline` 호출 코드에 가장 잘 통합 되는 작은 함수는 전역 연산자를 사용 하 여 자주 사용 됩니다. 또한 making 연산자 함수 인라인을 사용 하면 제네릭 정적으로 확인 된 코드를 생성 하기 위해 정적으로 확인 된 형식 매개 변수를 사용 하 여 작업할 수 있도록 합니다. 자세한 내용은 [인라인 함수](functions/inline-functions.md) 하 고 [정적으로 확인 한 형식 매개](generics/statically-resolved-type-parameters.md)합니다.

## <a name="see-also"></a>참고자료

- [멤버](members/index.md)
