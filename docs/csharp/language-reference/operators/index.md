---
title: C# 연산자 및 식 - C# 참조
description: C# 연산자 및 식, 연산자 우선 순위와 연산자 결합성에 대해 알아보세요.
ms.date: 08/04/2020
f1_keywords:
- cs.operators
helpviewer_keywords:
- operators [C#]
- operator precedence [C#]
- operator associativity [C#]
- expressions [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 19b5683a7cd334e1203c57fa90d275b659eac873
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556555"
---
# <a name="c-operators-and-expressions-c-reference"></a>C# 연산자 및 식(C# 참조)

C#은 여러 연산자를 제공합니다. 상당수의 연산자는 [기본 제공 형식](../builtin-types/built-in-types.md)에서 지원되며 해당 형식의 값을 사용하여 기본 연산을 수행할 수 있습니다. 해당 연산자는 다음 그룹을 포함합니다.

- [산술 연산자](arithmetic-operators.md): 숫자 피연산자를 사용하여 산술 연산을 수행함
- [비교 연산자](comparison-operators.md): 숫자 피연산자를 비교함
- [부울 논리 연산자](boolean-logical-operators.md): [`bool`](../builtin-types/bool.md) 피연산자를 사용하여 논리 연산을 수행함
- [비트 및 시프트 연산자](bitwise-and-shift-operators.md): 정수 형식의 피연산자를 사용하여 비트 또는 시프트 연산을 수행함
- [같음 연산자](equality-operators.md): 해당 피연산자가 같은지를 확인함

일반적으로 이 연산자들을 [오버로드](operator-overloading.md)할 수 있습니다. 즉, 사용자 정의 형식의 피연산자에 대한 연산자 동작을 지정할 수 있습니다.

가장 간단한 C# 식은 리터럴(예: [정수](../builtin-types/integral-numeric-types.md#integer-literals) 및 [실수](../builtin-types/floating-point-numeric-types.md#real-literals)) 및 변수 이름입니다. 연산자를 사용하여 이들을 복잡한 식으로 결합할 수 있습니다. 연산자 [우선 순위](#operator-precedence) 및 [결합성](#operator-associativity)은 식에서 연산이 수행되는 순서를 결정합니다. 괄호를 사용하여 연산자 우선 순위 및 결합성에 따라 주어진 계산 순서를 변경할 수 있습니다.

다음 코드에서 식의 예는 할당의 오른쪽에 있습니다.

[!code-csharp[expression examples](snippets/Overview.cs#Expressions)]

일반적으로 식은 결과를 생성하고 다른 식에 포함될 수 있습니다. [`void`](../builtin-types/void.md) 메서드 호출은 결과를 생성하지 않는 식의 예입니다. 다음 예에 나와 있는 것처럼 이 메서드 호출은 [문](../../programming-guide/statements-expressions-operators/statements.md)으로만 사용할 수 있습니다.

```csharp
Console.WriteLine("Hello, world!");
```

C#에서 제공하는 몇 가지 다른 종류의 식은 다음과 같습니다.

- [보간된 문자열 식](../tokens/interpolated.md): 다음과 같이 형식 문자열을 만들 수 있는 편리한 구문을 제공합니다.

  [!code-csharp-interactive[interpolated string](snippets/Overview.cs#InterpolatedString)]

- [람다 식](../../programming-guide/statements-expressions-operators/lambda-expressions.md): 다음과 같이 익명 함수를 만들 수 있습니다.

  [!code-csharp-interactive[lambda expression](snippets/Overview.cs#Lambda)]

- [쿼리 식](../keywords/query-keywords.md): 다음과 같이 C#에서 직접 쿼리 기능을 사용할 수 있습니다.

  [!code-csharp-interactive[query expression](snippets/Overview.cs#Query)]

[식 본문 정의](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)를 사용하여 메서드, 생성자, 속성, 인덱서 또는 종료자에 대한 간결한 정의를 제공할 수 있습니다.

## <a name="operator-precedence"></a>연산자 우선 순위

여러 연산자가 있는 식에서 우선 순위가 높은 연산자는 연산자가 우선 순위가 낮은 연산자보다 먼저 계산됩니다. 다음 예제에서는 곱하기가 더하기보다 높은 우선 순위를 가지므로 곱하기가 먼저 수행됩니다.

```csharp-interactive
var a = 2 + 2 * 2;
Console.WriteLine(a); //  output: 6
```

괄호를 사용하여 연산자 우선 순위에 따라 주어진 계산 순서를 변경합니다.

```csharp-interactive
var a = (2 + 2) * 2;
Console.WriteLine(a); //  output: 8
```

다음 표에서는 우선순위가 가장 높은 것부터 시작하여 순서대로 C# 연산자를 나열합니다. 각 행 내의 연산자는 우선 순위가 같습니다.

| 연산자 | 범주 또는 이름 |
| --------- | ---------------- |
| [x.y](member-access-operators.md#member-access-expression-), [f(x)](member-access-operators.md#invocation-expression-), [a&#91;i&#93;](member-access-operators.md#indexer-operator-), [`x?.y`](member-access-operators.md#null-conditional-operators--and-), [`x?[y]`](member-access-operators.md#null-conditional-operators--and-), [x++](arithmetic-operators.md#increment-operator-), [x--](arithmetic-operators.md#decrement-operator---), [x!](null-forgiving.md), [new](new-operator.md), [typeof](type-testing-and-cast.md#typeof-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [nameof](nameof.md), [delegate](delegate-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [x->y](pointer-related-operators.md#pointer-member-access-operator--) | 주 |
| [+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [\!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++x](arithmetic-operators.md#increment-operator-), [--x](arithmetic-operators.md#decrement-operator---), [^x](member-access-operators.md#index-from-end-operator-), [(T)x](type-testing-and-cast.md#cast-expression), [await](await.md), [&x](pointer-related-operators.md#address-of-operator-), [*x](pointer-related-operators.md#pointer-indirection-operator-), [true 및 false](true-false-operators.md) | 단항 |
| [x..y](member-access-operators.md#range-operator-) | 범위 |
| [switch](switch-expression.md) | `switch` 식 |
| [x * y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-) | 곱하기|
| [x + y](arithmetic-operators.md#addition-operator-), [x – y](arithmetic-operators.md#subtraction-operator--) | 더하기 |
| [x \<\<  y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-) | Shift |
| [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-), [is](type-testing-and-cast.md#is-operator), [as](type-testing-and-cast.md#as-operator) | 관계형 및 형식 테스트 |
| [x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-) | 같음 |
| `x & y` | [부울 논리 AND](boolean-logical-operators.md#logical-and-operator-) 또는 [비트 논리 AND](bitwise-and-shift-operators.md#logical-and-operator-) |
| `x ^ y` | [부울 논리 XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) 또는 [비트 논리 XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) |
| <code>x &#124; y</code> | [ OR](boolean-logical-operators.md#logical-or-operator-) 또는 [비트 논리 OR](bitwise-and-shift-operators.md#logical-or-operator-) |
| [x && y](boolean-logical-operators.md#conditional-logical-and-operator-) | 조건부 AND |
| [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) | 조건부 OR |
| [x ?? y](null-coalescing-operator.md) | Null 병합 연산자 |
| [c ? t : f](conditional-operator.md) | 조건 연산자 |
| [x = y](assignment-operator.md), [x += y](arithmetic-operators.md#compound-assignment), [x -= y](arithmetic-operators.md#compound-assignment), [x *= y](arithmetic-operators.md#compound-assignment), [x /= y](arithmetic-operators.md#compound-assignment), [x %= y](arithmetic-operators.md#compound-assignment), [x &= y](boolean-logical-operators.md#compound-assignment), [x &#124;= y](boolean-logical-operators.md#compound-assignment), [x ^= y](boolean-logical-operators.md#compound-assignment), [x <<= y](bitwise-and-shift-operators.md#compound-assignment), [x >>= y](bitwise-and-shift-operators.md#compound-assignment), [x ??= y](null-coalescing-operator.md), [=>](lambda-operator.md) | 할당 및 람다 선언 |

## <a name="operator-associativity"></a>연산자 결합성

연산자의 우선 순위가 같은 경우 연산자의 결합성이 연산이 수행되는 순서를 결정합니다.

- ‘왼쪽 결합성이 있는’ 연산자는 왼쪽에서 오른쪽으로 계산됩니다. [대입 연산자](assignment-operator.md) 및 [null 병합 연산자 ](null-coalescing-operator.md)를 제외하고, 모든 이진 연산자는 왼쪽 결합성이 있습니다. 예를 들어, `a + b - c`는 `(a + b) - c`로 계산됩니다.
- ‘오른쪽 결합성이 있는’ 연산자는 오른쪽에서 왼쪽으로 계산됩니다. 대입 연산자, null 병합 연산자 및 [조건 연산자 `?:`](conditional-operator.md)는 오른쪽 결합성이 있습니다. 예를 들어, `x = y = z`는 `x = (y = z)`로 계산됩니다.

괄호를 사용하여 연산자 결합성에 따라 주어진 계산 순서를 변경합니다.

```csharp-interactive
int a = 13 / 5 / 2;
int b = 13 / (5 / 2);
Console.WriteLine($"a = {a}, b = {b}");  // output: a = 1, b = 6
```

## <a name="operand-evaluation"></a>피연산자 계산

연산자 우선 순위 및 결합성과 관계없이 식의 피연산자는 왼쪽에서 오른쪽으로 계산됩니다. 다음 예제는 연산자와 피연산자가 계산되는 순서를 보여 줍니다.

| 식 | 계산 순서 |
| ---------- | ------------------- |
|`a + b`|a, b, +|
|`a + b * c`|a, b, c, *, +|
|`a / b + c * d`|a, b, /, c, d, *, +|
|`a / (b + c) * d`|a, b, c, +, /, d, *|

일반적으로 모든 연산자 피연산자가 계산됩니다. 그러나 일부 연산자는 조건부로 피연산자를 계산합니다. 즉, 이와 같은 연산자의 첫 번째 피연산자 값이 다른 피연산자를 계산해야 할지 여부 또는 계산해야 할 다른 피연산자를 정의합니다. 이에 해당하는 연산자는 조건부 논리 [AND(`&&`)](boolean-logical-operators.md#conditional-logical-and-operator-) 및 [OR(`||`)](boolean-logical-operators.md#conditional-logical-or-operator-) 연산자, [null 병합 연산자 `??` 및 `??=`](null-coalescing-operator.md), [null 조건부 연산자 `?.` 및 `?[]`](member-access-operators.md#null-conditional-operators--and-), 그리고 [조건 연산자 `?:`](conditional-operator.md)입니다. 자세한 내용은 각 연산자에 관한 설명을 참조하세요.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.

- [식](~/_csharplang/spec/expressions.md)
- [연산자](~/_csharplang/spec/expressions.md#operators)

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [연산자 오버로드](operator-overloading.md)
- [식 트리](../../programming-guide/concepts/expression-trees/index.md)
