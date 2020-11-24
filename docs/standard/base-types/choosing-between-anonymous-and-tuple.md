---
title: 무명 형식과 튜플 형식 중에서 선택
description: 무명 형식과 튜플 형식 중에서 선택하는 것이 적절한 경우에 대해 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 07/01/2020
ms.openlocfilehash: f8465b2f22ecfafd739355ddd35635e2eee49232
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823201"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a>무명 형식과 튜플 형식 중에서 선택

적절한 형식을 선택하려면 유용성, 성능, 장단점을 다른 형식과 비교하여 고려해야 합니다. 무명 형식은 C# 3.0부터 제공되었고 일반 <xref:System.Tuple%602?displayProperty=nameWithType> 형식은 .NET Framework 4.0에서 도입되었습니다. 이후에는 이름에서 알 수 있는 것과 같이 <xref:System.ValueTuple%602?displayProperty=nameWithType> 같은 언어 수준 지원과 함께 새로운 옵션이 도입되어 무명 형식의 유연성을 갖춘 값 형식을 제공합니다. 이 문서에서는 다른 형식에 비해 특정 형식을 선택하는 것이 적절한 경우에 대해 알아봅니다.

## <a name="usability-and-functionality"></a>유용성 및 기능

무명 형식은 C# 3.0에서 LINQ(Language-Integrated Query) 식에 도입되었습니다. LINQ를 사용할 때 개발자는 작업 중인 개체의 몇 가지 선택 속성이 포함된 무명 형식으로 쿼리 결과를 프로젝션하는 경우가 많습니다. 다음 예에서는 <xref:System.DateTime> 개체의 배열을 인스턴스화한 후 두 가지 속성으로 무명 형식으로 프로젝션하여 반복합니다.

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var anonymous in
             dates.Select(
                 date => new { Formatted = $"{date:MMM dd, yyyy hh:mm zzz}", date.Ticks }))
{
    Console.WriteLine($"Ticks: {anonymous.Ticks}, formatted: {anonymous.Formatted}");
}
```

무명 형식은 [`new`](../../csharp/language-reference/operators/new-operator.md) 연산자를 사용하여 인스턴스화되고, 속성 이름 및 형식이 선언에서 유추됩니다. 동일한 어셈블리에서 둘 이상의 익명 개체 이니셜라이저가 순서와 이름 및 형식이 동일한 속성의 시퀀스를 지정하는 경우 컴파일러는 개체를 동일한 형식의 인스턴스로 처리합니다. 이러한 개체는 컴파일러에서 생성된 동일한 형식 정보를 공유합니다.

앞의 C# 코드 조각은 컴파일러에서 생성된 다음 C# 클래스와 매우 비슷한 두 속성을 사용하여 무명 형식을 프로젝션합니다.

```csharp
internal sealed class f__AnonymousType0
{
    public string Formatted { get; }
    public long Ticks { get; }

    public f__AnonymousType0(string formatted, long ticks)
    {
        Formatted = formatted;
        Ticks = ticks;
    }
}
```

자세한 내용은 [무명 형식](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조하세요. 튜플의 경우 LINQ 쿼리를 프로젝션할 때 동일한 기능이 있습니다. 튜플에 속성을 선택할 수 있습니다. 이러한 튜플은 무명 형식과 마찬가지로 쿼리를 통해 흐릅니다. 이제 `System.Tuple<string, long>`을 사용하는 다음 예제를 살펴보겠습니다.

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var tuple in
            dates.Select(
                date => new Tuple<string, long>($"{date:MMM dd, yyyy hh:mm zzz}", date.Ticks)))
{
    Console.WriteLine($"Ticks: {tuple.Item2}, formatted: {tuple.Item1}");
}
```

