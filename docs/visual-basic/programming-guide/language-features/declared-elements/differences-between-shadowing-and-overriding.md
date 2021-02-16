---
description: '자세히 알아보기: 숨김과 재정의 간의 차이점 (Visual Basic)'
title: 섀도잉과 재정의 간의 차이점
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: 94e661c83b95448e7a78931b81c87b6e974059ed
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100485200"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a><span data-ttu-id="ba899-103">숨기기와 재정의의 차이점(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba899-103">Differences Between Shadowing and Overriding (Visual Basic)</span></span>

<span data-ttu-id="ba899-104">기본 클래스에서 상속 하는 클래스를 정의 하는 경우 파생 클래스에서 하나 이상의 기본 클래스 요소를 다시 정의 하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-104">When you define a class that inherits from a base class, you sometimes want to redefine one or more of the base class elements in the derived class.</span></span> <span data-ttu-id="ba899-105">이러한 용도로 숨김과 재정의를 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-105">Shadowing and overriding are both available for this purpose.</span></span>  
  
## <a name="comparison"></a><span data-ttu-id="ba899-106">비교</span><span class="sxs-lookup"><span data-stu-id="ba899-106">Comparison</span></span>  

 <span data-ttu-id="ba899-107">숨김 및 재정의는 모두 파생 클래스가 기본 클래스에서 상속 하는 경우와 선언 된 요소를 다른 요소와 모두 재정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-107">Shadowing and overriding are both used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="ba899-108">하지만 둘 사이에는 상당한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-108">But there are significant differences between the two.</span></span>  
  
 <span data-ttu-id="ba899-109">다음 표에서는 숨김과를 재정의 하는 것을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-109">The following table compares shadowing with overriding.</span></span>  
  
