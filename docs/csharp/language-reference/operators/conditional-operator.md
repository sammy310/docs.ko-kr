---
description: '?: 연산자 - C# 참조'
title: '?: 연산자 - C# 참조'
ms.date: 09/17/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: b6add045983619169bed0cd9f32eb27dba0a0338
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738881"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="18b02-103">?: 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="18b02-103">?: operator (C# reference)</span></span>

<span data-ttu-id="18b02-104">3개로 구성된 조건부 연산자라고도 하는 조건부 연산자 `?:`은 부울 식을 계산하고 부울 식이 `true` 또는 `false`으로 계산되는지에 따라 두 식 중 하나의 계산 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-104">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span>

<span data-ttu-id="18b02-105">조건 연산자의 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="18b02-106">`condition` 식은 `true` 또는 `false`로 계산되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="18b02-107">`condition`이 `true`로 계산되면 `consequent` 식이 계산되고 해당 결과가 연산 결과가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="18b02-108">`condition`이 `false`로 계산되면 `alternative` 식이 계산되고 해당 결과가 연산 결과가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="18b02-109">`consequent` 또는 `alternative`만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="18b02-110">C# 9.0부터 조건식은 대상으로 유형화됩니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-110">Beginning with C# 9.0, conditional expressions are target-typed.</span></span> <span data-ttu-id="18b02-111">즉, 조건식의 대상 유형을 알고 있는 경우 `consequent` 및 `alternative`의 형식은 다음 예제와 같이 대상 유형으로 암시적으로 변환 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-111">That is, if a target type of a conditional expression is known, the types of `consequent` and `alternative` must be implicitly convertible to the target type, as the following example shows:</span></span>

[!code-csharp[target-typed conditional](snippets/shared/ConditionalOperator.cs#TargetTyped)]

<span data-ttu-id="18b02-112">조건식의 대상 유형을 모르는 경우(예: [`var`](../keywords/var.md) 키워드 사용) 또는 C# 8.0 이하에서 `consequent` 및 `alternative`의 형식이 같아야 하거나 한 형식에서 다른 형식으로 암시적인 변환이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-112">If a target type of a conditional expression is unknown (for example, when you use the [`var`](../keywords/var.md) keyword) or in C# 8.0 and earlier, the type of `consequent` and `alternative` must be the same or there must be an implicit conversion from one type to the other:</span></span>

[!code-csharp[not target-typed conditional](snippets/shared/ConditionalOperator.cs#NotTargetTyped)]

<span data-ttu-id="18b02-113">조건부 연산자는 오른쪽 결합성입니다. 즉, 다음 형식의 식을 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="18b02-113">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="18b02-114">이 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-114">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="18b02-115">다음과 같은 니모닉 디바이스를 사용하여 조건부 연산자의 평가 방식을 기억할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-115">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="18b02-116">다음 예제에서는 조건부 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-116">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="18b02-117">조건부 ref 식</span><span class="sxs-lookup"><span data-stu-id="18b02-117">Conditional ref expression</span></span>

<span data-ttu-id="18b02-118">C# 7.2부터 조건부 ref 식으로 [ref 지역](../keywords/ref.md#ref-locals) 또는 [ref readonly 지역](../keywords/ref.md#ref-readonly-locals) 변수를 조건부로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-118">Beginning with C# 7.2, a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable can be assigned conditionally with a conditional ref expression.</span></span> <span data-ttu-id="18b02-119">조건부 ref 식을 [참조 반환 값](../keywords/ref.md#reference-return-values) 또는 [`ref` 메서드 인수](../keywords/ref.md#passing-an-argument-by-reference)로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-119">You can also use a conditional ref expression as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method argument](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="18b02-120">조건부 ref 식의 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-120">The syntax for a conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="18b02-121">원래 조건부 연산자와 마찬가지로 조건부 ref 식은 두 식 중 하나(`consequent` 또는 `alternative`)만 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-121">Like the original conditional operator, a conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="18b02-122">조건부 ref 식의 경우 `consequent` 및 `alternative`의 형식이 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-122">In the case of a conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span> <span data-ttu-id="18b02-123">조건부 ref 식은 대상으로 유형화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-123">Conditional ref expressions are not target-typed.</span></span>

<span data-ttu-id="18b02-124">다음 예제에서는 조건부 ref 식의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-124">The following example demonstrates the usage of a conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="18b02-125">조건부 연산자 및 `if..else` 문</span><span class="sxs-lookup"><span data-stu-id="18b02-125">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="18b02-126">[if-else](../keywords/if-else.md) 문보다 조건부 연산자를 사용하면 조건부로 값을 컴퓨팅해야 하는 경우 코드가 보다 간결해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-126">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="18b02-127">다음 예제에서는 정수를 음수 또는 음수가 아닌 값으로 분류하는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-127">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="18b02-128">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="18b02-128">Operator overloadability</span></span>

<span data-ttu-id="18b02-129">사용자 정의 형식으로 조건부 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18b02-129">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="18b02-130">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="18b02-130">C# language specification</span></span>

<span data-ttu-id="18b02-131">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [조건부 연산자](~/_csharplang/spec/expressions.md#conditional-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18b02-131">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="18b02-132">C# 7.2 이상에 추가된 기능에 대한 자세한 내용은 다음 기능 제안 노트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18b02-132">For more information about features added in C# 7.2 and later, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="18b02-133">조건부 ref 식(C# 7.2)</span><span class="sxs-lookup"><span data-stu-id="18b02-133">Conditional ref expressions (C# 7.2)</span></span>](~/_csharplang/proposals/csharp-7.2/conditional-ref.md)
- [<span data-ttu-id="18b02-134">대상으로 유형화된 조건식(C# 9.0)</span><span class="sxs-lookup"><span data-stu-id="18b02-134">Target-typed conditional expression (C# 9.0)</span></span>](~/_csharplang/proposals/csharp-9.0/target-typed-conditional-expression.md)

## <a name="see-also"></a><span data-ttu-id="18b02-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18b02-135">See also</span></span>

- [<span data-ttu-id="18b02-136">C# 참조</span><span class="sxs-lookup"><span data-stu-id="18b02-136">C# reference</span></span>](../index.md)
- [<span data-ttu-id="18b02-137">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="18b02-137">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="18b02-138">if-else 문</span><span class="sxs-lookup"><span data-stu-id="18b02-138">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="18b02-139">[?. 및 ?[] 연산자](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="18b02-139">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="18b02-140">및 ??= 연산자</span><span class="sxs-lookup"><span data-stu-id="18b02-140">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="18b02-141">ref 키워드</span><span class="sxs-lookup"><span data-stu-id="18b02-141">ref keyword</span></span>](../keywords/ref.md)
