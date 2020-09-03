---
title: LINQ 쿼리용 사용자 지정 메서드를 추가하는 방법(C#)
description: C#에서 IEnumerable<T> 인터페이스에 확장 메서드를 추가하여 LINQ 쿼리의 구문을 확장하는 방법을 알아봅니다.
ms.date: 08/26/2020
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: 768882fce40a2fc6e018f24c8928341e7c65bc4b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122428"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a>LINQ 쿼리용 사용자 지정 메서드를 추가하는 방법(C#)

<xref:System.Collections.Generic.IEnumerable%601> 인터페이스에 확장 메서드를 추가하여 LINQ 쿼리에 사용하는 메서드 세트를 확장합니다. 예를 들어 표준 평균 또는 최대 작업 외에 사용자 지정 집계 메서드를 만들어 값 시퀀스에서 단일 값을 계산합니다. 값 시퀀스에 대한 특정 데이터 변환 또는 사용자 지정 필터로 작동하고 새 시퀀스를 반환하는 메서드도 만듭니다. 이러한 메서드의 예로는 <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> 및 <xref:System.Linq.Enumerable.Reverse%2A>가 있습니다.

<xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 확장하면 사용자 지정 메서드를 열거 가능한 컬렉션에 적용할 수 있습니다. 자세한 내용은 [확장 메서드](../../classes-and-structs/extension-methods.md)를 참조하세요.

## <a name="adding-an-aggregate-method"></a>집계 메서드 추가

집계 메서드는 값 집합에서 하나의 값을 계산합니다. LINQ는 <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> 및 <xref:System.Linq.Enumerable.Max%2A>를 포함하여 여러 집계 메서드를 제공합니다. <xref:System.Collections.Generic.IEnumerable%601> 인터페이스에 확장 메서드를 추가하여 고유한 집계 메서드를 만들 수 있습니다.

다음 코드 예제에서는 `double` 형식의 숫자 시퀀스에 대한 중앙값을 계산하는 `Median`이라는 확장 메서드를 만드는 방법을 보여 줍니다.

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="LinqExtensionClass":::

<xref:System.Collections.Generic.IEnumerable%601> 인터페이스에서 다른 집계 메서드를 호출하는 것과 같은 방식으로 열거 가능한 컬렉션에 대해 이 확장 메서드를 호출합니다.

다음 코드 예제에서는 `double` 형식의 배열에 대해 `Median` 메서드를 사용하는 방법을 보여 줍니다.

:::code language="csharp" source="./snippets/Program.cs" ID="MedianUsage":::

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>다양한 형식을 허용하도록 집계 메서드 오버로드

다양한 형식의 시퀀스를 허용하도록 집계 메서드를 오버로드할 수 있습니다. 표준 접근법은 각 형식에 대한 오버로드를 만드는 것입니다. 또 다른 접근법은 제네릭 형식을 사용하고 대리자를 통해 이를 특정 형식으로 변환할 오버로드를 만드는 것입니다. 두 가지 접근법을 결합할 수도 있습니다.

#### <a name="to-create-an-overload-for-each-type"></a>각 형식에 대한 오버로드를 만들려면

지원하려는 각 형식에 대한 특정 오버로드를 만들 수 있습니다. 다음 코드 예제에서는 `int` 형식에 대한 `Median` 메서드의 오버로드를 보여 줍니다.

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="IntOverload":::

이제 다음 코드와 같이 `integer` 및 `double` 형식에 대한 `Median` 오버로드를 호출할 수 있습니다.

:::code language="csharp" source="./snippets/Program.cs" ID="OverloadUsage":::

#### <a name="to-create-a-generic-overload"></a>제네릭 오버로드를 만들려면

제네릭 개체의 시퀀스를 허용하는 오버로드를 만들 수도 있습니다. 이 오버로드는 대리자를 매개 변수로 사용하여 제네릭 형식의 개체 시퀀스를 특정 형식으로 변환합니다.

다음 코드에서는 <xref:System.Func%602> 대리자를 매개 변수로 사용하는 `Median` 메서드의 오버로드를 보여 줍니다. 이 대리자는 제네릭 형식 T의 개체를 사용하고 `double` 형식의 개체를 반환합니다.

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="GenericOverload":::

이제 임의 형식의 개체 시퀀스에 대해 `Median` 메서드를 호출할 수 있습니다. 형식에 자체 메서드 오버로드가 없으면 대리자 매개 변수를 전달해야 합니다. C#에서는 이 목적으로 람다 식을 사용할 수 있습니다. 또한 Visual Basic에서만, 메서드 호출 대신 `Aggregate` 또는 `Group By` 절을 사용할 경우 범위 내에 있는 값 또는 식을 이 절에 전달할 수 있습니다.

다음 예제 코드에서는 정수 배열 및 문자열 배열에 대해 `Median` 메서드를 호출하는 방법을 보여 줍니다. 문자열의 경우 배열에서 문자열 길이의 중앙값이 계산됩니다. 예제에서는 각 경우에 <xref:System.Func%602> 대리자 매개 변수를 `Median` 메서드에 전달하는 방법을 보여 줍니다.

:::code language="csharp" source="./snippets/Program.cs" ID="GenericUsage":::

## <a name="adding-a-method-that-returns-a-sequence"></a>시퀀스를 반환하는 메서드 추가

값 시퀀스를 반환하는 사용자 지정 쿼리 메서드를 사용하여 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 확장할 수 있습니다. 이 경우 메서드는 <xref:System.Collections.Generic.IEnumerable%601> 형식의 컬렉션을 반환해야 합니다. 이러한 메서드는 필터 또는 데이터 변환을 값 시퀀스에 적용하는 데 사용될 수 있습니다.

다음 예제에서는 모든 기타 요소를 첫 번째 인수부터 반환하는 `AlternateElements` 확장 메서드를 만드는 방법을 보여 줍니다.

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="SequenceElement":::

다음 코드와 같이 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스에서 다른 메서드를 호출할 때와 같은 방법으로 열거 가능한 모든 컬렉션에 대해 이 확장 메서드를 호출할 수 있습니다.

:::code language="csharp" source="./snippets/Program.cs" ID="SequenceUsage":::

## <a name="see-also"></a>참조

- <xref:System.Collections.Generic.IEnumerable%601>
- [확장명 메서드](../../classes-and-structs/extension-methods.md)
