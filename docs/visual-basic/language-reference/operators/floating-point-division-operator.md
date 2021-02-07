---
description: :/연산자 (Visual Basic)에 대해 자세히 알아보세요.
title: / 연산자
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
ms.openlocfilehash: 717c8fdc6abae02de555040a3aadb92fed2bfbee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666006"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="bf6d4-103">/ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf6d4-103">/ Operator (Visual Basic)</span></span>

<span data-ttu-id="bf6d4-104">두 숫자를 나누고 부동 소수점 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-104">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf6d4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf6d4-105">Syntax</span></span>  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="bf6d4-106">부분</span><span class="sxs-lookup"><span data-stu-id="bf6d4-106">Parts</span></span>  

 `expression1`  
 <span data-ttu-id="bf6d4-107">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-107">Required.</span></span> <span data-ttu-id="bf6d4-108">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-108">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="bf6d4-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-109">Required.</span></span> <span data-ttu-id="bf6d4-110">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-110">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="bf6d4-111">지원 형식</span><span class="sxs-lookup"><span data-stu-id="bf6d4-111">Supported Types</span></span>  

 <span data-ttu-id="bf6d4-112">부호 없는 형식 및 부동 소수점 형식 및를 포함 하는 모든 숫자 형식 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-112">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="bf6d4-113">결과</span><span class="sxs-lookup"><span data-stu-id="bf6d4-113">Result</span></span>  

 <span data-ttu-id="bf6d4-114">그 결과는 `expression1` 나머지를 포함 하 여로 나눈 전체 몫입니다 `expression2` .</span><span class="sxs-lookup"><span data-stu-id="bf6d4-114">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="bf6d4-115">[\ 연산자 (Visual Basic)](integer-division-operator.md) 는 나머지를 삭제 하는 정수 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-115">The [\ Operator (Visual Basic)](integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf6d4-116">설명</span><span class="sxs-lookup"><span data-stu-id="bf6d4-116">Remarks</span></span>  

 <span data-ttu-id="bf6d4-117">결과의 데이터 형식은 피연산자의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="bf6d4-118">다음 표에서는 결과의 데이터 형식을 결정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="bf6d4-119">피연산자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bf6d4-119">Operand data types</span></span>|<span data-ttu-id="bf6d4-120">Result 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bf6d4-120">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="bf6d4-121">두 식은 모두 정수 데이터 형식 ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))입니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-121">Both expressions are integral data types ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="bf6d4-122">한 식은 [단일](../data-types/single-data-type.md) 데이터 형식이 고 다른 하나는 [Double](../data-types/double-data-type.md) 이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-122">One expression is a [Single](../data-types/single-data-type.md) data type and the other is not a [Double](../data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="bf6d4-123">한 식은 [Decimal](../data-types/decimal-data-type.md) 데이터 형식이 고 다른 하나는 [단일](../data-types/single-data-type.md) 또는 [Double](../data-types/double-data-type.md) 이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-123">One expression is a [Decimal](../data-types/decimal-data-type.md) data type and the other is not a [Single](../data-types/single-data-type.md) or a [Double](../data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="bf6d4-124">두 식이 모두 [Double](../data-types/double-data-type.md) 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-124">Either expression is a [Double](../data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="bf6d4-125">나누기를 수행 하기 전에 정수 계열 숫자 식이로 확장 됩니다 `Double` .</span><span class="sxs-lookup"><span data-stu-id="bf6d4-125">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="bf6d4-126">정수 계열 데이터 형식에 결과를 할당 하는 경우 Visual Basic 결과를 해당 형식으로 변환 하려고 시도 합니다 `Double` .</span><span class="sxs-lookup"><span data-stu-id="bf6d4-126">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="bf6d4-127">결과가 해당 형식에 맞지 않는 경우 예외를 throw 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-127">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="bf6d4-128">특히이 도움말 페이지의 "0으로 나누기 시도"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-128">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="bf6d4-129">`expression1`또는가 `expression2` [Nothing](../nothing.md)으로 계산 되 면 0으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-129">If `expression1` or `expression2` evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="bf6d4-130">0으로 나누기 시도</span><span class="sxs-lookup"><span data-stu-id="bf6d4-130">Attempted Division by Zero</span></span>  

 <span data-ttu-id="bf6d4-131">가 `expression2` 0으로 계산 되는 경우 `/` 연산자는 피연산자 데이터 형식에 따라 다르게 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-131">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="bf6d4-132">다음 표에서는 가능한 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-132">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="bf6d4-133">피연산자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bf6d4-133">Operand data types</span></span>|<span data-ttu-id="bf6d4-134">`expression2`가 0 인 경우의 동작</span><span class="sxs-lookup"><span data-stu-id="bf6d4-134">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="bf6d4-135">부동 소수점 ( `Single` 또는 `Double` )</span><span class="sxs-lookup"><span data-stu-id="bf6d4-135">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="bf6d4-136"><xref:System.Double.PositiveInfinity>가 0 인 경우 infinity (또는 <xref:System.Double.NegativeInfinity> ) 또는 <xref:System.Double.NaN> (숫자가 아님) `expression1` 을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-136">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="bf6d4-137">되거나 <xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="bf6d4-137">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="bf6d4-138">정수 (부호 있음 또는 부호 없음)</span><span class="sxs-lookup"><span data-stu-id="bf6d4-138">Integral (signed or unsigned)</span></span>|<span data-ttu-id="bf6d4-139"><xref:System.OverflowException>정수 계열 형식 <xref:System.Double.PositiveInfinity> 에서, 또는를 사용할 수 없으므로 정수 계열 형식으로 다시 변환 하려고 시도 했습니다. <xref:System.Double.NegativeInfinity><xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="bf6d4-139">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
> <span data-ttu-id="bf6d4-140">`/`연산자를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-140">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="bf6d4-141">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-141">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="bf6d4-142">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-142">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf6d4-143">예제</span><span class="sxs-lookup"><span data-stu-id="bf6d4-143">Example</span></span>  

 <span data-ttu-id="bf6d4-144">이 예제에서는 연산자를 사용 `/` 하 여 부동 소수점 나누기를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-144">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="bf6d4-145">결과는 두 피연산자의 몫입니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-145">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 <span data-ttu-id="bf6d4-146">위의 예제에서 식은 2.5 및 3.333333의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-146">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="bf6d4-147">`Double`두 피연산자가 모두 정수 상수인 경우에도 결과는 항상 부동 소수점 ()입니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d4-147">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf6d4-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf6d4-148">See also</span></span>

- [<span data-ttu-id="bf6d4-149">/= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf6d4-149">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="bf6d4-150">\ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf6d4-150">\ Operator (Visual Basic)</span></span>](integer-division-operator.md)
- [<span data-ttu-id="bf6d4-151">연산자 결과의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bf6d4-151">Data Types of Operator Results</span></span>](data-types-of-operator-results.md)
- [<span data-ttu-id="bf6d4-152">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="bf6d4-152">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="bf6d4-153">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="bf6d4-153">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="bf6d4-154">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="bf6d4-154">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="bf6d4-155">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="bf6d4-155">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
