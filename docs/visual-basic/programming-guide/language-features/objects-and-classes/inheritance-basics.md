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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350827"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="78fa6-102">상속 기본 사항(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78fa6-102">Inheritance Basics (Visual Basic)</span></span>

<span data-ttu-id="78fa6-103">`Inherits` 문은 *기본 클래스*라고 하는 기존 클래스를 기반으로 *파생 클래스*라고 하는 새 클래스를 선언 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="78fa6-104">파생 클래스는 기본 클래스에 정의 된 속성, 메서드, 이벤트, 필드 및 상수를 상속 하 고 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="78fa6-105">다음 섹션에서는 상속에 대 한 몇 가지 규칙과 클래스가 상속 되거나 상속 되는 방식을 변경 하는 데 사용할 수 있는 한정자에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>

- <span data-ttu-id="78fa6-106">기본적으로 `NotInheritable` 키워드로 표시 되지 않은 경우 모든 클래스를 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="78fa6-107">클래스는 프로젝트의 다른 클래스나 프로젝트에서 참조 하는 다른 어셈블리의 클래스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>

- <span data-ttu-id="78fa6-108">다중 상속을 허용 하는 언어와 달리 Visual Basic에서는 클래스에서 단일 상속만 허용 합니다. 즉, 파생 클래스에는 하나의 기본 클래스만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="78fa6-109">클래스에서는 여러 상속이 허용 되지 않지만 클래스는 여러 인터페이스를 구현 하 여 동일한 종료를 효과적으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>

- <span data-ttu-id="78fa6-110">기본 클래스에서 제한 된 항목을 노출 하지 않도록 하려면 파생 클래스의 액세스 형식이 기본 클래스 보다 더 제한적 이거나 더 제한적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="78fa6-111">예를 들어 `Public` 클래스는 `Friend` 또는 `Private` 클래스를 상속할 수 없으며 `Friend` 클래스는 `Private` 클래스를 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>

## <a name="inheritance-modifiers"></a><span data-ttu-id="78fa6-112">상속 한정자</span><span class="sxs-lookup"><span data-stu-id="78fa6-112">Inheritance Modifiers</span></span>

<span data-ttu-id="78fa6-113">Visual Basic는 다음과 같은 클래스 수준 문과 한정자를 도입 하 여 상속을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>

- <span data-ttu-id="78fa6-114">`Inherits` statement-기본 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-114">`Inherits` statement — Specifies the base class.</span></span>

- <span data-ttu-id="78fa6-115">`NotInheritable` 한정자-프로그래머가 클래스를 기본 클래스로 사용할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>

- <span data-ttu-id="78fa6-116">`MustInherit` 한정자-클래스를 기본 클래스로만 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="78fa6-117">`MustInherit` 클래스의 인스턴스를 직접 만들 수 없습니다. 파생 클래스의 기본 클래스 인스턴스로만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="78fa6-118">C++ 및 C#등의 다른 프로그래밍 언어에서는 *추상 클래스* 라는 용어를 사용 하 여 이러한 클래스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>

## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="78fa6-119">파생 클래스의 속성 및 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="78fa6-119">Overriding Properties and Methods in Derived Classes</span></span>

<span data-ttu-id="78fa6-120">기본적으로 파생 클래스는 기본 클래스의 속성 및 메서드를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="78fa6-121">상속 된 속성 또는 메서드가 파생 클래스에서 다르게 동작 해야 하는 경우 *재정의할*수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="78fa6-122">즉, 파생 클래스에서 메서드의 새 구현을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="78fa6-123">다음 한정자는 속성 및 메서드가 재정의되는 방식을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-123">The following modifiers are used to control how properties and methods are overridden:</span></span>

- <span data-ttu-id="78fa6-124">`Overridable`-클래스의 속성 또는 메서드가 파생 클래스에서 재정의 될 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>

- <span data-ttu-id="78fa6-125">`Overrides`-기본 클래스에 정의 된 `Overridable` 속성 또는 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>

- <span data-ttu-id="78fa6-126">`NotOverridable`-상속 하는 클래스에서 속성 또는 메서드가 재정의 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="78fa6-127">기본적으로 `Public` 메서드는 `NotOverridable`됩니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-127">By default, `Public` methods are `NotOverridable`.</span></span>

- <span data-ttu-id="78fa6-128">`MustOverride`-파생 클래스가 속성 또는 메서드를 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="78fa6-129">`MustOverride` 키워드를 사용 하는 경우 메서드 정의는 `Sub`, `Function`또는 `Property` 문으로만 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="78fa6-130">다른 문은 허용 되지 않으며 특히 `End Sub` 또는 `End Function` 문이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="78fa6-131">`MustOverride` 메서드는 `MustInherit` 클래스에서 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>

<span data-ttu-id="78fa6-132">급여를 처리 하는 클래스를 정의 하려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="78fa6-133">일반적인 주에 대 한 급여를 계산 하는 `RunPayroll` 메서드를 포함 하는 제네릭 `Payroll` 클래스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="78fa6-134">그런 다음 `Payroll`를 보다 특수화 된 `BonusPayroll` 클래스의 기본 클래스로 사용할 수 있습니다 .이 클래스는 직원 보너스를 분산 하는 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>

<span data-ttu-id="78fa6-135">`BonusPayroll` 클래스는 기본 `Payroll` 클래스에 정의 된 `PayEmployee` 메서드를 상속 하 고 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>

