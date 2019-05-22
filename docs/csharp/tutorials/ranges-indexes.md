---
title: 인덱스 및 범위를 사용하여 데이터 범위 탐색
description: 이 고급 자습서에서는 인덱스 및 범위를 사용하여 순차적 데이터 세트를 검사하는 데이터 탐색을 살펴봅니다.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: 64fae4581e265d4f70b8356d5c651b4fdaca3fe9
ms.sourcegitcommit: dd3b897feb5c4ac39732bb165848e37a344b0765
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/25/2019
ms.locfileid: "64431494"
---
# <a name="indices-and-ranges"></a>인덱스 및 범위

범위와 인덱스는 배열, <xref:System.Array>, <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601>에서 단일 요소 또는 범위에 액세스하기 위한 간결한 구문을 제공합니다. 이러한 기능을 통해 더 간결하고 분명한 구문으로 시퀀스의 단일 요소 또는 요소 범위에 액세스할 수 있습니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 알아봅니다.

> [!div class="checklist"]
> * 시퀀스에서 범위에 구문을 사용합니다.
> * 각 시퀀스의 시작 및 끝에 대한 설계 의사 결정을 이해합니다.
> * <xref:System.Index> 및 <xref:System.Range> 형식에 대한 시나리오를 살펴봅니다.

## <a name="language-support-for-indices-and-ranges"></a>인덱스 및 범위에 대한 언어 지원

인덱스 앞에 `^` 문자를 사용하여 **끝에서부터** 인덱스를 지정할 수 있습니다. 끝에서부터의 인덱스는 `0..^0`이 전체 범위를 지정하는 규칙에서 시작합니다. 전체 배열을 열거하려면 *첫 번째 요소*에서 시작하고 *마지막 요소를 통과*할 때까지 계속합니다. 열거자에서 `MoveNext` 메서드의 동작을 고려해 봅니다. 즉 열거형이 마지막 요소를 통과하면 False를 반환합니다. 인덱스 `^0`은 “끝”, `array[array.Length]` 또는 마지막 요소 뒤에 오는 인덱스를 의미합니다. `array[2]`가 “앞에서부터 2번째” 요소를 의미한다는 것은 이미 잘 알고 계실 것입니다. `array[^2]`는 “뒤에서부터 2번째” 요소를 의미합니다. 

**범위**는 **범위 연산자** `..`를 사용하여 지정할 수 있습니다. 예를 들어, `0..^0`은 배열의 전체 범위를 지정하는데, 앞에서부터 인덱스 0에서 뒤에서부터 인덱스 1까지(즉, ^0 인덱스는 은 포함되지 않음)를 의미합니다. 피연산자 둘 다 “앞에서부터” 또는 “뒤에서부터”를 사용할 수 있습니다. 피연산자 둘 다 생략하는 것도 가능합니다. 시작 인덱스의 기본값은 `0`, 끝 인덱스의 기본값은 `^0`입니다.

```csharp-interactive
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

각 요소의 인덱스는 “앞에서부터”라는 개념과 “뒤에서부터”라는 개념과 범위에는 해당 범위의 끝은 포함되지 않음을 보여줍니다. 전체 배열의 “시작”은 첫 번째 요소입니다. 전체 배열의 “끝”은 마지막 요소의 “뒤”에 있습니다.

다음과 같이 `^1` 인덱스를 사용하여 마지막 단어를 가져올 수 있습니다. 초기화 아래에 다음 코드를 추가합니다.

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

다음 코드는 “quick”, “brown”, “fox”라는 단어를 포함하는 하위 범위를 만듭니다. 이 하위 범위에는 `words[1]`부터 `words[3]`까지 포함되며, `words[4]` 요소가 범위에 없습니다. 다음 코드를 같은 메서드에 추가합니다. 대화형 창의 맨 아래에 다음 코드를 복사하여 붙여넣습니다.

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

다음 코드는 “lazy”와 “dog”를 포함하는 하위 범위를 만듭니다. 이 하위 범위에는 `words[^2]`과 `words[^1]`이 포함되며. 끝 인덱스 `words[^0]`는 포함되지 않습니다. 다음 코드도 추가합니다.

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

다음 예제는 시작만, 끝만, 그리고 시작과 끝이 모두 열린 범위를 만듭니다.

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

범위나 인덱스를 변수로 선언할 수도 있습니다. 그러면 이 변수를 `[` 및 `]` 문자 사이에 사용할 수 있습니다.

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

앞의 예제에서는 추가적인 설명이 필요한 두 가지 설계 의사 결정을 보여 줍니다.

- 범위가 *배타적*이면 마지막 인덱스의 요소가 범위에 포함되지 않습니다.
- `^0` 인덱스는 컬렉션의 *끝*이지, 컬렉션의 *마지막 요소*가 아닙니다.

다음 샘플에서는 이러한 선택에 대한 여러 이유를 보여 줍니다. `x`, `y` 및 `z`를 수정하여 다양한 조합을 시도해 봅니다. 실험할 때는 올바른 조합을 위해 `x`가 `y`보다 작고 `y`가 `z`보다 작은 값을 사용합니다. 새 메서드에 다음 코드를 추가합니다. 다양한 조합을 시도해 봅니다.

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a>인덱스 및 범위에 대한 시나리오

전체 시퀀스의 하위 범위에 대한 특정 분석을 수행할 때 범위와 인덱스를 사용하게 됩니다. 새 구문에서는 어떤 하위 범위가 관련되었는지 더 명확히 이해할 수 있습니다. 로컬 함수 `MovingAverage`는 <xref:System.Range>를 인수로 사용합니다. 그러면 메서드가 최솟값, 최댓값, 평균을 계산할 때 이 범위만 열거합니다. 프로젝트에 다음 코드를 시도해 봅니다.

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

완료된 코드는 [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) 리포지토리에서 다운로드할 수 있습니다.
