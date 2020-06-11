---
title: 1차원 배열 - C# 프로그래밍 가이드
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: e189253eedc21fa2d51e16407f04b034610bb57b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410246"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a>1차원 배열(C# 프로그래밍 가이드)

배열 요소 형식과 요소 수를 지정하는 [new](../../language-reference/operators/new-operator.md) 연산자를 사용하여 1차원 배열을 만듭니다. 다음 예제에서는 정수가 5개인 배열을 선언합니다.

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

이 배열에는 `array[0]` ~ `array[4]`의 요소가 포함되어 있습니다. 배열의 요소는 기본값, 즉 정수에 대해 요소 형식 `0`으로 초기화됩니다.

문자열 배열을 선언하는 다음 예제와 같이, 배열은 지정되는 모든 요소 형식을 저장할 수 있습니다.

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a>배열 초기화

배열을 선언할 때 배열의 요소를 초기화할 수 있습니다. 길이 지정자는 초기화 목록의 요소 수에 따라 유추되므로 필요하지 않습니다. 예를 들어:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

다음 코드는 각 배열 요소가 요일 이름으로 초기화되는 문자열 배열의 선언을 보여 줍니다.

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
다음 코드와 같이 선언 시 배열을 초기화할 때 `new` 식과 배열 형식을 피할 수 있습니다. 이를 [암시적으로 형식화된 배열](implicitly-typed-arrays.md)이라고 합니다.

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

배열 변수를 만들지 않고 선언할 수 있지만 이 변수에 새 배열을 할당할 때는 `new` 연산자를 사용해야 합니다. 예를 들어:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a>값 형식 및 참조 형식 배열

다음 배열 선언을 살펴보세요.  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

이 문의 결과는 `SomeType`이 값 형식인지 또는 참조 형식인지에 따라 달라집니다. 값 형식인 경우 이 문은 각각 `SomeType` 형식인 10개 요소의 배열을 만듭니다. `SomeType`이 참조 형식인 경우 이 문은 각각 null 참조로 초기화된 10개 요소의 배열을 만듭니다. 두 인스턴스 모두에서 요소가 요소 형식에 대한 기본값으로 초기화됩니다. 값 형식과 참조 형식에 대한 자세한 내용은 [값 형식](../../language-reference/builtin-types/value-types.md) 및 [참조 형식](../../language-reference/keywords/reference-types.md)을 참조하세요.
  
## <a name="see-also"></a>참조

- <xref:System.Array>
- [배열](./index.md)
- [다차원 배열](./multidimensional-arrays.md)
- [가변 배열](./jagged-arrays.md)
