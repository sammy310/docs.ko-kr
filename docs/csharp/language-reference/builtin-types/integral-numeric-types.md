---
title: 정수 숫자 형식 - C# 참조
description: 각 정수 숫자 형식에 대한 범위, 스토리지 크기 및 용도에 대해 알아봅니다.
ms.date: 10/22/2019
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
ms.openlocfilehash: 394a809a9a2f45f4aee652d0eca892f62f0f2e54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093203"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="fbcd9-103">정수 숫자 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="fbcd9-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="fbcd9-104">*정수 숫자 형식*은 정수를 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-104">The *integral numeric types* represent integer numbers.</span></span> <span data-ttu-id="fbcd9-105">모든 정수 숫자 형식은 [값 형식](value-types.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-105">All integral numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="fbcd9-106">이것은 [기본 형식](value-types.md#built-in-value-types)이기도 하며, [리터럴](#integer-literals)로 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#integer-literals).</span></span> <span data-ttu-id="fbcd9-107">모든 정수 숫자 형식은 [산술](../operators/arithmetic-operators.md), [비트 논리](../operators/bitwise-and-shift-operators.md), [비교](../operators/comparison-operators.md) 및 [같음](../operators/equality-operators.md) 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-107">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="fbcd9-108">정수 형식의 특성</span><span class="sxs-lookup"><span data-stu-id="fbcd9-108">Characteristics of the integral types</span></span>

<span data-ttu-id="fbcd9-109">C#은 다음과 같은 미리 정의된 정수 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-109">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="fbcd9-110">C# 형식/키워드</span><span class="sxs-lookup"><span data-stu-id="fbcd9-110">C# type/keyword</span></span>|<span data-ttu-id="fbcd9-111">범위</span><span class="sxs-lookup"><span data-stu-id="fbcd9-111">Range</span></span>|<span data-ttu-id="fbcd9-112">Size</span><span class="sxs-lookup"><span data-stu-id="fbcd9-112">Size</span></span>|<span data-ttu-id="fbcd9-113">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="fbcd9-113">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="fbcd9-114">-128 ~ 127</span><span class="sxs-lookup"><span data-stu-id="fbcd9-114">-128 to 127</span></span>|<span data-ttu-id="fbcd9-115">부호 있는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="fbcd9-115">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="fbcd9-116">0 ~ 255</span><span class="sxs-lookup"><span data-stu-id="fbcd9-116">0 to 255</span></span>|<span data-ttu-id="fbcd9-117">부호 없는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="fbcd9-117">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="fbcd9-118">–32,768 ~ 32,767</span><span class="sxs-lookup"><span data-stu-id="fbcd9-118">-32,768 to 32,767</span></span>|<span data-ttu-id="fbcd9-119">부호 있는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="fbcd9-119">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="fbcd9-120">0 ~ 65,535</span><span class="sxs-lookup"><span data-stu-id="fbcd9-120">0 to 65,535</span></span>|<span data-ttu-id="fbcd9-121">부호 없는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="fbcd9-121">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="fbcd9-122">–2,147,483,648 ~ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="fbcd9-122">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="fbcd9-123">부호 있는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="fbcd9-123">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="fbcd9-124">0 ~ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="fbcd9-124">0 to 4,294,967,295</span></span>|<span data-ttu-id="fbcd9-125">부호 없는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="fbcd9-125">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="fbcd9-126">–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="fbcd9-126">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="fbcd9-127">부호 있는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="fbcd9-127">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="fbcd9-128">0 ~ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="fbcd9-128">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="fbcd9-129">부호 없는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="fbcd9-129">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="fbcd9-130">이전 표에서 맨 왼쪽 열의 각 C# 형식 키워드는 해당하는 .NET 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-130">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="fbcd9-131">서로 교환하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-131">They are interchangeable.</span></span> <span data-ttu-id="fbcd9-132">예를 들어 다음 선언은 동일한 형식의 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-132">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="fbcd9-133">각 정수 형식의 기본값은 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-133">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="fbcd9-134">각 정수 형식에는 해당 형식의 최솟값과 최댓값을 제공하는 `MinValue` 및 `MaxValue` 상수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-134">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="fbcd9-135"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 구조체를 사용하여 상한 또는 하한이 없는 부호 있는 정수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-135">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="fbcd9-136">정수 리터럴</span><span class="sxs-lookup"><span data-stu-id="fbcd9-136">Integer literals</span></span>

<span data-ttu-id="fbcd9-137">정수 리터럴은 다음 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-137">Integer literals can be</span></span>

- <span data-ttu-id="fbcd9-138">*10진*: 접두사가 없음</span><span class="sxs-lookup"><span data-stu-id="fbcd9-138">*decimal*: without any prefix</span></span>
- <span data-ttu-id="fbcd9-139">*16진수*: `0x` 또는 `0X` 접두사 사용</span><span class="sxs-lookup"><span data-stu-id="fbcd9-139">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="fbcd9-140">*이진*: `0b` 또는 `0B` 접두사 사용(C# 7.0 및 이후 버전에서 가능)</span><span class="sxs-lookup"><span data-stu-id="fbcd9-140">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="fbcd9-141">다음 코드에서는 각 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-141">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="fbcd9-142">앞의 예제에서는 C# 7.0부터 지원되는 *숫자 구분 기호*인 `_`를 사용하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-142">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="fbcd9-143">모든 종류의 숫자 리터럴에서 숫자 구분 기호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-143">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="fbcd9-144">정수 리터럴의 형식은 접미사로 다음과 같이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-144">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="fbcd9-145">리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 `int`, `uint`, `long`, `ulong` 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-145">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="fbcd9-146">리터럴에 접미사가 `U` 또는 `u`인 경우 해당 형식은 값이 표현될 수 있는 `uint`, `ulong` 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-146">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="fbcd9-147">리터럴에 접미사가 `L` 또는 `l`인 경우 해당 형식은 값이 표현될 수 있는 `long`, `ulong` 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-147">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="fbcd9-148">소문자 `l`를 접미사로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-148">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="fbcd9-149">그러나 이렇게 하면 문자 `l` 및 숫자 `1`을 혼동하기 쉬우므로 컴파일러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-149">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="fbcd9-150">쉽게 구별할 수 있도록 `L`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-150">Use `L` for clarity.</span></span>

- <span data-ttu-id="fbcd9-151">리터럴의 접미사가 `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` 또는 `lu`이면 해당 형식은 `ulong`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-151">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="fbcd9-152">정수 리터럴로 표시되는 값이 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>를 초과하면 컴파일 오류 [CS1021](../../misc/cs1021.md)이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-152">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="fbcd9-153">결정된 정수 리터럴 형식이 `int`이고 리터럴이 나타내는 값이 대상 형식의 범위 내에 있는 경우, 해당 값이 암시적으로 `sbyte`, `byte`, `short`, `ushort`, `uint` 또는 `ulong`으로 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-153">If the determined type of an integer literal is `int` and the value represented by the literal is within the range of the destination type, the value can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="fbcd9-154">앞의 예제에서 볼 수 있듯이 리터럴 값이 대상 형식의 범위 내에 있지 않으면 컴파일러 오류 [CS0031](../../misc/cs0031.md)이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="fbcd9-155">캐스트를 사용하여 정수 리터럴로 표시되는 값을 결정된 리터럴 형식 이외의 형식으로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-155">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="fbcd9-156">변환</span><span class="sxs-lookup"><span data-stu-id="fbcd9-156">Conversions</span></span>

<span data-ttu-id="fbcd9-157">모든 정수 숫자 형식을 다른 정수 숫자 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-157">You can convert any integral numeric type to any other integral numeric type.</span></span> <span data-ttu-id="fbcd9-158">대상 형식이 소스 형식의 모든 값을 저장할 수 있는 경우 변환은 암시적입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-158">If the destination type can store all values of the source type, the conversion is implicit.</span></span> <span data-ttu-id="fbcd9-159">그렇지 않으면 [cast 연산자 `()`](../operators/type-testing-and-cast.md#cast-operator-)를 사용하여 명시적 변환을 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-159">Otherwise, you need to use the [cast operator `()`](../operators/type-testing-and-cast.md#cast-operator-) to invoke an explicit conversion.</span></span> <span data-ttu-id="fbcd9-160">자세한 내용은 [기본 제공 숫자 변환](numeric-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-160">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fbcd9-161">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="fbcd9-161">C# language specification</span></span>

<span data-ttu-id="fbcd9-162">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbcd9-162">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="fbcd9-163">정수 형식</span><span class="sxs-lookup"><span data-stu-id="fbcd9-163">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="fbcd9-164">정수 리터럴</span><span class="sxs-lookup"><span data-stu-id="fbcd9-164">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="fbcd9-165">참조</span><span class="sxs-lookup"><span data-stu-id="fbcd9-165">See also</span></span>

- [<span data-ttu-id="fbcd9-166">C# 참조</span><span class="sxs-lookup"><span data-stu-id="fbcd9-166">C# reference</span></span>](../index.md)
- [<span data-ttu-id="fbcd9-167">값 형식</span><span class="sxs-lookup"><span data-stu-id="fbcd9-167">Value types</span></span>](value-types.md)
- [<span data-ttu-id="fbcd9-168">부동 소수점 형식</span><span class="sxs-lookup"><span data-stu-id="fbcd9-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="fbcd9-169">표준 숫자 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="fbcd9-169">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="fbcd9-170">.NET의 숫자</span><span class="sxs-lookup"><span data-stu-id="fbcd9-170">Numerics in .NET</span></span>](../../../standard/numerics.md)
