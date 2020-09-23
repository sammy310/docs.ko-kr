---
title: 섀도잉과 재정의 간의 차이점
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: 98c073f8fa403416b2425431ff4334b990726f44
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095449"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a><span data-ttu-id="9f08a-102">숨기기와 재정의의 차이점(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f08a-102">Differences Between Shadowing and Overriding (Visual Basic)</span></span>

<span data-ttu-id="9f08a-103">기본 클래스에서 상속 하는 클래스를 정의 하는 경우 파생 클래스에서 하나 이상의 기본 클래스 요소를 다시 정의 하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-103">When you define a class that inherits from a base class, you sometimes want to redefine one or more of the base class elements in the derived class.</span></span> <span data-ttu-id="9f08a-104">이러한 용도로 숨김과 재정의를 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-104">Shadowing and overriding are both available for this purpose.</span></span>  
  
## <a name="comparison"></a><span data-ttu-id="9f08a-105">비교</span><span class="sxs-lookup"><span data-stu-id="9f08a-105">Comparison</span></span>  

 <span data-ttu-id="9f08a-106">숨김 및 재정의는 모두 파생 클래스가 기본 클래스에서 상속 하는 경우와 선언 된 요소를 다른 요소와 모두 재정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-106">Shadowing and overriding are both used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="9f08a-107">하지만 둘 사이에는 상당한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-107">But there are significant differences between the two.</span></span>  
  
 <span data-ttu-id="9f08a-108">다음 표에서는 숨김과를 재정의 하는 것을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-108">The following table compares shadowing with overriding.</span></span>  
  