<xref:System.Tuple%602?displayProperty=nameWithType>에서 인스턴스는 `Item1`및 `Item2`와 같이 번호가 매겨진 항목 속성을 노출합니다. 이러한 속성 이름은 서수만 제공하므로, 이 속성 이름을 사용하면 속성 값의 의도를 이해하기가 더 어려울 수 있습니다. 또한 `System.Tuple` 형식은 참조 `class` 형식입니다. 하지만 <xref:System.ValueTuple%602?displayProperty=nameWithType>는 값 `struct` 형식입니다. 다음 C# 코드 조각에서는 `ValueTuple<string, long>`을 사용하여 프로젝션합니다. 이때 리터럴 구문을 사용하여 할당합니다.

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var (formatted, ticks) in
            dates.Select(
                date => (Formatted: $"{date:MMM dd, yyyy at hh:mm zzz}", date.Ticks)))
{
    Console.WriteLine($"Ticks: {ticks}, formatted: {formatted}");
}
```

튜플에 관한 자세한 내용은 [튜플 형식( C# 참조)](../../csharp/language-reference/builtin-types/value-tuples.md) 또는 [튜플(Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md)을 참조하세요.

앞의 예제는 모든 기능 면에서 동일하지만 유용성 및 기본 구현에는 약간의 차이가 있습니다.

## <a name="tradeoffs"></a>균형 유지

<xref:System.Tuple>에 비해 항상 <xref:System.ValueTuple>을 사용하고, 무명 형식을 사용하는 것이 좋습니다. 하지만 고려해야 할 장단점이 있습니다. <xref:System.ValueTuple> 형식은 변경 가능하고, <xref:System.Tuple>은 읽기 전용입니다. 무명 형식은 식 트리에 사용할 수 있고 튜플은 식 트리에 사용할 수 없습니다. 다음 표는 주요 차이점을 개략적으로 보여 줍니다.

### <a name="key-differences"></a>주요 차이점

| 이름                     | 액세스 한정자 | 형식     | 사용자 지정 멤버 이름 | 분해 지원 | 식 트리 지원 |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| 무명 형식          | `internal`      | `class`  | ✔️                   | ❌                     | ✔️                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | ✔️                     |
| <xref:System.ValueTuple> | `public`        | `struct` | ✔️                   | ✔️                     | ❌                     |

### <a name="serialization"></a>Serialization

형식을 선택할 때 중요한 한 가지 고려 사항은 직렬화해야 하는지 여부입니다. serialization은 지속시키거나 전송할 수 있는 형태로 개체 상태를 변환하는 프로세스입니다. 자세한 내용은 [serialization](../../csharp/programming-guide/concepts/serialization/index.md)을 참조하세요. serialization이 중요한 경우에는 무명 형식이나 튜플 형식보다 `class` 또는 `struct`를 만드는 것이 좋습니다.

## <a name="performance"></a>성능

이러한 형식 간의 성능은 시나리오에 따라 다릅니다. 주요 영향은 할당과 복사 간의 장단점과 관련이 있습니다. 대부분의 시나리오에서 영향은 적습니다. 주요 영향이 발생할 수 있는 경우 의사 결정을 알리기 위해 측정이 수행되어야 합니다.

## <a name="conclusion"></a>결론

튜플 형식과 무명 형식 중에서 선택할 때 개발자가 고려할 몇 가지 요소가 있습니다. 일반적으로, [식 트리](../../csharp/expression-trees.md)로 작업하지 않으며 튜플 구문에 익숙한 경우에는 유연하게 속성 이름을 지정할 수 있는 값 형식을 제공하므로 <xref:System.ValueTuple>을 선택합니다. 식 트리로 작업하며 속성 이름을 지정하려는 경우 무명 형식을 선택합니다. 그렇지 않으면 <xref:System.Tuple>를 사용합니다.

## <a name="see-also"></a>참조

- [무명 형식](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [식 트리](../../csharp/expression-trees.md)
- [튜플 형식(C# 참조)](../../csharp/language-reference/builtin-types/value-tuples.md)
- [튜플(Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md)
- [형식 디자인 지침](../design-guidelines/type.md)
