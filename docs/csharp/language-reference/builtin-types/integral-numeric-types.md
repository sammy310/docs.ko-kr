---
title: 정수 숫자 형식 - C# 참조
description: 각 정수 숫자 형식에 대한 범위, 스토리지 크기 및 용도에 대해 알아봅니다.
ms.date: 06/25/2019
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
ms.openlocfilehash: dfb1298abaff0cfe8eae7536f94511a30012a4a9
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236084"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="d9383-103">정수 숫자 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d9383-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="d9383-104">**정수 숫자 형식**은 **단순 형식**의 하위 집합이며 [*리터럴*](#integral-literals)을 사용하여 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="d9383-105">모든 정수 형식도 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-105">All integral types are also value types.</span></span> <span data-ttu-id="d9383-106">모든 정수 숫자 형식은 [산술](../operators/arithmetic-operators.md), [비트 논리](../operators/bitwise-and-shift-operators.md), [비교 및 같음](../operators/equality-operators.md) 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="d9383-107">정수 형식의 특성</span><span class="sxs-lookup"><span data-stu-id="d9383-107">Characteristics of the integral types</span></span>

<span data-ttu-id="d9383-108">C#은 다음과 같은 미리 정의된 정수 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="d9383-109">C# 형식/키워드</span><span class="sxs-lookup"><span data-stu-id="d9383-109">C# type/keyword</span></span>|<span data-ttu-id="d9383-110">범위</span><span class="sxs-lookup"><span data-stu-id="d9383-110">Range</span></span>|<span data-ttu-id="d9383-111">크기</span><span class="sxs-lookup"><span data-stu-id="d9383-111">Size</span></span>|<span data-ttu-id="d9383-112">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="d9383-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="d9383-113">-128 ~ 127</span><span class="sxs-lookup"><span data-stu-id="d9383-113">-128 to 127</span></span>|<span data-ttu-id="d9383-114">부호 있는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="d9383-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="d9383-115">0 ~ 255</span><span class="sxs-lookup"><span data-stu-id="d9383-115">0 to 255</span></span>|<span data-ttu-id="d9383-116">부호 없는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="d9383-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="d9383-117">–32,768 ~ 32,767</span><span class="sxs-lookup"><span data-stu-id="d9383-117">-32,768 to 32,767</span></span>|<span data-ttu-id="d9383-118">부호 있는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="d9383-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="d9383-119">0 ~ 65,535</span><span class="sxs-lookup"><span data-stu-id="d9383-119">0 to 65,535</span></span>|<span data-ttu-id="d9383-120">부호 없는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="d9383-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="d9383-121">–2,147,483,648 ~ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="d9383-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="d9383-122">부호 있는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="d9383-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="d9383-123">0 ~ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="d9383-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="d9383-124">부호 없는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="d9383-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="d9383-125">–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="d9383-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="d9383-126">부호 있는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="d9383-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="d9383-127">0 ~ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="d9383-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="d9383-128">부호 없는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="d9383-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="d9383-129">이전 표에서 맨 왼쪽 열의 각 C# 형식 키워드는 해당하는 .NET 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="d9383-130">서로 교환하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-130">They are interchangeable.</span></span> <span data-ttu-id="d9383-131">예를 들어 다음 선언은 동일한 형식의 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="d9383-132">각 정수 형식의 기본값은 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="d9383-133">각 정수 형식에는 해당 형식의 최솟값과 최댓값을 제공하는 `MinValue` 및 `MaxValue` 상수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="d9383-134"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 구조체를 사용하여 상한 또는 하한이 없는 부호 있는 정수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="d9383-135">정수 리터럴</span><span class="sxs-lookup"><span data-stu-id="d9383-135">Integral literals</span></span>

<span data-ttu-id="d9383-136">정수 리터럴은 *10진수 리터럴*, *16진수 리터럴* 또는 *이진 리터럴*로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-136">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="d9383-137">아래에 각각의 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-137">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="d9383-138">10진수 리터럴에는 어떤 접두사도 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-138">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="d9383-139">`x` 또는 `X` 접두사는 *16진수 리터럴*을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-139">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="d9383-140">`b` 또는 `B` 접두사는 *이진 리터럴*을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-140">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="d9383-141">`binaryLiteral`의 선언은 `_`을(를) *숫자 구분 기호*로 사용하는 것을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-141">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="d9383-142">숫자 구분 기호는 모든 숫자 리터럴과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-142">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="d9383-143">이진 리터럴 및 숫자 구분 기호 `_`은(는) C# 7.0부터 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-143">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

