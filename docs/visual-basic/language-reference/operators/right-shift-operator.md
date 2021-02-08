---
description: '자세한 정보:  >> 연산자 (Visual Basic)'
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
ms.openlocfilehash: 125b93f129734d196bd1f7f9c4fde86ab5d66319
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795302"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="f11cb-103">>> 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f11cb-103">>> Operator (Visual Basic)</span></span>

<span data-ttu-id="f11cb-104">비트 패턴에 산술 오른쪽 시프트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-104">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f11cb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f11cb-105">Syntax</span></span>  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="f11cb-106">부분</span><span class="sxs-lookup"><span data-stu-id="f11cb-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="f11cb-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-107">Required.</span></span> <span data-ttu-id="f11cb-108">정수 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-108">Integral numeric value.</span></span> <span data-ttu-id="f11cb-109">비트 패턴을 이동한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-109">The result of shifting the bit pattern.</span></span> <span data-ttu-id="f11cb-110">데이터 형식은 `pattern`의 형식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-110">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="f11cb-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f11cb-111">Required.</span></span> <span data-ttu-id="f11cb-112">정수 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-112">Integral numeric expression.</span></span> <span data-ttu-id="f11cb-113">이동할 비트 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-113">The bit pattern to be shifted.</span></span> <span data-ttu-id="f11cb-114">데이터 형식은 정수 계열 형식(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` 또는 `ULong`)이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-114">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="f11cb-115">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f11cb-115">Required.</span></span> <span data-ttu-id="f11cb-116">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-116">Numeric expression.</span></span> <span data-ttu-id="f11cb-117">비트 패턴을 이동할 비트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-117">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="f11cb-118">데이터 형식은 `Integer`이거나 `Integer`로 확장되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-118">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f11cb-119">설명</span><span class="sxs-lookup"><span data-stu-id="f11cb-119">Remarks</span></span>  

 <span data-ttu-id="f11cb-120">산술 시프트는 순환 하지 않습니다. 즉, 결과의 한쪽 끝에서 이동 하는 비트가 다른 쪽 끝에서는 다시 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-120">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="f11cb-121">산술 오른쪽 시프트에서 가장 오른쪽 비트 위치를 넘어 이동 하는 비트는 무시 되 고 맨 왼쪽 (부호) 비트가 왼쪽에서 비워진 비트 위치로 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-121">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="f11cb-122">즉 `pattern` ,의 값이 음수 이면 비워진 위치가 1로 설정 되 고, 그렇지 않으면 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-122">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="f11cb-123">데이터 형식인,, `Byte` 및는 `UShort` 서명 되지 `UInteger` `ULong` 않으므로 전파할 부호 비트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-123">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="f11cb-124">`pattern`가 부호 없는 형식이 면 빈 위치는 항상 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-124">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="f11cb-125">결과에 포함 될 수 있는 것 보다 더 많은 비트로 이동 하지 않도록 Visual Basic의 `amount` 데이터 형식에 해당 하는 크기 마스크를 사용 하 여의 값을 마스크 합니다 `pattern` .</span><span class="sxs-lookup"><span data-stu-id="f11cb-125">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="f11cb-126">이러한 값의 이진은 이동 양에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-126">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="f11cb-127">크기 마스크는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-127">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="f11cb-128">데이터 형식 `pattern`</span><span class="sxs-lookup"><span data-stu-id="f11cb-128">Data type of `pattern`</span></span>|<span data-ttu-id="f11cb-129">크기 마스크 (10 진수)</span><span class="sxs-lookup"><span data-stu-id="f11cb-129">Size mask (decimal)</span></span>|<span data-ttu-id="f11cb-130">크기 마스크 (16 진수)</span><span class="sxs-lookup"><span data-stu-id="f11cb-130">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="f11cb-131">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="f11cb-131">`SByte`, `Byte`</span></span>|<span data-ttu-id="f11cb-132">7</span><span class="sxs-lookup"><span data-stu-id="f11cb-132">7</span></span>|<span data-ttu-id="f11cb-133">&H00000007</span><span class="sxs-lookup"><span data-stu-id="f11cb-133">&H00000007</span></span>|  
|<span data-ttu-id="f11cb-134">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="f11cb-134">`Short`, `UShort`</span></span>|<span data-ttu-id="f11cb-135">15</span><span class="sxs-lookup"><span data-stu-id="f11cb-135">15</span></span>|<span data-ttu-id="f11cb-136">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="f11cb-136">&H0000000F</span></span>|  
|<span data-ttu-id="f11cb-137">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="f11cb-137">`Integer`, `UInteger`</span></span>|<span data-ttu-id="f11cb-138">31</span><span class="sxs-lookup"><span data-stu-id="f11cb-138">31</span></span>|<span data-ttu-id="f11cb-139">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="f11cb-139">&H0000001F</span></span>|  
|<span data-ttu-id="f11cb-140">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="f11cb-140">`Long`, `ULong`</span></span>|<span data-ttu-id="f11cb-141">63</span><span class="sxs-lookup"><span data-stu-id="f11cb-141">63</span></span>|<span data-ttu-id="f11cb-142">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="f11cb-142">&H0000003F</span></span>|  
  
 <span data-ttu-id="f11cb-143">`amount`가 0 인 경우의 값은 `result` 의 값과 동일 합니다 `pattern` .</span><span class="sxs-lookup"><span data-stu-id="f11cb-143">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="f11cb-144">`amount`가 음수 이면 부호 없는 값으로 사용 되 고 적절 한 크기 마스크로 마스크 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-144">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="f11cb-145">산술 시프트는 오버플로 예외를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-145">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f11cb-146">오버로딩</span><span class="sxs-lookup"><span data-stu-id="f11cb-146">Overloading</span></span>  

 <span data-ttu-id="f11cb-147">`>>`연산자를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-147">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f11cb-148">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-148">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f11cb-149">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f11cb-149">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f11cb-150">예제</span><span class="sxs-lookup"><span data-stu-id="f11cb-150">Example</span></span>  

 <span data-ttu-id="f11cb-151">다음 예에서는 연산자를 사용 `>>` 하 여 정수 값에 대 한 산술 오른쪽 시프트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-151">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="f11cb-152">결과는 항상 이동 하는 식의 데이터 형식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-152">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="f11cb-153">앞의 예제 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-153">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="f11cb-154">`result1` 는 2560 (0000 1010 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-154">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
- <span data-ttu-id="f11cb-155">`result2` 는 160 (0000 0000 1010 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-155">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
- <span data-ttu-id="f11cb-156">`result3` 는 2 (0000 0000 0000 0010)입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-156">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
- <span data-ttu-id="f11cb-157">`result4` 는 640 (0000 0010 1000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-157">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
- <span data-ttu-id="f11cb-158">`result5` 가 0 (오른쪽으로 15 자리 이동)입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-158">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="f11cb-159">의 이동 금액 `result4` 은 2와 같은 18 및 15로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-159">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="f11cb-160">다음 예에서는 음수 값에 대 한 산술 변화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-160">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="f11cb-161">앞의 예제 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-161">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="f11cb-162">`negresult1` 는-512 (1111 1110 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-162">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
- <span data-ttu-id="f11cb-163">`negresult2` -1 (부호 비트가 전파 됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="f11cb-163">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f11cb-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f11cb-164">See also</span></span>

- [<span data-ttu-id="f11cb-165">비트 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="f11cb-165">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="f11cb-166">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="f11cb-166">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="f11cb-167">>>= 연산자</span><span class="sxs-lookup"><span data-stu-id="f11cb-167">>>= Operator</span></span>](right-shift-assignment-operator.md)
- [<span data-ttu-id="f11cb-168">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="f11cb-168">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="f11cb-169">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="f11cb-169">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="f11cb-170">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="f11cb-170">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
