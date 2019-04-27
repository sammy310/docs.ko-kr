---
title: MustOverride(Visual Basic)
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
ms.openlocfilehash: 0ddd7d0d2a57afc02aa7483ba5e83b65c48af534
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920758"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="fb4b2-102">MustOverride(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb4b2-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="fb4b2-103">속성 또는 프로시저가이 클래스에서 구현 되지 않습니다 및 사용할 수 전에 파생된 클래스에서 재정의 해야 합니다를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb4b2-104">설명</span><span class="sxs-lookup"><span data-stu-id="fb4b2-104">Remarks</span></span>  
 <span data-ttu-id="fb4b2-105">속성 또는 프로시저 선언문에서만 `MustOverride`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="fb4b2-106">속성을 지정 하는 절차 `MustOverride` 클래스의 멤버 여야 합니다 클래스를 표시 해야 합니다 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="fb4b2-107">규칙</span><span class="sxs-lookup"><span data-stu-id="fb4b2-107">Rules</span></span>  
  
-   <span data-ttu-id="fb4b2-108">**완료 되지 않은 선언입니다.**</span><span class="sxs-lookup"><span data-stu-id="fb4b2-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="fb4b2-109">지정 하는 경우 `MustOverride`, 되지 모든 추가 속성 또는 프로시저에 대 한 코드 줄을 지정 하지 않으면 아무리 `End Function`, `End Property`, 또는 `End Sub` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="fb4b2-110">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="fb4b2-110">**Combined Modifiers.**</span></span> <span data-ttu-id="fb4b2-111">지정할 수 없습니다 `MustOverride` 와 함께 `NotOverridable`를 `Overridable`, 또는 `Shared` 같은 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
-   <span data-ttu-id="fb4b2-112">**숨기기와 재정의 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb4b2-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="fb4b2-113">숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방법에는 중요한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="fb4b2-114">자세한 내용은 [Visual Basic의 숨김 기능](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
-   <span data-ttu-id="fb4b2-115">**대체 용어입니다.**</span><span class="sxs-lookup"><span data-stu-id="fb4b2-115">**Alternate Terms.**</span></span> <span data-ttu-id="fb4b2-116">재정의에서 제외 하 고 사용할 수 없는 요소 라고도 함은 *순수 가상* 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="fb4b2-117">`MustOverride` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="fb4b2-118">Function 문</span><span class="sxs-lookup"><span data-stu-id="fb4b2-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="fb4b2-119">Property 문</span><span class="sxs-lookup"><span data-stu-id="fb4b2-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="fb4b2-120">Sub 문</span><span class="sxs-lookup"><span data-stu-id="fb4b2-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="fb4b2-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="fb4b2-121">See also</span></span>

- [<span data-ttu-id="fb4b2-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="fb4b2-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="fb4b2-123">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="fb4b2-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="fb4b2-124">재정의</span><span class="sxs-lookup"><span data-stu-id="fb4b2-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="fb4b2-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="fb4b2-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="fb4b2-126">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="fb4b2-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="fb4b2-127">Visual Basic의 숨김 기능</span><span class="sxs-lookup"><span data-stu-id="fb4b2-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
