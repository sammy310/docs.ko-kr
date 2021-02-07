---
description: '자세한 정보:  << 연산자 (Visual Basic)'
title: << 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 079af61e5c4ce3834db0877feace724c74c8169c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665629"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="7d60c-103">\<\< 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d60c-103">\<\< Operator (Visual Basic)</span></span>

<span data-ttu-id="7d60c-104">비트 패턴에 산술 왼쪽 시프트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-104">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d60c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d60c-105">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="7d60c-106">부분</span><span class="sxs-lookup"><span data-stu-id="7d60c-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="7d60c-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-107">Required.</span></span> <span data-ttu-id="7d60c-108">정수 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-108">Integral numeric value.</span></span> <span data-ttu-id="7d60c-109">비트 패턴을 이동한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-109">The result of shifting the bit pattern.</span></span> <span data-ttu-id="7d60c-110">데이터 형식은 `pattern`의 형식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-110">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="7d60c-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7d60c-111">Required.</span></span> <span data-ttu-id="7d60c-112">정수 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-112">Integral numeric expression.</span></span> <span data-ttu-id="7d60c-113">이동할 비트 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-113">The bit pattern to be shifted.</span></span> <span data-ttu-id="7d60c-114">데이터 형식은 정수 계열 형식(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` 또는 `ULong`)이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-114">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="7d60c-115">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7d60c-115">Required.</span></span> <span data-ttu-id="7d60c-116">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-116">Numeric expression.</span></span> <span data-ttu-id="7d60c-117">비트 패턴을 이동할 비트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-117">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="7d60c-118">데이터 형식은 `Integer`이거나 `Integer`로 확장되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-118">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d60c-119">설명</span><span class="sxs-lookup"><span data-stu-id="7d60c-119">Remarks</span></span>  

 <span data-ttu-id="7d60c-120">산술 시프트는 순환 하지 않습니다. 즉, 결과의 한쪽 끝에서 이동 하는 비트가 다른 쪽 끝에서는 다시 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-120">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="7d60c-121">산술 왼쪽 시프트에서 결과 데이터 형식의 범위를 벗어나 이동 하는 비트는 무시 되 고 오른쪽에서 비워진 비트 위치는 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-121">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="7d60c-122">결과에 포함 될 수 있는 것 보다 더 많은 비트로 시프트를 방지 하기 위해 Visual Basic의 `amount` 데이터 형식에 해당 하는 크기 마스크를 사용 하 여의 값을 마스크 합니다 `pattern` .</span><span class="sxs-lookup"><span data-stu-id="7d60c-122">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="7d60c-123">이러한 값의 이진은 이동 양에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-123">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="7d60c-124">크기 마스크는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-124">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="7d60c-125">데이터 형식 `pattern`</span><span class="sxs-lookup"><span data-stu-id="7d60c-125">Data type of `pattern`</span></span>|<span data-ttu-id="7d60c-126">크기 마스크 (10 진수)</span><span class="sxs-lookup"><span data-stu-id="7d60c-126">Size mask (decimal)</span></span>|<span data-ttu-id="7d60c-127">크기 마스크 (16 진수)</span><span class="sxs-lookup"><span data-stu-id="7d60c-127">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="7d60c-128">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="7d60c-128">`SByte`, `Byte`</span></span>|<span data-ttu-id="7d60c-129">7</span><span class="sxs-lookup"><span data-stu-id="7d60c-129">7</span></span>|<span data-ttu-id="7d60c-130">&H00000007</span><span class="sxs-lookup"><span data-stu-id="7d60c-130">&H00000007</span></span>|  
|<span data-ttu-id="7d60c-131">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="7d60c-131">`Short`, `UShort`</span></span>|<span data-ttu-id="7d60c-132">15</span><span class="sxs-lookup"><span data-stu-id="7d60c-132">15</span></span>|<span data-ttu-id="7d60c-133">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="7d60c-133">&H0000000F</span></span>|  
|<span data-ttu-id="7d60c-134">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="7d60c-134">`Integer`, `UInteger`</span></span>|<span data-ttu-id="7d60c-135">31</span><span class="sxs-lookup"><span data-stu-id="7d60c-135">31</span></span>|<span data-ttu-id="7d60c-136">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="7d60c-136">&H0000001F</span></span>|  
|<span data-ttu-id="7d60c-137">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="7d60c-137">`Long`, `ULong`</span></span>|<span data-ttu-id="7d60c-138">63</span><span class="sxs-lookup"><span data-stu-id="7d60c-138">63</span></span>|<span data-ttu-id="7d60c-139">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="7d60c-139">&H0000003F</span></span>|  
  
 <span data-ttu-id="7d60c-140">`amount`가 0 인 경우의 값은 `result` 의 값과 동일 합니다 `pattern` .</span><span class="sxs-lookup"><span data-stu-id="7d60c-140">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="7d60c-141">`amount`가 음수 이면 부호 없는 값으로 사용 되 고 적절 한 크기 마스크로 마스크 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-141">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="7d60c-142">산술 시프트는 오버플로 예외를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-142">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d60c-143">`<<`연산자를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-143">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7d60c-144">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-144">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="7d60c-145">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d60c-145">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d60c-146">예제</span><span class="sxs-lookup"><span data-stu-id="7d60c-146">Example</span></span>  

 <span data-ttu-id="7d60c-147">다음 예에서는 연산자를 사용 `<<` 하 여 정수 값에 대 한 산술 왼쪽 시프트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-147">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="7d60c-148">결과는 항상 이동 하는 식의 데이터 형식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-148">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="7d60c-149">이전 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-149">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="7d60c-150">`result1` 는 192 (0000 0000 1100 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-150">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="7d60c-151">`result2` 는 3072 (0000 1100 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-151">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="7d60c-152">`result3` 는-32768 (1000 0000 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-152">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="7d60c-153">`result4` 는 384 (0000 0001 1000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-153">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="7d60c-154">`result5` 가 0 (왼쪽으로 15 자리 이동)입니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-154">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="7d60c-155">의 이동 금액 `result4` 은 17과 15로 계산 되며 1과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d60c-155">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d60c-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d60c-156">See also</span></span>

- [<span data-ttu-id="7d60c-157">비트 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="7d60c-157">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="7d60c-158">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="7d60c-158">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="7d60c-159"><<= 연산자</span><span class="sxs-lookup"><span data-stu-id="7d60c-159"><<= Operator</span></span>](left-shift-assignment-operator.md)
- [<span data-ttu-id="7d60c-160">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="7d60c-160">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="7d60c-161">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="7d60c-161">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="7d60c-162">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="7d60c-162">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
