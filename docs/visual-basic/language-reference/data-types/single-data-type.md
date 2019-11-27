---
title: Single 데이터 형식
ms.date: 07/20/2015
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
ms.openlocfilehash: 60a688c510f6e36dca5809566b37a388429e18c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343926"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="e0448-102">Single 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0448-102">Single Data Type (Visual Basic)</span></span>

<span data-ttu-id="e0448-103">음수 값의 경우-3.4028235 E + 38부터-1.401298 E-45 까지의 값에 해당 하는 부호 있는 IEEE 32 비트 (4 바이트) 단 정밀도 부동 소수점 숫자와 양수 값의 경우 1.401298 E-45 ~ 3.4028235 E + 38 사이의 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="e0448-104">단 정밀도 숫자는 실수의 근사값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0448-105">주의</span><span class="sxs-lookup"><span data-stu-id="e0448-105">Remarks</span></span>  

 <span data-ttu-id="e0448-106">`Single` 데이터 형식을 사용 하 여 `Double`의 전체 데이터 너비가 필요 하지 않은 부동 소수점 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="e0448-107">경우에 따라 공용 언어 런타임에서 `Single` 변수를 긴밀 하 게 압축 하 고 메모리 사용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="e0448-108">`Single`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="e0448-109">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="e0448-109">Programming Tips</span></span>  
  
- <span data-ttu-id="e0448-110">**소수.**</span><span class="sxs-lookup"><span data-stu-id="e0448-110">**Precision.**</span></span> <span data-ttu-id="e0448-111">부동 소수점 숫자를 사용 하는 경우 항상 메모리에 정확한 표현이 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0448-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="e0448-112">이로 인해 값 비교 및 `Mod` 연산자와 같은 특정 작업에서 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="e0448-113">자세한 내용은 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0448-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="e0448-114">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="e0448-114">**Widening.**</span></span> <span data-ttu-id="e0448-115">`Single` 데이터 형식은 `Double`으로 확대 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="e0448-116">즉 <xref:System.OverflowException?displayProperty=nameWithType> 오류가 발생 하지 않고 `Single`을 `Double`로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="e0448-117">**후행 0입니다.**</span><span class="sxs-lookup"><span data-stu-id="e0448-117">**Trailing Zeros.**</span></span> <span data-ttu-id="e0448-118">부동 소수점 데이터 형식에는 후행 0 문자에 대 한 내부 표현이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="e0448-119">예를 들어 4.2000과 4.2를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="e0448-120">따라서 부동 소수점 값을 표시 하거나 인쇄할 때 후행 0 문자는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="e0448-121">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0448-121">**Type Characters.**</span></span> <span data-ttu-id="e0448-122">리터럴 형식 문자 `F`를 리터럴에 추가하면 `Single` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="e0448-123">식별자 형식 문자 `!`를 식별자에 추가하면 `Single`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
- <span data-ttu-id="e0448-124">**프레임 워크 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="e0448-124">**Framework Type.**</span></span> <span data-ttu-id="e0448-125">.NET Framework에서 해당하는 형식은 <xref:System.Single?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="e0448-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0448-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0448-126">See also</span></span>

- <xref:System.Single?displayProperty=nameWithType>
- [<span data-ttu-id="e0448-127">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e0448-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="e0448-128">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e0448-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="e0448-129">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e0448-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="e0448-130">CString</span><span class="sxs-lookup"><span data-stu-id="e0448-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="e0448-131">변환 요약</span><span class="sxs-lookup"><span data-stu-id="e0448-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="e0448-132">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="e0448-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="e0448-133">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e0448-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
