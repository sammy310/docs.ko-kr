---
title: 추상 클래스
description: 에 대해 알아봅니다 F# 추상 클래스 구현 되지 않은 일부 또는 모든 멤버를 유지 하는 및 개체 유형의 다양 한 집합의 공통 기능을 나타냅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 8251d481c9056d40a0b13ae3c89353406986c116
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645534"
---
# <a name="abstract-classes"></a><span data-ttu-id="a2dfd-103">추상 클래스</span><span class="sxs-lookup"><span data-stu-id="a2dfd-103">Abstract Classes</span></span>

<span data-ttu-id="a2dfd-104">*추상 클래스* 는 파생된 클래스에서 구현할 수 있도록 일부 또는 모든 멤버를 구현 되지 않은 채로 두는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-104">*Abstract classes* are classes that leave some or all members unimplemented, so that implementations can be provided by derived classes.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2dfd-105">구문</span><span class="sxs-lookup"><span data-stu-id="a2dfd-105">Syntax</span></span>

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a><span data-ttu-id="a2dfd-106">설명</span><span class="sxs-lookup"><span data-stu-id="a2dfd-106">Remarks</span></span>

<span data-ttu-id="a2dfd-107">개체 지향 프로그래밍에서 추상 클래스 계층의 기본 클래스로 사용 되 고 다양 한 개체 유형 집합의 공통 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-107">In object-oriented programming, an abstract class is used as a base class of a hierarchy, and represents common functionality of a diverse set of object types.</span></span> <span data-ttu-id="a2dfd-108">"Abstract" 이름에서 알 수 있듯이 추상 클래스 종종 맞지 않는 문제 도메인의 구체적 엔터티를 직접.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-108">As the name "abstract" implies, abstract classes often do not correspond directly onto concrete entities in the problem domain.</span></span> <span data-ttu-id="a2dfd-109">그러나 여러 다른 콘크리트 엔터티의 공통점 나타냅니다지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-109">However, they do represent what many different concrete entities have in common.</span></span>

<span data-ttu-id="a2dfd-110">추상 클래스에 있어야 합니다 `AbstractClass` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-110">Abstract classes must have the `AbstractClass` attribute.</span></span> <span data-ttu-id="a2dfd-111">구현 되 고 멤버를 구현 되지 않았으며 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-111">They can have implemented and unimplemented members.</span></span> <span data-ttu-id="a2dfd-112">하지만 이라는 용어를 사용 *추상* 적용할 때 클래스는 다른.NET 언어와 동일 이라는 용어를 사용 *추상* 메서드 (및 속성)에 적용 하는 경우에 약간 다릅니다은 F# 다른.NET 언어에서 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-112">The use of the term *abstract* when applied to a class is the same as in other .NET languages; however, the use of the term *abstract* when applied to methods (and properties) is a little different in F# from its use in other .NET languages.</span></span> <span data-ttu-id="a2dfd-113">F#메서드를 사용 하 여 표시할지 하는 경우를 `abstract` 키워드를이 의미 멤버인 이라고 하는 항목을는 *가상 디스패치와 슬롯*, 가상 함수는 형식에 대 한 내부 테이블에 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-113">In F#, when a method is marked with the `abstract` keyword, this indicates that a member has an entry, known as a *virtual dispatch slot*, in the internal table of virtual functions for that type.</span></span> <span data-ttu-id="a2dfd-114">즉, 메서드는 가상 있지만 합니다 `virtual` 키워드에 사용 되지 않습니다는 F# 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-114">In other words, the method is virtual, although the `virtual` keyword is not used in the F# language.</span></span> <span data-ttu-id="a2dfd-115">키워드 `abstract` 메서드를 구현 하는 여부에 관계 없이 가상 메서드에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-115">The keyword `abstract` is used on virtual methods regardless of whether the method is implemented.</span></span> <span data-ttu-id="a2dfd-116">가상 디스패치와 슬롯의 선언은 해당 디스패치 슬롯에 대 한 메서드의 정의에서 별도입니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-116">The declaration of a virtual dispatch slot is separate from the definition of a method for that dispatch slot.</span></span> <span data-ttu-id="a2dfd-117">따라서는 F# 가상 메서드 선언은 다른.NET 언어에서 정의 해당 하는 추상 메서드 선언 및 사용 하 여 별도 정의 모두의 조합 합니다 `default` 키워드와 `override` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-117">Therefore, the F# equivalent of a virtual method declaration and definition in another .NET language is a combination of both an abstract method declaration and a separate definition, with either the `default` keyword or the `override` keyword.</span></span> <span data-ttu-id="a2dfd-118">자세한 내용 및 예제를 참조 하세요 [메서드](members/methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-118">For more information and examples, see [Methods](members/methods.md).</span></span>

<span data-ttu-id="a2dfd-119">클래스는 추상 선언 되지만 정의 되지 않은 추상 메서드가 필요한 경우에 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-119">A class is considered abstract only if there are abstract methods that are declared but not defined.</span></span> <span data-ttu-id="a2dfd-120">따라서 추상 메서드가 있는 클래스는 반드시 추상 클래스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-120">Therefore, classes that have abstract methods are not necessarily abstract classes.</span></span> <span data-ttu-id="a2dfd-121">클래스의 추상 메서드를 정의 되지 않은 경우가 아니면 사용 하지 않는 합니다 **AbstractClass** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-121">Unless a class has undefined abstract methods, do not use the **AbstractClass** attribute.</span></span>