<span data-ttu-id="78fa6-136">다음 예제에서는 기본 클래스 `Payroll,` 및 파생 클래스 `BonusPayroll`를 정의 합니다 .이 클래스는 상속 된 메서드 `PayEmployee`를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="78fa6-137">`RunPayroll`프로시저는 `Payroll` 개체와 `BonusPayroll` 개체를 만들어 두 개체의 `PayEmployee` 메서드를 실행 하는 함수 `Pay`에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a><span data-ttu-id="78fa6-138">MyBase 키워드</span><span class="sxs-lookup"><span data-stu-id="78fa6-138">The MyBase Keyword</span></span>

<span data-ttu-id="78fa6-139">`MyBase` 키워드는 클래스의 현재 인스턴스에 대 한 기본 클래스를 참조 하는 개체 변수 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="78fa6-140">`MyBase`은 파생 클래스에서 재정의 되거나 숨겨진 기본 클래스 멤버에 액세스 하는 데 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="78fa6-141">특히 파생 클래스 생성자에서 기본 클래스 생성자를 명시적으로 호출 하는 데 `MyBase.New`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>

<span data-ttu-id="78fa6-142">예를 들어 기본 클래스에서 상속 된 메서드를 재정의 하는 파생 클래스를 디자인 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="78fa6-143">재정의 된 메서드는 기본 클래스의 메서드를 호출 하 고 다음 코드 조각과 같이 반환 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

<span data-ttu-id="78fa6-144">다음 목록에서는 `MyBase`사용에 대 한 제한 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-144">The following list describes restrictions on using `MyBase`:</span></span>

- <span data-ttu-id="78fa6-145">`MyBase`는 직계 기본 클래스 및 상속 된 멤버를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="78fa6-146">클래스의 `Private` 멤버에 액세스 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-146">It cannot be used to access `Private` members in the class.</span></span>

- <span data-ttu-id="78fa6-147">`MyBase`은 실제 개체가 아닌 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="78fa6-148">`MyBase`를 변수에 할당 하거나 프로시저에 전달 하거나 `Is` 비교에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="78fa6-149">`MyBase` 하는 메서드는 직접 실행 기본 클래스에서 정의 하지 않아도 됩니다. 대신 간접적으로 상속 된 기본 클래스에서 정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="78fa6-150">`MyBase`으로 정규화 된 참조가 올바르게 컴파일되도록 하려면 일부 기본 클래스에는 호출에 표시 되는 매개 변수의 이름과 형식과 일치 하는 메서드가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>

- <span data-ttu-id="78fa6-151">`MyBase`를 사용 하 여 `MustOverride` 기본 클래스 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>

- <span data-ttu-id="78fa6-152">`MyBase`은 자신을 정규화 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="78fa6-153">따라서 다음 코드는 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-153">Therefore, the following code is not valid:</span></span>

  `MyBase.MyBase.BtnOK_Click()`

- <span data-ttu-id="78fa6-154">`MyBase`는 모듈에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-154">`MyBase` cannot be used in modules.</span></span>

- <span data-ttu-id="78fa6-155">기본 클래스가 다른 어셈블리에 있는 경우 `MyBase`를 사용 하 여 `Friend`으로 표시 된 기본 클래스 멤버에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>

<span data-ttu-id="78fa6-156">자세한 내용 및 다른 예제 [는 방법: 파생 클래스에 의해 숨겨진 변수에 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78fa6-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>

## <a name="the-myclass-keyword"></a><span data-ttu-id="78fa6-157">MyClass 키워드</span><span class="sxs-lookup"><span data-stu-id="78fa6-157">The MyClass Keyword</span></span>

<span data-ttu-id="78fa6-158">`MyClass` 키워드는 원래 구현 된 클래스의 현재 인스턴스를 참조 하는 개체 변수 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="78fa6-159">`MyClass` `Me`와 유사 하지만 `MyClass`의 모든 메서드 및 속성 호출은 메서드 또는 속성이 [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)된 것 처럼 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="78fa6-160">따라서 메서드 또는 속성은 파생 클래스에서 재정의 하는 경우에는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>

- <span data-ttu-id="78fa6-161">`MyClass`은 실제 개체가 아닌 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="78fa6-162">`MyClass`를 변수에 할당 하거나 프로시저에 전달 하거나 `Is` 비교에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="78fa6-163">`MyClass`는 포함 하는 클래스 및 상속 된 멤버를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-163">`MyClass` refers to the containing class and its inherited members.</span></span>

- <span data-ttu-id="78fa6-164">`MyClass` `Shared` 멤버의 한정자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>

- <span data-ttu-id="78fa6-165">`MyClass`은 `Shared` 메서드 내에서 사용할 수 없지만 인스턴스 메서드 내에서 사용 하 여 클래스의 공유 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>

- <span data-ttu-id="78fa6-166">`MyClass` 표준 모듈에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-166">`MyClass` cannot be used in standard modules.</span></span>

- <span data-ttu-id="78fa6-167">`MyClass`를 사용 하 여 기본 클래스에 정의 된 메서드를 정규화 하 고 해당 클래스에서 제공 된 메서드를 구현 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="78fa6-168">이러한 참조는 `MyBase.`*메서드와*동일한 의미를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>

<span data-ttu-id="78fa6-169">다음 예에서는 `Me`와 `MyClass`를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-169">The following example compares `Me` and `MyClass`.</span></span>

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

<span data-ttu-id="78fa6-170">`derivedClass`에서 `testMethod`를 재정의 하더라도 `useMyClass`의 `MyClass` 키워드는 재정의 효과를 nullifies 컴파일러는 `testMethod`의 기본 클래스 버전에 대 한 호출을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fa6-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>

## <a name="see-also"></a><span data-ttu-id="78fa6-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78fa6-171">See also</span></span>

- [<span data-ttu-id="78fa6-172">Inherits 문</span><span class="sxs-lookup"><span data-stu-id="78fa6-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="78fa6-173">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="78fa6-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
