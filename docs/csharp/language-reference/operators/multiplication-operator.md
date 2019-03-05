---
title: '* 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: a5e120d26614f1e38cc2f2db02949552140b594e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977346"
---
# <a name="-operator-c-reference"></a>* 연산자(C# 참조)

`*` 연산자는 두 개의 형식인 단항 포인터 간접 참조 연산자 또는 이항 곱하기 연산자에서 지원됩니다.

## <a name="pointer-indirection-operator"></a>포인터 간접 참조 연산자

단항 `*` 연산자를 사용하여 포인터 형식 피연산자가 가리키는 변수를 가져옵니다. 자세한 내용은 [방법: 포인터 변수 값 가져오기](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md)를 참조하세요.

포인터 간접 참조 연산자 `*`에는 [unsafe](../keywords/unsafe.md) 컨텍스트가 필요합니다.

## <a name="multiplication-operator"></a>곱하기 연산자

숫자 형식의 경우 `*` 연산자는 해당 피연산자의 곱을 계산합니다.

[!code-csharp-interactive[multiplication](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#Multiply)]

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

사용자 정의 형식은 이항 `*` 연산자를 [오버로드](../keywords/operator.md)할 수 있습니다. 이항 `*` 연산자가 오버로드되면 [곱하기 대입 연산자](multiplication-assignment-operator.md) `*=`도 암시적으로 오버로드됩니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [포인터 간접 참조](~/_csharplang/spec/unsafe-code.md#pointer-indirection) 및 [곱하기 연산자](~/_csharplang/spec/expressions.md#multiplication-operator) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)
- [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)