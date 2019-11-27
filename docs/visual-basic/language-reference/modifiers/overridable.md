---
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
ms.openlocfilehash: 9c639665fd92a56de6fb6e5147cda873ef457b45
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351395"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="542c4-102">Overridable(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="542c4-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="542c4-103">속성 또는 프로시저가 파생 클래스의 이름이 같은 속성 또는 프로시저로 재정의 될 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="542c4-104">주의</span><span class="sxs-lookup"><span data-stu-id="542c4-104">Remarks</span></span>  
 <span data-ttu-id="542c4-105">`Overridable` 한정자를 사용 하면 클래스의 속성 또는 메서드가 파생 클래스에서 재정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="542c4-106">[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) 한정자는 속성 또는 메서드가 파생 클래스에서 재정의 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="542c4-107">자세한 내용은 [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="542c4-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="542c4-108">`Overridable` 또는 `NotOverridable` 한정자가 지정 되지 않은 경우 기본 설정은 속성이 나 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="542c4-109">속성 또는 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정은 `Overridable`입니다. 그렇지 않으면 `NotOverridable`됩니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="542c4-110">을 숨기 나 재정의 하 여 상속 된 요소를 다시 정의할 수 있지만 두 방법 간에는 상당한 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="542c4-111">자세한 내용은 [Visual Basic에서 숨기기](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="542c4-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="542c4-112">재정의할 수 있는 요소를 *가상* 요소 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="542c4-113">재정의할 수는 있지만 일 필요가 없는 경우에는 *구체적* 요소가 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="542c4-114">`Overridable`는 속성 또는 프로시저 선언문 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="542c4-115">결합 된 한정자</span><span class="sxs-lookup"><span data-stu-id="542c4-115">Combined Modifiers</span></span>  
 <span data-ttu-id="542c4-116">`Private` 메서드에 대해 `Overridable` 또는 `NotOverridable`를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="542c4-117">동일한 선언에서 `MustOverride`, `NotOverridable`또는 `Shared`와 함께 `Overridable`를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="542c4-118">재정의 요소는 암시적으로 재정의할 수 있으므로 `Overridable`과 `Overrides`를 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="542c4-119">사용법</span><span class="sxs-lookup"><span data-stu-id="542c4-119">Usage</span></span>  
 <span data-ttu-id="542c4-120">`Overridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542c4-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="542c4-121">Function 문</span><span class="sxs-lookup"><span data-stu-id="542c4-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="542c4-122">Property 문</span><span class="sxs-lookup"><span data-stu-id="542c4-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="542c4-123">Sub 문</span><span class="sxs-lookup"><span data-stu-id="542c4-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="542c4-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="542c4-124">See also</span></span>

- [<span data-ttu-id="542c4-125">한정자</span><span class="sxs-lookup"><span data-stu-id="542c4-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="542c4-126">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="542c4-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="542c4-127">MyBase</span><span class="sxs-lookup"><span data-stu-id="542c4-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="542c4-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="542c4-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="542c4-129">재정의</span><span class="sxs-lookup"><span data-stu-id="542c4-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="542c4-130">키워드</span><span class="sxs-lookup"><span data-stu-id="542c4-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="542c4-131">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="542c4-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
