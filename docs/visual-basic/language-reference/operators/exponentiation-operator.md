---
title: ^ 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: 54de9c91d4e166b8ca1733952dfa9c98ebf11ffe
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674096"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="1521d-102">^ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1521d-102">^ Operator (Visual Basic)</span></span>

<span data-ttu-id="1521d-103">한 숫자가 다른 숫자의 거듭제곱 수를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-103">Raises a number to the power of another number.</span></span>

## <a name="syntax"></a><span data-ttu-id="1521d-104">구문</span><span class="sxs-lookup"><span data-stu-id="1521d-104">Syntax</span></span>

```
number ^ exponent
```

## <a name="parts"></a><span data-ttu-id="1521d-105">요소</span><span class="sxs-lookup"><span data-stu-id="1521d-105">Parts</span></span>

`number`\
<span data-ttu-id="1521d-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1521d-106">Required.</span></span> <span data-ttu-id="1521d-107">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-107">Any numeric expression.</span></span>

`exponent`\
<span data-ttu-id="1521d-108">필수.</span><span class="sxs-lookup"><span data-stu-id="1521d-108">Required.</span></span> <span data-ttu-id="1521d-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-109">Any numeric expression.</span></span>

## <a name="result"></a><span data-ttu-id="1521d-110">결과</span><span class="sxs-lookup"><span data-stu-id="1521d-110">Result</span></span>

<span data-ttu-id="1521d-111">결과 `number` 의 거듭제곱 `exponent`을 항상으로 `Double` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>

## <a name="supported-types"></a><span data-ttu-id="1521d-112">지원 형식</span><span class="sxs-lookup"><span data-stu-id="1521d-112">Supported Types</span></span>

<span data-ttu-id="1521d-113">`Double`.</span><span class="sxs-lookup"><span data-stu-id="1521d-113">`Double`.</span></span> <span data-ttu-id="1521d-114">다른 형식의 피연산자 변환할 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-114">Operands of any different type are converted to `Double`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1521d-115">설명</span><span class="sxs-lookup"><span data-stu-id="1521d-115">Remarks</span></span>

<span data-ttu-id="1521d-116">Visual Basic에서 지 수를 항상 수행 합니다 [Double 데이터 형식](../../../visual-basic/language-reference/data-types/double-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>

<span data-ttu-id="1521d-117">변수의 `exponent` 소수인 수 음수 또는 둘 다.</span><span class="sxs-lookup"><span data-stu-id="1521d-117">The value of `exponent` can be fractional, negative, or both.</span></span>

<span data-ttu-id="1521d-118">단일 식에서 둘 이상의 지 수 연산을 수행 되는 `^` 연산자는 왼쪽에서 오른쪽으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>

> [!NOTE]
> <span data-ttu-id="1521d-119">합니다 `^` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우.</span><span class="sxs-lookup"><span data-stu-id="1521d-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1521d-120">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1521d-121">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1521d-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="1521d-122">예제</span><span class="sxs-lookup"><span data-stu-id="1521d-122">Example</span></span>

<span data-ttu-id="1521d-123">다음 예제에서는 `^` 숫자의 지 수의 거듭제곱을 발생 시키는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="1521d-124">결과 첫 번째 피연산자에서 두 번째의 거듭제곱입니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-124">The result is the first operand raised to the power of the second.</span></span>

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

<span data-ttu-id="1521d-125">앞의 예제 결과 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-125">The preceding example produces the following results:</span></span>

<span data-ttu-id="1521d-126">`exp1` (2의 제곱) 4로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-126">`exp1` is set to 4 (2 squared).</span></span>

<span data-ttu-id="1521d-127">`exp2` 19683 (3, 3 제곱 값을 구합니다)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>

<span data-ttu-id="1521d-128">`exp3` (3 제곱-5)-125로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-128">`exp3` is set to -125 (-5 cubed).</span></span>

<span data-ttu-id="1521d-129">`exp4` 625 (네 번째 기능-5)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>

<span data-ttu-id="1521d-130">`exp5` 2 (8의 세 제곱근)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-130">`exp5` is set to 2 (cube root of 8).</span></span>

<span data-ttu-id="1521d-131">`exp6` (1.0 8의 세 제곱근으로 나눈) 0.5로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>

<span data-ttu-id="1521d-132">앞의 예제 식에서는 괄호의 중요성을 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="1521d-133">때문에 *연산자 우선 순위*, Visual Basic에서 일반적으로 수행 합니다 `^` 연산자, 다른 대체 이전에 단항 `–` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="1521d-134">하는 경우 `exp4` 고 `exp6` 없이 계산 괄호 다음 결과 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>

<span data-ttu-id="1521d-135">`exp4 = -5 ^ 4` -(4 제곱 5)로 계산 됩니다는-625 초래 합니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>

<span data-ttu-id="1521d-136">`exp6 = 8 ^ -1.0 / 3.0` (-1 제곱, 즉 0.125 8)으로 계산 됩니다 0.041666666666666666666666666666667 3.0로 나눈 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1521d-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>

## <a name="see-also"></a><span data-ttu-id="1521d-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="1521d-137">See also</span></span>

- [<span data-ttu-id="1521d-138">^= 연산자</span><span class="sxs-lookup"><span data-stu-id="1521d-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="1521d-139">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="1521d-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="1521d-140">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="1521d-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="1521d-141">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="1521d-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="1521d-142">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="1521d-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
