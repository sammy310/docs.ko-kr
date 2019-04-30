---
title: Overridable(Visual Basic)
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
ms.openlocfilehash: 91a1cedc66fd66e336b6e7976ad87ad638cb43c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053901"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="ad4da-102">Overridable(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad4da-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="ad4da-103">속성 또는 프로시저를 동일 하 게 명명 된 속성 또는 프로시저가 파생된 클래스에서 재정의할 수 있음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad4da-104">설명</span><span class="sxs-lookup"><span data-stu-id="ad4da-104">Remarks</span></span>  
 <span data-ttu-id="ad4da-105">`Overridable` 한정자 파생된 클래스에서 재정의 될 수 클래스에서 속성 또는 메서드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="ad4da-106">합니다 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) 파생된 클래스에서 재정의 되는 속성 또는 메서드를 방지 하는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="ad4da-107">자세한 내용은 [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad4da-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="ad4da-108">경우는 `Overridable` 또는 `NotOverridable` 한정자를 지정 하지 않으면 기본 설정 속성 또는 메서드의 기본 클래스 속성 또는 메서드를 재정의 하는 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="ad4da-109">속성 또는 메서드의 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정은입니다 `Overridable`이 고, 그렇지 않으면 것 `NotOverridable`입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="ad4da-110">섀도 하거나 상속된 된 요소를 다시 정의 하기 위해 재정의할 수 있지만 두 가지 방법 간에 중요 한 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="ad4da-111">자세한 내용은 [Visual Basic의 숨김 기능](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="ad4da-112">재정의할 수 있는 요소는 때때로 이라고 하는 *가상* 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="ad4da-113">수도 라고를 재정의할 수 있습니다 수 없는 경우에 *구체적인* 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="ad4da-114">속성 또는 프로시저 선언문에서만 `Overridable`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="ad4da-115">결합 된 한정자</span><span class="sxs-lookup"><span data-stu-id="ad4da-115">Combined Modifiers</span></span>  
 <span data-ttu-id="ad4da-116">지정할 수 없습니다 `Overridable` 나 `NotOverridable` 에 대 한는 `Private` 메서드.</span><span class="sxs-lookup"><span data-stu-id="ad4da-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="ad4da-117">지정할 수 없습니다 `Overridable` 와 함께 `MustOverride`를 `NotOverridable`, 또는 `Shared` 같은 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="ad4da-118">재정의 요소는 암시적으로 재정의할 수 있으므로 `Overridable`과 `Overrides`를 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="ad4da-119">사용법</span><span class="sxs-lookup"><span data-stu-id="ad4da-119">Usage</span></span>  
 <span data-ttu-id="ad4da-120">`Overridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad4da-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ad4da-121">Function 문</span><span class="sxs-lookup"><span data-stu-id="ad4da-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ad4da-122">Property 문</span><span class="sxs-lookup"><span data-stu-id="ad4da-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ad4da-123">Sub 문</span><span class="sxs-lookup"><span data-stu-id="ad4da-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ad4da-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad4da-124">See also</span></span>

- [<span data-ttu-id="ad4da-125">한정자</span><span class="sxs-lookup"><span data-stu-id="ad4da-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="ad4da-126">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="ad4da-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="ad4da-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="ad4da-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="ad4da-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="ad4da-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="ad4da-129">재정의</span><span class="sxs-lookup"><span data-stu-id="ad4da-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="ad4da-130">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="ad4da-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="ad4da-131">Visual Basic의 숨김 기능</span><span class="sxs-lookup"><span data-stu-id="ad4da-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
