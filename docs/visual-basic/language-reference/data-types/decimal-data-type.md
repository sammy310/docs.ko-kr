---
title: Decimal 데이터 형식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: 892824b61cfb6a0172361d220c638cab0a78565d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700871"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="87042-102">Decimal 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87042-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="87042-103">10의 변수 거듭제곱으로 크기가 조정 된 96 비트 (12 바이트) 정수 숫자를 나타내는 부호 있는 128 비트 (16 바이트) 값을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="87042-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="87042-104">배율 인수는 소수점 오른쪽의 자릿수를 지정 합니다. 범위는 0에서 28 까지입니다.</span><span class="sxs-lookup"><span data-stu-id="87042-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="87042-105">소수 자릿수가 0 인 소수 자릿수가 0 인 경우 가능한 최대값은 +/-79228162514264337593543950335 (+/-7.9228162514264337593543950335E + 28)입니다.</span><span class="sxs-lookup"><span data-stu-id="87042-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="87042-106">28 자리의 소수 자릿수를 사용 하면 가장 큰 값은 +/-7.9228162514264337593543950335이 고 0이 아닌 가장 작은 값은 +/-0.0000000000000000000000000001 (+/-1E-28)입니다.</span><span class="sxs-lookup"><span data-stu-id="87042-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="87042-107">설명</span><span class="sxs-lookup"><span data-stu-id="87042-107">Remarks</span></span>

<span data-ttu-id="87042-108">@No__t-0 데이터 형식은 숫자에 대 한 최대 유효 자릿수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="87042-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="87042-109">최대 29 개의 유효 숫자를 지원 하며 7.9228 x 10 ^ 28을 초과 하는 값을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87042-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="87042-110">매우 많은 숫자가 필요 하지만 반올림 오류를 허용할 수 없는 재무와 같은 계산에 특히 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="87042-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="87042-111">`Decimal`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="87042-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="87042-112">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="87042-112">Programming Tips</span></span>

- <span data-ttu-id="87042-113">**소수.**</span><span class="sxs-lookup"><span data-stu-id="87042-113">**Precision.**</span></span> <span data-ttu-id="87042-114">`Decimal`은 부동 소수점 데이터 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="87042-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="87042-115">@No__t-0 구조체는 부호 비트와 소수 부분을 지정 하는 정수 배율 인수와 함께 이진 정수 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="87042-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="87042-116">이로 인해 `Decimal` 숫자는 부동 소수점 형식 (`Single` 및 `Double`) 보다 메모리에서 보다 정확 하 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87042-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="87042-117">**성능.**</span><span class="sxs-lookup"><span data-stu-id="87042-117">**Performance.**</span></span> <span data-ttu-id="87042-118">@No__t-0 데이터 형식은 모든 숫자 형식의 가장 느린 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="87042-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="87042-119">데이터 형식을 선택 하기 전에 성능에 대 한 정밀도의 중요도를 평가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87042-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="87042-120">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="87042-120">**Widening.**</span></span> <span data-ttu-id="87042-121">@No__t-0 데이터 형식은 `Single` 또는 `Double`로 확대 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87042-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="87042-122">즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 발생 하지 않고 `Decimal`을 이러한 형식 중 하나로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87042-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="87042-123">**후행 0입니다.**</span><span class="sxs-lookup"><span data-stu-id="87042-123">**Trailing Zeros.**</span></span> <span data-ttu-id="87042-124">Visual Basic는 `Decimal` 리터럴에 후행 0을 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87042-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="87042-125">그러나 `Decimal` 변수는 계산 된 후행 0을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="87042-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="87042-126">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="87042-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="87042-127">위의 예제에서 `MsgBox`의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87042-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="87042-128">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="87042-128">**Type Characters.**</span></span> <span data-ttu-id="87042-129">리터럴 형식 문자 `D`를 리터럴에 추가하면 `Decimal` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87042-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="87042-130">식별자 형식 문자 `@`를 식별자에 추가하면 `Decimal`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87042-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="87042-131">**프레임 워크 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="87042-131">**Framework Type.**</span></span> <span data-ttu-id="87042-132">.NET Framework에서 해당하는 형식은 <xref:System.Decimal?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="87042-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="87042-133">범위</span><span class="sxs-lookup"><span data-stu-id="87042-133">Range</span></span>
 <span data-ttu-id="87042-134">@No__t-0 형식 문자를 사용 하 여 `Decimal` 변수 또는 상수에 많은 값을 할당 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87042-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="87042-135">이 요구 사항은 다음 예제와 같이 리터럴 형식 문자가 리터럴을 따르는 경우를 제외 하 고 컴파일러가 리터럴을 `Long`으로 해석 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="87042-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="87042-136">할당 된 값이 `Long`의 범위 내에 있기 때문에 `bigDec1`에 대 한 선언이 오버플로를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87042-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="87042-137">@No__t-0 값을 `Decimal` 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87042-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="87042-138">@No__t-0에 대 한 선언은 할당 된 값이 `Long`에 비해 너무 커서 오버플로 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="87042-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="87042-139">숫자 리터럴은 먼저 `Long`으로 해석할 수 없으므로 `Decimal` 변수에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87042-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="87042-140">@No__t-0의 경우 리터럴 형식 문자 `D`은 컴파일러가 리터럴을 `Long`이 아닌 `Decimal`로 해석 하도록 하 여 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="87042-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="87042-141">참조</span><span class="sxs-lookup"><span data-stu-id="87042-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="87042-142">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="87042-142">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="87042-143">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="87042-143">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="87042-144">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="87042-144">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="87042-145">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="87042-145">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="87042-146">변환 요약</span><span class="sxs-lookup"><span data-stu-id="87042-146">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="87042-147">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="87042-147">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
