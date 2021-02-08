---
description: 다음에 대 한 자세한 정보:-연산자 (Visual Basic)
title: '- 연산자'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 858e887fa7c5c0cc6129996c98bddb78bc53045c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795263"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="3a1d8-103">- 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a1d8-103">- Operator (Visual Basic)</span></span>

<span data-ttu-id="3a1d8-104">두 숫자 식의 차이를 반환 하거나 숫자 식의 음수 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-104">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a1d8-105">구문</span><span class="sxs-lookup"><span data-stu-id="3a1d8-105">Syntax</span></span>  
  
```vb  
expression1 – expression2
```
  
<span data-ttu-id="3a1d8-106">또는</span><span class="sxs-lookup"><span data-stu-id="3a1d8-106">or</span></span>

```vb  
–expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="3a1d8-107">부분</span><span class="sxs-lookup"><span data-stu-id="3a1d8-107">Parts</span></span>  

 `expression1`  
 <span data-ttu-id="3a1d8-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-108">Required.</span></span> <span data-ttu-id="3a1d8-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-109">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="3a1d8-110">`–`연산자가 음수 값을 계산 하지 않는 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-110">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="3a1d8-111">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-111">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="3a1d8-112">결과</span><span class="sxs-lookup"><span data-stu-id="3a1d8-112">Result</span></span>  

 <span data-ttu-id="3a1d8-113">결과는 `expression1` 와 `expression2` 의 차이 또는의 부정 값입니다 `expression1` .</span><span class="sxs-lookup"><span data-stu-id="3a1d8-113">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="3a1d8-114">결과 데이터 형식은 및의 데이터 형식에 적합 한 숫자 형식입니다 `expression1` `expression2` .</span><span class="sxs-lookup"><span data-stu-id="3a1d8-114">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="3a1d8-115">[연산자 결과의 데이터 형식](data-types-of-operator-results.md)에서 "정수 산술 연산" 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-115">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="3a1d8-116">지원 형식</span><span class="sxs-lookup"><span data-stu-id="3a1d8-116">Supported Types</span></span>  

 <span data-ttu-id="3a1d8-117">모든 숫자 형식.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-117">All numeric types.</span></span> <span data-ttu-id="3a1d8-118">여기에는 부호 없는 및 부동 소수점 형식 및가 포함 됩니다 `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="3a1d8-118">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a1d8-119">설명</span><span class="sxs-lookup"><span data-stu-id="3a1d8-119">Remarks</span></span>  

 <span data-ttu-id="3a1d8-120">앞에 표시 된 구문에 표시 된 첫 번째 사용에서 `–` 연산자는 두 숫자 식의 차이에 대 한 *이진* 산술 빼기 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-120">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="3a1d8-121">앞에 표시 된 구문에 표시 된 두 번째 사용에서 `–` 연산자는 식의 음수 값에 대 한 *단항* 부정 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-121">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="3a1d8-122">이러한 의미에서 부정은의 부호를 반대로 하 여 `expression1` 가 음수인 경우 결과가 양수인 것으로 구성 됩니다 `expression1` .</span><span class="sxs-lookup"><span data-stu-id="3a1d8-122">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="3a1d8-123">두 식이 모두 [Nothing](../nothing.md)으로 계산 되는 경우 `–` 연산자는이 값을 0으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-123">If either expression evaluates to [Nothing](../nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a1d8-124">`–`연산자를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-124">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="3a1d8-125">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-125">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="3a1d8-126">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-126">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a1d8-127">예제</span><span class="sxs-lookup"><span data-stu-id="3a1d8-127">Example</span></span>  

 <span data-ttu-id="3a1d8-128">다음 예에서는 연산자를 사용 하 여 `–` 두 숫자 간의 차이를 계산 하 고 반환한 다음 숫자를 부정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-128">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="3a1d8-129">이러한 문을 실행 한 후에는 `binaryResult` 124.45이 포함 되 고 `unaryResult` -334.90가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a1d8-129">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a1d8-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a1d8-130">See also</span></span>

- [<span data-ttu-id="3a1d8-131">-= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a1d8-131">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="3a1d8-132">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="3a1d8-132">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="3a1d8-133">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="3a1d8-133">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="3a1d8-134">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="3a1d8-134">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="3a1d8-135">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="3a1d8-135">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
