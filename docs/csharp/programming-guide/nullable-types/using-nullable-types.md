---
title: nullable 형식 사용 - C# 프로그래밍 가이드
ms.custom: seodec18
description: C# nullable 형식을 사용하는 방법 알아보기
ms.date: 08/02/2018
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 75b8889f5f1f1b0dab4aa365daa34ef5ae226b02
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588826"
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="5b7a7-103">nullable 형식 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5b7a7-103">Using nullable types (C# Programming Guide)</span></span>

<span data-ttu-id="5b7a7-104">nullable 형식은 기본 값 형식 `T`의 모든 값과 추가 [Null](../../language-reference/keywords/null.md) 값을 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-104">Nullable types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="5b7a7-105">자세한 내용은 [Nullable 형식](index.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-105">For more information, see the [Nullable types](index.md) topic.</span></span>

<span data-ttu-id="5b7a7-106">다음 형식 `Nullable<T>` 또는 `T?` 중 하나에서 nullable 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-106">You can refer to a nullable type in any of the following forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="5b7a7-107">이러한 두 가지 형태는 동일하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-107">These two forms are interchangeable.</span></span>  
  
## <a name="declaration-and-assignment"></a><span data-ttu-id="5b7a7-108">선언 및 할당</span><span class="sxs-lookup"><span data-stu-id="5b7a7-108">Declaration and assignment</span></span>

<span data-ttu-id="5b7a7-109">값 형식은 해당 nullable 형식으로 암시적으로 변환될 수 있으므로 해당 기본 값 형식과 마찬가지로 값을 nullable 형식에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-109">As a value type can be implicitly converted to the corresponding nullable type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="5b7a7-110">`null` 값을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-110">You also can assign the `null` value.</span></span>  <span data-ttu-id="5b7a7-111">예:</span><span class="sxs-lookup"><span data-stu-id="5b7a7-111">For example:</span></span>
  