||||  
|---|---|---|  
|<span data-ttu-id="ba899-110">비교 지점</span><span class="sxs-lookup"><span data-stu-id="ba899-110">Point of comparison</span></span>|<span data-ttu-id="ba899-111">섀도잉</span><span class="sxs-lookup"><span data-stu-id="ba899-111">Shadowing</span></span>|<span data-ttu-id="ba899-112">대체</span><span class="sxs-lookup"><span data-stu-id="ba899-112">Overriding</span></span>|  
|<span data-ttu-id="ba899-113">용도</span><span class="sxs-lookup"><span data-stu-id="ba899-113">Purpose</span></span>|<span data-ttu-id="ba899-114">파생 클래스에 이미 정의 된 멤버를 소개 하는 후속 기본 클래스 수정 으로부터 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-114">Protects against a subsequent base-class modification that introduces a member you have already defined in your derived class</span></span>|<span data-ttu-id="ba899-115">동일한 호출 시퀀스<sup>1</sup> 을 사용 하 여 프로시저 또는 속성의 다른 구현을 정의 함으로써 다형성을 달성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-115">Achieves polymorphism by defining a different implementation of a procedure or property with the same calling sequence<sup>1</sup></span></span>|  
|<span data-ttu-id="ba899-116">다시 정의 요소</span><span class="sxs-lookup"><span data-stu-id="ba899-116">Redefined element</span></span>|<span data-ttu-id="ba899-117">선언 된 모든 요소 형식</span><span class="sxs-lookup"><span data-stu-id="ba899-117">Any declared element type</span></span>|<span data-ttu-id="ba899-118">프로시저 ( `Function` , `Sub` 또는 `Operator` ) 또는 속성만</span><span class="sxs-lookup"><span data-stu-id="ba899-118">Only a procedure (`Function`, `Sub`, or `Operator`) or property</span></span>|  
|<span data-ttu-id="ba899-119">요소 재정의</span><span class="sxs-lookup"><span data-stu-id="ba899-119">Redefining element</span></span>|<span data-ttu-id="ba899-120">선언 된 모든 요소 형식</span><span class="sxs-lookup"><span data-stu-id="ba899-120">Any declared element type</span></span>|<span data-ttu-id="ba899-121">동일한 호출 시퀀스<sup>1</sup> 을 사용 하는 프로시저나 속성만</span><span class="sxs-lookup"><span data-stu-id="ba899-121">Only a procedure or property with the identical calling sequence<sup>1</sup></span></span>|  
|<span data-ttu-id="ba899-122">재정의 요소의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="ba899-122">Access level of redefining element</span></span>|<span data-ttu-id="ba899-123">모든 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="ba899-123">Any access level</span></span>|<span data-ttu-id="ba899-124">재정의 된 요소의 액세스 수준을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-124">Cannot change access level of overridden element</span></span>|  
|<span data-ttu-id="ba899-125">재정의 요소의 가독성 및 쓰기 가능성</span><span class="sxs-lookup"><span data-stu-id="ba899-125">Readability and writability of redefining element</span></span>|<span data-ttu-id="ba899-126">모든 조합</span><span class="sxs-lookup"><span data-stu-id="ba899-126">Any combination</span></span>|<span data-ttu-id="ba899-127">재정의 된 속성의 가독성 또는 쓰기 가능성를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-127">Cannot change readability or writability of overridden property</span></span>|  
|<span data-ttu-id="ba899-128">재정의를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-128">Control over redefining</span></span>|<span data-ttu-id="ba899-129">기본 클래스 요소는 숨김을 적용 하거나 금지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-129">Base class element cannot enforce or prohibit shadowing</span></span>|<span data-ttu-id="ba899-130">기본 클래스 요소는 `MustOverride` , `NotOverridable` 또는를 지정할 수 있습니다. `Overridable`</span><span class="sxs-lookup"><span data-stu-id="ba899-130">Base class element can specify `MustOverride`, `NotOverridable`, or `Overridable`</span></span>|  
|<span data-ttu-id="ba899-131">키워드 사용</span><span class="sxs-lookup"><span data-stu-id="ba899-131">Keyword usage</span></span>|<span data-ttu-id="ba899-132">`Shadows`파생 클래스에서 권장 됩니다. `Shadows`또는 지정 되지 않은 경우 `Shadows` `Overrides` <sup>두</sup> 가지 모두</span><span class="sxs-lookup"><span data-stu-id="ba899-132">`Shadows` recommended in derived class; `Shadows` assumed if neither `Shadows` nor `Overrides` specified<sup>2</sup></span></span>|<span data-ttu-id="ba899-133">`Overridable` 또는 `MustOverride` 기본 클래스에 필요 합니다 `Overrides` . 파생 클래스에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-133">`Overridable` or `MustOverride` required in base class; `Overrides` required in derived class</span></span>|  
|<span data-ttu-id="ba899-134">파생 클래스에서 파생 되는 클래스에의 한 재정의 요소 상속</span><span class="sxs-lookup"><span data-stu-id="ba899-134">Inheritance of redefining element by classes deriving from your derived class</span></span>|<span data-ttu-id="ba899-135">추가 파생 클래스에서 상속 되는 요소 숨김 숨겨진 요소는 계속 숨겨져 있습니다.<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ba899-135">Shadowing element inherited by further derived classes; shadowed element still hidden<sup>3</sup></span></span>|<span data-ttu-id="ba899-136">추가로 파생 된 클래스에서 상속 된 요소 재정의 재정의 된 요소가 계속 재정의 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-136">Overriding element inherited by further derived classes; overridden element still overridden</span></span>|  
  
 <span data-ttu-id="ba899-137"><sup>1</sup> *호출 시퀀스* 는 요소 형식 ( `Function` ,, `Sub` `Operator` 또는 `Property` ), 이름, 매개 변수 목록 및 반환 형식으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-137"><sup>1</sup> The *calling sequence* consists of the element type (`Function`, `Sub`, `Operator`, or `Property`), name, parameter list, and return type.</span></span> <span data-ttu-id="ba899-138">속성 또는 그 밖의 다른 방법으로는 프로시저를 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-138">You cannot override a procedure with a property, or the other way around.</span></span> <span data-ttu-id="ba899-139">한 종류의 프로시저 ( `Function` , `Sub` 또는 `Operator` )를 다른 종류의 프로시저로 재정의할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-139">You cannot override one kind of procedure (`Function`, `Sub`, or `Operator`) with another kind.</span></span>  
  
 <span data-ttu-id="ba899-140"><sup>2</sup> 또는 중 하나를 지정 하지 `Shadows` 않으면 `Overrides` 컴파일러에서 사용 하려는 재정의의 종류를 확인할 수 있도록 경고 메시지를 발행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-140"><sup>2</sup> If you do not specify either `Shadows` or `Overrides`, the compiler issues a warning message to help you be sure which kind of redefinition you want to use.</span></span> <span data-ttu-id="ba899-141">경고를 무시 하면 섀도잉 메커니즘이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-141">If you ignore the warning, the shadowing mechanism is used.</span></span>  
  
 <span data-ttu-id="ba899-142"><sup>3</sup> 추가 파생 클래스에서 섀도잉 요소에 액세스할 수 없는 경우 숨김은 상속 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-142"><sup>3</sup> If the shadowing element is inaccessible in a further derived class, shadowing is not inherited.</span></span> <span data-ttu-id="ba899-143">예를 들어, 섀도잉 요소를로 선언 하는 경우 `Private` 파생 클래스에서 파생 되는 클래스는 숨기는 요소가 아니라 원래 요소를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-143">For example, if you declare the shadowing element as `Private`, a class deriving from your derived class inherits the original element instead of the shadowing element.</span></span>  
  
