---
title: 익명 형식과 튜플 형식 중에서 선택
description: 익명 형식 및 튜플 형식 중에서 선택 하는 것이 적절 한 경우에 대해 알아봅니다.
ms.date: 06/29/2020
ms.technology: dotnet-standard
ms.openlocfilehash: bc17695830a42a6eed9d60c0e097ee9d02a7957e
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803770"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a>익명 형식과 튜플 형식 중에서 선택

적절 한 형식을 선택 하는 것은 다른 형식에 비해 유용성, 성능 및 장단점을 고려 하는 것입니다. 무명 형식은 c # 3.0부터 사용할 수 있었지만 제네릭 <xref:System.Tuple%602?displayProperty=nameWithType> 형식은 .NET Framework 4.0에서 도입 되었습니다. 이후에서는 이름에서 알 수 있는 것 처럼 언어 수준 지원에 새 옵션이 도입 되었으므로 <xref:System.ValueTuple%602?displayProperty=nameWithType> 익명 형식의 유연성을 가진 값 형식을 제공 합니다. 이 문서에서는 다른 유형을 선택 하는 것이 적절 한 경우에 대해 알아봅니다.

## <a name="usability-and-functionality"></a>유용성 및 기능

익명 형식은 LINQ (통합 언어 쿼리) 식과 함께 c # 3.0에서 도입 되었습니다. LINQ를 사용 하면 개발자가 작업 중인 개체에서 몇 가지 선택 속성을 보유 하는 무명 형식으로 쿼리 결과를 주로 프로젝션 합니다. 개체의 배열을 인스턴스화하고 <xref:System.DateTime> 두 개의 속성을 사용 하 여 익명 형식으로 프로젝션 하는 다음 예제를 살펴보겠습니다.

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

무명 형식은 연산자를 사용 하 여 인스턴스화되고 [`new`](../../csharp/language-reference/operators/new-operator.md) 속성 이름 및 형식은 선언에서 유추 됩니다. 동일한 어셈블리에 있는 둘 이상의 익명 개체 이니셜라이저가 동일한 순서에 있고 이름과 형식이 같은 속성의 시퀀스를 지정 하는 경우 컴파일러는 개체를 동일한 형식의 인스턴스로 처리 합니다. 이러한 개체는 컴파일러에서 생성된 동일한 형식 정보를 공유합니다.

이전 c # 코드 조각은 다음과 같은 두 가지 속성을 사용 하 여 익명 형식을 프로젝션 합니다. 다음은 컴파일러에서 생성 된 c # 클래스와 매우 비슷합니다.

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

자세한 내용은 [무명 형식](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조 하세요. LINQ 쿼리를 프로젝션 할 때 튜플의 기능과 동일한 기능이 존재 하므로 튜플로 속성을 선택할 수 있습니다. 이러한 튜플은 익명 형식과 마찬가지로 쿼리를 통해 흐릅니다. 이제를 사용 하는 다음 예제를 살펴보겠습니다 `System.Tuple<string, long>` .

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

를 사용 하 여 <xref:System.Tuple%602?displayProperty=nameWithType> 인스턴스는, 및와 같은 번호가 매겨진 항목 속성을 노출 합니다 `Item1` `Item2` . 속성 이름은 서 수만 제공 하므로 이러한 속성 이름을 사용 하면 속성 값의 의도를 이해 하기가 더 어려워질 수 있습니다. 또한 `System.Tuple` 형식은 참조 `class` 형식입니다. <xref:System.ValueTuple%602?displayProperty=nameWithType>그러나는 값 `struct` 형식입니다. 다음 c # 코드 조각은를 사용 하 여를 `ValueTuple<string, long>` 프로젝션 합니다. 이렇게 하면 리터럴 구문을 사용 하 여을 할당 합니다.

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

C #에서는 <xref:System.ValueTuple> 형식 및에 대 한 의미 체계를 사용 하는 튜플의 언어 지원을 제공 합니다.

- [튜플 할당](../../csharp/tuples.md#assignment-and-tuples)
- [튜플 분해](../../csharp/deconstruct.md) (튜플로 제한 되지 않음)
- [튜플 같음 검사](../../csharp/tuples.md#equality-and-tuples)
- [튜플 프로젝션 이니셜라이저](../../csharp/tuples.md#tuple-projection-initializers)

그러나 이전 예제는 모든 기능적으로 동일 합니다. 유용성 및 기본 구현에는 약간의 차이가 있습니다.

## <a name="tradeoffs"></a>균형 유지

항상 <xref:System.ValueTuple> <xref:System.Tuple> 및 익명 형식을 사용할 수 있지만 고려해 야 할 장단점이 있습니다. <xref:System.ValueTuple>형식은 변경 <xref:System.Tuple> 가능 하지만는 읽기 전용입니다. 식 트리에는 무명 형식을 사용할 수 있지만 튜플은 사용할 수 없습니다. 다음 표는 몇 가지 주요 차이점에 대 한 개요입니다.

### <a name="key-differences"></a>주요 차이점

| Name                     | 액세스 한정자 | 형식     | 사용자 지정 속성 이름 | 분해 지원 | 식 트리 지원 |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| 무명 형식          | `internal`      | `class`  | ✔️                   | ❌                     | ✔️                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | ✔️                     |
| <xref:System.ValueTuple> | `public`        | `struct` | ✔️                   | ✔️                     | ❌                     |

### <a name="serialization"></a>Serialization

형식을 선택할 때 중요 한 고려 사항 중 하나는 serialize 해야 하는지 여부입니다. serialization은 지속시키거나 전송할 수 있는 형태로 개체 상태를 변환하는 프로세스입니다. 자세한 내용은 [serialization](../../csharp/programming-guide/concepts/serialization/index.md)을 참조 하세요. Serialization이 중요할 경우 또는를 만드는 `class` 것 `struct` 은 익명 형식 또는 튜플 형식 보다 선호 됩니다.

## <a name="performance"></a>성능

이러한 형식 간의 성능은 시나리오에 따라 달라 집니다. 주요 영향은 할당과 복사 간의 균형을 유지 하는 것입니다. 대부분의 시나리오에서 영향은 작습니다. 주요 영향을 받을 수 있는 경우 의사 결정을 알리기 위해 측정이 수행 되어야 합니다.

## <a name="conclusion"></a>결론

튜플 및 익명 형식 중에서 선택할 수 있는 개발자는 여러 가지 요인을 고려해 야 합니다. 일반적으로 [식 트리로](../../csharp/expression-trees.md)작업 하지 않는 경우 튜플 구문에 익숙해지면 <xref:System.ValueTuple> 속성 이름에 유연성을 제공 하는 값 형식을 제공 하는 것을 선택 합니다. 식 트리로 작업 하는 경우 속성의 이름을 선택 하는 것이 좋습니다. 익명 형식을 선택 합니다. 그렇지 않으면 <xref:System.Tuple>를 사용합니다.

## <a name="see-also"></a>참고 항목

- [무명 형식](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [식 트리](../../csharp/expression-trees.md)
- [프레임워크 디자인 지침](index.md)
- [튜플 형식](../../csharp/tuples.md)
- [형식 디자인 지침](type.md)
