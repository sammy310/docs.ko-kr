---
title: '[] 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 01/10/2019
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 9088393f61d300ee76e56e320bec17b4a79bfebb
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835592"
---
# <a name="-operator-c-reference"></a>[] 연산자(C# 참조)

대괄호 `[]`는 일반적으로 배열, 인덱서 또는 포인터 요소 액세스에 사용됩니다.

포인터 요소 액세스에 대한 자세한 내용은 [방법: 포인터를 사용하여 배열 요소 액세스](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md)를 참조하세요.

또한 대괄호를 사용하여 [특성](../../programming-guide/concepts/attributes/index.md)을 지정합니다.

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="array-access"></a>배열 액세스

다음 예제는 배열 요소에 액세스하는 방법을 보여 줍니다.

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Arrays)]

배열 인덱스가 배열의 해당 차원 범위를 벗어난 경우 <xref:System.IndexOutOfRangeException>이 throw됩니다.

앞의 예제와 같이, 배열 형식의 선언 및 배열 인스턴스의 인스턴스화에도 대괄호를 사용합니다.

배열에 대한 자세한 내용은 [배열](../../programming-guide/arrays/index.md)을 참조하세요.

## <a name="indexer-access"></a>인덱서 액세스

다음 예제는 .NET <xref:System.Collections.Generic.Dictionary%602> 형식을 사용하여 인덱서 액세스를 보여 줍니다.

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Indexers)]

인덱서를 사용하면 배열 인덱싱과 비슷한 방법으로 사용자 정의 형식의 인스턴스를 인덱싱할 수 있습니다. 정수여야 하는 배열 인덱스와 달리, 인덱서 인수는 임의 형식으로 선언할 수 있습니다.

인덱서에 대한 자세한 내용은 [인덱서](../../programming-guide/indexers/index.md)를 참조하세요.

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

요소 액세스 `[]`는 오버로드 가능한 연산자로 간주되지 않습니다. [인덱서](../../programming-guide/indexers/index.md)를 사용하여 사용자 정의 형식의 인덱싱을 지원합니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [요소 액세스](~/_csharplang/spec/expressions.md#element-access) 및 [포인터 요소 액세스](~/_csharplang/spec/unsafe-code.md#pointer-element-access) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)
- [배열](../../programming-guide/arrays/index.md)
- [인덱서](../../programming-guide/indexers/index.md)
- [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [특성](../../programming-guide/concepts/attributes/index.md)
- [?. 및 ?[] 연산자](null-conditional-operators.md)