## <a name="guidelines"></a><span data-ttu-id="ba899-144">지침</span><span class="sxs-lookup"><span data-stu-id="ba899-144">Guidelines</span></span>  

 <span data-ttu-id="ba899-145">일반적으로 다음과 같은 경우에 재정의를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-145">You normally use overriding in the following cases:</span></span>  
  
- <span data-ttu-id="ba899-146">다형 파생 클래스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-146">You are defining polymorphic derived classes.</span></span>  
  
- <span data-ttu-id="ba899-147">컴파일러가 동일한 요소 형식 및 호출 시퀀스를 강제 적용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-147">You want the safety of having the compiler enforce the identical element type and calling sequence.</span></span>  
  
 <span data-ttu-id="ba899-148">일반적으로 다음과 같은 경우에 섀도잉을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-148">You normally use shadowing in the following cases:</span></span>  
  
- <span data-ttu-id="ba899-149">기본 클래스를 수정 하 고 사용자와 동일한 이름을 사용 하 여 요소를 정의 하는 것이 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-149">You anticipate that your base class might be modified and define an element using the same name as yours.</span></span>  
  
- <span data-ttu-id="ba899-150">요소 형식 또는 호출 시퀀스를 자유롭게 변경 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba899-150">You want the freedom of changing the element type or calling sequence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba899-151">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ba899-151">See also</span></span>

- [<span data-ttu-id="ba899-152">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="ba899-152">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="ba899-153">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="ba899-153">Shadowing in Visual Basic</span></span>](shadowing.md)
- [<span data-ttu-id="ba899-154">방법: 사용자 변수와 이름이 같은 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="ba899-154">How to: Hide a Variable with the Same Name as Your Variable</span></span>](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="ba899-155">방법: 상속된 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="ba899-155">How to: Hide an Inherited Variable</span></span>](how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="ba899-156">방법: 파생 클래스에 의해 숨겨진 변수에 액세스</span><span class="sxs-lookup"><span data-stu-id="ba899-156">How to: Access a Variable Hidden by a Derived Class</span></span>](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="ba899-157">Overloads</span><span class="sxs-lookup"><span data-stu-id="ba899-157">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
- [<span data-ttu-id="ba899-158">재정의</span><span class="sxs-lookup"><span data-stu-id="ba899-158">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
