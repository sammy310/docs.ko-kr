---
title: '\ 연산자'
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: 2b4cca99ed54195162530bb8eb950bd251bfbff9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347113"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="4fabe-102">\ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fabe-102">\ Operator (Visual Basic)</span></span>
<span data-ttu-id="4fabe-103">두 숫자를 나누고 정수 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fabe-104">구문</span><span class="sxs-lookup"><span data-stu-id="4fabe-104">Syntax</span></span>  
  
```vb  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="4fabe-105">요소</span><span class="sxs-lookup"><span data-stu-id="4fabe-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="4fabe-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-106">Required.</span></span> <span data-ttu-id="4fabe-107">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="4fabe-108">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-108">Required.</span></span> <span data-ttu-id="4fabe-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="4fabe-110">지원 형식</span><span class="sxs-lookup"><span data-stu-id="4fabe-110">Supported Types</span></span>  
 <span data-ttu-id="4fabe-111">부호 없는 형식 및 부동 소수점 형식 및 `Decimal`을 포함 한 모든 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="4fabe-112">결과</span><span class="sxs-lookup"><span data-stu-id="4fabe-112">Result</span></span>  
 <span data-ttu-id="4fabe-113">결과는 `expression2`으로 나눈 `expression1`의 정수 몫으로, 나머지는 무시 하 고 정수 부분만 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="4fabe-114">이를 *잘림*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="4fabe-115">결과 데이터 형식은 `expression1` 및 `expression2`데이터 형식에 적합 한 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="4fabe-116">[연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)에서 "정수 산술 연산" 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4fabe-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="4fabe-117">[/연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) 는 나머지를 소수 부분으로 유지 하는 전체 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-117">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fabe-118">주의</span><span class="sxs-lookup"><span data-stu-id="4fabe-118">Remarks</span></span>  
 <span data-ttu-id="4fabe-119">나누기를 수행 하기 전에 Visual Basic 부동 소수점 숫자 식을 `Long`변환 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="4fabe-120">`Option Strict` `On`이면 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="4fabe-121">이 `Option Strict` 인 `Off` 경우, 값이 <xref:System.OverflowException>Long 데이터 형식[의 범위를 벗어나면](../../../visual-basic/language-reference/data-types/long-data-type.md)이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md).</span></span> <span data-ttu-id="4fabe-122">`Long`로의 변환에도 *은행원의 반올림*이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="4fabe-123">자세한 내용은 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)에서 "소수 부분"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4fabe-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="4fabe-124">`expression1` 또는 `expression2`가 [Nothing](../../../visual-basic/language-reference/nothing.md)으로 평가 되 면 0으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-124">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="4fabe-125">0으로 나누기 시도</span><span class="sxs-lookup"><span data-stu-id="4fabe-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="4fabe-126">`expression2` 0으로 계산 되 면 `\` 연산자는 <xref:System.DivideByZeroException> 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="4fabe-127">피연산자의 모든 숫자 데이터 형식에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4fabe-128">`\` 연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4fabe-129">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="4fabe-130">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fabe-130">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fabe-131">예제</span><span class="sxs-lookup"><span data-stu-id="4fabe-131">Example</span></span>  
 <span data-ttu-id="4fabe-132">다음 예에서는 `\` 연산자를 사용 하 여 정수 나누기를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="4fabe-133">결과는 두 피연산자의 정수 몫을 나타내며 나머지는 삭제 된 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 <span data-ttu-id="4fabe-134">앞의 예제에서 식은 각각 2, 3, 33 및-22의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fabe-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fabe-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fabe-135">See also</span></span>

- [<span data-ttu-id="4fabe-136">\\= 연산자</span><span class="sxs-lookup"><span data-stu-id="4fabe-136">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="4fabe-137">/연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fabe-137">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="4fabe-138">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="4fabe-138">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="4fabe-139">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="4fabe-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="4fabe-140">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="4fabe-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="4fabe-141">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="4fabe-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="4fabe-142">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="4fabe-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
