---
title: () 연산자 - C# 참조
ms.custom: seodec18
ms.date: 01/15/2019
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 8f7382a49c81b6fd8e104b864ffc2f70db7fe4a6
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758116"
---
# <a name="-operator-c-reference"></a>() 연산자(C# 참조)

괄호 `()`는 일반적으로 메서드 또는 대리자 호출이나 캐스트 식에 사용됩니다.

또한 괄호를 사용하여 식에서 연산을 계산하는 순서를 지정합니다. 자세한 내용은 [연산자](../../programming-guide/statements-expressions-operators/operators.md) 문서의 [괄호 추가](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) 섹션을 참조하세요. 우선 순위 수준에 따라 정렬된 연산자 목록은 [C# 연산자](index.md)를 참조하세요.

## <a name="method-invocation"></a>메서드 호출

다음 예제는 인수를 사용하거나 사용하지 않고 메서드를 호출하는 방법과 대리자를 호출하는 방법을 보여 줍니다.

[!code-csharp-interactive[use for invocation](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Invocation)]

[`new`](../keywords/new-operator.md) 연산자를 사용하여 [생성자](../../programming-guide/classes-and-structs/constructors.md)를 호출하는 경우에도 괄호를 사용합니다.

메서드에 대한 자세한 내용은 [메서드](../../programming-guide/classes-and-structs/methods.md)를 참조하세요. 대리자에 대한 자세한 내용은 [대리자](../../programming-guide/delegates/index.md)를 참조하세요.

## <a name="cast-expression"></a>캐스트 식

`(T)E` 형태의 캐스트 식은 변환 연산자를 호출하여 식 `E`의 값을 `T` 형식으로 변환합니다. `E` 형식에서 `T` 형식으로의 명시적 변환이 없는 경우 컴파일 시간 오류가 발생합니다. 변환 연산자를 정의하는 방법에 대한 자세한 내용은 [explicit](../keywords/explicit.md) 및 [implicit](../keywords/implicit.md) 키워드 문서를 참조하세요.

다음 예제는 숫자 형식 간의 형식 변환을 보여 줍니다.

[!code-csharp-interactive[use for cast](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Cast)]

숫자 형식 간에 미리 정의된 명시적 변환에 대한 자세한 내용은 [명시적 숫자 변환 표](../keywords/explicit-numeric-conversions-table.md)를 참조하세요.

자세한 내용은 [캐스팅 및 형식 변환](../../programming-guide/types/casting-and-type-conversions.md)과 [변환 연산자](../../programming-guide/statements-expressions-operators/conversion-operators.md)를 참조하세요.

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

`()` 연산자를 오버로드할 수 없습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [호출 식](~/_csharplang/spec/expressions.md#invocation-expressions) 및 [캐스트 식](~/_csharplang/spec/expressions.md#cast-expressions) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)
