---
title: 정수 숫자 형식 - C# 참조
description: 각 정수 숫자 형식에 대한 범위, 스토리지 크기 및 용도에 대해 알아봅니다.
ms.date: 03/17/2021
f1_keywords:
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- short_CSharpKeyword
- ushort_CSharpKeyword
- int_CSharpKeyword
- uint_CSharpKeyword
- long_CSharpKeyword
- ulong_CSharpKeyword
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
ms.openlocfilehash: 02b1451dc3aa22dfe27181b0e9160d198349107c
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760173"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="34ffd-103">정수 숫자 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="34ffd-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="34ffd-104">*정수 숫자 형식* 은 정수를 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-104">The *integral numeric types* represent integer numbers.</span></span> <span data-ttu-id="34ffd-105">모든 정수 숫자 형식은 [값 형식](value-types.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-105">All integral numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="34ffd-106">이것은 [기본 형식](value-types.md#built-in-value-types)이기도 하며, [리터럴](#integer-literals)로 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#integer-literals).</span></span> <span data-ttu-id="34ffd-107">모든 정수 숫자 형식은 [산술](../operators/arithmetic-operators.md), [비트 논리](../operators/bitwise-and-shift-operators.md), [비교](../operators/comparison-operators.md) 및 [같음](../operators/equality-operators.md) 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-107">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="34ffd-108">정수 형식의 특성</span><span class="sxs-lookup"><span data-stu-id="34ffd-108">Characteristics of the integral types</span></span>

<span data-ttu-id="34ffd-109">C#은 다음과 같은 미리 정의된 정수 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-109">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="34ffd-110">C# 형식/키워드</span><span class="sxs-lookup"><span data-stu-id="34ffd-110">C# type/keyword</span></span>|<span data-ttu-id="34ffd-111">범위</span><span class="sxs-lookup"><span data-stu-id="34ffd-111">Range</span></span>|<span data-ttu-id="34ffd-112">크기</span><span class="sxs-lookup"><span data-stu-id="34ffd-112">Size</span></span>|<span data-ttu-id="34ffd-113">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="34ffd-113">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="34ffd-114">-128 ~ 127</span><span class="sxs-lookup"><span data-stu-id="34ffd-114">-128 to 127</span></span>|<span data-ttu-id="34ffd-115">부호 있는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="34ffd-115">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="34ffd-116">0 ~ 255</span><span class="sxs-lookup"><span data-stu-id="34ffd-116">0 to 255</span></span>|<span data-ttu-id="34ffd-117">부호 없는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="34ffd-117">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="34ffd-118">–32,768 ~ 32,767</span><span class="sxs-lookup"><span data-stu-id="34ffd-118">-32,768 to 32,767</span></span>|<span data-ttu-id="34ffd-119">부호 있는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="34ffd-119">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="34ffd-120">0 ~ 65,535</span><span class="sxs-lookup"><span data-stu-id="34ffd-120">0 to 65,535</span></span>|<span data-ttu-id="34ffd-121">부호 없는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="34ffd-121">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="34ffd-122">–2,147,483,648 ~ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="34ffd-122">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="34ffd-123">부호 있는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="34ffd-123">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="34ffd-124">0 ~ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="34ffd-124">0 to 4,294,967,295</span></span>|<span data-ttu-id="34ffd-125">부호 없는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="34ffd-125">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="34ffd-126">–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="34ffd-126">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="34ffd-127">부호 있는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="34ffd-127">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="34ffd-128">0 ~ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="34ffd-128">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="34ffd-129">부호 없는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="34ffd-129">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|
|`nint`|<span data-ttu-id="34ffd-130">플랫폼에 따라 다름</span><span class="sxs-lookup"><span data-stu-id="34ffd-130">Depends on platform</span></span>|<span data-ttu-id="34ffd-131">부호 있는 32비트 또는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="34ffd-131">Signed 32-bit or 64-bit integer</span></span>|<xref:System.IntPtr?displayProperty=nameWithType>|
|`nuint`|<span data-ttu-id="34ffd-132">플랫폼에 따라 다름</span><span class="sxs-lookup"><span data-stu-id="34ffd-132">Depends on platform</span></span>|<span data-ttu-id="34ffd-133">부호 없는 32비트 또는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="34ffd-133">Unsigned 32-bit or 64-bit integer</span></span>|<xref:System.UIntPtr?displayProperty=nameWithType>|

<span data-ttu-id="34ffd-134">마지막 두 개를 제외한 모든 테이블 행에서 맨 왼쪽 열의 각 C# 형식 키워드는 해당하는 .NET 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-134">In all of the table rows except the last two, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="34ffd-135">키워드와 .NET 형식 이름은 서로 바꿔 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-135">The keyword and .NET type name are interchangeable.</span></span> <span data-ttu-id="34ffd-136">예를 들어 다음 선언은 동일한 형식의 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-136">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="34ffd-137">표의 마지막 두 행에 있는 `nint` 및 `nuint` 형식은 기본 크기 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-137">The `nint` and `nuint` types in the last two rows of the table are native-sized integers.</span></span> <span data-ttu-id="34ffd-138">이들은 지정된 .NET 형식에 의해 내부적으로 표시되지만, 각 경우에 키워드와 .NET 형식을 서로 바꿔 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-138">They are represented internally by the indicated .NET types, but in each case the keyword and the .NET type are not interchangeable.</span></span> <span data-ttu-id="34ffd-139">컴파일러는 `nint` 및 `nuint`에 대한 작업 및 변환을 포인터 형식 `System.IntPtr` 및 `System.UIntPtr`에 대해 제공하지 않는 정수 형식으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-139">The compiler provides operations and conversions for `nint` and `nuint` as integer types that it doesn't provide for the pointer types `System.IntPtr` and `System.UIntPtr`.</span></span> <span data-ttu-id="34ffd-140">자세한 내용은 [`nint` 및 `nuint`형식](nint-nuint.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34ffd-140">For more information, see [`nint` and `nuint` types](nint-nuint.md).</span></span>

<span data-ttu-id="34ffd-141">기본 크기 정수 형식에 대한 자세한 내용은 [`nint` 및 `nuint`](nint-nuint.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34ffd-141">For information about the native-sized integer types, see [`nint` and `nuint`](nint-nuint.md).</span></span>

<span data-ttu-id="34ffd-142">각 정수 형식의 기본값은 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-142">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="34ffd-143">기본 크기 형식을 제외한 각 정수 형식에는 해당 형식의 최소값과 최대값을 제공하는 `MinValue` 및 `MaxValue` 상수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-143">Each of the integral types except the native-sized types has `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="34ffd-144"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 구조체를 사용하여 상한 또는 하한이 없는 부호 있는 정수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-144">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="34ffd-145">정수 리터럴</span><span class="sxs-lookup"><span data-stu-id="34ffd-145">Integer literals</span></span>

<span data-ttu-id="34ffd-146">정수 리터럴은 다음 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-146">Integer literals can be</span></span>

- <span data-ttu-id="34ffd-147">*10진*: 접두사가 없음</span><span class="sxs-lookup"><span data-stu-id="34ffd-147">*decimal*: without any prefix</span></span>
- <span data-ttu-id="34ffd-148">*16진수*: `0x` 또는 `0X` 접두사 사용</span><span class="sxs-lookup"><span data-stu-id="34ffd-148">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="34ffd-149">*이진*: `0b` 또는 `0B` 접두사 사용(C# 7.0 및 이후 버전에서 가능)</span><span class="sxs-lookup"><span data-stu-id="34ffd-149">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="34ffd-150">다음 코드에서는 각 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-150">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="34ffd-151">앞의 예제에서는 C# 7.0부터 지원되는 *숫자 구분 기호* 인 `_`를 사용하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-151">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="34ffd-152">모든 종류의 숫자 리터럴에서 숫자 구분 기호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-152">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="34ffd-153">정수 리터럴의 형식은 접미사로 다음과 같이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-153">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="34ffd-154">리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 `int`, `uint`, `long`, `ulong` 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-154">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="34ffd-155">리터럴에 접미사가 `U` 또는 `u`인 경우 해당 형식은 값이 표현될 수 있는 `uint`, `ulong` 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-155">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="34ffd-156">리터럴에 접미사가 `L` 또는 `l`인 경우 해당 형식은 값이 표현될 수 있는 `long`, `ulong` 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-156">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="34ffd-157">소문자 `l`를 접미사로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-157">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="34ffd-158">그러나 이렇게 하면 문자 `l` 및 숫자 `1`을 혼동하기 쉬우므로 컴파일러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-158">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="34ffd-159">쉽게 구별할 수 있도록 `L`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-159">Use `L` for clarity.</span></span>

- <span data-ttu-id="34ffd-160">리터럴의 접미사가 `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` 또는 `lu`이면 해당 형식은 `ulong`입니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-160">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="34ffd-161">정수 리터럴로 표시되는 값이 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>를 초과하면 컴파일 오류 [CS1021](../../misc/cs1021.md)이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-161">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="34ffd-162">결정된 정수 리터럴 형식이 `int`이고 리터럴이 나타내는 값이 대상 형식의 범위 내에 있는 경우, 해당 값이 암시적으로 `sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`, `nint` 또는 `nuint`으로 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-162">If the determined type of an integer literal is `int` and the value represented by the literal is within the range of the destination type, the value can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`, `nint` or `nuint`:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="34ffd-163">앞의 예제에서 볼 수 있듯이 리터럴 값이 대상 형식의 범위 내에 있지 않으면 컴파일러 오류 [CS0031](../../misc/cs0031.md)이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-163">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="34ffd-164">캐스트를 사용하여 정수 리터럴로 표시되는 값을 결정된 리터럴 형식 이외의 형식으로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-164">You can also use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="34ffd-165">변환</span><span class="sxs-lookup"><span data-stu-id="34ffd-165">Conversions</span></span>

<span data-ttu-id="34ffd-166">모든 정수 숫자 형식을 다른 정수 숫자 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-166">You can convert any integral numeric type to any other integral numeric type.</span></span> <span data-ttu-id="34ffd-167">대상 형식이 소스 형식의 모든 값을 저장할 수 있는 경우 변환은 암시적입니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-167">If the destination type can store all values of the source type, the conversion is implicit.</span></span> <span data-ttu-id="34ffd-168">저장할 수 없는 경우에는 [캐스트 식](../operators/type-testing-and-cast.md#cast-expression)를 사용하여 명시적 변환을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ffd-168">Otherwise, you need to use a [cast expression](../operators/type-testing-and-cast.md#cast-expression) to perform an explicit conversion.</span></span> <span data-ttu-id="34ffd-169">자세한 내용은 [기본 제공 숫자 변환](numeric-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34ffd-169">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="34ffd-170">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="34ffd-170">C# language specification</span></span>

<span data-ttu-id="34ffd-171">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34ffd-171">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="34ffd-172">정수 형식</span><span class="sxs-lookup"><span data-stu-id="34ffd-172">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="34ffd-173">정수 리터럴</span><span class="sxs-lookup"><span data-stu-id="34ffd-173">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="34ffd-174">참조</span><span class="sxs-lookup"><span data-stu-id="34ffd-174">See also</span></span>

- [<span data-ttu-id="34ffd-175">C# 참조</span><span class="sxs-lookup"><span data-stu-id="34ffd-175">C# reference</span></span>](../index.md)
- [<span data-ttu-id="34ffd-176">값 형식</span><span class="sxs-lookup"><span data-stu-id="34ffd-176">Value types</span></span>](value-types.md)
- [<span data-ttu-id="34ffd-177">부동 소수점 형식</span><span class="sxs-lookup"><span data-stu-id="34ffd-177">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="34ffd-178">표준 숫자 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="34ffd-178">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="34ffd-179">.NET의 숫자</span><span class="sxs-lookup"><span data-stu-id="34ffd-179">Numerics in .NET</span></span>](../../../standard/numerics.md)
