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
# <a name="choosing-between-anonymous-and-tuple-types"></a><span data-ttu-id="200d6-103">익명 형식과 튜플 형식 중에서 선택</span><span class="sxs-lookup"><span data-stu-id="200d6-103">Choosing between anonymous and tuple types</span></span>

<span data-ttu-id="200d6-104">적절 한 형식을 선택 하는 것은 다른 형식에 비해 유용성, 성능 및 장단점을 고려 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-104">Choosing the appropriate type involves considering its usability, performance, and tradeoffs compared to other types.</span></span> <span data-ttu-id="200d6-105">무명 형식은 c # 3.0부터 사용할 수 있었지만 제네릭 <xref:System.Tuple%602?displayProperty=nameWithType> 형식은 .NET Framework 4.0에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-105">Anonymous types have been available since C# 3.0, while generic <xref:System.Tuple%602?displayProperty=nameWithType> types were introduced with .NET Framework 4.0.</span></span> <span data-ttu-id="200d6-106">이후에서는 이름에서 알 수 있는 것 처럼 언어 수준 지원에 새 옵션이 도입 되었으므로 <xref:System.ValueTuple%602?displayProperty=nameWithType> 익명 형식의 유연성을 가진 값 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-106">Since then new options have been introduced with language level support, such as <xref:System.ValueTuple%602?displayProperty=nameWithType> - which as the name implies, provide a value type with the flexibility of anonymous types.</span></span> <span data-ttu-id="200d6-107">이 문서에서는 다른 유형을 선택 하는 것이 적절 한 경우에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-107">In this article, you'll learn when it's appropriate to choose one type over the other.</span></span>

## <a name="usability-and-functionality"></a><span data-ttu-id="200d6-108">유용성 및 기능</span><span class="sxs-lookup"><span data-stu-id="200d6-108">Usability and functionality</span></span>

<span data-ttu-id="200d6-109">익명 형식은 LINQ (통합 언어 쿼리) 식과 함께 c # 3.0에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-109">Anonymous types were introduced in C# 3.0 with Language-Integrated Query (LINQ) expressions.</span></span> <span data-ttu-id="200d6-110">LINQ를 사용 하면 개발자가 작업 중인 개체에서 몇 가지 선택 속성을 보유 하는 무명 형식으로 쿼리 결과를 주로 프로젝션 합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-110">With LINQ, developers often project results from queries into anonymous types that hold a few select properties from the objects they're working with.</span></span> <span data-ttu-id="200d6-111">개체의 배열을 인스턴스화하고 <xref:System.DateTime> 두 개의 속성을 사용 하 여 익명 형식으로 프로젝션 하는 다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-111">Consider the following example, that instantiates an array of <xref:System.DateTime> objects, and iterates through them projecting into an anonymous type with two properties.</span></span>

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

<span data-ttu-id="200d6-112">무명 형식은 연산자를 사용 하 여 인스턴스화되고 [`new`](../../csharp/language-reference/operators/new-operator.md) 속성 이름 및 형식은 선언에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-112">Anonymous types are instantiated by using the [`new`](../../csharp/language-reference/operators/new-operator.md) operator, and the property names and types are inferred from the declaration.</span></span> <span data-ttu-id="200d6-113">동일한 어셈블리에 있는 둘 이상의 익명 개체 이니셜라이저가 동일한 순서에 있고 이름과 형식이 같은 속성의 시퀀스를 지정 하는 경우 컴파일러는 개체를 동일한 형식의 인스턴스로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-113">If two or more anonymous object initializers in the same assembly specify a sequence of properties that are in the same order and that have the same names and types, the compiler treats the objects as instances of the same type.</span></span> <span data-ttu-id="200d6-114">이러한 개체는 컴파일러에서 생성된 동일한 형식 정보를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-114">They share the same compiler-generated type information.</span></span>

<span data-ttu-id="200d6-115">이전 c # 코드 조각은 다음과 같은 두 가지 속성을 사용 하 여 익명 형식을 프로젝션 합니다. 다음은 컴파일러에서 생성 된 c # 클래스와 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-115">The previous C# snippet projects an anonymous type with two properties, much like the following compiler-generated C# class:</span></span>

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

