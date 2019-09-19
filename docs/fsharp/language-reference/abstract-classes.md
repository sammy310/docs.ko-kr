---
title: 추상 클래스
description: 일부 또는 F# 모든 멤버를 구현 하지 않고 다양 한 개체 형식 집합의 공통 기능을 나타내는 추상 클래스에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: d7fc87178cff7c5c824992c97198b49f87025f00
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082956"
---
# <a name="abstract-classes"></a><span data-ttu-id="8f5f3-103">추상 클래스</span><span class="sxs-lookup"><span data-stu-id="8f5f3-103">Abstract Classes</span></span>

<span data-ttu-id="8f5f3-104">*추상 클래스* 는 파생 클래스에서 구현을 제공할 수 있도록 일부 또는 모든 멤버를 구현 하지 않은 상태로 유지 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-104">*Abstract classes* are classes that leave some or all members unimplemented, so that implementations can be provided by derived classes.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f5f3-105">구문</span><span class="sxs-lookup"><span data-stu-id="8f5f3-105">Syntax</span></span>

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a><span data-ttu-id="8f5f3-106">설명</span><span class="sxs-lookup"><span data-stu-id="8f5f3-106">Remarks</span></span>

<span data-ttu-id="8f5f3-107">개체 지향 프로그래밍에서 추상 클래스는 계층의 기본 클래스로 사용 되며 다양 한 개체 형식 집합의 공통 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-107">In object-oriented programming, an abstract class is used as a base class of a hierarchy, and represents common functionality of a diverse set of object types.</span></span> <span data-ttu-id="8f5f3-108">이름 "abstract"가 암시 하는 것 처럼, 추상 클래스는 문제 도메인의 구체적 엔터티와 직접 일치 하지 않는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-108">As the name "abstract" implies, abstract classes often do not correspond directly onto concrete entities in the problem domain.</span></span> <span data-ttu-id="8f5f3-109">그러나 이러한 항목은 공통 된 다양 한 구체적인 엔터티를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-109">However, they do represent what many different concrete entities have in common.</span></span>

<span data-ttu-id="8f5f3-110">추상 클래스에는 `AbstractClass` 특성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-110">Abstract classes must have the `AbstractClass` attribute.</span></span> <span data-ttu-id="8f5f3-111">구현 및 구현 되지 않은 멤버가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-111">They can have implemented and unimplemented members.</span></span> <span data-ttu-id="8f5f3-112">클래스에 적용 될 때 *추상* 이라는 용어를 사용 하는 것은 다른 .net 언어의 경우와 동일 합니다. 그러나 메서드 (및 속성)에 적용할 때 *추상* 이라는 용어를 사용 하는 것은 다른 .net 언어 F# 에서 사용 하는 것과 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-112">The use of the term *abstract* when applied to a class is the same as in other .NET languages; however, the use of the term *abstract* when applied to methods (and properties) is a little different in F# from its use in other .NET languages.</span></span> <span data-ttu-id="8f5f3-113">에서 F#메서드가 `abstract` 키워드로 표시 되 면이는 멤버에 *가상 디스패치 슬롯*이라는 항목이 해당 형식에 대 한 가상 함수 내부 테이블에 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-113">In F#, when a method is marked with the `abstract` keyword, this indicates that a member has an entry, known as a *virtual dispatch slot*, in the internal table of virtual functions for that type.</span></span> <span data-ttu-id="8f5f3-114">즉, `virtual` 키워드가 F# 언어로 사용 되지 않지만 메서드는 가상입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-114">In other words, the method is virtual, although the `virtual` keyword is not used in the F# language.</span></span> <span data-ttu-id="8f5f3-115">키워드 `abstract` 는 메서드가 구현 되었는지 여부에 관계 없이 가상 메서드에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-115">The keyword `abstract` is used on virtual methods regardless of whether the method is implemented.</span></span> <span data-ttu-id="8f5f3-116">가상 디스패치 슬롯의 선언은 해당 디스패치 슬롯에 대 한 메서드의 정의와 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-116">The declaration of a virtual dispatch slot is separate from the definition of a method for that dispatch slot.</span></span> <span data-ttu-id="8f5f3-117">F# 따라서 다른 .net 언어의 가상 메서드 선언 및 정의에 해당 하는 것은 `default` 키워드 또는 `override` 키워드를 사용 하 여 추상 메서드 선언과 개별 정의의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-117">Therefore, the F# equivalent of a virtual method declaration and definition in another .NET language is a combination of both an abstract method declaration and a separate definition, with either the `default` keyword or the `override` keyword.</span></span> <span data-ttu-id="8f5f3-118">자세한 내용 및 예제는 [메서드](./members/methods.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-118">For more information and examples, see [Methods](./members/methods.md).</span></span>

<span data-ttu-id="8f5f3-119">클래스는 선언 되었지만 정의 되지 않은 추상 메서드가 있는 경우에만 추상으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-119">A class is considered abstract only if there are abstract methods that are declared but not defined.</span></span> <span data-ttu-id="8f5f3-120">따라서 추상 메서드를 포함 하는 클래스는 추상 클래스가 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-120">Therefore, classes that have abstract methods are not necessarily abstract classes.</span></span> <span data-ttu-id="8f5f3-121">클래스에 정의 되지 않은 추상 메서드가 없으면 **AbstractClass** 특성을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-121">Unless a class has undefined abstract methods, do not use the **AbstractClass** attribute.</span></span>

