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
ms.openlocfilehash: 7038fef4258d190b726a851b26f2a2840ff3c0ea
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873366"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e0f21-102">\* 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0f21-102">\* Operator (Visual Basic)</span></span>

<span data-ttu-id="e0f21-103">두 숫자를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0f21-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0f21-104">Syntax</span></span>  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="e0f21-105">부분</span><span class="sxs-lookup"><span data-stu-id="e0f21-105">Parts</span></span>  
  
|<span data-ttu-id="e0f21-106">용어</span><span class="sxs-lookup"><span data-stu-id="e0f21-106">Term</span></span>|<span data-ttu-id="e0f21-107">정의</span><span class="sxs-lookup"><span data-stu-id="e0f21-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="e0f21-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e0f21-108">Required.</span></span> <span data-ttu-id="e0f21-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="e0f21-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e0f21-110">Required.</span></span> <span data-ttu-id="e0f21-111">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="e0f21-112">결과</span><span class="sxs-lookup"><span data-stu-id="e0f21-112">Result</span></span>  

 <span data-ttu-id="e0f21-113">결과는 및의 곱입니다 `number1` `number2` .</span><span class="sxs-lookup"><span data-stu-id="e0f21-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="e0f21-114">지원 형식</span><span class="sxs-lookup"><span data-stu-id="e0f21-114">Supported Types</span></span>  

 <span data-ttu-id="e0f21-115">부호 없는 형식 및 부동 소수점 형식 및를 포함 하는 모든 숫자 형식 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0f21-116">설명</span><span class="sxs-lookup"><span data-stu-id="e0f21-116">Remarks</span></span>  

 <span data-ttu-id="e0f21-117">결과의 데이터 형식은 피연산자의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="e0f21-118">다음 표에서는 결과의 데이터 형식을 결정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="e0f21-119">피연산자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e0f21-119">Operand data types</span></span>|<span data-ttu-id="e0f21-120">Result 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e0f21-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="e0f21-121">두 식은 모두 정수 데이터 형식 ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))입니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-121">Both expressions are integral data types ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="e0f21-122">및의 데이터 형식에 적합 한 숫자 데이터 형식 `number1` 입니다 `number2` .</span><span class="sxs-lookup"><span data-stu-id="e0f21-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="e0f21-123">[연산자 결과의 데이터 형식](data-types-of-operator-results.md)에서 "정수 산술 연산" 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0f21-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="e0f21-124">두 식이 모두 [Decimal](../data-types/decimal-data-type.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-124">Both expressions are [Decimal](../data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="e0f21-125">두 식이 모두 [단일](../data-types/single-data-type.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-125">Both expressions are [Single](../data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="e0f21-126">두 식이 모두 부동 소수점 데이터 형식 ( `Single` 또는 [Double](../data-types/double-data-type.md)) 이지만 둘 다는 아닙니다 `Single` (참고 `Decimal` 는 부동 소수점 데이터 형식이 아님).</span><span class="sxs-lookup"><span data-stu-id="e0f21-126">Either expression is a floating-point data type (`Single` or [Double](../data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="e0f21-127">식이 [Nothing](../nothing.md)으로 계산 되 면 0으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-127">If an expression evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="e0f21-128">오버로딩</span><span class="sxs-lookup"><span data-stu-id="e0f21-128">Overloading</span></span>  

 <span data-ttu-id="e0f21-129">`*`연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e0f21-130">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e0f21-131">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0f21-131">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0f21-132">예제</span><span class="sxs-lookup"><span data-stu-id="e0f21-132">Example</span></span>  

 <span data-ttu-id="e0f21-133">이 예제에서는 연산자를 사용 `*` 하 여 두 숫자를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="e0f21-134">결과는 두 피연산자의 곱입니다.</span><span class="sxs-lookup"><span data-stu-id="e0f21-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="e0f21-135">참조</span><span class="sxs-lookup"><span data-stu-id="e0f21-135">See also</span></span>

- [<span data-ttu-id="e0f21-136">\* = 연산자</span><span class="sxs-lookup"><span data-stu-id="e0f21-136">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="e0f21-137">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="e0f21-137">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="e0f21-138">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="e0f21-138">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="e0f21-139">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="e0f21-139">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="e0f21-140">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="e0f21-140">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
