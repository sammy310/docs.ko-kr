---
description: '자세한 정보: 단일 데이터 형식 (Visual Basic)'
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
ms.openlocfilehash: f30e21d3b2d2960a040609a9422ec71cc029f5be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792130"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="f65e7-103">Single 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f65e7-103">Single Data Type (Visual Basic)</span></span>

<span data-ttu-id="f65e7-104">음수 값의 경우-3.4028235 E + 38부터-1.401298 E-45 까지의 값에 해당 하는 부호 있는 IEEE 32 비트 (4 바이트) 단 정밀도 부동 소수점 숫자와 양수 값의 경우 1.401298 E-45 ~ 3.4028235 E + 38 사이의 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f65e7-104">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="f65e7-105">단 정밀도 숫자는 실수의 근사값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f65e7-105">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f65e7-106">설명</span><span class="sxs-lookup"><span data-stu-id="f65e7-106">Remarks</span></span>  

 <span data-ttu-id="f65e7-107">`Single`데이터 형식을 사용 하 여의 전체 데이터 너비가 필요 하지 않은 부동 소수점 값을 포함 합니다 `Double` .</span><span class="sxs-lookup"><span data-stu-id="f65e7-107">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="f65e7-108">경우에 따라 공용 언어 런타임에서 변수를 긴밀 하 게 압축 하 `Single` 고 메모리 사용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f65e7-108">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="f65e7-109">`Single`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="f65e7-109">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="f65e7-110">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="f65e7-110">Programming Tips</span></span>  
  
- <span data-ttu-id="f65e7-111">**소수.**</span><span class="sxs-lookup"><span data-stu-id="f65e7-111">**Precision.**</span></span> <span data-ttu-id="f65e7-112">부동 소수점 숫자를 사용 하는 경우 항상 메모리에 정확한 표현이 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f65e7-112">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="f65e7-113">이로 인해 값 비교 및 연산자와 같은 특정 작업에서 예기치 않은 결과가 발생할 수 있습니다 `Mod` .</span><span class="sxs-lookup"><span data-stu-id="f65e7-113">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="f65e7-114">자세한 내용은 [데이터 형식 문제 해결](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f65e7-114">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="f65e7-115">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="f65e7-115">**Widening.**</span></span> <span data-ttu-id="f65e7-116">`Single`데이터 형식이로 확대 `Double` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f65e7-116">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="f65e7-117">즉, `Single` `Double` 오류가 발생 하지 않고로 변환할 수 있습니다 <xref:System.OverflowException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f65e7-117">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="f65e7-118">**후행 0입니다.**</span><span class="sxs-lookup"><span data-stu-id="f65e7-118">**Trailing Zeros.**</span></span> <span data-ttu-id="f65e7-119">부동 소수점 데이터 형식에는 후행 0 문자에 대 한 내부 표현이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f65e7-119">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="f65e7-120">예를 들어 4.2000과 4.2를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f65e7-120">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="f65e7-121">따라서 부동 소수점 값을 표시 하거나 인쇄할 때 후행 0 문자는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f65e7-121">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="f65e7-122">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f65e7-122">**Type Characters.**</span></span> <span data-ttu-id="f65e7-123">리터럴 형식 문자 `F`를 리터럴에 추가하면 `Single` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f65e7-123">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="f65e7-124">식별자 형식 문자 `!`를 식별자에 추가하면 `Single`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f65e7-124">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
- <span data-ttu-id="f65e7-125">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="f65e7-125">**Framework Type.**</span></span> <span data-ttu-id="f65e7-126">.NET Framework에서 해당하는 형식은 <xref:System.Single?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="f65e7-126">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f65e7-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f65e7-127">See also</span></span>

- <xref:System.Single?displayProperty=nameWithType>
- [<span data-ttu-id="f65e7-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f65e7-128">Data Types</span></span>](index.md)
- [<span data-ttu-id="f65e7-129">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f65e7-129">Decimal Data Type</span></span>](decimal-data-type.md)
- [<span data-ttu-id="f65e7-130">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f65e7-130">Double Data Type</span></span>](double-data-type.md)
- [<span data-ttu-id="f65e7-131">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="f65e7-131">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="f65e7-132">변환 요약</span><span class="sxs-lookup"><span data-stu-id="f65e7-132">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="f65e7-133">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="f65e7-133">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="f65e7-134">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f65e7-134">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
