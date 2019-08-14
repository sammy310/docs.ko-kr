---
title: C# 연산자 - C# 참조
ms.date: 04/30/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 0e49c28f05d52c704a46806559407381c7eb3530
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971258"
---
# <a name="c-operators-c-reference"></a>C# 연산자(C# 참조)

C#은 기본 제공 형식에서 지원되는 미리 정의된 여러 연산자를 제공합니다. 예를 들어 [산술 연산자](arithmetic-operators.md)는 기본 제공 숫자 형식의 피연산자를 사용하여 산술 연산을 수행하고 [부울 논리 연산자](boolean-logical-operators.md)는 [bool](../keywords/bool.md) 피연산자를 사용하여 논리 연산을 수행합니다.

사용자 정의 형식은 특정 연산자를 오버로드하여 해당 형식의 피연산자에 대한 해당 동작을 정의할 수 있습니다. 자세한 내용은 [연산자 오버로드](operator-overloading.md)를 참조하세요.

다음 표에서는 우선순위가 가장 높은 것부터 시작하여 순서대로 C# 연산자를 나열합니다. 각 행의 연산자는 동일한 우선 순위 수준을 공유합니다.

| 연산자 | 범주 또는 이름 |
| --------- | ---------------- |
| [x.y](member-access-operators.md#member-access-operator-), [x?.y](member-access-operators.md#null-conditional-operators--and-), [x?[y]](member-access-operators.md#null-conditional-operators--and-), [f(x)](member-access-operators.md#invocation-operator-), [a&#91;x&#93;](member-access-operators.md#indexer-operator-), [x++](arithmetic-operators.md#increment-operator-), [x--](arithmetic-operators.md#decrement-operator---), [new](new-operator.md), [typeof](type-testing-and-conversion-operators.md#typeof-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [nameof](nameof.md), [delegate](delegate-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [->](pointer-related-operators.md#pointer-member-access-operator--) | 기본 연산자 |
| [+x](addition-operator.md), [-x](subtraction-operator.md), [\!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++x](arithmetic-operators.md#increment-operator-), [--x](arithmetic-operators.md#decrement-operator---), [(T)x](type-testing-and-conversion-operators.md#cast-operator-), [await](../keywords/await.md), [&x](pointer-related-operators.md#address-of-operator-), [*x](pointer-related-operators.md#pointer-indirection-operator-), [true 및 false](true-false-operators.md) | 단항 |
| [x * y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-) | 곱하기|
| [x + y](arithmetic-operators.md#addition-operator-), [x – y](arithmetic-operators.md#subtraction-operator--) | 더하기 |
| [x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-) | 시프트 |
| [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-), [is](type-testing-and-conversion-operators.md#is-operator), [as](type-testing-and-conversion-operators.md#as-operator) | 관계형 및 형식 테스트 |
| [x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-) | 같음 |
| `x & y` | [부울 논리 AND](boolean-logical-operators.md#logical-and-operator-) 또는 [비트 논리 AND](bitwise-and-shift-operators.md#logical-and-operator-) |
| `x ^ y` | [부울 논리 XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) 또는 [비트 논리 XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) |
| <code>x &#124; y</code> | [ OR](boolean-logical-operators.md#logical-or-operator-) 또는 [비트 논리 OR](bitwise-and-shift-operators.md#logical-or-operator-) |
| [x && y](boolean-logical-operators.md#conditional-logical-and-operator-) | 조건부 AND |
| [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) | 조건부 OR |
| [x ?? y](null-coalescing-operator.md) | Null 병합 연산자 |
| [t ? x : y](conditional-operator.md) | 조건 연산자 |
| [x = y](assignment-operator.md), [x += y](arithmetic-operators.md#compound-assignment), [x -= y](arithmetic-operators.md#compound-assignment), [x *= y](arithmetic-operators.md#compound-assignment), [x /= y](arithmetic-operators.md#compound-assignment), [x %= y](arithmetic-operators.md#compound-assignment), [x &= y](boolean-logical-operators.md#compound-assignment), [x &#124;= y](boolean-logical-operators.md#compound-assignment), [x ^= y](boolean-logical-operators.md#compound-assignment), [x <<= y](bitwise-and-shift-operators.md#compound-assignment), [x >>= y](bitwise-and-shift-operators.md#compound-assignment), [=>](lambda-operator.md) | 할당 및 람다 선언 |

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [연산자](../../programming-guide/statements-expressions-operators/operators.md)
