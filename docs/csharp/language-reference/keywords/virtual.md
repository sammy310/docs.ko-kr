---
description: virtual - C# 참조
title: virtual - C# 참조
ms.date: 07/20/2015
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
ms.openlocfilehash: 67bdfcf27bb108ca85e94ba7fdce208e4cd83b80
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141727"
---
# <a name="virtual-c-reference"></a><span data-ttu-id="8a654-103">virtual(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8a654-103">virtual (C# Reference)</span></span>

<span data-ttu-id="8a654-104">`virtual` 키워드는 메서드, 속성, 인덱서 또는 이벤트 선언을 수정하고 파생 클래스에서 재정의하도록 허용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-104">The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class.</span></span> <span data-ttu-id="8a654-105">예를 들어 이 메서드는 이를 상속하는 모든 클래스에서 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-105">For example, this method can be overridden by any class that inherits it:</span></span>

```csharp
public virtual double Area()
{
    return x * y;
}
```

<span data-ttu-id="8a654-106">가상 멤버의 구현은 파생 클래스의 [재정의 멤버](override.md)로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-106">The implementation of a virtual member can be changed by an [overriding member](override.md) in a derived class.</span></span> <span data-ttu-id="8a654-107">`virtual` 키워드 사용 방법에 대한 자세한 내용은 [Override 및 New 키워드를 사용하여 버전 관리](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) 및 [Override 및 New 키워드를 사용해야 하는 경우](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a654-107">For more information about how to use the `virtual` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="8a654-108">설명</span><span class="sxs-lookup"><span data-stu-id="8a654-108">Remarks</span></span>

<span data-ttu-id="8a654-109">가상 메서드가 호출되면 재정의 멤버에 대해 개체의 런타임 형식이 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-109">When a virtual method is invoked, the run-time type of the object is checked for an overriding member.</span></span> <span data-ttu-id="8a654-110">파생 클래스가 멤버를 재정의하지 않은 경우 가장 많이 파생된 클래스의 재정의 멤버(원래 멤버일 수 있음)가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-110">The overriding member in the most derived class is called, which might be the original member, if no derived class has overridden the member.</span></span>

<span data-ttu-id="8a654-111">기본적으로 메서드는 가상이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-111">By default, methods are non-virtual.</span></span> <span data-ttu-id="8a654-112">가상이 아닌 메서드는 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-112">You cannot override a non-virtual method.</span></span>

<span data-ttu-id="8a654-113">`virtual` 한정자는 `static`, `abstract`, `private` 또는 `override` 한정자와 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-113">You cannot use the `virtual` modifier with the `static`, `abstract`, `private`, or `override` modifiers.</span></span> <span data-ttu-id="8a654-114">다음 예제에서는 가상 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-114">The following example shows a virtual property:</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="8a654-115">선언과 호출 구문에서의 차이점을 제외하면 가상 속성은 가상 메서드처럼 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-115">Virtual properties behave like virtual methods, except for the differences in declaration and invocation syntax.</span></span>

- <span data-ttu-id="8a654-116">정적 속성에서 `virtual` 한정자를 사용하는 것은 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-116">It is an error to use the `virtual` modifier on a static property.</span></span>

- <span data-ttu-id="8a654-117">`override` 한정자를 사용하는 속성 선언을 포함함으로써 상속된 가상 속성을 파생 클래스에서 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-117">A virtual inherited property can be overridden in a derived class by including a property declaration that uses the `override` modifier.</span></span>

## <a name="example"></a><span data-ttu-id="8a654-118">예제</span><span class="sxs-lookup"><span data-stu-id="8a654-118">Example</span></span>

<span data-ttu-id="8a654-119">이 예제에서 `Shape` 클래스는 두 개의 좌표 `x`, `y`와 `Area()` 가상 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-119">In this example, the `Shape` class contains the two coordinates `x`, `y`, and the `Area()` virtual method.</span></span> <span data-ttu-id="8a654-120">`Circle`, `Cylinder` 및 `Sphere`와 같은 서로 다른 도형의 클래스는 `Shape` 클래스를 상속하며, 각 모양에 대해 노출 영역이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-120">Different shape classes such as `Circle`, `Cylinder`, and `Sphere` inherit the `Shape` class, and the surface area is calculated for each figure.</span></span> <span data-ttu-id="8a654-121">각 파생 클래스에는 `Area()`의 자체 재정의 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-121">Each derived class has its own override implementation of `Area()`.</span></span>

<span data-ttu-id="8a654-122">다음 선언에 나와 있는 것처럼 상속된 클래스 `Circle`, `Sphere` 및 `Cylinder`는 모두 기본 클래스를 초기화하는 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-122">Notice that the inherited classes `Circle`, `Sphere`, and `Cylinder` all use constructors that initialize the base class, as shown in the following declaration.</span></span>

```csharp
public Cylinder(double r, double h): base(r, h) {}
```

<span data-ttu-id="8a654-123">다음 프로그램은 메서드와 연결된 개체에 따라 `Area()` 메서드의 적절한 구현을 호출하여 각 그림의 해당 영역을 계산하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8a654-123">The following program calculates and displays the appropriate area for each figure by invoking the appropriate implementation of the `Area()` method, according to the object that is associated with the method.</span></span>

[!code-csharp[csrefKeywordsModifiers#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#23)]

## <a name="c-language-specification"></a><span data-ttu-id="8a654-124">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8a654-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="8a654-125">참조</span><span class="sxs-lookup"><span data-stu-id="8a654-125">See also</span></span>

- [<span data-ttu-id="8a654-126">다형성</span><span class="sxs-lookup"><span data-stu-id="8a654-126">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
- [<span data-ttu-id="8a654-127">abstract</span><span class="sxs-lookup"><span data-stu-id="8a654-127">abstract</span></span>](abstract.md)
- [<span data-ttu-id="8a654-128">override</span><span class="sxs-lookup"><span data-stu-id="8a654-128">override</span></span>](override.md)
- [<span data-ttu-id="8a654-129">new(한정자)</span><span class="sxs-lookup"><span data-stu-id="8a654-129">new (modifier)</span></span>](new-modifier.md)
