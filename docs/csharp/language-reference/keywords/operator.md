---
title: 연산자 키워드 - C# 참조
ms.custom: seodec18
description: 기본 제공 C# 연산자를 오버로드하는 방법 알아보기
ms.date: 08/27/2018
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: 47ce91c343092ac2f7555c1edf3418527776e131
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754765"
---
# <a name="operator-c-reference"></a><span data-ttu-id="91419-103">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="91419-103">operator (C# Reference)</span></span>

<span data-ttu-id="91419-104">`operator` 키워드를 사용하여 기본 제공 연산자를 오버로드하거나 클래스 또는 구조체 선언에서 사용자 정의 변환을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91419-104">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

<span data-ttu-id="91419-105">사용자 지정 클래스 또는 구조체에서 연산자를 오버로드하려면 해당 형식으로 연산자 선언문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91419-105">To overload an operator on a custom class or struct, you create an operator declaration in the corresponding type.</span></span> <span data-ttu-id="91419-106">기본 제공 C# 연산자를 오버로드하는 연산자 선언은 다음 규칙을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91419-106">The operator declaration that overloads a built-in C# operator must satisfy the following rules:</span></span>

- <span data-ttu-id="91419-107">`public` 및 `static` 한정자를 모두 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="91419-107">It includes both a `public` and a `static` modifier.</span></span>
- <span data-ttu-id="91419-108">여기에는 `operator X`가 포함되며, 여기서 `X`는 오버로드되는 연산자의 이름 또는 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="91419-108">It includes `operator X` where `X` is the name or symbol of the operator being overloaded.</span></span>
- <span data-ttu-id="91419-109">단항 연산자는 매개 변수가 하나이고, 이항 연산자는 매개 변수가 두 개입니다.</span><span class="sxs-lookup"><span data-stu-id="91419-109">Unary operators have one parameter, and binary operators have two parameters.</span></span> <span data-ttu-id="91419-110">각각의 경우 적어도 하나의 매개 변수는 연산자를 선언하는 클래스나 구조체와 동일한 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91419-110">In each case, at least one parameter must be the same type as the class or struct that declares the operator.</span></span>

<span data-ttu-id="91419-111">변환 연산자를 정의하는 방법에 대한 자세한 내용은 [explicit](explicit.md) 및 [implicit](implicit.md) 키워드 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91419-111">For information about how to define conversion operators, see the [explicit](explicit.md) and [implicit](implicit.md) keyword articles.</span></span>

<span data-ttu-id="91419-112">오버로드할 수 있는 C# 연산자에 대한 개요는 [오버로드할 수 있는 연산자](../../programming-guide/statements-expressions-operators/overloadable-operators.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91419-112">For an overview of the C# operators that can be overloaded, see the [Overloadable operators](../../programming-guide/statements-expressions-operators/overloadable-operators.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="91419-113">예제</span><span class="sxs-lookup"><span data-stu-id="91419-113">Example</span></span>

<span data-ttu-id="91419-114">다음 예제에서는 소수를 나타내는 `Fraction` 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="91419-114">The following example defines a `Fraction` type that represents fractional numbers.</span></span> <span data-ttu-id="91419-115">`+` 및 `*` 연산자를 오버로드하여 소수 더하기 및 곱하기를 수행하고 `Fraction` 형식을 `double` 형식으로 변환하는 변환 연산자도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91419-115">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="91419-116">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="91419-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="91419-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91419-117">See also</span></span>

- [<span data-ttu-id="91419-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="91419-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="91419-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="91419-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="91419-120">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="91419-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="91419-121">implicit</span><span class="sxs-lookup"><span data-stu-id="91419-121">implicit</span></span>](implicit.md)
- [<span data-ttu-id="91419-122">explicit</span><span class="sxs-lookup"><span data-stu-id="91419-122">explicit</span></span>](explicit.md)
- [<span data-ttu-id="91419-123">오버로드할 수 있는 연산자</span><span class="sxs-lookup"><span data-stu-id="91419-123">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="91419-124">방법: 구조체 간의 사용자 정의 변환 구현</span><span class="sxs-lookup"><span data-stu-id="91419-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
