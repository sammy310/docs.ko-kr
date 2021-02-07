---
description: '자세한 정보: 연산자 (Visual Basic)'
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
ms.openlocfilehash: e15a630d37e423b7a7d0040e495f2543889f37b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665785"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a91da-103">\ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a91da-103">\ Operator (Visual Basic)</span></span>

<span data-ttu-id="a91da-104">두 숫자를 나누고 정수 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-104">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a91da-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a91da-105">Syntax</span></span>  
  
```vb  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="a91da-106">부분</span><span class="sxs-lookup"><span data-stu-id="a91da-106">Parts</span></span>  

 `expression1`  
 <span data-ttu-id="a91da-107">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a91da-107">Required.</span></span> <span data-ttu-id="a91da-108">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-108">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="a91da-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a91da-109">Required.</span></span> <span data-ttu-id="a91da-110">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-110">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="a91da-111">지원 형식</span><span class="sxs-lookup"><span data-stu-id="a91da-111">Supported Types</span></span>  

 <span data-ttu-id="a91da-112">부호 없는 형식 및 부동 소수점 형식 및를 포함 하는 모든 숫자 형식 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-112">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="a91da-113">결과</span><span class="sxs-lookup"><span data-stu-id="a91da-113">Result</span></span>  

 <span data-ttu-id="a91da-114">결과는로 나눈 정수 몫으로 `expression1` `expression2` , 나머지는 무시 하 고 정수 부분만 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-114">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="a91da-115">이를 *잘림* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-115">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="a91da-116">결과 데이터 형식은 및의 데이터 형식에 적합 한 숫자 형식입니다 `expression1` `expression2` .</span><span class="sxs-lookup"><span data-stu-id="a91da-116">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="a91da-117">[연산자 결과의 데이터 형식](data-types-of-operator-results.md)에서 "정수 산술 연산" 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a91da-117">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="a91da-118">[/연산자 (Visual Basic)](floating-point-division-operator.md) 는 나머지를 소수 부분으로 유지 하는 전체 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-118">The [/ Operator (Visual Basic)](floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a91da-119">설명</span><span class="sxs-lookup"><span data-stu-id="a91da-119">Remarks</span></span>  

 <span data-ttu-id="a91da-120">나누기를 수행 하기 전에 Visual Basic 부동 소수점 숫자 식을로 변환 하려고 `Long` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-120">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="a91da-121">`Option Strict`가 이면 `On` 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-121">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="a91da-122">이 `Option Strict` 인 `Off` 경우, 값이 [Long 데이터 형식](../data-types/long-data-type.md)의 범위를 벗어나면<xref:System.OverflowException>이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-122">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../data-types/long-data-type.md).</span></span> <span data-ttu-id="a91da-123">로의 변환에 `Long` 는 *은행원의 반올림* 도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-123">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="a91da-124">자세한 내용은 [형식 변환 함수](../functions/type-conversion-functions.md)에서 "소수 부분"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a91da-124">For more information, see "Fractional Parts" in [Type Conversion Functions](../functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="a91da-125">`expression1`또는가 `expression2` [Nothing](../nothing.md)으로 계산 되 면 0으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-125">If `expression1` or `expression2` evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="a91da-126">0으로 나누기 시도</span><span class="sxs-lookup"><span data-stu-id="a91da-126">Attempted Division by Zero</span></span>  

 <span data-ttu-id="a91da-127">가 `expression2` 0으로 계산 되는 경우 `\` 연산자는 <xref:System.DivideByZeroException> 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-127">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="a91da-128">피연산자의 모든 숫자 데이터 형식에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-128">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a91da-129">`\`연산자를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-129">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a91da-130">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a91da-131">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a91da-131">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a91da-132">예제</span><span class="sxs-lookup"><span data-stu-id="a91da-132">Example</span></span>  

 <span data-ttu-id="a91da-133">다음 예에서는 연산자를 사용 `\` 하 여 정수 나누기를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-133">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="a91da-134">결과는 두 피연산자의 정수 몫을 나타내며 나머지는 삭제 된 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-134">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 <span data-ttu-id="a91da-135">앞의 예제에서 식은 각각 2, 3, 33 및-22의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91da-135">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a91da-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a91da-136">See also</span></span>

- [<span data-ttu-id="a91da-137">\\= 연산자</span><span class="sxs-lookup"><span data-stu-id="a91da-137">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="a91da-138">/연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a91da-138">/ Operator (Visual Basic)</span></span>](floating-point-division-operator.md)
- [<span data-ttu-id="a91da-139">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="a91da-139">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
- [<span data-ttu-id="a91da-140">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="a91da-140">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="a91da-141">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="a91da-141">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="a91da-142">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="a91da-142">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="a91da-143">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="a91da-143">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
