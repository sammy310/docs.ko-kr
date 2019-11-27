---
title: '>> 연산자'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: cabf8c569435cc0fc98282f5e8f5fd410e6708dc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347816"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="1ea5f-102">> > 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ea5f-102">>> Operator (Visual Basic)</span></span>
<span data-ttu-id="1ea5f-103">비트 패턴에 산술 오른쪽 시프트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ea5f-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ea5f-104">Syntax</span></span>  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="1ea5f-105">요소</span><span class="sxs-lookup"><span data-stu-id="1ea5f-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="1ea5f-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-106">Required.</span></span> <span data-ttu-id="1ea5f-107">정수 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-107">Integral numeric value.</span></span> <span data-ttu-id="1ea5f-108">결과 비트 패턴을 이동한입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="1ea5f-109">데이터 형식은 `pattern`와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="1ea5f-110">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-110">Required.</span></span> <span data-ttu-id="1ea5f-111">정수 계열 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-111">Integral numeric expression.</span></span> <span data-ttu-id="1ea5f-112">이동할 비트 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="1ea5f-113">데이터 형식은 정수 계열 형식 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`또는 `ULong`) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="1ea5f-114">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-114">Required.</span></span> <span data-ttu-id="1ea5f-115">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-115">Numeric expression.</span></span> <span data-ttu-id="1ea5f-116">비트 패턴을 이동할 비트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="1ea5f-117">데이터 형식을 `Integer` 하거나 `Integer`으로 확장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ea5f-118">주의</span><span class="sxs-lookup"><span data-stu-id="1ea5f-118">Remarks</span></span>  
 <span data-ttu-id="1ea5f-119">산술 시프트는 순환 하지 않습니다. 즉, 결과의 한쪽 끝에서 이동 하는 비트가 다른 쪽 끝에서는 다시 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="1ea5f-120">산술 오른쪽 시프트에서 가장 오른쪽 비트 위치를 넘어 이동 하는 비트는 무시 되 고 맨 왼쪽 (부호) 비트가 왼쪽에서 비워진 비트 위치로 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="1ea5f-121">즉, `pattern`의 값이 음수 이면 빈 위치가 1로 설정 됩니다. 그렇지 않으면 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="1ea5f-122">`Byte`, `UShort`, `UInteger`및 `ULong` 데이터 형식은 부호가 없기 때문에 전파할 부호 비트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="1ea5f-123">`pattern` 부호 없는 형식이 면 빈 위치는 항상 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="1ea5f-124">결과에 포함 될 수 있는 것 보다 더 많은 비트로 이동 하지 않도록 Visual Basic는 `pattern`데이터 형식에 해당 하는 크기 마스크를 사용 하 여 `amount` 값을 마스크 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="1ea5f-125">이러한 값의 이진은 이동 양에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="1ea5f-126">크기 마스크는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="1ea5f-127">`pattern` 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ea5f-127">Data type of `pattern`</span></span>|<span data-ttu-id="1ea5f-128">크기 마스크 (10 진수)</span><span class="sxs-lookup"><span data-stu-id="1ea5f-128">Size mask (decimal)</span></span>|<span data-ttu-id="1ea5f-129">크기 마스크 (16 진수)</span><span class="sxs-lookup"><span data-stu-id="1ea5f-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="1ea5f-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="1ea5f-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="1ea5f-131">7</span><span class="sxs-lookup"><span data-stu-id="1ea5f-131">7</span></span>|<span data-ttu-id="1ea5f-132">&H00000007</span><span class="sxs-lookup"><span data-stu-id="1ea5f-132">&H00000007</span></span>|  
|<span data-ttu-id="1ea5f-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="1ea5f-133">`Short`, `UShort`</span></span>|<span data-ttu-id="1ea5f-134">15</span><span class="sxs-lookup"><span data-stu-id="1ea5f-134">15</span></span>|<span data-ttu-id="1ea5f-135">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="1ea5f-135">&H0000000F</span></span>|  
|<span data-ttu-id="1ea5f-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="1ea5f-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="1ea5f-137">31</span><span class="sxs-lookup"><span data-stu-id="1ea5f-137">31</span></span>|<span data-ttu-id="1ea5f-138">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="1ea5f-138">&H0000001F</span></span>|  
|<span data-ttu-id="1ea5f-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="1ea5f-139">`Long`, `ULong`</span></span>|<span data-ttu-id="1ea5f-140">63</span><span class="sxs-lookup"><span data-stu-id="1ea5f-140">63</span></span>|<span data-ttu-id="1ea5f-141">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="1ea5f-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="1ea5f-142">`amount` 0 이면 `result`의 값이 `pattern`의 값과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="1ea5f-143">`amount` 음수 이면 부호 없는 값으로 사용 되 고 적절 한 크기 마스크로 마스크 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="1ea5f-144">산술 시프트는 오버플로 예외를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="1ea5f-145">오버로드</span><span class="sxs-lookup"><span data-stu-id="1ea5f-145">Overloading</span></span>  
 <span data-ttu-id="1ea5f-146">`>>` 연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1ea5f-147">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1ea5f-148">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ea5f-149">예제</span><span class="sxs-lookup"><span data-stu-id="1ea5f-149">Example</span></span>  
 <span data-ttu-id="1ea5f-150">다음 예에서는 `>>` 연산자를 사용 하 여 정수 값에 대 한 산술 오른쪽 시프트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="1ea5f-151">결과는 항상 이동 하는 식의 데이터 형식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="1ea5f-152">앞의 예제 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-152">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="1ea5f-153">`result1`은 2560 (0000 1010 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
- <span data-ttu-id="1ea5f-154">`result2`은 160 (0000 0000 1010 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
- <span data-ttu-id="1ea5f-155">`result3` 2 (0000 0000 0000 0010)입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
- <span data-ttu-id="1ea5f-156">`result4`은 640 (0000 0010 1000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
- <span data-ttu-id="1ea5f-157">`result5`은 0 (오른쪽으로 15 자리 이동)입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="1ea5f-158">`result4`의 이동 양은 18과 15로 계산 되며 2와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="1ea5f-159">다음 예에서는 음수 값에 대 한 산술 변화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="1ea5f-160">앞의 예제 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-160">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="1ea5f-161">`negresult1`-512 (1111 1110 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="1ea5f-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
- <span data-ttu-id="1ea5f-162">`negresult2`-1입니다 (부호 비트는 전파 됨).</span><span class="sxs-lookup"><span data-stu-id="1ea5f-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ea5f-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ea5f-163">See also</span></span>

- [<span data-ttu-id="1ea5f-164">비트 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="1ea5f-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="1ea5f-165">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="1ea5f-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="1ea5f-166">>>= 연산자</span><span class="sxs-lookup"><span data-stu-id="1ea5f-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [<span data-ttu-id="1ea5f-167">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="1ea5f-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="1ea5f-168">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="1ea5f-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="1ea5f-169">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="1ea5f-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
