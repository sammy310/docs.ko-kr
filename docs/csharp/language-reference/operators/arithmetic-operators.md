---
title: 산술 연산자 - C# 참조
description: 숫자 형식이 포함된 곱하기, 나누기, 나머지, 더하기 및 빼기 작업을 수행하는 C# 연산자에 대해 알아봅니다.
ms.date: 03/27/2019
author: pkulikov
f1_keywords:
- ++_CSharpKeyword
- --_CSharpKeyword
- '*_CSharpKeyword'
- /_CSharpKeyword
- '%_CSharpKeyword'
- +_CSharpKeyword
- -_CSharpKeyword
helpviewer_keywords:
- arithmetic operators [C#]
- increment operator [C#]
- ++ operator [C#]
- decrement operator [C#]
- -- operator [C#]
- multiplication operator [C#]
- '* operator [C#]'
- division operator [C#]
- / operator [C#]
- remainder operator [C#]
- '% operator [C#]'
- addition operator [C#]
- + operator [C#]
- subtraction operator [C#]
- '- operator [C#]'
ms.openlocfilehash: 9760be0fcfe29d2c11cbb1f4d4d81c5a79261a0d
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771729"
---
# <a name="arithmetic-operators-c-reference"></a><span data-ttu-id="50976-103">산술 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="50976-103">Arithmetic operators (C# reference)</span></span>

<span data-ttu-id="50976-104">다음 연산자는 숫자 형식을 포함한 산술 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-104">The following operators perform arithmetic operations with numeric types:</span></span>

- <span data-ttu-id="50976-105">단항 [`++`(증분)](#increment-operator-), [`--`(감소)](#decrement-operator---), [`+`(더하기)](#unary-plus-and-minus-operators), [`-`(빼기)](#unary-plus-and-minus-operators) 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-105">Unary [`++` (increment)](#increment-operator-), [`--` (decrement)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators), and [`-` (minus)](#unary-plus-and-minus-operators) operators</span></span>
- <span data-ttu-id="50976-106">이진 [`*`(곱하기)](#multiplication-operator-), [`/`(나누기)](#division-operator-), [`%`(나머지)](#remainder-operator-), [`+`(더하기)](#addition-operator-) 및 [`-`(빼기)](#subtraction-operator--) 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-106">Binary [`*` (multiplication)](#multiplication-operator-), [`/` (division)](#division-operator-), [`%` (remainder)](#remainder-operator-), [`+` (addition)](#addition-operator-), and [`-` (subtraction)](#subtraction-operator--) operators</span></span>

<span data-ttu-id="50976-107">해당 연산자는 모든 [정수](../builtin-types/integral-numeric-types.md) 및 [부동 소수점](../builtin-types/floating-point-numeric-types.md) 숫자 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-107">Those operators support all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

## <a name="increment-operator-"></a><span data-ttu-id="50976-108">증가 연산자 ++</span><span class="sxs-lookup"><span data-stu-id="50976-108">Increment operator ++</span></span>

<span data-ttu-id="50976-109">단항 증가 연산자(`++`)는 피연산자를 1씩 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-109">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="50976-110">피연산자는 변수, [속성](../../programming-guide/classes-and-structs/properties.md) 액세스 또는 [인덱서](../../programming-guide/indexers/index.md) 액세스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-110">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="50976-111">증가 연산자는 후위 증가 연산자 `x++` 및 전위 증가 연산자 `++x`라는 두 가지 양식으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="50976-111">The increment operator is supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

### <a name="postfix-increment-operator"></a><span data-ttu-id="50976-112">후위 증가 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-112">Postfix increment operator</span></span>

<span data-ttu-id="50976-113">`x++`의 결과는 다음 예제와 같이 연산 ‘전’ `x`의 값입니다. </span><span class="sxs-lookup"><span data-stu-id="50976-113">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a><span data-ttu-id="50976-114">후위 증가 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-114">Prefix increment operator</span></span>

<span data-ttu-id="50976-115">`++x`의 결과는 다음 예제와 같이 연산 ‘후’ `x`의 값입니다. </span><span class="sxs-lookup"><span data-stu-id="50976-115">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a><span data-ttu-id="50976-116">감소 연산자 --</span><span class="sxs-lookup"><span data-stu-id="50976-116">Decrement operator --</span></span>

<span data-ttu-id="50976-117">단항 감소 연산자(`--`)는 피연산자를 1씩 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-117">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="50976-118">피연산자는 변수, [속성](../../programming-guide/classes-and-structs/properties.md) 액세스 또는 [인덱서](../../programming-guide/indexers/index.md) 액세스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-118">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="50976-119">감소 연산자는 후위 감소 연산자 `x--` 및 전위 감소 연산자 `--x`라는 두 가지 양식으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="50976-119">The decrement operator is supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

### <a name="postfix-decrement-operator"></a><span data-ttu-id="50976-120">후위 감소 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-120">Postfix decrement operator</span></span>

<span data-ttu-id="50976-121">`x--`의 결과는 다음 예제와 같이 연산 ‘전’ `x`의 값입니다. </span><span class="sxs-lookup"><span data-stu-id="50976-121">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a><span data-ttu-id="50976-122">후위 감소 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-122">Prefix decrement operator</span></span>

<span data-ttu-id="50976-123">`--x`의 결과는 다음 예제와 같이 연산 ‘후’ `x`의 값입니다. </span><span class="sxs-lookup"><span data-stu-id="50976-123">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a><span data-ttu-id="50976-124">단항 더하기 및 빼기 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-124">Unary plus and minus operators</span></span>

<span data-ttu-id="50976-125">단항 `+` 연산자는 피연산자의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-125">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="50976-126">단항 `-` 연산자는 피연산자의 숫자 부정을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-126">The unary `-` operator computes the numeric negation of its operand.</span></span>

[!code-csharp-interactive[unary plus and minus](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#UnaryPlusAndMinus)]

<span data-ttu-id="50976-127">단항 `-` 연산자는 [ulong](../builtin-types/integral-numeric-types.md) 형식을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-127">The unary `-` operator doesn't support the [ulong](../builtin-types/integral-numeric-types.md) type.</span></span>

## <a name="multiplication-operator-"></a><span data-ttu-id="50976-128">곱하기 연산자 \*</span><span class="sxs-lookup"><span data-stu-id="50976-128">Multiplication operator \*</span></span>

<span data-ttu-id="50976-129">곱하기 연산자 `*`는 피연산자의 곱을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-129">The multiplication operator `*` computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication operator](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#Multiplication)]

<span data-ttu-id="50976-130">단항 `*` 연산자는 [포인터 간접 참조 연산자](pointer-related-operators.md#pointer-indirection-operator-)입니다.</span><span class="sxs-lookup"><span data-stu-id="50976-130">The unary `*` operator is the [pointer indirection operator](pointer-related-operators.md#pointer-indirection-operator-).</span></span>

## <a name="division-operator-"></a><span data-ttu-id="50976-131">나누기 연산자 /</span><span class="sxs-lookup"><span data-stu-id="50976-131">Division operator /</span></span>

<span data-ttu-id="50976-132">나누기 연산자 `/`는 오른쪽 피연산자로 왼쪽 피연산자를 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="50976-132">The division operator `/` divides its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-division"></a><span data-ttu-id="50976-133">정수 나누기</span><span class="sxs-lookup"><span data-stu-id="50976-133">Integer division</span></span>

<span data-ttu-id="50976-134">정수 형식의 피연산자의 경우 `/` 연산자의 결과는 정수 형식이고 두 피연산자의 몫과 동일한 값은 0으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="50976-134">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerDivision)]

<span data-ttu-id="50976-135">두 피연산자의 몫을 부동 소수점 숫자로 가져오려면 `float`, `double` 또는 `decimal` 형식을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="50976-135">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a><span data-ttu-id="50976-136">부동 소수점 나누기</span><span class="sxs-lookup"><span data-stu-id="50976-136">Floating-point division</span></span>

<span data-ttu-id="50976-137">`float`, `double` 및 `decimal` 형식의 경우 `/` 연산자의 결과는 두 피연산자의 몫입니다.</span><span class="sxs-lookup"><span data-stu-id="50976-137">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointDivision)]

<span data-ttu-id="50976-138">피연산자 중 하나가 `decimal`이면 `float` 또는 `double` 모두 `decimal`로 암시적으로 변환할 수 없기 때문에 나머지 피연산자는 `float` 또는 `double`일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-138">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="50976-139">`float` 또는 `double` 피연산자를 `decimal` 형식으로 암시적으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-139">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="50976-140">숫자 형식 간의 변환에 대한 자세한 내용은 [기본 제공 숫자 변환](../builtin-types/numeric-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50976-140">For more information about conversions between numeric types, see [Built-in numeric conversions](../builtin-types/numeric-conversions.md).</span></span>

## <a name="remainder-operator-"></a><span data-ttu-id="50976-141">나머지 연산자 %</span><span class="sxs-lookup"><span data-stu-id="50976-141">Remainder operator %</span></span>

<span data-ttu-id="50976-142">나머지 연산자 `%`는 왼쪽 피연산자를 오른쪽 피연산자로 나눈 후 나머지를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-142">The remainder operator `%` computes the remainder after dividing its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-remainder"></a><span data-ttu-id="50976-143">정수 나머지</span><span class="sxs-lookup"><span data-stu-id="50976-143">Integer remainder</span></span>
  
<span data-ttu-id="50976-144">정수 형식의 피연산자의 경우 `a % b`의 결과가 `a - (a / b) * b`에서 생성된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="50976-144">For the operands of integer types, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="50976-145">다음 예와 같이 0이 아닌 나머지의 부호는 왼쪽 피연산자와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-145">The sign of the non-zero remainder is the same as that of the left-hand operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerRemainder)]

<span data-ttu-id="50976-146"><xref:System.Math.DivRem%2A?displayProperty=nameWithType> 메서드를 사용하여 정수 나누기 및 나머지 결과를 모두 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-146">Use the <xref:System.Math.DivRem%2A?displayProperty=nameWithType> method to compute both integer division and remainder results.</span></span>

### <a name="floating-point-remainder"></a><span data-ttu-id="50976-147">부동 소수점 나머지</span><span class="sxs-lookup"><span data-stu-id="50976-147">Floating-point remainder</span></span>

<span data-ttu-id="50976-148">`float` 및 `double` 피연산자의 경우 유한 `x` 및 `y`에 대한 `x % y`의 결과는 다음과 같은 `z` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="50976-148">For the `float` and `double` operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="50976-149">0이 아닌 경우 `z`의 부호는 `x`의 부호와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-149">The sign of `z`, if non-zero, is the same as the sign of `x`.</span></span>
- <span data-ttu-id="50976-150">`z`의 절대 값은 `|x| - n * |y|`에서 생성된 값입니다. 여기서 `n`은 `|x| / |y|`보다 작거나 같은 가능한 최대 정수이고 `|x|` 및 `|y|`는 각각 `x` 및 `y`의 절대 값입니다.</span><span class="sxs-lookup"><span data-stu-id="50976-150">The absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="50976-151">나머지 계산 방법은 정수 피연산자에 사용되는 것과 유사하지만 IEEE 754와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="50976-151">This method of computing the remainder is analogous to that used for integer operands, but differs from the IEEE 754.</span></span> <span data-ttu-id="50976-152">IEEE 754를 준수하는 나머지 작업이 필요한 경우 <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-152">If you need the remainder operation that complies with the IEEE 754, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="50976-153">무한 피연산자가 있는 `%` 연산자의 동작에 대한 자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [나머지 연산자](~/_csharplang/spec/expressions.md#remainder-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50976-153">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="50976-154">`decimal` 피연산자의 경우 나머지 연산자 `%`는 <xref:System.Decimal?displayProperty=nameWithType> 형식의 [나머지 연산자](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>)와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-154">For the `decimal` operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

<span data-ttu-id="50976-155">다음 예제에서는 부동 소수점 피연산자를 포함한 나머지 연산자의 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="50976-155">The following example demonstrates the behavior of the remainder operator with floating-point operands:</span></span>

[!code-csharp-interactive[floating-point remainder](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a><span data-ttu-id="50976-156">더하기 연산자 +</span><span class="sxs-lookup"><span data-stu-id="50976-156">Addition operator +</span></span>

<span data-ttu-id="50976-157">더하기 연산자 `+`는 피연산자의 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-157">The addition operator `+` computes the sum of its operands:</span></span>

[!code-csharp-interactive[addition operator](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#Addition)]

<span data-ttu-id="50976-158">문자열 연결 및 대리자 조합의 경우 `+` 연산자를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-158">You also can use the `+` operator for string concatenation and delegate combination.</span></span> <span data-ttu-id="50976-159">자세한 내용은 참조는 [`+` 및 `+=`연산자](addition-operator.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50976-159">For more information, see the [`+` and `+=` operators](addition-operator.md) article.</span></span>

## <a name="subtraction-operator--"></a><span data-ttu-id="50976-160">빼기 연산자 -</span><span class="sxs-lookup"><span data-stu-id="50976-160">Subtraction operator -</span></span>

<span data-ttu-id="50976-161">빼기 연산자 `-`는 왼쪽 피연산자에서 오른쪽 피연산자를 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="50976-161">The subtraction operator `-` subtracts its right-hand operand from its left-hand operand:</span></span>

[!code-csharp-interactive[subtraction operator](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#Subtraction)]

<span data-ttu-id="50976-162">대리자 제거의 경우 `-` 연산자를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-162">You also can use the `-` operator for delegate removal.</span></span> <span data-ttu-id="50976-163">자세한 내용은 [`-` 연산자](subtraction-operator.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50976-163">For more information, see the [`-` operator](subtraction-operator.md) article.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="50976-164">복합 할당</span><span class="sxs-lookup"><span data-stu-id="50976-164">Compound assignment</span></span>

<span data-ttu-id="50976-165">이진 연산자(`op`)의 경우 양식의 복합 할당 식</span><span class="sxs-lookup"><span data-stu-id="50976-165">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="50976-166">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-166">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="50976-167">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="50976-167">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="50976-168">다음 예제에서는 산술 연산자를 사용하는 복합 할당의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="50976-168">The following example demonstrates the usage of compound assignment with arithmetic operators:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#CompoundAssignment)]

<span data-ttu-id="50976-169">[숫자 승격](~/_csharplang/spec/expressions.md#numeric-promotions)으로 인해 `op` 연산의 결과가 암시적으로 `x`의 `T` 형식으로 변환되지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-169">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="50976-170">이 경우 `op`가 미리 정의된 연산자이고 연산의 결과가 명시적으로 `x`의 `T` 형식으로 변환 가능하다면 `x op= y` 양식의 복합 할당 식이 `x = (T)(x op y)`에 해당합니다. 단 `x`는 한 번만 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="50976-170">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="50976-171">다음 예제에서는 해당 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="50976-171">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#CompoundAssignmentWithCast)]

<span data-ttu-id="50976-172">`+=` 및 `-=` 연산자를 사용하여 [이벤트](../keywords/event.md)에서 구독하거나 구독을 취소할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-172">You also use the `+=` and `-=` operators to subscribe to and unsubscribe from [events](../keywords/event.md).</span></span> <span data-ttu-id="50976-173">자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50976-173">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-precedence-and-associativity"></a><span data-ttu-id="50976-174">연산자 우선 순위 및 결합성</span><span class="sxs-lookup"><span data-stu-id="50976-174">Operator precedence and associativity</span></span>

<span data-ttu-id="50976-175">다음 목록에서는 산술 연산자를 가장 높은 우선 순위부터 가장 낮은 것으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-175">The following list orders arithmetic operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="50976-176">후위 증가 `x++` 및 감소 `x--` 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-176">Postfix increment `x++` and decrement `x--` operators</span></span>
- <span data-ttu-id="50976-177">전위 증가 `++x` 및 감소 `--x` 및 단항 `+` 및 `-` 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-177">Prefix increment `++x` and decrement `--x` and unary `+` and `-` operators</span></span>
- <span data-ttu-id="50976-178">곱하기 `*`, `/` 및 `%` 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-178">Multiplicative `*`, `/`, and `%` operators</span></span>
- <span data-ttu-id="50976-179">가감 `+` 및 `-` 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-179">Additive `+` and `-` operators</span></span>

<span data-ttu-id="50976-180">이진 산술 연산자는 왼쪽 결합형입니다.</span><span class="sxs-lookup"><span data-stu-id="50976-180">Binary arithmetic operators are left-associative.</span></span> <span data-ttu-id="50976-181">즉, 우선 순위 수준이 같은 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="50976-181">That is, operators with the same precedence level are evaluated from left to right.</span></span>

<span data-ttu-id="50976-182">괄호(`()`)를 사용하여 연산자 우선 순위와 연결에 따라 주어진 계산 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-182">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence and associativity.</span></span>

[!code-csharp-interactive[precedence and associativity](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

<span data-ttu-id="50976-183">우선 순위 수준에 따라 정렬된 전체 연산자 목록은 [C# 연산자](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50976-183">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="arithmetic-overflow-and-division-by-zero"></a><span data-ttu-id="50976-184">산술 오버플로 및 0으로 나누기</span><span class="sxs-lookup"><span data-stu-id="50976-184">Arithmetic overflow and division by zero</span></span>

<span data-ttu-id="50976-185">산술 연산의 결과가 관련된 숫자 형식의 가능한 유한 값 범위를 벗어나는 경우 산술 연산자의 동작은 해당하는 피연산자의 형식에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="50976-185">When the result of an arithmetic operation is outside the range of possible finite values of the involved numeric type, the behavior of an arithmetic operator depends on the type of its operands.</span></span>

### <a name="integer-arithmetic-overflow"></a><span data-ttu-id="50976-186">정수 산술 오버플로</span><span class="sxs-lookup"><span data-stu-id="50976-186">Integer arithmetic overflow</span></span>

<span data-ttu-id="50976-187">정수를 0으로 나누면 항상 <xref:System.DivideByZeroException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="50976-187">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

<span data-ttu-id="50976-188">정수 산술 오버플로의 경우 [checked 또는 unchecked](../keywords/checked-and-unchecked.md)일 수 있는 오버플로 검사 컨텍스트는 결과 동작을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-188">In case of integer arithmetic overflow, an overflow checking context, which can be [checked or unchecked](../keywords/checked-and-unchecked.md), controls the resulting behavior:</span></span>

- <span data-ttu-id="50976-189">checked 컨텍스트인 경우 상수 식에서 오버플로가 일어나면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-189">In a checked context, if overflow happens in a constant expression, a compile-time error occurs.</span></span> <span data-ttu-id="50976-190">그렇지 않으면, 런타임 시 작업을 수행하는 경우 <xref:System.OverflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="50976-190">Otherwise, when the operation is performed at run time, an <xref:System.OverflowException> is thrown.</span></span>
- <span data-ttu-id="50976-191">unchecked 컨텍스트에서는 대상 형식에 맞지 않는 상위 비트를 버려서 해당 결과가 잘려집니다.</span><span class="sxs-lookup"><span data-stu-id="50976-191">In an unchecked context, the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>

<span data-ttu-id="50976-192">[checked 및 unchecked](../keywords/checked-and-unchecked.md) 문과 함께 `checked` 및 `unchecked` 연산자를 사용하여 식을 계산하는 오버플로 검사 컨텍스트를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-192">Along with the [checked and unchecked](../keywords/checked-and-unchecked.md) statements, you can use the `checked` and `unchecked` operators to control the overflow checking context, in which an expression is evaluated:</span></span>

[!code-csharp-interactive[checked and unchecked](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#CheckedUnchecked)]

<span data-ttu-id="50976-193">기본적으로 산술 연산은 *unchecked* 컨텍스트에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-193">By default, arithmetic operations occur in an *unchecked* context.</span></span>

### <a name="floating-point-arithmetic-overflow"></a><span data-ttu-id="50976-194">부동 소수점 산술 오버플로</span><span class="sxs-lookup"><span data-stu-id="50976-194">Floating-point arithmetic overflow</span></span>

<span data-ttu-id="50976-195">`float` 및 `double` 형식을 포함한 산술 연산은 예외를 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-195">Arithmetic operations with the `float` and `double` types never throw an exception.</span></span> <span data-ttu-id="50976-196">이러한 형식의 산술 연산 결과는 무한대를 나타내거나 숫자가 아닌 특수 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-196">The result of arithmetic operations with those types can be one of special values that represent infinity and not-a-number:</span></span>

[!code-csharp-interactive[double non-finite values](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointOverflow)]

<span data-ttu-id="50976-197">`decimal` 형식의 피연산자의 경우 산술 오버플로는 항상 <xref:System.OverflowException>을 throw하고, 0으로 나누기는 항상 <xref:System.DivideByZeroException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-197">For the operands of the `decimal` type, arithmetic overflow always throws an <xref:System.OverflowException> and division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

## <a name="round-off-errors"></a><span data-ttu-id="50976-198">반올림 오류</span><span class="sxs-lookup"><span data-stu-id="50976-198">Round-off errors</span></span>

<span data-ttu-id="50976-199">실수 및 부동 소수점 산술의 부동 소수점 표현을 일반적으로 제한함으로 인해 부동 소수점 형식을 사용하는 계산에서 반올림 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-199">Because of general limitations of the floating-point representation of real numbers and floating-point arithmetic, the round-off errors might occur in calculations with floating-point types.</span></span> <span data-ttu-id="50976-200">즉, 생성된 식의 결과는 예상되는 수학적 결과와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-200">That is, the produced result of an expression might differ from the expected mathematical result.</span></span> <span data-ttu-id="50976-201">다음 예제에서는 이러한 몇몇 사례에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="50976-201">The following example demonstrates several such cases:</span></span>

[!code-csharp-interactive[round-off errors](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#RoundOffErrors)]

<span data-ttu-id="50976-202">자세한 내용은 [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks) 또는 [System.Decimal](/dotnet/api/system.decimal#remarks) 참조 페이지에서 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50976-202">For more information, see remarks at [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks), or [System.Decimal](/dotnet/api/system.decimal#remarks) reference pages.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="50976-203">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="50976-203">Operator overloadability</span></span>

<span data-ttu-id="50976-204">사용자 정의 형식은 단항(`++`, `--`, `+` 및 `-`) 및 이진(`*`, `/`, `%`, `+` 및 `-`) 산술 연산자를 [오버로드](operator-overloading.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-204">A user-defined type can [overload](operator-overloading.md) the unary (`++`, `--`, `+`, and `-`) and binary (`*`, `/`, `%`, `+`, and `-`) arithmetic operators.</span></span> <span data-ttu-id="50976-205">이항 연산자가 오버로드되면 해당하는 복합 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="50976-205">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="50976-206">사용자 정의 형식은 복합 대입 연산자를 명시적으로 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50976-206">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="50976-207">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="50976-207">C# language specification</span></span>

<span data-ttu-id="50976-208">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50976-208">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="50976-209">후위 증가 및 감소 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-209">Postfix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [<span data-ttu-id="50976-210">전위 증가 및 감소 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-210">Prefix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [<span data-ttu-id="50976-211">단항 더하기 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-211">Unary plus operator</span></span>](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [<span data-ttu-id="50976-212">단항 빼기 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-212">Unary minus operator</span></span>](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [<span data-ttu-id="50976-213">곱하기 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-213">Multiplication operator</span></span>](~/_csharplang/spec/expressions.md#multiplication-operator)
- [<span data-ttu-id="50976-214">나누기 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-214">Division operator</span></span>](~/_csharplang/spec/expressions.md#division-operator)
- [<span data-ttu-id="50976-215">나머지 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-215">Remainder operator</span></span>](~/_csharplang/spec/expressions.md#remainder-operator)
- [<span data-ttu-id="50976-216">더하기 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-216">Addition operator</span></span>](~/_csharplang/spec/expressions.md#addition-operator)
- [<span data-ttu-id="50976-217">빼기 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-217">Subtraction operator</span></span>](~/_csharplang/spec/expressions.md#subtraction-operator)
- [<span data-ttu-id="50976-218">복합 할당</span><span class="sxs-lookup"><span data-stu-id="50976-218">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="50976-219">Checked 및 Unchecked 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-219">The checked and unchecked operators</span></span>](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)
- [<span data-ttu-id="50976-220">숫자 승격</span><span class="sxs-lookup"><span data-stu-id="50976-220">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="50976-221">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50976-221">See also</span></span>

- [<span data-ttu-id="50976-222">C# 참조</span><span class="sxs-lookup"><span data-stu-id="50976-222">C# reference</span></span>](../index.md)
- [<span data-ttu-id="50976-223">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="50976-223">C# operators</span></span>](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [<span data-ttu-id="50976-224">.NET의 숫자</span><span class="sxs-lookup"><span data-stu-id="50976-224">Numerics in .NET</span></span>](../../../standard/numerics.md)
