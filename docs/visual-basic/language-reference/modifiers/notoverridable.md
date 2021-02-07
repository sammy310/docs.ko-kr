---
description: '자세히 알아보기: NotOverridable (Visual Basic)'
title: NotOverridable
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
ms.openlocfilehash: f0363024aacc1ed6ab9d8820cc965b5b71e557b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666097"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="79a46-103">NotOverridable(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79a46-103">NotOverridable (Visual Basic)</span></span>

<span data-ttu-id="79a46-104">속성이 나 프로시저를 파생 클래스에서 재정의할 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79a46-104">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79a46-105">설명</span><span class="sxs-lookup"><span data-stu-id="79a46-105">Remarks</span></span>  

 <span data-ttu-id="79a46-106">`NotOverridable`한정자는 속성 또는 메서드가 파생 클래스에서 재정의 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="79a46-106">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="79a46-107">[재정의할](overridable.md) 수 있는 한정자를 사용 하면 클래스의 속성 또는 메서드가 파생 클래스에서 재정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79a46-107">The [Overridable](overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="79a46-108">자세한 내용은 [상속 기본 사항](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79a46-108">For more information, see [Inheritance Basics](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="79a46-109">`Overridable`또는 `NotOverridable` 한정자가 지정 되지 않은 경우 기본 설정은 속성이 나 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="79a46-109">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="79a46-110">속성 또는 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정은입니다 `Overridable` . 그렇지 않으면 `NotOverridable` 입니다.</span><span class="sxs-lookup"><span data-stu-id="79a46-110">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="79a46-111">재정의할 수 없는 요소를 *sealed* 요소 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="79a46-111">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="79a46-112">`NotOverridable`속성 또는 프로시저 선언 문에서만를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79a46-112">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="79a46-113">`NotOverridable`다른 속성 또는 프로시저를 재정의 하는 속성 또는 프로시저 (즉,와 함께 사용)만 지정할 수 있습니다 `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="79a46-113">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="79a46-114">결합 된 한정자</span><span class="sxs-lookup"><span data-stu-id="79a46-114">Combined Modifiers</span></span>  

 <span data-ttu-id="79a46-115">`Overridable`메서드에 대해 또는를 지정할 수 없습니다 `NotOverridable` `Private` .</span><span class="sxs-lookup"><span data-stu-id="79a46-115">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="79a46-116">`NotOverridable` `MustOverride` `Overridable` 동일한 선언에서, 또는를 함께 지정할 수 없습니다 `Shared` .</span><span class="sxs-lookup"><span data-stu-id="79a46-116">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="79a46-117">사용량</span><span class="sxs-lookup"><span data-stu-id="79a46-117">Usage</span></span>  

 <span data-ttu-id="79a46-118">`NotOverridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79a46-118">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="79a46-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="79a46-119">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="79a46-120">Property Statement</span><span class="sxs-lookup"><span data-stu-id="79a46-120">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="79a46-121">Sub 문</span><span class="sxs-lookup"><span data-stu-id="79a46-121">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="79a46-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79a46-122">See also</span></span>

- [<span data-ttu-id="79a46-123">한정자</span><span class="sxs-lookup"><span data-stu-id="79a46-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="79a46-124">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="79a46-124">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="79a46-125">New</span><span class="sxs-lookup"><span data-stu-id="79a46-125">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="79a46-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="79a46-126">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="79a46-127">재정의</span><span class="sxs-lookup"><span data-stu-id="79a46-127">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="79a46-128">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="79a46-128">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="79a46-129">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="79a46-129">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
