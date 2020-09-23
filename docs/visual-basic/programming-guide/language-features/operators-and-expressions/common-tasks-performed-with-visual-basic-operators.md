---
title: Visual Basic 연산자를 사용한 일반적인 작업
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], logical
- operators [Visual Basic], string concatenation
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- operators [Visual Basic], arithmetic
- operators [Visual Basic], string comparison
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- operators [Visual Basic], comparison
- operators [Visual Basic], short-circuiting logical
ms.assetid: d181afe5-fafa-460f-a13b-81203f6f4587
ms.openlocfilehash: a8a8d7898e52077fef47b91172e34ad50d7f54e7
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075215"
---
# <a name="common-tasks-performed-with-visual-basic-operators"></a><span data-ttu-id="a7037-102">Visual Basic 연산자를 사용한 일반적인 작업</span><span class="sxs-lookup"><span data-stu-id="a7037-102">Common Tasks Performed with Visual Basic Operators</span></span>

<span data-ttu-id="a7037-103">연산자는 *피연산자*라는 하나 이상의 식과 관련 된 여러 일반적인 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-103">Operators perform many common tasks involving one or more expressions called *operands*.</span></span>  
  
## <a name="arithmetic-and-bit-shift-tasks"></a><span data-ttu-id="a7037-104">산술 및 비트 시프트 작업</span><span class="sxs-lookup"><span data-stu-id="a7037-104">Arithmetic and Bit-shift Tasks</span></span>  

 <span data-ttu-id="a7037-105">다음 표에는 사용 가능한 산술 및 비트 시프트 연산이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-105">The following table summarizes the available arithmetic and bit-shift operations.</span></span>  
  
|<span data-ttu-id="a7037-106">대상</span><span class="sxs-lookup"><span data-stu-id="a7037-106">To</span></span>|<span data-ttu-id="a7037-107">참조 항목</span><span class="sxs-lookup"><span data-stu-id="a7037-107">See</span></span>|  
|---|---|  
|<span data-ttu-id="a7037-108">한 숫자 값을 다른 숫자 값에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-108">Add one numeric value to another</span></span>|[<span data-ttu-id="a7037-109">+ 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-109">+ Operator</span></span>](../../../language-reference/operators/addition-operator.md)|  
|<span data-ttu-id="a7037-110">다른 숫자 값에서 한 숫자 값을 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-110">Subtract one numeric value from another</span></span>|[<span data-ttu-id="a7037-111">-연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7037-111">- Operator (Visual Basic)</span></span>](../../../language-reference/operators/subtraction-operator.md)|  
|<span data-ttu-id="a7037-112">숫자 값의 부호를 반대로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-112">Reverse the sign of a numeric value</span></span>|[<span data-ttu-id="a7037-113">-연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7037-113">- Operator (Visual Basic)</span></span>](../../../language-reference/operators/subtraction-operator.md)|  
|<span data-ttu-id="a7037-114">한 숫자 값을 다른 숫자 값과 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-114">Multiply one numeric value by another</span></span>|[<span data-ttu-id="a7037-115">\* 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-115">\* Operator</span></span>](../../../language-reference/operators/multiplication-operator.md)|  
|<span data-ttu-id="a7037-116">한 숫자 값을 다른 숫자 값으로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-116">Divide one numeric value into another</span></span>|[<span data-ttu-id="a7037-117">/연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7037-117">/ Operator (Visual Basic)</span></span>](../../../language-reference/operators/floating-point-division-operator.md)|  
|<span data-ttu-id="a7037-118">한 숫자 값을 다른 값으로 나눈 값 (나머지는 제외)을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-118">Find the quotient of one numeric value divided by another (without the remainder)</span></span>|[<span data-ttu-id="a7037-119">\ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7037-119">\ Operator (Visual Basic)</span></span>](../../../language-reference/operators/integer-division-operator.md)|  
|<span data-ttu-id="a7037-120">하나의 숫자 값을 다른 값으로 나눈 나머지 (몫 제외)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-120">Find the remainder of one numeric value divided by another (without the quotient)</span></span>|[<span data-ttu-id="a7037-121">Mod 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-121">Mod Operator</span></span>](../../../language-reference/operators/mod-operator.md)|  
|<span data-ttu-id="a7037-122">한 숫자 값을 다른 숫자 값으로 거듭제곱 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-122">Raise one numeric value to the power of another</span></span>|[<span data-ttu-id="a7037-123">^ 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-123">^ Operator</span></span>](../../../language-reference/operators/exponentiation-operator.md)|  
|<span data-ttu-id="a7037-124">숫자 값의 비트 패턴을 왼쪽으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-124">Shift the bit pattern of a numeric value to the left</span></span>|[<span data-ttu-id="a7037-125"><\< 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-125"><\< Operator</span></span>](../../../language-reference/operators/left-shift-operator.md)|  
|<span data-ttu-id="a7037-126">숫자 값의 비트 패턴을 오른쪽으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-126">Shift the bit pattern of a numeric value to the right</span></span>|[<span data-ttu-id="a7037-127">>> 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-127">>> Operator</span></span>](../../../language-reference/operators/right-shift-operator.md)|  
  
