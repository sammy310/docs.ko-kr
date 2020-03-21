---
title: 상속 기본 사항
ms.date: 07/20/2015
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
ms.openlocfilehash: 89fcf2a14d8938d536aa72628218242811baa1a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401462"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="7a695-102">상속 기본 사항(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a695-102">Inheritance Basics (Visual Basic)</span></span>

<span data-ttu-id="7a695-103">문은 `Inherits` *기본*클래스라고 하는 기존 클래스를 기반으로 *파생 클래스라고*하는 새 클래스를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="7a695-104">파생 클래스는 기본 클래스에 정의된 속성, 메서드, 이벤트, 필드 및 상수를 상속하고 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="7a695-105">다음 섹션에서는 상속에 대한 몇 가지 규칙과 클래스가 상속되거나 상속되는 방식을 변경하는 데 사용할 수 있는 수정자를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>

- <span data-ttu-id="7a695-106">기본적으로 키워드로 표시되지 않는 한 모든 `NotInheritable` 클래스를 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="7a695-107">클래스는 프로젝트의 다른 클래스 또는 프로젝트에서 참조하는 다른 어셈블리의 클래스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>

- <span data-ttu-id="7a695-108">여러 상속을 허용하는 언어와 달리 Visual Basic은 클래스에서 단일 상속만 허용합니다. 즉, 파생 클래스에는 하나의 기본 클래스만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="7a695-109">클래스에서는 여러 상속이 허용되지 않지만 클래스는 동일한 끝을 효과적으로 수행할 수 있는 여러 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>

- <span data-ttu-id="7a695-110">기본 클래스에서 제한된 항목이 노출되지 않도록 하려면 파생 클래스의 액세스 형식이 기본 클래스와 같거나 더 제한적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="7a695-111">예를 들어 `Public` 클래스는 a `Friend` 또는 `Private` 클래스를 `Friend` 상속할 수 `Private` 없으며 클래스는 클래스를 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>

## <a name="inheritance-modifiers"></a><span data-ttu-id="7a695-112">상속 수정자</span><span class="sxs-lookup"><span data-stu-id="7a695-112">Inheritance Modifiers</span></span>

<span data-ttu-id="7a695-113">Visual Basic은 상속을 지원하기 위해 다음 클래스 수준 문 및 수정자를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>

- <span data-ttu-id="7a695-114">`Inherits`문 — 기본 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-114">`Inherits` statement — Specifies the base class.</span></span>

- <span data-ttu-id="7a695-115">`NotInheritable`수정자 - 프로그래머가 클래스를 기본 클래스로 사용하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>

- <span data-ttu-id="7a695-116">`MustInherit`수정자 - 클래스가 기본 클래스로만 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="7a695-117">클래스의 `MustInherit` 인스턴스를 직접 만들 수 없습니다. 파생 클래스의 기본 클래스 인스턴스로만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="7a695-118">C++ 및 C#과 같은 다른 프로그래밍 언어는 *추상 클래스라는* 용어를 사용하여 이러한 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>

## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="7a695-119">파생 클래스에서 속성 및 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="7a695-119">Overriding Properties and Methods in Derived Classes</span></span>

<span data-ttu-id="7a695-120">기본적으로 파생 된 클래스는 기본 클래스에서 속성 및 메서드를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="7a695-121">상속된 속성 또는 메서드파생 클래스에서 다르게 작동 해야 하는 경우 *재정의할*수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="7a695-122">즉, 파생 클래스에서 메서드의 새 구현을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="7a695-123">다음 한정자는 속성 및 메서드가 재정의되는 방식을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-123">The following modifiers are used to control how properties and methods are overridden:</span></span>

- <span data-ttu-id="7a695-124">`Overridable`— 파생 클래스에서 클래스의 속성 또는 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>

- <span data-ttu-id="7a695-125">`Overrides`— 기본 `Overridable` 클래스에 정의된 속성 또는 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>