### <a name="literal-suffixes"></a><span data-ttu-id="d9383-144">리터럴 접미사</span><span class="sxs-lookup"><span data-stu-id="d9383-144">Literal suffixes</span></span>

<span data-ttu-id="d9383-145">`l` 또는 `L` 접미사는 정수 리터럴이 `long` 유형이어야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-145">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="d9383-146">`ul` 또는 `UL` 접미사는 `ulong` 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-146">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="d9383-147">`L` 접미사가 9,223,372,036,854,775,807(`long`의 최댓값)보다 큰 리터럴에서 사용되는 경우 `ulong` 유형으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-147">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="d9383-148">정수 리터럴로 표시되는 값이 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>을 초과하면 컴파일 오류 [CS1021](../../misc/cs1021.md)이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-148">If the value represented by an integral literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="d9383-149">소문자 "l"을 접미사로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-149">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="d9383-150">그러나 이렇게 하면 문자 "l"과 숫자 "1"을 혼동하기 쉬우므로 컴파일러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-150">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="d9383-151">쉽게 구별할 수 있도록 "L"을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-151">Use "L" for clarity.</span></span>

### <a name="type-of-an-integral-literal"></a><span data-ttu-id="d9383-152">정수 리터럴 유형</span><span class="sxs-lookup"><span data-stu-id="d9383-152">Type of an integral literal</span></span>

<span data-ttu-id="d9383-153">정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 다음 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-153">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="d9383-154">할당 또는 캐스트를 사용하여 정수 리터럴을 기본값보다 작은 범위의 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-154">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="d9383-155">정수 리터럴을 리터럴에 할당, 캐스트 또는 접미사를 사용하여 기본값보다 큰 범위의 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-155">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="d9383-156">변환</span><span class="sxs-lookup"><span data-stu-id="d9383-156">Conversions</span></span>

<span data-ttu-id="d9383-157">대상 유형에는 소스 유형의 모든 값을 저장할 수 있는 두 개의 정수 유형 간에 암시적 변환(*확대 변환*이라고 함)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-157">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="d9383-158">예를 들어 `int` 값의 범위가 `long`의 적절한 하위 집합이기 때문에 `int`에서 `long`으로의 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-158">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="d9383-159">더 작은 부호 없는 정수 형식에서 더 큰 부호 있는 정수 형식으로 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-159">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="d9383-160">정수 형식에서 부동 소수점 형식으로 변환하는 암시적 변환도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-160">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="d9383-161">부호 있는 정수 형식에서 부호 없는 정수 형식으로 변환하는 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-161">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="d9383-162">암시적 변환이 소스 유형에서 대상 유형으로 정의되지 않은 경우 명시적 캐스트를 사용하여 하나의 정수 형식을 다른 정수 형식으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-162">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="d9383-163">이를 *축소 변환*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-163">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="d9383-164">변환이 데이터 손실을 초래할 수 있기 때문에 명시적인 사례가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9383-164">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9383-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9383-165">See also</span></span>

- [<span data-ttu-id="d9383-166">C# 언어 사양 - 정수 형식</span><span class="sxs-lookup"><span data-stu-id="d9383-166">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="d9383-167">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d9383-167">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d9383-168">부동 소수점 형식</span><span class="sxs-lookup"><span data-stu-id="d9383-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="d9383-169">기본값 표</span><span class="sxs-lookup"><span data-stu-id="d9383-169">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="d9383-170">숫자 결과 형식 지정 표</span><span class="sxs-lookup"><span data-stu-id="d9383-170">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="d9383-171">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="d9383-171">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="d9383-172">.NET의 숫자</span><span class="sxs-lookup"><span data-stu-id="d9383-172">Numerics in .NET</span></span>](../../../standard/numerics.md)
