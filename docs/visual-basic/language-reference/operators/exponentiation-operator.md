---
description: '다음에 대 한 자세한 정보: ^ 연산자 (Visual Basic)'
title: ^ 연산자
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
ms.openlocfilehash: 9333eec7236c363417be7323b673231509da8f1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666045"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="be2cb-103">^ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be2cb-103">^ Operator (Visual Basic)</span></span>

<span data-ttu-id="be2cb-104">특정 숫자를 다른 숫자의 승수로 거듭제곱합니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-104">Raises a number to the power of another number.</span></span>

## <a name="syntax"></a><span data-ttu-id="be2cb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="be2cb-105">Syntax</span></span>

```vb
number ^ exponent
```

## <a name="parts"></a><span data-ttu-id="be2cb-106">부분</span><span class="sxs-lookup"><span data-stu-id="be2cb-106">Parts</span></span>

`number`\
<span data-ttu-id="be2cb-107">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="be2cb-107">Required.</span></span> <span data-ttu-id="be2cb-108">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-108">Any numeric expression.</span></span>

`exponent`\
<span data-ttu-id="be2cb-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="be2cb-109">Required.</span></span> <span data-ttu-id="be2cb-110">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-110">Any numeric expression.</span></span>

## <a name="result"></a><span data-ttu-id="be2cb-111">결과</span><span class="sxs-lookup"><span data-stu-id="be2cb-111">Result</span></span>

<span data-ttu-id="be2cb-112">결과는 `number` 항상 값으로의 거듭제곱으로 발생 합니다 `exponent` `Double` .</span><span class="sxs-lookup"><span data-stu-id="be2cb-112">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>

## <a name="supported-types"></a><span data-ttu-id="be2cb-113">지원 형식</span><span class="sxs-lookup"><span data-stu-id="be2cb-113">Supported Types</span></span>

<span data-ttu-id="be2cb-114">`Double`.</span><span class="sxs-lookup"><span data-stu-id="be2cb-114">`Double`.</span></span> <span data-ttu-id="be2cb-115">다른 형식의 피연산자는로 변환 됩니다 `Double` .</span><span class="sxs-lookup"><span data-stu-id="be2cb-115">Operands of any different type are converted to `Double`.</span></span>

## <a name="remarks"></a><span data-ttu-id="be2cb-116">설명</span><span class="sxs-lookup"><span data-stu-id="be2cb-116">Remarks</span></span>

<span data-ttu-id="be2cb-117">Visual Basic는 [Double 데이터 형식](../data-types/double-data-type.md)에서 항상 지 각 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-117">Visual Basic always performs exponentiation in the [Double Data Type](../data-types/double-data-type.md).</span></span>

<span data-ttu-id="be2cb-118">의 값은 `exponent` 소수 자릿수, 음수 또는 둘 다 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-118">The value of `exponent` can be fractional, negative, or both.</span></span>

<span data-ttu-id="be2cb-119">단일 식에서 두 개 이상의 지 수를 수행 하는 경우 `^` 왼쪽에서 오른쪽으로 발견 되 면 연산자가 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-119">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>

> [!NOTE]
> <span data-ttu-id="be2cb-120">`^`연산자를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-120">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="be2cb-121">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-121">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="be2cb-122">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be2cb-122">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="be2cb-123">예제</span><span class="sxs-lookup"><span data-stu-id="be2cb-123">Example</span></span>

<span data-ttu-id="be2cb-124">다음 예에서는 연산자를 사용 하 여 `^` 숫자를 지 수의 거듭제곱으로 거듭제곱 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-124">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="be2cb-125">결과는 첫 번째 피연산자가 두 번째 피연산자의 거듭제곱으로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-125">The result is the first operand raised to the power of the second.</span></span>

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

<span data-ttu-id="be2cb-126">앞의 예제에서는 다음과 같은 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-126">The preceding example produces the following results:</span></span>

<span data-ttu-id="be2cb-127">`exp1` 는 4 (4 제곱)로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-127">`exp1` is set to 4 (2 squared).</span></span>

<span data-ttu-id="be2cb-128">`exp2` 가 19683 (3 제곱으로 설정 되 고 그 값은 3 제곱)로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-128">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>

<span data-ttu-id="be2cb-129">`exp3` 는-125 (-5 제곱)로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-129">`exp3` is set to -125 (-5 cubed).</span></span>

<span data-ttu-id="be2cb-130">`exp4` 는 625 (-5에서 4 제곱)로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-130">`exp4` is set to 625 (-5 to the fourth power).</span></span>

<span data-ttu-id="be2cb-131">`exp5` 는 2 (큐브 루트 8)로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-131">`exp5` is set to 2 (cube root of 8).</span></span>

<span data-ttu-id="be2cb-132">`exp6` 는 0.5 (1.0을 8의 큐브 루트로 나눈 값)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-132">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>

<span data-ttu-id="be2cb-133">앞의 예제에서 식의 괄호의 중요도를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-133">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="be2cb-134">*연산자 우선 순위로* 인해 Visual Basic은 일반적으로 `^` 단항 연산자를 비롯 하 여 다른 연산자 앞에 연산자를 수행 `–` 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-134">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="be2cb-135">`exp4`및가 `exp6` 괄호 없이 계산 된 경우 다음과 같은 결과가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-135">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>

<span data-ttu-id="be2cb-136">`exp4 = -5 ^ 4` 는 – (5에서 4 제곱)로 계산 되어-625이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-136">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>

<span data-ttu-id="be2cb-137">`exp6 = 8 ^ -1.0 / 3.0` 는 (8에서 – 1 제곱 또는 0.125)로 구분 되어 3.0로 구분 됩니다. 그러면 0.041666666666666666666666666666667이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2cb-137">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>

## <a name="see-also"></a><span data-ttu-id="be2cb-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be2cb-138">See also</span></span>

- [<span data-ttu-id="be2cb-139">^ = 연산자</span><span class="sxs-lookup"><span data-stu-id="be2cb-139">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="be2cb-140">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="be2cb-140">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="be2cb-141">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="be2cb-141">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="be2cb-142">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="be2cb-142">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="be2cb-143">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="be2cb-143">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
