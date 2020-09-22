---
title: MustInherit
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 6502da947ae331a26e66d8ce2dbcda46e4172a6e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867958"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="fd3f3-102">MustInherit(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd3f3-102">MustInherit (Visual Basic)</span></span>

<span data-ttu-id="fd3f3-103">클래스를 기본 클래스로만 사용할 수 있고이 클래스에서 직접 개체를 만들 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd3f3-104">설명</span><span class="sxs-lookup"><span data-stu-id="fd3f3-104">Remarks</span></span>  

 <span data-ttu-id="fd3f3-105">*기본 클래스* ( *추상 클래스*라고도 함)의 목적은 클래스에서 파생 되는 모든 클래스에 공통적인 기능을 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="fd3f3-106">이렇게 하면 파생 클래스가 공통 요소를 다시 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="fd3f3-107">경우에 따라이 일반적인 기능은 사용 가능한 개체를 만들기에 충분 하지 않으며 각 파생 클래스는 누락 된 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="fd3f3-108">이러한 경우에는 사용 하는 코드가 파생 된 클래스 에서만 개체를 만들도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="fd3f3-109">`MustInherit`기본 클래스에서를 사용 하 여이를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="fd3f3-110">클래스의 또 다른 용도 `MustInherit` 는 변수를 관련 클래스 집합으로 제한 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="fd3f3-111">기본 클래스를 정의 하 고이 클래스에서 이러한 관련 클래스를 모두 파생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="fd3f3-112">기본 클래스는 모든 파생 클래스에 공통적인 기능을 제공 하지 않아도 되지만 변수에 값을 할당 하는 필터 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="fd3f3-113">소비 하는 코드에서 변수를 기본 클래스로 선언 하는 경우 Visual Basic를 사용 하 여 파생 클래스 중 하나의 개체만 해당 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="fd3f3-114">.NET Framework는, 및 중에서 여러 클래스를 정의 합니다 `MustInherit` <xref:System.Array> <xref:System.Enum> <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="fd3f3-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="fd3f3-115"><xref:System.ValueType> 는 변수를 제한 하는 기본 클래스의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="fd3f3-116">모든 값 형식은에서 파생 <xref:System.ValueType> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="fd3f3-117">변수를로 선언 하는 경우에 <xref:System.ValueType> 는 값 형식만 해당 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="fd3f3-118">규칙</span><span class="sxs-lookup"><span data-stu-id="fd3f3-118">Rules</span></span>  
  
- <span data-ttu-id="fd3f3-119">**선언 컨텍스트.**</span><span class="sxs-lookup"><span data-stu-id="fd3f3-119">**Declaration Context.**</span></span> <span data-ttu-id="fd3f3-120">문에서만를 사용할 수 있습니다 `MustInherit` `Class` .</span><span class="sxs-lookup"><span data-stu-id="fd3f3-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
- <span data-ttu-id="fd3f3-121">**결합된 한정자.**</span><span class="sxs-lookup"><span data-stu-id="fd3f3-121">**Combined Modifiers.**</span></span> <span data-ttu-id="fd3f3-122">`MustInherit`을 동일한 선언에 함께 지정할 수 없습니다 `NotInheritable` .</span><span class="sxs-lookup"><span data-stu-id="fd3f3-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd3f3-123">예제</span><span class="sxs-lookup"><span data-stu-id="fd3f3-123">Example</span></span>  

 <span data-ttu-id="fd3f3-124">다음 예제에서는 강제 상속과 강제 재정의를 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="fd3f3-125">기본 클래스는 `shape` 변수를 정의 합니다 `acrossLine` .</span><span class="sxs-lookup"><span data-stu-id="fd3f3-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="fd3f3-126">및 클래스 `circle` 는 `square` 에서 파생 `shape` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="fd3f3-127">의 정의를 상속 `acrossLine` 하지만 `area` 각 종류의 셰이프에 대해 계산이 다르므로 함수를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="fd3f3-128">`shape1`및 `shape2` 를 형식으로 선언할 수 있습니다 `shape` .</span><span class="sxs-lookup"><span data-stu-id="fd3f3-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="fd3f3-129">그러나에서 개체를 만들 수 없습니다 `shape` .이는 함수 기능이 `area` 없고로 표시 되어 있기 때문입니다 `MustInherit` .</span><span class="sxs-lookup"><span data-stu-id="fd3f3-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="fd3f3-130">로 선언 되기 때문에 `shape` 및 변수는 `shape1` `shape2` 파생 된 클래스 및의 개체로 제한 됩니다 `circle` `square` .</span><span class="sxs-lookup"><span data-stu-id="fd3f3-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="fd3f3-131">Visual Basic를 사용 하 여 이러한 변수에 다른 개체를 할당할 수 없으며,이는 높은 수준의 형식 안전성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="fd3f3-132">사용량</span><span class="sxs-lookup"><span data-stu-id="fd3f3-132">Usage</span></span>  

 <span data-ttu-id="fd3f3-133">`MustInherit`이 컨텍스트에서는 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3f3-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="fd3f3-134">Class 문</span><span class="sxs-lookup"><span data-stu-id="fd3f3-134">Class Statement</span></span>](../statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="fd3f3-135">참조</span><span class="sxs-lookup"><span data-stu-id="fd3f3-135">See also</span></span>

- [<span data-ttu-id="fd3f3-136">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="fd3f3-136">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="fd3f3-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="fd3f3-137">NotInheritable</span></span>](notinheritable.md)
- [<span data-ttu-id="fd3f3-138">키워드</span><span class="sxs-lookup"><span data-stu-id="fd3f3-138">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="fd3f3-139">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="fd3f3-139">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
