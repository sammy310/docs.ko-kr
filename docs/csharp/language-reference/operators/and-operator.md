---
title: '&amp; 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 67d60709e1c6c76071ecfb7aac74c83dec6f372a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310046"
---
# <a name="amp-operator-c-reference"></a>&amp; 연산자(C# 참조)

`&` 연산자는 단항 주소 연산자 또는 이진 논리 연산자의 두 가지 형식으로 지원됩니다.

## <a name="unary-address-of-operator"></a>단항 주소 연산자

단항 `&` 연산자는 해당 피연산자의 주소를 반환합니다. 자세한 내용은 [방법: 변수의 주소 가져오기](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md)를 참조하세요.

주소 연산자 `&`에 [안전하지 않은](../keywords/unsafe.md) 컨텍스트가 필요합니다.

## <a name="integer-logical-bitwise-and-operator"></a>정수 논리적 비트 AND 연산자

정수 형식의 경우 `&` 연산자는 해당 피연산자의 논리적 비트 AND를 계산합니다.

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> 앞의 예제에서는 [C# 7.0에서 도입](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements)되고 [C# 7.2에서 향상](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals)된 이진 리터럴을 사용합니다.

정수 형식에 대한 작업은 일반적으로 열거형 형식에서 허용되므로 `&` 연산자는 [enum](../keywords/enum.md) 피연산자도 지원합니다.

## <a name="boolean-logical-and-operator"></a>부울 논리 AND 연산자

[bool](../keywords/bool.md) 피연산자의 경우 `&` 연산자는 피 연산자의 논리 AND를 계산합니다. `x` 및 `y`가 모두 `true`인 경우 `x & y`의 결과는 `true`입니다. 그렇지 않으면 결과는 `false`입니다.

첫 번째 피연산자가 `false`로 평가되더라도 `&` 연산자는 두 피연산자를 평가하여 두 번째 피연산자의 값에 관계없이 `false`이어야 합니다. 다음 예제에서는 해당 동작을 보여줍니다.

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

[조건부 AND 연산자](boolean-logical-operators.md#conditional-logical-and-operator-) `&&`도 해당 피연산자의 논리 AND를 컴퓨팅하지만, 첫 번째 피연산자가 `false`로 평가되는 경우에는 두 번째 피연산자를 평가하지 않습니다.

nullable bool 피연산자의 경우 `&` 연산자는 동작은 SQL의 값이 세 개인 논리와 일치합니다. 자세한 내용은 [부울 논리 연산자](boolean-logical-operators.md) 문서의 [Nullable 부울 논리 연산자](boolean-logical-operators.md#nullable-boolean-logical-operators) 섹션을 참조하세요.

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

사용자 정의 형식에는 이진 `&` 연산자를 [오버로드](../keywords/operator.md)할 수 있습니다. 이진 `&` 연산자가 오버로드되면 [AND 할당 연산자](and-assignment-operator.md) `&=`도 암시적으로 오버로드됩니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [주소 연산자](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) 및 [논리 연산자](~/_csharplang/spec/expressions.md#logical-operators) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)
- [부울 논리 연산자](boolean-logical-operators.md)
- [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [| 연산자](or-operator.md)
- [^ 연산자](xor-operator.md)
- [~ 연산자](bitwise-complement-operator.md)
