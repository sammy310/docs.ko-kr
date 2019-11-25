---
title: << 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 327d0e5cbd1ebcc43bd47fb068f4513940c2165a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350977"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="bac7f-102">\<\< Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bac7f-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="bac7f-103">Performs an arithmetic left shift on a bit pattern.</span><span class="sxs-lookup"><span data-stu-id="bac7f-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bac7f-104">구문</span><span class="sxs-lookup"><span data-stu-id="bac7f-104">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="bac7f-105">요소</span><span class="sxs-lookup"><span data-stu-id="bac7f-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="bac7f-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="bac7f-106">Required.</span></span> <span data-ttu-id="bac7f-107">Integral numeric value.</span><span class="sxs-lookup"><span data-stu-id="bac7f-107">Integral numeric value.</span></span> <span data-ttu-id="bac7f-108">The result of shifting the bit pattern.</span><span class="sxs-lookup"><span data-stu-id="bac7f-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="bac7f-109">The data type is the same as that of `pattern`.</span><span class="sxs-lookup"><span data-stu-id="bac7f-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="bac7f-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="bac7f-110">Required.</span></span> <span data-ttu-id="bac7f-111">Integral numeric expression.</span><span class="sxs-lookup"><span data-stu-id="bac7f-111">Integral numeric expression.</span></span> <span data-ttu-id="bac7f-112">The bit pattern to be shifted.</span><span class="sxs-lookup"><span data-stu-id="bac7f-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="bac7f-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span><span class="sxs-lookup"><span data-stu-id="bac7f-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="bac7f-114">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="bac7f-114">Required.</span></span> <span data-ttu-id="bac7f-115">Numeric expression.</span><span class="sxs-lookup"><span data-stu-id="bac7f-115">Numeric expression.</span></span> <span data-ttu-id="bac7f-116">The number of bits to shift the bit pattern.</span><span class="sxs-lookup"><span data-stu-id="bac7f-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="bac7f-117">The data type must be `Integer` or widen to `Integer`.</span><span class="sxs-lookup"><span data-stu-id="bac7f-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bac7f-118">주의</span><span class="sxs-lookup"><span data-stu-id="bac7f-118">Remarks</span></span>  
 <span data-ttu-id="bac7f-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span><span class="sxs-lookup"><span data-stu-id="bac7f-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="bac7f-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span><span class="sxs-lookup"><span data-stu-id="bac7f-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="bac7f-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span><span class="sxs-lookup"><span data-stu-id="bac7f-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="bac7f-122">The binary AND of these values is used for the shift amount.</span><span class="sxs-lookup"><span data-stu-id="bac7f-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="bac7f-123">The size masks are as follows:</span><span class="sxs-lookup"><span data-stu-id="bac7f-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="bac7f-124">Data type of `pattern`</span><span class="sxs-lookup"><span data-stu-id="bac7f-124">Data type of `pattern`</span></span>|<span data-ttu-id="bac7f-125">Size mask (decimal)</span><span class="sxs-lookup"><span data-stu-id="bac7f-125">Size mask (decimal)</span></span>|<span data-ttu-id="bac7f-126">Size mask (hexadecimal)</span><span class="sxs-lookup"><span data-stu-id="bac7f-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="bac7f-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="bac7f-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="bac7f-128">7</span><span class="sxs-lookup"><span data-stu-id="bac7f-128">7</span></span>|<span data-ttu-id="bac7f-129">&H00000007</span><span class="sxs-lookup"><span data-stu-id="bac7f-129">&H00000007</span></span>|  
|<span data-ttu-id="bac7f-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="bac7f-130">`Short`, `UShort`</span></span>|<span data-ttu-id="bac7f-131">15</span><span class="sxs-lookup"><span data-stu-id="bac7f-131">15</span></span>|<span data-ttu-id="bac7f-132">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="bac7f-132">&H0000000F</span></span>|  
|<span data-ttu-id="bac7f-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="bac7f-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="bac7f-134">31</span><span class="sxs-lookup"><span data-stu-id="bac7f-134">31</span></span>|<span data-ttu-id="bac7f-135">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="bac7f-135">&H0000001F</span></span>|  
|<span data-ttu-id="bac7f-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="bac7f-136">`Long`, `ULong`</span></span>|<span data-ttu-id="bac7f-137">63</span><span class="sxs-lookup"><span data-stu-id="bac7f-137">63</span></span>|<span data-ttu-id="bac7f-138">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="bac7f-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="bac7f-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span><span class="sxs-lookup"><span data-stu-id="bac7f-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="bac7f-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span><span class="sxs-lookup"><span data-stu-id="bac7f-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="bac7f-141">Arithmetic shifts never generate overflow exceptions.</span><span class="sxs-lookup"><span data-stu-id="bac7f-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bac7f-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span><span class="sxs-lookup"><span data-stu-id="bac7f-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="bac7f-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span><span class="sxs-lookup"><span data-stu-id="bac7f-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="bac7f-144">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bac7f-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bac7f-145">예제</span><span class="sxs-lookup"><span data-stu-id="bac7f-145">Example</span></span>  
 <span data-ttu-id="bac7f-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span><span class="sxs-lookup"><span data-stu-id="bac7f-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="bac7f-147">The result always has the same data type as that of the expression being shifted.</span><span class="sxs-lookup"><span data-stu-id="bac7f-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="bac7f-148">The results of the previous example are as follows:</span><span class="sxs-lookup"><span data-stu-id="bac7f-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="bac7f-149">`result1` is 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="bac7f-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="bac7f-150">`result2` is 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="bac7f-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="bac7f-151">`result3` is -32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="bac7f-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="bac7f-152">`result4` is 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="bac7f-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="bac7f-153">`result5` is 0 (shifted 15 places to the left).</span><span class="sxs-lookup"><span data-stu-id="bac7f-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="bac7f-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span><span class="sxs-lookup"><span data-stu-id="bac7f-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac7f-155">참조</span><span class="sxs-lookup"><span data-stu-id="bac7f-155">See also</span></span>

- [<span data-ttu-id="bac7f-156">비트 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="bac7f-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="bac7f-157">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="bac7f-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="bac7f-158"><<= 연산자</span><span class="sxs-lookup"><span data-stu-id="bac7f-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="bac7f-159">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="bac7f-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="bac7f-160">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="bac7f-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="bac7f-161">Arithmetic Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bac7f-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
