---
title: = 연산자 - C# 참조
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 40dc844f2a4b6411ea82aa2f029b36d7dd8f6e5a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716321"
---
# <a name="-operator-c-reference"></a>= 연산자(C# 참조)

대입 연산자 `=`은 오른쪽 피연산자의 값을 왼쪽 피연산자가 제공하는 변수, [속성](../../programming-guide/classes-and-structs/properties.md) 또는 [인덱서](../../../csharp/programming-guide/indexers/index.md) 요소에 할당합니다. 대입식의 결과는 왼쪽 피연산자에 할당된 값입니다. 오른쪽 피연산자의 형식은 왼쪽 피연산자의 형식과 동일하거나 왼쪽 피연산자의 형식으로 암시적으로 변환할 수 있어야 합니다.

대입 연산자는 오른쪽 결합성입니다. 즉, 다음 형식의 식을 가정해 보세요.

```csharp
a = b = c
```

이 식은 다음과 같이 계산됩니다.

```csharp
a = (b = c)
```

다음 예제는 대입 연산자를 사용하여 지역 변수, 속성 및 인덱서 요소에 값을 할당하는 방법을 보여 줍니다.

[!code-csharp-interactive[assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a>ref 대입 연산자

C# 7.3부터 ref 대입 연산자 `= ref`를 사용하여 [ref 지역](../keywords/ref.md#ref-locals) 또는 [ref readonly 지역](../keywords/ref.md#ref-readonly-locals) 변수를 다시 할당할 수 있습니다. 다음 예제에서는 ref 대입 연산자의 사용법을 보여 줍니다.

[!code-csharp[ref assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

ref 대입 연산자의 경우 왼쪽 피연산자의 형식과 오른쪽 피연산자의 형식이 같아야 합니다.

자세한 내용은 [기능 제안 노트](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md)를 참조하세요.

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

사용자 정의 형식은 대입 연산자를 오버로드할 수 없습니다. 그러나 사용자 정의 형식은 다른 형식으로 암시적 변환을 정의할 수 있습니다. 이렇게 하면 사용자 정의 형식의 값을 다른 형식의 변수, 속성 또는 인덱서 요소에 할당할 수 있습니다. 자세한 내용은 [implicit](../keywords/implicit.md) 키워드 문서를 참조하세요.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [단순 할당](~/_csharplang/spec/expressions.md#simple-assignment) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)
- [ref 키워드](../keywords/ref.md)
