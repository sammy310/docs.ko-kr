---
title: 정수 숫자 형식 - C# 참조
description: 각 정수 숫자 형식에 대한 범위, 스토리지 크기 및 용도에 대해 알아봅니다.
ms.date: 10/18/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: 3d4f3164d67a000123417619f3be6be455d5ab87
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579190"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="ca54d-103">정수 숫자 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="ca54d-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="ca54d-104">**정수 숫자 형식**은 **단순 형식**의 하위 집합이며 [*리터럴*](#integer-literals)을 사용하여 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integer-literals).</span></span> <span data-ttu-id="ca54d-105">모든 정수 형식도 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-105">All integral types are also value types.</span></span> <span data-ttu-id="ca54d-106">모든 정수 숫자 형식은 [산술](../operators/arithmetic-operators.md), [비트 논리](../operators/bitwise-and-shift-operators.md), [비교](../operators/comparison-operators.md) 및 [같음](../operators/equality-operators.md) 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="ca54d-107">정수 형식의 특성</span><span class="sxs-lookup"><span data-stu-id="ca54d-107">Characteristics of the integral types</span></span>

<span data-ttu-id="ca54d-108">C#은 다음과 같은 미리 정의된 정수 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="ca54d-109">C# 형식/키워드</span><span class="sxs-lookup"><span data-stu-id="ca54d-109">C# type/keyword</span></span>|<span data-ttu-id="ca54d-110">범위</span><span class="sxs-lookup"><span data-stu-id="ca54d-110">Range</span></span>|<span data-ttu-id="ca54d-111">Size</span><span class="sxs-lookup"><span data-stu-id="ca54d-111">Size</span></span>|<span data-ttu-id="ca54d-112">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="ca54d-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="ca54d-113">-128 ~ 127</span><span class="sxs-lookup"><span data-stu-id="ca54d-113">-128 to 127</span></span>|<span data-ttu-id="ca54d-114">부호 있는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="ca54d-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="ca54d-115">0 ~ 255</span><span class="sxs-lookup"><span data-stu-id="ca54d-115">0 to 255</span></span>|<span data-ttu-id="ca54d-116">부호 없는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="ca54d-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="ca54d-117">–32,768 ~ 32,767</span><span class="sxs-lookup"><span data-stu-id="ca54d-117">-32,768 to 32,767</span></span>|<span data-ttu-id="ca54d-118">부호 있는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="ca54d-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="ca54d-119">0 ~ 65,535</span><span class="sxs-lookup"><span data-stu-id="ca54d-119">0 to 65,535</span></span>|<span data-ttu-id="ca54d-120">부호 없는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="ca54d-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="ca54d-121">–2,147,483,648 ~ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="ca54d-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="ca54d-122">부호 있는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="ca54d-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="ca54d-123">0 ~ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="ca54d-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="ca54d-124">부호 없는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="ca54d-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="ca54d-125">–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="ca54d-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="ca54d-126">부호 있는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="ca54d-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="ca54d-127">0 ~ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="ca54d-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="ca54d-128">부호 없는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="ca54d-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="ca54d-129">이전 표에서 맨 왼쪽 열의 각 C# 형식 키워드는 해당하는 .NET 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="ca54d-130">서로 교환하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-130">They are interchangeable.</span></span> <span data-ttu-id="ca54d-131">예를 들어 다음 선언은 동일한 형식의 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="ca54d-132">각 정수 형식의 기본값은 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="ca54d-133">각 정수 형식에는 해당 형식의 최솟값과 최댓값을 제공하는 `MinValue` 및 `MaxValue` 상수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="ca54d-134"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 구조체를 사용하여 상한 또는 하한이 없는 부호 있는 정수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="ca54d-135">정수 리터럴</span><span class="sxs-lookup"><span data-stu-id="ca54d-135">Integer literals</span></span>

<span data-ttu-id="ca54d-136">정수 리터럴은 다음 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-136">Integer literals can be</span></span>

- <span data-ttu-id="ca54d-137">*10진*: 접두사가 없음</span><span class="sxs-lookup"><span data-stu-id="ca54d-137">*decimal*: without any prefix</span></span>
- <span data-ttu-id="ca54d-138">*16진수*: `0x` 또는 `0X` 접두사 사용</span><span class="sxs-lookup"><span data-stu-id="ca54d-138">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="ca54d-139">*이진*: `0b` 또는 `0B` 접두사 사용(C# 7.0 및 이후 버전에서 가능)</span><span class="sxs-lookup"><span data-stu-id="ca54d-139">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="ca54d-140">다음 코드에서는 각 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-140">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="ca54d-141">앞의 예제에서는 C# 7.0부터 지원되는 *숫자 구분 기호*인 `_`를 사용하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-141">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="ca54d-142">모든 종류의 숫자 리터럴에서 숫자 구분 기호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-142">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="ca54d-143">정수 리터럴의 형식은 접미사로 다음과 같이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-143">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="ca54d-144">리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 `int`, `uint`, `long`, `ulong` 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-144">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="ca54d-145">리터럴에 접미사가 `U` 또는 `u`인 경우 해당 형식은 값이 표현될 수 있는 `uint`, `ulong` 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-145">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="ca54d-146">리터럴에 접미사가 `L` 또는 `l`인 경우 해당 형식은 값이 표현될 수 있는 `long`, `ulong` 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-146">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ca54d-147">소문자 `l`를 접미사로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-147">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="ca54d-148">그러나 이렇게 하면 문자 `l` 및 숫자 `1`을 혼동하기 쉬우므로 컴파일러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-148">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="ca54d-149">쉽게 구별할 수 있도록 `L`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-149">Use `L` for clarity.</span></span>

- <span data-ttu-id="ca54d-150">리터럴의 접미사가 `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` 또는 `lu`이면 해당 형식은 `ulong`입니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-150">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="ca54d-151">정수 리터럴로 표시되는 값이 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>를 초과하면 컴파일 오류 [CS1021](../../misc/cs1021.md)이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-151">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="ca54d-152">정수 리터럴로 표시되는 값은 결정된 리터럴 형식보다 범위가 작은 유형으로 암시적으로 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-152">The value represented by an integer literal can be implicitly converted to a type with a smaller range than the determined type of the literal.</span></span> <span data-ttu-id="ca54d-153">이는 값이 대상 형식의 범위 내에 있을 때 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-153">That's possible when the value is within the range of the destination type:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="ca54d-154">앞의 예제에서 볼 수 있듯이 리터럴 값이 대상 형식의 범위 내에 있지 않으면 컴파일러 오류 [CS0031](../../misc/cs0031.md)이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="ca54d-155">캐스트를 사용하여 정수 리터럴로 표시되는 값을 결정된 리터럴 형식 이외의 형식으로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-155">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="ca54d-156">변환</span><span class="sxs-lookup"><span data-stu-id="ca54d-156">Conversions</span></span>

<span data-ttu-id="ca54d-157">대상 유형에는 소스 유형의 모든 값을 저장할 수 있는 두 개의 정수 유형 간에 암시적 변환(*확대 변환*이라고 함)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-157">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="ca54d-158">예를 들어 `int` 값의 범위가 `long`의 적절한 하위 집합이기 때문에 `int`에서 `long`으로의 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-158">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="ca54d-159">더 작은 부호 없는 정수 형식에서 더 큰 부호 있는 정수 형식으로 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-159">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="ca54d-160">정수 형식에서 부동 소수점 형식으로 변환하는 암시적 변환도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-160">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="ca54d-161">부호 있는 정수 형식에서 부호 없는 정수 형식으로 변환하는 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-161">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="ca54d-162">암시적 변환이 소스 유형에서 대상 유형으로 정의되지 않은 경우 명시적 캐스트를 사용하여 하나의 정수 형식을 다른 정수 형식으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-162">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="ca54d-163">이를 *축소 변환*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-163">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="ca54d-164">변환이 데이터 손실을 초래할 수 있기 때문에 명시적인 사례가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54d-164">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ca54d-165">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="ca54d-165">C# language specification</span></span>

<span data-ttu-id="ca54d-166">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca54d-166">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="ca54d-167">정수 형식</span><span class="sxs-lookup"><span data-stu-id="ca54d-167">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="ca54d-168">정수 리터럴</span><span class="sxs-lookup"><span data-stu-id="ca54d-168">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="ca54d-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca54d-169">See also</span></span>

- [<span data-ttu-id="ca54d-170">C# 참조</span><span class="sxs-lookup"><span data-stu-id="ca54d-170">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ca54d-171">부동 소수점 형식</span><span class="sxs-lookup"><span data-stu-id="ca54d-171">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="ca54d-172">기본값 표</span><span class="sxs-lookup"><span data-stu-id="ca54d-172">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="ca54d-173">숫자 결과 형식 지정 표</span><span class="sxs-lookup"><span data-stu-id="ca54d-173">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="ca54d-174">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="ca54d-174">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="ca54d-175">.NET의 숫자</span><span class="sxs-lookup"><span data-stu-id="ca54d-175">Numerics in .NET</span></span>](../../../standard/numerics.md)
