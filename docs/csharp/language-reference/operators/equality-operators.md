---
title: 같음 연산자 - C# 참조
description: C# 같음 비교 연산자 및 C# 형식 같음에 대해 알아봅니다.
ms.date: 06/26/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 6771edcca8159b0805018c16167b25c287d3152c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743735"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="1f7aa-103">같음 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1f7aa-103">Equality operators (C# reference)</span></span>

<span data-ttu-id="1f7aa-104">[`==`(같음)](#equality-operator-) 및 [`!=`(같지 않음)](#inequality-operator-) 연산자는 피연산자가 같은지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-104">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="1f7aa-105">같음 연산자 ==</span><span class="sxs-lookup"><span data-stu-id="1f7aa-105">Equality operator ==</span></span>

<span data-ttu-id="1f7aa-106">같음 연산자 `==`는 피연산자가 같으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-106">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="1f7aa-107">값 형식 같음</span><span class="sxs-lookup"><span data-stu-id="1f7aa-107">Value types equality</span></span>

<span data-ttu-id="1f7aa-108">[기본 제공 값 형식](../builtin-types/value-types.md#built-in-value-types)의 피연산자는 해당 값이 같은 경우 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-108">Operands of the [built-in value types](../builtin-types/value-types.md#built-in-value-types) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="1f7aa-109">`==`, [, `<`, `>`, `<=` 및 `>=`](comparison-operators.md) 연산자의 경우 피연산자 중 하나가 숫자(<xref:System.Double.NaN?displayProperty=nameWithType> 또는 <xref:System.Single.NaN?displayProperty=nameWithType>)가 아니면 연산의 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-109">For the `==`, [`<`, `>`, `<=`, and `>=`](comparison-operators.md) operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="1f7aa-110">즉, `NaN` 값이 `NaN`를 포함한 다른 `double`(또는 `float`) 값보다 크거나, 작거나, 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-110">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="1f7aa-111">자세한 내용과 예제는 <xref:System.Double.NaN?displayProperty=nameWithType> 또는 <xref:System.Single.NaN?displayProperty=nameWithType> 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-111">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="1f7aa-112">기본 정수 형식의 해당 값이 같은 경우 동일한 [열거형](../builtin-types/enum.md) 형식의 피연산자가 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-112">Two operands of the same [enum](../builtin-types/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="1f7aa-113">사용자 정의 [구조체](../keywords/struct.md) 형식은 기본적으로 `==` 연산자를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-113">User-defined [struct](../keywords/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="1f7aa-114">`==` 연산자를 지원하려면 사용자 정의 구조체가 해당 연산자를 [오버로드](operator-overloading.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-114">To support the `==` operator, a user-defined struct must [overload](operator-overloading.md) it.</span></span>

<span data-ttu-id="1f7aa-115">C# 7.3부터는 `==` 및 `!=` 연산자가 C# [튜플](../../tuples.md)에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-115">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="1f7aa-116">자세한 내용은 [C# 튜플 형식](../../tuples.md) 문서의 [같음 및 튜플](../../tuples.md#equality-and-tuples) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-116">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="1f7aa-117">참조 형식 같음</span><span class="sxs-lookup"><span data-stu-id="1f7aa-117">Reference types equality</span></span>

<span data-ttu-id="1f7aa-118">기본적으로 두 개의 참조 형식 피연산자는 동일한 개체를 참조하는 경우 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-118">By default, two reference-type operands are equal if they refer to the same object:</span></span>

[!code-csharp[reference type equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ReferenceTypesEquality)]

<span data-ttu-id="1f7aa-119">이 예제에서 표시한 대로 사용자 지정 참조 형식은 기본적으로 `==` 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-119">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="1f7aa-120">그러나 참조 형식은 `==` 연산자를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-120">However, a reference type can overload the `==` operator.</span></span> <span data-ttu-id="1f7aa-121">참조 형식이 `==` 연산자를 오버로드하는 경우 <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> 메서드를 사용하여 해당 형식의 두 참조가 동일한 개체를 참조하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-121">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

### <a name="string-equality"></a><span data-ttu-id="1f7aa-122">문자열 같음</span><span class="sxs-lookup"><span data-stu-id="1f7aa-122">String equality</span></span>

<span data-ttu-id="1f7aa-123">두 개의 [문자열](../builtin-types/reference-types.md#the-string-type) 피연산자가 모두 `null`이거나 두 문자열 인스턴스가 같은 길이고 각 문자 위치에 동일한 문자가 있을 때 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-123">Two [string](../builtin-types/reference-types.md#the-string-type) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#StringEquality)]

<span data-ttu-id="1f7aa-124">대/소문자 구분 서수 비교입니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-124">That is a case-sensitive ordinal comparison.</span></span> <span data-ttu-id="1f7aa-125">문자열 비교에 대한 자세한 내용은 [C#에서 문자열을 비교하는 방법](../../how-to/compare-strings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-125">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="delegate-equality"></a><span data-ttu-id="1f7aa-126">대리자 같음</span><span class="sxs-lookup"><span data-stu-id="1f7aa-126">Delegate equality</span></span>

<span data-ttu-id="1f7aa-127">동일한 런타임 형식의 두 [대리자](../../programming-guide/delegates/index.md) 피연산자가 둘 다 `null`이거나 해당 호출 목록의 길이가 같고 각 위치에 동일한 항목이 있는 경우 두 피연산자는 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-127">Two [delegate](../../programming-guide/delegates/index.md) operands of the same runtime type are equal when both of them are `null` or their invocation lists are of the same length and have equal entries in each position:</span></span>

[!code-csharp-interactive[delegate equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#DelegateEquality)]

<span data-ttu-id="1f7aa-128">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [대리자 같음 연산자](~/_csharplang/spec/expressions.md#delegate-equality-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-128">For more information, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="1f7aa-129">의미상 동일한 [람다 식](../../programming-guide/statements-expressions-operators/lambda-expressions.md) 평가에서 생성된 대리자는 다음 예제와 같이 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-129">Delegates that are produced from evaluation of semantically identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal, as the following example shows:</span></span>

[!code-csharp-interactive[from identical lambdas](~/samples/csharp/language-reference/operators/EqualityOperators.cs#IdenticalLambdas)]

## <a name="inequality-operator-"></a><span data-ttu-id="1f7aa-130">같지 않음 연산자 !=</span><span class="sxs-lookup"><span data-stu-id="1f7aa-130">Inequality operator !=</span></span>

<span data-ttu-id="1f7aa-131">같지 않음 연산자 `!=`는 피연산자가 같지 않으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-131">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="1f7aa-132">[기본 제공 형식](../keywords/built-in-types-table.md)의 피연산자의 경우 식 `x != y`는 식 `!(x == y)`와 동일한 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-132">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="1f7aa-133">형식 같음에 대한 자세한 내용은 [같음 연산자](#equality-operator-) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-133">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="1f7aa-134">다음 예제에서는 `!=` 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-134">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/csharp/language-reference/operators/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="1f7aa-135">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="1f7aa-135">Operator overloadability</span></span>

<span data-ttu-id="1f7aa-136">사용자 정의 형식은 `==` 및 `!=` 연산자를 [오버로드](operator-overloading.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-136">A user-defined type can [overload](operator-overloading.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="1f7aa-137">형식이 두 연산자 중 하나를 오버로드하는 경우 나머지 연산자도 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-137">If a type overloads one of the two operators, it must also overload another one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1f7aa-138">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="1f7aa-138">C# language specification</span></span>

<span data-ttu-id="1f7aa-139">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [관계형 및 형식 테스트 연산자](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f7aa-139">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1f7aa-140">참조</span><span class="sxs-lookup"><span data-stu-id="1f7aa-140">See also</span></span>

- [<span data-ttu-id="1f7aa-141">C# 참조</span><span class="sxs-lookup"><span data-stu-id="1f7aa-141">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1f7aa-142">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="1f7aa-142">C# operators</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1f7aa-143">같음 비교</span><span class="sxs-lookup"><span data-stu-id="1f7aa-143">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [<span data-ttu-id="1f7aa-144">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="1f7aa-144">Comparison operators</span></span>](comparison-operators.md)
