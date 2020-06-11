---
title: C# foreach 문
ms.date: 06/03/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 1645a246c9feee2a92c0d4e4bbeda47f0afde7d9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401890"
---
# <a name="foreach-in-c-reference"></a>foreach, in(C# 참조)

`foreach` 문은 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 인터페이스를 구현하는 형식의 인스턴스에 있는 각 요소에 대해 문 또는 문 블록을 실행합니다. `foreach` 문은 해당 형식으로 제한되지 않으며 다음 조건을 충족하는 모든 형식의 인스턴스에 적용될 수 있습니다.

- 반환 형식이 클래스, 구조체 또는 인터페이스 유형인 public 매개 변수가 없는 `GetEnumerator` 메서드를 포함합니다.
- `GetEnumerator` 메서드의 반환 형식이 public `Current` 속성과 반환 형식이 <xref:System.Boolean>인 public 매개 변수가 없는 `MoveNext` 메서드를 포함합니다.

대부분의 사용에서 `foreach`는 각 요소가 `T`형식인 `IEnumerable<T>` 식을 반복합니다. 그러나 요소는 `Current` 속성의 형식이 암시적 또는 명시적으로 변환된 모든 형식일 수 있습니다. `Current` 속성이 `SomeType`을 반환하는 경우 요소의 형식은 다음과 같을 수도 있습니다.

- `SomeType`의 임의 기본 클래스
- `SomeType`에서 구현하는 임의 인터페이스

또한 `SomeType`이 `class` 또는 `interface`이고 `sealed`가 아닌 경우 요소의 형식에는 다음이 포함될 수도 있습니다.

- `SomeType`에서 파생된 임의 형식
- 임의 인터페이스. `SomeType`에서 파생되거나 이 형식을 구현하는 클래스에서 모든 인터페이스가 구현될 수 있기 때문에 모든 인터페이스가 허용됩니다.

이전 규칙과 일치하는 임의 형식을 사용하여 반복 변수를 선언할 수도 있습니다. `SomeType`에서 반복 변수의 형식으로 변환하는 데 명시적인 캐스트가 필요한 경우에는 변환이 실패하면 해당 작업에서 <xref:System.InvalidCastException>을 throw할 수도 있습니다.

C# 7.3부터는 열거자의 `Current` 속성이 [참조 반환 값](ref.md#reference-return-values)(`ref T` 여기서 `T`는 컬렉션 요소의 형식임)을 반환하는 경우 `ref` 또는 `ref readonly` 한정자를 사용하여 반복 변수를 선언할 수 있습니다.

C# 8.0부터 컬렉션 형식이 <xref:System.Collections.Generic.IAsyncEnumerable%601> 인터페이스를 구현할 때 `foreach` 문에 `await` 연산자가 적용될 수도 있습니다. 루프의 각 반복은 다음 요소가 비동기적으로 검색되는 동안 일시 중단될 수도 있습니다. 기본적으로 스트림 요소는 캡처된 컨텍스트에서 처리됩니다. 컨텍스트 캡처를 사용하지 않도록 설정하려면 <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> 확장 메서드를 사용합니다. 동기화 컨텍스트 및 현재 컨텍스트 캡처에 대한 자세한 내용은 [작업 기반 비동기 패턴 사용](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)에 대한 문서를 참조하세요.

`foreach` 문 블록 내 원하는 지점에서 [break](break.md) 문을 사용하여 루프를 중단하거나 [continue](continue.md) 문을 사용하여 루프의 다음 반복을 한 단계 실행할 수 있습니다. [goto](goto.md), [return](return.md) 또는 [throw](throw.md) 문으로 `foreach` 루프를 종료할 수도 있습니다.

`foreach` 문이 `null`에 적용되면 <xref:System.NullReferenceException>이 throw됩니다. `foreach` 문의 소스 컬렉션이 비어 있으면 `foreach` 루프의 본문이 실행되지 않고 건너뜁니다.

## <a name="examples"></a>예

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

다음 예제는 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현하는 <xref:System.Collections.Generic.List%601> 형식의 인스턴스와 함께 `foreach` 문의 사용법을 보여줍니다.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

다음 예제에서는 인터페이스를 구현하지 않는 <xref:System.Span%601?displayProperty=nameWithType> 형식의 인스턴스와 함께 `foreach` 문을 사용합니다.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

다음 예제에서는 `ref` 반복 변수를 사용하여 stackalloc 배열의 각 항목 값을 설정합니다. `ref readonly` 버전은 컬렉션을 반복하여 모든 값을 인쇄합니다. `readonly` 선언은 암시적 로컬 변수 선언을 사용합니다. 명시적으로 변수 선언을 입력하므로 `ref` 또는 `ref readonly`에서 암시적 변수 선언을 사용할 수 있습니다.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

다음 예에서는 `await foreach`를 사용하여 각 요소를 비동기적으로 생성하는 컬렉션을 반복합니다.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach"  :::

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [foreach 문](~/_csharplang/spec/statements.md#the-foreach-statement) 섹션을 참조하세요.

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
- [배열에 foreach 사용](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [for 문](for.md)
