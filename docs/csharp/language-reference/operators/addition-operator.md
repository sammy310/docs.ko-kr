---
title: + 연산자 - C# 참조
ms.custom: seodec18
ms.date: 10/22/2018
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 0f04ba837f9c03107acd0b2174cbd07c14a8c213
ms.sourcegitcommit: 8258515adc6c37ab6278e5a3d102d593246f8672
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58504472"
---
# <a name="-operator-c-reference"></a>+ 연산자(C# 참조)

`+` 연산자는 두 개의 형식인 단항 더하기 연산자 또는 이항 더하기 연산자에서 지원됩니다.

## <a name="unary-plus-operator"></a>단항 더하기 연산자

단항 `+` 연산자는 피연산자의 값을 반환합니다. 모든 숫자 형식에서 지원됩니다.

## <a name="numeric-addition"></a>숫자 더하기

숫자 형식의 경우 `+` 연산자는 해당 피연산자의 합계를 계산합니다.

[!code-csharp-interactive[numeric addition](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddNumerics)]

산술 연산자에 대한 자세한 내용은 [산술 연산자](arithmetic-operators.md)를 참조하세요.

## <a name="string-concatenation"></a>문자열 연결

피연산자 중 하나 또는 둘 다가 [문자열](../keywords/string.md) 형식이면 `+` 연산자는 피연산자의 문자열 표현을 연결합니다.

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

C# 6부터 [문자열 보간](../tokens/interpolated.md)은 문자열 형식을 지정하는 더욱 편리한 방법을 제공합니다.

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>대리자 조합

[대리자](../keywords/delegate.md) 형식의 경우 `+` 연산자는 호출될 때 첫 번째 피연산자를 호출한 후 두 번째 피연산자를 호출하는 새 대리자 인스턴스를 반환합니다. 피연산자 중 하나라도 `null`이면 `+` 연산자는 다른 피연산자(`null`일 수도 있음)의 값을 반환합니다. 다음 예제는 `+` 연산자를 사용하여 대리자를 결합하는 방법을 보여 줍니다.

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

대리자 형식에 대한 자세한 내용은 [대리자](../../programming-guide/delegates/index.md)를 참조하세요.

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

사용자 정의 형식은 단항 및 이항 `+` 연산자를 [오버로드](../keywords/operator.md)할 수 있습니다. 이항 `+` 연산자가 오버로드되면 [더하기 대입 연산자](addition-assignment-operator.md) `+=`도 암시적으로 오버로드됩니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [단항 더하기 연산자](~/_csharplang/spec/expressions.md#unary-plus-operator) 및 [더하기 연산자](~/_csharplang/spec/expressions.md#addition-operator) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)
- [문자열 보간](../tokens/interpolated.md)
- [방법: 여러 문자열 연결](../../how-to/concatenate-multiple-strings.md)
- [대리자](../../programming-guide/delegates/index.md)
- [Checked 및 Unchecked](../keywords/checked-and-unchecked.md)
