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
# <a name="choosing-between-anonymous-and-tuple-types"></a><span data-ttu-id="b0172-103">무명 형식과 튜플 형식 중에서 선택</span><span class="sxs-lookup"><span data-stu-id="b0172-103">Choosing between anonymous and tuple types</span></span>

<span data-ttu-id="b0172-104">적절한 형식을 선택하려면 유용성, 성능, 장단점을 다른 형식과 비교하여 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-104">Choosing the appropriate type involves considering its usability, performance, and tradeoffs compared to other types.</span></span> <span data-ttu-id="b0172-105">무명 형식은 C# 3.0부터 제공되었고 일반 <xref:System.Tuple%602?displayProperty=nameWithType> 형식은 .NET Framework 4.0에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-105">Anonymous types have been available since C# 3.0, while generic <xref:System.Tuple%602?displayProperty=nameWithType> types were introduced with .NET Framework 4.0.</span></span> <span data-ttu-id="b0172-106">이후에는 이름에서 알 수 있는 것과 같이 <xref:System.ValueTuple%602?displayProperty=nameWithType> 같은 언어 수준 지원과 함께 새로운 옵션이 도입되어 무명 형식의 유연성을 갖춘 값 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-106">Since then new options have been introduced with language level support, such as <xref:System.ValueTuple%602?displayProperty=nameWithType> - which as the name implies, provide a value type with the flexibility of anonymous types.</span></span> <span data-ttu-id="b0172-107">이 문서에서는 다른 형식에 비해 특정 형식을 선택하는 것이 적절한 경우에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-107">In this article, you'll learn when it's appropriate to choose one type over the other.</span></span>

## <a name="usability-and-functionality"></a><span data-ttu-id="b0172-108">유용성 및 기능</span><span class="sxs-lookup"><span data-stu-id="b0172-108">Usability and functionality</span></span>

<span data-ttu-id="b0172-109">무명 형식은 C# 3.0에서 LINQ(Language-Integrated Query) 식에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-109">Anonymous types were introduced in C# 3.0 with Language-Integrated Query (LINQ) expressions.</span></span> <span data-ttu-id="b0172-110">LINQ를 사용할 때 개발자는 작업 중인 개체의 몇 가지 선택 속성이 포함된 무명 형식으로 쿼리 결과를 프로젝션하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-110">With LINQ, developers often project results from queries into anonymous types that hold a few select properties from the objects they're working with.</span></span> <span data-ttu-id="b0172-111">다음 예에서는 <xref:System.DateTime> 개체의 배열을 인스턴스화한 후 두 가지 속성으로 무명 형식으로 프로젝션하여 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-111">Consider the following example, that instantiates an array of <xref:System.DateTime> objects, and iterates through them projecting into an anonymous type with two properties.</span></span>

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

<span data-ttu-id="b0172-112">무명 형식은 [`new`](../../csharp/language-reference/operators/new-operator.md) 연산자를 사용하여 인스턴스화되고, 속성 이름 및 형식이 선언에서 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-112">Anonymous types are instantiated by using the [`new`](../../csharp/language-reference/operators/new-operator.md) operator, and the property names and types are inferred from the declaration.</span></span> <span data-ttu-id="b0172-113">동일한 어셈블리에서 둘 이상의 익명 개체 이니셜라이저가 순서와 이름 및 형식이 동일한 속성의 시퀀스를 지정하는 경우 컴파일러는 개체를 동일한 형식의 인스턴스로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-113">If two or more anonymous object initializers in the same assembly specify a sequence of properties that are in the same order and that have the same names and types, the compiler treats the objects as instances of the same type.</span></span> <span data-ttu-id="b0172-114">이러한 개체는 컴파일러에서 생성된 동일한 형식 정보를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-114">They share the same compiler-generated type information.</span></span>

<span data-ttu-id="b0172-115">앞의 C# 코드 조각은 컴파일러에서 생성된 다음 C# 클래스와 매우 비슷한 두 속성을 사용하여 무명 형식을 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-115">The previous C# snippet projects an anonymous type with two properties, much like the following compiler-generated C# class:</span></span>

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

