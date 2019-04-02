---
title: '>= 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 0dd3aa8976c10f0adc5dc7620237991202f772ee
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545548"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d13cd-102">>= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d13cd-102">>= Operator (C# Reference)</span></span>

<span data-ttu-id="d13cd-103">"크거나 같음" 관계 연산자 `>=`은 첫 번째 피연산자가 두 번째 피연산자 보다 크거나 같으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d13cd-103">The "greater than or equal" relational operator `>=` returns `true` if its first operand is greater than or equal to its second operand, `false` otherwise.</span></span> <span data-ttu-id="d13cd-104">모든 숫자 및 열거형 형식은 `>=` 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d13cd-104">All numeric and  enumeration types support the `>=` operator.</span></span> <span data-ttu-id="d13cd-105">동일한 [열거형](../keywords/enum.md) 형식의 피연산자의 경우 기본 정수 형식의 해당 값이 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="d13cd-105">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

> [!NOTE]
> <span data-ttu-id="d13cd-106">관계형 연산자 `==`, `>`, `<`, `>=` 및 `<=`의 경우 피연산자 중 하나가 숫자(<xref:System.Double.NaN?displayProperty=nameWithType> 또는 <xref:System.Single.NaN?displayProperty=nameWithType>)가 아니s며 연산의 결과는 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d13cd-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="d13cd-107">이는 `NaN` 값이 다른 `double`(또는 `float`) 값보다 크거나, 작거나, 같지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d13cd-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="d13cd-108">자세한 내용과 예제는 <xref:System.Double.NaN?displayProperty=nameWithType> 또는 <xref:System.Single.NaN?displayProperty=nameWithType> 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d13cd-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="d13cd-109">다음 예제에서는 `>=` 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d13cd-109">The following example demonstrates the usage of the `>=` operator:</span></span>

[!code-csharp-interactive[greater than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="d13cd-110">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="d13cd-110">Operator overloadability</span></span>

<span data-ttu-id="d13cd-111">사용자 정의 형식은 `>=` 연산자를 [오버로드](../keywords/operator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d13cd-111">User-defined types can [overload](../keywords/operator.md) the `>=` operator.</span></span> <span data-ttu-id="d13cd-112">형식이 "크거나 같음" 연산자 `>=`을 오버로드하는 경우 ["작거나 같음" 연산자](less-than-equal-operator.md) `<=`도 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d13cd-112">If a type overloads the "greater than or equal" operator `>=`, it must also overload the ["less than or equal" operator](less-than-equal-operator.md) `<=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d13cd-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d13cd-113">C# language specification</span></span>

<span data-ttu-id="d13cd-114">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [관계형 및 형식 테스트 연산자](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d13cd-114">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d13cd-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d13cd-115">See also</span></span>

- [<span data-ttu-id="d13cd-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d13cd-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d13cd-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d13cd-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d13cd-118">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="d13cd-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="d13cd-119">> 연산자</span><span class="sxs-lookup"><span data-stu-id="d13cd-119">> Operator</span></span>](greater-than-operator.md)
- [<span data-ttu-id="d13cd-120">== 연산자</span><span class="sxs-lookup"><span data-stu-id="d13cd-120">== Operator</span></span>](equality-operators.md#equality-operator-)
- <xref:System.IComparable%601?displayProperty=nameWithType>
