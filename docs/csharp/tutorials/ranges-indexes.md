---
title: 인덱스 및 범위를 사용하여 데이터 범위 탐색
description: 이 고급 자습서에서는 인덱스 및 범위를 사용하여 연속 범위의 순차적 데이터 세트를 검사하는 데이터를 탐색하는 방법을 살펴봅니다.
ms.date: 09/11/2020
ms.technology: csharp-fundamentals
ms.custom: mvc
ms.openlocfilehash: c0484a42233466e3a2a70a673aee81fce91fe31b
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585405"
---
# <a name="indices-and-ranges"></a>인덱스 및 범위

범위와 인덱스는 시퀀스의 단일 요소 또는 범위에 액세스하기 위한 간결한 구문을 제공합니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 알아봅니다.

> [!div class="checklist"]
>
> - 시퀀스에서 범위에 구문을 사용합니다.
> - 각 시퀀스의 시작 및 끝에 대한 설계 의사 결정을 이해합니다.
> - <xref:System.Index> 및 <xref:System.Range> 형식에 대한 시나리오를 살펴봅니다.

## <a name="language-support-for-indices-and-ranges"></a>인덱스 및 범위에 대한 언어 지원

이 언어 지원은 다음과 같은 두 가지 새 형식 및 두 가지 새 연산자를 사용합니다.

- <xref:System.Index?displayProperty=nameWithType>는 인덱스를 시퀀스로 표현합니다.
- 인덱스가 시퀀스의 끝을 기준으로 하도록 지정하는 끝부터 인덱스 연산자 `^`입니다.
- <xref:System.Range?displayProperty=nameWithType>는 시퀀스의 하위 범위를 나타냅니다.
- 범위의 시작과 끝을 피연산자로 지정하는 범위 연산자 `..`입니다.

인덱스에 대한 규칙을 사용하여 시작하겠습니다. `sequence`배열을 고려합니다. `0` 인덱스는 `sequence[0]`과 동일합니다. `^0` 인덱스는 `sequence[sequence.Length]`와 동일합니다. `sequence[^0]` 식은 `sequence[sequence.Length]`처럼 예외를 throw합니다. `n`이 어떤 숫자이든, 인덱스 `^n`은 `sequence[sequence.Length - n]`과 동일합니다.

