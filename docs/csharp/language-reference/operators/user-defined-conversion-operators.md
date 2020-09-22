---
title: 사용자 정의 전환 연산자 - C# 참조
description: C#에서 사용자 지정 암시적 및 명시적 형식 변환을 정의하는 방법을 알아봅니다.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
- explicit
- implicit
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: ab977408ed891bd7c996ce3644b22ea984425664
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536381"
---
# <a name="user-defined-conversion-operators-c-reference"></a><span data-ttu-id="a7a7c-103">사용자 정의 전환 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a7a7c-103">User-defined conversion operators (C# reference)</span></span>

<span data-ttu-id="a7a7c-104">사용자 정의 형식은 다른 형식에서 또는 다른 형식으로 사용자 지정 암시적 또는 명시적 변환을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-104">A user-defined type can define a custom implicit or explicit conversion from or to another type.</span></span>

<span data-ttu-id="a7a7c-105">암시적 변환은 특별한 구문을 호출할 필요가 없으며, 할당과 메서드 호출과 같은 다양한 상황에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-105">Implicit conversions don't require special syntax to be invoked and can occur in a variety of situations, for example, in assignments and methods invocations.</span></span> <span data-ttu-id="a7a7c-106">미리 정의된 C# 암시적 변환은 항상 성공하며 예외를 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-106">Predefined C# implicit conversions always succeed and never throw an exception.</span></span> <span data-ttu-id="a7a7c-107">사용자 정의 암시적 변화도 이러한 방식으로 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-107">User-defined implicit conversions should behave in that way as well.</span></span> <span data-ttu-id="a7a7c-108">사용자 지정 변환이 예외를 throw하거나 정보가 손실될 수 있는 경우 이를 명시적 변환으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-108">If a custom conversion can throw an exception or lose information, define it as an explicit conversion.</span></span>

<span data-ttu-id="a7a7c-109">사용자 정의 변환은 [is](type-testing-and-cast.md#is-operator) 및 [as](type-testing-and-cast.md#as-operator) 연산자로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-109">User-defined conversions are not considered by the [is](type-testing-and-cast.md#is-operator) and [as](type-testing-and-cast.md#as-operator) operators.</span></span> <span data-ttu-id="a7a7c-110">[캐스트 식](type-testing-and-cast.md#cast-expression)을 사용하여 사용자 정의 명시적 변환을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-110">Use a [cast expression](type-testing-and-cast.md#cast-expression) to invoke a user-defined explicit conversion.</span></span>

<span data-ttu-id="a7a7c-111">`operator` 및 `implicit` 또는 `explicit` 키워드를 사용하여 각각 암시적 또는 명시적 변환을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-111">Use the `operator` and `implicit` or `explicit` keywords to define an implicit or explicit conversion, respectively.</span></span> <span data-ttu-id="a7a7c-112">변환을 정의하는 유형은 해당 변환의 소스 유형 또는 대상 유형이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-112">The type that defines a conversion must be either a source type or a target type of that conversion.</span></span> <span data-ttu-id="a7a7c-113">두 형식 중 하나에서 두 개의 사용자 정의 형식 간의 변환을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-113">A conversion between two user-defined types can be defined in either of the two types.</span></span>

<span data-ttu-id="a7a7c-114">다음 예제에서는 암시적 및 명시적 변환을 정의하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-114">The following example demonstrates how to define an implicit and explicit conversion:</span></span>

[!code-csharp[implicit an explicit conversions](snippets/shared/UserDefinedConversions.cs)]

<span data-ttu-id="a7a7c-115">또한 `operator` 키워드를 사용하여 미리 정의된 C# 연산자를 오버로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-115">You also use the `operator` keyword to overload a predefined C# operator.</span></span> <span data-ttu-id="a7a7c-116">자세한 내용은 [연산자 오버로드](operator-overloading.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-116">For more information, see [Operator overloading](operator-overloading.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a7a7c-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="a7a7c-117">C# language specification</span></span>

<span data-ttu-id="a7a7c-118">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7a7c-118">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="a7a7c-119">변환 연산자</span><span class="sxs-lookup"><span data-stu-id="a7a7c-119">Conversion operators</span></span>](~/_csharplang/spec/classes.md#conversion-operators)
- [<span data-ttu-id="a7a7c-120">사용자 정의 변환</span><span class="sxs-lookup"><span data-stu-id="a7a7c-120">User-defined conversions</span></span>](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [<span data-ttu-id="a7a7c-121">암시적 변환</span><span class="sxs-lookup"><span data-stu-id="a7a7c-121">Implicit conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-conversions)
- [<span data-ttu-id="a7a7c-122">명시적 변환</span><span class="sxs-lookup"><span data-stu-id="a7a7c-122">Explicit conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a><span data-ttu-id="a7a7c-123">참조</span><span class="sxs-lookup"><span data-stu-id="a7a7c-123">See also</span></span>

- [<span data-ttu-id="a7a7c-124">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a7a7c-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a7a7c-125">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="a7a7c-125">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="a7a7c-126">연산자 오버로드</span><span class="sxs-lookup"><span data-stu-id="a7a7c-126">Operator overloading</span></span>](operator-overloading.md)
- [<span data-ttu-id="a7a7c-127">형식 테스트 및 캐스트 연산자</span><span class="sxs-lookup"><span data-stu-id="a7a7c-127">Type-testing and cast operators</span></span>](type-testing-and-cast.md)
- [<span data-ttu-id="a7a7c-128">캐스팅 및 형식 변환</span><span class="sxs-lookup"><span data-stu-id="a7a7c-128">Casting and type conversion</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="a7a7c-129">디자인 지침 - 변환 연산자</span><span class="sxs-lookup"><span data-stu-id="a7a7c-129">Design guidelines - Conversion operators</span></span>](../../../standard/design-guidelines/operator-overloads.md#conversion-operators)
- <span data-ttu-id="a7a7c-130">[Chained user-defined explicit conversions in C#](/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c)(C#의 연결된 사용자 정의 명시적 변환)</span><span class="sxs-lookup"><span data-stu-id="a7a7c-130">[Chained user-defined explicit conversions in C#](/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c)</span></span>
