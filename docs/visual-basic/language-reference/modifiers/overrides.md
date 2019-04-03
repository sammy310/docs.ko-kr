---
title: Overrides(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 9eb19bf5e89b12a32cae28b2c087570acc10f3ad
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826589"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="ee356-102">Overrides(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee356-102">Overrides (Visual Basic)</span></span>
<span data-ttu-id="ee356-103">속성 또는 프로시저가 기본 클래스에서 상속된 이름이 같은 속성 또는 프로시저를 재정의하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee356-104">설명</span><span class="sxs-lookup"><span data-stu-id="ee356-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ee356-105">규칙</span><span class="sxs-lookup"><span data-stu-id="ee356-105">Rules</span></span>  
  
-   <span data-ttu-id="ee356-106">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="ee356-106">**Declaration Context.**</span></span> <span data-ttu-id="ee356-107">속성 또는 프로시저 선언문에서만 `Overrides`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-107">You can use `Overrides` only in a property or procedure declaration statement.</span></span>  
  
-   <span data-ttu-id="ee356-108">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="ee356-108">**Combined Modifiers.**</span></span> <span data-ttu-id="ee356-109">동일한 선언에서 `Shadows` 또는 `Shared`와 함께 `Overrides`를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-109">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="ee356-110">재정의 요소는 암시적으로 재정의할 수 있으므로 `Overridable`과 `Overrides`를 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-110">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
-   <span data-ttu-id="ee356-111">**일치 하는 서명입니다.**</span><span class="sxs-lookup"><span data-stu-id="ee356-111">**Matching Signatures.**</span></span> <span data-ttu-id="ee356-112">이 선언의 서명은 정확히 일치 해야 합니다 *서명* 속성 또는 프로시저를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-112">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="ee356-113">즉, 매개 변수 목록에 동일한 데이터 형식의 매개 변수가 동일한 개수 및 순서로 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-113">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>  
  
     <span data-ttu-id="ee356-114">서명 외에도 재정의 선언이 다음과 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-114">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>  
  
    -   <span data-ttu-id="ee356-115">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="ee356-115">The access level</span></span>  
  
    -   <span data-ttu-id="ee356-116">반환 형식(있는 경우)</span><span class="sxs-lookup"><span data-stu-id="ee356-116">The return type, if any</span></span>  
  
-   <span data-ttu-id="ee356-117">**제네릭 서명입니다.**</span><span class="sxs-lookup"><span data-stu-id="ee356-117">**Generic Signatures.**</span></span> <span data-ttu-id="ee356-118">제네릭 프로시저의 경우 서명에 형식 매개 변수 개수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-118">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="ee356-119">따라서 해당 측면에서도 재정의 선언이 기본 클래스 버전과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-119">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>  
  
-   <span data-ttu-id="ee356-120">**추가 일치.**</span><span class="sxs-lookup"><span data-stu-id="ee356-120">**Additional Matching.**</span></span> <span data-ttu-id="ee356-121">기본 클래스 버전과의 서명 일치 외에도 이 선언은 다음 측면에서 기본 클래스 버전과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-121">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>  
  
    -   <span data-ttu-id="ee356-122">액세스 수준 한정자 (같은 [공용](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="ee356-122">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>  
  
    -   <span data-ttu-id="ee356-123">각 매개 변수의 전달 메커니즘 ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) 하거나 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="ee356-123">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>  
  
    -   <span data-ttu-id="ee356-124">제네릭 프로시저의 각 형식 매개 변수에 대한 제약 조건 목록</span><span class="sxs-lookup"><span data-stu-id="ee356-124">Constraint lists on each type parameter of a generic procedure</span></span>  
  
-   <span data-ttu-id="ee356-125">**숨기기와 재정의 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ee356-125">**Shadowing and Overriding.**</span></span> <span data-ttu-id="ee356-126">숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방법에는 중요한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-126">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="ee356-127">자세한 내용은 [Visual Basic의 숨김 기능](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-127">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="ee356-128">`Overrides`를 사용하는 경우 라이브러리 API가 보다 쉽게 C#으로 작업할 수 있도록 컴파일러에서 암시적으로 `Overloads`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-128">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="ee356-129">`Overrides` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee356-129">The `Overrides` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ee356-130">Function 문</span><span class="sxs-lookup"><span data-stu-id="ee356-130">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ee356-131">Property 문</span><span class="sxs-lookup"><span data-stu-id="ee356-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ee356-132">Sub 문</span><span class="sxs-lookup"><span data-stu-id="ee356-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ee356-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="ee356-133">See also</span></span>

- [<span data-ttu-id="ee356-134">MustOverride</span><span class="sxs-lookup"><span data-stu-id="ee356-134">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="ee356-135">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="ee356-135">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="ee356-136">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="ee356-136">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="ee356-137">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="ee356-137">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="ee356-138">Visual Basic의 숨김 기능</span><span class="sxs-lookup"><span data-stu-id="ee356-138">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="ee356-139">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="ee356-139">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="ee356-140">형식 목록</span><span class="sxs-lookup"><span data-stu-id="ee356-140">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