<span data-ttu-id="a2dfd-122">이전 구문에서 *접근성 한정자* 될 수 있습니다 `public`를 `private` 또는 `internal`합니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-122">In the previous syntax, *accessibility-modifier* can be `public`, `private` or `internal`.</span></span> <span data-ttu-id="a2dfd-123">자세한 내용은 [액세스 제어](access-control.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-123">For more information, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="a2dfd-124">다른 형식과 마찬가지로 추상 클래스는 기본 클래스와 하나 이상의 기본 인터페이스를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-124">As with other types, abstract classes can have a base class and one or more base interfaces.</span></span> <span data-ttu-id="a2dfd-125">각 기본 클래스 또는 인터페이스와 함께 별도 줄에 표시 되는 `inherit` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-125">Each base class or interface appears on a separate line together with the `inherit` keyword.</span></span>

<span data-ttu-id="a2dfd-126">추상 클래스의 형식 정의는 완벽 하 게 정의 된 멤버를 포함할 수 있습니다 하지만 추상 멤버를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-126">The type definition of an abstract class can contain fully defined members, but it can also contain abstract members.</span></span> <span data-ttu-id="a2dfd-127">추상 멤버를 포함 하는 구문은 이전 구문에서 별도로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-127">The syntax for abstract members is shown separately in the previous syntax.</span></span> <span data-ttu-id="a2dfd-128">이 구문에서은 *형식 시그니처* 멤버의 목록을 포함 하는 순서는 반환 형식에는 매개 변수 형식으로 구분 됩니다 `->` 토큰 및/또는 `*` 변환에 대 한 적절 하 게 토큰 및 튜플 되었을 수 있는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-128">In this syntax, the *type signature* of a member is a list that contains the parameter types in order and the return types, separated by `->` tokens and/or `*` tokens as appropriate for curried and tupled parameters.</span></span> <span data-ttu-id="a2dfd-129">추상 멤버 형식 서명에 대 한 구문을 서명 파일에서 사용 하 고 Visual Studio 코드 편집기에서 IntelliSense에서 표시와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-129">The syntax for abstract member type signatures is the same as that used in signature files and that shown by IntelliSense in the Visual Studio Code Editor.</span></span>

<span data-ttu-id="a2dfd-130">다음 코드에는 추상 클래스를 두 비추상 파생된 클래스, 사각형, 원에 있는 셰이프를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-130">The following code illustrates an abstract class Shape, which has two non-abstract derived classes, Square and Circle.</span></span> <span data-ttu-id="a2dfd-131">추상 클래스, 메서드 및 속성을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-131">The example shows how to use abstract classes, methods, and properties.</span></span> <span data-ttu-id="a2dfd-132">예제에서는 추상 클래스 모양 구체적 엔터티 원과 사각형의 공통 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-132">In the example, the abstract class Shape represents the common elements of the concrete entities circle and square.</span></span> <span data-ttu-id="a2dfd-133">셰이프 (2 차원 좌표 시스템)의 일반적인 기능 셰이프 클래스로 추상화 됩니다: 면적 및 둘레 속성 표, 회전 각도에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-133">The common features of all shapes (in a two-dimensional coordinate system) are abstracted out into the Shape class: the position on the grid, an angle of rotation, and the area and perimeter properties.</span></span> <span data-ttu-id="a2dfd-134">이 재정의할 수 있습니다 위치를 변경할 수 없습니다 개별 셰이프는 동작을 제외 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-134">These can be overridden, except for position, the behavior of which individual shapes cannot change.</span></span>

<span data-ttu-id="a2dfd-135">대칭성 회전 고정이 Circle 클래스에서와 같이 회전 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-135">The rotation method can be overridden, as in the Circle class, which is rotation invariant because of its symmetry.</span></span> <span data-ttu-id="a2dfd-136">따라서 Circle 클래스에서 회전 메서드는 아무 작업도 수행 하지 하는 메서드에서 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2dfd-136">So in the Circle class, the rotation method is replaced by a method that does nothing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

<span data-ttu-id="a2dfd-137">**출력:**</span><span class="sxs-lookup"><span data-stu-id="a2dfd-137">**Output:**</span></span>

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a><span data-ttu-id="a2dfd-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="a2dfd-138">See also</span></span>

- [<span data-ttu-id="a2dfd-139">클래스</span><span class="sxs-lookup"><span data-stu-id="a2dfd-139">Classes</span></span>](classes.md)
- [<span data-ttu-id="a2dfd-140">멤버</span><span class="sxs-lookup"><span data-stu-id="a2dfd-140">Members</span></span>](members/index.md)
- [<span data-ttu-id="a2dfd-141">메서드</span><span class="sxs-lookup"><span data-stu-id="a2dfd-141">Methods</span></span>](members/methods.md)
- [<span data-ttu-id="a2dfd-142">속성</span><span class="sxs-lookup"><span data-stu-id="a2dfd-142">Properties</span></span>](members/Properties.md)
