---
title: let 바인딩
description: 사용 하는 방법을 알아봅니다는 F# 'let' 바인딩 값 또는 함수를 사용 하 여 식별자를 연결 하는 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: 45de82acf6f4423698cd8037266968e023f40dcb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941007"
---
# <a name="let-bindings"></a>let 바인딩

A *바인딩* 식별자 값 또는 함수를 연결 합니다. 사용할는 `let` 값 또는 함수에 이름을 바인딩할 키워드입니다.

## <a name="syntax"></a>구문

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>설명

`let` 키워드 또는 이름 하나 이상에 대 한 함수 값을 정의 하는 바인딩 식에 사용 됩니다. 가장 간단한 형태의 `let` 식에 이름을 바인딩하는 간단한 값을 다음과 같이 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

새 줄을 사용 하 여 식의 식별자를 구분 하는 경우 다음 코드와 같이 식의 각 줄을 들여쓰기 해야 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

단순한 이름 대신 이름을 포함 하는 패턴을 지정할 수 있습니다, 예를 들어, 튜플, 다음 코드와 같이 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

합니다 *식 본문* 이름이 사용 되는 식입니다. 본문 식에서 첫 번째 문자를 사용 하 여 정확 하 게 구성 줄 들여쓰기 자체 줄에 표시 된 `let` 키워드:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

`let` 바인딩 수 수준에 나타날 모듈, 클래스 형식 정의에서 나 로컬 범위에서 함수 정의와 같이 합니다. `let` 최상위 수준 모듈 또는 클래스 형식에 바인딩 본문 식을에 필요 하지는 않지만 다른 범위 수준에서 본문 식이 필요 합니다. 바인딩된 이름을 정의 하면서 전 시점에는 없는 지점 이후에 사용할 수는 `let` 다음 코드 에서처럼 바인딩 표시 됩니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a>함수 바인딩

다음 코드와 같이 함수 이름 및 매개 변수를 함수 바인딩을 포함 한다는 함수 바인딩 값 바인딩에 대 한 규칙을 따릅니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

일반적으로 매개 변수는 튜플 패턴 같은 패턴.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

`let` 바인딩 식 마지막 식의 값을 반환 합니다. 다음 코드 예제에서는 값에 따라서 `result` 에서 계산 됩니다 `100 * function3 (1, 2)`를 반환 하는 `300`합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

자세한 내용은 [함수](index.md)를 참조하세요.

## <a name="type-annotations"></a>형식 주석

괄호 안에 포함 된 모든 형식 이름 뒤에 오는 콜론 (:)를 포함 하 여 형식 매개 변수를 지정할 수 있습니다. 또한 마지막 매개 변수 뒤에 콜론과 형식을 추가 하 여 반환 값의 형식을 지정할 수 있습니다. 전체 형식 주석은 `function1`, 매개 변수 형식으로 정수를 사용 하 여은 다음과 같을 수 있습니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

명시적 형식 매개 변수가 없는 경우 함수 매개 변수의 형식을 확인할 형식을 유추가 됩니다. 제네릭으로 매개 변수의 형식을 자동으로 일반화 포함할 수 있습니다.

자세한 내용은 [자동 일반화](../generics/automatic-generalization.md) 하 고 [Typeinference](../type-inference.md)합니다.

## <a name="let-bindings-in-classes"></a>클래스의 let 바인딩

`let` 바인딩 구조체 또는 레코드 종류는 있지만 클래스 형식에 나타날 수 있습니다. 클래스 형식에 바인딩 let을 사용 하려면 클래스에 기본 생성자가 있어야 합니다. 생성자 매개 변수는 클래스 정의의 형식 이름 뒤에 나타나야 합니다. A `let` 전용 필드 및 해당 클래스 형식 및 함께 멤버 클래스 형식에 대 한 바인딩 정의 `do` 형식에서 바인딩 유형에 대 한 기본 생성자의 코드를 형성 합니다. 다음 코드 예제에서는 클래스를 보여 줍니다 `MyClass` 전용 필드를 사용 하 여 `field1` 고 `field2`입니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

범위 `field1` 고 `field2` 선언 된 형식으로 제한 됩니다. 자세한 내용은 참조 하세요. [ `let` 클래스에서 바인딩을](../members/let-bindings-in-classes.md) 하 고 [클래스](../classes.md)합니다.

## <a name="type-parameters-in-let-bindings"></a>형식 매개 변수에 let 바인딩

`let` 계산 식 또는 형식의 모듈 수준에서 바인딩 명시적 형식 매개 변수를 가질 수 있습니다. Let 식에서 함수 정의 내에서 같은 바인딩을 형식 매개 변수를 사용할 수 없습니다. 자세한 내용은 [제네릭](../generics/index.md)을 참조하세요.

## <a name="attributes-on-let-bindings"></a>특성의 let 바인딩

특성은 최상위에 적용할 수 있습니다 `let` 모듈에서는 다음 코드 에서처럼 바인딩.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a>범위 및 액세스 가능성의 Let 바인딩

Let 바인딩을 사용 하 여 선언 된 엔터티의 범위를 포함 하는 부분으로 제한 됩니다 바인딩은 표시 되 면 (예: 함수, 모듈, 파일 또는 클래스)의 범위입니다. 따라서 해당 한다고 할 수 있습니다 let 바인딩 범위로 이름을 새로 추가 합니다. 모듈의 let 바인딩 값 또는 함수는 모듈의 클라이언트에서 액세스할 수 한 모듈은 모듈의 공용 함수로 컴파일된 모듈의 let 바인딩 때문에 액세스할 수 합니다. 반면, 클래스의 let 바인딩에 private 클래스입니다.

일반적으로 모듈의 함수에에서는 클라이언트 코드에서 사용 하는 경우 모듈의 이름으로 한정 되어야 합니다. 예를 들어 모듈 `Module1` 함수가 `function1`, 사용자 지정 `Module1.function1` 함수를 가리킵니다.

사용자가 모듈의 모듈 이름으로 한정 되지 않고 해당 모듈 내 함수 사용 하기 위해 사용할 수 있도록 내보내기 선언은 사용할 수 있습니다. 위에서 언급 한 예에서 사용자 모듈의 열 수 있습니다이 경우 모듈 가져오기 선언 열기를 사용 하 여 `Module1` 이후에 참조 및 `function1` 직접.

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

일부 모듈 특성이 [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), 즉, 노출 되는 함수는 모듈의 이름으로 한정 되어야 합니다. 예를 들어는 F# 특성이이 목록 모듈입니다.

모듈 및 액세스 제어에 대 한 자세한 내용은 참조 하세요. [모듈](../modules.md) 하 고 [Access Control](../access-control.md)합니다.

## <a name="see-also"></a>참고자료

- [함수](index.md)
- [클래스의 `let` 바인딩](../members/let-bindings-in-classes.md)