- <span data-ttu-id="7a695-126">`NotOverridable`— 상속 클래스에서 속성 또는 메서드가 재정의되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="7a695-127">기본적으로 `Public` 메서드는 `NotOverridable`는 .</span><span class="sxs-lookup"><span data-stu-id="7a695-127">By default, `Public` methods are `NotOverridable`.</span></span>

- <span data-ttu-id="7a695-128">`MustOverride`— 파생 클래스가 속성 또는 메서드를 재정의하도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="7a695-129">키워드를 `MustOverride` 사용하는 경우 메서드 정의는 `Sub`" `Function`또는 `Property` 문으로만 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="7a695-130">다른 문은 허용되지 않으며 구체적으로 는 `End Sub` `End Function` 또는 문이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="7a695-131">`MustOverride`메서드를 클래스에서 `MustInherit` 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>

<span data-ttu-id="7a695-132">급여를 처리할 클래스를 정의한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="7a695-133">일반적인 주에 대한 `Payroll` 급여를 계산하는 메서드가 `RunPayroll` 포함된 일반 클래스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="7a695-134">그런 다음 `Payroll` 직원 보너스를 배포할 `BonusPayroll` 때 사용할 수 있는 보다 전문적인 클래스의 기본 클래스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>

<span data-ttu-id="7a695-135">클래스는 `BonusPayroll` 기본 `PayEmployee` `Payroll` 클래스에 정의된 메서드를 상속하고 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>

<span data-ttu-id="7a695-136">다음 예제에서는 상속된 메서드를 재정의하는 기본 `Payroll,` 클래스와 파생 `BonusPayroll`클래스를 `PayEmployee`정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="7a695-137">프로시저를 `RunPayroll`만들고 `Payroll` 개체와 개체를 `BonusPayroll` 함수에 `Pay`전달하여 두 개체의 `PayEmployee` 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a><span data-ttu-id="7a695-138">마이베이스 키워드</span><span class="sxs-lookup"><span data-stu-id="7a695-138">The MyBase Keyword</span></span>

<span data-ttu-id="7a695-139">키워드는 `MyBase` 클래스의 현재 인스턴스의 기본 클래스를 참조 하는 개체 변수처럼 행동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="7a695-140">`MyBase`파생 클래스에서 재정의되거나 그림자가 있는 기본 클래스 멤버에 액세스하는 데 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="7a695-141">특히 `MyBase.New` 파생 된 클래스 생성자에서 base 클래스 생성자 명시적으로 호출 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>

<span data-ttu-id="7a695-142">예를 들어 기본 클래스에서 상속된 메서드를 재정의하는 파생 클래스를 디자인한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="7a695-143">재정의된 메서드는 기본 클래스의 메서드를 호출하고 다음 코드 조각에 표시된 대로 반환 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

<span data-ttu-id="7a695-144">다음 목록에서는 다음 사용에 `MyBase`대한 제한 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-144">The following list describes restrictions on using `MyBase`:</span></span>

- <span data-ttu-id="7a695-145">`MyBase`는 즉시 기본 클래스와 상속된 멤버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="7a695-146">클래스의 멤버에 `Private` 액세스하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-146">It cannot be used to access `Private` members in the class.</span></span>

- <span data-ttu-id="7a695-147">`MyBase`는 실제 개체가 아닌 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="7a695-148">`MyBase`변수에 할당하거나 프로시저에 전달하거나 비교에 `Is` 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="7a695-149">`MyBase` 자격을 갖춘 메서드는 즉시 기본 클래스에 정의할 필요가 없습니다. 대신 간접적으로 상속된 기본 클래스에서 정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="7a695-150">올바르게 컴파일하여 `MyBase` 정규화된 참조를 사용하려면 일부 기본 클래스에는 호출에 나타나는 매개 변수의 이름과 형식과 일치하는 메서드가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>

- <span data-ttu-id="7a695-151">기본 클래스 `MyBase` 메서드를 호출하는 `MustOverride` 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>

