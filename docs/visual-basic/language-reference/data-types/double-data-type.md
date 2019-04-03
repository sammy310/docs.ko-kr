---
title: Double 데이터 형식(Visual Basic)
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
ms.openlocfilehash: 701d10a334757a96ffd634204c1e1d5eb5418ce6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824665"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="ec896-102">Double 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec896-102">Double Data Type (Visual Basic)</span></span>
<span data-ttu-id="ec896-103">부호 있는 IEEE 64 비트 (8 바이트) 배정밀도 부동 소수점 숫자 값에서-1.79769313486231570 + 308에서-범위에 있는 저장 4.94065645841246544E-324 음수 값을 한 경우 4.94065645841246544 e에서-324 1.79769313486231570 e + 308에 대 한 양수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="ec896-104">배정밀도 숫자는 실수의 근사값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-104">Double-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec896-105">설명</span><span class="sxs-lookup"><span data-stu-id="ec896-105">Remarks</span></span>  
 <span data-ttu-id="ec896-106">`Double` 숫자 데이터 형식을 사용할 수 있는 가장 크고 가장 작은 크기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>  
  
 <span data-ttu-id="ec896-107">`Double`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-107">The default value of `Double` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="ec896-108">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="ec896-108">Programming Tips</span></span>  
  
-   <span data-ttu-id="ec896-109">**전체 자릿수입니다.**</span><span class="sxs-lookup"><span data-stu-id="ec896-109">**Precision.**</span></span> <span data-ttu-id="ec896-110">부동 소수점 숫자를 사용 하 여 작업할 때 없다는 점에 주의 해야 하는 항상 정확한 표현을 메모리에서.</span><span class="sxs-lookup"><span data-stu-id="ec896-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="ec896-111">값 비교 등의 특정 작업에서 예기치 않은 결과가 나타날 수 및 `Mod` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="ec896-112">자세한 내용은 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-112">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
-   <span data-ttu-id="ec896-113">**뒤에 오는 0입니다.**</span><span class="sxs-lookup"><span data-stu-id="ec896-113">**Trailing Zeros.**</span></span> <span data-ttu-id="ec896-114">부동 소수점 데이터 형식에 후행 0 문자의 모든 내부 표현이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="ec896-115">예를 들어, 이러한 구분 하지 않습니다 4.2000 및 4.2 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="ec896-116">결과적으로 후행 0 문자 표시 하는 경우 또는 인쇄 부동 소수점 값 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>  
  
-   <span data-ttu-id="ec896-117">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="ec896-117">**Type Characters.**</span></span> <span data-ttu-id="ec896-118">리터럴 형식 문자 `R`를 리터럴에 추가하면 `Double` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="ec896-119">예를 들어 정수 값을 뒤 `R`, 값으로 변경 되는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     <span data-ttu-id="ec896-120">식별자 형식 문자 `#`를 식별자에 추가하면 `Double`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="ec896-121">다음 예에서 변수 `num` 으로 입력 된를 `Double`:</span><span class="sxs-lookup"><span data-stu-id="ec896-121">In the following example, the variable `num` is typed as a `Double`:</span></span>  
  
    ```  
    Dim num# = 3  
    ```  
  
-   <span data-ttu-id="ec896-122">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="ec896-122">**Framework Type.**</span></span> <span data-ttu-id="ec896-123">.NET Framework에서 해당하는 형식은 <xref:System.Double?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="ec896-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec896-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="ec896-124">See also</span></span>

- <xref:System.Double?displayProperty=nameWithType>
- [<span data-ttu-id="ec896-125">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ec896-125">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="ec896-126">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ec896-126">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="ec896-127">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ec896-127">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="ec896-128">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="ec896-128">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="ec896-129">변환 요약</span><span class="sxs-lookup"><span data-stu-id="ec896-129">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="ec896-130">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="ec896-130">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="ec896-131">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ec896-131">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="ec896-132">형식 문자</span><span class="sxs-lookup"><span data-stu-id="ec896-132">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
