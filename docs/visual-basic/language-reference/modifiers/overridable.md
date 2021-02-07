---
description: '자세한 정보: 재정의 가능 (Visual Basic)'
title: Overrides
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: acbbd715113c836a3fb7f8a88bf74307c38ac682
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730501"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="6c8d2-103">Overridable(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c8d2-103">Overridable (Visual Basic)</span></span>

<span data-ttu-id="6c8d2-104">속성 또는 프로시저가 파생 클래스의 이름이 같은 속성 또는 프로시저로 재정의 될 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-104">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c8d2-105">설명</span><span class="sxs-lookup"><span data-stu-id="6c8d2-105">Remarks</span></span>  

 <span data-ttu-id="6c8d2-106">`Overridable`한정자를 사용 하면 클래스의 속성 또는 메서드가 파생 클래스에서 재정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-106">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="6c8d2-107">[NotOverridable](notoverridable.md) 한정자는 속성 또는 메서드가 파생 클래스에서 재정의 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-107">The [NotOverridable](notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="6c8d2-108">자세한 내용은 [상속 기본 사항](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-108">For more information, see [Inheritance Basics](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="6c8d2-109">`Overridable`또는 `NotOverridable` 한정자가 지정 되지 않은 경우 기본 설정은 속성이 나 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-109">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="6c8d2-110">속성 또는 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정은입니다 `Overridable` . 그렇지 않으면 `NotOverridable` 입니다.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-110">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="6c8d2-111">을 숨기 나 재정의 하 여 상속 된 요소를 다시 정의할 수 있지만 두 방법 간에는 상당한 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-111">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="6c8d2-112">자세한 내용은 [Visual Basic에서 숨기기](../../programming-guide/language-features/declared-elements/shadowing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-112">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="6c8d2-113">재정의할 수 있는 요소를 *가상* 요소 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-113">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="6c8d2-114">재정의할 수는 있지만 일 필요가 없는 경우에는 *구체적* 요소가 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-114">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="6c8d2-115">`Overridable`속성 또는 프로시저 선언 문에서만를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-115">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="6c8d2-116">결합 된 한정자</span><span class="sxs-lookup"><span data-stu-id="6c8d2-116">Combined Modifiers</span></span>  

 <span data-ttu-id="6c8d2-117">`Overridable`메서드에 대해 또는를 지정할 수 없습니다 `NotOverridable` `Private` .</span><span class="sxs-lookup"><span data-stu-id="6c8d2-117">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="6c8d2-118">`Overridable` `MustOverride` `NotOverridable` 동일한 선언에서, 또는를 함께 지정할 수 없습니다 `Shared` .</span><span class="sxs-lookup"><span data-stu-id="6c8d2-118">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="6c8d2-119">재정의 요소는 암시적으로 재정의할 수 있으므로 `Overridable`과 `Overrides`를 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-119">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="6c8d2-120">사용량</span><span class="sxs-lookup"><span data-stu-id="6c8d2-120">Usage</span></span>  

 <span data-ttu-id="6c8d2-121">`Overridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c8d2-121">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="6c8d2-122">Function 문</span><span class="sxs-lookup"><span data-stu-id="6c8d2-122">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="6c8d2-123">Property Statement</span><span class="sxs-lookup"><span data-stu-id="6c8d2-123">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="6c8d2-124">Sub 문</span><span class="sxs-lookup"><span data-stu-id="6c8d2-124">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="6c8d2-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c8d2-125">See also</span></span>

- [<span data-ttu-id="6c8d2-126">한정자</span><span class="sxs-lookup"><span data-stu-id="6c8d2-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="6c8d2-127">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="6c8d2-127">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="6c8d2-128">New</span><span class="sxs-lookup"><span data-stu-id="6c8d2-128">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="6c8d2-129">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="6c8d2-129">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="6c8d2-130">재정의</span><span class="sxs-lookup"><span data-stu-id="6c8d2-130">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="6c8d2-131">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="6c8d2-131">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="6c8d2-132">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="6c8d2-132">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
