---
title: 코드 인용
description: 에 대해 알아봅니다 F# 코드 인용을 생성 하 여 작업할 수 있는 언어 기능 F# 식에 프로그래밍 방식으로 코드입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 464df5e3fafa683c93fd5fb6e94d24c229903491
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641997"
---
# <a name="code-quotations"></a>코드 인용

> [!NOTE]
> API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

이 항목에 설명 합니다 *코드 인용*를 생성 하 여 작업할 수 있도록 언어 기능을 F# 식을 프로그래밍 방식으로 코드입니다. 이 기능은 사용 하는 추상 구문 트리를 생성할 수 있습니다. F# 코드입니다. 추상 구문 트리 트래버스 고 응용 프로그램의 필요에 따라 처리 될 수 있습니다. 예를 들어, 생성 하는 트리를 사용할 수 있습니다 F# 코드 또는 다른 언어로 코드를 생성 합니다.

## <a name="quoted-expressions"></a>따옴표 붙은 식

*인용 된 식* 됩니다는 F# 프로그램의 일부로 컴파일되지 않은 방식으로 구분 된 하지만 대신 나타내는 개체로 컴파일된 코드에서 식은 F# 식입니다. 따옴표 붙은 식에서 두 가지 방법 중 하나를 표시할 수 있습니다: 형식 정보를 사용 하 여 만들거나 형식 정보가 없는 합니다. 기호를 사용 하는 형식 정보를 포함 하려는 경우 `<@` 및 `@>` 인용된 식을 구분 합니다. 기호를 사용 하는 형식 정보를 필요 하지 않은 경우 `<@@` 고 `@@>`입니다. 다음 코드는 형식화 및 형식화 되지 않은 따옴표를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

큰 식 트리를 트래버스하 빠릅니다 형식 정보가 포함 되지 않습니다. 형식화 된 기호를 사용 하 여 따옴표 붙은 식의 결과 형식은 `Expr<'T>`, 형식 매개 변수를 기준으로 식의 형식에는 F# 컴파일러의 형식 유추 알고리즘입니다. 따옴표 붙은 식의 형식이 제네릭이 아닌 형식의 형식 정보 없이 코드 인용을 사용 하면 [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65)합니다. 호출할 수 있습니다 합니다 [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) 형식화 된 속성 `Expr` 클래스는 형식화 되지 않은 가져오려고 `Expr` 개체입니다.

다양 한 정적 메서드를 생성할 수 있도록 F# 식에 프로그래밍 방식으로 개체를 `Expr` 클래스를 사용 하지 않고 따옴표 붙은 식입니다.

참고 코드 인용에는 전체 식이 포함 되어야 합니다. 에 대 한는 `let` 바인딩, 예를 들어 해야 바인딩된 이름 및 바인딩을 사용 하는 추가 식을 정의 합니다. 자세한 구문에서이 뒤에 오는 식의 `in` 키워드입니다. 모듈의 최상위 수준에서 모듈에서 다음 식은 바로 이것이 이지만 인용에 명시적으로 필요 합니다.

따라서 다음 식은 올바르지 않습니다.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

하지만 다음 식은 유효 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

코드 인용을 사용 하려면 가져오기 선언 추가 해야 합니다 (사용 하 여 합니다 `open` 키워드) 열리는 합니다 [Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2) 네임 스페이스입니다.

F# PowerPack 지 평가 하 고 실행 F# 식 개체입니다.

## <a name="expr-type"></a>Expr 형식

인스턴스를 `Expr` 나타내는 입력는 F# 식입니다. 제네릭 및 제네릭이 아닌 `Expr` 형식에 설명 된는 F# 라이브러리 설명서를 참조 합니다. 자세한 내용은 [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) 하 고 [Quotations.Expr 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d)합니다.

## <a name="splicing-operators"></a>결합 연산자

스플라이스를 사용 하면 프로그래밍 방식으로 또는 다른 코드 인용에 만든 식 사용 하 여 리터럴 코드 인용을 결합할 수 있습니다. `%` 하 고 `%%` 연산자를 사용 하면 추가할 수는 F# 코드 인용에 식 개체입니다. 사용할 합니다 `%` 형식의 식 개체를 형식화 된 따옴표로 삽입 연산자를 사용 하 여는 `%%` 는 형식화 되지 않은 따옴표에 형식화 되지 않은 식 개체를 삽입 하는 연산자. 두 연산자는 단항 전위 연산자입니다. 따라서 경우 `expr` 형식의 형식화 되지 않은 식 `Expr`, 다음 코드는 유효 합니다.

```fsharp
<@@ 1 + %%expr @@>
```

경우에 `expr` 형식의 형식화 된 견적 `Expr<int>`, 다음 코드는 유효 합니다.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 예제에서는 적용할 코드 인용의 사용을 보여 줍니다. F# 코드를 expression 개체를 한 다음 인쇄를 F# expression을 나타내는 코드입니다. 함수 `println` 정의 된 재귀 함수를 포함 하는 `print` 표시 하는 F# expression 개체 (형식의 `Expr`) 친숙 한 형식입니다. 여러 활성 패턴은는 [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) 하 고 [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) 식 개체를 분석 하는 모듈입니다. 이 예제에 표시 될 수 있는 모든 패턴을 다루지 않습니다는 F# 식입니다. 패턴 와일드 카드 패턴 일치를 트리거 인식 되지 않은 (`_`) 하 고 사용 하 여 렌더링 되는 `ToString` 메서드는에 `Expr` 입력을 일치 식에 추가할 활성 패턴을 확인할 수 있습니다.

### <a name="code"></a>코드

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a>출력

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>예제

### <a name="description"></a>설명

세 가지 활성 패턴을 사용할 수도 있습니다는 [ExprShape 모듈](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) 적은 활성 패턴을 사용 하 여 식 트리. 이러한 활성 패턴 트리 트래버스 하려고 하지만 노드의 대부분에서 모든 정보를 수행 해야 하는 경우 유용할 수 있습니다. 사용 하는 경우 이러한 패턴을 모든 F# 식의 다음 세 가지 패턴 중 하 나와 일치: `ShapeVar` 식이 변수에 `ShapeLambda` 식이 람다 식 또는 `ShapeCombination` 식이 다른 경우. 더 많은 패턴을 사용 하 여 모든 가능한 처리 해야 하는 이전 코드 예제와 같이 활성 패턴을 사용 하 여 식 트리를 이동 하는 경우 F# 식 형식 및 코드는 더 복잡 한 됩니다. 자세한 내용은 [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination 활성 패턴](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d)합니다.

다음 코드 예제에서는 보다 복잡 한 순회에 대 한 기준으로 사용할 수 있습니다. 이 코드에서는 함수 호출을 포함 하는 식에 대 한 식 트리로 만들어집니다 `add`합니다. 합니다 [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) 활성 패턴에 대 한 호출과 검색 하는 `add` 식 트리에서 합니다. 이 활성 패턴에 대 한 호출의 인수를 할당 합니다 `exprList` 값입니다. 이 경우 두 가지 유형만 있습니다를 끌어내기이 고 함수는 인수에 재귀적으로 호출 됩니다. 결과에 대 한 호출을 나타내는 코드 인용에 삽입 됩니다 `mul` 결합 연산자를 사용 하 여 (`%%`). `println` 이전 예제의 함수 결과 표시 하는 합니다.

다른 활성 패턴 분기의 코드에 동일한 식 트리를 결과 식에서 유일한 변경 내용은 변경 이므로 다시 생성 `add` 에 `mul`입니다.

### <a name="code"></a>코드

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a>출력

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