[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="5b7a7-112">nullable 형식 값의 검사</span><span class="sxs-lookup"><span data-stu-id="5b7a7-112">Examination of a nullable type value</span></span>

<span data-ttu-id="5b7a7-113">다음 읽기 전용 속성을 사용하여 Null에 대한 nullable 형식의 인스턴스를 검사하고 내부 형식의 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-113">Use the following readonly properties to examine an instance of a nullable type for null and retrieve a value of an underlying type:</span></span>  
  
- <span data-ttu-id="5b7a7-114"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType>은 nullable 형식의 인스턴스에 해당 기본 형식의 값이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-114"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable type has a value of its underlying type.</span></span>
  
- <span data-ttu-id="5b7a7-115"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType>은 <xref:System.Nullable%601.HasValue%2A>가 `true`인 경우 기본 형식의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-115"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="5b7a7-116"><xref:System.Nullable%601.HasValue%2A>가 `false`인 경우 <xref:System.Nullable%601.Value%2A> 속성은 <xref:System.InvalidOperationException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-116">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>
  
<span data-ttu-id="5b7a7-117">다음 예제의 코드는 `HasValue` 속성을 사용하여 표시하기 전에 변수가 값을 포함하는지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-117">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>
  
[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]
  
<span data-ttu-id="5b7a7-118">다음 예제와 같이 `HasValue` 속성을 사용하는 대신 nullable 형식 변수를 `null`과 비교할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-118">You also can compare a nullable type variable with `null` instead of using the `HasValue` property, as the following example shows:</span></span>  
  
[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="5b7a7-119">C# 7.0부터는 [패턴 일치](../../pattern-matching.md)를 사용하여 nullable 형식의 값을 검사하고 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-119">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-type-to-an-underlying-type"></a><span data-ttu-id="5b7a7-120">nullable 형식에서 기본 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="5b7a7-120">Conversion from a nullable type to an underlying type</span></span>

<span data-ttu-id="5b7a7-121">nullable이 아닌 형식에 nullable 형식 값을 할당해야 하는 경우 [Null 병합 연산자를 사용하여 `??`](../../language-reference/operators/null-coalescing-operator.md) nullable 형식 값이 Null인 경우 할당될 값을 지정합니다(<xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> 메서드를 사용하여 작업을 수행할 수도 있음).</span><span class="sxs-lookup"><span data-stu-id="5b7a7-121">If you need to assign a nullable type value to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a nullable type value is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>
  
[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="5b7a7-122">nullable 형식 값이 Null일 때 사용될 값이 기본 값 형식의 기본 값이어야 하는 경우 <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-122">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is null should be the default value of the underlying value type.</span></span>
  
<span data-ttu-id="5b7a7-123">nullable 형식을 nullable이 아닌 형식으로 명시적으로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-123">You can explicitly cast a nullable type to a non-nullable type.</span></span> <span data-ttu-id="5b7a7-124">예:</span><span class="sxs-lookup"><span data-stu-id="5b7a7-124">For example:</span></span>  
  
[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="5b7a7-125">런타임 시 nullable 형식의 값이 Null인 경우 명시적 캐스트는 <xref:System.InvalidOperationException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-125">At run time, if the value of a nullable type is null, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="5b7a7-126">nullable이 아닌 값 형식이 해당 nullable 형식으로 암시적으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-126">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>
  
## <a name="operators"></a><span data-ttu-id="5b7a7-127">연산자</span><span class="sxs-lookup"><span data-stu-id="5b7a7-127">Operators</span></span>

<span data-ttu-id="5b7a7-128">미리 정의된 단항 및 이항 연산자와 값 형식에 대해 존재하는 모든 사용자 정의 연산자는 nullable 형식에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-128">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="5b7a7-129">이러한 연산자는 하나 또는 두 개의 피연산자가 Null인 경우 Null 값을 생성하고, 그렇지 않으면 연산자는 포함된 값을 사용하여 결과를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-129">These operators produce a null value if one or both operands are null; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="5b7a7-130">예:</span><span class="sxs-lookup"><span data-stu-id="5b7a7-130">For example:</span></span>  
  
[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> <span data-ttu-id="5b7a7-131">`|` 형식의 경우 미리 정의된 `bool?` 및 `&` 연산자는 이 섹션에서 설명된 규칙을 따르지 않습니다. 연산자 평가의 결과는 피연산자 중 하나가 Null인 경우에도 Null이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-131">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is null.</span></span> <span data-ttu-id="5b7a7-132">자세한 내용은 [부울 논리 연산자](../../language-reference/operators/boolean-logical-operators.md) 문서의 [Nullable 부울 논리 연산자](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-132">For more information, see the [Nullable Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md) article.</span></span>
  
<span data-ttu-id="5b7a7-133">관계 연산자(`<`, `>`, `<=`, `>=`)의 경우 하나 또는 두 개의 피연산자가 Null인 경우 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-133">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are null, the result is `false`.</span></span> <span data-ttu-id="5b7a7-134">특정 비교(예: `<=`)에서는 `false`를 반환하고 그 반대의 비교(`>`)에서는 `true`를 반환한다고 가정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-134">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="5b7a7-135">다음 예제에서는 10이</span><span class="sxs-lookup"><span data-stu-id="5b7a7-135">The following example shows that 10 is</span></span>

- <span data-ttu-id="5b7a7-136">Null보다 크거나 같거나</span><span class="sxs-lookup"><span data-stu-id="5b7a7-136">neither greater than or equal to null,</span></span>
- <span data-ttu-id="5b7a7-137">Null보다 작지 않음을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-137">nor less than null.</span></span>
  
[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]
  
<span data-ttu-id="5b7a7-138">또한 위의 예제에서는 둘 다 Null인 두 nullable 형식의 같음 비교는 `true`로 계산되는 것을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-138">The above example also shows that an equality comparison of two nullable types that are both null evaluates to `true`.</span></span>

<span data-ttu-id="5b7a7-139">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [리프트 연산자](~/_csharplang/spec/expressions.md#lifted-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-139">For more information, see the [Lifted operators](~/_csharplang/spec/expressions.md#lifted-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="5b7a7-140">boxing 및 unboxing</span><span class="sxs-lookup"><span data-stu-id="5b7a7-140">Boxing and unboxing</span></span>

<span data-ttu-id="5b7a7-141">nullable 값 형식은 다음 규칙에 따라 [boxed](../types/boxing-and-unboxing.md)됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-141">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="5b7a7-142"><xref:System.Nullable%601.HasValue%2A>가 `false`를 반환하는 경우 Null 참조가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-142">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>  
- <span data-ttu-id="5b7a7-143"><xref:System.Nullable%601.HasValue%2A>가 `true`를 반환하는 경우 <xref:System.Nullable%601>의 인스턴스가 아닌 기본 값 형식의 값 `T`는 boxed됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-143">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="5b7a7-144">다음 예제와 같이 boxed 값 형식을 해당 nullable 형식으로 unbox할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7a7-144">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a><span data-ttu-id="5b7a7-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b7a7-145">See also</span></span>

- [<span data-ttu-id="5b7a7-146">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="5b7a7-146">Nullable types</span></span>](index.md)
- [<span data-ttu-id="5b7a7-147">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5b7a7-147">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5b7a7-148">'리프트'란 정확히 어떤 의미입니까?</span><span class="sxs-lookup"><span data-stu-id="5b7a7-148">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