<span data-ttu-id="8f5f3-122">이전 구문에서 *액세스 가능성 한정자* 는, `public` `private` 또는 `internal`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-122">In the previous syntax, *accessibility-modifier* can be `public`, `private` or `internal`.</span></span> <span data-ttu-id="8f5f3-123">자세한 내용은 [액세스 제어](access-control.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-123">For more information, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="8f5f3-124">다른 형식과 마찬가지로 추상 클래스에는 기본 클래스와 하나 이상의 기본 인터페이스가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-124">As with other types, abstract classes can have a base class and one or more base interfaces.</span></span> <span data-ttu-id="8f5f3-125">각 기본 클래스 또는 인터페이스는 `inherit` 키워드와 함께 별도의 줄에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-125">Each base class or interface appears on a separate line together with the `inherit` keyword.</span></span>

<span data-ttu-id="8f5f3-126">추상 클래스의 형식 정의에는 완전히 정의 된 멤버가 포함 될 수 있지만 추상 멤버가 포함 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-126">The type definition of an abstract class can contain fully defined members, but it can also contain abstract members.</span></span> <span data-ttu-id="8f5f3-127">추상 멤버의 구문은 앞의 구문에서 별도로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-127">The syntax for abstract members is shown separately in the previous syntax.</span></span> <span data-ttu-id="8f5f3-128">이 구문에서 멤버의 *형식 시그니처* 는 변환 및 튜플 된 매개 변수에 적절 한 토큰 및/또는 `->` `*` 토큰으로 구분 된 매개 변수 형식 및 반환 형식을 포함 하는 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-128">In this syntax, the *type signature* of a member is a list that contains the parameter types in order and the return types, separated by `->` tokens and/or `*` tokens as appropriate for curried and tupled parameters.</span></span> <span data-ttu-id="8f5f3-129">추상 멤버 형식 시그니처의 구문은 서명 파일에서 사용 되 고 Visual Studio Code 편집기에서 IntelliSense에 의해 표시 되는 구문과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-129">The syntax for abstract member type signatures is the same as that used in signature files and that shown by IntelliSense in the Visual Studio Code Editor.</span></span>

<span data-ttu-id="8f5f3-130">다음 코드에서는 두 개의 비추상 파생 클래스인 Square 및 Circle을 포함 하는 추상 클래스 셰이프를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-130">The following code illustrates an abstract class Shape, which has two non-abstract derived classes, Square and Circle.</span></span> <span data-ttu-id="8f5f3-131">예제에서는 추상 클래스, 메서드 및 속성을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-131">The example shows how to use abstract classes, methods, and properties.</span></span> <span data-ttu-id="8f5f3-132">예제에서 추상 클래스 도형은 구체적 엔터티 원과 사각형의 공통 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-132">In the example, the abstract class Shape represents the common elements of the concrete entities circle and square.</span></span> <span data-ttu-id="8f5f3-133">모든 모양의 일반 기능 (2 차원 좌표계에서)은 Shape 클래스 (표의 위치, 회전 각도 및 영역 및 둘레 속성)로 요약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-133">The common features of all shapes (in a two-dimensional coordinate system) are abstracted out into the Shape class: the position on the grid, an angle of rotation, and the area and perimeter properties.</span></span> <span data-ttu-id="8f5f3-134">이를 재정의할 수 있습니다. 단, 위치를 제외 하 고 개별 셰이프를 변경할 수 없는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-134">These can be overridden, except for position, the behavior of which individual shapes cannot change.</span></span>

<span data-ttu-id="8f5f3-135">순환 클래스에서와 같이 회전 메서드를 재정의할 수 있습니다 .이는 대칭으로 인해 회전 고정입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-135">The rotation method can be overridden, as in the Circle class, which is rotation invariant because of its symmetry.</span></span> <span data-ttu-id="8f5f3-136">따라서 Circle 클래스에서 회전 메서드는 아무 작업도 수행 하지 않는 메서드로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f5f3-136">So in the Circle class, the rotation method is replaced by a method that does nothing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

<span data-ttu-id="8f5f3-137">**출력:**</span><span class="sxs-lookup"><span data-stu-id="8f5f3-137">**Output:**</span></span>

```console
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a><span data-ttu-id="8f5f3-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="8f5f3-138">See also</span></span>

- [<span data-ttu-id="8f5f3-139">클래스</span><span class="sxs-lookup"><span data-stu-id="8f5f3-139">Classes</span></span>](classes.md)
- [<span data-ttu-id="8f5f3-140">멤버</span><span class="sxs-lookup"><span data-stu-id="8f5f3-140">Members</span></span>](./members/index.md)
- [<span data-ttu-id="8f5f3-141">메서드</span><span class="sxs-lookup"><span data-stu-id="8f5f3-141">Methods</span></span>](./members/methods.md)
- [<span data-ttu-id="8f5f3-142">Properties</span><span class="sxs-lookup"><span data-stu-id="8f5f3-142">Properties</span></span>](./members/Properties.md)