||||  
|---|---|---|  
|<span data-ttu-id="9f08a-109">비교 지점</span><span class="sxs-lookup"><span data-stu-id="9f08a-109">Point of comparison</span></span>|<span data-ttu-id="9f08a-110">섀도잉</span><span class="sxs-lookup"><span data-stu-id="9f08a-110">Shadowing</span></span>|<span data-ttu-id="9f08a-111">대체</span><span class="sxs-lookup"><span data-stu-id="9f08a-111">Overriding</span></span>|  
|<span data-ttu-id="9f08a-112">목적</span><span class="sxs-lookup"><span data-stu-id="9f08a-112">Purpose</span></span>|<span data-ttu-id="9f08a-113">파생 클래스에 이미 정의 된 멤버를 소개 하는 후속 기본 클래스 수정 으로부터 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-113">Protects against a subsequent base-class modification that introduces a member you have already defined in your derived class</span></span>|<span data-ttu-id="9f08a-114">동일한 호출 시퀀스<sup>1</sup> 을 사용 하 여 프로시저 또는 속성의 다른 구현을 정의 함으로써 다형성을 달성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-114">Achieves polymorphism by defining a different implementation of a procedure or property with the same calling sequence<sup>1</sup></span></span>|  
|<span data-ttu-id="9f08a-115">다시 정의 요소</span><span class="sxs-lookup"><span data-stu-id="9f08a-115">Redefined element</span></span>|<span data-ttu-id="9f08a-116">선언 된 모든 요소 형식</span><span class="sxs-lookup"><span data-stu-id="9f08a-116">Any declared element type</span></span>|<span data-ttu-id="9f08a-117">프로시저 ( `Function` , `Sub` 또는 `Operator` ) 또는 속성만</span><span class="sxs-lookup"><span data-stu-id="9f08a-117">Only a procedure (`Function`, `Sub`, or `Operator`) or property</span></span>|  
|<span data-ttu-id="9f08a-118">요소 재정의</span><span class="sxs-lookup"><span data-stu-id="9f08a-118">Redefining element</span></span>|<span data-ttu-id="9f08a-119">선언 된 모든 요소 형식</span><span class="sxs-lookup"><span data-stu-id="9f08a-119">Any declared element type</span></span>|<span data-ttu-id="9f08a-120">동일한 호출 시퀀스<sup>1</sup> 을 사용 하는 프로시저나 속성만</span><span class="sxs-lookup"><span data-stu-id="9f08a-120">Only a procedure or property with the identical calling sequence<sup>1</sup></span></span>|  
|<span data-ttu-id="9f08a-121">재정의 요소의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="9f08a-121">Access level of redefining element</span></span>|<span data-ttu-id="9f08a-122">모든 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="9f08a-122">Any access level</span></span>|<span data-ttu-id="9f08a-123">재정의 된 요소의 액세스 수준을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-123">Cannot change access level of overridden element</span></span>|  
|<span data-ttu-id="9f08a-124">재정의 요소의 가독성 및 쓰기 가능성</span><span class="sxs-lookup"><span data-stu-id="9f08a-124">Readability and writability of redefining element</span></span>|<span data-ttu-id="9f08a-125">모든 조합</span><span class="sxs-lookup"><span data-stu-id="9f08a-125">Any combination</span></span>|<span data-ttu-id="9f08a-126">재정의 된 속성의 가독성 또는 쓰기 가능성를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-126">Cannot change readability or writability of overridden property</span></span>|  
|<span data-ttu-id="9f08a-127">재정의를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-127">Control over redefining</span></span>|<span data-ttu-id="9f08a-128">기본 클래스 요소는 숨김을 적용 하거나 금지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-128">Base class element cannot enforce or prohibit shadowing</span></span>|<span data-ttu-id="9f08a-129">기본 클래스 요소는 `MustOverride` , `NotOverridable` 또는를 지정할 수 있습니다. `Overridable`</span><span class="sxs-lookup"><span data-stu-id="9f08a-129">Base class element can specify `MustOverride`, `NotOverridable`, or `Overridable`</span></span>|  
|<span data-ttu-id="9f08a-130">키워드 사용</span><span class="sxs-lookup"><span data-stu-id="9f08a-130">Keyword usage</span></span>|<span data-ttu-id="9f08a-131">`Shadows`파생 클래스에서 권장 됩니다. `Shadows`또는 지정 되지 않은 경우 `Shadows` `Overrides` <sup>두</sup> 가지 모두</span><span class="sxs-lookup"><span data-stu-id="9f08a-131">`Shadows` recommended in derived class; `Shadows` assumed if neither `Shadows` nor `Overrides` specified<sup>2</sup></span></span>|<span data-ttu-id="9f08a-132">`Overridable` 또는 `MustOverride` 기본 클래스에 필요 합니다 `Overrides` . 파생 클래스에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-132">`Overridable` or `MustOverride` required in base class; `Overrides` required in derived class</span></span>|  
|<span data-ttu-id="9f08a-133">파생 클래스에서 파생 되는 클래스에의 한 재정의 요소 상속</span><span class="sxs-lookup"><span data-stu-id="9f08a-133">Inheritance of redefining element by classes deriving from your derived class</span></span>|<span data-ttu-id="9f08a-134">추가 파생 클래스에서 상속 되는 요소 숨김 숨겨진 요소는 계속 숨겨져 있습니다.<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9f08a-134">Shadowing element inherited by further derived classes; shadowed element still hidden<sup>3</sup></span></span>|<span data-ttu-id="9f08a-135">추가로 파생 된 클래스에서 상속 된 요소 재정의 재정의 된 요소가 계속 재정의 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-135">Overriding element inherited by further derived classes; overridden element still overridden</span></span>|  
  
 <span data-ttu-id="9f08a-136"><sup>1</sup> *호출 시퀀스* 는 요소 형식 ( `Function` ,, `Sub` `Operator` 또는 `Property` ), 이름, 매개 변수 목록 및 반환 형식으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-136"><sup>1</sup> The *calling sequence* consists of the element type (`Function`, `Sub`, `Operator`, or `Property`), name, parameter list, and return type.</span></span> <span data-ttu-id="9f08a-137">속성 또는 그 밖의 다른 방법으로는 프로시저를 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-137">You cannot override a procedure with a property, or the other way around.</span></span> <span data-ttu-id="9f08a-138">한 종류의 프로시저 ( `Function` , `Sub` 또는 `Operator` )를 다른 종류의 프로시저로 재정의할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-138">You cannot override one kind of procedure (`Function`, `Sub`, or `Operator`) with another kind.</span></span>  
  
 <span data-ttu-id="9f08a-139"><sup>2</sup> 또는 중 하나를 지정 하지 `Shadows` 않으면 `Overrides` 컴파일러에서 사용 하려는 재정의의 종류를 확인할 수 있도록 경고 메시지를 발행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-139"><sup>2</sup> If you do not specify either `Shadows` or `Overrides`, the compiler issues a warning message to help you be sure which kind of redefinition you want to use.</span></span> <span data-ttu-id="9f08a-140">경고를 무시 하면 섀도잉 메커니즘이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-140">If you ignore the warning, the shadowing mechanism is used.</span></span>  
  
 <span data-ttu-id="9f08a-141"><sup>3</sup> 추가 파생 클래스에서 섀도잉 요소에 액세스할 수 없는 경우 숨김은 상속 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-141"><sup>3</sup> If the shadowing element is inaccessible in a further derived class, shadowing is not inherited.</span></span> <span data-ttu-id="9f08a-142">예를 들어, 섀도잉 요소를로 선언 하는 경우 `Private` 파생 클래스에서 파생 되는 클래스는 숨기는 요소가 아니라 원래 요소를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-142">For example, if you declare the shadowing element as `Private`, a class deriving from your derived class inherits the original element instead of the shadowing element.</span></span>  
  
