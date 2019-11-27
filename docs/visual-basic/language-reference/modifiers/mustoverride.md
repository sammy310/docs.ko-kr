---
title: '%%amp;lt;CLSCompliant(False)%%amp;gt;'
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: dc6a153a604fd0e5cee9d7d46ebcd63294f33628
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351489"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="7c720-102">MustOverride(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c720-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="7c720-103">속성 또는 프로시저가이 클래스에서 구현 되지 않고 파생 클래스에서 재정의 되어야 사용할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c720-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c720-104">설명</span><span class="sxs-lookup"><span data-stu-id="7c720-104">Remarks</span></span>  
 <span data-ttu-id="7c720-105">`MustOverride`는 속성 또는 프로시저 선언문 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c720-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="7c720-106">`MustOverride`를 지정 하는 속성 또는 프로시저는 클래스의 멤버 여야 하 고 클래스는 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c720-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="7c720-107">규칙</span><span class="sxs-lookup"><span data-stu-id="7c720-107">Rules</span></span>  
  
- <span data-ttu-id="7c720-108">**선언이 완전 하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="7c720-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="7c720-109">`MustOverride`지정 하면 `End Function`, `End Property`또는 `End Sub` 문이 아니더라도 속성 또는 프로시저에 대 한 추가 코드 줄을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c720-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="7c720-110">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="7c720-110">**Combined Modifiers.**</span></span> <span data-ttu-id="7c720-111">동일한 선언에서 `NotOverridable`, `Overridable`또는 `Shared`와 함께 `MustOverride`를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c720-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="7c720-112">**숨김 및 재정의.**</span><span class="sxs-lookup"><span data-stu-id="7c720-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="7c720-113">숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방법에는 중요한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c720-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="7c720-114">자세한 내용은 [Visual Basic에서 숨기기](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c720-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="7c720-115">**대체 용어.**</span><span class="sxs-lookup"><span data-stu-id="7c720-115">**Alternate Terms.**</span></span> <span data-ttu-id="7c720-116">재정의를 제외 하 고 사용할 수 없는 요소는 *순수 가상* 요소 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c720-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="7c720-117">`MustOverride` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c720-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="7c720-118">Function 문</span><span class="sxs-lookup"><span data-stu-id="7c720-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="7c720-119">Property 문</span><span class="sxs-lookup"><span data-stu-id="7c720-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="7c720-120">Sub 문</span><span class="sxs-lookup"><span data-stu-id="7c720-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="7c720-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="7c720-121">See also</span></span>

- [<span data-ttu-id="7c720-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="7c720-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="7c720-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="7c720-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="7c720-124">재정의</span><span class="sxs-lookup"><span data-stu-id="7c720-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="7c720-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="7c720-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="7c720-126">키워드</span><span class="sxs-lookup"><span data-stu-id="7c720-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="7c720-127">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="7c720-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
