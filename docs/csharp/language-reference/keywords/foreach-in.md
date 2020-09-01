---
description: foreach, in(C# 참조)
title: C# foreach 문
ms.date: 07/22/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 2ed89fa52b2d3d369d668bf79ab32eaf7be18a8a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142078"
---
# <a name="foreach-in-c-reference"></a>foreach, in(C# 참조)

`foreach` 문은 다음 예제와 같이 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 인터페이스를 구현하는 형식의 인스턴스에 있는 각 요소에 대해 문 또는 문 블록을 실행합니다.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

`foreach` 문은 이러한 형식으로 제한되지 않습니다. 다음 조건을 충족하는 모든 형식의 인스턴스와 함께 사용할 수 있습니다.

- 형식에는 반환 형식이 클래스, 구조체 또는 인터페이스 유형인 public 매개 변수가 없는 `GetEnumerator` 메서드가 포함됩니다.
- `GetEnumerator` 메서드의 반환 형식이 public `Current` 속성과 반환 형식이 <xref:System.Boolean>인 public 매개 변수가 없는 `MoveNext` 메서드를 포함합니다.

다음 예제에서는 인터페이스를 구현하지 않는 <xref:System.Span%601?displayProperty=nameWithType> 형식의 인스턴스와 함께 `foreach` 문을 사용합니다.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

C# 7.3부터는 열거자의 `Current` 속성이 [참조 반환 값](ref.md#reference-return-values)(`ref T` 여기서 `T`는 컬렉션 요소의 형식임)을 반환하는 경우 다음 예제와 같이 `ref` 또는 `ref readonly` 한정자를 사용하여 반복 변수를 선언할 수 있습니다.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

C# 8.0부터는 `await foreach` 문을 사용하여 비동기 데이터 스트림 즉, <xref:System.Collections.Generic.IAsyncEnumerable%601> 인터페이스를 구현하는 컬렉션 형식을 사용할 수 있습니다. 루프의 각 반복은 다음 요소가 비동기적으로 검색되는 동안 일시 중단될 수도 있습니다. 다음 예제에서는 `await foreach` 문을 사용하는 방법을 보여줍니다.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

기본적으로 스트림 요소는 캡처된 컨텍스트에서 처리됩니다. 컨텍스트 캡처를 사용하지 않도록 설정하려면 <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> 확장 메서드를 사용합니다. 동기화 컨텍스트 및 현재 컨텍스트 캡처에 대한 자세한 내용은 [작업 기반 비동기 패턴 사용](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)을 참조하세요. 비동기 스트림에 대한 자세한 내용은 [C# 8.0의 새로운 기능](../../whats-new/csharp-8.md) 문서의 [비동기 스트림](../../whats-new/csharp-8.md#asynchronous-streams) 섹션을 참조하세요.

`foreach` 문 블록 내 원하는 지점에서 [break](break.md) 문을 사용하여 루프를 중단하거나 [continue](continue.md) 문을 사용하여 루프의 다음 반복을 한 단계 실행할 수 있습니다. [goto](goto.md), [return](return.md) 또는 [throw](throw.md) 문으로 `foreach` 루프를 종료할 수도 있습니다.

`foreach` 문이 `null`에 적용되면 <xref:System.NullReferenceException>이 throw됩니다. `foreach` 문의 소스 컬렉션이 비어 있으면 `foreach` 루프의 본문이 실행되지 않고 건너뜁니다.

## <a name="type-of-an-iteration-variable"></a>반복 변수의 형식

다음 코드와 같이 `var` 키워드를 사용하여 컴파일러가 `foreach` 문에서 반복 변수의 형식을 유추할 수 있습니다.

```csharp
foreach (var item in collection) { }
```

다음 코드와 같이 반복 변수의 형식을 명시적으로 지정할 수도 있습니다.

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

위의 양식에서 컬렉션 요소의 `T` 형식은 암시적 또는 명시적으로 반복 변수의 `V` 형식으로 변환할 수 있어야 합니다. `T`에서 `V`로의 명시적 변환이 런타임에 실패하는 경우 `foreach` 문은 <xref:System.InvalidCastException>을 throw합니다. 예를 들어 `T`가 봉인되지 않은 클래스 형식인 경우 `V`는 `T`가 구현하지 않는 형식을 포함하여 모든 인터페이스 형식일 수 있습니다. 런타임에 컬렉션 요소의 형식은 `T`에서 파생되어 실제로 `V`를 구현하는 형식일 수 있습니다. 그렇지 않은 경우에는 <xref:System.InvalidCastException>을 throw합니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [foreach 문](~/_csharplang/spec/statements.md#the-foreach-statement) 섹션을 참조하세요.

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 키워드](index.md)
- [배열에 foreach 사용](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [for 문](for.md)
