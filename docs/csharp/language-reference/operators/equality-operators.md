---
title: 같음 연산자 - C# 참조
description: C# 같음 비교 연산자에 대해 알아봅니다.
ms.date: 03/28/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: f60d62d1823a8bd06b0417638719a81e95d7438b
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267691"
---
# <a name="equality-operators-c-reference"></a>같음 연산자(C# 참조)

[`==`(같음)](#equality-operator-) 및 [`!=`(같지 않음)](#inequality-operator-) 연산자는 피연산자가 같은지 여부를 확인합니다.

## <a name="equality-operator-"></a>같음 연산자 ==

같음 연산자 `==`는 피연산자가 같으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.

### <a name="value-types-equality"></a>값 형식 같음

[기본 제공 값 형식](../keywords/value-types-table.md)의 피연산자는 해당 값이 같은 경우 동일합니다.

[!code-csharp-interactive[value types equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> `==`, [, `<`, `>`, `<=` 및 `>=`](comparison-operators.md) 연산자의 경우 피연산자 중 하나가 숫자(<xref:System.Double.NaN?displayProperty=nameWithType> 또는 <xref:System.Single.NaN?displayProperty=nameWithType>)가 아니면 연산의 결과는 `false`입니다. 즉, `NaN` 값이 `NaN`를 포함한 다른 `double`(또는 `float`) 값보다 크거나, 작거나, 같지 않습니다. 자세한 내용과 예제는 <xref:System.Double.NaN?displayProperty=nameWithType> 또는 <xref:System.Single.NaN?displayProperty=nameWithType> 참조 문서를 참조하세요.

기본 정수 형식의 해당 값이 같은 경우 동일한 [열거형](../keywords/enum.md) 형식의 피연산자가 동일합니다.

사용자 정의 [구조체](../keywords/struct.md) 형식은 기본적으로 `==` 연산자를 지원하지 않습니다. `==` 연산자를 지원하려면 사용자 정의 구조체가 해당 연산자를 [오버로드](#operator-overloadability)해야 합니다.

C# 7.3부터는 `==` 및 `!=` 연산자가 C# [튜플](../../tuples.md)에서 지원됩니다. 자세한 내용은 [C# 튜플 형식](../../tuples.md) 문서의 [같음 및 튜플](../../tuples.md#equality-and-tuples) 섹션을 참조하세요.

### <a name="string-equality"></a>문자열 같음

두 개의 [문자열](../keywords/string.md) 피연산자가 모두 `null`이거나 두 문자열 인스턴스가 같은 길이고 각 문자 위치에 동일한 문자가 있을 때 동일합니다.

[!code-csharp-interactive[string equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#StringEquality)]

대/소문자 구분 서수 비교입니다. 문자열 비교에 대한 자세한 내용은 [C#에서 문자열을 비교하는 방법](../../how-to/compare-strings.md)을 참조하세요.

### <a name="reference-types-equality"></a>참조 형식 같음

동일한 개체를 참조하는 경우 `string` 참조 형식 피연산자가 아닌 두 개의 피연산자가 동일합니다.

[!code-csharp[reference type equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ReferenceTypesEquality)]

이 예제에서 표시한 대로 사용자 지정 참조 형식은 기본적으로 `==` 연산자를 지원합니다. 그러나 사용자 정의 참조 형식은 `==` 연산자를 오버로드할 수 있습니다. 참조 형식이 `==` 연산자를 오버로드하는 경우 <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> 메서드를 사용하여 해당 형식의 두 참조가 동일한 개체를 참조하는지 확인합니다.

## <a name="inequality-operator-"></a>같지 않음 연산자 !=

같지 않음 연산자 `!=`는 피연산자가 같지 않으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다. [기본 제공 형식](../keywords/built-in-types-table.md)의 피연산자의 경우 식 `x != y`는 식 `!(x == y)`와 동일한 결과를 생성합니다. 형식 같음에 대한 자세한 내용은 [같음 연산자](#equality-operator-) 섹션을 참조하세요.

다음 예제에서는 `!=` 연산자의 사용법을 보여 줍니다.

[!code-csharp-interactive[non-equality examples](~/samples/csharp/language-reference/operators/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

사용자 정의 형식은 `==` 및 `!=` 연산자를 [오버로드](../keywords/operator.md)할 수 있습니다. 형식이 두 연산자 중 하나를 오버로드하는 경우 나머지 연산자도 오버로드해야 합니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [관계형 및 형식 테스트 연산자](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 연산자](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [같음 비교](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [비교 연산자](comparison-operators.md)
