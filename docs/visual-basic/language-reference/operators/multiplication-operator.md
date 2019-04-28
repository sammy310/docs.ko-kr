---
title: '* 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: 09b95585325b05c0b7925c4c1c9e123f45791e10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936645"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a4a68-102">\* 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4a68-102">\* Operator (Visual Basic)</span></span>
<span data-ttu-id="a4a68-103">두 숫자를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4a68-104">구문</span><span class="sxs-lookup"><span data-stu-id="a4a68-104">Syntax</span></span>  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="a4a68-105">요소</span><span class="sxs-lookup"><span data-stu-id="a4a68-105">Parts</span></span>  
  
|<span data-ttu-id="a4a68-106">용어</span><span class="sxs-lookup"><span data-stu-id="a4a68-106">Term</span></span>|<span data-ttu-id="a4a68-107">정의</span><span class="sxs-lookup"><span data-stu-id="a4a68-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="a4a68-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a4a68-108">Required.</span></span> <span data-ttu-id="a4a68-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="a4a68-110">필수.</span><span class="sxs-lookup"><span data-stu-id="a4a68-110">Required.</span></span> <span data-ttu-id="a4a68-111">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="a4a68-112">결과</span><span class="sxs-lookup"><span data-stu-id="a4a68-112">Result</span></span>  
 <span data-ttu-id="a4a68-113">결과 곱한 `number1` 고 `number2`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="a4a68-114">지원 형식</span><span class="sxs-lookup"><span data-stu-id="a4a68-114">Supported Types</span></span>  
 <span data-ttu-id="a4a68-115">모든 숫자 형식, 부동 소수점 및 부호 없는 형식을 포함 하 고 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4a68-116">설명</span><span class="sxs-lookup"><span data-stu-id="a4a68-116">Remarks</span></span>  
 <span data-ttu-id="a4a68-117">데이터 형식의 결과 피연산자의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="a4a68-118">다음 표에서 결과의 데이터 형식을 결정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="a4a68-119">피연산자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a4a68-119">Operand data types</span></span>|<span data-ttu-id="a4a68-120">결과 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a4a68-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="a4a68-121">두 식이 모두 정수 데이터 형식 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)를 [바이트](../../../visual-basic/language-reference/data-types/byte-data-type.md)를 [짧은](../../../visual-basic/language-reference/data-types/short-data-type.md)를 [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)를 [정수](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)하십시오 [긴](../../../visual-basic/language-reference/data-types/long-data-type.md)하십시오 [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="a4a68-121">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="a4a68-122">데이터 형식에 대 한 적절 한 숫자 데이터 형식 `number1` 고 `number2`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="a4a68-123">"정수 산술" 표를 참조 하십시오 [연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="a4a68-124">두 식이 모두 [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="a4a68-124">Both expressions are [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="a4a68-125">두 식이 모두 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="a4a68-125">Both expressions are [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="a4a68-126">두 식 중 하나가 부동 소수점 데이터 형식 (`Single` 또는 [이중](../../../visual-basic/language-reference/data-types/double-data-type.md)) 중 하나만 `Single` (참고 `Decimal` 부동 소수점 데이터 형식이 아닌)</span><span class="sxs-lookup"><span data-stu-id="a4a68-126">Either expression is a floating-point data type (`Single` or [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="a4a68-127">식을 계산 되는 경우 [Nothing](../../../visual-basic/language-reference/nothing.md)를 0으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-127">If an expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a4a68-128">오버로딩</span><span class="sxs-lookup"><span data-stu-id="a4a68-128">Overloading</span></span>  
 <span data-ttu-id="a4a68-129">합니다 `*` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우.</span><span class="sxs-lookup"><span data-stu-id="a4a68-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a4a68-130">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a4a68-131">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4a68-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4a68-132">예제</span><span class="sxs-lookup"><span data-stu-id="a4a68-132">Example</span></span>  
 <span data-ttu-id="a4a68-133">이 예제에서는 `*` 두 숫자를 곱하기 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="a4a68-134">결과 두 피연산자의 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a68-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="a4a68-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="a4a68-135">See also</span></span>

- [<span data-ttu-id="a4a68-136">\*= 연산자</span><span class="sxs-lookup"><span data-stu-id="a4a68-136">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="a4a68-137">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="a4a68-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="a4a68-138">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="a4a68-138">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="a4a68-139">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="a4a68-139">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="a4a68-140">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="a4a68-140">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
