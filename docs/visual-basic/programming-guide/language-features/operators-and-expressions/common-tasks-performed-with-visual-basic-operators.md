---
description: '자세한 정보: Visual Basic 연산자를 사용 하 여 수행 되는 일반 작업'
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
ms.openlocfilehash: 5103241c7c92ffe7264178e9abb6a56ba03d4b52
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100465264"
---
# <a name="common-tasks-performed-with-visual-basic-operators"></a><span data-ttu-id="06303-103">Visual Basic 연산자를 사용한 일반적인 작업</span><span class="sxs-lookup"><span data-stu-id="06303-103">Common Tasks Performed with Visual Basic Operators</span></span>

<span data-ttu-id="06303-104">연산자는 *피연산자* 라는 하나 이상의 식과 관련 된 여러 일반적인 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-104">Operators perform many common tasks involving one or more expressions called *operands*.</span></span>  
  
## <a name="arithmetic-and-bit-shift-tasks"></a><span data-ttu-id="06303-105">산술 및 비트 시프트 작업</span><span class="sxs-lookup"><span data-stu-id="06303-105">Arithmetic and Bit-shift Tasks</span></span>  

 <span data-ttu-id="06303-106">다음 표에는 사용 가능한 산술 및 비트 시프트 연산이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06303-106">The following table summarizes the available arithmetic and bit-shift operations.</span></span>  
  
