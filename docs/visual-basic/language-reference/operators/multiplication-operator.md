---
title: '* 연산자'
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
ms.openlocfilehash: 4f6a8ea2c5f4e23791afdfe98d2a08bf67219048
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348373"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="73b3e-102">\* 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73b3e-102">\* Operator (Visual Basic)</span></span>
<span data-ttu-id="73b3e-103">두 숫자를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73b3e-104">구문</span><span class="sxs-lookup"><span data-stu-id="73b3e-104">Syntax</span></span>  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="73b3e-105">요소</span><span class="sxs-lookup"><span data-stu-id="73b3e-105">Parts</span></span>  
  
|<span data-ttu-id="73b3e-106">용어</span><span class="sxs-lookup"><span data-stu-id="73b3e-106">Term</span></span>|<span data-ttu-id="73b3e-107">정의</span><span class="sxs-lookup"><span data-stu-id="73b3e-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="73b3e-108">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-108">Required.</span></span> <span data-ttu-id="73b3e-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="73b3e-110">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-110">Required.</span></span> <span data-ttu-id="73b3e-111">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="73b3e-112">결과</span><span class="sxs-lookup"><span data-stu-id="73b3e-112">Result</span></span>  
 <span data-ttu-id="73b3e-113">결과는 `number1` 및 `number2`제품입니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="73b3e-114">지원 형식</span><span class="sxs-lookup"><span data-stu-id="73b3e-114">Supported Types</span></span>  
 <span data-ttu-id="73b3e-115">부호 없는 형식 및 부동 소수점 형식 및 `Decimal`을 포함 한 모든 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73b3e-116">주의</span><span class="sxs-lookup"><span data-stu-id="73b3e-116">Remarks</span></span>  
 <span data-ttu-id="73b3e-117">결과의 데이터 형식은 피연산자의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="73b3e-118">다음 표에서는 결과의 데이터 형식을 결정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="73b3e-119">피연산자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="73b3e-119">Operand data types</span></span>|<span data-ttu-id="73b3e-120">Result 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="73b3e-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="73b3e-121">두 식은 모두 정수 데이터 형식 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))입니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-121">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="73b3e-122">`number1` 및 `number2`의 데이터 형식에 적합 한 숫자 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="73b3e-123">[연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)에서 "정수 산술 연산" 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73b3e-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="73b3e-124">두 식이 모두 [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-124">Both expressions are [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="73b3e-125">두 식이 모두 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-125">Both expressions are [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="73b3e-126">두 식이 모두 부동 소수점 데이터 형식 (`Single` 또는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) 이지만 `Single` 둘 다는 아닙니다 (참고 `Decimal`가 부동 소수점 데이터 형식이 아님).</span><span class="sxs-lookup"><span data-stu-id="73b3e-126">Either expression is a floating-point data type (`Single` or [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="73b3e-127">식이 [Nothing](../../../visual-basic/language-reference/nothing.md)으로 계산 되 면 0으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-127">If an expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="73b3e-128">오버로드</span><span class="sxs-lookup"><span data-stu-id="73b3e-128">Overloading</span></span>  
 <span data-ttu-id="73b3e-129">`*` 연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="73b3e-130">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="73b3e-131">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73b3e-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73b3e-132">예제</span><span class="sxs-lookup"><span data-stu-id="73b3e-132">Example</span></span>  
 <span data-ttu-id="73b3e-133">이 예에서는 `*` 연산자를 사용 하 여 두 숫자를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="73b3e-134">결과는 두 피연산자의 곱입니다.</span><span class="sxs-lookup"><span data-stu-id="73b3e-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="73b3e-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73b3e-135">See also</span></span>

- [<span data-ttu-id="73b3e-136">\*= 연산자</span><span class="sxs-lookup"><span data-stu-id="73b3e-136">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="73b3e-137">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="73b3e-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="73b3e-138">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="73b3e-138">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="73b3e-139">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="73b3e-139">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="73b3e-140">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="73b3e-140">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
