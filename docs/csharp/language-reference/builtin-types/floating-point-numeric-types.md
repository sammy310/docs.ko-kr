---
title: 부동 소수점 숫자 형식 - C# 참조
description: 기본 제공 C# 부동 소수점 형식인 float, double 및 decimal에 대해 알아보기
ms.date: 02/10/2020
f1_keywords:
- float
- float_CSharpKeyword
- double
- double_CSharpKeyword
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- floating-point numbers [C#]
- ranges of floating-point types [C#]
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: a277215d438b5f6b0bbbef72e5e0121b6ce41990
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121476"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="6face-103">부동 소수점 숫자 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="6face-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="6face-104">*부동 소수점 숫자 형식*은 실수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6face-104">The *floating-point numeric types* represent real numbers.</span></span> <span data-ttu-id="6face-105">모든 부동 소수점 숫자 형식은 [값 형식](value-types.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="6face-105">All floating-point numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="6face-106">이것은 [기본 형식](value-types.md#built-in-value-types)이기도 하며, [리터럴](#real-literals)로 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6face-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#real-literals).</span></span> <span data-ttu-id="6face-107">모든 부동 소수점 숫자 형식은 [산술](../operators/arithmetic-operators.md), [비교](../operators/comparison-operators.md) 및 [같음](../operators/equality-operators.md) 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6face-107">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="6face-108">부동 소수점 형식의 특성</span><span class="sxs-lookup"><span data-stu-id="6face-108">Characteristics of the floating-point types</span></span>

<span data-ttu-id="6face-109">C#은 다음과 같은 미리 정의된 부동 소수점 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6face-109">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="6face-110">C# 형식/키워드</span><span class="sxs-lookup"><span data-stu-id="6face-110">C# type/keyword</span></span>|<span data-ttu-id="6face-111">근사 범위</span><span class="sxs-lookup"><span data-stu-id="6face-111">Approximate range</span></span>|<span data-ttu-id="6face-112">자릿수</span><span class="sxs-lookup"><span data-stu-id="6face-112">Precision</span></span>|<span data-ttu-id="6face-113">Size</span><span class="sxs-lookup"><span data-stu-id="6face-113">Size</span></span>|<span data-ttu-id="6face-114">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="6face-114">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="6face-115">±1.5 x 10<sup>−45</sup> ~ ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="6face-115">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="6face-116">~6-9개 자릿수</span><span class="sxs-lookup"><span data-stu-id="6face-116">~6-9 digits</span></span>|<span data-ttu-id="6face-117">4바이트</span><span class="sxs-lookup"><span data-stu-id="6face-117">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="6face-118">±5.0 × 10<sup>−324</sup> ~ ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="6face-118">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="6face-119">~15-17개 자릿수</span><span class="sxs-lookup"><span data-stu-id="6face-119">~15-17 digits</span></span>|<span data-ttu-id="6face-120">8바이트</span><span class="sxs-lookup"><span data-stu-id="6face-120">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="6face-121">±1.0 x 10<sup>-28</sup> ~ ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="6face-121">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="6face-122">28-29개의 자릿수</span><span class="sxs-lookup"><span data-stu-id="6face-122">28-29 digits</span></span>|<span data-ttu-id="6face-123">16바이트</span><span class="sxs-lookup"><span data-stu-id="6face-123">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="6face-124">이전 표에서 맨 왼쪽 열의 각 C# 형식 키워드는 해당하는 .NET 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="6face-124">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="6face-125">서로 교환하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6face-125">They are interchangeable.</span></span> <span data-ttu-id="6face-126">예를 들어 다음 선언은 동일한 형식의 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="6face-126">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="6face-127">각 부동 소수점 형식의 기본값은 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="6face-127">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="6face-128">각 부동 소수점 형식에는 해당 형식의 최소 및 최대 유한값을 제공하는 `MinValue` 및 `MaxValue` 상수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6face-128">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="6face-129">또한 `float` 및 `double` 형식은 숫자가 아닌 무한 값을 나타내는 상수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6face-129">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="6face-130">예를 들어 `double` 형식은 <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> 및 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>와 같은 상수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6face-130">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="6face-131">`decimal` 형식은 `float` 및 `double`보다 정밀도가 높고 범위가 작으므로 재무 및 통화 계산에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="6face-131">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="6face-132">식에서 [정수](integral-numeric-types.md) 형식과 `float` 및 `double` 형식을 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6face-132">You can mix [integral](integral-numeric-types.md) types and the `float` and `double` types in an expression.</span></span> <span data-ttu-id="6face-133">이 경우 정수 형식이 암시적으로 부동 소수점 형식 중 하나로 변환되며, 필요한 경우 `float` 형식이 암시적으로 `double`로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6face-133">In this case, integral types are implicitly converted to one of the floating-point types and, if necessary, the `float` type is implicitly converted to `double`.</span></span> <span data-ttu-id="6face-134">이 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6face-134">The expression is evaluated as follows:</span></span>

- <span data-ttu-id="6face-135">식에 `double` 형식이 있는 경우 식은 관계형 및 같음 비교에서 `double` 또는 [`bool`](bool.md)로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6face-135">If there is `double` type in the expression, the expression evaluates to `double`, or to [`bool`](bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="6face-136">식에 `double` 형식이 없는 경우 식은 관계형 및 같음 비교에서 `float` 또는 `bool`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6face-136">If there is no `double` type in the expression, the expression evaluates to `float`, or to `bool` in relational and equality comparisons.</span></span>

<span data-ttu-id="6face-137">식에서 정수 형식과 `decimal` 형식을 혼합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6face-137">You can also mix integral types and the `decimal` type in an expression.</span></span> <span data-ttu-id="6face-138">이 경우 정수 형식은 암시적으로 `decimal` 형식으로 변환되고 식은 관계형 및 같음 비교에서 `decimal` 또는 `bool`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6face-138">In this case, integral types are implicitly converted to the `decimal` type and the expression evaluates to `decimal`, or to `bool` in relational and equality comparisons.</span></span>

<span data-ttu-id="6face-139">식에서 `decimal` 형식을 `float` 및 `double` 형식과 혼합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6face-139">You cannot mix the `decimal` type with the `float` and `double` types in an expression.</span></span> <span data-ttu-id="6face-140">이 경우 산술, 비교 또는 같음 연산을 수행하려면 다음 예제와 같이 명시적으로 피연산자를 `decimal` 형식으로 변환하거나 반대로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6face-140">In this case, if you want to perform arithmetic, comparison, or equality operations, you must explicitly convert the operands either from or to the `decimal` type, as the following example shows:</span></span>

```csharp-interactive
double a = 1.0;
decimal b = 2.1m;
Console.WriteLine(a + (double)b);
Console.WriteLine((decimal)a + b);
```

<span data-ttu-id="6face-141">[표준 숫자 서식 문자열](../../../standard/base-types/standard-numeric-format-strings.md) 또는 [사용자 지정 숫자 서식 문자열](../../../standard/base-types/custom-numeric-format-strings.md)을 사용하여 부동 소수점 값의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6face-141">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="6face-142">real 리터럴</span><span class="sxs-lookup"><span data-stu-id="6face-142">Real literals</span></span>

<span data-ttu-id="6face-143">real 리터럴의 형식은 접미사로 다음과 같이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6face-143">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="6face-144">접미사가 없거나 `d` 또는 `D` 접미사가 있는 리터럴은 `double` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6face-144">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="6face-145">`f` 또는 `F` 접미사가 있는 리터럴은 `float` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6face-145">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="6face-146">`m` 또는 `M` 접미사가 있는 리터럴은 `decimal` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6face-146">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="6face-147">다음 코드에서는 각 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6face-147">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="6face-148">앞의 예제에서는 C# 7.0부터 지원되는 `_`숫자 구분 기호*인* 를 사용하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6face-148">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="6face-149">모든 종류의 숫자 리터럴에서 숫자 구분 기호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6face-149">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="6face-150">또한 다음 예제와 같이 과학적 표기법을 사용하여 real 리터럴의 지수 부분을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6face-150">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="6face-151">변환</span><span class="sxs-lookup"><span data-stu-id="6face-151">Conversions</span></span>

<span data-ttu-id="6face-152">부동 소수점 숫자 형식 간의 암시적 변환은 `float`에서 `double`로의 암시적 변환 하나뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="6face-152">There is only one implicit conversion between floating-point numeric types: from `float` to `double`.</span></span> <span data-ttu-id="6face-153">그러나 [명시적 캐스트](../operators/type-testing-and-cast.md#cast-expression)를 사용하여 부동 소수점 형식을 다른 부동 소수점 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6face-153">However, you can convert any floating-point type to any other floating-point type with the [explicit cast](../operators/type-testing-and-cast.md#cast-expression).</span></span> <span data-ttu-id="6face-154">자세한 내용은 [기본 제공 숫자 변환](numeric-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6face-154">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6face-155">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="6face-155">C# language specification</span></span>

<span data-ttu-id="6face-156">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6face-156">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="6face-157">부동 소수점 형식</span><span class="sxs-lookup"><span data-stu-id="6face-157">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="6face-158">10진 형식</span><span class="sxs-lookup"><span data-stu-id="6face-158">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="6face-159">real 리터럴</span><span class="sxs-lookup"><span data-stu-id="6face-159">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="6face-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6face-160">See also</span></span>

- [<span data-ttu-id="6face-161">C# 참조</span><span class="sxs-lookup"><span data-stu-id="6face-161">C# reference</span></span>](../index.md)
- [<span data-ttu-id="6face-162">값 형식</span><span class="sxs-lookup"><span data-stu-id="6face-162">Value types</span></span>](value-types.md)
- [<span data-ttu-id="6face-163">정수 형식</span><span class="sxs-lookup"><span data-stu-id="6face-163">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="6face-164">표준 숫자 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="6face-164">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="6face-165">.NET의 숫자</span><span class="sxs-lookup"><span data-stu-id="6face-165">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