```csharp
string[] words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

다음과 같이 `^1` 인덱스를 사용하여 마지막 단어를 가져올 수 있습니다. 초기화 아래에 다음 코드를 추가합니다.

[!code-csharp[LastIndex](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

한 범위는 어떤 범위의 *시작* 및 *끝* 을 지정합니다. 여러 범위는 배타적입니다. 즉, ‘끝’이 범위에 포함되지 않습니다.  `[0..sequence.Length]`가 전체 범위를 나타내는 것처럼 `[0..^0]` 범위는 전체 범위를 나타냅니다.

다음 코드는 “quick”, “brown”, “fox”라는 단어를 포함하는 하위 범위를 만듭니다. 이 하위 범위에는 `words[1]`부터 `words[3]`까지 포함되며, `words[4]` 요소가 범위에 없습니다. 다음 코드를 같은 메서드에 추가합니다. 대화형 창의 맨 아래에 다음 코드를 복사하여 붙여넣습니다.

[!code-csharp[Range](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

다음 코드는 “lazy”와 “dog”을 포함하는 범위를 반환합니다. 이 하위 범위에는 `words[^2]`과 `words[^1]`이 포함되며. 끝 인덱스 `words[^0]`는 포함되지 않습니다. 다음 코드도 추가합니다.

[!code-csharp[LastRange](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

다음 예제는 시작만, 끝만, 그리고 시작과 끝이 모두 열린 범위를 만듭니다.

[!code-csharp[PartialRange](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

범위나 인덱스를 변수로 선언할 수도 있습니다. 그러면 이 변수를 `[` 및 `]` 문자 사이에 사용할 수 있습니다.

[!code-csharp[IndexRangeTypes](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

다음 샘플에서는 이러한 선택에 대한 여러 이유를 보여 줍니다. `x`, `y` 및 `z`를 수정하여 다양한 조합을 시도해 봅니다. 실험할 때는 올바른 조합을 위해 `x`가 `y`보다 작고 `y`가 `z`보다 작은 값을 사용합니다. 새 메서드에 다음 코드를 추가합니다. 다양한 조합을 시도해 봅니다.

[!code-csharp[SemanticsExamples](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="type-support-for-indices-and-ranges"></a>인덱스 및 범위에 대한 형식 지원

인덱스 및 범위는 시퀀스에서 단일 요소 또는 요소의 범위에 액세스하기 위한 명확하고 간결한 구문을 제공합니다. 인덱스 식은 일반적으로 시퀀스의 요소 형식을 반환합니다. 범위 식은 일반적으로 소스 시퀀스와 동일한 시퀀스 형식을 반환합니다.

<xref:System.Index> 또는 <xref:System.Range> 매개 변수를 사용하여 [인덱서](../programming-guide/indexers/index.md)를 제공하는 형식은 각각 인덱스 또는 범위를 명시적으로 지원합니다. 단일 <xref:System.Range> 매개 변수를 사용하는 인덱서는 다양한 시퀀스 형식(예: <xref:System.Span%601?displayProperty=nameWithType>)을 반환할 수 있습니다.

> [!IMPORTANT]
> 범위 연산자를 사용하는 코드의 성능은 시퀀스 피연산자의 형식에 따라 다릅니다.
>
> 범위 연산자의 시간 복잡성은 시퀀스 형식에 따라 다릅니다. 예를 들어 시퀀스가 `string` 또는 배열인 경우 결과는 지정된 입력 섹션의 복사본이므로, 시간 복잡성은 *O(N)* 입니다(여기서 N은 범위의 길이입니다.). 반면, 시퀀스가 <xref:System.Span%601?displayProperty=nameWithType> 또는 <xref:System.Memory%601?displayProperty=nameWithType>인 경우 결과는 동일한 백업 저장소를 참조합니다. 다시 말해서, 복사본이 없고 작업은 *O(1)* 이 됩니다.
>
> 이로 인해 시간 복잡성 외에도 추가 할당과 복사본이 발생하여 성능에 영향을 미칩니다. 성능에 중요한 코드에서는 시퀀스 형식으로 `Span<T>` 또는 `Memory<T>`를 사용하는 것이 좋습니다. 이에 대해 범위 연산자가 할당되지 않기 때문입니다.

이름이 `Length` 또는 `Count`이고 액세스 가능한 getter 및 반환 형식 `int`를 갖는 속성이 있는 경우 형식은 **countable** 입니다. 인덱스 또는 범위를 명시적으로 지원하지 않는 countable 형식은 해당 형식에 대한 암시적 지원을 제공할 수 있습니다. 자세한 내용은 [기능 제한 참고](~/_csharplang/proposals/csharp-8.0/ranges.md)의 [암시적 인덱스 지원](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) 및 [암시적 범위 지원](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) 섹션을 참조하세요. 암시적 범위 지원을 사용하는 범위는 소스 시퀀스와 동일한 시퀀스 형식을 반환합니다.

예를 들어, .NET 형식 <xref:System.String>, <xref:System.Span%601> 및 <xref:System.ReadOnlySpan%601>은 인덱스와 범위를 모두 지원합니다. <xref:System.Collections.Generic.List%601>는 인덱스는 지원하고 범위는 지원하지 않습니다.

<xref:System.Array>에는 좀 더 미묘한 동작이 더 있습니다. 1차원 배열은 인덱스와 범위를 모두 지원합니다. 다차원 배열은 인덱서 또는 범위를 지원하지 않습니다. 다차원 배열에 대한 인덱서에는 단일 매개 변수가 아닌 여러 개의 매개 변수가 있습니다. 배열의 배열이라고도 하는 가변 배열은 범위와 인덱서를 모두 지원합니다. 다음 예에서는 가변 배열의 사각형 하위 섹션을 반복하는 방법을 보여 줍니다. 첫 행과 마지막 3개 행을 제외하고, 선택된 각 행에서 첫 열과 마지막 2개 열을 제외하고 중앙의 섹션을 반복합니다.

[!code-csharp[JaggedArrays](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_JaggedArrays)]

모든 경우에 <xref:System.Array>의 범위 연산자는 반환된 요소를 저장할 배열을 할당합니다.

## <a name="scenarios-for-indices-and-ranges"></a>인덱스 및 범위에 대한 시나리오

더 큰 시퀀스의 부분을 분석할 때 자주 범위와 인덱스를 사용하게 됩니다. 새 구문에서는 시퀀스의 어떤 부분이 관련되었는지 더 명확히 이해할 수 있습니다. 로컬 함수 `MovingAverage`는 <xref:System.Range>를 인수로 사용합니다. 그러면 메서드가 최솟값, 최댓값, 평균을 계산할 때 이 범위만 열거합니다. 프로젝트에 다음 코드를 시도해 봅니다.

[!code-csharp[MovingAverages](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]
