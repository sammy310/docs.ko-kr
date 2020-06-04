---
title: Double 데이터 형식
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 899554f427ac77ead465752c35e51ca88d045763
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415636"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="fea08-102">Double 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fea08-102">Double Data Type (Visual Basic)</span></span>

<span data-ttu-id="fea08-103">음수 324 값의 경우-1.79769313486231570 E + 308부터-4.94065645841246544 E-324 까지의 값 범위에 해당 하는 부호 있는 IEEE 64 비트 (8 바이트) 배정밀도 부동 소수점 숫자를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea08-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="fea08-104">배정밀도 숫자는 실수의 근사값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea08-104">Double-precision numbers store an approximation of a real number.</span></span>

## <a name="remarks"></a><span data-ttu-id="fea08-105">설명</span><span class="sxs-lookup"><span data-stu-id="fea08-105">Remarks</span></span>

<span data-ttu-id="fea08-106">`Double`데이터 형식은 숫자에 대해 가능한 가장 크고 가장 작은 크고 많을을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea08-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>

<span data-ttu-id="fea08-107">`Double`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="fea08-107">The default value of `Double` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="fea08-108">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="fea08-108">Programming Tips</span></span>

- <span data-ttu-id="fea08-109">**소수.**</span><span class="sxs-lookup"><span data-stu-id="fea08-109">**Precision.**</span></span> <span data-ttu-id="fea08-110">부동 소수점 숫자를 사용 하는 경우 항상 메모리에 정확한 표현이 없다는 점을 명심 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fea08-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="fea08-111">이로 인해 값 비교 및 연산자와 같은 특정 작업에서 예기치 않은 결과가 발생할 수 있습니다 `Mod` .</span><span class="sxs-lookup"><span data-stu-id="fea08-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="fea08-112">자세한 내용은 [데이터 형식 문제 해결](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fea08-112">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

- <span data-ttu-id="fea08-113">**후행 0입니다.**</span><span class="sxs-lookup"><span data-stu-id="fea08-113">**Trailing Zeros.**</span></span> <span data-ttu-id="fea08-114">부동 소수점 데이터 형식에는 후행 0 문자에 대 한 내부 표현이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fea08-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="fea08-115">예를 들어 4.2000과 4.2를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fea08-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="fea08-116">따라서 부동 소수점 값을 표시 하거나 인쇄할 때 후행 0 문자는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fea08-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>

- <span data-ttu-id="fea08-117">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fea08-117">**Type Characters.**</span></span> <span data-ttu-id="fea08-118">리터럴 형식 문자 `R`를 리터럴에 추가하면 `Double` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fea08-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="fea08-119">예를 들어 정수 값 뒤에가 오는 경우 `R` 값이로 변경 됩니다 `Double` .</span><span class="sxs-lookup"><span data-stu-id="fea08-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  <span data-ttu-id="fea08-120">식별자 형식 문자 `#`를 식별자에 추가하면 `Double`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fea08-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="fea08-121">다음 예제에서 변수는 `num` 로 형식화 됩니다 `Double` .</span><span class="sxs-lookup"><span data-stu-id="fea08-121">In the following example, the variable `num` is typed as a `Double`:</span></span>

  ```vb
  Dim num# = 3
  ```

- <span data-ttu-id="fea08-122">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="fea08-122">**Framework Type.**</span></span> <span data-ttu-id="fea08-123">.NET Framework에서 해당하는 형식은 <xref:System.Double?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="fea08-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="fea08-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fea08-124">See also</span></span>

- <xref:System.Double?displayProperty=nameWithType>
- [<span data-ttu-id="fea08-125">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fea08-125">Data Types</span></span>](index.md)
- [<span data-ttu-id="fea08-126">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fea08-126">Decimal Data Type</span></span>](decimal-data-type.md)
- [<span data-ttu-id="fea08-127">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fea08-127">Single Data Type</span></span>](single-data-type.md)
- [<span data-ttu-id="fea08-128">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="fea08-128">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="fea08-129">변환 요약</span><span class="sxs-lookup"><span data-stu-id="fea08-129">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="fea08-130">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="fea08-130">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="fea08-131">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fea08-131">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="fea08-132">형식 문자</span><span class="sxs-lookup"><span data-stu-id="fea08-132">Type Characters</span></span>](../../programming-guide/language-features/data-types/type-characters.md)
