---
title: 산술 연산자 - C# 참조
description: 숫자 형식이 포함된 곱하기, 나누기, 나머지, 더하기 및 빼기 작업을 수행하는 C# 연산자에 대해 알아봅니다.
ms.date: 05/11/2020
author: pkulikov
f1_keywords:
- ++_CSharpKeyword
- --_CSharpKeyword
- '*_CSharpKeyword'
- /_CSharpKeyword
- '%_CSharpKeyword'
- +_CSharpKeyword
- -_CSharpKeyword
- '%=_CSharpKeyword'
- '*=_CSharpKeyword'
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
ms.openlocfilehash: f5da9c4433ffcf3e6a110bbb1543343289240778
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916942"
---
# <a name="arithmetic-operators-c-reference"></a><span data-ttu-id="09a9b-103">산술 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="09a9b-103">Arithmetic operators (C# reference)</span></span>

<span data-ttu-id="09a9b-104">다음 연산자는 숫자 형식 피연산자를 포함한 산술 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-104">The following operators perform arithmetic operations with operands of numeric types:</span></span>

- <span data-ttu-id="09a9b-105">단항 [`++`(증분)](#increment-operator-), [`--`(감소)](#decrement-operator---), [`+`(더하기)](#unary-plus-and-minus-operators), [`-`(빼기)](#unary-plus-and-minus-operators) 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-105">Unary [`++` (increment)](#increment-operator-), [`--` (decrement)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators), and [`-` (minus)](#unary-plus-and-minus-operators) operators</span></span>
- <span data-ttu-id="09a9b-106">이진 [`*`(곱하기)](#multiplication-operator-), [`/`(나누기)](#division-operator-), [`%`(나머지)](#remainder-operator-), [`+`(더하기)](#addition-operator-) 및 [`-`(빼기)](#subtraction-operator--) 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-106">Binary [`*` (multiplication)](#multiplication-operator-), [`/` (division)](#division-operator-), [`%` (remainder)](#remainder-operator-), [`+` (addition)](#addition-operator-), and [`-` (subtraction)](#subtraction-operator--) operators</span></span>

<span data-ttu-id="09a9b-107">해당 연산자는 모든 [정수](../builtin-types/integral-numeric-types.md) 및 [부동 소수점](../builtin-types/floating-point-numeric-types.md) 숫자 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-107">Those operators are supported by all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

<span data-ttu-id="09a9b-108">정수 형식의 경우 이러한 연산자(`++` 및 `--` 연산자 제외)는 `int`, `uint`, `long`및 `ulong` 형식에 대해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-108">In the case of integral types, those operators (except the `++` and `--` operators) are defined for the `int`, `uint`, `long`, and `ulong` types.</span></span> <span data-ttu-id="09a9b-109">피연산자가 다른 정수 형식(`sbyte`, `byte`, `short`, `ushort` 또는 `char`)인 경우, 해당 값은 연산의 결과 형식이기도 한 `int` 형식으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-109">When operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type, which is also the result type of an operation.</span></span> <span data-ttu-id="09a9b-110">피연산자가 정수 형식 또는 부동 소수점 형식인 경우 해당 형식이 있으면 값은 가장 근사한 포함하는 형식으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-110">When operands are of different integral or floating-point types, their values are converted to the closest containing type, if such a type exists.</span></span> <span data-ttu-id="09a9b-111">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [숫자 승격](~/_csharplang/spec/expressions.md#numeric-promotions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09a9b-111">For more information, see the [Numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span> <span data-ttu-id="09a9b-112">`++` 및 `--` 연산자는 모든 정수 형식 및 부동 소수점 숫자 형식과 [char](../builtin-types/char.md) 형식에 대해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-112">The `++` and `--` operators are defined for all integral and floating-point numeric types and the [char](../builtin-types/char.md) type.</span></span>

## <a name="increment-operator-"></a><span data-ttu-id="09a9b-113">증가 연산자 ++</span><span class="sxs-lookup"><span data-stu-id="09a9b-113">Increment operator ++</span></span>

<span data-ttu-id="09a9b-114">단항 증가 연산자(`++`)는 피연산자를 1씩 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-114">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="09a9b-115">피연산자는 변수, [속성](../../programming-guide/classes-and-structs/properties.md) 액세스 또는 [인덱서](../../programming-guide/indexers/index.md) 액세스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-115">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="09a9b-116">증가 연산자는 후위 증가 연산자 `x++` 및 전위 증가 연산자 `++x`라는 두 가지 양식으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-116">The increment operator is supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

### <a name="postfix-increment-operator"></a><span data-ttu-id="09a9b-117">후위 증가 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-117">Postfix increment operator</span></span>

<span data-ttu-id="09a9b-118">`x++`의 결과는 다음 예제와 같이 연산 *전* `x`의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-118">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](snippets/shared/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a><span data-ttu-id="09a9b-119">후위 증가 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-119">Prefix increment operator</span></span>

<span data-ttu-id="09a9b-120">`++x`의 결과는 다음 예제와 같이 연산 *후* `x`의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-120">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](snippets/shared/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a><span data-ttu-id="09a9b-121">감소 연산자 --</span><span class="sxs-lookup"><span data-stu-id="09a9b-121">Decrement operator --</span></span>

<span data-ttu-id="09a9b-122">단항 감소 연산자(`--`)는 피연산자를 1씩 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-122">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="09a9b-123">피연산자는 변수, [속성](../../programming-guide/classes-and-structs/properties.md) 액세스 또는 [인덱서](../../programming-guide/indexers/index.md) 액세스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-123">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="09a9b-124">감소 연산자는 후위 감소 연산자 `x--` 및 전위 감소 연산자 `--x`라는 두 가지 양식으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-124">The decrement operator is supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

### <a name="postfix-decrement-operator"></a><span data-ttu-id="09a9b-125">후위 감소 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-125">Postfix decrement operator</span></span>

<span data-ttu-id="09a9b-126">`x--`의 결과는 다음 예제와 같이 연산 *전* `x`의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-126">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](snippets/shared/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a><span data-ttu-id="09a9b-127">후위 감소 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-127">Prefix decrement operator</span></span>

<span data-ttu-id="09a9b-128">`--x`의 결과는 다음 예제와 같이 연산 *후* `x`의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-128">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](snippets/shared/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a><span data-ttu-id="09a9b-129">단항 더하기 및 빼기 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-129">Unary plus and minus operators</span></span>

<span data-ttu-id="09a9b-130">단항 `+` 연산자는 피연산자의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-130">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="09a9b-131">단항 `-` 연산자는 피연산자의 숫자 부정을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-131">The unary `-` operator computes the numeric negation of its operand.</span></span>

[!code-csharp-interactive[unary plus and minus](snippets/shared/ArithmeticOperators.cs#UnaryPlusAndMinus)]

<span data-ttu-id="09a9b-132">단항 `-` 연산자는 [ulong](../builtin-types/integral-numeric-types.md) 형식을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-132">The [ulong](../builtin-types/integral-numeric-types.md) type doesn't support the unary `-` operator.</span></span>

## <a name="multiplication-operator-"></a><span data-ttu-id="09a9b-133">곱하기 연산자 \*</span><span class="sxs-lookup"><span data-stu-id="09a9b-133">Multiplication operator \*</span></span>

<span data-ttu-id="09a9b-134">곱하기 연산자 `*`는 피연산자의 곱을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-134">The multiplication operator `*` computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication operator](snippets/shared/ArithmeticOperators.cs#Multiplication)]

<span data-ttu-id="09a9b-135">단항 `*` 연산자는 [포인터 간접 참조 연산자](pointer-related-operators.md#pointer-indirection-operator-)입니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-135">The unary `*` operator is the [pointer indirection operator](pointer-related-operators.md#pointer-indirection-operator-).</span></span>

## <a name="division-operator-"></a><span data-ttu-id="09a9b-136">나누기 연산자 /</span><span class="sxs-lookup"><span data-stu-id="09a9b-136">Division operator /</span></span>

<span data-ttu-id="09a9b-137">나누기 연산자 `/`는 오른쪽 피연산자로 왼쪽 피연산자를 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-137">The division operator `/` divides its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-division"></a><span data-ttu-id="09a9b-138">정수 나누기</span><span class="sxs-lookup"><span data-stu-id="09a9b-138">Integer division</span></span>

<span data-ttu-id="09a9b-139">정수 형식의 피연산자의 경우 `/` 연산자의 결과는 정수 형식이고 두 피연산자의 몫과 동일한 값은 0으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-139">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](snippets/shared/ArithmeticOperators.cs#IntegerDivision)]

<span data-ttu-id="09a9b-140">두 피연산자의 몫을 부동 소수점 숫자로 가져오려면 `float`, `double` 또는 `decimal` 형식을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="09a9b-140">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](snippets/shared/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a><span data-ttu-id="09a9b-141">부동 소수점 나누기</span><span class="sxs-lookup"><span data-stu-id="09a9b-141">Floating-point division</span></span>

<span data-ttu-id="09a9b-142">`float`, `double` 및 `decimal` 형식의 경우 `/` 연산자의 결과는 두 피연산자의 몫입니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-142">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](snippets/shared/ArithmeticOperators.cs#FloatingPointDivision)]

<span data-ttu-id="09a9b-143">피연산자 중 하나가 `decimal`이면 `float` 또는 `double` 모두 `decimal`로 암시적으로 변환할 수 없기 때문에 나머지 피연산자는 `float` 또는 `double`일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-143">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="09a9b-144">`float` 또는 `double` 피연산자를 `decimal` 형식으로 암시적으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-144">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="09a9b-145">숫자 형식 간의 변환에 대한 자세한 내용은 [기본 제공 숫자 변환](../builtin-types/numeric-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09a9b-145">For more information about conversions between numeric types, see [Built-in numeric conversions](../builtin-types/numeric-conversions.md).</span></span>

## <a name="remainder-operator-"></a><span data-ttu-id="09a9b-146">나머지 연산자 %</span><span class="sxs-lookup"><span data-stu-id="09a9b-146">Remainder operator %</span></span>

<span data-ttu-id="09a9b-147">나머지 연산자 `%`는 왼쪽 피연산자를 오른쪽 피연산자로 나눈 후 나머지를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-147">The remainder operator `%` computes the remainder after dividing its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-remainder"></a><span data-ttu-id="09a9b-148">정수 나머지</span><span class="sxs-lookup"><span data-stu-id="09a9b-148">Integer remainder</span></span>

<span data-ttu-id="09a9b-149">정수 형식의 피연산자의 경우 `a % b`의 결과가 `a - (a / b) * b`에서 생성된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-149">For the operands of integer types, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="09a9b-150">다음 예와 같이 0이 아닌 나머지의 부호는 왼쪽 피연산자와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-150">The sign of the non-zero remainder is the same as that of the left-hand operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](snippets/shared/ArithmeticOperators.cs#IntegerRemainder)]

<span data-ttu-id="09a9b-151"><xref:System.Math.DivRem%2A?displayProperty=nameWithType> 메서드를 사용하여 정수 나누기 및 나머지 결과를 모두 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-151">Use the <xref:System.Math.DivRem%2A?displayProperty=nameWithType> method to compute both integer division and remainder results.</span></span>

### <a name="floating-point-remainder"></a><span data-ttu-id="09a9b-152">부동 소수점 나머지</span><span class="sxs-lookup"><span data-stu-id="09a9b-152">Floating-point remainder</span></span>

<span data-ttu-id="09a9b-153">`float` 및 `double` 피연산자의 경우 유한 `x` 및 `y`에 대한 `x % y`의 결과는 다음과 같은 `z` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-153">For the `float` and `double` operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="09a9b-154">0이 아닌 경우 `z`의 부호는 `x`의 부호와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-154">The sign of `z`, if non-zero, is the same as the sign of `x`.</span></span>
- <span data-ttu-id="09a9b-155">`z`의 절대 값은 `|x| - n * |y|`에서 생성된 값입니다. 여기서 `n`은 `|x| / |y|`보다 작거나 같은 가능한 최대 정수이고 `|x|` 및 `|y|`는 각각 `x` 및 `y`의 절대 값입니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-155">The absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="09a9b-156">나머지 계산 방법은 정수 피연산자에 사용되는 것과 유사하지만 IEEE 754 사양과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-156">This method of computing the remainder is analogous to that used for integer operands, but different from the IEEE 754 specification.</span></span> <span data-ttu-id="09a9b-157">IEEE 754 사양을 준수하는 나머지 작업이 필요한 경우 <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-157">If you need the remainder operation that complies with the IEEE 754 specification, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="09a9b-158">무한 피연산자가 있는 `%` 연산자의 동작에 대한 자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [나머지 연산자](~/_csharplang/spec/expressions.md#remainder-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09a9b-158">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="09a9b-159">`decimal` 피연산자의 경우 나머지 연산자 `%`는 <xref:System.Decimal?displayProperty=nameWithType> 형식의 [나머지 연산자](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>)와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-159">For the `decimal` operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

<span data-ttu-id="09a9b-160">다음 예제에서는 부동 소수점 피연산자를 포함한 나머지 연산자의 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-160">The following example demonstrates the behavior of the remainder operator with floating-point operands:</span></span>

[!code-csharp-interactive[floating-point remainder](snippets/shared/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a><span data-ttu-id="09a9b-161">더하기 연산자 +</span><span class="sxs-lookup"><span data-stu-id="09a9b-161">Addition operator +</span></span>

<span data-ttu-id="09a9b-162">더하기 연산자 `+`는 피연산자의 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-162">The addition operator `+` computes the sum of its operands:</span></span>

[!code-csharp-interactive[addition operator](snippets/shared/ArithmeticOperators.cs#Addition)]

<span data-ttu-id="09a9b-163">문자열 연결 및 대리자 조합의 경우 `+` 연산자를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-163">You can also use the `+` operator for string concatenation and delegate combination.</span></span> <span data-ttu-id="09a9b-164">자세한 내용은 참조는 [`+` 및 `+=`연산자](addition-operator.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09a9b-164">For more information, see the [`+` and `+=` operators](addition-operator.md) article.</span></span>

## <a name="subtraction-operator--"></a><span data-ttu-id="09a9b-165">빼기 연산자 -</span><span class="sxs-lookup"><span data-stu-id="09a9b-165">Subtraction operator -</span></span>

<span data-ttu-id="09a9b-166">빼기 연산자 `-`는 왼쪽 피연산자에서 오른쪽 피연산자를 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-166">The subtraction operator `-` subtracts its right-hand operand from its left-hand operand:</span></span>

[!code-csharp-interactive[subtraction operator](snippets/shared/ArithmeticOperators.cs#Subtraction)]

<span data-ttu-id="09a9b-167">대리자 제거를 위해 `-` 연산자를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-167">You can also use the `-` operator for delegate removal.</span></span> <span data-ttu-id="09a9b-168">자세한 내용은 참조는 [`-` 및 `-=`연산자](subtraction-operator.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09a9b-168">For more information, see the [`-` and `-=` operators](subtraction-operator.md) article.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="09a9b-169">복합 할당</span><span class="sxs-lookup"><span data-stu-id="09a9b-169">Compound assignment</span></span>

<span data-ttu-id="09a9b-170">이진 연산자(`op`)의 경우 양식의 복합 할당 식</span><span class="sxs-lookup"><span data-stu-id="09a9b-170">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="09a9b-171">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-171">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="09a9b-172">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-172">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="09a9b-173">다음 예제에서는 산술 연산자를 사용하는 복합 할당의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-173">The following example demonstrates the usage of compound assignment with arithmetic operators:</span></span>

[!code-csharp-interactive[compound assignment](snippets/shared/ArithmeticOperators.cs#CompoundAssignment)]

<span data-ttu-id="09a9b-174">[숫자 승격](~/_csharplang/spec/expressions.md#numeric-promotions)으로 인해 `op` 연산의 결과가 암시적으로 `x`의 `T` 형식으로 변환되지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-174">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="09a9b-175">이 경우 `op`가 미리 정의된 연산자이고 연산의 결과가 명시적으로 `x`의 `T` 형식으로 변환 가능하다면 `x op= y` 양식의 복합 할당 식이 `x = (T)(x op y)`에 해당합니다. 단 `x`는 한 번만 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-175">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="09a9b-176">다음 예제에서는 해당 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-176">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](snippets/shared/ArithmeticOperators.cs#CompoundAssignmentWithCast)]

<span data-ttu-id="09a9b-177">각각 `+=` 및 `-=` 연산자를 사용하여 [이벤트](../keywords/event.md)에서 구독하거나 구독을 취소할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-177">You also use the `+=` and `-=` operators to subscribe to and unsubscribe from an [event](../keywords/event.md), respectively.</span></span> <span data-ttu-id="09a9b-178">자세한 내용은 [이벤트를 구독 및 구독 취소하는 방법](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09a9b-178">For more information, see [How to subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-precedence-and-associativity"></a><span data-ttu-id="09a9b-179">연산자 우선 순위 및 결합성</span><span class="sxs-lookup"><span data-stu-id="09a9b-179">Operator precedence and associativity</span></span>

<span data-ttu-id="09a9b-180">다음 목록에서는 산술 연산자를 가장 높은 우선 순위부터 가장 낮은 것으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-180">The following list orders arithmetic operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="09a9b-181">후위 증가 `x++` 및 감소 `x--` 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-181">Postfix increment `x++` and decrement `x--` operators</span></span>
- <span data-ttu-id="09a9b-182">전위 증가 `++x` 및 감소 `--x` 및 단항 `+` 및 `-` 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-182">Prefix increment `++x` and decrement `--x` and unary `+` and `-` operators</span></span>
- <span data-ttu-id="09a9b-183">곱하기 `*`, `/` 및 `%` 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-183">Multiplicative `*`, `/`, and `%` operators</span></span>
- <span data-ttu-id="09a9b-184">가감 `+` 및 `-` 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-184">Additive `+` and `-` operators</span></span>

<span data-ttu-id="09a9b-185">이진 산술 연산자는 왼쪽 결합형입니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-185">Binary arithmetic operators are left-associative.</span></span> <span data-ttu-id="09a9b-186">즉, 우선 순위 수준이 같은 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-186">That is, operators with the same precedence level are evaluated from left to right.</span></span>

<span data-ttu-id="09a9b-187">괄호(`()`)를 사용하여 연산자 우선 순위와 연결에 따라 주어진 계산 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-187">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence and associativity.</span></span>

[!code-csharp-interactive[precedence and associativity](snippets/shared/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

<span data-ttu-id="09a9b-188">우선 순위 수준에 따라 정렬된 전체 연산자 목록은 [C# 연산자](index.md#operator-precedence) 문서의 [연산자 우선 순위](index.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09a9b-188">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="arithmetic-overflow-and-division-by-zero"></a><span data-ttu-id="09a9b-189">산술 오버플로 및 0으로 나누기</span><span class="sxs-lookup"><span data-stu-id="09a9b-189">Arithmetic overflow and division by zero</span></span>

<span data-ttu-id="09a9b-190">산술 연산의 결과가 관련된 숫자 형식의 가능한 유한 값 범위를 벗어나는 경우 산술 연산자의 동작은 해당하는 피연산자의 형식에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-190">When the result of an arithmetic operation is outside the range of possible finite values of the involved numeric type, the behavior of an arithmetic operator depends on the type of its operands.</span></span>

### <a name="integer-arithmetic-overflow"></a><span data-ttu-id="09a9b-191">정수 산술 오버플로</span><span class="sxs-lookup"><span data-stu-id="09a9b-191">Integer arithmetic overflow</span></span>

<span data-ttu-id="09a9b-192">정수를 0으로 나누면 항상 <xref:System.DivideByZeroException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-192">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

<span data-ttu-id="09a9b-193">정수 산술 오버플로의 경우 [checked 또는 unchecked](../keywords/checked-and-unchecked.md)일 수 있는 오버플로 검사 컨텍스트는 결과 동작을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-193">In case of integer arithmetic overflow, an overflow checking context, which can be [checked or unchecked](../keywords/checked-and-unchecked.md), controls the resulting behavior:</span></span>

- <span data-ttu-id="09a9b-194">checked 컨텍스트인 경우 상수 식에서 오버플로가 일어나면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-194">In a checked context, if overflow happens in a constant expression, a compile-time error occurs.</span></span> <span data-ttu-id="09a9b-195">그렇지 않으면, 런타임 시 작업을 수행하는 경우 <xref:System.OverflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-195">Otherwise, when the operation is performed at run time, an <xref:System.OverflowException> is thrown.</span></span>
- <span data-ttu-id="09a9b-196">unchecked 컨텍스트에서는 대상 형식에 맞지 않는 상위 비트를 버려서 해당 결과가 잘려집니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-196">In an unchecked context, the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>

<span data-ttu-id="09a9b-197">[checked 및 unchecked](../keywords/checked-and-unchecked.md) 문과 함께 `checked` 및 `unchecked` 연산자를 사용하여 식을 계산하는 오버플로 검사 컨텍스트를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-197">Along with the [checked and unchecked](../keywords/checked-and-unchecked.md) statements, you can use the `checked` and `unchecked` operators to control the overflow checking context, in which an expression is evaluated:</span></span>

[!code-csharp-interactive[checked and unchecked](snippets/shared/ArithmeticOperators.cs#CheckedUnchecked)]

<span data-ttu-id="09a9b-198">기본적으로 산술 연산은 *unchecked* 컨텍스트에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-198">By default, arithmetic operations occur in an *unchecked* context.</span></span>

### <a name="floating-point-arithmetic-overflow"></a><span data-ttu-id="09a9b-199">부동 소수점 산술 오버플로</span><span class="sxs-lookup"><span data-stu-id="09a9b-199">Floating-point arithmetic overflow</span></span>

<span data-ttu-id="09a9b-200">`float` 및 `double` 형식을 포함한 산술 연산은 예외를 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-200">Arithmetic operations with the `float` and `double` types never throw an exception.</span></span> <span data-ttu-id="09a9b-201">이러한 형식의 산술 연산 결과는 무한대를 나타내거나 숫자가 아닌 특수 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-201">The result of arithmetic operations with those types can be one of special values that represent infinity and not-a-number:</span></span>

[!code-csharp-interactive[double non-finite values](snippets/shared/ArithmeticOperators.cs#FloatingPointOverflow)]

<span data-ttu-id="09a9b-202">`decimal` 형식의 피연산자의 경우 산술 오버플로는 항상 <xref:System.OverflowException>을 throw하고, 0으로 나누기는 항상 <xref:System.DivideByZeroException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-202">For the operands of the `decimal` type, arithmetic overflow always throws an <xref:System.OverflowException> and division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

## <a name="round-off-errors"></a><span data-ttu-id="09a9b-203">반올림 오류</span><span class="sxs-lookup"><span data-stu-id="09a9b-203">Round-off errors</span></span>

<span data-ttu-id="09a9b-204">실수 및 부동 소수점 산술의 부동 소수점 표현을 일반적으로 제한함으로 인해 부동 소수점 형식을 사용하는 계산에서 반올림 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-204">Because of general limitations of the floating-point representation of real numbers and floating-point arithmetic, round-off errors might occur in calculations with floating-point types.</span></span> <span data-ttu-id="09a9b-205">즉, 생성된 식의 결과는 예상되는 수학적 결과와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-205">That is, the produced result of an expression might differ from the expected mathematical result.</span></span> <span data-ttu-id="09a9b-206">다음 예제에서는 이러한 몇몇 사례에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-206">The following example demonstrates several such cases:</span></span>

[!code-csharp-interactive[round-off errors](snippets/shared/ArithmeticOperators.cs#RoundOffErrors)]

<span data-ttu-id="09a9b-207">자세한 내용은 [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks) 또는 [System.Decimal](/dotnet/api/system.decimal#remarks) 참조 페이지에서 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09a9b-207">For more information, see remarks at the [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks), or [System.Decimal](/dotnet/api/system.decimal#remarks) reference pages.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="09a9b-208">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="09a9b-208">Operator overloadability</span></span>

<span data-ttu-id="09a9b-209">사용자 정의 형식은 단항(`++`, `--`, `+` 및 `-`) 및 이진(`*`, `/`, `%`, `+` 및 `-`) 산술 연산자를 [오버로드](operator-overloading.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-209">A user-defined type can [overload](operator-overloading.md) the unary (`++`, `--`, `+`, and `-`) and binary (`*`, `/`, `%`, `+`, and `-`) arithmetic operators.</span></span> <span data-ttu-id="09a9b-210">이항 연산자가 오버로드되면 해당하는 복합 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-210">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="09a9b-211">사용자 정의 형식은 복합 대입 연산자를 명시적으로 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09a9b-211">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="09a9b-212">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="09a9b-212">C# language specification</span></span>

<span data-ttu-id="09a9b-213">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09a9b-213">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="09a9b-214">후위 증가 및 감소 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-214">Postfix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [<span data-ttu-id="09a9b-215">전위 증가 및 감소 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-215">Prefix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [<span data-ttu-id="09a9b-216">단항 더하기 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-216">Unary plus operator</span></span>](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [<span data-ttu-id="09a9b-217">단항 빼기 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-217">Unary minus operator</span></span>](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [<span data-ttu-id="09a9b-218">곱하기 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-218">Multiplication operator</span></span>](~/_csharplang/spec/expressions.md#multiplication-operator)
- [<span data-ttu-id="09a9b-219">나누기 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-219">Division operator</span></span>](~/_csharplang/spec/expressions.md#division-operator)
- [<span data-ttu-id="09a9b-220">나머지 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-220">Remainder operator</span></span>](~/_csharplang/spec/expressions.md#remainder-operator)
- [<span data-ttu-id="09a9b-221">더하기 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-221">Addition operator</span></span>](~/_csharplang/spec/expressions.md#addition-operator)
- [<span data-ttu-id="09a9b-222">빼기 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-222">Subtraction operator</span></span>](~/_csharplang/spec/expressions.md#subtraction-operator)
- [<span data-ttu-id="09a9b-223">복합 할당</span><span class="sxs-lookup"><span data-stu-id="09a9b-223">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="09a9b-224">Checked 및 Unchecked 연산자</span><span class="sxs-lookup"><span data-stu-id="09a9b-224">The checked and unchecked operators</span></span>](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)
- [<span data-ttu-id="09a9b-225">숫자 승격</span><span class="sxs-lookup"><span data-stu-id="09a9b-225">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="09a9b-226">참조</span><span class="sxs-lookup"><span data-stu-id="09a9b-226">See also</span></span>

- [<span data-ttu-id="09a9b-227">C# 참조</span><span class="sxs-lookup"><span data-stu-id="09a9b-227">C# reference</span></span>](../index.md)
- [<span data-ttu-id="09a9b-228">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="09a9b-228">C# operators and expressions</span></span>](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [<span data-ttu-id="09a9b-229">.NET의 숫자</span><span class="sxs-lookup"><span data-stu-id="09a9b-229">Numerics in .NET</span></span>](../../../standard/numerics.md)
