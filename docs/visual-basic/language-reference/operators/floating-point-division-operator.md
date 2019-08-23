---
title: / 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: d30d871d48bc87e050a072cd01a38065be20616c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933269"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="88f06-102">/ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88f06-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="88f06-103">두 숫자를 나누고 부동 소수점 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88f06-104">구문</span><span class="sxs-lookup"><span data-stu-id="88f06-104">Syntax</span></span>  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="88f06-105">요소</span><span class="sxs-lookup"><span data-stu-id="88f06-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="88f06-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="88f06-106">Required.</span></span> <span data-ttu-id="88f06-107">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="88f06-108">필수.</span><span class="sxs-lookup"><span data-stu-id="88f06-108">Required.</span></span> <span data-ttu-id="88f06-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="88f06-110">지원 형식</span><span class="sxs-lookup"><span data-stu-id="88f06-110">Supported Types</span></span>  
 <span data-ttu-id="88f06-111">부호 없는 형식 및 부동 소수점 형식 및 `Decimal`를 포함 하는 모든 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="88f06-112">결과</span><span class="sxs-lookup"><span data-stu-id="88f06-112">Result</span></span>  
 <span data-ttu-id="88f06-113">그 결과는 나머지를 포함 하 `expression1` 여로 `expression2`나눈 전체 몫입니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="88f06-114">[\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) 는 나머지를 삭제 하는 정수 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88f06-115">설명</span><span class="sxs-lookup"><span data-stu-id="88f06-115">Remarks</span></span>  
 <span data-ttu-id="88f06-116">결과의 데이터 형식은 피연산자의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="88f06-117">다음 표에서는 결과의 데이터 형식을 결정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="88f06-118">피연산자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="88f06-118">Operand data types</span></span>|<span data-ttu-id="88f06-119">Result 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="88f06-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="88f06-120">두 식은 모두 정수 데이터 형식 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))입니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="88f06-121">한 식은 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) 데이터 형식이 고 다른 하나는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) 이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="88f06-122">한 식은 [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) 데이터 형식이 고 다른 하나는 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) 또는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) 이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="88f06-123">두 식이 모두 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="88f06-124">나누기를 수행 하기 전에 정수 계열 숫자 식이로 `Double`확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="88f06-125">정수 계열 데이터 형식에 결과를 할당 하는 경우 Visual Basic 결과 `Double` 를 해당 형식으로 변환 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="88f06-126">결과가 해당 형식에 맞지 않는 경우 예외를 throw 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="88f06-127">특히이 도움말 페이지의 "0으로 나누기 시도"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="88f06-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="88f06-128">또는 `expression1` 가`expression2` [Nothing](../../../visual-basic/language-reference/nothing.md)으로 계산 되 면 0으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="88f06-129">0으로 나누기 시도</span><span class="sxs-lookup"><span data-stu-id="88f06-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="88f06-130">가 `expression2` 0으로 계산 되는 `/` 경우 연산자는 피연산자 데이터 형식에 따라 다르게 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="88f06-131">다음 표에서는 가능한 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="88f06-132">피연산자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="88f06-132">Operand data types</span></span>|<span data-ttu-id="88f06-133">가 0 `expression2` 인 경우의 동작</span><span class="sxs-lookup"><span data-stu-id="88f06-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="88f06-134">부동 소수점 (`Single` 또는 `Double`)</span><span class="sxs-lookup"><span data-stu-id="88f06-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="88f06-135">가 0 인<xref:System.Double.PositiveInfinity> 경우 <xref:System.Double.NaN> <xref:System.Double.NegativeInfinity> infinity`expression1` (또는) 또는 (숫자가 아님)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="88f06-136">되거나<xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="88f06-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="88f06-137">정수 (부호 있음 또는 부호 없음)</span><span class="sxs-lookup"><span data-stu-id="88f06-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="88f06-138">정수 계열 형식에서, <xref:System.OverflowException> <xref:System.Double.NegativeInfinity>또는를 사용할 <xref:System.Double.PositiveInfinity>수 없으므로 정수 계열 형식으로 다시 변환 하려고 시도 했습니다.<xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="88f06-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
> <span data-ttu-id="88f06-139">연산자를 오버 로드할 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. `/`</span><span class="sxs-lookup"><span data-stu-id="88f06-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="88f06-140">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="88f06-141">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88f06-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="88f06-142">예제</span><span class="sxs-lookup"><span data-stu-id="88f06-142">Example</span></span>  
 <span data-ttu-id="88f06-143">이 예제에서는 `/` 연산자를 사용 하 여 부동 소수점 나누기를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="88f06-144">결과는 두 피연산자의 몫입니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 <span data-ttu-id="88f06-145">위의 예제에서 식은 2.5 및 3.333333의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="88f06-146">두 피연산자가 모두 정수 상수인 경우에도 결과`Double`는 항상 부동 소수점 ()입니다.</span><span class="sxs-lookup"><span data-stu-id="88f06-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88f06-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="88f06-147">See also</span></span>

- [<span data-ttu-id="88f06-148">/= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88f06-148">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="88f06-149">\ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88f06-149">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="88f06-150">연산자 결과의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="88f06-150">Data Types of Operator Results</span></span>](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [<span data-ttu-id="88f06-151">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="88f06-151">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="88f06-152">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="88f06-152">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="88f06-153">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="88f06-153">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="88f06-154">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="88f06-154">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