## <a name="comparison-tasks"></a><span data-ttu-id="a7037-128">비교 작업</span><span class="sxs-lookup"><span data-stu-id="a7037-128">Comparison Tasks</span></span>  

 <span data-ttu-id="a7037-129">다음 표에서는 사용 가능한 비교 작업을 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-129">The following table summarizes the available comparison operations.</span></span>  
  
|<span data-ttu-id="a7037-130">대상</span><span class="sxs-lookup"><span data-stu-id="a7037-130">To</span></span>|<span data-ttu-id="a7037-131">참조 항목</span><span class="sxs-lookup"><span data-stu-id="a7037-131">See</span></span>|  
|---|---|  
|<span data-ttu-id="a7037-132">두 값이 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-132">Determine whether two values are equal</span></span>|<span data-ttu-id="a7037-133">`=` 연산자 ([Visual Basic의 비교 연산자](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="a7037-133">`=` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="a7037-134">두 값이 같지 않은지 확인</span><span class="sxs-lookup"><span data-stu-id="a7037-134">Determine whether two values are unequal</span></span>|<span data-ttu-id="a7037-135">`<>` 연산자 ([Visual Basic의 비교 연산자](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="a7037-135">`<>` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="a7037-136">한 값이 다른 값 보다 작지 않은지 확인</span><span class="sxs-lookup"><span data-stu-id="a7037-136">Determine whether one value is less than another</span></span>|<span data-ttu-id="a7037-137">`<` 연산자 ([Visual Basic의 비교 연산자](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="a7037-137">`<` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="a7037-138">한 값이 다른 값 보다 큰지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-138">Determine whether one value is greater than another</span></span>|<span data-ttu-id="a7037-139">`>` 연산자 ([Visual Basic의 비교 연산자](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="a7037-139">`>` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="a7037-140">한 값이 다른 값 보다 작거나 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-140">Determine whether one value is less than or equal to another</span></span>|<span data-ttu-id="a7037-141">`<=` 연산자 ([Visual Basic의 비교 연산자](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="a7037-141">`<=` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="a7037-142">한 값이 다른 값 보다 크거나 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-142">Determine whether one value is greater than or equal to another</span></span>|<span data-ttu-id="a7037-143">`>=` 연산자 ([Visual Basic의 비교 연산자](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="a7037-143">`>=` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="a7037-144">두 개체 변수가 동일한 개체 인스턴스를 참조 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-144">Determine whether two object variables refer to the same object instance</span></span>|[<span data-ttu-id="a7037-145">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-145">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)|  
|<span data-ttu-id="a7037-146">두 개체 변수가 서로 다른 개체 인스턴스를 참조 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-146">Determine whether two object variables refer to different object instances</span></span>|[<span data-ttu-id="a7037-147">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-147">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)|  
|<span data-ttu-id="a7037-148">개체가 특정 형식 인지 확인</span><span class="sxs-lookup"><span data-stu-id="a7037-148">Determine whether an object is of a specific type</span></span>|[<span data-ttu-id="a7037-149">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-149">TypeOf Operator</span></span>](../../../language-reference/operators/typeof-operator.md)|  
  
## <a name="concatenation-tasks"></a><span data-ttu-id="a7037-150">연결 태스크</span><span class="sxs-lookup"><span data-stu-id="a7037-150">Concatenation Tasks</span></span>  

 <span data-ttu-id="a7037-151">다음 표에서는 사용 가능한 연결 작업을 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-151">The following table summarizes the available concatenation operations.</span></span>  
  
|<span data-ttu-id="a7037-152">대상</span><span class="sxs-lookup"><span data-stu-id="a7037-152">To</span></span>|<span data-ttu-id="a7037-153">참조 항목</span><span class="sxs-lookup"><span data-stu-id="a7037-153">See</span></span>|  
|---|---|  
|<span data-ttu-id="a7037-154">여러 문자열을 단일 문자열로 조인</span><span class="sxs-lookup"><span data-stu-id="a7037-154">Join multiple strings into a single string</span></span>|<span data-ttu-id="a7037-155">`&` 연산자 ([Visual Basic의 연결 연산자](concatenation-operators.md))</span><span class="sxs-lookup"><span data-stu-id="a7037-155">`&` Operator ([Concatenation Operators in Visual Basic](concatenation-operators.md))</span></span>|  
|<span data-ttu-id="a7037-156">문자열 값을 사용 하 여 숫자 값 조인</span><span class="sxs-lookup"><span data-stu-id="a7037-156">Join numeric values with string values</span></span>|<span data-ttu-id="a7037-157">`+` 연산자 ([Visual Basic의 연결 연산자](concatenation-operators.md))</span><span class="sxs-lookup"><span data-stu-id="a7037-157">`+` Operator ([Concatenation Operators in Visual Basic](concatenation-operators.md))</span></span>|  
  
## <a name="logical-and-bitwise-tasks"></a><span data-ttu-id="a7037-158">논리적 and 비트 작업</span><span class="sxs-lookup"><span data-stu-id="a7037-158">Logical and Bitwise Tasks</span></span>  

 <span data-ttu-id="a7037-159">다음 표에는 사용 가능한 논리 및 비트 연산이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-159">The following table summarizes the available logical and bitwise operations.</span></span>  
  
|<span data-ttu-id="a7037-160">대상</span><span class="sxs-lookup"><span data-stu-id="a7037-160">To</span></span>|<span data-ttu-id="a7037-161">참조 항목</span><span class="sxs-lookup"><span data-stu-id="a7037-161">See</span></span>|  
|---|---|  
|<span data-ttu-id="a7037-162">부울 값에 논리 부정 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-162">Perform logical negation on a Boolean value</span></span>|[<span data-ttu-id="a7037-163">Not 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-163">Not Operator</span></span>](../../../language-reference/operators/not-operator.md)|  
|<span data-ttu-id="a7037-164">두 부울 값에 대해 논리 결합 수행</span><span class="sxs-lookup"><span data-stu-id="a7037-164">Perform logical conjunction on two Boolean values</span></span>|[<span data-ttu-id="a7037-165">And 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-165">And Operator</span></span>](../../../language-reference/operators/and-operator.md)|  
|<span data-ttu-id="a7037-166">두 부울 값에 대 한 포함 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-166">Perform inclusive logical disjunction on two Boolean values</span></span>|[<span data-ttu-id="a7037-167">Or 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-167">Or Operator</span></span>](../../../language-reference/operators/or-operator.md)|  
|<span data-ttu-id="a7037-168">두 부울 값에 배타적 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-168">Perform exclusive logical disjunction on two Boolean values</span></span>|[<span data-ttu-id="a7037-169">Xor 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-169">Xor Operator</span></span>](../../../language-reference/operators/xor-operator.md)|  
|<span data-ttu-id="a7037-170">두 부울 값에 대 한 짧은 short-circuit 논리 결합을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-170">Perform short-circuited logical conjunction on two Boolean values</span></span>|[<span data-ttu-id="a7037-171">AndAlso 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-171">AndAlso Operator</span></span>](../../../language-reference/operators/andalso-operator.md)|  
|<span data-ttu-id="a7037-172">두 부울 값에 대해 짧은 short-circuit 포함 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-172">Perform short-circuited inclusive logical disjunction on two Boolean values</span></span>|[<span data-ttu-id="a7037-173">OrElse 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-173">OrElse Operator</span></span>](../../../language-reference/operators/orelse-operator.md)|  
|<span data-ttu-id="a7037-174">두 정수 값에 비트 논리 결합 수행</span><span class="sxs-lookup"><span data-stu-id="a7037-174">Perform bit-by-bit logical conjunction on two integral values</span></span>|[<span data-ttu-id="a7037-175">And 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-175">And Operator</span></span>](../../../language-reference/operators/and-operator.md)|  
|<span data-ttu-id="a7037-176">두 정수 값에 비트 단위로 포함 된 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-176">Perform bit-by-bit inclusive logical disjunction on two integral values</span></span>|[<span data-ttu-id="a7037-177">Or 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-177">Or Operator</span></span>](../../../language-reference/operators/or-operator.md)|  
|<span data-ttu-id="a7037-178">두 정수 값에 비트 배타적 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-178">Perform bit-by-bit exclusive logical disjunction on two integral values</span></span>|[<span data-ttu-id="a7037-179">Xor 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-179">Xor Operator</span></span>](../../../language-reference/operators/xor-operator.md)|  
|<span data-ttu-id="a7037-180">정수 계열 값에 비트 논리 부정 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7037-180">Perform bit-by-bit logical negation on an integral value</span></span>|[<span data-ttu-id="a7037-181">Not 연산자</span><span class="sxs-lookup"><span data-stu-id="a7037-181">Not Operator</span></span>](../../../language-reference/operators/not-operator.md)|  
  
## <a name="see-also"></a><span data-ttu-id="a7037-182">참조</span><span class="sxs-lookup"><span data-stu-id="a7037-182">See also</span></span>

- [<span data-ttu-id="a7037-183">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="a7037-183">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="a7037-184">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="a7037-184">Operators Listed by Functionality</span></span>](../../../language-reference/operators/operators-listed-by-functionality.md)
