---
description: const 키워드 - C# 참조
title: const 키워드 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: 312725c3a231f0ca766d5b99bf7d9308ddd634c4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142091"
---
# <a name="const-c-reference"></a><span data-ttu-id="67ead-103">const(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="67ead-103">const (C# Reference)</span></span>

<span data-ttu-id="67ead-104">상수 필드 또는 지역 상수를 선언할 때는 `const` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-104">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="67ead-105">상수 필드 및 지역 상수는 변수가 아니며 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-105">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="67ead-106">상수는 숫자, 부울 값, 문자열 또는 null 참조일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-106">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="67ead-107">언제든지 변경될 수 있는 정보를 나타낼 때는 상수를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="67ead-107">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="67ead-108">예를 들어, 상수 필드를 사용하여 서비스의 가격, 제품 버전 번호 또는 회사의 브랜드 이름을 저장하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="67ead-108">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="67ead-109">이러한 값은 시간이 지남에 따라 변경될 수 있으며, 컴파일러는 상수를 전파하므로 변경 내용을 보기 위해서는 라이브러리를 사용하여 컴파일된 다른 코드를 다시 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-109">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="67ead-110">[readonly](./readonly.md) 키워드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67ead-110">See also the [readonly](./readonly.md) keyword.</span></span> <span data-ttu-id="67ead-111">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-111">For example:</span></span>

```csharp
const int X = 0;
public const double GravitationalConstant = 6.673e-11;
private const string ProductName = "Visual C#";
```

## <a name="remarks"></a><span data-ttu-id="67ead-112">설명</span><span class="sxs-lookup"><span data-stu-id="67ead-112">Remarks</span></span>

<span data-ttu-id="67ead-113">상수 선언 형식은 선언에서 제공하는 멤버의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-113">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="67ead-114">지역 상수 또는 상수 필드의 이니셜라이저는 대상 형식으로 암시적으로 변환될 수 있는 상수 식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-114">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>

<span data-ttu-id="67ead-115">상수 식은 컴파일 시간에 완전히 계산될 수 있는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-115">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="67ead-116">따라서 참조 형식의 상수에 대해 가능한 값은 `string` 및 null 참조뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-116">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>

<span data-ttu-id="67ead-117">상수 선언에서는 다음과 같이 여러 상수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-117">The constant declaration can declare multiple constants, such as:</span></span>

```csharp
public const double X = 1.0, Y = 2.0, Z = 3.0;
```

<span data-ttu-id="67ead-118">`static` 한정자는 상수 선언에는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-118">The `static` modifier is not allowed in a constant declaration.</span></span>

<span data-ttu-id="67ead-119">상수는 다음과 같이 상수 식에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-119">A constant can participate in a constant expression, as follows:</span></span>

```csharp
public const int C1 = 5;
public const int C2 = C1 + 100;
```

> [!NOTE]
> <span data-ttu-id="67ead-120">[readonly](./readonly.md) 키워드는 `const` 키워드와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-120">The [readonly](./readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="67ead-121">`const` 필드는 필드 선언에서만 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-121">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="67ead-122">`readonly` 필드는 선언이나 생성자에서 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-122">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="67ead-123">따라서 `readonly` 필드는 사용된 생성자에 따라 다른 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-123">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="67ead-124">또한 `const` 필드가 컴파일 시간 상수라고 하더라도 `readonly` 필드는 다음 줄에서와 같이 런타임 상수에 사용될 수 있습니다. `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="67ead-124">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>

## <a name="example"></a><span data-ttu-id="67ead-125">예제</span><span class="sxs-lookup"><span data-stu-id="67ead-125">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a><span data-ttu-id="67ead-126">예제</span><span class="sxs-lookup"><span data-stu-id="67ead-126">Example</span></span>

<span data-ttu-id="67ead-127">이 예제에서는 상수를 지역 변수로 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="67ead-127">This example demonstrates how to use constants as local variables.</span></span>

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="67ead-128">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="67ead-128">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="67ead-129">참조</span><span class="sxs-lookup"><span data-stu-id="67ead-129">See also</span></span>

- [<span data-ttu-id="67ead-130">C# 참조</span><span class="sxs-lookup"><span data-stu-id="67ead-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="67ead-131">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="67ead-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="67ead-132">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="67ead-132">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="67ead-133">한정자</span><span class="sxs-lookup"><span data-stu-id="67ead-133">Modifiers</span></span>](index.md)
- [<span data-ttu-id="67ead-134">readonly</span><span class="sxs-lookup"><span data-stu-id="67ead-134">readonly</span></span>](./readonly.md)
