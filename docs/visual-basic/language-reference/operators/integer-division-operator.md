---
title: '\ 연산자(Visual Basic)'
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
ms.openlocfilehash: 1753199e2ecf3f156b90d8c0a5cacd672397260d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828706"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="419c1-102">\ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="419c1-102">\ Operator (Visual Basic)</span></span>
<span data-ttu-id="419c1-103">두 숫자를 나누고 정수 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="419c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="419c1-104">Syntax</span></span>  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="419c1-105">요소</span><span class="sxs-lookup"><span data-stu-id="419c1-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="419c1-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="419c1-106">Required.</span></span> <span data-ttu-id="419c1-107">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="419c1-108">필수.</span><span class="sxs-lookup"><span data-stu-id="419c1-108">Required.</span></span> <span data-ttu-id="419c1-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="419c1-110">지원 형식</span><span class="sxs-lookup"><span data-stu-id="419c1-110">Supported Types</span></span>  
 <span data-ttu-id="419c1-111">모든 숫자 형식, 부동 소수점 및 부호 없는 형식을 포함 하 고 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="419c1-112">결과</span><span class="sxs-lookup"><span data-stu-id="419c1-112">Result</span></span>  
 <span data-ttu-id="419c1-113">결과의 정수 몫입니다 `expression1` 나눈 `expression2`, 나머지는 버리고 정수 부분만 남긴 합니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="419c1-114">이 이라고 *잘림*합니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="419c1-115">결과 데이터 형식은 데이터 유형에 대 한 적절 한 숫자 형식 `expression1` 고 `expression2`입니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="419c1-116">"정수 산술" 표를 참조 하십시오 [연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="419c1-117">합니다 [/ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) 나머지 소수 부분을를 유지 하는 전체 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-117">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="419c1-118">설명</span><span class="sxs-lookup"><span data-stu-id="419c1-118">Remarks</span></span>  
 <span data-ttu-id="419c1-119">나누기를 수행 하기 전에 Visual Basic 모든 부동 소수점 숫자 식으로 변환 하려고 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="419c1-120">하는 경우 `Option Strict` 는 `On`, 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="419c1-121">경우 `Option Strict` 됩니다 `Off`, <xref:System.OverflowException> 값의 범위를 벗어난 경우 가능 합니다 [Long 데이터 형식](../../../visual-basic/language-reference/data-types/long-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md).</span></span> <span data-ttu-id="419c1-122">변환할 `Long` 적용할 이기도 *은행원의 반올림*합니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="419c1-123">자세한 내용은 "소수 부분이"를 참조 하세요 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="419c1-124">하는 경우 `expression1` 또는 `expression2` 로 [Nothing](../../../visual-basic/language-reference/nothing.md)를 0으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-124">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="419c1-125">0으로 나누기</span><span class="sxs-lookup"><span data-stu-id="419c1-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="419c1-126">하는 경우 `expression2` 0으로 계산 되는 `\` 연산자 throw를 <xref:System.DivideByZeroException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="419c1-127">모든 숫자 데이터 형식의 피연산자에 대 한 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="419c1-128">합니다 `\` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우.</span><span class="sxs-lookup"><span data-stu-id="419c1-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="419c1-129">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="419c1-130">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="419c1-130">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="419c1-131">예제</span><span class="sxs-lookup"><span data-stu-id="419c1-131">Example</span></span>  
 <span data-ttu-id="419c1-132">다음 예제에서는 `\` 정수 나누기를 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="419c1-133">결과 나머지 삭제는 두 피연산자의 몫을 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 <span data-ttu-id="419c1-134">식 앞의 예제에서는 각각 2, 3, 33으로,-22의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="419c1-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="419c1-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="419c1-135">See also</span></span>

- [<span data-ttu-id="419c1-136">\\= 연산자</span><span class="sxs-lookup"><span data-stu-id="419c1-136">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="419c1-137">/ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="419c1-137">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="419c1-138">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="419c1-138">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="419c1-139">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="419c1-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="419c1-140">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="419c1-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="419c1-141">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="419c1-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="419c1-142">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="419c1-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
