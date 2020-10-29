---
description: override 한정자 - C# 참조
title: override 한정자 - C# 참조
ms.date: 10/22/2020
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 618200183348e68a4600adb9592a635f61f6a875
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434875"
---
# <a name="override-c-reference"></a><span data-ttu-id="50a4e-103">override(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="50a4e-103">override (C# reference)</span></span>

<span data-ttu-id="50a4e-104">`override` 한정자는 상속된 메서드, 속성, 인덱서 또는 이벤트의 추상 또는 가상 구현을 확장하거나 수정하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-104">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

<span data-ttu-id="50a4e-105">다음 예제에서 `Square` 클래스는 `GetArea`가 추상 `Shape` 클래스에서 상속되기 때문에 `GetArea`의 재정의된 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-105">In the following example, the `Square` class must provide an overridden implementation of `GetArea` because `GetArea` is inherited from the abstract `Shape` class:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="50a4e-106">`override` 메서드는 기본 클래스에서 상속된 멤버의 새 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-106">An `override` method provides a new implementation of the method inherited from a base class.</span></span> <span data-ttu-id="50a4e-107">`override` 선언에서 재정의된 메서드를 재정의된 기본 메서드라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="50a4e-108">`override` 메서드에는 재정의된 기본 메서드와 동일한 시그니처가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-108">An `override` method must have the same signature as the overridden base method.</span></span> <span data-ttu-id="50a4e-109">C# 9.0부터 `override` 메서드는 공변 반환 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-109">Beginning with C# 9.0, `override` methods support covariant return types.</span></span> <span data-ttu-id="50a4e-110">특히 `override` 메서드의 반환 형식은 해당하는 기본 메서드의 반환 형식에서 파생될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-110">In particular, the return type of an `override` method can derive from the return type of the corresponding base method.</span></span> <span data-ttu-id="50a4e-111">C# 8.0 이전 버전에서는 `override` 메서드의 반환 형식과 재정의된 기본 메서드가 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-111">In C# 8.0 and earlier, the return types of an `override` method and the overridden base method must be the same.</span></span>

<span data-ttu-id="50a4e-112">비가상 또는 정적 메서드는 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-112">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="50a4e-113">재정의된 기본 메서드는 `virtual`, `abstract` 또는 `override`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-113">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="50a4e-114">`override` 선언에서는 `virtual` 메서드의 액세스 가능성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-114">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="50a4e-115">`override` 메서드 및 `virtual` 메서드 둘 다에 동일한 [액세스 수준 한정자](access-modifiers.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-115">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="50a4e-116">`new`, `static` 또는 `virtual` 한정자를 사용하여 `override` 메서드를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-116">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="50a4e-117">재정의 속성 선언은 상속된 속성과 동일한 액세스 한정자, 형식 및 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-117">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property.</span></span> <span data-ttu-id="50a4e-118">C# 9.0부터 읽기 전용 재정의 속성은 공변 반환 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-118">Beginning with C# 9.0, read-only overriding properties support covariant return types.</span></span> <span data-ttu-id="50a4e-119">재정의된 속성은 `virtual`, `abstract` 또는 `override`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-119">The overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="50a4e-120">`override` 키워드 사용 방법에 대한 자세한 내용은 [Override 및 New 키워드를 사용하여 버전 관리](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) 및 [Override 및 New 키워드를 사용해야 하는 경우](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a4e-120">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span> <span data-ttu-id="50a4e-121">상속에 대한 자세한 내용은 [상속](../../programming-guide/classes-and-structs/inheritance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a4e-121">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

## <a name="example"></a><span data-ttu-id="50a4e-122">예제</span><span class="sxs-lookup"><span data-stu-id="50a4e-122">Example</span></span>

<span data-ttu-id="50a4e-123">이 예제에서는 `Employee`라는 기본 클래스와 `SalesEmployee`라는 파생 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-123">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="50a4e-124">`SalesEmployee` 클래스에는 추가 필드 `salesbonus`가 포함되어 있고, 이를 고려하기 위해 `CalculatePay` 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="50a4e-124">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="50a4e-125">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="50a4e-125">C# language specification</span></span>

<span data-ttu-id="50a4e-126">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [재정의 메서드](~/_csharplang/spec/classes.md#override-methods) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a4e-126">For more information, see the [Override methods](~/_csharplang/spec/classes.md#override-methods) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="50a4e-127">공변 반환 형식에 대한 자세한 내용은 [기능 제안 노트](~/_csharplang/proposals/csharp-9.0/covariant-returns.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a4e-127">For more information about covariant return types, see the [feature proposal note](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="50a4e-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50a4e-128">See also</span></span>

- [<span data-ttu-id="50a4e-129">C# 참조</span><span class="sxs-lookup"><span data-stu-id="50a4e-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="50a4e-130">상속</span><span class="sxs-lookup"><span data-stu-id="50a4e-130">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="50a4e-131">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="50a4e-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="50a4e-132">한정자</span><span class="sxs-lookup"><span data-stu-id="50a4e-132">Modifiers</span></span>](index.md)
- [<span data-ttu-id="50a4e-133">abstract</span><span class="sxs-lookup"><span data-stu-id="50a4e-133">abstract</span></span>](abstract.md)
- [<span data-ttu-id="50a4e-134">virtual</span><span class="sxs-lookup"><span data-stu-id="50a4e-134">virtual</span></span>](virtual.md)
- [<span data-ttu-id="50a4e-135">new(한정자)</span><span class="sxs-lookup"><span data-stu-id="50a4e-135">new (modifier)</span></span>](new-modifier.md)
- [<span data-ttu-id="50a4e-136">다형성</span><span class="sxs-lookup"><span data-stu-id="50a4e-136">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
