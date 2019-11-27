---
title: Mod 연산자
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: b7552550d4b0496d6ad7ee76a7327054d544b874
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350910"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="863c8-102">Mod 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="863c8-102">Mod operator (Visual Basic)</span></span>

<span data-ttu-id="863c8-103">두 숫자를 나누고 나머지만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-103">Divides two numbers and returns only the remainder.</span></span>

## <a name="syntax"></a><span data-ttu-id="863c8-104">구문</span><span class="sxs-lookup"><span data-stu-id="863c8-104">Syntax</span></span>

```vb
result = number1 Mod number2
```

## <a name="parts"></a><span data-ttu-id="863c8-105">요소</span><span class="sxs-lookup"><span data-stu-id="863c8-105">Parts</span></span>

`result` \
<span data-ttu-id="863c8-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-106">Required.</span></span> <span data-ttu-id="863c8-107">임의의 숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-107">Any numeric variable or property.</span></span>

`number1` \
<span data-ttu-id="863c8-108">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-108">Required.</span></span> <span data-ttu-id="863c8-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-109">Any numeric expression.</span></span>

`number2` \
<span data-ttu-id="863c8-110">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-110">Required.</span></span> <span data-ttu-id="863c8-111">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-111">Any numeric expression.</span></span>

## <a name="supported-types"></a><span data-ttu-id="863c8-112">지원되는 유형</span><span class="sxs-lookup"><span data-stu-id="863c8-112">Supported types</span></span>

<span data-ttu-id="863c8-113">모든 숫자 형식.</span><span class="sxs-lookup"><span data-stu-id="863c8-113">All numeric types.</span></span> <span data-ttu-id="863c8-114">여기에는 부호 없는 형식과 부동 소수점 형식 및 `Decimal`포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-114">This includes the unsigned and floating-point types and `Decimal`.</span></span>

## <a name="result"></a><span data-ttu-id="863c8-115">결과</span><span class="sxs-lookup"><span data-stu-id="863c8-115">Result</span></span>

<span data-ttu-id="863c8-116">결과는 `number1` `number2`으로 나눈 나머지입니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-116">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="863c8-117">예를 들어 식 `14 Mod 4`는 2로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-117">For example, the expression `14 Mod 4` evaluates to 2.</span></span>

> [!NOTE]
> <span data-ttu-id="863c8-118">수학의 *나머지가* 서로 다르며 *음수에 대해* 다른 결과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-118">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="863c8-119">Visual Basic, .NET Framework `op_Modulus` 연산자 및 기본 [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL 명령의 `Mod` 연산자는 모두 나머지 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-119">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="863c8-120">`Mod` 작업의 결과는 피제수, `number1`의 부호를 유지 하므로 양수 또는 음수일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-120">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="863c8-121">결과는 항상 범위 (-`number2`, `number2`), 배타 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-121">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="863c8-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-122">For example:</span></span>

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a><span data-ttu-id="863c8-123">주의</span><span class="sxs-lookup"><span data-stu-id="863c8-123">Remarks</span></span>

<span data-ttu-id="863c8-124">`number1` 또는 `number2`가 부동 소수점 값 이면 나누기의 부동 소수점 나머지가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-124">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="863c8-125">결과의 데이터 형식은 `number1`의 데이터 형식으로 나눈 값과 `number2`가능한 모든 값을 포함할 수 있는 가장 작은 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-125">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>

<span data-ttu-id="863c8-126">`number1` 또는 `number2`가 [Nothing](../../../visual-basic/language-reference/nothing.md)으로 평가 되 면 0으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-126">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>

<span data-ttu-id="863c8-127">관련 연산자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-127">Related operators include the following:</span></span>

- <span data-ttu-id="863c8-128">[\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) 는 나눗셈의 정수 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-128">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="863c8-129">예를 들어 `14 \ 4` 식은 3으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-129">For example, the expression `14 \ 4` evaluates to 3.</span></span>

- <span data-ttu-id="863c8-130">[/연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) 는 나머지를 포함 하 여 전체 몫을 부동 소수점 숫자로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-130">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="863c8-131">예를 들어 `14 / 4` 식은 3.5로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-131">For example, the expression `14 / 4` evaluates to 3.5.</span></span>

