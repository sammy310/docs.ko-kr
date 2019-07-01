---
title: float 키워드 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
ms.openlocfilehash: db0139f2000c1bc2c5a13a3a542164201e73f0fb
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424216"
---
# <a name="float-c-reference"></a><span data-ttu-id="aec9c-102">float(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="aec9c-102">float (C# Reference)</span></span>

<span data-ttu-id="aec9c-103">`float` 키워드는 32비트 부동 소수점 값을 저장하는 단순 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-103">The `float` keyword signifies a simple type that stores 32-bit floating-point values.</span></span> <span data-ttu-id="aec9c-104">다음 표에서는 `float` 형식의 전체 자릿수와 근사 범위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-104">The following table shows the precision and approximate range for the `float` type.</span></span>

|<span data-ttu-id="aec9c-105">형식</span><span class="sxs-lookup"><span data-stu-id="aec9c-105">Type</span></span>|<span data-ttu-id="aec9c-106">근사 범위</span><span class="sxs-lookup"><span data-stu-id="aec9c-106">Approximate range</span></span>|<span data-ttu-id="aec9c-107">전체 자릿수</span><span class="sxs-lookup"><span data-stu-id="aec9c-107">Precision</span></span>|<span data-ttu-id="aec9c-108">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="aec9c-108">.NET type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|<span data-ttu-id="aec9c-109">±1.5 x 10<sup>−45</sup> ~ ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="aec9c-109">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="aec9c-110">~6-9개 자릿수</span><span class="sxs-lookup"><span data-stu-id="aec9c-110">~6-9 digits</span></span>|<xref:System.Single?displayProperty=nameWithType>|  

## <a name="literals"></a><span data-ttu-id="aec9c-111">리터럴</span><span class="sxs-lookup"><span data-stu-id="aec9c-111">Literals</span></span>

<span data-ttu-id="aec9c-112">기본적으로 대입 연산자 오른쪽의 실수 리터럴은 [double](double.md)로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-112">By default, a real numeric literal on the right side of the assignment operator is treated as [double](double.md).</span></span> <span data-ttu-id="aec9c-113">따라서 부동 변수를 초기화하려면 다음 예제와 같이 접미사 `f` 또는 `F`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-113">Therefore, to initialize a float variable, use the suffix `f` or `F`, as in the following example:</span></span>

```csharp
float x = 3.5F;
```

<span data-ttu-id="aec9c-114">이전 선언에서 접미사를 사용하지 않은 경우 [double](double.md) 값을 `float` 변수에 저장하려고 하기 때문에 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-114">If you do not use the suffix in the previous declaration, you will get a compilation error because you are trying to store a [double](double.md) value into a `float` variable.</span></span>

## <a name="conversions"></a><span data-ttu-id="aec9c-115">변환</span><span class="sxs-lookup"><span data-stu-id="aec9c-115">Conversions</span></span>

<span data-ttu-id="aec9c-116">식에서 숫자 정수 형식과 부동 소수점 형식을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-116">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="aec9c-117">이 경우 정수 형식이 부동 소수점 형식으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-117">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="aec9c-118">식의 계산은 다음 규칙에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-118">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="aec9c-119">부동 소수점 형식 중 하나가 [double](double.md)이면 식은 같음에 대한 관계형 비교 또는 비교에서 [double](double.md) 또는 [bool](bool.md)로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-119">If one of the floating-point types is [double](double.md), the expression evaluates to [double](double.md), or to [bool](bool.md) in relational comparisons or comparisons for equality.</span></span>

- <span data-ttu-id="aec9c-120">식에 [double](double.md) 형식이 없는 경우 식은 같음에 대한 관계형 비교 또는 비교에서 `float` 또는 [bool](bool.md)로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-120">If there is no [double](double.md) type in the expression, the expression evaluates to `float`, or to [bool](bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="aec9c-121">부동 소수점 식에는 다음과 같은 값 집합이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-121">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="aec9c-122">양수 및 음수 0</span><span class="sxs-lookup"><span data-stu-id="aec9c-122">Positive and negative zero</span></span>

- <span data-ttu-id="aec9c-123">양수 및 음수 무한대</span><span class="sxs-lookup"><span data-stu-id="aec9c-123">Positive and negative infinity</span></span>

- <span data-ttu-id="aec9c-124">NaN(Not-a-Number) 값</span><span class="sxs-lookup"><span data-stu-id="aec9c-124">Not-a-Number value (NaN)</span></span>

- <span data-ttu-id="aec9c-125">한정된 0이 아닌 값의 집합</span><span class="sxs-lookup"><span data-stu-id="aec9c-125">The finite set of nonzero values</span></span>

<span data-ttu-id="aec9c-126">이러한 값에 대한 자세한 내용은 [IEEE](https://www.ieee.org) 웹 사이트에서 제공되는 이진 부동 소수점 연산에 대한 IEEE 표준을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aec9c-126">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

## <a name="example"></a><span data-ttu-id="aec9c-127">예</span><span class="sxs-lookup"><span data-stu-id="aec9c-127">Example</span></span>

<span data-ttu-id="aec9c-128">다음 예제에서는 [int](../builtin-types/integral-numeric-types.md), [short](../builtin-types/integral-numeric-types.md) 및 `float`가 수학 식에 포함되어 `float` 결과를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-128">In the following example, an [int](../builtin-types/integral-numeric-types.md), a [short](../builtin-types/integral-numeric-types.md), and a `float` are included in a mathematical expression giving a `float` result.</span></span> <span data-ttu-id="aec9c-129">(`float`는 <xref:System.Single?displayProperty=nameWithType> 형식의 별칭입니다.) 식에 [double](double.md)이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aec9c-129">(Remember that `float` is an alias for the <xref:System.Single?displayProperty=nameWithType> type.) Notice that there is no [double](double.md) in the expression.</span></span>

[!code-csharp[csrefKeywordsTypes#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="aec9c-130">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="aec9c-130">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="aec9c-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aec9c-131">See also</span></span>

- <xref:System.Single>
- [<span data-ttu-id="aec9c-132">C# 참조</span><span class="sxs-lookup"><span data-stu-id="aec9c-132">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="aec9c-133">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="aec9c-133">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="aec9c-134">캐스팅 및 형식 변환</span><span class="sxs-lookup"><span data-stu-id="aec9c-134">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="aec9c-135">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="aec9c-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="aec9c-136">정수 형식</span><span class="sxs-lookup"><span data-stu-id="aec9c-136">Integral types</span></span>](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="aec9c-137">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="aec9c-137">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="aec9c-138">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="aec9c-138">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="aec9c-139">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="aec9c-139">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
