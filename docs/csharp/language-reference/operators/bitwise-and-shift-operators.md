---
title: 비트 및 시프트 연산자 - C# 참조
description: 정수 형식의 피연산자를 사용하여 비트 논리 또는 시프트 연산을 수행하는 C# 연산자에 대해 알아봅니다.
ms.date: 04/18/2019
author: pkulikov
f1_keywords:
- ~_CSharpKeyword
- <<_CSharpKeyword
- '>>_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- <<=_CSharpKeyword
- '>>=_CSharpKeyword'
helpviewer_keywords:
- bitwise logical operators [C#]
- shift operators [C#]
- tilde operator [C#]
- one's complement operator [C#]
- bitwise complement operator [C#]
- ~ operator [C#]
- left shift operator [C#]
- << operator [C#]
- right shift operator [C#]
- '>> operator [C#]'
- bitwise logical AND operator [C#]
- ampersand operator [C#]
- '& operator [C#]'
- bitwise logical exclusive OR operator [C#]
- bitwise logical XOR operator [C#]
- ^ operator [C#]
- bitwise logical OR operator [C#]
- '| operator [C#]'
ms.openlocfilehash: 99181855fdf8e937676e44e8b347510f9405aa3d
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916908"
---
# <a name="bitwise-and-shift-operators-c-reference"></a><span data-ttu-id="acb34-103">비트 및 시프트 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="acb34-103">Bitwise and shift operators (C# reference)</span></span>

<span data-ttu-id="acb34-104">다음 연산자는 [정수 형식](../builtin-types/integral-numeric-types.md) 또는 [char](../builtin-types/char.md) 형식의 피연산자를 사용하여 비트 논리 또는 시프트 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-104">The following operators perform bitwise or shift operations with operands of the [integral numeric types](../builtin-types/integral-numeric-types.md) or the [char](../builtin-types/char.md) type:</span></span>

- <span data-ttu-id="acb34-105">단항 [`~`(비트 보수)](#bitwise-complement-operator-) 연산자</span><span class="sxs-lookup"><span data-stu-id="acb34-105">Unary [`~` (bitwise complement)](#bitwise-complement-operator-) operator</span></span>
- <span data-ttu-id="acb34-106">이진 [`<<`(왼쪽 시프트)](#left-shift-operator-) 및 [`>>`(오른쪽 시프트)](#right-shift-operator-) 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="acb34-106">Binary [`<<` (left shift)](#left-shift-operator-) and [`>>` (right shift)](#right-shift-operator-) shift operators</span></span>
- <span data-ttu-id="acb34-107">이진 [`&`(논리 AND)](#logical-and-operator-), [`|`(논리 OR)](#logical-or-operator-) 및 [`^`(논리 배타적 OR)](#logical-exclusive-or-operator-) 연산자</span><span class="sxs-lookup"><span data-stu-id="acb34-107">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators</span></span>

<span data-ttu-id="acb34-108">이러한 연산자는 `int`, `uint`, `long` 및 `ulong` 형식에 대해 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-108">Those operators are defined for the `int`, `uint`, `long`, and `ulong` types.</span></span> <span data-ttu-id="acb34-109">두 피연산자가 모두 다른 정수 형식(`sbyte`, `byte`, `short`, `ushort` 또는 `char`)인 경우, 해당 값은 작업의 결과 형식이기도 한 `int` 유형으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-109">When both operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type, which is also the result type of an operation.</span></span> <span data-ttu-id="acb34-110">피연산자가 다른 정수 형식인 경우 해당 값은 가장 가까운 정수 형식으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-110">When operands are of different integral types, their values are converted to the closest containing integral type.</span></span> <span data-ttu-id="acb34-111">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [숫자 승격](~/_csharplang/spec/expressions.md#numeric-promotions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acb34-111">For more information, see the [Numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="acb34-112">`bool` 유형의 피연산자에 대한 `&`, `|` 및 `^` 연산자도 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-112">The `&`, `|`, and `^` operators are also defined for operands of the `bool` type.</span></span> <span data-ttu-id="acb34-113">자세한 내용은 [부울 논리 연산자](boolean-logical-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acb34-113">For more information, see [Boolean logical operators](boolean-logical-operators.md).</span></span>

<span data-ttu-id="acb34-114">비트 및 시프트 작업으로 인해 오버플로가 발생하지 않고 [Checked 및 Unchecked](../keywords/checked-and-unchecked.md) 컨텍스트에서 동일한 결과가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-114">Bitwise and shift operations never cause overflow and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="bitwise-complement-operator-"></a><span data-ttu-id="acb34-115">비트 보수 연산자 ~</span><span class="sxs-lookup"><span data-stu-id="acb34-115">Bitwise complement operator ~</span></span>

<span data-ttu-id="acb34-116">`~` 연산자는 각 비트를 반대로 하여 해당 피연산자의 비트 보수를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-116">The `~` operator produces a bitwise complement of its operand by reversing each bit:</span></span>

[!code-csharp-interactive[bitwise NOT](snippets/shared/BitwiseAndShiftOperators.cs#BitwiseComplement)]

<span data-ttu-id="acb34-117">`~` 기호를 사용하여 종료자를 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-117">You can also use the `~` symbol to declare finalizers.</span></span> <span data-ttu-id="acb34-118">자세한 내용은 [종료자](../../programming-guide/classes-and-structs/destructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acb34-118">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

## <a name="left-shift-operator-"></a><span data-ttu-id="acb34-119">왼쪽 시프트 연산자 \<\<</span><span class="sxs-lookup"><span data-stu-id="acb34-119">Left-shift operator \<\<</span></span>

<span data-ttu-id="acb34-120">`<<` 연산자는 왼쪽 피연산자를 [오른쪽 피연산자로 정의된 비트 수](#shift-count-of-the-shift-operators)만큼 왼쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-120">The `<<` operator shifts its left-hand operand left by the [number of bits defined by its right-hand operand](#shift-count-of-the-shift-operators).</span></span>

<span data-ttu-id="acb34-121">왼쪽 시프트 연산은 결과 형식의 범위를 벗어나는 상위 비트를 삭제하고 다음 예제와 같이 빈 하위 비트 위치를 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-121">The left-shift operation discards the high-order bits that are outside the range of the result type and sets the low-order empty bit positions to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift](snippets/shared/BitwiseAndShiftOperators.cs#LeftShift)]

<span data-ttu-id="acb34-122">시프트 연산자는 `int`, `uint`, `long` 및 `ulong` 유형에 대해서만 정의되므로 작업 결과에는 항상 32비트 이상이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-122">Because the shift operators are defined only for the `int`, `uint`, `long`, and `ulong` types, the result of an operation always contains at least 32 bits.</span></span> <span data-ttu-id="acb34-123">왼쪽 피연산자가 다른 정수 형식(`sbyte`, `byte`, `short`, `ushort` 또는 `char`)인 경우, 다음 예제와 같이 해당 값이 `int` 유형으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-123">If the left-hand operand is of another integral type (`sbyte`, `byte`, `short`, `ushort`, or `char`), its value is converted to the `int` type, as the following example shows:</span></span>

[!code-csharp-interactive[left shift with promotion](snippets/shared/BitwiseAndShiftOperators.cs#LeftShiftPromoted)]

<span data-ttu-id="acb34-124">`<<` 연산자의 오른쪽 피연산자가 시프트 수를 정의하는 방법에 대한 자세한 내용은 [시프트 연산자의 시프트 수](#shift-count-of-the-shift-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acb34-124">For information about how the right-hand operand of the `<<` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="right-shift-operator-"></a><span data-ttu-id="acb34-125">오른쪽 시프트 연산자 >></span><span class="sxs-lookup"><span data-stu-id="acb34-125">Right-shift operator >></span></span>

<span data-ttu-id="acb34-126">`>>` 연산자는 왼쪽 피연산자를 [오른쪽 피연산자로 정의된 비트 수](#shift-count-of-the-shift-operators)만큼 오른쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-126">The `>>` operator shifts its left-hand operand right by the [number of bits defined by its right-hand operand](#shift-count-of-the-shift-operators).</span></span>

<span data-ttu-id="acb34-127">오른쪽 시프트 연산은 다음 예제와 같이 하위 비트를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-127">The right-shift operation discards the low-order bits, as the following example shows:</span></span>

[!code-csharp-interactive[right shift](snippets/shared/BitwiseAndShiftOperators.cs#RightShift)]

<span data-ttu-id="acb34-128">빈 상위 공백 비트 위치는 다음과 같이 왼쪽 피연산자 형식에 따라 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-128">The high-order empty bit positions are set based on the type of the left-hand operand as follows:</span></span>

- <span data-ttu-id="acb34-129">왼쪽 피연산자가 `int` 또는 `long` 형식인 경우 오른쪽 시프트 연산자는 *산술* 시프트를 수행합니다. 왼쪽 피연산자의 최상위 비트(부호 비트) 값이 빈 상위 비트 위치로 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-129">If the left-hand operand is of type `int` or `long`, the right-shift operator performs an *arithmetic* shift: the value of the most significant bit (the sign bit) of the left-hand operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="acb34-130">즉, 빈 상위 비트 위치는 왼쪽 피연산자가 음수가 아닌 경우 0으로 설정되고, 음수인 경우 1로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-130">That is, the high-order empty bit positions are set to zero if the left-hand operand is non-negative and set to one if it's negative.</span></span>

  [!code-csharp-interactive[arithmetic right shift](snippets/shared/BitwiseAndShiftOperators.cs#ArithmeticRightShift)]

- <span data-ttu-id="acb34-131">왼쪽 피연산자가 `uint` 또는 `ulong` 형식이면 오른쪽 시프트 피연산자는 *논리적* 시프트를 수행합니다. 빈 상위 비트 위치가 항상 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-131">If the left-hand operand is of type `uint` or `ulong`, the right-shift operator performs a *logical* shift: the high-order empty bit positions are always set to zero.</span></span>

  [!code-csharp-interactive[logical right shift](snippets/shared/BitwiseAndShiftOperators.cs#LogicalRightShift)]

<span data-ttu-id="acb34-132">`>>` 연산자의 오른쪽 피연산자가 시프트 수를 정의하는 방법에 대한 자세한 내용은 [시프트 연산자의 시프트 수](#shift-count-of-the-shift-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acb34-132">For information about how the right-hand operand of the `>>` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="logical-and-operator-amp"></a><a name="logical-and-operator-"></a> <span data-ttu-id="acb34-133">논리 AND 연산자 &amp;</span><span class="sxs-lookup"><span data-stu-id="acb34-133">Logical AND operator &amp;</span></span>

<span data-ttu-id="acb34-134">`&` 연산자는 해당 피연산자의 비트 논리 AND를 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-134">The `&` operator computes the bitwise logical AND of its operands:</span></span>

[!code-csharp-interactive[bitwise AND](snippets/shared/BitwiseAndShiftOperators.cs#BitwiseAnd)]

<span data-ttu-id="acb34-135">`bool` 피연산자의 경우 `&` 연산자는 피연산자의 [논리 AND](boolean-logical-operators.md#logical-and-operator-)를 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-135">For `bool` operands, the `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="acb34-136">단항 `&` 연산자는 [address-of 연산자](pointer-related-operators.md#address-of-operator-)입니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-136">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="acb34-137">논리 배타적 OR 연산자 ^</span><span class="sxs-lookup"><span data-stu-id="acb34-137">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="acb34-138">`^` 연산자는 해당 피연산자의 비트 논리 XOR이라고도 하는 비트 논리 배타적 OR을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-138">The `^` operator computes the bitwise logical exclusive OR, also known as the bitwise logical XOR, of its operands:</span></span>

[!code-csharp-interactive[bitwise XOR](snippets/shared/BitwiseAndShiftOperators.cs#BitwiseXor)]

<span data-ttu-id="acb34-139">`bool` 피연산자의 경우 `^` 연산자는 피연산자의 [논리 배타적 OR](boolean-logical-operators.md#logical-exclusive-or-operator-)을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-139">For `bool` operands, the `^` operator computes the [logical exclusive OR](boolean-logical-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="acb34-140">논리 OR 연산자 |</span><span class="sxs-lookup"><span data-stu-id="acb34-140">Logical OR operator |</span></span>

<span data-ttu-id="acb34-141">`|` 연산자는 해당 피연산자의 비트 논리 OR을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-141">The `|` operator computes the bitwise logical OR of its operands:</span></span>

[!code-csharp-interactive[bitwise OR](snippets/shared/BitwiseAndShiftOperators.cs#BitwiseOr)]

<span data-ttu-id="acb34-142">`bool` 피연산자의 경우 `|` 연산자는 피연산자의 [논리 OR](boolean-logical-operators.md#logical-or-operator-)을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-142">For `bool` operands, the `|` operator computes the [logical OR](boolean-logical-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="acb34-143">복합 할당</span><span class="sxs-lookup"><span data-stu-id="acb34-143">Compound assignment</span></span>

<span data-ttu-id="acb34-144">이진 연산자(`op`)의 경우 양식의 복합 할당 식</span><span class="sxs-lookup"><span data-stu-id="acb34-144">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="acb34-145">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-145">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="acb34-146">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-146">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="acb34-147">다음 예제에서는 비트 및 시프트 연산자를 사용하는 복합 할당의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-147">The following example demonstrates the usage of compound assignment with bitwise and shift operators:</span></span>

[!code-csharp-interactive[compound assignment](snippets/shared/BitwiseAndShiftOperators.cs#CompoundAssignment)]

<span data-ttu-id="acb34-148">[숫자 승격](~/_csharplang/spec/expressions.md#numeric-promotions)으로 인해 `op` 연산의 결과가 암시적으로 `x`의 `T` 형식으로 변환되지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-148">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="acb34-149">이 경우 `op`가 미리 정의된 연산자이고 연산의 결과가 명시적으로 `x`의 `T` 형식으로 변환 가능하다면 `x op= y` 양식의 복합 할당 식이 `x = (T)(x op y)`에 해당합니다. 단 `x`는 한 번만 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-149">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="acb34-150">다음 예제에서는 해당 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-150">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](snippets/shared/BitwiseAndShiftOperators.cs#CompoundAssignmentWithCast)]

## <a name="operator-precedence"></a><span data-ttu-id="acb34-151">연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="acb34-151">Operator precedence</span></span>

<span data-ttu-id="acb34-152">다음 목록에서는 비트 및 시프트 연산자를 가장 높은 우선순위부터 가장 낮은 것으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-152">The following list orders bitwise and shift operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="acb34-153">비트 보수 연산자 `~`</span><span class="sxs-lookup"><span data-stu-id="acb34-153">Bitwise complement operator `~`</span></span>
- <span data-ttu-id="acb34-154">시프트 연산자 `<<` 및 `>>`</span><span class="sxs-lookup"><span data-stu-id="acb34-154">Shift operators `<<` and `>>`</span></span>
- <span data-ttu-id="acb34-155">논리 AND 연산자 `&`</span><span class="sxs-lookup"><span data-stu-id="acb34-155">Logical AND operator `&`</span></span>
- <span data-ttu-id="acb34-156">논리 배타적 OR 연산자 `^`</span><span class="sxs-lookup"><span data-stu-id="acb34-156">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="acb34-157">논리 OR 연산자 `|`</span><span class="sxs-lookup"><span data-stu-id="acb34-157">Logical OR operator `|`</span></span>

<span data-ttu-id="acb34-158">괄호(`()`)를 사용하여 연산자 우선 순위에 따라 주어진 평가 순서를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-158">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](snippets/shared/BitwiseAndShiftOperators.cs#Precedence)]

<span data-ttu-id="acb34-159">우선 순위 수준에 따라 정렬된 전체 연산자 목록은 [C# 연산자](index.md#operator-precedence) 문서의 [연산자 우선 순위](index.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acb34-159">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="shift-count-of-the-shift-operators"></a><span data-ttu-id="acb34-160">시프트 연산자의 시프트 수</span><span class="sxs-lookup"><span data-stu-id="acb34-160">Shift count of the shift operators</span></span>

<span data-ttu-id="acb34-161">시트프 연산자 `<<` 및 `>>`의 경우 오른쪽 피연산자의 형식은 `int`이거나 `int`로의 [미리 정의된 암시적 숫자 변환](../builtin-types/numeric-conversions.md#implicit-numeric-conversions)이 있는 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-161">For the shift operators `<<` and `>>`, the type of the right-hand operand must be `int` or a type that has a [predefined implicit numeric conversion](../builtin-types/numeric-conversions.md#implicit-numeric-conversions) to `int`.</span></span>

<span data-ttu-id="acb34-162">`x << count` 및 `x >> count`식의 경우 실제 시프트 수는 다음과 같이 `x` 형식에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-162">For the `x << count` and `x >> count` expressions, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="acb34-163">`x`의 형식이 `int` 또는 `uint`이면 시프트 수는 오른쪽 피연산자의 하위 *5*비트로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-163">If the type of `x` is `int` or `uint`, the shift count is defined by the low-order *five* bits of the right-hand operand.</span></span> <span data-ttu-id="acb34-164">즉, 시프트 수는 `count & 0x1F`(또는 `count & 0b_1_1111`)에서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-164">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="acb34-165">`x`의 형식이 `long` 또는 `ulong`이면 시프트 수는 오른쪽 피연산자의 하위 *6*비트로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-165">If the type of `x` is `long` or `ulong`, the shift count is defined by the low-order *six* bits of the right-hand operand.</span></span> <span data-ttu-id="acb34-166">즉, 시프트 수는 `count & 0x3F`(또는 `count & 0b_11_1111`)에서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-166">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="acb34-167">다음 예제에서는 해당 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-167">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](snippets/shared/BitwiseAndShiftOperators.cs#ShiftCount)]

> [!NOTE]
> <span data-ttu-id="acb34-168">앞의 예제에서 볼 수 있듯이 오른쪽 피연산자의 값이 왼쪽 피연산자의 비트 수보다 크면 시프트 연산의 결과가 0이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-168">As the preceding example shows, the result of a shift operation can be non-zero even if the value of the right-hand operand is greater than the number of bits in the left-hand operand.</span></span>

## <a name="enumeration-logical-operators"></a><span data-ttu-id="acb34-169">열거형 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="acb34-169">Enumeration logical operators</span></span>

<span data-ttu-id="acb34-170">`~`, `&`, `|` 및 `^` 연산자도 [열거형](../builtin-types/enum.md) 형식에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-170">The `~`, `&`, `|`, and `^` operators are also supported by any [enumeration](../builtin-types/enum.md) type.</span></span> <span data-ttu-id="acb34-171">동일한 열거형 형식의 피연산자인 경우, 기본 정수 형식의 해당 값에 대해 논리 연산을 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-171">For operands of the same enumeration type, a logical operation is performed on the corresponding values of the underlying integral type.</span></span> <span data-ttu-id="acb34-172">예를 들어 기본 형식이 `U`인 열거형 형식 `T`의 `x` 및 `y`에 대해 `x & y` 식은 `(T)((U)x & (U)y)` 식과 동일한 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-172">For example, for any `x` and `y` of an enumeration type `T` with an underlying type `U`, the `x & y` expression produces the same result as the `(T)((U)x & (U)y)` expression.</span></span>

<span data-ttu-id="acb34-173">일반적으로 [Flags](xref:System.FlagsAttribute) 특성으로 정의된 열거형 형식을 가진 비트 논리 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-173">You typically use bitwise logical operators with an enumeration type that is defined with the [Flags](xref:System.FlagsAttribute) attribute.</span></span> <span data-ttu-id="acb34-174">자세한 내용은 [열거형 형식](../builtin-types/enum.md) 문서의 [비트 플래그로서 열거형 형식](../builtin-types/enum.md#enumeration-types-as-bit-flags)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acb34-174">For more information, see the [Enumeration types as bit flags](../builtin-types/enum.md#enumeration-types-as-bit-flags) section of the [Enumeration types](../builtin-types/enum.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="acb34-175">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="acb34-175">Operator overloadability</span></span>

<span data-ttu-id="acb34-176">사용자 정의 형식은 `~`, `<<`, `>>`, `&`, `|` 및 `^` 연산자를 [오버로드](operator-overloading.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-176">A user-defined type can [overload](operator-overloading.md) the `~`, `<<`, `>>`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="acb34-177">이항 연산자가 오버로드되면 해당하는 복합 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-177">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="acb34-178">사용자 정의 형식은 복합 대입 연산자를 명시적으로 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-178">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="acb34-179">사용자 정의 형식 `T`가 `<<` 또는 `>>` 연산자를 오버로드하는 경우 첫 번째 피연산자의 형식은 `T`여야 하고, 두 번째 피연산자의 형식은 `int`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acb34-179">If a user-defined type `T` overloads the `<<` or `>>` operator, the type of the left-hand operand must be `T` and the type of the right-hand operand must be `int`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="acb34-180">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="acb34-180">C# language specification</span></span>

<span data-ttu-id="acb34-181">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acb34-181">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="acb34-182">비트 보수 연산자</span><span class="sxs-lookup"><span data-stu-id="acb34-182">Bitwise complement operator</span></span>](~/_csharplang/spec/expressions.md#bitwise-complement-operator)
- [<span data-ttu-id="acb34-183">시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="acb34-183">Shift operators</span></span>](~/_csharplang/spec/expressions.md#shift-operators)
- [<span data-ttu-id="acb34-184">논리 연산자</span><span class="sxs-lookup"><span data-stu-id="acb34-184">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="acb34-185">복합 할당</span><span class="sxs-lookup"><span data-stu-id="acb34-185">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="acb34-186">숫자 승격</span><span class="sxs-lookup"><span data-stu-id="acb34-186">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="acb34-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acb34-187">See also</span></span>

- [<span data-ttu-id="acb34-188">C# 참조</span><span class="sxs-lookup"><span data-stu-id="acb34-188">C# reference</span></span>](../index.md)
- [<span data-ttu-id="acb34-189">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="acb34-189">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="acb34-190">부울 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="acb34-190">Boolean logical operators</span></span>](boolean-logical-operators.md)
