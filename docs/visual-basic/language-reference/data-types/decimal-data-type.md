---
description: '자세한 정보: Decimal 데이터 형식 (Visual Basic)'
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
ms.openlocfilehash: 5806041e7737b8fe0f1c7ffa63f6cbadcbf92e42
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792234"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="53290-103">Decimal 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53290-103">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="53290-104">10의 가변 배율로 조정된 96비트(12바이트) 정수 숫자를 표시하는 서명된 128비트(16바이트) 값을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="53290-104">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="53290-105">배율 인수는 소수점 오른쪽의 자릿수를 지정 합니다. 범위는 0에서 28 까지입니다.</span><span class="sxs-lookup"><span data-stu-id="53290-105">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="53290-106">소수 자릿수가 0 인 소수 자릿수가 0 인 경우 가능한 최대값은 +/-79228162514264337593543950335 (+/-7.9228162514264337593543950335E + 28)입니다.</span><span class="sxs-lookup"><span data-stu-id="53290-106">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="53290-107">28 자리의 소수 자릿수를 사용 하면 가장 큰 값은 +/-7.9228162514264337593543950335이 고 0이 아닌 가장 작은 값은 +/-0.0000000000000000000000000001 (+/-1E-28)입니다.</span><span class="sxs-lookup"><span data-stu-id="53290-107">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="53290-108">설명</span><span class="sxs-lookup"><span data-stu-id="53290-108">Remarks</span></span>

<span data-ttu-id="53290-109">`Decimal`데이터 형식은 숫자에 대 한 최대 유효 자릿수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="53290-109">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="53290-110">최대 29 개의 유효 숫자를 지원 하며 7.9228 x 10 ^ 28을 초과 하는 값을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53290-110">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="53290-111">매우 많은 숫자가 필요 하지만 반올림 오류를 허용할 수 없는 재무와 같은 계산에 특히 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="53290-111">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="53290-112">`Decimal`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="53290-112">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="53290-113">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="53290-113">Programming Tips</span></span>

- <span data-ttu-id="53290-114">**소수.**</span><span class="sxs-lookup"><span data-stu-id="53290-114">**Precision.**</span></span> <span data-ttu-id="53290-115">`Decimal` 이 부동 소수점 데이터 형식이 아닌 경우</span><span class="sxs-lookup"><span data-stu-id="53290-115">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="53290-116">`Decimal`구조체는 부호 비트와 소수 부분을 지정 하는 정수 배율 인수와 함께 이진 정수 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="53290-116">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="53290-117">이로 인해 `Decimal` 숫자는 부동 소수점 형식 (및) 보다 메모리를 보다 정확 하 게 `Single` 표현 `Double` 합니다.</span><span class="sxs-lookup"><span data-stu-id="53290-117">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="53290-118">**성능.**</span><span class="sxs-lookup"><span data-stu-id="53290-118">**Performance.**</span></span> <span data-ttu-id="53290-119">`Decimal`데이터 형식은 모든 숫자 형식이 가장 느립니다.</span><span class="sxs-lookup"><span data-stu-id="53290-119">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="53290-120">데이터 형식을 선택 하기 전에 성능에 대 한 정밀도의 중요도를 평가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53290-120">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="53290-121">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="53290-121">**Widening.**</span></span> <span data-ttu-id="53290-122">`Decimal`데이터 형식이 또는로 확대 `Single` `Double` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53290-122">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="53290-123">즉, `Decimal` 오류가 발생 하지 않고 이러한 형식 중 하나로 변환할 수 있습니다 <xref:System.OverflowException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="53290-123">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="53290-124">**후행 0입니다.**</span><span class="sxs-lookup"><span data-stu-id="53290-124">**Trailing Zeros.**</span></span> <span data-ttu-id="53290-125">Visual Basic는 리터럴에 후행 0을 저장 하지 않습니다 `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="53290-125">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="53290-126">그러나 변수는 `Decimal` 계산이 획득 된 후행 0을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="53290-126">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="53290-127">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="53290-127">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="53290-128">앞의 예제에서의 출력은 다음과 같습니다 `MsgBox` .</span><span class="sxs-lookup"><span data-stu-id="53290-128">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="53290-129">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="53290-129">**Type Characters.**</span></span> <span data-ttu-id="53290-130">리터럴 형식 문자 `D`를 리터럴에 추가하면 `Decimal` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53290-130">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="53290-131">식별자 형식 문자 `@`를 식별자에 추가하면 `Decimal`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53290-131">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="53290-132">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="53290-132">**Framework Type.**</span></span> <span data-ttu-id="53290-133">.NET Framework에서 해당하는 형식은 <xref:System.Decimal?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="53290-133">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="53290-134">범위</span><span class="sxs-lookup"><span data-stu-id="53290-134">Range</span></span>

 <span data-ttu-id="53290-135">형식 문자를 사용 하 여 `D` 변수 또는 상수에 많은 값을 할당 해야 할 수도 있습니다 `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="53290-135">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="53290-136">이 요구 사항은 `Long` 다음 예제와 같이 리터럴 형식 문자가 리터럴을 따르는 경우를 제외 하 고 컴파일러가 리터럴을 해석 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="53290-136">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="53290-137">에 할당 된 `bigDec1` 값이의 범위 내에 있기 때문에에 대 한 선언은 오버플로를 생성 하지 않습니다 `Long` .</span><span class="sxs-lookup"><span data-stu-id="53290-137">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="53290-138">`Long`변수에 값을 할당할 수 있습니다 `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="53290-138">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="53290-139">에 할당 된 `bigDec2` 값이에 비해 너무 커서 오버플로 오류가 발생 합니다 `Long` .</span><span class="sxs-lookup"><span data-stu-id="53290-139">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="53290-140">숫자 리터럴은 먼저로 해석 될 수 없으므로 `Long` 변수에 할당할 수 없습니다 `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="53290-140">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="53290-141">의 경우 `bigDec3` 리터럴 형식 문자는 `D` 컴파일러가 리터럴을 대신로 해석 하도록 하 여 문제를 해결 합니다 `Decimal` `Long` .</span><span class="sxs-lookup"><span data-stu-id="53290-141">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="53290-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53290-142">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="53290-143">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="53290-143">Data Types</span></span>](index.md)
- [<span data-ttu-id="53290-144">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="53290-144">Single Data Type</span></span>](single-data-type.md)
- [<span data-ttu-id="53290-145">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="53290-145">Double Data Type</span></span>](double-data-type.md)
- [<span data-ttu-id="53290-146">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="53290-146">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="53290-147">변환 요약</span><span class="sxs-lookup"><span data-stu-id="53290-147">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="53290-148">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="53290-148">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
