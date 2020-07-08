---
title: 부울 논리 연산자 - C# 참조
description: 부울 피연산자를 사용하여 논리 부정, 결합(AND) 및 포괄적/배타적 분리(OR) 작업을 수행하는 C# 연산자에 대해 알아봅니다.
ms.date: 06/29/2020
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
helpviewer_keywords:
- logical operators [C#]
- short-circuiting operators [C#]
- logical negation operator [C#]
- NOT operator [C#]
- '! operator [C#]'
- AND operator [C#]
- ampersand operator [C#]
- conjunction operator [C#]
- '& operator [C#]'
- exclusive OR operator [C#]
- XOR operator [C#]
- ^ operator [C#]
- OR operator [C#]
- disjunction operator [C#]
- '| operator [C#]'
- conditional AND operator [C#]
- short-circuiting AND operator [C#]
- '&& operator [C#]'
- conditional OR operator [C#]
- short-circuiting OR operator [C#]
- '|| operator [C#]'
ms.openlocfilehash: a19c804c624153ef608885bc6493537302275765
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618196"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="51244-103">부울 논리 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="51244-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="51244-104">다음 연산자는 [부울](../builtin-types/bool.md) 피연산자를 사용하여 논리 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-104">The following operators perform logical operations with [bool](../builtin-types/bool.md) operands:</span></span>

- <span data-ttu-id="51244-105">단항 [`!`(논리 부정)](#logical-negation-operator-) 연산자.</span><span class="sxs-lookup"><span data-stu-id="51244-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="51244-106">이진 [`&`(논리 AND)](#logical-and-operator-), [`|`(논리 OR)](#logical-or-operator-) 및 [`^`(논리 배타적 OR)](#logical-exclusive-or-operator-) 연산자.</span><span class="sxs-lookup"><span data-stu-id="51244-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="51244-107">해당 연산자는 항상 두 피연산자를 모두 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="51244-108">이진 [`&&`(조건부 논리 AND)](#conditional-logical-and-operator-) 및 [`||`(조건부 논리 OR)](#conditional-logical-or-operator-) 연산자.</span><span class="sxs-lookup"><span data-stu-id="51244-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="51244-109">해당 연산자는 필요한 경우에만 오른쪽 피연산자를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="51244-110">[정수](../builtin-types/integral-numeric-types.md) 형식 피연산자의 경우 `&`, `|` 및 `^` 연산자는 비트 논리 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-110">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="51244-111">자세한 내용은 [비트 및 시프트 연산자](bitwise-and-shift-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51244-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="51244-112">논리 부정 연산자 !</span><span class="sxs-lookup"><span data-stu-id="51244-112">Logical negation operator !</span></span>

<span data-ttu-id="51244-113">단항 접두사 `!` 연산자는 해당 피연산자의 논리 부정을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-113">The unary prefix `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="51244-114">즉, 피연산자가 `false`로 평가되는 경우 `true`를 생성하고, 피연산자가 `true`로 평가되는 경우 `false`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](snippets/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="51244-115">C# 8.0부터 단항 후위 `!` 연산자는 [null 허용 연산자](null-forgiving.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-115">Beginning with C# 8.0, the unary postfix `!` operator is the [null-forgiving operator](null-forgiving.md).</span></span>

## <a name="logical-and-operator-amp"></a><a name="logical-and-operator-"></a> <span data-ttu-id="51244-116">논리 AND 연산자 &amp;</span><span class="sxs-lookup"><span data-stu-id="51244-116">Logical AND operator &amp;</span></span>

<span data-ttu-id="51244-117">`&` 연산자는 해당 피연산자의 논리 AND를 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-117">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="51244-118">`x` 및 `y`가 모두 `true`로 평가되면 `x & y`의 결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-118">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="51244-119">그렇지 않으면 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-119">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="51244-120">왼쪽 피연산자가 `false`로 평가되더라도 `&` 연산자는 두 피연산자를 평가하여 오른쪽 피연산자의 값에 관계없이 `false`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-120">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the operation result is `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="51244-121">다음 예제에서 `&` 연산자의 오른쪽 피연산자는 왼쪽 피연산자의 값과 관계없이 수행되는 메서드 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-121">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](snippets/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="51244-122">[조건부 논리 AND 연산자](#conditional-logical-and-operator-) `&&`도 해당 피연산자의 논리 AND를 계산하지만, 왼쪽 피연산자가 `false`로 평가되는 경우에는 오른쪽 피연산자를 평가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51244-122">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="51244-123">[정수 형식](../builtin-types/integral-numeric-types.md) 피연산자의 경우 `&` 연산자는 해당 피연산자의 [비트 논리 AND](bitwise-and-shift-operators.md#logical-and-operator-)를 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-123">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="51244-124">단항 `&` 연산자는 [address-of 연산자](pointer-related-operators.md#address-of-operator-)입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-124">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="51244-125">논리 배타적 OR 연산자 ^</span><span class="sxs-lookup"><span data-stu-id="51244-125">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="51244-126">`^` 연산자는 해당 피연산자의 논리 XOR이라고도 하는 논리 배타적 OR을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-126">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="51244-127">`x`가 `true`로 평가되고 `y`가 `false`로 평가되거나, `x`가 `false`로 평가되고 `y`가 `true`로 평가되는 경우 `x ^ y`의 결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-127">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="51244-128">그렇지 않으면 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-128">Otherwise, the result is `false`.</span></span> <span data-ttu-id="51244-129">즉, `bool` 피연산자의 경우 `^` 연산자는 [같지 않음 연산자](equality-operators.md#inequality-operator-) `!=`과 같은 결과를 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-129">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](snippets/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="51244-130">[정수 숫자 형식](../builtin-types/integral-numeric-types.md) 피연산자의 경우 `^` 연산자는 해당 피연산자의 [비트 논리 배타적 OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-130">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="51244-131">논리 OR 연산자 |</span><span class="sxs-lookup"><span data-stu-id="51244-131">Logical OR operator |</span></span>

<span data-ttu-id="51244-132">`|` 연산자는 해당 피연산자의 논리 OR을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-132">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="51244-133">`x` 또는 `y`가 `true`로 평가되면 `x | y`의 결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-133">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="51244-134">그렇지 않으면 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-134">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="51244-135">왼쪽 피연산자가 `true`로 평가되더라도 `|` 연산자는 두 피연산자를 평가하여 오른쪽 피연산자의 값에 관계없이 `true`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-135">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the operation result is `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="51244-136">다음 예제에서 `|` 연산자의 오른쪽 피연산자는 왼쪽 피연산자의 값과 관계없이 수행되는 메서드 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-136">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](snippets/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="51244-137">[조건부 논리 OR 연산자](#conditional-logical-or-operator-) `||`도 해당 피연산자의 논리 OR을 계산하지만, 왼쪽 피연산자가 `true`로 평가되는 경우에는 오른쪽 피연산자를 평가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51244-137">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="51244-138">[정수 숫자 형식](../builtin-types/integral-numeric-types.md) 피연산자의 경우 `|` 연산자는 해당 피연산자의 [비트 논리 OR](bitwise-and-shift-operators.md#logical-or-operator-)을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-138">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><a name="conditional-logical-and-operator-"></a> <span data-ttu-id="51244-139">조건부 논리 AND 연산자 &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="51244-139">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="51244-140">“단락(short-circuiting)” 논리 AND 연산자로도 알려진 조건부 논리 AND 연산자 `&&`는 해당 피연산자의 논리 AND를 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-140">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="51244-141">`x` 및 `y`가 모두 `true`로 평가되면 `x && y`의 결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-141">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="51244-142">그렇지 않으면 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-142">Otherwise, the result is `false`.</span></span> <span data-ttu-id="51244-143">`x`가 `false`이면 `y`는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51244-143">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="51244-144">다음 예제에서 `&&` 연산자의 오른쪽 피연산자는 왼쪽 피연산자가 `false`로 평가되는 경우 수행되지 않는 메서드 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-144">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](snippets/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="51244-145">[논리 AND 연산자](#logical-and-operator-) `&`도 해당 피연산자의 논리 AND를 컴퓨팅하지만 항상 두 피연산자를 모두 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-145">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="51244-146">조건부 논리 OR 연산자 ||</span><span class="sxs-lookup"><span data-stu-id="51244-146">Conditional logical OR operator ||</span></span>

<span data-ttu-id="51244-147">“단락(short-circuiting)” 논리 OR 연산자로도 알려진 조건부 논리 OR 연산자 `||`는 해당 피연산자의 논리 OR을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-147">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="51244-148">`x` 또는 `y`가 `true`로 평가되면 `x || y`의 결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-148">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="51244-149">그렇지 않으면 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-149">Otherwise, the result is `false`.</span></span> <span data-ttu-id="51244-150">`x`가 `true`이면 `y`는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51244-150">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="51244-151">다음 예제에서 `||` 연산자의 오른쪽 피연산자는 왼쪽 피연산자가 `true`로 평가되는 경우 수행되지 않는 메서드 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-151">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](snippets/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="51244-152">[논리 OR 연산자](#logical-or-operator-) `|`도 해당 피연산자의 논리 OR을 컴퓨팅하지만 항상 두 피연산자를 모두 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-152">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="51244-153">Nullable 부울 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="51244-153">Nullable Boolean logical operators</span></span>

<span data-ttu-id="51244-154">`bool?` 피연산자의 경우 [`&`(논리적 AND)](#logical-and-operator-) 및 [`|`(논리적 OR)](#logical-or-operator-) 연산자는 다음과 같이 값이 세 개인 논리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-154">For `bool?` operands, the [`&` (logical AND)](#logical-and-operator-) and [`|` (logical OR)](#logical-or-operator-) operators support the three-valued logic as follows:</span></span>

- <span data-ttu-id="51244-155">`&` 연산자는 두 피연산자가 모두 `true`로 평가되는 경우에만 `true`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-155">The `&` operator produces `true` only if both its operands evaluate to `true`.</span></span> <span data-ttu-id="51244-156">`x` 또는 `y`가 `false`로 평가되는 경우 다른 피연산자가 `null`로 평가되더라도 `x & y`는 `false`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-156">If either `x` or `y` evaluates to `false`, `x & y` produces `false` (even if another operand evaluates to `null`).</span></span> <span data-ttu-id="51244-157">그러지 않으면 `x & y`의 결과는 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-157">Otherwise, the result of `x & y` is `null`.</span></span>

- <span data-ttu-id="51244-158">`|` 연산자는 두 피연산자가 모두 `false`로 평가되는 경우에만 `false`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-158">The `|` operator produces `false` only if both its operands evaluate to `false`.</span></span> <span data-ttu-id="51244-159">`x` 또는 `y`가 `true`로 평가되는 경우 다른 피연산자가 `null`로 평가되더라도 `x | y`는 `true`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-159">If either `x` or `y` evaluates to `true`, `x | y` produces `true` (even if another operand evaluates to `null`).</span></span> <span data-ttu-id="51244-160">그러지 않으면 `x | y`의 결과는 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="51244-160">Otherwise, the result of `x | y` is `null`.</span></span>

<span data-ttu-id="51244-161">다음 표는 이 의미 체계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51244-161">The following table presents that semantics:</span></span>

|<span data-ttu-id="51244-162">x</span><span class="sxs-lookup"><span data-stu-id="51244-162">x</span></span>|<span data-ttu-id="51244-163">y</span><span class="sxs-lookup"><span data-stu-id="51244-163">y</span></span>|<span data-ttu-id="51244-164">x&y</span><span class="sxs-lookup"><span data-stu-id="51244-164">x&y</span></span>|<span data-ttu-id="51244-165">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="51244-165">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="51244-166">true</span><span class="sxs-lookup"><span data-stu-id="51244-166">true</span></span>|<span data-ttu-id="51244-167">true</span><span class="sxs-lookup"><span data-stu-id="51244-167">true</span></span>|<span data-ttu-id="51244-168">true</span><span class="sxs-lookup"><span data-stu-id="51244-168">true</span></span>|<span data-ttu-id="51244-169">true</span><span class="sxs-lookup"><span data-stu-id="51244-169">true</span></span>|  
|<span data-ttu-id="51244-170">true</span><span class="sxs-lookup"><span data-stu-id="51244-170">true</span></span>|<span data-ttu-id="51244-171">false</span><span class="sxs-lookup"><span data-stu-id="51244-171">false</span></span>|<span data-ttu-id="51244-172">false</span><span class="sxs-lookup"><span data-stu-id="51244-172">false</span></span>|<span data-ttu-id="51244-173">true</span><span class="sxs-lookup"><span data-stu-id="51244-173">true</span></span>|  
|<span data-ttu-id="51244-174">true</span><span class="sxs-lookup"><span data-stu-id="51244-174">true</span></span>|<span data-ttu-id="51244-175">null</span><span class="sxs-lookup"><span data-stu-id="51244-175">null</span></span>|<span data-ttu-id="51244-176">null</span><span class="sxs-lookup"><span data-stu-id="51244-176">null</span></span>|<span data-ttu-id="51244-177">true</span><span class="sxs-lookup"><span data-stu-id="51244-177">true</span></span>|  
|<span data-ttu-id="51244-178">false</span><span class="sxs-lookup"><span data-stu-id="51244-178">false</span></span>|<span data-ttu-id="51244-179">true</span><span class="sxs-lookup"><span data-stu-id="51244-179">true</span></span>|<span data-ttu-id="51244-180">false</span><span class="sxs-lookup"><span data-stu-id="51244-180">false</span></span>|<span data-ttu-id="51244-181">true</span><span class="sxs-lookup"><span data-stu-id="51244-181">true</span></span>|  
|<span data-ttu-id="51244-182">false</span><span class="sxs-lookup"><span data-stu-id="51244-182">false</span></span>|<span data-ttu-id="51244-183">false</span><span class="sxs-lookup"><span data-stu-id="51244-183">false</span></span>|<span data-ttu-id="51244-184">false</span><span class="sxs-lookup"><span data-stu-id="51244-184">false</span></span>|<span data-ttu-id="51244-185">false</span><span class="sxs-lookup"><span data-stu-id="51244-185">false</span></span>|  
|<span data-ttu-id="51244-186">false</span><span class="sxs-lookup"><span data-stu-id="51244-186">false</span></span>|<span data-ttu-id="51244-187">null</span><span class="sxs-lookup"><span data-stu-id="51244-187">null</span></span>|<span data-ttu-id="51244-188">false</span><span class="sxs-lookup"><span data-stu-id="51244-188">false</span></span>|<span data-ttu-id="51244-189">null</span><span class="sxs-lookup"><span data-stu-id="51244-189">null</span></span>|  
|<span data-ttu-id="51244-190">null</span><span class="sxs-lookup"><span data-stu-id="51244-190">null</span></span>|<span data-ttu-id="51244-191">true</span><span class="sxs-lookup"><span data-stu-id="51244-191">true</span></span>|<span data-ttu-id="51244-192">null</span><span class="sxs-lookup"><span data-stu-id="51244-192">null</span></span>|<span data-ttu-id="51244-193">true</span><span class="sxs-lookup"><span data-stu-id="51244-193">true</span></span>|  
|<span data-ttu-id="51244-194">null</span><span class="sxs-lookup"><span data-stu-id="51244-194">null</span></span>|<span data-ttu-id="51244-195">false</span><span class="sxs-lookup"><span data-stu-id="51244-195">false</span></span>|<span data-ttu-id="51244-196">false</span><span class="sxs-lookup"><span data-stu-id="51244-196">false</span></span>|<span data-ttu-id="51244-197">null</span><span class="sxs-lookup"><span data-stu-id="51244-197">null</span></span>|  
|<span data-ttu-id="51244-198">null</span><span class="sxs-lookup"><span data-stu-id="51244-198">null</span></span>|<span data-ttu-id="51244-199">null</span><span class="sxs-lookup"><span data-stu-id="51244-199">null</span></span>|<span data-ttu-id="51244-200">null</span><span class="sxs-lookup"><span data-stu-id="51244-200">null</span></span>|<span data-ttu-id="51244-201">null</span><span class="sxs-lookup"><span data-stu-id="51244-201">null</span></span>|  

<span data-ttu-id="51244-202">해당 연산자의 동작은 Nullable 값 형식을 사용하는 일반 연산자 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="51244-202">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="51244-203">일반적으로 값 형식의 피연산자에 대해 정의된 연산자도 해당 Nullable 값 형식의 피연산자와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51244-203">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="51244-204">피연산자가 `null`로 평가되는 경우 해당 연산자는 `null`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-204">Such an operator produces `null` if any of its operands evaluates to `null`.</span></span> <span data-ttu-id="51244-205">그러나 피연산자 중 하나가 `null`로 평가되는 경우에도 `&` 및 `|` 연산자는 Null이 아닌 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-205">However, the `&` and `|` operators can produce non-null even if one of the operands evaluates to `null`.</span></span> <span data-ttu-id="51244-206">Nullable 값 형식을 사용한 연산자 동작에 대한 자세한 내용은 [Nullable 값 형식](../builtin-types/nullable-value-types.md) 문서의 [리프트된 연산자](../builtin-types/nullable-value-types.md#lifted-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51244-206">For more information about the operator behavior with nullable value types, see the [Lifted operators](../builtin-types/nullable-value-types.md#lifted-operators) section of the [Nullable value types](../builtin-types/nullable-value-types.md) article.</span></span>

<span data-ttu-id="51244-207">다음 예제와 같이 `!` 및 `^` 연산자를 `bool?` 피연산자와 함께 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51244-207">You can also use the `!` and `^` operators with `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](snippets/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="51244-208">조건부 논리 연산자 `&&` 및 `||`는 `bool?` 피연산자를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51244-208">The conditional logical operators `&&` and `||` don't support `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="51244-209">복합 할당</span><span class="sxs-lookup"><span data-stu-id="51244-209">Compound assignment</span></span>

<span data-ttu-id="51244-210">이진 연산자(`op`)의 경우 양식의 복합 할당 식</span><span class="sxs-lookup"><span data-stu-id="51244-210">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="51244-211">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-211">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="51244-212">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="51244-212">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="51244-213">`&`, `|` 및 `^` 연산자는 다음 예제와 같이 복합 할당을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-213">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](snippets/BooleanLogicalOperators.cs#CompoundAssignment)]

> [!NOTE]
> <span data-ttu-id="51244-214">조건부 논리 연산자 `&&` 및 `||`는 복합 할당을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51244-214">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="51244-215">연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="51244-215">Operator precedence</span></span>

<span data-ttu-id="51244-216">다음 목록에서는 논리 연산자를 가장 높은 우선 순위부터 가장 낮은 것으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-216">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="51244-217">논리 부정 연산자 `!`</span><span class="sxs-lookup"><span data-stu-id="51244-217">Logical negation operator `!`</span></span>
- <span data-ttu-id="51244-218">논리 AND 연산자 `&`</span><span class="sxs-lookup"><span data-stu-id="51244-218">Logical AND operator `&`</span></span>
- <span data-ttu-id="51244-219">논리 배타적 OR 연산자 `^`</span><span class="sxs-lookup"><span data-stu-id="51244-219">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="51244-220">논리 OR 연산자 `|`</span><span class="sxs-lookup"><span data-stu-id="51244-220">Logical OR operator `|`</span></span>
- <span data-ttu-id="51244-221">조건부 논리 AND 연산자 `&&`</span><span class="sxs-lookup"><span data-stu-id="51244-221">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="51244-222">조건부 논리 OR 연산자 `||`</span><span class="sxs-lookup"><span data-stu-id="51244-222">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="51244-223">괄호(`()`)를 사용하여 연산자 우선 순위에 따라 주어진 평가 순서를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="51244-223">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](snippets/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="51244-224">우선 순위 수준에 따라 정렬된 전체 연산자 목록은 [C# 연산자](index.md#operator-precedence) 문서의 [연산자 우선 순위](index.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51244-224">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="51244-225">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="51244-225">Operator overloadability</span></span>

<span data-ttu-id="51244-226">사용자 정의 형식은 `!`, `&`, `|` 및 `^` 연산자를 [오버로드](operator-overloading.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51244-226">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="51244-227">이항 연산자가 오버로드되면 해당하는 복합 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="51244-227">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="51244-228">사용자 정의 형식은 복합 대입 연산자를 명시적으로 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51244-228">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="51244-229">사용자 정의 형식은 조건부 논리 연산자 `&&` 및 `||`를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51244-229">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="51244-230">그러나 사용자 정의 형식이 [true 및 false 연산자](true-false-operators.md)와 `&` 또는 `|` 연산자를 특정 방식으로 오버로드하는 경우 `&&` 또는 `||` 작업은 각각 해당 형식의 피연산자에 대해 평가될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51244-230">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="51244-231">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [사용자 정의 조건부 논리 연산자](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51244-231">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="51244-232">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="51244-232">C# language specification</span></span>

<span data-ttu-id="51244-233">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51244-233">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="51244-234">논리 부정 연산자</span><span class="sxs-lookup"><span data-stu-id="51244-234">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="51244-235">논리 연산자</span><span class="sxs-lookup"><span data-stu-id="51244-235">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="51244-236">조건부 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="51244-236">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="51244-237">복합 할당</span><span class="sxs-lookup"><span data-stu-id="51244-237">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="51244-238">참조</span><span class="sxs-lookup"><span data-stu-id="51244-238">See also</span></span>

- [<span data-ttu-id="51244-239">C# 참조</span><span class="sxs-lookup"><span data-stu-id="51244-239">C# reference</span></span>](../index.md)
- [<span data-ttu-id="51244-240">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="51244-240">C# operators</span></span>](index.md)
- [<span data-ttu-id="51244-241">비트 및 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="51244-241">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