<span data-ttu-id="200d6-116">자세한 내용은 [무명 형식](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="200d6-116">For more information, see [anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="200d6-117">LINQ 쿼리를 프로젝션 할 때 튜플의 기능과 동일한 기능이 존재 하므로 튜플로 속성을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-117">The same functionality exists with tuples when projecting into LINQ queries, you can select properties into tuples.</span></span> <span data-ttu-id="200d6-118">이러한 튜플은 익명 형식과 마찬가지로 쿼리를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-118">These tuples flow through the query, just as anonymous types would.</span></span> <span data-ttu-id="200d6-119">이제를 사용 하는 다음 예제를 살펴보겠습니다 `System.Tuple<string, long>` .</span><span class="sxs-lookup"><span data-stu-id="200d6-119">Now consider the following example using the `System.Tuple<string, long>`.</span></span>

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

<span data-ttu-id="200d6-120">를 사용 하 여 <xref:System.Tuple%602?displayProperty=nameWithType> 인스턴스는, 및와 같은 번호가 매겨진 항목 속성을 노출 합니다 `Item1` `Item2` .</span><span class="sxs-lookup"><span data-stu-id="200d6-120">With the <xref:System.Tuple%602?displayProperty=nameWithType>, the instance exposes numbered item properties, such as `Item1`, and `Item2`.</span></span> <span data-ttu-id="200d6-121">속성 이름은 서 수만 제공 하므로 이러한 속성 이름을 사용 하면 속성 값의 의도를 이해 하기가 더 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-121">These property names can make it more difficult to understand the intent of the property values, as the property name only provides the ordinal.</span></span> <span data-ttu-id="200d6-122">또한 `System.Tuple` 형식은 참조 `class` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-122">Furthermore, the `System.Tuple` types are reference `class` types.</span></span> <span data-ttu-id="200d6-123"><xref:System.ValueTuple%602?displayProperty=nameWithType>그러나는 값 `struct` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-123">The <xref:System.ValueTuple%602?displayProperty=nameWithType> however, is a value `struct` type.</span></span> <span data-ttu-id="200d6-124">다음 c # 코드 조각은를 사용 하 여를 `ValueTuple<string, long>` 프로젝션 합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-124">The following C# snippet, uses `ValueTuple<string, long>` to project into.</span></span> <span data-ttu-id="200d6-125">이렇게 하면 리터럴 구문을 사용 하 여을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-125">In doing so, it assigns using a literal syntax.</span></span>

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

<span data-ttu-id="200d6-126">C #에서는 <xref:System.ValueTuple> 형식 및에 대 한 의미 체계를 사용 하는 튜플의 언어 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-126">C# provides language support of tuples with the <xref:System.ValueTuple> type, and semantics for:</span></span>

- [<span data-ttu-id="200d6-127">튜플 할당</span><span class="sxs-lookup"><span data-stu-id="200d6-127">Tuple assignment</span></span>](../../csharp/tuples.md#assignment-and-tuples)
- <span data-ttu-id="200d6-128">[튜플 분해](../../csharp/deconstruct.md) (튜플로 제한 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="200d6-128">[Tuple deconstruction](../../csharp/deconstruct.md) (not limited to tuples)</span></span>
- [<span data-ttu-id="200d6-129">튜플 같음 검사</span><span class="sxs-lookup"><span data-stu-id="200d6-129">Tuple equality checks</span></span>](../../csharp/tuples.md#equality-and-tuples)
- [<span data-ttu-id="200d6-130">튜플 프로젝션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="200d6-130">Tuple projection initializers</span></span>](../../csharp/tuples.md#tuple-projection-initializers)

<span data-ttu-id="200d6-131">그러나 이전 예제는 모든 기능적으로 동일 합니다. 유용성 및 기본 구현에는 약간의 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-131">The previous examples are all functionally equivalent, however; there are slight differences in their usability and their underlying implementations.</span></span>

## <a name="tradeoffs"></a><span data-ttu-id="200d6-132">균형 유지</span><span class="sxs-lookup"><span data-stu-id="200d6-132">Tradeoffs</span></span>

<span data-ttu-id="200d6-133">항상 <xref:System.ValueTuple> <xref:System.Tuple> 및 익명 형식을 사용할 수 있지만 고려해 야 할 장단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-133">You might want to always use <xref:System.ValueTuple> over <xref:System.Tuple>, and anonymous types, but there are tradeoffs you should consider.</span></span> <span data-ttu-id="200d6-134"><xref:System.ValueTuple>형식은 변경 <xref:System.Tuple> 가능 하지만는 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-134">The <xref:System.ValueTuple> types are mutable, whereas <xref:System.Tuple> are read-only.</span></span> <span data-ttu-id="200d6-135">식 트리에는 무명 형식을 사용할 수 있지만 튜플은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-135">Anonymous types can be used in expression trees, while tuples cannot.</span></span> <span data-ttu-id="200d6-136">다음 표는 몇 가지 주요 차이점에 대 한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-136">The following table is an overview of some of the key differences.</span></span>

### <a name="key-differences"></a><span data-ttu-id="200d6-137">주요 차이점</span><span class="sxs-lookup"><span data-stu-id="200d6-137">Key differences</span></span>

| <span data-ttu-id="200d6-138">Name</span><span class="sxs-lookup"><span data-stu-id="200d6-138">Name</span></span>                     | <span data-ttu-id="200d6-139">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="200d6-139">Access modifier</span></span> | <span data-ttu-id="200d6-140">형식</span><span class="sxs-lookup"><span data-stu-id="200d6-140">Type</span></span>     | <span data-ttu-id="200d6-141">사용자 지정 속성 이름</span><span class="sxs-lookup"><span data-stu-id="200d6-141">Custom property name</span></span> | <span data-ttu-id="200d6-142">분해 지원</span><span class="sxs-lookup"><span data-stu-id="200d6-142">Deconstruction support</span></span> | <span data-ttu-id="200d6-143">식 트리 지원</span><span class="sxs-lookup"><span data-stu-id="200d6-143">Expression tree support</span></span> |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| <span data-ttu-id="200d6-144">무명 형식</span><span class="sxs-lookup"><span data-stu-id="200d6-144">Anonymous types</span></span>          | `internal`      | `class`  | <span data-ttu-id="200d6-145">✔️</span><span class="sxs-lookup"><span data-stu-id="200d6-145">✔️</span></span>                   | ❌                     | <span data-ttu-id="200d6-146">✔️</span><span class="sxs-lookup"><span data-stu-id="200d6-146">✔️</span></span>                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | <span data-ttu-id="200d6-147">✔️</span><span class="sxs-lookup"><span data-stu-id="200d6-147">✔️</span></span>                     |
| <xref:System.ValueTuple> | `public`        | `struct` | <span data-ttu-id="200d6-148">✔️</span><span class="sxs-lookup"><span data-stu-id="200d6-148">✔️</span></span>                   | <span data-ttu-id="200d6-149">✔️</span><span class="sxs-lookup"><span data-stu-id="200d6-149">✔️</span></span>                     | ❌                     |

### <a name="serialization"></a><span data-ttu-id="200d6-150">Serialization</span><span class="sxs-lookup"><span data-stu-id="200d6-150">Serialization</span></span>

<span data-ttu-id="200d6-151">형식을 선택할 때 중요 한 고려 사항 중 하나는 serialize 해야 하는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-151">One important consideration when choosing a type, is whether or not it will need to be serialized.</span></span> <span data-ttu-id="200d6-152">serialization은 지속시키거나 전송할 수 있는 형태로 개체 상태를 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-152">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="200d6-153">자세한 내용은 [serialization](../../csharp/programming-guide/concepts/serialization/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="200d6-153">For more information, see [serialization](../../csharp/programming-guide/concepts/serialization/index.md).</span></span> <span data-ttu-id="200d6-154">Serialization이 중요할 경우 또는를 만드는 `class` 것 `struct` 은 익명 형식 또는 튜플 형식 보다 선호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-154">When serialization is important, creating a `class` or `struct` is preferred over anonymous types or tuple types.</span></span>

## <a name="performance"></a><span data-ttu-id="200d6-155">성능</span><span class="sxs-lookup"><span data-stu-id="200d6-155">Performance</span></span>

<span data-ttu-id="200d6-156">이러한 형식 간의 성능은 시나리오에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-156">Performance between these types depends on the scenario.</span></span> <span data-ttu-id="200d6-157">주요 영향은 할당과 복사 간의 균형을 유지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-157">The major impact involves the tradeoff between allocations and copying.</span></span> <span data-ttu-id="200d6-158">대부분의 시나리오에서 영향은 작습니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-158">In most scenarios, the impact is small.</span></span> <span data-ttu-id="200d6-159">주요 영향을 받을 수 있는 경우 의사 결정을 알리기 위해 측정이 수행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-159">When major impacts could arise, measurements should be taken to inform the decision.</span></span>

## <a name="conclusion"></a><span data-ttu-id="200d6-160">결론</span><span class="sxs-lookup"><span data-stu-id="200d6-160">Conclusion</span></span>

<span data-ttu-id="200d6-161">튜플 및 익명 형식 중에서 선택할 수 있는 개발자는 여러 가지 요인을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-161">As a developer choosing between tuples and anonymous types, there are several factors to consider.</span></span> <span data-ttu-id="200d6-162">일반적으로 [식 트리로](../../csharp/expression-trees.md)작업 하지 않는 경우 튜플 구문에 익숙해지면 <xref:System.ValueTuple> 속성 이름에 유연성을 제공 하는 값 형식을 제공 하는 것을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-162">Generally speaking, if you're not working with [expression trees](../../csharp/expression-trees.md), and you're comfortable with tuple syntax then choose <xref:System.ValueTuple> as they provide a value type with the flexibility to name properties.</span></span> <span data-ttu-id="200d6-163">식 트리로 작업 하는 경우 속성의 이름을 선택 하는 것이 좋습니다. 익명 형식을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-163">If you're working with expression trees, and you'd prefer to name properties, choose anonymous types.</span></span> <span data-ttu-id="200d6-164">그렇지 않으면 <xref:System.Tuple>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="200d6-164">Otherwise, use <xref:System.Tuple>.</span></span>

## <a name="see-also"></a><span data-ttu-id="200d6-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="200d6-165">See also</span></span>

- [<span data-ttu-id="200d6-166">무명 형식</span><span class="sxs-lookup"><span data-stu-id="200d6-166">Anonymous types</span></span>](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="200d6-167">식 트리</span><span class="sxs-lookup"><span data-stu-id="200d6-167">Expression trees</span></span>](../../csharp/expression-trees.md)
- [<span data-ttu-id="200d6-168">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="200d6-168">Framework design guidelines</span></span>](index.md)
- [<span data-ttu-id="200d6-169">튜플 형식</span><span class="sxs-lookup"><span data-stu-id="200d6-169">Tuple types</span></span>](../../csharp/tuples.md)
- [<span data-ttu-id="200d6-170">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="200d6-170">Type design guidelines</span></span>](type.md)
