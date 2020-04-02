---
title: 기본값 식 - C# 참조
description: 기본값 식을 사용하여 형식의 기본값을 가져옵니다.
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 2adfd8d24066e9dad50c3c18407d3ade71b4b68e
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507180"
---
# <a name="default-value-expressions-c-reference"></a><span data-ttu-id="9c203-103">기본값 식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9c203-103">default value expressions (C# reference)</span></span>

<span data-ttu-id="9c203-104">기본값 식은 형식의 [기본값](../builtin-types/default-values.md)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c203-104">A default value expression produces the [default value](../builtin-types/default-values.md) of a type.</span></span> <span data-ttu-id="9c203-105">기본값 식에는 두 가지가 있습니다. [기본 연산자](#default-operator) 호출 및 [기본 리터럴](#default-literal).</span><span class="sxs-lookup"><span data-stu-id="9c203-105">There are two kinds of default value expressions: the [default operator](#default-operator) call and a [default literal](#default-literal).</span></span>

<span data-ttu-id="9c203-106">또한 `default` 키워드를 [`switch` 문](../keywords/switch.md) 내의 기본 사례 레이블로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c203-106">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-operator"></a><span data-ttu-id="9c203-107">default 연산자</span><span class="sxs-lookup"><span data-stu-id="9c203-107">default operator</span></span>

<span data-ttu-id="9c203-108">`default` 연산자의 인수는 다음 예제와 같이 형식 또는 형식 매개 변수의 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c203-108">The argument to the `default` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[default of T](snippets/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a><span data-ttu-id="9c203-109">기본 리터럴</span><span class="sxs-lookup"><span data-stu-id="9c203-109">default literal</span></span>

<span data-ttu-id="9c203-110">C# 7.1부터 `default` 리터럴을 사용하여 컴파일러가 식 형식을 유추할 수 있는 경우 형식의 기본값을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c203-110">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="9c203-111">`default` 리터럴 식은 `T`가 추론된 형식은 `default(T)` 식과 동일한 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c203-111">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="9c203-112">다음과 같은 경우에 `default` 리터럴 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c203-112">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="9c203-113">변수의 할당 또는 초기화에서</span><span class="sxs-lookup"><span data-stu-id="9c203-113">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="9c203-114">[선택적 메서드 매개 변수](../../methods.md#optional-parameters-and-arguments)에 대한 기본값 선언에서</span><span class="sxs-lookup"><span data-stu-id="9c203-114">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="9c203-115">인수 값을 제공하기 위한 메서드 호출에서</span><span class="sxs-lookup"><span data-stu-id="9c203-115">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="9c203-116">[`return` 문](../keywords/return.md)에서 또는 [식 본문 멤버](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)의 식으로</span><span class="sxs-lookup"><span data-stu-id="9c203-116">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="9c203-117">다음 예제에서는 `default` 리터의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9c203-117">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](snippets/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="9c203-118">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="9c203-118">C# language specification</span></span>

<span data-ttu-id="9c203-119">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [기본값 식](~/_csharplang/spec/expressions.md#default-value-expressions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c203-119">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="9c203-120">`default` 리터럴에 대한 자세한 내용은 [기능 제안 노트](~/_csharplang/proposals/csharp-7.1/target-typed-default.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c203-120">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9c203-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c203-121">See also</span></span>

- [<span data-ttu-id="9c203-122">C# 참조</span><span class="sxs-lookup"><span data-stu-id="9c203-122">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9c203-123">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="9c203-123">C# operators</span></span>](index.md)
- [<span data-ttu-id="9c203-124">C# 형식의 기본값</span><span class="sxs-lookup"><span data-stu-id="9c203-124">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="9c203-125">.NET의 제네릭</span><span class="sxs-lookup"><span data-stu-id="9c203-125">Generics in .NET</span></span>](../../../standard/generics/index.md)
