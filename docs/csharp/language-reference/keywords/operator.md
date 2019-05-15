---
title: 연산자 키워드 - C# 참조
ms.custom: seodec18
description: 기본 제공 C# 연산자를 오버로드하는 방법 알아보기
ms.date: 08/27/2018
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: 47ce91c343092ac2f7555c1edf3418527776e131
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754765"
---
# <a name="operator-c-reference"></a>연산자(C# 참조)

`operator` 키워드를 사용하여 기본 제공 연산자를 오버로드하거나 클래스 또는 구조체 선언에서 사용자 정의 변환을 제공할 수 있습니다.

사용자 지정 클래스 또는 구조체에서 연산자를 오버로드하려면 해당 형식으로 연산자 선언문을 만듭니다. 기본 제공 C# 연산자를 오버로드하는 연산자 선언은 다음 규칙을 충족해야 합니다.

- `public` 및 `static` 한정자를 모두 포함합니다.
- 여기에는 `operator X`가 포함되며, 여기서 `X`는 오버로드되는 연산자의 이름 또는 기호입니다.
- 단항 연산자는 매개 변수가 하나이고, 이항 연산자는 매개 변수가 두 개입니다. 각각의 경우 적어도 하나의 매개 변수는 연산자를 선언하는 클래스나 구조체와 동일한 형식이어야 합니다.

변환 연산자를 정의하는 방법에 대한 자세한 내용은 [explicit](explicit.md) 및 [implicit](implicit.md) 키워드 문서를 참조하세요.

오버로드할 수 있는 C# 연산자에 대한 개요는 [오버로드할 수 있는 연산자](../../programming-guide/statements-expressions-operators/overloadable-operators.md) 문서를 참조하세요.

## <a name="example"></a>예제

다음 예제에서는 소수를 나타내는 `Fraction` 형식을 정의합니다. `+` 및 `*` 연산자를 오버로드하여 소수 더하기 및 곱하기를 수행하고 `Fraction` 형식을 `double` 형식으로 변환하는 변환 연산자도 제공합니다.

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
- [implicit](implicit.md)
- [explicit](explicit.md)
- [오버로드할 수 있는 연산자](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [방법: 구조체 간의 사용자 정의 변환 구현](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