## <a name="guidelines"></a><span data-ttu-id="9f08a-143">지침</span><span class="sxs-lookup"><span data-stu-id="9f08a-143">Guidelines</span></span>  

 <span data-ttu-id="9f08a-144">일반적으로 다음과 같은 경우에 재정의를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-144">You normally use overriding in the following cases:</span></span>  
  
- <span data-ttu-id="9f08a-145">다형 파생 클래스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-145">You are defining polymorphic derived classes.</span></span>  
  
- <span data-ttu-id="9f08a-146">컴파일러가 동일한 요소 형식 및 호출 시퀀스를 강제 적용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-146">You want the safety of having the compiler enforce the identical element type and calling sequence.</span></span>  
  
 <span data-ttu-id="9f08a-147">일반적으로 다음과 같은 경우에 섀도잉을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-147">You normally use shadowing in the following cases:</span></span>  
  
- <span data-ttu-id="9f08a-148">기본 클래스를 수정 하 고 사용자와 동일한 이름을 사용 하 여 요소를 정의 하는 것이 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-148">You anticipate that your base class might be modified and define an element using the same name as yours.</span></span>  
  
- <span data-ttu-id="9f08a-149">요소 형식 또는 호출 시퀀스를 자유롭게 변경 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f08a-149">You want the freedom of changing the element type or calling sequence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f08a-150">참조</span><span class="sxs-lookup"><span data-stu-id="9f08a-150">See also</span></span>

- [<span data-ttu-id="9f08a-151">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="9f08a-151">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="9f08a-152">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="9f08a-152">Shadowing in Visual Basic</span></span>](shadowing.md)
- [<span data-ttu-id="9f08a-153">방법: 사용자 변수와 이름이 같은 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="9f08a-153">How to: Hide a Variable with the Same Name as Your Variable</span></span>](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="9f08a-154">방법: 상속된 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="9f08a-154">How to: Hide an Inherited Variable</span></span>](how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="9f08a-155">방법: 파생 클래스에 의해 숨겨진 변수에 액세스</span><span class="sxs-lookup"><span data-stu-id="9f08a-155">How to: Access a Variable Hidden by a Derived Class</span></span>](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="9f08a-156">Overloads</span><span class="sxs-lookup"><span data-stu-id="9f08a-156">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
- [<span data-ttu-id="9f08a-157">재정의</span><span class="sxs-lookup"><span data-stu-id="9f08a-157">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
