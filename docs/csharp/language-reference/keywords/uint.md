---
title: uint 키워드 - C# 참조
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.openlocfilehash: 9a60460f67f9b6cf0b57d40ebf2789536e870d75
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633153"
---
# <a name="uint-c-reference"></a><span data-ttu-id="44955-102">uint(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="44955-102">uint (C# Reference)</span></span>

<span data-ttu-id="44955-103">`uint` 키워드는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44955-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="44955-104">형식</span><span class="sxs-lookup"><span data-stu-id="44955-104">Type</span></span>|<span data-ttu-id="44955-105">범위</span><span class="sxs-lookup"><span data-stu-id="44955-105">Range</span></span>|<span data-ttu-id="44955-106">크기</span><span class="sxs-lookup"><span data-stu-id="44955-106">Size</span></span>|<span data-ttu-id="44955-107">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="44955-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`uint`|<span data-ttu-id="44955-108">0 ~ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="44955-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="44955-109">부호 없는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="44955-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|

<span data-ttu-id="44955-110">**참고** `uint` 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="44955-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="44955-111">가능한 경우 항상 `int`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44955-111">Use `int` whenever possible.</span></span>

## <a name="literals"></a><span data-ttu-id="44955-112">리터럴</span><span class="sxs-lookup"><span data-stu-id="44955-112">Literals</span></span>

<span data-ttu-id="44955-113">10진수 리터럴, 16진수 리터럴 또는 (C# 7.0부터) 이진 리터럴을 할당하여 `uint` 변수를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44955-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="44955-114">정수 리터럴이 `uint` 범위를 벗어나는 경우(즉 <xref:System.UInt32.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="44955-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="44955-115">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 3,000,000,000과 같은 정수가 `uint` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="44955-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]

> [!NOTE]
> <span data-ttu-id="44955-116">`0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44955-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="44955-117">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44955-117">Decimal literals have no prefix.</span></span>

<span data-ttu-id="44955-118">C# 7.0부터 가독성 향상을 위해 몇 가지 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44955-118">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="44955-119">C# 7.0은 숫자 구분 기호로 밑줄 문자 `_`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44955-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="44955-120">C# 7.2는 접두사 뒤에 이진 또는 16진수 리터럴에 대한 자리 구분 기호로 `_`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44955-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="44955-121">10진수 리터럴에 선행 밑줄이 있는 것이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44955-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="44955-122">일부 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44955-122">Some examples are shown below.</span></span>

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]

<span data-ttu-id="44955-123">형식을 나타내는 접미사가 정수 리터럴에 포함되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44955-123">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="44955-124">`U` 또는 'u' 접미사는 리터럴의 숫자 값에 따라 `uint` 또는 `ulong`을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44955-124">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="44955-125">다음 예제에서는 `u` 접미사를 사용하여 두 형식의 부호 없는 정수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44955-125">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="44955-126">첫 번째 리터럴은 해당 값이 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>보다 작기 때문에 `uint`인 반면, 두 번째 리터럴은 해당 값이 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>보다 크기 때문에 `ulong`입니다.</span><span class="sxs-lookup"><span data-stu-id="44955-126">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>

[!code-csharp[usuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]

<span data-ttu-id="44955-127">정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 다음 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="44955-127">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. [<span data-ttu-id="44955-128">int</span><span class="sxs-lookup"><span data-stu-id="44955-128">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="44955-129">long</span><span class="sxs-lookup"><span data-stu-id="44955-129">long</span></span>](long.md)
4. [<span data-ttu-id="44955-130">ulong</span><span class="sxs-lookup"><span data-stu-id="44955-130">ulong</span></span>](ulong.md)

## <a name="conversions"></a><span data-ttu-id="44955-131">변환</span><span class="sxs-lookup"><span data-stu-id="44955-131">Conversions</span></span>

<span data-ttu-id="44955-132">`uint`에서 [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) 또는 [decimal](decimal.md)로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44955-132">There is a predefined implicit conversion from `uint` to [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span> <span data-ttu-id="44955-133">예:</span><span class="sxs-lookup"><span data-stu-id="44955-133">For example:</span></span>

```csharp
float myFloat = 4294967290;   // OK: implicit conversion to float
```

<span data-ttu-id="44955-134">[byte](byte.md), [ushort](ushort.md) 또는 [char](char.md)에서 `uint`로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44955-134">There is a predefined implicit conversion from [byte](byte.md), [ushort](ushort.md), or [char](char.md) to `uint`.</span></span> <span data-ttu-id="44955-135">그렇지 않으면 캐스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44955-135">Otherwise you must use a cast.</span></span> <span data-ttu-id="44955-136">예를 들어 다음 대입문은 캐스트 없이 컴파일 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="44955-136">For example, the following assignment statement will produce a compilation error without a cast:</span></span>

```csharp
long aLong = 22;
// Error -- no implicit conversion from long:
uint uInt1 = aLong;
// OK -- explicit conversion:
uint uInt2 = (uint)aLong;
```

<span data-ttu-id="44955-137">부동 소수점 형식에서 `uint`로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44955-137">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="44955-138">예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="44955-138">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
uint x = 3.0;
// OK -- explicit conversion:
uint y = (uint)3.0;
```

<span data-ttu-id="44955-139">부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](float.md) 및 [double](double.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44955-139">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="44955-140">암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](implicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44955-140">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="44955-141">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="44955-141">C# language specification</span></span>

<span data-ttu-id="44955-142">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [정수 형식](~/_csharplang/spec/types.md#integral-types)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44955-142">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="44955-143">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44955-143">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="44955-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44955-144">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="44955-145">C# 참조</span><span class="sxs-lookup"><span data-stu-id="44955-145">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="44955-146">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="44955-146">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="44955-147">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="44955-147">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="44955-148">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="44955-148">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="44955-149">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="44955-149">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="44955-150">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="44955-150">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="44955-151">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="44955-151">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
