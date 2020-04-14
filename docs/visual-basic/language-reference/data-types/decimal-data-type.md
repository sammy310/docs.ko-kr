---
title: Decimal 데이터 형식
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
ms.openlocfilehash: d4d868ba7c05cf3c2d538de1217231df91d4f43d
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243325"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="fb419-102">Decimal 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb419-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="fb419-103">10의 가변 배율로 조정된 96비트(12바이트) 정수 숫자를 표시하는 서명된 128비트(16바이트) 값을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="fb419-104">배율 인수는 소수점 의 오른쪽에 있는 자릿수를 지정합니다. 0에서 28까지의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="fb419-105">배율이 0(소수자릿수 없음)인 경우 가능한 가장 큰 값은 +/79,228,162,514,264,337,593,543,950,335(+/7.92286251444337555353335+)입니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="fb419-106">소수점 이하 28자리의 경우 가장 큰 값은 +/7.9228162514264437533335555335이며, 가장 작은 비영값은 +/-0.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000035입니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="fb419-107">설명</span><span class="sxs-lookup"><span data-stu-id="fb419-107">Remarks</span></span>

<span data-ttu-id="fb419-108">데이터 `Decimal` 형식은 숫자에 대해 가장 많은 중요한 숫자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="fb419-109">최대 29개의 중요한 숫자를 지원하며 7.9228 x 10^28을 초과하는 값을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="fb419-110">많은 숫자가 필요하지만 반올림 오류를 견딜 수 없는 재무 와 같은 계산에 특히 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="fb419-111">`Decimal`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="fb419-112">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="fb419-112">Programming Tips</span></span>

- <span data-ttu-id="fb419-113">**정밀도.**</span><span class="sxs-lookup"><span data-stu-id="fb419-113">**Precision.**</span></span> <span data-ttu-id="fb419-114">`Decimal`는 부동 지점 데이터 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="fb419-115">구조는 `Decimal` 이진 정수 값을 가지며, 부호 비트 및 값의 소수점 분수 부분을 지정하는 정수 배율 인수와 함께 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="fb419-116">따라서 `Decimal` 숫자는 부동 점 형식 (및)보다`Single` `Double`메모리에서 더 정확한 표현을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="fb419-117">**성능.**</span><span class="sxs-lookup"><span data-stu-id="fb419-117">**Performance.**</span></span> <span data-ttu-id="fb419-118">데이터 `Decimal` 형식은 모든 숫자 형식 중 에서 가장 느립니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="fb419-119">데이터 형식을 선택하기 전에 성능과 정밀도의 중요성을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="fb419-120">**확대.**</span><span class="sxs-lookup"><span data-stu-id="fb419-120">**Widening.**</span></span> <span data-ttu-id="fb419-121">데이터 `Decimal` 형식이 또는 `Single` `Double`로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="fb419-122">즉, 오류가 `Decimal` 발생하지 않고 이러한 형식 중 <xref:System.OverflowException?displayProperty=nameWithType> 하나로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="fb419-123">**후행 영점.**</span><span class="sxs-lookup"><span data-stu-id="fb419-123">**Trailing Zeros.**</span></span> <span data-ttu-id="fb419-124">Visual Basic은 후행 영점을 `Decimal` 리터럴에 저장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="fb419-125">그러나 변수는 `Decimal` 후행 영점 0을 계산적으로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="fb419-126">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="fb419-127">앞의 `MsgBox` 예제의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="fb419-128">**문자를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb419-128">**Type Characters.**</span></span> <span data-ttu-id="fb419-129">리터럴 형식 문자 `D`를 리터럴에 추가하면 `Decimal` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="fb419-130">식별자 형식 문자 `@`를 식별자에 추가하면 `Decimal`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="fb419-131">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="fb419-131">**Framework Type.**</span></span> <span data-ttu-id="fb419-132">.NET Framework에서 해당하는 형식은 <xref:System.Decimal?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="fb419-133">범위</span><span class="sxs-lookup"><span data-stu-id="fb419-133">Range</span></span>

 <span data-ttu-id="fb419-134">`D` 형식 문자를 사용하여 변수 또는 상수에 큰 값을 할당해야 할 수 `Decimal` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="fb419-135">이 요구 사항은 다음 예제에서 볼 `Long` 수 있듯이 리터럴 형식 문자가 리터럴을 따르지 않는 한 컴파일러가 리터럴을 문자로 해석하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="fb419-136">에 대 `bigDec1` 한 선언은 오버플로를 생성 하지 않습니다 에 할당 된 `Long`값이 에 대 한 범위 내에 있기 때문에.</span><span class="sxs-lookup"><span data-stu-id="fb419-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="fb419-137">변수에 `Long` 값을 할당할 `Decimal` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="fb419-138">에 할당된 `bigDec2` 값이 너무 커서 오버플로 오류가 `Long`생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="fb419-139">숫자 리터럴은 먼저 로 `Long`해석할 수 없으므로 `Decimal` 변수에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="fb419-140">의 `bigDec3`경우 리터럴 `D` 형식 문자는 컴파일러가 리터럴을 `Decimal` `Long`대신 에 로 해석하도록 하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="fb419-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb419-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb419-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fb419-142">데이터 유형</span><span class="sxs-lookup"><span data-stu-id="fb419-142">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="fb419-143">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fb419-143">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="fb419-144">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fb419-144">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="fb419-145">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="fb419-145">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="fb419-146">변환 요약</span><span class="sxs-lookup"><span data-stu-id="fb419-146">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="fb419-147">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="fb419-147">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
