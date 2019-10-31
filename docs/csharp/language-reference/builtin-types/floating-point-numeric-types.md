---
title: 부동 소수점 숫자 형식 - C# 참조
description: 기본 제공 C# 부동 소수점 형식의 개요
ms.date: 10/22/2019
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
ms.openlocfilehash: 4d71f7eea3f574e483dc4250f5c87e1ffd551f2f
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771898"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="32e19-103">부동 소수점 숫자 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="32e19-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="32e19-104">**부동 소수점 형식**은 **단순 형식**의 하위 집합이며 [*리터럴*](#real-literals)을 사용하여 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#real-literals).</span></span> <span data-ttu-id="32e19-105">모든 부동 소수점 형식도 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-105">All floating-point types are also value types.</span></span> <span data-ttu-id="32e19-106">모든 부동 소수점 숫자 형식은 [산술](../operators/arithmetic-operators.md), [비교](../operators/comparison-operators.md) 및 [같음](../operators/equality-operators.md) 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="32e19-107">부동 소수점 형식의 특성</span><span class="sxs-lookup"><span data-stu-id="32e19-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="32e19-108">C#은 다음과 같은 미리 정의된 부동 소수점 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="32e19-109">C# 형식/키워드</span><span class="sxs-lookup"><span data-stu-id="32e19-109">C# type/keyword</span></span>|<span data-ttu-id="32e19-110">근사 범위</span><span class="sxs-lookup"><span data-stu-id="32e19-110">Approximate range</span></span>|<span data-ttu-id="32e19-111">전체 자릿수</span><span class="sxs-lookup"><span data-stu-id="32e19-111">Precision</span></span>|<span data-ttu-id="32e19-112">Size</span><span class="sxs-lookup"><span data-stu-id="32e19-112">Size</span></span>|<span data-ttu-id="32e19-113">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="32e19-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="32e19-114">±1.5 x 10<sup>−45</sup> ~ ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="32e19-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="32e19-115">~6-9개 자릿수</span><span class="sxs-lookup"><span data-stu-id="32e19-115">~6-9 digits</span></span>|<span data-ttu-id="32e19-116">4바이트</span><span class="sxs-lookup"><span data-stu-id="32e19-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="32e19-117">±5.0 × 10<sup>−324</sup> ~ ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="32e19-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="32e19-118">~15-17개 자릿수</span><span class="sxs-lookup"><span data-stu-id="32e19-118">~15-17 digits</span></span>|<span data-ttu-id="32e19-119">8바이트</span><span class="sxs-lookup"><span data-stu-id="32e19-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="32e19-120">±1.0 x 10<sup>-28</sup> ~ ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="32e19-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="32e19-121">28-29개의 자릿수</span><span class="sxs-lookup"><span data-stu-id="32e19-121">28-29 digits</span></span>|<span data-ttu-id="32e19-122">16바이트</span><span class="sxs-lookup"><span data-stu-id="32e19-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="32e19-123">이전 표에서 맨 왼쪽 열의 각 C# 형식 키워드는 해당하는 .NET 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="32e19-124">서로 교환하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-124">They are interchangeable.</span></span> <span data-ttu-id="32e19-125">예를 들어 다음 선언은 동일한 형식의 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="32e19-126">각 부동 소수점 형식의 기본값은 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="32e19-127">각 부동 소수점 형식에는 해당 형식의 최소 및 최대 유한값을 제공하는 `MinValue` 및 `MaxValue` 상수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="32e19-128">또한 `float` 및 `double` 형식은 숫자가 아닌 무한 값을 나타내는 상수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="32e19-129">예를 들어 `double` 형식은 <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> 및 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>와 같은 상수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="32e19-130">`decimal` 형식은 `float` 및 `double`보다 정밀도가 높고 범위가 작으므로 재무 및 통화 계산에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="32e19-131">식에서 [정수](integral-numeric-types.md) 형식과 부동 소수점 형식을 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="32e19-132">이 경우 정수 형식이 부동 소수점 형식으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="32e19-133">식의 계산은 다음 규칙에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="32e19-134">부동 소수점 형식 중 하나가 `double`인 경우 식은 관계형 및 같음에 대한 비교에서 `double` 또는 [bool](../keywords/bool.md)로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="32e19-135">식에 `double` 형식이 없는 경우 식은 같음에 대한 관계형 또는 비교에서 `float` 또는 [bool](../keywords/bool.md)로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational and equality comparisons.</span></span>

<span data-ttu-id="32e19-136">부동 소수점 식에는 다음과 같은 값 집합이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="32e19-137">양수 및 음수 0</span><span class="sxs-lookup"><span data-stu-id="32e19-137">Positive and negative zero</span></span>
- <span data-ttu-id="32e19-138">양수 및 음수 무한대</span><span class="sxs-lookup"><span data-stu-id="32e19-138">Positive and negative infinity</span></span>
- <span data-ttu-id="32e19-139">NaN(Not-a-Number) 값</span><span class="sxs-lookup"><span data-stu-id="32e19-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="32e19-140">한정된 0이 아닌 값의 집합</span><span class="sxs-lookup"><span data-stu-id="32e19-140">The finite set of nonzero values</span></span>

<span data-ttu-id="32e19-141">이러한 값에 대한 자세한 내용은 [IEEE](https://www.ieee.org) 웹 사이트에서 제공되는 이진 부동 소수점 연산에 대한 IEEE 표준을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32e19-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="32e19-142">[표준 숫자 서식 문자열](../../../standard/base-types/standard-numeric-format-strings.md) 또는 [사용자 지정 숫자 서식 문자열](../../../standard/base-types/custom-numeric-format-strings.md)을 사용하여 부동 소수점 값의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="32e19-143">real 리터럴</span><span class="sxs-lookup"><span data-stu-id="32e19-143">Real literals</span></span>

<span data-ttu-id="32e19-144">real 리터럴의 형식은 접미사로 다음과 같이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-144">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="32e19-145">접미사가 없거나 `d` 또는 `D` 접미사가 있는 리터럴은 `double` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-145">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="32e19-146">`f` 또는 `F` 접미사가 있는 리터럴은 `float` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-146">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="32e19-147">`m` 또는 `M` 접미사가 있는 리터럴은 `decimal` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-147">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="32e19-148">다음 코드에서는 각 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-148">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="32e19-149">앞의 예제에서는 C# 7.0부터 지원되는 *숫자 구분 기호*인 `_`를 사용하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-149">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="32e19-150">모든 종류의 숫자 리터럴에서 숫자 구분 기호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-150">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="32e19-151">또한 다음 예제와 같이 과학적 표기법을 사용하여 real 리터럴의 지수 부분을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-151">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="32e19-152">변환</span><span class="sxs-lookup"><span data-stu-id="32e19-152">Conversions</span></span>

<span data-ttu-id="32e19-153">부동 소수점 숫자 형식 간의 암시적 변환은 `float`에서 `double`로의 암시적 변환 하나뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-153">There is only one implicit conversion between floating-point numeric types: from `float` to `double`.</span></span> <span data-ttu-id="32e19-154">그러나 [명시적 캐스트](../operators/type-testing-and-cast.md#cast-operator-)를 사용하여 부동 소수점 형식을 다른 부동 소수점 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e19-154">However, you can convert any floating-point type to any other floating-point type with the [explicit cast](../operators/type-testing-and-cast.md#cast-operator-).</span></span> <span data-ttu-id="32e19-155">자세한 내용은 [기본 제공 숫자 변환](numeric-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32e19-155">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="32e19-156">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="32e19-156">C# language specification</span></span>

<span data-ttu-id="32e19-157">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32e19-157">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="32e19-158">부동 소수점 형식</span><span class="sxs-lookup"><span data-stu-id="32e19-158">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="32e19-159">10진 형식</span><span class="sxs-lookup"><span data-stu-id="32e19-159">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="32e19-160">real 리터럴</span><span class="sxs-lookup"><span data-stu-id="32e19-160">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="32e19-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32e19-161">See also</span></span>

- [<span data-ttu-id="32e19-162">C# 참조</span><span class="sxs-lookup"><span data-stu-id="32e19-162">C# reference</span></span>](../index.md)
- [<span data-ttu-id="32e19-163">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="32e19-163">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="32e19-164">정수 형식</span><span class="sxs-lookup"><span data-stu-id="32e19-164">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="32e19-165">숫자 결과 형식 지정 표</span><span class="sxs-lookup"><span data-stu-id="32e19-165">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="32e19-166">표준 숫자 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="32e19-166">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="32e19-167">.NET의 숫자</span><span class="sxs-lookup"><span data-stu-id="32e19-167">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
