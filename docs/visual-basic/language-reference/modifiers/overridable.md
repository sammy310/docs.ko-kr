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
ms.openlocfilehash: 8506aba7e64f2dbd975cc275cefb7b5bb1aefda5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875003"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="69b02-102">Overridable(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69b02-102">Overridable (Visual Basic)</span></span>

<span data-ttu-id="69b02-103">속성 또는 프로시저가 파생 클래스의 이름이 같은 속성 또는 프로시저로 재정의 될 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b02-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69b02-104">설명</span><span class="sxs-lookup"><span data-stu-id="69b02-104">Remarks</span></span>  

 <span data-ttu-id="69b02-105">`Overridable`한정자를 사용 하면 클래스의 속성 또는 메서드가 파생 클래스에서 재정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b02-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="69b02-106">[NotOverridable](notoverridable.md) 한정자는 속성 또는 메서드가 파생 클래스에서 재정의 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b02-106">The [NotOverridable](notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="69b02-107">자세한 내용은 [상속 기본 사항](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69b02-107">For more information, see [Inheritance Basics](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="69b02-108">`Overridable`또는 `NotOverridable` 한정자가 지정 되지 않은 경우 기본 설정은 속성이 나 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="69b02-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="69b02-109">속성 또는 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정은입니다 `Overridable` . 그렇지 않으면 `NotOverridable` 입니다.</span><span class="sxs-lookup"><span data-stu-id="69b02-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="69b02-110">을 숨기 나 재정의 하 여 상속 된 요소를 다시 정의할 수 있지만 두 방법 간에는 상당한 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b02-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="69b02-111">자세한 내용은 [Visual Basic에서 숨기기](../../programming-guide/language-features/declared-elements/shadowing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69b02-111">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="69b02-112">재정의할 수 있는 요소를 *가상* 요소 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b02-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="69b02-113">재정의할 수는 있지만 일 필요가 없는 경우에는 *구체적* 요소가 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b02-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="69b02-114">`Overridable`속성 또는 프로시저 선언 문에서만를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b02-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="69b02-115">결합 된 한정자</span><span class="sxs-lookup"><span data-stu-id="69b02-115">Combined Modifiers</span></span>  

 <span data-ttu-id="69b02-116">`Overridable`메서드에 대해 또는를 지정할 수 없습니다 `NotOverridable` `Private` .</span><span class="sxs-lookup"><span data-stu-id="69b02-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="69b02-117">`Overridable` `MustOverride` `NotOverridable` 동일한 선언에서, 또는를 함께 지정할 수 없습니다 `Shared` .</span><span class="sxs-lookup"><span data-stu-id="69b02-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="69b02-118">재정의 요소는 암시적으로 재정의할 수 있으므로 `Overridable`과 `Overrides`를 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69b02-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="69b02-119">사용량</span><span class="sxs-lookup"><span data-stu-id="69b02-119">Usage</span></span>  

 <span data-ttu-id="69b02-120">`Overridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b02-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="69b02-121">Function 문</span><span class="sxs-lookup"><span data-stu-id="69b02-121">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="69b02-122">Property Statement</span><span class="sxs-lookup"><span data-stu-id="69b02-122">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="69b02-123">Sub 문</span><span class="sxs-lookup"><span data-stu-id="69b02-123">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="69b02-124">참조</span><span class="sxs-lookup"><span data-stu-id="69b02-124">See also</span></span>

- [<span data-ttu-id="69b02-125">한정자</span><span class="sxs-lookup"><span data-stu-id="69b02-125">Modifiers</span></span>](index.md)
- [<span data-ttu-id="69b02-126">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="69b02-126">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="69b02-127">New</span><span class="sxs-lookup"><span data-stu-id="69b02-127">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="69b02-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="69b02-128">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="69b02-129">재정의</span><span class="sxs-lookup"><span data-stu-id="69b02-129">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="69b02-130">키워드</span><span class="sxs-lookup"><span data-stu-id="69b02-130">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="69b02-131">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="69b02-131">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