<span data-ttu-id="b0172-116">자세한 내용은 [무명 형식](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0172-116">For more information, see [anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="b0172-117">튜플의 경우 LINQ 쿼리를 프로젝션할 때 동일한 기능이 있습니다. 튜플에 속성을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-117">The same functionality exists with tuples when projecting into LINQ queries, you can select properties into tuples.</span></span> <span data-ttu-id="b0172-118">이러한 튜플은 무명 형식과 마찬가지로 쿼리를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-118">These tuples flow through the query, just as anonymous types would.</span></span> <span data-ttu-id="b0172-119">이제 `System.Tuple<string, long>`을 사용하는 다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-119">Now consider the following example using the `System.Tuple<string, long>`.</span></span>

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

<span data-ttu-id="b0172-120"><xref:System.Tuple%602?displayProperty=nameWithType>에서 인스턴스는 `Item1`및 `Item2`와 같이 번호가 매겨진 항목 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-120">With the <xref:System.Tuple%602?displayProperty=nameWithType>, the instance exposes numbered item properties, such as `Item1`, and `Item2`.</span></span> <span data-ttu-id="b0172-121">이러한 속성 이름은 서수만 제공하므로, 이 속성 이름을 사용하면 속성 값의 의도를 이해하기가 더 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-121">These property names can make it more difficult to understand the intent of the property values, as the property name only provides the ordinal.</span></span> <span data-ttu-id="b0172-122">또한 `System.Tuple` 형식은 참조 `class` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-122">Furthermore, the `System.Tuple` types are reference `class` types.</span></span> <span data-ttu-id="b0172-123">하지만 <xref:System.ValueTuple%602?displayProperty=nameWithType>는 값 `struct` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-123">The <xref:System.ValueTuple%602?displayProperty=nameWithType> however, is a value `struct` type.</span></span> <span data-ttu-id="b0172-124">다음 C# 코드 조각에서는 `ValueTuple<string, long>`을 사용하여 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-124">The following C# snippet, uses `ValueTuple<string, long>` to project into.</span></span> <span data-ttu-id="b0172-125">이때 리터럴 구문을 사용하여 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-125">In doing so, it assigns using a literal syntax.</span></span>

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

<span data-ttu-id="b0172-126">튜플에 관한 자세한 내용은 [튜플 형식( C# 참조)](../../csharp/language-reference/builtin-types/value-tuples.md) 또는 [튜플(Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0172-126">For more information about tuples, see [Tuple types (C# reference)](../../csharp/language-reference/builtin-types/value-tuples.md) or [Tuples (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md).</span></span>

<span data-ttu-id="b0172-127">앞의 예제는 모든 기능 면에서 동일하지만 유용성 및 기본 구현에는 약간의 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-127">The previous examples are all functionally equivalent, however; there are slight differences in their usability and their underlying implementations.</span></span>

## <a name="tradeoffs"></a><span data-ttu-id="b0172-128">균형 유지</span><span class="sxs-lookup"><span data-stu-id="b0172-128">Tradeoffs</span></span>

<span data-ttu-id="b0172-129"><xref:System.Tuple>에 비해 항상 <xref:System.ValueTuple>을 사용하고, 무명 형식을 사용하는 것이 좋습니다. 하지만 고려해야 할 장단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-129">You might want to always use <xref:System.ValueTuple> over <xref:System.Tuple>, and anonymous types, but there are tradeoffs you should consider.</span></span> <span data-ttu-id="b0172-130"><xref:System.ValueTuple> 형식은 변경 가능하고, <xref:System.Tuple>은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-130">The <xref:System.ValueTuple> types are mutable, whereas <xref:System.Tuple> are read-only.</span></span> <span data-ttu-id="b0172-131">무명 형식은 식 트리에 사용할 수 있고 튜플은 식 트리에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-131">Anonymous types can be used in expression trees, while tuples cannot.</span></span> <span data-ttu-id="b0172-132">다음 표는 주요 차이점을 개략적으로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-132">The following table is an overview of some of the key differences.</span></span>

### <a name="key-differences"></a><span data-ttu-id="b0172-133">주요 차이점</span><span class="sxs-lookup"><span data-stu-id="b0172-133">Key differences</span></span>

| <span data-ttu-id="b0172-134">이름</span><span class="sxs-lookup"><span data-stu-id="b0172-134">Name</span></span>                     | <span data-ttu-id="b0172-135">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="b0172-135">Access modifier</span></span> | <span data-ttu-id="b0172-136">형식</span><span class="sxs-lookup"><span data-stu-id="b0172-136">Type</span></span>     | <span data-ttu-id="b0172-137">사용자 지정 멤버 이름</span><span class="sxs-lookup"><span data-stu-id="b0172-137">Custom member name</span></span> | <span data-ttu-id="b0172-138">분해 지원</span><span class="sxs-lookup"><span data-stu-id="b0172-138">Deconstruction support</span></span> | <span data-ttu-id="b0172-139">식 트리 지원</span><span class="sxs-lookup"><span data-stu-id="b0172-139">Expression tree support</span></span> |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| <span data-ttu-id="b0172-140">무명 형식</span><span class="sxs-lookup"><span data-stu-id="b0172-140">Anonymous types</span></span>          | `internal`      | `class`  | <span data-ttu-id="b0172-141">✔️</span><span class="sxs-lookup"><span data-stu-id="b0172-141">✔️</span></span>                   | ❌                     | <span data-ttu-id="b0172-142">✔️</span><span class="sxs-lookup"><span data-stu-id="b0172-142">✔️</span></span>                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | <span data-ttu-id="b0172-143">✔️</span><span class="sxs-lookup"><span data-stu-id="b0172-143">✔️</span></span>                     |
| <xref:System.ValueTuple> | `public`        | `struct` | <span data-ttu-id="b0172-144">✔️</span><span class="sxs-lookup"><span data-stu-id="b0172-144">✔️</span></span>                   | <span data-ttu-id="b0172-145">✔️</span><span class="sxs-lookup"><span data-stu-id="b0172-145">✔️</span></span>                     | ❌                     |

### <a name="serialization"></a><span data-ttu-id="b0172-146">Serialization</span><span class="sxs-lookup"><span data-stu-id="b0172-146">Serialization</span></span>

<span data-ttu-id="b0172-147">형식을 선택할 때 중요한 한 가지 고려 사항은 직렬화해야 하는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-147">One important consideration when choosing a type, is whether or not it will need to be serialized.</span></span> <span data-ttu-id="b0172-148">serialization은 지속시키거나 전송할 수 있는 형태로 개체 상태를 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-148">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="b0172-149">자세한 내용은 [serialization](../../csharp/programming-guide/concepts/serialization/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0172-149">For more information, see [serialization](../../csharp/programming-guide/concepts/serialization/index.md).</span></span> <span data-ttu-id="b0172-150">serialization이 중요한 경우에는 무명 형식이나 튜플 형식보다 `class` 또는 `struct`를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-150">When serialization is important, creating a `class` or `struct` is preferred over anonymous types or tuple types.</span></span>

## <a name="performance"></a><span data-ttu-id="b0172-151">성능</span><span class="sxs-lookup"><span data-stu-id="b0172-151">Performance</span></span>

<span data-ttu-id="b0172-152">이러한 형식 간의 성능은 시나리오에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-152">Performance between these types depends on the scenario.</span></span> <span data-ttu-id="b0172-153">주요 영향은 할당과 복사 간의 장단점과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-153">The major impact involves the tradeoff between allocations and copying.</span></span> <span data-ttu-id="b0172-154">대부분의 시나리오에서 영향은 적습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-154">In most scenarios, the impact is small.</span></span> <span data-ttu-id="b0172-155">주요 영향이 발생할 수 있는 경우 의사 결정을 알리기 위해 측정이 수행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-155">When major impacts could arise, measurements should be taken to inform the decision.</span></span>

## <a name="conclusion"></a><span data-ttu-id="b0172-156">결론</span><span class="sxs-lookup"><span data-stu-id="b0172-156">Conclusion</span></span>

<span data-ttu-id="b0172-157">튜플 형식과 무명 형식 중에서 선택할 때 개발자가 고려할 몇 가지 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-157">As a developer choosing between tuples and anonymous types, there are several factors to consider.</span></span> <span data-ttu-id="b0172-158">일반적으로, [식 트리](../../csharp/expression-trees.md)로 작업하지 않으며 튜플 구문에 익숙한 경우에는 유연하게 속성 이름을 지정할 수 있는 값 형식을 제공하므로 <xref:System.ValueTuple>을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-158">Generally speaking, if you're not working with [expression trees](../../csharp/expression-trees.md), and you're comfortable with tuple syntax then choose <xref:System.ValueTuple> as they provide a value type with the flexibility to name properties.</span></span> <span data-ttu-id="b0172-159">식 트리로 작업하며 속성 이름을 지정하려는 경우 무명 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-159">If you're working with expression trees, and you'd prefer to name properties, choose anonymous types.</span></span> <span data-ttu-id="b0172-160">그렇지 않으면 <xref:System.Tuple>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0172-160">Otherwise, use <xref:System.Tuple>.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0172-161">참조</span><span class="sxs-lookup"><span data-stu-id="b0172-161">See also</span></span>

- [<span data-ttu-id="b0172-162">무명 형식</span><span class="sxs-lookup"><span data-stu-id="b0172-162">Anonymous types</span></span>](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="b0172-163">식 트리</span><span class="sxs-lookup"><span data-stu-id="b0172-163">Expression trees</span></span>](../../csharp/expression-trees.md)
- [<span data-ttu-id="b0172-164">튜플 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b0172-164">Tuple types (C# reference)</span></span>](../../csharp/language-reference/builtin-types/value-tuples.md)
- [<span data-ttu-id="b0172-165">튜플(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0172-165">Tuples (Visual Basic)</span></span>](../../visual-basic/programming-guide/language-features/data-types/tuples.md)
- [<span data-ttu-id="b0172-166">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b0172-166">Type design guidelines</span></span>](../design-guidelines/type.md)
