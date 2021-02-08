---
description: '자세히 알아보기: MustOverride (Visual Basic)'
title: New
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
ms.openlocfilehash: df7200a7f7ec4bfda34765747d6318bc50a38dd1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774527"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="9341e-103">MustOverride(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9341e-103">MustOverride (Visual Basic)</span></span>

<span data-ttu-id="9341e-104">속성 또는 프로시저가이 클래스에서 구현 되지 않고 파생 클래스에서 재정의 되어야 사용할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9341e-104">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9341e-105">설명</span><span class="sxs-lookup"><span data-stu-id="9341e-105">Remarks</span></span>  

 <span data-ttu-id="9341e-106">`MustOverride`속성 또는 프로시저 선언 문에서만를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9341e-106">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="9341e-107">를 지정 하는 속성 또는 프로시저는 `MustOverride` 클래스의 멤버 여야 하 고 클래스는 [MustInherit](mustinherit.md)로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9341e-107">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9341e-108">규칙</span><span class="sxs-lookup"><span data-stu-id="9341e-108">Rules</span></span>  
  
- <span data-ttu-id="9341e-109">**선언이 완전 하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="9341e-109">**Incomplete Declaration.**</span></span> <span data-ttu-id="9341e-110">을 지정 하는 경우 `MustOverride` `End Function` , `End Property` 또는 문 뿐만 아니라 속성 또는 프로시저에 대 한 추가 코드 줄을 제공 하지 않습니다 `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="9341e-110">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="9341e-111">**결합된 한정자.**</span><span class="sxs-lookup"><span data-stu-id="9341e-111">**Combined Modifiers.**</span></span> <span data-ttu-id="9341e-112">`MustOverride` `NotOverridable` `Overridable` 동일한 선언에서, 또는를 함께 지정할 수 없습니다 `Shared` .</span><span class="sxs-lookup"><span data-stu-id="9341e-112">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="9341e-113">**숨김 및 재정의.**</span><span class="sxs-lookup"><span data-stu-id="9341e-113">**Shadowing and Overriding.**</span></span> <span data-ttu-id="9341e-114">숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방법에는 중요한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9341e-114">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="9341e-115">자세한 내용은 [Visual Basic에서 숨기기](../../programming-guide/language-features/declared-elements/shadowing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9341e-115">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="9341e-116">**대체 용어.**</span><span class="sxs-lookup"><span data-stu-id="9341e-116">**Alternate Terms.**</span></span> <span data-ttu-id="9341e-117">재정의를 제외 하 고 사용할 수 없는 요소는 *순수 가상* 요소 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="9341e-117">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="9341e-118">`MustOverride` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9341e-118">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="9341e-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="9341e-119">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="9341e-120">Property Statement</span><span class="sxs-lookup"><span data-stu-id="9341e-120">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="9341e-121">Sub 문</span><span class="sxs-lookup"><span data-stu-id="9341e-121">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="9341e-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9341e-122">See also</span></span>

- [<span data-ttu-id="9341e-123">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="9341e-123">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="9341e-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="9341e-124">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="9341e-125">재정의</span><span class="sxs-lookup"><span data-stu-id="9341e-125">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="9341e-126">MustInherit</span><span class="sxs-lookup"><span data-stu-id="9341e-126">MustInherit</span></span>](mustinherit.md)
- [<span data-ttu-id="9341e-127">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="9341e-127">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="9341e-128">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="9341e-128">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