|<span data-ttu-id="06303-107">대상</span><span class="sxs-lookup"><span data-stu-id="06303-107">To</span></span>|<span data-ttu-id="06303-108">참조 항목</span><span class="sxs-lookup"><span data-stu-id="06303-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="06303-109">한 숫자 값을 다른 숫자 값에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-109">Add one numeric value to another</span></span>|[<span data-ttu-id="06303-110">+ 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-110">+ Operator</span></span>](../../../language-reference/operators/addition-operator.md)|  
|<span data-ttu-id="06303-111">다른 숫자 값에서 한 숫자 값을 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="06303-111">Subtract one numeric value from another</span></span>|[<span data-ttu-id="06303-112">- 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06303-112">- Operator (Visual Basic)</span></span>](../../../language-reference/operators/subtraction-operator.md)|  
|<span data-ttu-id="06303-113">숫자 값의 부호를 반대로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="06303-113">Reverse the sign of a numeric value</span></span>|[<span data-ttu-id="06303-114">- 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06303-114">- Operator (Visual Basic)</span></span>](../../../language-reference/operators/subtraction-operator.md)|  
|<span data-ttu-id="06303-115">한 숫자 값을 다른 숫자 값과 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-115">Multiply one numeric value by another</span></span>|[<span data-ttu-id="06303-116">\* 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-116">\* Operator</span></span>](../../../language-reference/operators/multiplication-operator.md)|  
|<span data-ttu-id="06303-117">한 숫자 값을 다른 숫자 값으로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="06303-117">Divide one numeric value into another</span></span>|[<span data-ttu-id="06303-118">/연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06303-118">/ Operator (Visual Basic)</span></span>](../../../language-reference/operators/floating-point-division-operator.md)|  
|<span data-ttu-id="06303-119">한 숫자 값을 다른 값으로 나눈 값 (나머지는 제외)을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="06303-119">Find the quotient of one numeric value divided by another (without the remainder)</span></span>|[<span data-ttu-id="06303-120">\ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06303-120">\ Operator (Visual Basic)</span></span>](../../../language-reference/operators/integer-division-operator.md)|  
|<span data-ttu-id="06303-121">하나의 숫자 값을 다른 값으로 나눈 나머지 (몫 제외)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="06303-121">Find the remainder of one numeric value divided by another (without the quotient)</span></span>|[<span data-ttu-id="06303-122">Mod 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-122">Mod Operator</span></span>](../../../language-reference/operators/mod-operator.md)|  
|<span data-ttu-id="06303-123">한 숫자 값을 다른 숫자 값으로 거듭제곱 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-123">Raise one numeric value to the power of another</span></span>|[<span data-ttu-id="06303-124">^ 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-124">^ Operator</span></span>](../../../language-reference/operators/exponentiation-operator.md)|  
|<span data-ttu-id="06303-125">숫자 값의 비트 패턴을 왼쪽으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-125">Shift the bit pattern of a numeric value to the left</span></span>|[<span data-ttu-id="06303-126"><\< 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-126"><\< Operator</span></span>](../../../language-reference/operators/left-shift-operator.md)|  
|<span data-ttu-id="06303-127">숫자 값의 비트 패턴을 오른쪽으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-127">Shift the bit pattern of a numeric value to the right</span></span>|[<span data-ttu-id="06303-128">>> 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-128">>> Operator</span></span>](../../../language-reference/operators/right-shift-operator.md)|  
  
## <a name="comparison-tasks"></a><span data-ttu-id="06303-129">비교 작업</span><span class="sxs-lookup"><span data-stu-id="06303-129">Comparison Tasks</span></span>  

 <span data-ttu-id="06303-130">다음 표에서는 사용 가능한 비교 작업을 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-130">The following table summarizes the available comparison operations.</span></span>  
  
|<span data-ttu-id="06303-131">대상</span><span class="sxs-lookup"><span data-stu-id="06303-131">To</span></span>|<span data-ttu-id="06303-132">참조 항목</span><span class="sxs-lookup"><span data-stu-id="06303-132">See</span></span>|  
|---|---|  
|<span data-ttu-id="06303-133">두 값이 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-133">Determine whether two values are equal</span></span>|<span data-ttu-id="06303-134">`=` 연산자 ([Visual Basic의 비교 연산자](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="06303-134">`=` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="06303-135">두 값이 같지 않은지 확인</span><span class="sxs-lookup"><span data-stu-id="06303-135">Determine whether two values are unequal</span></span>|<span data-ttu-id="06303-136">`<>` 연산자 ([Visual Basic의 비교 연산자](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="06303-136">`<>` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="06303-137">한 값이 다른 값 보다 작지 않은지 확인</span><span class="sxs-lookup"><span data-stu-id="06303-137">Determine whether one value is less than another</span></span>|<span data-ttu-id="06303-138">`<` 연산자 ([Visual Basic의 비교 연산자](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="06303-138">`<` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="06303-139">한 값이 다른 값 보다 큰지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-139">Determine whether one value is greater than another</span></span>|<span data-ttu-id="06303-140">`>` 연산자 ([Visual Basic의 비교 연산자](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="06303-140">`>` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="06303-141">한 값이 다른 값 보다 작거나 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-141">Determine whether one value is less than or equal to another</span></span>|<span data-ttu-id="06303-142">`<=` 연산자 ([Visual Basic의 비교 연산자](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="06303-142">`<=` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="06303-143">한 값이 다른 값 보다 크거나 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-143">Determine whether one value is greater than or equal to another</span></span>|<span data-ttu-id="06303-144">`>=` 연산자 ([Visual Basic의 비교 연산자](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="06303-144">`>=` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="06303-145">두 개체 변수가 동일한 개체 인스턴스를 참조 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-145">Determine whether two object variables refer to the same object instance</span></span>|[<span data-ttu-id="06303-146">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-146">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)|  
|<span data-ttu-id="06303-147">두 개체 변수가 서로 다른 개체 인스턴스를 참조 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-147">Determine whether two object variables refer to different object instances</span></span>|[<span data-ttu-id="06303-148">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-148">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)|  
|<span data-ttu-id="06303-149">개체가 특정 형식 인지 확인</span><span class="sxs-lookup"><span data-stu-id="06303-149">Determine whether an object is of a specific type</span></span>|[<span data-ttu-id="06303-150">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-150">TypeOf Operator</span></span>](../../../language-reference/operators/typeof-operator.md)|  
  
## <a name="concatenation-tasks"></a><span data-ttu-id="06303-151">연결 태스크</span><span class="sxs-lookup"><span data-stu-id="06303-151">Concatenation Tasks</span></span>  

 <span data-ttu-id="06303-152">다음 표에서는 사용 가능한 연결 작업을 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-152">The following table summarizes the available concatenation operations.</span></span>  
  
|<span data-ttu-id="06303-153">대상</span><span class="sxs-lookup"><span data-stu-id="06303-153">To</span></span>|<span data-ttu-id="06303-154">참조 항목</span><span class="sxs-lookup"><span data-stu-id="06303-154">See</span></span>|  
|---|---|  
|<span data-ttu-id="06303-155">여러 문자열을 단일 문자열로 조인</span><span class="sxs-lookup"><span data-stu-id="06303-155">Join multiple strings into a single string</span></span>|<span data-ttu-id="06303-156">`&` 연산자 ([Visual Basic의 연결 연산자](concatenation-operators.md))</span><span class="sxs-lookup"><span data-stu-id="06303-156">`&` Operator ([Concatenation Operators in Visual Basic](concatenation-operators.md))</span></span>|  
|<span data-ttu-id="06303-157">문자열 값을 사용 하 여 숫자 값 조인</span><span class="sxs-lookup"><span data-stu-id="06303-157">Join numeric values with string values</span></span>|<span data-ttu-id="06303-158">`+` 연산자 ([Visual Basic의 연결 연산자](concatenation-operators.md))</span><span class="sxs-lookup"><span data-stu-id="06303-158">`+` Operator ([Concatenation Operators in Visual Basic](concatenation-operators.md))</span></span>|  
  
## <a name="logical-and-bitwise-tasks"></a><span data-ttu-id="06303-159">논리적 and 비트 작업</span><span class="sxs-lookup"><span data-stu-id="06303-159">Logical and Bitwise Tasks</span></span>  

 <span data-ttu-id="06303-160">다음 표에는 사용 가능한 논리 및 비트 연산이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06303-160">The following table summarizes the available logical and bitwise operations.</span></span>  
  
|<span data-ttu-id="06303-161">대상</span><span class="sxs-lookup"><span data-stu-id="06303-161">To</span></span>|<span data-ttu-id="06303-162">참조 항목</span><span class="sxs-lookup"><span data-stu-id="06303-162">See</span></span>|  
|---|---|  
|<span data-ttu-id="06303-163">부울 값에 논리 부정 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-163">Perform logical negation on a Boolean value</span></span>|[<span data-ttu-id="06303-164">Not 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-164">Not Operator</span></span>](../../../language-reference/operators/not-operator.md)|  
|<span data-ttu-id="06303-165">두 부울 값에 대해 논리 결합 수행</span><span class="sxs-lookup"><span data-stu-id="06303-165">Perform logical conjunction on two Boolean values</span></span>|[<span data-ttu-id="06303-166">And 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-166">And Operator</span></span>](../../../language-reference/operators/and-operator.md)|  
|<span data-ttu-id="06303-167">두 부울 값에 대 한 포함 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-167">Perform inclusive logical disjunction on two Boolean values</span></span>|[<span data-ttu-id="06303-168">Or 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-168">Or Operator</span></span>](../../../language-reference/operators/or-operator.md)|  
|<span data-ttu-id="06303-169">두 부울 값에 배타적 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-169">Perform exclusive logical disjunction on two Boolean values</span></span>|[<span data-ttu-id="06303-170">Xor 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-170">Xor Operator</span></span>](../../../language-reference/operators/xor-operator.md)|  
|<span data-ttu-id="06303-171">두 부울 값에 대 한 짧은 short-circuit 논리 결합을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-171">Perform short-circuited logical conjunction on two Boolean values</span></span>|[<span data-ttu-id="06303-172">AndAlso 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-172">AndAlso Operator</span></span>](../../../language-reference/operators/andalso-operator.md)|  
|<span data-ttu-id="06303-173">두 부울 값에 대해 짧은 short-circuit 포함 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-173">Perform short-circuited inclusive logical disjunction on two Boolean values</span></span>|[<span data-ttu-id="06303-174">OrElse 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-174">OrElse Operator</span></span>](../../../language-reference/operators/orelse-operator.md)|  
|<span data-ttu-id="06303-175">두 정수 값에 비트 논리 결합 수행</span><span class="sxs-lookup"><span data-stu-id="06303-175">Perform bit-by-bit logical conjunction on two integral values</span></span>|[<span data-ttu-id="06303-176">And 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-176">And Operator</span></span>](../../../language-reference/operators/and-operator.md)|  
|<span data-ttu-id="06303-177">두 정수 값에 비트 단위로 포함 된 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-177">Perform bit-by-bit inclusive logical disjunction on two integral values</span></span>|[<span data-ttu-id="06303-178">Or 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-178">Or Operator</span></span>](../../../language-reference/operators/or-operator.md)|  
|<span data-ttu-id="06303-179">두 정수 값에 비트 배타적 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-179">Perform bit-by-bit exclusive logical disjunction on two integral values</span></span>|[<span data-ttu-id="06303-180">Xor 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-180">Xor Operator</span></span>](../../../language-reference/operators/xor-operator.md)|  
|<span data-ttu-id="06303-181">정수 계열 값에 비트 논리 부정 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="06303-181">Perform bit-by-bit logical negation on an integral value</span></span>|[<span data-ttu-id="06303-182">Not 연산자</span><span class="sxs-lookup"><span data-stu-id="06303-182">Not Operator</span></span>](../../../language-reference/operators/not-operator.md)|  
  
## <a name="see-also"></a><span data-ttu-id="06303-183">추가 정보</span><span class="sxs-lookup"><span data-stu-id="06303-183">See also</span></span>

- [<span data-ttu-id="06303-184">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="06303-184">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="06303-185">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="06303-185">Operators Listed by Functionality</span></span>](../../../language-reference/operators/operators-listed-by-functionality.md)
