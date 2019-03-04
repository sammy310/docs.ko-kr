---
title: '?: 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: c3c875cf5b8d1b5e69cd76cb0ee4df0a989a35a0
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202901"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="e94ef-102">?: 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e94ef-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="e94ef-103">일반적으로 3개로 구성된 조건부 연산자라고 하는 조건부 연산자 `?:`은 부울 식을 계산하고 부울 식이 `true` 또는 `false`으로 계산되는지에 따라 두 식 중 하나의 계산 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-103">The conditional operator `?:`, commonly known as the ternary conditional operator, evaluates a Boolean expression, and returns the result of evaluating one of two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="e94ef-104">C# 7.2부터 [조건부 ref 식](#conditional-ref-expression)은 두 식 중 하나의 결과에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="e94ef-105">조건 연산자의 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequence : alternative
```

<span data-ttu-id="e94ef-106">`condition` 식은 `true` 또는 `false`로 계산되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="e94ef-107">`condition`이 `true`로 계산되면 `consequence` 식이 계산되고 해당 결과가 연산 결과가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-107">If `condition` evaluates to `true`, the `consequence` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="e94ef-108">`condition`이 `false`로 계산되면 `alternative` 식이 계산되고 해당 결과가 연산 결과가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="e94ef-109">`consequence` 또는 `alternative`만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-109">Only `consequence` or `alternative` is evaluated.</span></span>

<span data-ttu-id="e94ef-110">`consequence` 및 `alternative`의 형식이 동일해야 하거나 한 형식에서 다른 형식으로 암시적 변환이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-110">The type of `consequence` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="e94ef-111">조건부 연산자는 오른쪽 결합성입니다. 즉, 다음 형식의 식을 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="e94ef-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="e94ef-112">이 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

<span data-ttu-id="e94ef-113">다음 예제에서는 조건부 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-113">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="e94ef-114">조건부 ref 식</span><span class="sxs-lookup"><span data-stu-id="e94ef-114">Conditional ref expression</span></span>

<span data-ttu-id="e94ef-115">C# 7.2부터 조건부 ref 식을 사용하여 두 식 중 하나의 결과에 대한 참조를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-115">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="e94ef-116">[ref 지역](../keywords/ref.md#ref-locals) 또는 [ref readonly 지역](../keywords/ref.md#ref-readonly-locals) 변수에 해당 참조를 할당하거나, [참조 반환 값](../keywords/ref.md#reference-return-values) 또는 [ `ref` 메서드 매개 변수](../keywords/ref.md#passing-an-argument-by-reference)로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-116">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="e94ef-117">조건부 ref 식의 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-117">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequence : ref alternative
```

<span data-ttu-id="e94ef-118">원래 조건부 연산자와 마찬가지로 조건부 ref 식은 두 식 중 하나(`consequence` 또는 `alternative`)만 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-118">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequence` or `alternative`.</span></span>

<span data-ttu-id="e94ef-119">조건부 ref 식의 경우 `consequence` 및 `alternative`의 형식이 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-119">In the case of the conditional ref expression, the type of `consequence` and `alternative` must be the same.</span></span>

<span data-ttu-id="e94ef-120">다음 예제에서는 조건부 ref 식의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-120">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

<span data-ttu-id="e94ef-121">자세한 내용은 [기능 제안 노트](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e94ef-121">For more information, see the [feature proposal note](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="e94ef-122">조건부 연산자 및 `if..else` 문</span><span class="sxs-lookup"><span data-stu-id="e94ef-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="e94ef-123">[if-else](../keywords/if-else.md) 문보다 조건부 연산자를 사용하면 조건부로 값을 계산해야 하는 경우 코드가 보다 간결해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-123">Use of the conditional operator over an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="e94ef-124">다음 예제에서는 정수를 음수 또는 음수가 아닌 값으로 분류하는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="e94ef-125">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="e94ef-125">Operator overloadability</span></span>

<span data-ttu-id="e94ef-126">조건 연산자는 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e94ef-126">The conditional operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e94ef-127">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="e94ef-127">C# language specification</span></span>

<span data-ttu-id="e94ef-128">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [조건부 연산자](~/_csharplang/spec/expressions.md#conditional-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e94ef-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e94ef-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e94ef-129">See also</span></span>

- [<span data-ttu-id="e94ef-130">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e94ef-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e94ef-131">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e94ef-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e94ef-132">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="e94ef-132">C# Operators</span></span>](index.md)
- [<span data-ttu-id="e94ef-133">if-else 문</span><span class="sxs-lookup"><span data-stu-id="e94ef-133">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="e94ef-134">[?. 및 ?[] 연산자](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="e94ef-134">[?. and ?[] Operators](null-conditional-operators.md)</span></span>
- [<span data-ttu-id="e94ef-135">?? 연산자</span><span class="sxs-lookup"><span data-stu-id="e94ef-135">?? Operator</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="e94ef-136">ref 키워드</span><span class="sxs-lookup"><span data-stu-id="e94ef-136">ref keyword</span></span>](../keywords/ref.md)
