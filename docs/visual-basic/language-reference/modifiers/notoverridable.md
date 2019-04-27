---
title: NotOverridable(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: 41c08a48fdb7501081e887fb5cf9f99c334c72ac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920655"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="eaa7c-102">NotOverridable(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eaa7c-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="eaa7c-103">파생된 클래스에서 속성 또는 프로시저를 재정의할 수 없음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7c-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaa7c-104">설명</span><span class="sxs-lookup"><span data-stu-id="eaa7c-104">Remarks</span></span>  
 <span data-ttu-id="eaa7c-105">`NotOverridable` 파생된 클래스에서 재정의 되는 속성 또는 메서드를 방지 하는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7c-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="eaa7c-106">합니다 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) 한정자 파생된 클래스에서 재정의 될 수 클래스에서 속성 또는 메서드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7c-106">The [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="eaa7c-107">자세한 내용은 [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eaa7c-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="eaa7c-108">경우는 `Overridable` 또는 `NotOverridable` 한정자를 지정 하지 않으면 기본 설정 속성 또는 메서드의 기본 클래스 속성 또는 메서드를 재정의 하는 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7c-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="eaa7c-109">속성 또는 메서드의 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정은입니다 `Overridable`이 고, 그렇지 않으면 것 `NotOverridable`입니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7c-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="eaa7c-110">재정의할 수 없는 요소 라고도 함은 *봉인* 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7c-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="eaa7c-111">속성 또는 프로시저 선언문에서만 `NotOverridable`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7c-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="eaa7c-112">지정할 수 있습니다 `NotOverridable` 함께에서 다른 속성 또는 프로시저, 즉, 재정의 하는 프로시저 또는 속성에만 `Overrides`합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7c-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="eaa7c-113">결합 된 한정자</span><span class="sxs-lookup"><span data-stu-id="eaa7c-113">Combined Modifiers</span></span>  
 <span data-ttu-id="eaa7c-114">지정할 수 없습니다 `Overridable` 나 `NotOverridable` 에 대 한는 `Private` 메서드.</span><span class="sxs-lookup"><span data-stu-id="eaa7c-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="eaa7c-115">지정할 수 없습니다 `NotOverridable` 와 함께 `MustOverride`를 `Overridable`, 또는 `Shared` 같은 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7c-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="eaa7c-116">사용법</span><span class="sxs-lookup"><span data-stu-id="eaa7c-116">Usage</span></span>  
 <span data-ttu-id="eaa7c-117">`NotOverridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7c-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="eaa7c-118">Function 문</span><span class="sxs-lookup"><span data-stu-id="eaa7c-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="eaa7c-119">Property 문</span><span class="sxs-lookup"><span data-stu-id="eaa7c-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="eaa7c-120">Sub 문</span><span class="sxs-lookup"><span data-stu-id="eaa7c-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="eaa7c-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="eaa7c-121">See also</span></span>

- [<span data-ttu-id="eaa7c-122">한정자</span><span class="sxs-lookup"><span data-stu-id="eaa7c-122">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="eaa7c-123">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="eaa7c-123">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="eaa7c-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="eaa7c-124">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="eaa7c-125">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="eaa7c-125">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="eaa7c-126">재정의</span><span class="sxs-lookup"><span data-stu-id="eaa7c-126">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="eaa7c-127">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="eaa7c-127">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="eaa7c-128">Visual Basic의 숨김 기능</span><span class="sxs-lookup"><span data-stu-id="eaa7c-128">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
