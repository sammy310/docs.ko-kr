---
title: 비교 연산자 - C# 참조
description: 숫자 값 순서를 확인하는 데 사용할 수 있는 C# 비교 연산자에 대해 알아봅니다.
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: 86f557d0575b440455fd6363f0d0d6783a9e7acc
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345324"
---
# <a name="comparison-operators-c-reference"></a><span data-ttu-id="d8363-103">비교 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d8363-103">Comparison operators (C# reference)</span></span>

<span data-ttu-id="d8363-104">[`<`(보다 작음)](#less-than-operator-), [`>`(보다 큼)](#greater-than-operator-), [`<=`(작거나 같음)](#less-than-or-equal-operator-) 및 [`>=`(크거나 같음)](#greater-than-or-equal-operator-) 비교는 관계형 연산자라고도 하며, 피연사자를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-104">The [`<` (less than)](#less-than-operator-), [`>` (greater than)](#greater-than-operator-), [`<=` (less than or equal)](#less-than-or-equal-operator-), and [`>=` (greater than or equal)](#greater-than-or-equal-operator-) comparison, also known as relational, operators compare their operands.</span></span> <span data-ttu-id="d8363-105">해당 연산자는 모든 [정수](../builtin-types/integral-numeric-types.md) 및 [부동 소수점](../builtin-types/floating-point-numeric-types.md) 숫자 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-105">Those operators are supported by all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

> [!NOTE]
> <span data-ttu-id="d8363-106">`==`, `<`, `>`, `<=` 및 `>=` 연산자의 경우 피연산자 중 하나가 숫자(<xref:System.Double.NaN?displayProperty=nameWithType> 또는 <xref:System.Single.NaN?displayProperty=nameWithType>)가 아니면 연산의 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-106">For the `==`, `<`, `>`, `<=`, and `>=` operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="d8363-107">즉, `NaN` 값이 `NaN`를 포함한 다른 `double`(또는 `float`) 값보다 크거나, 작거나, 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="d8363-108">자세한 내용과 예제는 <xref:System.Double.NaN?displayProperty=nameWithType> 또는 <xref:System.Single.NaN?displayProperty=nameWithType> 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8363-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="d8363-109">열거형 형식은 비교 연산자도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-109">Enumeration types also support comparison operators.</span></span> <span data-ttu-id="d8363-110">동일한 [열거형](../builtin-types/enum.md) 형식의 피연산자의 경우 기본 정수 형식의 해당 값이 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-110">For operands of the same [enum](../builtin-types/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

<span data-ttu-id="d8363-111">[`==` 및 `!=` 연산자는](equality-operators.md) 피연산자가 같은지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-111">The [`==` and `!=` operators](equality-operators.md) check if their operands are equal or not.</span></span>

## <a name="less-than-operator-"></a><span data-ttu-id="d8363-112">보다 작음 연산자 \<</span><span class="sxs-lookup"><span data-stu-id="d8363-112">Less than operator \<</span></span>

<span data-ttu-id="d8363-113">`<` 연산자는 왼쪽 피연산자가 오른쪽 피연산자보다 작으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-113">The `<` operator returns `true` if its left-hand operand is less than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a><span data-ttu-id="d8363-114">보다 큼 연산자 ></span><span class="sxs-lookup"><span data-stu-id="d8363-114">Greater than operator ></span></span>

<span data-ttu-id="d8363-115">`>` 연산자는 왼쪽 피연산자가 오른쪽 피연산자보다 크면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-115">The `>` operator returns `true` if its left-hand operand is greater than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a><span data-ttu-id="d8363-116">작거나 같음 연산자 \<=</span><span class="sxs-lookup"><span data-stu-id="d8363-116">Less than or equal operator \<=</span></span>

<span data-ttu-id="d8363-117">`<=` 연산자는 왼쪽 피연산자가 오른쪽 피연산자보다 작거나 같으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-117">The `<=` operator returns `true` if its left-hand operand is less than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a><span data-ttu-id="d8363-118">크거나 같음 연산자 >=</span><span class="sxs-lookup"><span data-stu-id="d8363-118">Greater than or equal operator >=</span></span>

<span data-ttu-id="d8363-119">`>=` 연산자는 왼쪽 피연산자가 오른쪽 피연산자보다 크거나 같으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-119">The `>=` operator returns `true` if its left-hand operand is greater than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="d8363-120">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="d8363-120">Operator overloadability</span></span>

<span data-ttu-id="d8363-121">사용자 정의 형식은 `<`, `>`, `<=` 및 `>=` 연산자를 [오버로드](operator-overloading.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-121">A user-defined type can [overload](operator-overloading.md) the `<`, `>`, `<=`, and `>=` operators.</span></span>

<span data-ttu-id="d8363-122">형식이 `<` 또는 `>` 연산자 중 하나를 오버로드하는 경우 `<` 및 `>` 모두 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-122">If a type overloads one of the `<` or `>` operators, it must overload both `<` and `>`.</span></span> <span data-ttu-id="d8363-123">형식이 `<=` 또는 `>=` 연산자 중 하나를 오버로드하는 경우 `<=` 및 `>=` 모두 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8363-123">If a type overloads one of the `<=` or `>=` operators, it must overload both `<=` and `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d8363-124">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d8363-124">C# language specification</span></span>

<span data-ttu-id="d8363-125">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [관계형 및 형식 테스트 연산자](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8363-125">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d8363-126">참조</span><span class="sxs-lookup"><span data-stu-id="d8363-126">See also</span></span>

- [<span data-ttu-id="d8363-127">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d8363-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d8363-128">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="d8363-128">C# operators</span></span>](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [<span data-ttu-id="d8363-129">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="d8363-129">Equality operators</span></span>](equality-operators.md)
