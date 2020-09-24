---
description: '?: 연산자 - C# 참조'
title: '?: 연산자 - C# 참조'
ms.date: 09/17/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: b6add045983619169bed0cd9f32eb27dba0a0338
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738881"
---
# <a name="-operator-c-reference"></a>?: 연산자(C# 참조)

3개로 구성된 조건부 연산자라고도 하는 조건부 연산자 `?:`은 부울 식을 계산하고 부울 식이 `true` 또는 `false`으로 계산되는지에 따라 두 식 중 하나의 계산 결과를 반환합니다.

조건 연산자의 구문은 다음과 같습니다.

```csharp
condition ? consequent : alternative
```

`condition` 식은 `true` 또는 `false`로 계산되어야 합니다. `condition`이 `true`로 계산되면 `consequent` 식이 계산되고 해당 결과가 연산 결과가 됩니다. `condition`이 `false`로 계산되면 `alternative` 식이 계산되고 해당 결과가 연산 결과가 됩니다. `consequent` 또는 `alternative`만 계산됩니다.

C# 9.0부터 조건식은 대상으로 유형화됩니다. 즉, 조건식의 대상 유형을 알고 있는 경우 `consequent` 및 `alternative`의 형식은 다음 예제와 같이 대상 유형으로 암시적으로 변환 가능해야 합니다.

[!code-csharp[target-typed conditional](snippets/shared/ConditionalOperator.cs#TargetTyped)]

조건식의 대상 유형을 모르는 경우(예: [`var`](../keywords/var.md) 키워드 사용) 또는 C# 8.0 이하에서 `consequent` 및 `alternative`의 형식이 같아야 하거나 한 형식에서 다른 형식으로 암시적인 변환이 있어야 합니다.

[!code-csharp[not target-typed conditional](snippets/shared/ConditionalOperator.cs#NotTargetTyped)]

조건부 연산자는 오른쪽 결합성입니다. 즉, 다음 형식의 식을 가정해 보세요.

```csharp
a ? b : c ? d : e
```

이 식은 다음과 같이 계산됩니다.

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> 다음과 같은 니모닉 디바이스를 사용하여 조건부 연산자의 평가 방식을 기억할 수 있습니다.
>
> ```text
> is this condition true ? yes : no
> ```

다음 예제에서는 조건부 연산자의 사용법을 보여 줍니다.

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a>조건부 ref 식

C# 7.2부터 조건부 ref 식으로 [ref 지역](../keywords/ref.md#ref-locals) 또는 [ref readonly 지역](../keywords/ref.md#ref-readonly-locals) 변수를 조건부로 할당할 수 있습니다. 조건부 ref 식을 [참조 반환 값](../keywords/ref.md#reference-return-values) 또는 [`ref` 메서드 인수](../keywords/ref.md#passing-an-argument-by-reference)로 사용할 수도 있습니다.

조건부 ref 식의 구문은 다음과 같습니다.

```csharp
condition ? ref consequent : ref alternative
```

원래 조건부 연산자와 마찬가지로 조건부 ref 식은 두 식 중 하나(`consequent` 또는 `alternative`)만 계산합니다.

조건부 ref 식의 경우 `consequent` 및 `alternative`의 형식이 동일해야 합니다. 조건부 ref 식은 대상으로 유형화되지 않습니다.

다음 예제에서는 조건부 ref 식의 사용법을 보여 줍니다.

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a>조건부 연산자 및 `if..else` 문

[if-else](../keywords/if-else.md) 문보다 조건부 연산자를 사용하면 조건부로 값을 컴퓨팅해야 하는 경우 코드가 보다 간결해질 수 있습니다. 다음 예제에서는 정수를 음수 또는 음수가 아닌 값으로 분류하는 두 가지 방법을 보여 줍니다.

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

사용자 정의 형식으로 조건부 연산자를 오버로드할 수 없습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [조건부 연산자](~/_csharplang/spec/expressions.md#conditional-operator) 섹션을 참조하세요.

C# 7.2 이상에 추가된 기능에 대한 자세한 내용은 다음 기능 제안 노트를 참조하세요.

- [조건부 ref 식(C# 7.2)](~/_csharplang/proposals/csharp-7.2/conditional-ref.md)
- [대상으로 유형화된 조건식(C# 9.0)](~/_csharplang/proposals/csharp-9.0/target-typed-conditional-expression.md)

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 연산자 및 식](index.md)
- [if-else 문](../keywords/if-else.md)
- [?. 및 ?[] 연산자](member-access-operators.md#null-conditional-operators--and-)
- [및 ??= 연산자](null-coalescing-operator.md)
- [ref 키워드](../keywords/ref.md)
