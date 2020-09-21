---
title: Null 허용 값 형식 - C# 참조
description: C# nullable 값 형식 및 사용 방법 알아보기
ms.date: 11/04/2019
helpviewer_keywords:
- nullable value types [C#]
ms.openlocfilehash: 8c3a8b997fbb8154f79dff04018cf3ea76f85d7a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537355"
---
# <a name="nullable-value-types-c-reference"></a><span data-ttu-id="097f9-103">Nullalbe 값 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="097f9-103">Nullable value types (C# reference)</span></span>

<span data-ttu-id="097f9-104">*Null 허용 값 형식* `T?`는 기본 [값 형식](value-types.md) `T`의 모든 값과 추가 [null](../keywords/null.md) 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-104">A *nullable value type* `T?` represents all values of its underlying [value type](value-types.md) `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="097f9-105">예를 들어 `bool?` 변수에는 다음 세 가지 값 중 하나를 할당할 수 있습니다. `true`, `false`, `null`.</span><span class="sxs-lookup"><span data-stu-id="097f9-105">For example, you can assign any of the following three values to a `bool?` variable: `true`, `false`, or `null`.</span></span> <span data-ttu-id="097f9-106">기본 값 형식 `T`는 null 허용 값 형식 자체일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-106">An underlying value type `T` cannot be a nullable value type itself.</span></span>

> [!NOTE]
> <span data-ttu-id="097f9-107">C# 8.0에서는 nullable 참조 형식 기능을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-107">C# 8.0 introduces the nullable reference types feature.</span></span> <span data-ttu-id="097f9-108">자세한 내용은 [nullable 참조 형식](nullable-reference-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="097f9-108">For more information, see [Nullable reference types](nullable-reference-types.md).</span></span> <span data-ttu-id="097f9-109">Null 허용 값 형식은 C# 2부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-109">The nullable value types are available beginning with C# 2.</span></span>

<span data-ttu-id="097f9-110">Null 허용 값 형식은 제네릭 <xref:System.Nullable%601?displayProperty=nameWithType> 구조체의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-110">Any nullable value type is an instance of the generic <xref:System.Nullable%601?displayProperty=nameWithType> structure.</span></span> <span data-ttu-id="097f9-111">서로 교환 가능한 형식인 `Nullable<T>` 또는 `T?` 중 하나에서 기본 값 형식 `T`의 null 허용 값 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-111">You can refer to a nullable value type with an underlying type `T` in any of the following interchangeable forms: `Nullable<T>` or `T?`.</span></span>

<span data-ttu-id="097f9-112">기본 값 형식의 정의되지 않은 값을 표시해야 하는 경우 일반적으로 null 허용 값 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-112">You typically use a nullable value type when you need to represent the undefined value of an underlying value type.</span></span> <span data-ttu-id="097f9-113">예를 들어 부울(`bool`) 변수는 `true` 또는 `false`만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-113">For example, a Boolean, or `bool`, variable can only be either `true` or `false`.</span></span> <span data-ttu-id="097f9-114">그러나 일부 애플리케이션에서는 변수 값이 정의되지 않았거나 누락될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-114">However, in some applications a variable value can be undefined or missing.</span></span> <span data-ttu-id="097f9-115">예를 들어 데이터베이스 필드는 `true` 또는 `false`를 포함하거나 아무 값도 없을 수 있습니다(즉 `NULL`).</span><span class="sxs-lookup"><span data-stu-id="097f9-115">For example, a database field may contain `true` or `false`, or it may contain no value at all, that is, `NULL`.</span></span> <span data-ttu-id="097f9-116">이러한 시나리오에서 `bool?` 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-116">You can use the `bool?` type in that scenario.</span></span>

## <a name="declaration-and-assignment"></a><span data-ttu-id="097f9-117">선언 및 할당</span><span class="sxs-lookup"><span data-stu-id="097f9-117">Declaration and assignment</span></span>

<span data-ttu-id="097f9-118">값 형식이 암시적으로 해당 null 허용 값 형식으로 변환될 수 있기 때문에 기본 값 형식에서와 마찬가지로 null 허용 값 형식의 변수에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-118">As a value type is implicitly convertible to the corresponding nullable value type, you can assign a value to a variable of a nullable value type as you would do that for its underlying value type.</span></span> <span data-ttu-id="097f9-119">`null` 값을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-119">You can also assign the `null` value.</span></span> <span data-ttu-id="097f9-120">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="097f9-120">For example:</span></span>

[!code-csharp[declare and assign](snippets/NullableValueTypes.cs#Declaration)]

<span data-ttu-id="097f9-121">Null 허용 값 형식의 기본값은 `null`을 나타냅니다. 즉, <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> 속성이 `false`을 반환하는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-121">The default value of a nullable value type represents `null`, that is, it's an instance whose <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> property returns `false`.</span></span>

## <a name="examination-of-an-instance-of-a-nullable-value-type"></a><span data-ttu-id="097f9-122">Null 허용 값 형식의 인스턴스 검사</span><span class="sxs-lookup"><span data-stu-id="097f9-122">Examination of an instance of a nullable value type</span></span>

<span data-ttu-id="097f9-123">C# 7.0부터 [`is`형식 패턴 포함 연산자](../operators/type-testing-and-cast.md#type-testing-with-pattern-matching)를 사용하여 null 허용 값 형식의 인스턴스에서 `null` 여부를 검사하고 기본 형식의 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-123">Beginning with C# 7.0, you can use the [`is` operator with a type pattern](../operators/type-testing-and-cast.md#type-testing-with-pattern-matching) to both examine an instance of a nullable value type for `null` and retrieve a value of an underlying type:</span></span>

[!code-csharp-interactive[use pattern matching](snippets/NullableValueTypes.cs#PatternMatching)]

<span data-ttu-id="097f9-124">항상 다음 읽기 전용 속성을 사용하여 null 허용 값 형식 변수의 값을 검사하고 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-124">You always can use the following read-only properties to examine and get a value of a nullable value type variable:</span></span>

- <span data-ttu-id="097f9-125"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType>은 null 허용 값 형식의 인스턴스에 해당 기본 형식의 값이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-125"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable value type has a value of its underlying type.</span></span>

- <span data-ttu-id="097f9-126"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType>은 <xref:System.Nullable%601.HasValue%2A>가 `true`인 경우 기본 형식의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-126"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="097f9-127"><xref:System.Nullable%601.HasValue%2A>가 `false`인 경우 <xref:System.Nullable%601.Value%2A> 속성은 <xref:System.InvalidOperationException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-127">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="097f9-128">다음 예제는 `HasValue` 속성을 사용하여 표시하기 전에 변수가 값을 포함하는지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-128">The following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>

[!code-csharp-interactive[use HasValue](snippets/NullableValueTypes.cs#HasValue)]

<span data-ttu-id="097f9-129">다음 예제와 같이 `HasValue` 속성을 사용하는 대신 null 허용 값 형식 변수를 `null`과 비교할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-129">You can also compare a variable of a nullable value type with `null` instead of using the `HasValue` property, as the following example shows:</span></span>

[!code-csharp-interactive[use comparison with null](snippets/NullableValueTypes.cs#CompareWithNull)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a><span data-ttu-id="097f9-130">nullable 값 형식에서 기본 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="097f9-130">Conversion from a nullable value type to an underlying type</span></span>

<span data-ttu-id="097f9-131">Null 허용 값 형식의 값을 null을 허용하지 않는 값 형식 변수에 할당하려는 경우 `null` 대신 할당할 값을 지정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-131">If you want to assign a value of a nullable value type to a non-nullable value type variable, you might need to specify the value to be assigned in place of `null`.</span></span> <span data-ttu-id="097f9-132">[null 병합 연산자`??`](../operators/null-coalescing-operator.md)를 사용하여 이 작업을 수행할 수 있습니다(<xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> 메서드를 동일한 용도로 사용할 수도 있음).</span><span class="sxs-lookup"><span data-stu-id="097f9-132">Use the [null-coalescing operator `??`](../operators/null-coalescing-operator.md) to do that (you can also use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method for the same purpose):</span></span>

[!code-csharp-interactive[?? operator](snippets/NullableValueTypes.cs#NullCoalescing)]

<span data-ttu-id="097f9-133">`null` 대신 기본 값 형식의 [기본값](default-values.md)을 사용하려면 <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-133">If you want to use the [default](default-values.md) value of the underlying value type in place of `null`, use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="097f9-134">다음 예제와 같이 null 허용 값 형식을 null을 허용하지 않는 형식으로 명시적으로 캐스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-134">You can also explicitly cast a nullable value type to a non-nullable type, as the following example shows:</span></span>

[!code-csharp[explicit cast](snippets/NullableValueTypes.cs#Cast)]

<span data-ttu-id="097f9-135">런타임 시 nullable 값 형식의 값이 `null`인 경우 명시적 캐스트는 <xref:System.InvalidOperationException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-135">At run time, if the value of a nullable value type is `null`, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="097f9-136">null을 허용하지 않는 값 형식 `T`는 해당 null 허용 값 형식 `T?`로 암시적으로 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-136">A non-nullable value type `T` is implicitly convertible to the corresponding nullable value type `T?`.</span></span>

## <a name="lifted-operators"></a><span data-ttu-id="097f9-137">리프트 연산자</span><span class="sxs-lookup"><span data-stu-id="097f9-137">Lifted operators</span></span>

<span data-ttu-id="097f9-138">미리 정의된 단항 및 이항 [연산자](../operators/index.md) 또는 값 형식 `T`에서 지원하는 오버로드된 연산자는 해당 null 허용 값 형식 `T?`에서도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-138">The predefined unary and binary [operators](../operators/index.md) or any overloaded operators that are supported by a value type `T` are also supported by the corresponding nullable value type `T?`.</span></span> <span data-ttu-id="097f9-139">*리프트 연산자*라고도 하는 이러한 연산자는 하나 또는 두 개의 피연산자가 `null`인 경우 `null` 값을 생성하고, 그렇지 않으면 연산자는 포함된 피연산자 값을 사용하여 결과를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-139">These operators, also known as *lifted operators*, produce `null` if one or both operands are `null`; otherwise, the operator uses the contained values of its operands to calculate the result.</span></span> <span data-ttu-id="097f9-140">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="097f9-140">For example:</span></span>

[!code-csharp[lifted operators](snippets/NullableValueTypes.cs#LiftedOperator)]

> [!NOTE]
> <span data-ttu-id="097f9-141">`|` 형식의 경우 미리 정의된 `bool?` 및 `&` 연산자는 이 섹션에서 설명된 규칙을 따르지 않습니다. 연산자 평가의 결과는 피연산자 중 하나가 `null`인 경우에도 Null이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-141">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="097f9-142">자세한 내용은 [부울 논리 연산자](../operators/boolean-logical-operators.md) 문서의 [Nullable 부울 논리 연산자](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="097f9-142">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

<span data-ttu-id="097f9-143">[비교 연산자](../operators/comparison-operators.md) `<`, `>`, `<=` 및 `>=`의 경우 피연산자 중 하나 또는 둘 모두가 `null`이면 결과는 `false`입니다. 그렇지 않으면 포함된 피연산자 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-143">For the [comparison operators](../operators/comparison-operators.md) `<`, `>`, `<=`, and `>=`, if one or both operands are `null`, the result is `false`; otherwise, the contained values of operands are compared.</span></span> <span data-ttu-id="097f9-144">특정 비교(예: `<=`)에서는 `false`를 반환하고 그 반대의 비교(`>`)에서는 `true`를 반환한다고 가정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="097f9-144">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="097f9-145">다음 예제에서는 10이</span><span class="sxs-lookup"><span data-stu-id="097f9-145">The following example shows that 10 is</span></span>

- <span data-ttu-id="097f9-146">`null`보다 크지도, 같지도 않고</span><span class="sxs-lookup"><span data-stu-id="097f9-146">neither greater than or equal to `null`</span></span>
- <span data-ttu-id="097f9-147">`null`보다 작지도 않음을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-147">nor less than `null`</span></span>

[!code-csharp-interactive[relational and equality operators](snippets/NullableValueTypes.cs#ComparisonOperators)]

<span data-ttu-id="097f9-148">[같음 연산자](../operators/equality-operators.md#equality-operator-) `==`의 경우 두 피연산자 모두 `null`이면 결과는 `true`이고 피연산자 중 하나만 `null`이면 결과는 `false`입니다. 그렇지 않으면 포함된 피연산자 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-148">For the [equality operator](../operators/equality-operators.md#equality-operator-) `==`, if both operands are `null`, the result is `true`, if only one of the operands is `null`, the result is `false`; otherwise, the contained values of operands are compared.</span></span>

<span data-ttu-id="097f9-149">[같지 않음 연산자](../operators/equality-operators.md#inequality-operator-) `!=`의 경우 두 피연산자 모두 `null`이면 결과는 `false`이고 피연산자 중 하나만 `null`이면 결과는 `true`입니다. 그렇지 않으면 포함된 피연산자 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-149">For the [inequality operator](../operators/equality-operators.md#inequality-operator-) `!=`, if both operands are `null`, the result is `false`, if only one of the operands is `null`, the result is `true`; otherwise, the contained values of operands are compared.</span></span>

<span data-ttu-id="097f9-150">두 값 형식 사이에 [사용자 정의 변환](../operators/user-defined-conversion-operators.md)이 있는 경우 해당 null 허용 값 형식 사이에도 같은 변환을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-150">If there exists a [user-defined conversion](../operators/user-defined-conversion-operators.md) between two value types, the same conversion can also be used between the corresponding nullable value types.</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="097f9-151">boxing 및 unboxing</span><span class="sxs-lookup"><span data-stu-id="097f9-151">Boxing and unboxing</span></span>

<span data-ttu-id="097f9-152">Null 허용 값 형식 `T?`의 인스턴스는 다음과 같이 [box](../../programming-guide/types/boxing-and-unboxing.md)됩니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-152">An instance of a nullable value type `T?` is [boxed](../../programming-guide/types/boxing-and-unboxing.md) as follows:</span></span>

- <span data-ttu-id="097f9-153"><xref:System.Nullable%601.HasValue%2A>가 `false`를 반환하는 경우 Null 참조가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-153">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>
- <span data-ttu-id="097f9-154"><xref:System.Nullable%601.HasValue%2A>가 `true`를 반환하는 경우 <xref:System.Nullable%601>의 인스턴스가 아닌 기본 값 형식 `T`의 인스턴스가 box됩니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-154">If <xref:System.Nullable%601.HasValue%2A> returns `true`, the corresponding value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="097f9-155">다음 예제와 같이 값 형식 `T`의 boxed 값을 해당 null 허용 값 형식 `T?`로 unbox할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-155">You can unbox a boxed value of a value type `T` to the corresponding nullable value type `T?`, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](snippets/NullableValueTypes.cs#Boxing)]

## <a name="how-to-identify-a-nullable-value-type"></a><span data-ttu-id="097f9-156">Null 허용 값 형식 식별 방법</span><span class="sxs-lookup"><span data-stu-id="097f9-156">How to identify a nullable value type</span></span>

<span data-ttu-id="097f9-157">다음 예제는 <xref:System.Type?displayProperty=nameWithType> 인스턴스가 구성된 null 허용 값 형식(지정된 형식 매개 변수 `T`가 포함된 <xref:System.Nullable%601?displayProperty=nameWithType> 형식)을 나타내는지 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-157">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a constructed nullable value type, that is, the <xref:System.Nullable%601?displayProperty=nameWithType> type with a specified type parameter `T`:</span></span>

[!code-csharp-interactive[whether Type is nullable](snippets/NullableValueTypes.cs#IsTypeNullable)]

<span data-ttu-id="097f9-158">예제에서와 같이 [typeof](../operators/type-testing-and-cast.md#typeof-operator) 연산자를 사용하여 <xref:System.Type?displayProperty=nameWithType> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-158">As the example shows, you use the [typeof](../operators/type-testing-and-cast.md#typeof-operator) operator to create a <xref:System.Type?displayProperty=nameWithType> instance.</span></span>

<span data-ttu-id="097f9-159">인스턴스가 있는지 nullable 값 형식인지 여부를 확인하려는 경우 위의 코드로 테스트되도록 <xref:System.Type> 인스턴스를 가져오는 데 <xref:System.Object.GetType%2A?displayProperty=nameWithType> 메서드를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="097f9-159">If you want to determine whether an instance is of a nullable value type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="097f9-160">nullable 값 형식의 인스턴스에서 <xref:System.Object.GetType%2A?displayProperty=nameWithType> 메서드를 호출하는 경우 인스턴스는 <xref:System.Object>로 [boxing](#boxing-and-unboxing)됩니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-160">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable value type, the instance is [boxed](#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="097f9-161">Null 허용 값 형식의 Null이 아닌 인스턴스의 boxing은 기본 형식 값의 boxing과 동일하며, <xref:System.Object.GetType%2A>는 null 허용 값 형식의 기본 형식을 나타내는 <xref:System.Type> 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-161">As boxing of a non-null instance of a nullable value type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> instance that represents the underlying type of a nullable value type:</span></span>

[!code-csharp-interactive[GetType example](snippets/NullableValueTypes.cs#GetType)]

<span data-ttu-id="097f9-162">그리고 인스턴스가 null 허용 값 형식인지 여부를 확인하는 데 [is](../operators/type-testing-and-cast.md#is-operator) 연산자를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="097f9-162">Also, don't use the [is](../operators/type-testing-and-cast.md#is-operator) operator to determine whether an instance is of a nullable value type.</span></span> <span data-ttu-id="097f9-163">다음 예제에서와 같이 null 허용 값 형식 인스턴스와 `is` 연산자를 사용하는 해당 형식 인스턴스를 구분할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-163">As the following example shows, you cannot distinguish types of a nullable value type instance and its underlying type instance with the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](snippets/NullableValueTypes.cs#IsOperator)]

<span data-ttu-id="097f9-164">다음 예제에서 제공된 코드를 사용하여 인스턴스가 nullable 값 형식인지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-164">You can use the code presented in the following example to determine whether an instance is of a nullable value type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](snippets/NullableValueTypes.cs#IsInstanceNullable)]

> [!NOTE]
> <span data-ttu-id="097f9-165">이 섹션에서 설명하는 방법은 [nullable 참조 형식](nullable-reference-types.md)의 경우에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="097f9-165">The methods described in this section are not applicable in the case of [nullable reference types](nullable-reference-types.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="097f9-166">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="097f9-166">C# language specification</span></span>

<span data-ttu-id="097f9-167">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="097f9-167">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="097f9-168">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="097f9-168">Nullable types</span></span>](~/_csharplang/spec/types.md#nullable-types)
- [<span data-ttu-id="097f9-169">리프트 연산자</span><span class="sxs-lookup"><span data-stu-id="097f9-169">Lifted operators</span></span>](~/_csharplang/spec/expressions.md#lifted-operators)
- [<span data-ttu-id="097f9-170">암시적 null 허용 전환</span><span class="sxs-lookup"><span data-stu-id="097f9-170">Implicit nullable conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-nullable-conversions)
- [<span data-ttu-id="097f9-171">명시적 null 허용 전환</span><span class="sxs-lookup"><span data-stu-id="097f9-171">Explicit nullable conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-nullable-conversions)
- [<span data-ttu-id="097f9-172">리프트 변환 연산자</span><span class="sxs-lookup"><span data-stu-id="097f9-172">Lifted conversion operators</span></span>](~/_csharplang/spec/conversions.md#lifted-conversion-operators)

## <a name="see-also"></a><span data-ttu-id="097f9-173">참조</span><span class="sxs-lookup"><span data-stu-id="097f9-173">See also</span></span>

- [<span data-ttu-id="097f9-174">C# 참조</span><span class="sxs-lookup"><span data-stu-id="097f9-174">C# reference</span></span>](../index.md)
- [<span data-ttu-id="097f9-175">'리프트'란 정확히 어떤 의미입니까?</span><span class="sxs-lookup"><span data-stu-id="097f9-175">What exactly does 'lifted' mean?</span></span>](/archive/blogs/ericlippert/what-exactly-does-lifted-mean)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
- <xref:System.Nullable.GetUnderlyingType%2A?displayProperty=nameWithType>
- [<span data-ttu-id="097f9-176">nullable 참조 형식</span><span class="sxs-lookup"><span data-stu-id="097f9-176">Nullable reference types</span></span>](nullable-reference-types.md)
