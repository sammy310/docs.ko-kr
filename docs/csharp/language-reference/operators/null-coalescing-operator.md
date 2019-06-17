---
title: ?? 연산자 - C# 참조
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 8ca97261b348b7813ab179abbc1f2c5f535966a1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816014"
---
# <a name="-operator-c-reference"></a>?? 연산자(C# 참조)

null 병합 연산자 `??`는 `null`이 아닌 경우 왼쪽 피연산자의 값을 반환합니다. 그렇지 않으면 오른쪽 피연자를 평가하고 그 결과를 반환합니다. 왼쪽 피연산자가 null이 아닌 것으로 평가되면 `??` 연산자는 오른쪽 피연산자를 평가하지 않습니다.

null 병합 연산자는 오른쪽 결합성입니다. 즉, 다음 형식의 식을 가정해 보세요.

```csharp
a ?? b ?? c
```

이 식은 다음과 같이 계산됩니다.

```csharp
a ?? (b ?? c)
```

`??` 연산자는 다음과 같은 시나리오에서 유용할 수 있습니다.

- [null 병합 연산자 ?. 및 ?[]](member-access-operators.md#null-conditional-operators--and-)가 있는 식에서 null 병합 연산자를 사용하여 null 조건부 연산을 사용한 식의 결과가 `null`인 경우 평가하는 대체 식을 제공할 수 있습니다.

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- [nullable 값 형식](../../programming-guide/nullable-types/index.md)을 사용하고 기본값 유형의 값을 제공해야 할 때 null 병합 연산자를 사용하여 nullable 값이 `null`인 경우 제공할 값을 지정합니다.

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  nullable 형식 값이 `null`일 때 사용될 값이 기본 값 형식의 기본 값이어야 하는 경우 <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> 메서드를 사용합니다.

- C# 7.0부터 null 병합 연산자의 오른쪽 피연산자로 [`throw` 식](../keywords/throw.md#the-throw-expression)을 사용하여 인수 확인 코드를 보다 간결하게 만들 수 있습니다.

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  앞의 예제에서는 [식 본문 멤버](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)를 사용하여 속성을 정의하는 방법도 보여줍니다.

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

null 병합 연산자를 오버로드할 수 없습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [null 병합 연산자](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)
- [?. 및 ?[] 연산자](member-access-operators.md#null-conditional-operators--and-)
- [?: 연산자](conditional-operator.md)
