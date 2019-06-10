---
title: () 연산자 - C# 참조
ms.custom: seodec18
ms.date: 01/15/2019
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 8f7382a49c81b6fd8e104b864ffc2f70db7fe4a6
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758116"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="99257-102">() 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="99257-102">() operator (C# Reference)</span></span>

<span data-ttu-id="99257-103">괄호 `()`는 일반적으로 메서드 또는 대리자 호출이나 캐스트 식에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="99257-103">Parentheses, `()`, are typically used for method or delegate invocation or in cast expressions.</span></span>

<span data-ttu-id="99257-104">또한 괄호를 사용하여 식에서 연산을 계산하는 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99257-104">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="99257-105">자세한 내용은 [연산자](../../programming-guide/statements-expressions-operators/operators.md) 문서의 [괄호 추가](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99257-105">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="99257-106">우선 순위 수준에 따라 정렬된 연산자 목록은 [C# 연산자](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99257-106">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="method-invocation"></a><span data-ttu-id="99257-107">메서드 호출</span><span class="sxs-lookup"><span data-stu-id="99257-107">Method invocation</span></span>

<span data-ttu-id="99257-108">다음 예제는 인수를 사용하거나 사용하지 않고 메서드를 호출하는 방법과 대리자를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99257-108">The following example demonstrates how to invoke a method, with or without arguments, and a delegate:</span></span>

[!code-csharp-interactive[use for invocation](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Invocation)]

<span data-ttu-id="99257-109">[`new`](../keywords/new-operator.md) 연산자를 사용하여 [생성자](../../programming-guide/classes-and-structs/constructors.md)를 호출하는 경우에도 괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99257-109">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

<span data-ttu-id="99257-110">메서드에 대한 자세한 내용은 [메서드](../../programming-guide/classes-and-structs/methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99257-110">For more information about methods, see [Methods](../../programming-guide/classes-and-structs/methods.md).</span></span> <span data-ttu-id="99257-111">대리자에 대한 자세한 내용은 [대리자](../../programming-guide/delegates/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99257-111">For more information about delegates, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="cast-expression"></a><span data-ttu-id="99257-112">캐스트 식</span><span class="sxs-lookup"><span data-stu-id="99257-112">Cast expression</span></span>

<span data-ttu-id="99257-113">`(T)E` 형태의 캐스트 식은 변환 연산자를 호출하여 식 `E`의 값을 `T` 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="99257-113">A cast expression of the form `(T)E` invokes a conversion operator to convert the value of expression `E` to type `T`.</span></span> <span data-ttu-id="99257-114">`E` 형식에서 `T` 형식으로의 명시적 변환이 없는 경우 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="99257-114">If no explicit conversion exists from the type of `E` to type `T`, a compile-time error occurs.</span></span> <span data-ttu-id="99257-115">변환 연산자를 정의하는 방법에 대한 자세한 내용은 [explicit](../keywords/explicit.md) 및 [implicit](../keywords/implicit.md) 키워드 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99257-115">For information about how to define a conversion operator, see the [explicit](../keywords/explicit.md) and [implicit](../keywords/implicit.md) keyword articles.</span></span>

<span data-ttu-id="99257-116">다음 예제는 숫자 형식 간의 형식 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99257-116">The following example demonstrates type conversion between numeric types:</span></span>

[!code-csharp-interactive[use for cast](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Cast)]

<span data-ttu-id="99257-117">숫자 형식 간에 미리 정의된 명시적 변환에 대한 자세한 내용은 [명시적 숫자 변환 표](../keywords/explicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99257-117">For more information about predefined explicit conversions between numeric types, see [Explicit numeric conversions table](../keywords/explicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="99257-118">자세한 내용은 [캐스팅 및 형식 변환](../../programming-guide/types/casting-and-type-conversions.md)과 [변환 연산자](../../programming-guide/statements-expressions-operators/conversion-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99257-118">For more information, see [Casting and type conversions](../../programming-guide/types/casting-and-type-conversions.md) and [Conversion operators](../../programming-guide/statements-expressions-operators/conversion-operators.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="99257-119">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="99257-119">Operator overloadability</span></span>

<span data-ttu-id="99257-120">`()` 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99257-120">The operator `()` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="99257-121">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="99257-121">C# language specification</span></span>

<span data-ttu-id="99257-122">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [호출 식](~/_csharplang/spec/expressions.md#invocation-expressions) 및 [캐스트 식](~/_csharplang/spec/expressions.md#cast-expressions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99257-122">For more information, see the [Invocation expressions](~/_csharplang/spec/expressions.md#invocation-expressions) and [Cast expressions](~/_csharplang/spec/expressions.md#cast-expressions) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="99257-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99257-123">See also</span></span>

- [<span data-ttu-id="99257-124">C# 참조</span><span class="sxs-lookup"><span data-stu-id="99257-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="99257-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="99257-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="99257-126">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="99257-126">C# Operators</span></span>](index.md)
