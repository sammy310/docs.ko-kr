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
ms.openlocfilehash: ecb0f5f6416a2dd4ddd6888cb80ed3ac11ee58df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415533"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="60efa-102">Single 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60efa-102">Single Data Type (Visual Basic)</span></span>

<span data-ttu-id="60efa-103">음수 값의 경우-3.4028235 E + 38부터-1.401298 E-45 까지의 값에 해당 하는 부호 있는 IEEE 32 비트 (4 바이트) 단 정밀도 부동 소수점 숫자와 양수 값의 경우 1.401298 E-45 ~ 3.4028235 E + 38 사이의 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="60efa-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="60efa-104">단 정밀도 숫자는 실수의 근사값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="60efa-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60efa-105">설명</span><span class="sxs-lookup"><span data-stu-id="60efa-105">Remarks</span></span>  

 <span data-ttu-id="60efa-106">`Single`데이터 형식을 사용 하 여의 전체 데이터 너비가 필요 하지 않은 부동 소수점 값을 포함 합니다 `Double` .</span><span class="sxs-lookup"><span data-stu-id="60efa-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="60efa-107">경우에 따라 공용 언어 런타임에서 변수를 긴밀 하 게 압축 하 `Single` 고 메모리 사용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60efa-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="60efa-108">`Single`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="60efa-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="60efa-109">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="60efa-109">Programming Tips</span></span>  
  
- <span data-ttu-id="60efa-110">**소수.**</span><span class="sxs-lookup"><span data-stu-id="60efa-110">**Precision.**</span></span> <span data-ttu-id="60efa-111">부동 소수점 숫자를 사용 하는 경우 항상 메모리에 정확한 표현이 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="60efa-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="60efa-112">이로 인해 값 비교 및 연산자와 같은 특정 작업에서 예기치 않은 결과가 발생할 수 있습니다 `Mod` .</span><span class="sxs-lookup"><span data-stu-id="60efa-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="60efa-113">자세한 내용은 [데이터 형식 문제 해결](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60efa-113">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="60efa-114">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="60efa-114">**Widening.**</span></span> <span data-ttu-id="60efa-115">`Single`데이터 형식이로 확대 `Double` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60efa-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="60efa-116">즉, `Single` `Double` 오류가 발생 하지 않고로 변환할 수 있습니다 <xref:System.OverflowException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="60efa-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="60efa-117">**후행 0입니다.**</span><span class="sxs-lookup"><span data-stu-id="60efa-117">**Trailing Zeros.**</span></span> <span data-ttu-id="60efa-118">부동 소수점 데이터 형식에는 후행 0 문자에 대 한 내부 표현이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60efa-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="60efa-119">예를 들어 4.2000과 4.2를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60efa-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="60efa-120">따라서 부동 소수점 값을 표시 하거나 인쇄할 때 후행 0 문자는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60efa-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="60efa-121">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="60efa-121">**Type Characters.**</span></span> <span data-ttu-id="60efa-122">리터럴 형식 문자 `F`를 리터럴에 추가하면 `Single` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60efa-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="60efa-123">식별자 형식 문자 `!`를 식별자에 추가하면 `Single`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60efa-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
- <span data-ttu-id="60efa-124">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="60efa-124">**Framework Type.**</span></span> <span data-ttu-id="60efa-125">.NET Framework에서 해당하는 형식은 <xref:System.Single?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="60efa-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60efa-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60efa-126">See also</span></span>

- <xref:System.Single?displayProperty=nameWithType>
- [<span data-ttu-id="60efa-127">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="60efa-127">Data Types</span></span>](index.md)
- [<span data-ttu-id="60efa-128">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="60efa-128">Decimal Data Type</span></span>](decimal-data-type.md)
- [<span data-ttu-id="60efa-129">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="60efa-129">Double Data Type</span></span>](double-data-type.md)
- [<span data-ttu-id="60efa-130">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="60efa-130">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="60efa-131">변환 요약</span><span class="sxs-lookup"><span data-stu-id="60efa-131">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="60efa-132">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="60efa-132">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="60efa-133">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="60efa-133">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
