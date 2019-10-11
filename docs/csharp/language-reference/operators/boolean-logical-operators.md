---
title: 부울 논리 연산자 - C# 참조
description: 부울 피연산자를 사용하여 논리 부정, 결합(AND) 및 포괄적/배타적 분리(OR) 작업을 수행하는 C# 연산자에 대해 알아봅니다.
ms.date: 09/27/2019
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
ms.openlocfilehash: cc25d4bfd444dc0acb30fc1c6e6c3c9918af537c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698675"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="95d51-103">부울 논리 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="95d51-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="95d51-104">다음 연산자는 [부울](../keywords/bool.md) 피연산자를 사용하여 논리 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="95d51-105">단항 [`!`(논리 부정)](#logical-negation-operator-) 연산자.</span><span class="sxs-lookup"><span data-stu-id="95d51-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="95d51-106">이진 [`&`(논리 AND)](#logical-and-operator-), [`|`(논리 OR)](#logical-or-operator-) 및 [`^`(논리 배타적 OR)](#logical-exclusive-or-operator-) 연산자.</span><span class="sxs-lookup"><span data-stu-id="95d51-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="95d51-107">해당 연산자는 항상 두 피연산자를 모두 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="95d51-108">이진 [`&&`(조건부 논리 AND)](#conditional-logical-and-operator-) 및 [`||`(조건부 논리 OR)](#conditional-logical-or-operator-) 연산자.</span><span class="sxs-lookup"><span data-stu-id="95d51-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="95d51-109">해당 연산자는 필요한 경우에만 오른쪽 피연산자를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="95d51-110">[정수](../builtin-types/integral-numeric-types.md) 형식 피연산자의 경우 `&`, `|` 및 `^` 연산자는 비트 논리 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-110">For the operands of the [integral](../builtin-types/integral-numeric-types.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="95d51-111">자세한 내용은 [비트 및 시프트 연산자](bitwise-and-shift-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95d51-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="95d51-112">논리 부정 연산자 !</span><span class="sxs-lookup"><span data-stu-id="95d51-112">Logical negation operator !</span></span>

<span data-ttu-id="95d51-113">`!` 연산자는 해당 피연산자의 논리 부정을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-113">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="95d51-114">즉, 피연산자가 `false`로 평가되는 경우 `true`를 생성하고, 피연산자가 `true`로 평가되는 경우 `false`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="95d51-115">C# 8.0부터 단항 후위 `!` 연산자는 null 허용 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-115">Starting with C# 8.0, the unary postfix `!` operator is a null-forgiving operator.</span></span> <span data-ttu-id="95d51-116">null 허용 주석 컨텍스트가 활성화된 경우에는 null 허용 참조 형식의 식 `x`이 null이 아님을 선언하는 데 `x!`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-116">In an enabled nullable annotation context, you use it to declare that expression `x` of a nullable reference type isn't null: `x!`.</span></span> <span data-ttu-id="95d51-117">자세한 내용은 [nullable 참조 형식](../../nullable-references.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95d51-117">For more information, see [Nullable reference types](../../nullable-references.md).</span></span>

## <a name="logical-and-operator-"></a> <span data-ttu-id="95d51-118">논리 AND 연산자 &amp;</span><span class="sxs-lookup"><span data-stu-id="95d51-118">Logical AND operator &amp;</span></span>

<span data-ttu-id="95d51-119">`&` 연산자는 해당 피연산자의 논리 AND를 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-119">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="95d51-120">`x` 및 `y`가 모두 `true`로 평가되면 `x & y`의 결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-120">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="95d51-121">그렇지 않으면 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-121">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="95d51-122">왼쪽 피연산자가 `false`로 평가되더라도 `&` 연산자는 두 피연산자를 평가하여 오른쪽 피연산자의 값에 관계없이 `false`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-122">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the result must be `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="95d51-123">다음 예제에서 `&` 연산자의 오른쪽 피연산자는 왼쪽 피연산자의 값과 관계없이 수행되는 메서드 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-123">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="95d51-124">[조건부 논리 AND 연산자](#conditional-logical-and-operator-) `&&`도 해당 피연산자의 논리 AND를 계산하지만, 왼쪽 피연산자가 `false`로 평가되는 경우에는 오른쪽 피연산자를 평가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-124">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="95d51-125">정수 형식 피연산자의 경우 `&` 연산자는 해당 피연산자의 [비트 논리 AND](bitwise-and-shift-operators.md#logical-and-operator-)를 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-125">For the operands of the integral types, the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="95d51-126">단항 `&` 연산자는 [address-of 연산자](pointer-related-operators.md#address-of-operator-)입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-126">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="95d51-127">논리 배타적 OR 연산자 ^</span><span class="sxs-lookup"><span data-stu-id="95d51-127">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="95d51-128">`^` 연산자는 해당 피연산자의 논리 XOR이라고도 하는 논리 배타적 OR을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-128">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="95d51-129">`x`가 `true`로 평가되고 `y`가 `false`로 평가되거나, `x`가 `false`로 평가되고 `y`가 `true`로 평가되는 경우 `x ^ y`의 결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-129">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="95d51-130">그렇지 않으면 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-130">Otherwise, the result is `false`.</span></span> <span data-ttu-id="95d51-131">즉, `bool` 피연산자의 경우 `^` 연산자는 [같지 않음 연산자](equality-operators.md#inequality-operator-) `!=`와 같은 결과를 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-131">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="95d51-132">정수 형식 피연산자의 경우 `^` 연산자는 해당 피연산자의 [비트 논리 배타적 OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-132">For the operands of the integral types, the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="95d51-133">논리 OR 연산자 |</span><span class="sxs-lookup"><span data-stu-id="95d51-133">Logical OR operator |</span></span>

<span data-ttu-id="95d51-134">`|` 연산자는 해당 피연산자의 논리 OR을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-134">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="95d51-135">`x` 또는 `y`가 `true`로 평가되면 `x | y`의 결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-135">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="95d51-136">그렇지 않으면 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-136">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="95d51-137">왼쪽 피연산자가 `true`로 평가되더라도 `|` 연산자는 두 피연산자를 평가하여 오른쪽 피연산자의 값에 관계없이 `true`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-137">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the result must be `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="95d51-138">다음 예제에서 `|` 연산자의 오른쪽 피연산자는 왼쪽 피연산자의 값과 관계없이 수행되는 메서드 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-138">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="95d51-139">[조건부 논리 OR 연산자](#conditional-logical-or-operator-) `||`도 해당 피연산자의 논리 OR을 계산하지만, 왼쪽 피연산자가 `true`로 평가되는 경우에는 오른쪽 피연산자를 평가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-139">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="95d51-140">정수 형식 피연산자의 경우 `|` 연산자는 해당 피연산자의 [비트 논리 OR](bitwise-and-shift-operators.md#logical-or-operator-)을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-140">For the operands of the integral types, the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-"></a> <span data-ttu-id="95d51-141">조건부 논리 AND 연산자 &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="95d51-141">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="95d51-142">“단락(short-circuiting)” 논리 AND 연산자로도 알려진 조건부 논리 AND 연산자 `&&`는 해당 피연산자의 논리 AND를 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-142">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="95d51-143">`x` 및 `y`가 모두 `true`로 평가되면 `x && y`의 결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-143">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="95d51-144">그렇지 않으면 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-144">Otherwise, the result is `false`.</span></span> <span data-ttu-id="95d51-145">`x`가 `false`이면 `y`는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-145">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="95d51-146">다음 예제에서 `&&` 연산자의 오른쪽 피연산자는 왼쪽 피연산자가 `false`로 평가되는 경우 수행되지 않는 메서드 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-146">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="95d51-147">[논리 AND 연산자](#logical-and-operator-) `&`도 해당 피연산자의 논리 AND를 컴퓨팅하지만 항상 두 피연산자를 모두 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-147">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="95d51-148">조건부 논리 OR 연산자 ||</span><span class="sxs-lookup"><span data-stu-id="95d51-148">Conditional logical OR operator ||</span></span>

<span data-ttu-id="95d51-149">“단락(short-circuiting)” 논리 OR 연산자로도 알려진 조건부 논리 OR 연산자 `||`는 해당 피연산자의 논리 OR을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-149">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="95d51-150">`x` 또는 `y`가 `true`로 평가되면 `x || y`의 결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-150">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="95d51-151">그렇지 않으면 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-151">Otherwise, the result is `false`.</span></span> <span data-ttu-id="95d51-152">`x`가 `true`이면 `y`는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-152">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="95d51-153">다음 예제에서 `||` 연산자의 오른쪽 피연산자는 왼쪽 피연산자가 `true`로 평가되는 경우 수행되지 않는 메서드 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-153">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="95d51-154">[논리 OR 연산자](#logical-or-operator-) `|`도 해당 피연산자의 논리 OR을 컴퓨팅하지만 항상 두 피연산자를 모두 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-154">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="95d51-155">Nullable 부울 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="95d51-155">Nullable Boolean logical operators</span></span>

<span data-ttu-id="95d51-156">`bool?` 피연산자의 경우 `&` 및 `|` 연산자는 값이 세 개인 논리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-156">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="95d51-157">이러한 연산자의 의미 체계는 다음 표에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-157">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="95d51-158">x</span><span class="sxs-lookup"><span data-stu-id="95d51-158">x</span></span>|<span data-ttu-id="95d51-159">y</span><span class="sxs-lookup"><span data-stu-id="95d51-159">y</span></span>|<span data-ttu-id="95d51-160">x&y</span><span class="sxs-lookup"><span data-stu-id="95d51-160">x&y</span></span>|<span data-ttu-id="95d51-161">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="95d51-161">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="95d51-162">true</span><span class="sxs-lookup"><span data-stu-id="95d51-162">true</span></span>|<span data-ttu-id="95d51-163">true</span><span class="sxs-lookup"><span data-stu-id="95d51-163">true</span></span>|<span data-ttu-id="95d51-164">true</span><span class="sxs-lookup"><span data-stu-id="95d51-164">true</span></span>|<span data-ttu-id="95d51-165">true</span><span class="sxs-lookup"><span data-stu-id="95d51-165">true</span></span>|  
|<span data-ttu-id="95d51-166">true</span><span class="sxs-lookup"><span data-stu-id="95d51-166">true</span></span>|<span data-ttu-id="95d51-167">false</span><span class="sxs-lookup"><span data-stu-id="95d51-167">false</span></span>|<span data-ttu-id="95d51-168">false</span><span class="sxs-lookup"><span data-stu-id="95d51-168">false</span></span>|<span data-ttu-id="95d51-169">true</span><span class="sxs-lookup"><span data-stu-id="95d51-169">true</span></span>|  
|<span data-ttu-id="95d51-170">true</span><span class="sxs-lookup"><span data-stu-id="95d51-170">true</span></span>|<span data-ttu-id="95d51-171">null</span><span class="sxs-lookup"><span data-stu-id="95d51-171">null</span></span>|<span data-ttu-id="95d51-172">null</span><span class="sxs-lookup"><span data-stu-id="95d51-172">null</span></span>|<span data-ttu-id="95d51-173">true</span><span class="sxs-lookup"><span data-stu-id="95d51-173">true</span></span>|  
|<span data-ttu-id="95d51-174">false</span><span class="sxs-lookup"><span data-stu-id="95d51-174">false</span></span>|<span data-ttu-id="95d51-175">true</span><span class="sxs-lookup"><span data-stu-id="95d51-175">true</span></span>|<span data-ttu-id="95d51-176">false</span><span class="sxs-lookup"><span data-stu-id="95d51-176">false</span></span>|<span data-ttu-id="95d51-177">true</span><span class="sxs-lookup"><span data-stu-id="95d51-177">true</span></span>|  
|<span data-ttu-id="95d51-178">false</span><span class="sxs-lookup"><span data-stu-id="95d51-178">false</span></span>|<span data-ttu-id="95d51-179">false</span><span class="sxs-lookup"><span data-stu-id="95d51-179">false</span></span>|<span data-ttu-id="95d51-180">false</span><span class="sxs-lookup"><span data-stu-id="95d51-180">false</span></span>|<span data-ttu-id="95d51-181">false</span><span class="sxs-lookup"><span data-stu-id="95d51-181">false</span></span>|  
|<span data-ttu-id="95d51-182">false</span><span class="sxs-lookup"><span data-stu-id="95d51-182">false</span></span>|<span data-ttu-id="95d51-183">null</span><span class="sxs-lookup"><span data-stu-id="95d51-183">null</span></span>|<span data-ttu-id="95d51-184">false</span><span class="sxs-lookup"><span data-stu-id="95d51-184">false</span></span>|<span data-ttu-id="95d51-185">null</span><span class="sxs-lookup"><span data-stu-id="95d51-185">null</span></span>|  
|<span data-ttu-id="95d51-186">null</span><span class="sxs-lookup"><span data-stu-id="95d51-186">null</span></span>|<span data-ttu-id="95d51-187">true</span><span class="sxs-lookup"><span data-stu-id="95d51-187">true</span></span>|<span data-ttu-id="95d51-188">null</span><span class="sxs-lookup"><span data-stu-id="95d51-188">null</span></span>|<span data-ttu-id="95d51-189">true</span><span class="sxs-lookup"><span data-stu-id="95d51-189">true</span></span>|  
|<span data-ttu-id="95d51-190">null</span><span class="sxs-lookup"><span data-stu-id="95d51-190">null</span></span>|<span data-ttu-id="95d51-191">false</span><span class="sxs-lookup"><span data-stu-id="95d51-191">false</span></span>|<span data-ttu-id="95d51-192">false</span><span class="sxs-lookup"><span data-stu-id="95d51-192">false</span></span>|<span data-ttu-id="95d51-193">null</span><span class="sxs-lookup"><span data-stu-id="95d51-193">null</span></span>|  
|<span data-ttu-id="95d51-194">null</span><span class="sxs-lookup"><span data-stu-id="95d51-194">null</span></span>|<span data-ttu-id="95d51-195">null</span><span class="sxs-lookup"><span data-stu-id="95d51-195">null</span></span>|<span data-ttu-id="95d51-196">null</span><span class="sxs-lookup"><span data-stu-id="95d51-196">null</span></span>|<span data-ttu-id="95d51-197">null</span><span class="sxs-lookup"><span data-stu-id="95d51-197">null</span></span>|  

<span data-ttu-id="95d51-198">해당 연산자의 동작은 Nullable 값 형식을 사용하는 일반 연산자 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-198">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="95d51-199">일반적으로 값 형식의 피연산자에 대해 정의된 연산자도 해당 Nullable 값 형식의 피연산자와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-199">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="95d51-200">피연산자가 `null`인 경우 해당 연산자는 `null`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-200">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="95d51-201">그러나 피연산자 중 하나가 `null`인 경우에도 `&` 및 `|` 연산자는 Null이 아닌 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-201">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="95d51-202">Nullable 값 형식을 사용한 연산자 동작에 대한 자세한 내용은 [nullable 형식 사용](../../programming-guide/nullable-types/using-nullable-types.md) 문서의 [연산자](../../programming-guide/nullable-types/using-nullable-types.md#operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95d51-202">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable value types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="95d51-203">다음 예제와 같이 `!` 및 `^` 연산자를 `bool?` 피연산자와 함께 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-203">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="95d51-204">조건부 논리 연산자 `&&` 및 `||`는 `bool?` 피연산자를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-204">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="95d51-205">복합 할당</span><span class="sxs-lookup"><span data-stu-id="95d51-205">Compound assignment</span></span>

<span data-ttu-id="95d51-206">이진 연산자(`op`)의 경우 양식의 복합 할당 식</span><span class="sxs-lookup"><span data-stu-id="95d51-206">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="95d51-207">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-207">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="95d51-208">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-208">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="95d51-209">`&`, `|` 및 `^` 연산자는 다음 예제와 같이 복합 할당을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-209">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="95d51-210">조건부 논리 연산자 `&&` 및 `||`는 복합 할당을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-210">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="95d51-211">연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="95d51-211">Operator precedence</span></span>

<span data-ttu-id="95d51-212">다음 목록에서는 논리 연산자를 가장 높은 우선 순위부터 가장 낮은 것으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-212">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="95d51-213">논리 부정 연산자 `!`</span><span class="sxs-lookup"><span data-stu-id="95d51-213">Logical negation operator `!`</span></span>
- <span data-ttu-id="95d51-214">논리 AND 연산자 `&`</span><span class="sxs-lookup"><span data-stu-id="95d51-214">Logical AND operator `&`</span></span>
- <span data-ttu-id="95d51-215">논리 배타적 OR 연산자 `^`</span><span class="sxs-lookup"><span data-stu-id="95d51-215">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="95d51-216">논리 OR 연산자 `|`</span><span class="sxs-lookup"><span data-stu-id="95d51-216">Logical OR operator `|`</span></span>
- <span data-ttu-id="95d51-217">조건부 논리 AND 연산자 `&&`</span><span class="sxs-lookup"><span data-stu-id="95d51-217">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="95d51-218">조건부 논리 OR 연산자 `||`</span><span class="sxs-lookup"><span data-stu-id="95d51-218">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="95d51-219">괄호(`()`)를 사용하여 연산자 우선 순위에 따라 주어진 평가 순서를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-219">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="95d51-220">우선 순위 수준에 따라 정렬된 전체 연산자 목록은 [C# 연산자](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95d51-220">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="95d51-221">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="95d51-221">Operator overloadability</span></span>

<span data-ttu-id="95d51-222">사용자 정의 형식은 `!`, `&`, `|` 및 `^` 연산자를 [오버로드](operator-overloading.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-222">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="95d51-223">이항 연산자가 오버로드되면 해당하는 복합 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-223">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="95d51-224">사용자 정의 형식은 복합 대입 연산자를 명시적으로 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-224">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="95d51-225">사용자 정의 형식은 조건부 논리 연산자 `&&` 및 `||`를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-225">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="95d51-226">그러나 사용자 정의 형식이 [true 및 false 연산자](true-false-operators.md)와 `&` 또는 `|` 연산자를 특정 방식으로 오버로드하는 경우 `&&` 또는 `||` 작업은 각각 해당 형식의 피연산자에 대해 평가될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95d51-226">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="95d51-227">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [사용자 정의 조건부 논리 연산자](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95d51-227">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="95d51-228">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="95d51-228">C# language specification</span></span>

<span data-ttu-id="95d51-229">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95d51-229">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="95d51-230">논리 부정 연산자</span><span class="sxs-lookup"><span data-stu-id="95d51-230">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="95d51-231">논리 연산자</span><span class="sxs-lookup"><span data-stu-id="95d51-231">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="95d51-232">조건부 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="95d51-232">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="95d51-233">복합 할당</span><span class="sxs-lookup"><span data-stu-id="95d51-233">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="95d51-234">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95d51-234">See also</span></span>

- [<span data-ttu-id="95d51-235">C# 참조</span><span class="sxs-lookup"><span data-stu-id="95d51-235">C# reference</span></span>](../index.md)
- [<span data-ttu-id="95d51-236">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="95d51-236">C# operators</span></span>](index.md)
- [<span data-ttu-id="95d51-237">비트 및 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="95d51-237">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
