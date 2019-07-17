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
ms.openlocfilehash: 0a1ed01d9e6cb86ea177e8b947627f9dc02eedae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744221"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="77899-103">정수 숫자 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="77899-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="77899-104">**정수 숫자 형식**은 **단순 형식**의 하위 집합이며 [*리터럴*](#integral-literals)을 사용하여 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="77899-105">모든 정수 형식도 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="77899-105">All integral types are also value types.</span></span>

<span data-ttu-id="77899-106">모든 정수 숫자 형식은 [산술](../operators/arithmetic-operators.md), [비트 논리](../operators/bitwise-and-shift-operators.md), [비교 및 같음](../operators/equality-operators.md) 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="77899-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="sizes-and-ranges"></a><span data-ttu-id="77899-107">크기 및 범위</span><span class="sxs-lookup"><span data-stu-id="77899-107">Sizes and ranges</span></span>

<span data-ttu-id="77899-108">다음 표는 정수 형식의 크기와 범위를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="77899-108">The following table shows the sizes and ranges of the integral types:</span></span>

|<span data-ttu-id="77899-109">형식</span><span class="sxs-lookup"><span data-stu-id="77899-109">Type</span></span>|<span data-ttu-id="77899-110">범위</span><span class="sxs-lookup"><span data-stu-id="77899-110">Range</span></span>|<span data-ttu-id="77899-111">크기</span><span class="sxs-lookup"><span data-stu-id="77899-111">Size</span></span>|  
|----------|-----------|----------|  
|`sbyte`|<span data-ttu-id="77899-112">-128 ~ 127</span><span class="sxs-lookup"><span data-stu-id="77899-112">-128 to 127</span></span>|<span data-ttu-id="77899-113">부호 있는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="77899-113">Signed 8-bit integer</span></span>|  
|`byte`|<span data-ttu-id="77899-114">0 ~ 255</span><span class="sxs-lookup"><span data-stu-id="77899-114">0 to 255</span></span>|<span data-ttu-id="77899-115">부호 없는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="77899-115">Unsigned 8-bit integer</span></span>|  
|`short`|<span data-ttu-id="77899-116">–32,768 ~ 32,767</span><span class="sxs-lookup"><span data-stu-id="77899-116">-32,768 to 32,767</span></span>|<span data-ttu-id="77899-117">부호 있는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="77899-117">Signed 16-bit integer</span></span>|  
|`ushort`|<span data-ttu-id="77899-118">0 ~ 65,535</span><span class="sxs-lookup"><span data-stu-id="77899-118">0 to 65,535</span></span>|<span data-ttu-id="77899-119">부호 없는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="77899-119">Unsigned 16-bit integer</span></span>|  
|`int`|<span data-ttu-id="77899-120">–2,147,483,648 ~ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="77899-120">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="77899-121">부호 있는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="77899-121">Signed 32-bit integer</span></span>|  
|`uint`|<span data-ttu-id="77899-122">0 ~ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="77899-122">0 to 4,294,967,295</span></span>|<span data-ttu-id="77899-123">부호 없는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="77899-123">Unsigned 32-bit integer</span></span>|  
|`long`|<span data-ttu-id="77899-124">–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="77899-124">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="77899-125">부호 있는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="77899-125">Signed 64-bit integer</span></span>|  
|`ulong`|<span data-ttu-id="77899-126">0 ~ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="77899-126">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="77899-127">부호 없는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="77899-127">Unsigned 64-bit integer</span></span>|  

<span data-ttu-id="77899-128">모든 정수 형식의 기본값은 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="77899-128">The default value for all integral types is `0`.</span></span> <span data-ttu-id="77899-129">각 정수 형식에는 해당 형식의 최솟값과 최댓값에 대해 `MinValue` 및 `MaxValue`라는 상수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-129">Each of the integral types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span>

<span data-ttu-id="77899-130"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 구조체를 사용하여 상한 또는 하한이 없는 부호 있는 정수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77899-130">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="77899-131">정수 리터럴</span><span class="sxs-lookup"><span data-stu-id="77899-131">Integral literals</span></span>

<span data-ttu-id="77899-132">정수 리터럴은 *10진수 리터럴*, *16진수 리터럴* 또는 *이진 리터럴*로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-132">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="77899-133">아래에 각각의 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-133">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="77899-134">10진수 리터럴에는 어떤 접두사도 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-134">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="77899-135">`x` 또는 `X` 접두사는 *16진수 리터럴*을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="77899-135">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="77899-136">`b` 또는 `B` 접두사는 *이진 리터럴*을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="77899-136">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="77899-137">`binaryLiteral`의 선언은 `_`을(를) *숫자 구분 기호*로 사용하는 것을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="77899-137">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="77899-138">숫자 구분 기호는 모든 숫자 리터럴과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-138">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="77899-139">이진 리터럴 및 숫자 구분 기호 `_`은(는) C# 7.0부터 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="77899-139">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

### <a name="literal-suffixes"></a><span data-ttu-id="77899-140">리터럴 접미사</span><span class="sxs-lookup"><span data-stu-id="77899-140">Literal suffixes</span></span> 

<span data-ttu-id="77899-141">`l` 또는 `L` 접미사는 정수 리터럴이 `long` 유형이어야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="77899-141">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="77899-142">`ul` 또는 `UL` 접미사는 `ulong` 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="77899-142">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="77899-143">`L` 접미사가 9,223,372,036,854,775,807(`long`의 최댓값)보다 큰 리터럴에서 사용되는 경우 `ulong` 유형으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="77899-143">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="77899-144">정수 리터럴로 표시되는 값이 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>을 초과하면 컴파일 오류 [CS1021](../../misc/cs1021.md)이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="77899-144">If the value represented by an integral literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="77899-145">소문자 "l"을 접미사로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-145">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="77899-146">그러나 이렇게 하면 문자 "l"과 숫자 "1"을 혼동하기 쉬우므로 컴파일러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="77899-146">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="77899-147">쉽게 구별할 수 있도록 "L"을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77899-147">Use "L" for clarity.</span></span>

### <a name="type-of-an-integral-literal"></a><span data-ttu-id="77899-148">정수 리터럴 유형</span><span class="sxs-lookup"><span data-stu-id="77899-148">Type of an integral literal</span></span>

<span data-ttu-id="77899-149">정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 다음 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="77899-149">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="77899-150">할당 또는 캐스트를 사용하여 정수 리터럴을 기본값보다 작은 범위의 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-150">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="77899-151">정수 리터럴을 리터럴에 할당, 캐스트 또는 접미사를 사용하여 기본값보다 큰 범위의 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-151">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="77899-152">변환</span><span class="sxs-lookup"><span data-stu-id="77899-152">Conversions</span></span>

<span data-ttu-id="77899-153">대상 유형에는 소스 유형의 모든 값을 저장할 수 있는 두 개의 정수 유형 간에 암시적 변환(*확대 변환*이라고 함)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-153">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="77899-154">예를 들어 `int` 값의 범위가 `long`의 적절한 하위 집합이기 때문에 `int`에서 `long`으로의 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-154">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="77899-155">더 작은 부호 없는 정수 형식에서 더 큰 부호 있는 정수 형식으로 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-155">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="77899-156">정수 형식에서 부동 소수점 형식으로 변환하는 암시적 변환도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-156">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="77899-157">부호 있는 정수 형식에서 부호 없는 정수 형식으로 변환하는 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77899-157">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="77899-158">암시적 변환이 소스 유형에서 대상 유형으로 정의되지 않은 경우 명시적 캐스트를 사용하여 하나의 정수 형식을 다른 정수 형식으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77899-158">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="77899-159">이를 *축소 변환*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="77899-159">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="77899-160">변환이 데이터 손실을 초래할 수 있기 때문에 명시적인 사례가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="77899-160">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="77899-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77899-161">See also</span></span>

- [<span data-ttu-id="77899-162">C# 언어 사양 - 정수 형식</span><span class="sxs-lookup"><span data-stu-id="77899-162">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="77899-163">C# 참조</span><span class="sxs-lookup"><span data-stu-id="77899-163">C# reference</span></span>](../index.md)
- [<span data-ttu-id="77899-164">부동 소수점 형식</span><span class="sxs-lookup"><span data-stu-id="77899-164">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="77899-165">기본값 표</span><span class="sxs-lookup"><span data-stu-id="77899-165">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="77899-166">숫자 결과 형식 지정 표</span><span class="sxs-lookup"><span data-stu-id="77899-166">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="77899-167">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="77899-167">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="77899-168">.NET의 숫자</span><span class="sxs-lookup"><span data-stu-id="77899-168">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Byte?displayProperty=nameWithType>
- <xref:System.SByte?displayProperty=nameWithType>
- <xref:System.Int16?displayProperty=nameWithType>
- <xref:System.UInt16?displayProperty=nameWithType>
- <xref:System.Int32?displayProperty=nameWithType>
- <xref:System.UInt32?displayProperty=nameWithType>
- <xref:System.Int64?displayProperty=nameWithType>
- <xref:System.UInt64?displayProperty=nameWithType>