## <a name="attempted-division-by-zero"></a><span data-ttu-id="863c8-132">0으로 나누기 시도</span><span class="sxs-lookup"><span data-stu-id="863c8-132">Attempted division by zero</span></span>

<span data-ttu-id="863c8-133">`number2` 0으로 계산 되는 경우 `Mod` 연산자의 동작은 피연산자의 데이터 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-133">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands:</span></span>

- <span data-ttu-id="863c8-134">컴파일 시간에 `number2`을 확인할 수 없는 경우 정수 나누기는 <xref:System.DivideByZeroException> 예외를 throw 하 고 컴파일 시간에 `number2` 0으로 평가 되는 경우 컴파일 타임 오류 `BC30542 Division by zero occurred while evaluating this expression` 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-134">An integral division throws a <xref:System.DivideByZeroException> exception if `number2` cannot be determined in compile-time and generates a compile-time error `BC30542 Division by zero occurred while evaluating this expression` if `number2` is evaluated to zero at compile-time.</span></span>
- <span data-ttu-id="863c8-135">부동 소수점 나누기는 <xref:System.Double.NaN?displayProperty=nameWithType>를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-135">A floating-point division returns <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>

## <a name="equivalent-formula"></a><span data-ttu-id="863c8-136">동일한 수식</span><span class="sxs-lookup"><span data-stu-id="863c8-136">Equivalent formula</span></span>

<span data-ttu-id="863c8-137">식 `a Mod b` 다음 수식 중 하에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-137">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a><span data-ttu-id="863c8-138">부동 소수점 부정확</span><span class="sxs-lookup"><span data-stu-id="863c8-138">Floating-point imprecision</span></span>

<span data-ttu-id="863c8-139">부동 소수점 숫자를 사용 하는 경우 메모리에 항상 정확한 10 진수가 없다는 것을 명심 하십시오.</span><span class="sxs-lookup"><span data-stu-id="863c8-139">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="863c8-140">이로 인해 값 비교 및 `Mod` 연산자와 같은 특정 작업에서 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-140">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="863c8-141">자세한 내용은 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="863c8-141">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="overloading"></a><span data-ttu-id="863c8-142">오버로드</span><span class="sxs-lookup"><span data-stu-id="863c8-142">Overloading</span></span>

<span data-ttu-id="863c8-143">`Mod` 연산자를 *오버 로드할*수 있습니다. 즉, 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-143">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="863c8-144">코드가 이러한 오버 로드를 포함 하는 클래스 또는 구조체의 인스턴스에 `Mod` 적용 되는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-144">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="863c8-145">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="863c8-145">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="863c8-146">예제</span><span class="sxs-lookup"><span data-stu-id="863c8-146">Example</span></span>

<span data-ttu-id="863c8-147">다음 예에서는 `Mod` 연산자를 사용 하 여 두 숫자를 나누고 나머지만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-147">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="863c8-148">두 숫자 중 하나가 부동 소수점 숫자인 경우 결과는 나머지를 나타내는 부동 소수점 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-148">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a><span data-ttu-id="863c8-149">예제</span><span class="sxs-lookup"><span data-stu-id="863c8-149">Example</span></span>

<span data-ttu-id="863c8-150">다음 예제에서는 부동 소수점 피연산자의 잠재적 부정확을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-150">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="863c8-151">첫 번째 문에서 피연산자는 `Double`되며 0.2는 저장 된 값이 0.20000000000000001 인 무한 반복 이진 분수입니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-151">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="863c8-152">두 번째 문에서 리터럴 형식 문자 `D` 두 피연산자를 `Decimal`하 고 0.2에 정확한 표현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="863c8-152">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a><span data-ttu-id="863c8-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="863c8-153">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [<span data-ttu-id="863c8-154">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="863c8-154">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="863c8-155">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="863c8-155">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="863c8-156">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="863c8-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="863c8-157">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="863c8-157">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="863c8-158">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="863c8-158">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="863c8-159">\ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="863c8-159">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
