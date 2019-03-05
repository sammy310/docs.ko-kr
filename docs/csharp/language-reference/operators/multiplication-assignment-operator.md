---
title: '*= 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 70461f79e714e44354fe4137e5360769fa048d3e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967388"
---
# <a name="-operator-c-reference"></a>\*= 연산자(C# 참조)

곱하기 대입 연산자입니다.

다음과 같은 `*=` 연산자를 사용하는 식의 경우

```csharp
x *= y
```

위의 식은 아래의 식과 동일합니다.

```csharp
x = x * y
```

단, `x`가 한 번만 계산됩니다.

숫자 형식의 경우 [\* 연산자](multiplication-operator.md)는 해당 피연산자의 곱을 계산합니다.

다음 예제에서는 `*=` 연산자의 사용법을 보여 줍니다.

[!code-csharp-interactive[multiply and assign](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#MultiplyAndAssign)]

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

사용자 정의 형식이 [곱하기 연산자](multiplication-operator.md) `*`를 [오버로드](../keywords/operator.md)하면 곱하기 대입 연산자 `*=`는 암시적으로 오버로드됩니다. 사용자 정의 형식은 곱하기 대입 연산자를 명시적으로 오버로드할 수 없습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [복합 할당](~/_csharplang/spec/expressions.md#compound-assignment) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)