- <span data-ttu-id="7a695-152">`MyBase`자격을 갖추는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="7a695-153">따라서 다음 코드는 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-153">Therefore, the following code is not valid:</span></span>

  `MyBase.MyBase.BtnOK_Click()`

- <span data-ttu-id="7a695-154">`MyBase`모듈에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-154">`MyBase` cannot be used in modules.</span></span>

- <span data-ttu-id="7a695-155">`MyBase`기본 클래스가 다른 어셈블리에 `Friend` 있는 것처럼 표시된 기본 클래스 멤버에 액세스하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>

<span data-ttu-id="7a695-156">자세한 정보 및 다른 예제는 [파생 클래스에 의해 숨겨진 변수에 액세스하는 방법을](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a695-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>

## <a name="the-myclass-keyword"></a><span data-ttu-id="7a695-157">마이클래스 키워드</span><span class="sxs-lookup"><span data-stu-id="7a695-157">The MyClass Keyword</span></span>

<span data-ttu-id="7a695-158">키워드는 `MyClass` 원래 구현된 클래스의 현재 인스턴스를 참조하는 개체 변수처럼 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="7a695-159">`MyClass`유사하지만 `Me`모든 메서드 및 속성 `MyClass` 호출은 메서드 또는 속성이 [초과 ridable이 아닌](../../../../visual-basic/language-reference/modifiers/notoverridable.md)것처럼 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="7a695-160">따라서 메서드 또는 속성파생 클래스에서 재정의의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>

- <span data-ttu-id="7a695-161">`MyClass`는 실제 개체가 아닌 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="7a695-162">`MyClass`변수에 할당하거나 프로시저에 전달하거나 비교에 `Is` 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="7a695-163">`MyClass`은 포함 클래스와 해당 상속된 멤버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-163">`MyClass` refers to the containing class and its inherited members.</span></span>

- <span data-ttu-id="7a695-164">`MyClass`멤버에 대한 `Shared` 한정자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>

- <span data-ttu-id="7a695-165">`MyClass``Shared` 메서드 내에서 사용할 수는 없지만 인스턴스 메서드 내에서 클래스의 공유 멤버에 액세스하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>

- <span data-ttu-id="7a695-166">`MyClass`표준 모듈에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-166">`MyClass` cannot be used in standard modules.</span></span>

- <span data-ttu-id="7a695-167">`MyClass`기본 클래스에 정의되고 해당 클래스에 제공된 메서드의 구현이 없는 메서드를 한정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="7a695-168">이러한 참조는 `MyBase.` *Method*와 동일한 의미를 가합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>

<span data-ttu-id="7a695-169">다음 예제는 `Me` 비교 `MyClass`및 .</span><span class="sxs-lookup"><span data-stu-id="7a695-169">The following example compares `Me` and `MyClass`.</span></span>

```vb
Class baseClass
    Public Overridable Sub testMethod()
        MsgBox("Base class string")
    End Sub
    Public Sub useMe()
        ' The following call uses the calling class's method, even if
        ' that method is an override.
        Me.testMethod()
    End Sub
    Public Sub useMyClass()
        ' The following call uses this instance's method and not any
        ' override.
        MyClass.testMethod()
    End Sub
End Class
Class derivedClass : Inherits baseClass
    Public Overrides Sub testMethod()
        MsgBox("Derived class string")
    End Sub
End Class
Class testClasses
    Sub startHere()
        Dim testObj As derivedClass = New derivedClass()
        ' The following call displays "Derived class string".
        testObj.useMe()
        ' The following call displays "Base class string".
        testObj.useMyClass()
    End Sub
End Class
```

<span data-ttu-id="7a695-170">재정의하더라도 `derivedClass` `testMethod`키워드는 `MyClass` `useMyClass` 재정의의 효과를 무효화하고 컴파일러는 `testMethod`의 기본 클래스 버전에 대한 호출을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="7a695-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a695-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a695-171">See also</span></span>

- [<span data-ttu-id="7a695-172">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="7a695-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="7a695-173">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="7a695-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
