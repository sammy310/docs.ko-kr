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
ms.openlocfilehash: ea8d8ab5ac14ec94c647ed33cca6f949a90737bd
ms.sourcegitcommit: dd3b897feb5c4ac39732bb165848e37a344b0765
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/25/2019
ms.locfileid: "64431612"
---
# <a name="comparison-operators-c-reference"></a><span data-ttu-id="b8c5f-103">비교 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b8c5f-103">Comparison operators (C# Reference)</span></span>

<span data-ttu-id="b8c5f-104">[`<`(보다 작음)](#less-than-operator-), [`>`(보다 큼)](#greater-than-operator-), [`<=`(작거나 같음)](#less-than-or-equal-operator-) 및 [`>=`(크거나 같음)](#greater-than-or-equal-operator-) 비교는 관계형 연산자라고도 하며, 피연사자를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-104">The [`<` (less than)](#less-than-operator-), [`>` (greater than)](#greater-than-operator-), [`<=` (less than or equal)](#less-than-or-equal-operator-), and [`>=` (greater than or equal)](#greater-than-or-equal-operator-) comparison, also known as relational, operators compare their operands.</span></span> <span data-ttu-id="b8c5f-105">해당 연산자는 모든 [정수](../keywords/integral-types-table.md) 및 [부동 소수점](../keywords/floating-point-types-table.md) 숫자 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-105">Those operators support all [integral](../keywords/integral-types-table.md) and [floating-point](../keywords/floating-point-types-table.md) numeric types.</span></span>

> [!NOTE]
> <span data-ttu-id="b8c5f-106">`==`, `<`, `>`, `<=` 및 `>=` 연산자의 경우 피연산자 중 하나가 숫자(<xref:System.Double.NaN?displayProperty=nameWithType> 또는 <xref:System.Single.NaN?displayProperty=nameWithType>)가 아니면 연산의 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-106">For the `==`, `<`, `>`, `<=`, and `>=` operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="b8c5f-107">즉, `NaN` 값이 `NaN`를 포함한 다른 `double`(또는 `float`) 값보다 크거나, 작거나, 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="b8c5f-108">자세한 내용과 예제는 <xref:System.Double.NaN?displayProperty=nameWithType> 또는 <xref:System.Single.NaN?displayProperty=nameWithType> 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="b8c5f-109">열거형 형식은 비교 연산자도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-109">Enumeration types also support comparison operators.</span></span> <span data-ttu-id="b8c5f-110">동일한 [열거형](../keywords/enum.md) 형식의 피연산자의 경우 기본 정수 형식의 해당 값이 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-110">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

<span data-ttu-id="b8c5f-111">[`==` 및 `!=` 연산자는](equality-operators.md) 피연산자가 같은지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-111">The [`==` and `!=` operators](equality-operators.md) check if their operands are equal or not.</span></span>

## <a name="less-than-operator-"></a><span data-ttu-id="b8c5f-112">보다 작음 연산자 \<</span><span class="sxs-lookup"><span data-stu-id="b8c5f-112">Less than operator \<</span></span>

<span data-ttu-id="b8c5f-113">`<` 연산자는 첫 번째 피연산자가 두 번째 피연산자보다 작으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-113">The `<` operator returns `true` if its first operand is less than its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Less)]

## <a name="greater-than-operator-"></a><span data-ttu-id="b8c5f-114">보다 큼 연산자 ></span><span class="sxs-lookup"><span data-stu-id="b8c5f-114">Greater than operator ></span></span>

<span data-ttu-id="b8c5f-115">`>` 연산자는 첫 번째 피연산자가 두 번째 피연산자보다 크면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-115">The `>` operator returns `true` if its first operand is greater than its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a><span data-ttu-id="b8c5f-116">작거나 같음 연산자 \<=</span><span class="sxs-lookup"><span data-stu-id="b8c5f-116">Less than or equal operator \<=</span></span>

<span data-ttu-id="b8c5f-117">`<=` 연산자는 첫 번째 피연산자가 두 번째 피연산자보다 작거나 같으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-117">The `<=` operator returns `true` if its first operand is less than or equal to its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a><span data-ttu-id="b8c5f-118">크거나 같음 연산자 >=</span><span class="sxs-lookup"><span data-stu-id="b8c5f-118">Greater than or equal operator >=</span></span>

<span data-ttu-id="b8c5f-119">`>=` 연산자는 첫 번째 피연산자가 두 번째 피연산자보다 크거나 같으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-119">The `>=` operator returns `true` if its first operand is greater than or equal to its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="b8c5f-120">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="b8c5f-120">Operator overloadability</span></span>

<span data-ttu-id="b8c5f-121">사용자 정의 형식은 `<`, `>`, `<=` 및 `>=` 연산자를 [오버로드](../keywords/operator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-121">A user-defined type can [overload](../keywords/operator.md) the `<`, `>`, `<=`, and `>=` operators.</span></span>

<span data-ttu-id="b8c5f-122">형식이 `<` 또는 `>` 연산자 중 하나를 오버로드하는 경우 `<` 및 `>` 모두 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-122">If a type overloads one of the `<` or `>` operators, it must overload both `<` and `>`.</span></span> <span data-ttu-id="b8c5f-123">형식이 `<=` 또는 `>=` 연산자 중 하나를 오버로드하는 경우 `<=` 및 `>=` 모두 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-123">If a type overloads one of the `<=` or `>=` operators, it must overload both `<=` and `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b8c5f-124">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="b8c5f-124">C# language specification</span></span>

<span data-ttu-id="b8c5f-125">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [관계형 및 형식 테스트 연산자](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8c5f-125">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8c5f-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8c5f-126">See also</span></span>

- [<span data-ttu-id="b8c5f-127">C# 참조</span><span class="sxs-lookup"><span data-stu-id="b8c5f-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b8c5f-128">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b8c5f-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b8c5f-129">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="b8c5f-129">C# Operators</span></span>](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [<span data-ttu-id="b8c5f-130">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="b8c5f-130">Equality operators</span></span>](equality-operators.md)
