---
title: 생성자 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
ms.openlocfilehash: 823bc893c9384bb687e5f9a196abe497db14f4db
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709480"
---
# <a name="constructor-design"></a><span data-ttu-id="1c929-102">생성자 디자인</span><span class="sxs-lookup"><span data-stu-id="1c929-102">Constructor Design</span></span>

<span data-ttu-id="1c929-103">생성자에는 형식 생성자와 인스턴스 생성자의 두 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>

<span data-ttu-id="1c929-104">형식 생성자는 정적 이며 형식을 사용 하기 전에 CLR에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="1c929-105">인스턴스 생성자는 형식의 인스턴스를 만들 때 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-105">Instance constructors run when an instance of a type is created.</span></span>

<span data-ttu-id="1c929-106">형식 생성자는 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="1c929-107">인스턴스 생성자는 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-107">Instance constructors can.</span></span> <span data-ttu-id="1c929-108">매개 변수를 사용 하지 않는 인스턴스 생성자를 종종 매개 변수가 없는 생성자 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>

<span data-ttu-id="1c929-109">생성자는 형식의 인스턴스를 만드는 가장 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="1c929-110">대부분의 개발자는 인스턴스를 만드는 다른 방법 (예: 팩터리 메서드)을 고려 하기 전에 생성자를 검색 하 고 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>

<span data-ttu-id="1c929-111">**✓ CONSIDER** 단순, 이상적으로 기본적으로 생성자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>

<span data-ttu-id="1c929-112">간단한 생성자에는 매우 적은 수의 매개 변수가 있고 모든 매개 변수는 기본 형식 또는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="1c929-113">이러한 간단한 생성자는 프레임 워크의 유용성을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-113">Such simple constructors increase usability of the framework.</span></span>

<span data-ttu-id="1c929-114">**✓ CONSIDER** 원하는 작업의 의미 체계의 새 인스턴스를 생성에 직접 매핑되지 않는 경우 또는 비 자연 느낌 생성자 설계 지침을 따르는 경우 생성자를 대신 정적 팩터리 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>

<span data-ttu-id="1c929-115">**✓ DO** 가기로 생성자 매개 변수를 사용 하 여 기본 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>

<span data-ttu-id="1c929-116">빈 생성자와 몇 가지 속성 집합을 사용 하 고 여러 인수를 사용 하는 생성자를 사용 하는 경우에는 의미 체계가 차이가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>

<span data-ttu-id="1c929-117">**✓ DO** 생성자 매개 변수는 단순히 속성을 설정 하는 데 사용 되는 경우 생성자 매개 변수 및 속성에 대 한 동일한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>

<span data-ttu-id="1c929-118">이러한 매개 변수와 속성의 유일한 차이점은 대/소문자를 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-118">The only difference between such parameters and the properties should be casing.</span></span>

<span data-ttu-id="1c929-119">**✓ DO** 생성자에서 최소한의 작업만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-119">**✓ DO** minimal work in the constructor.</span></span>

<span data-ttu-id="1c929-120">생성자는 생성자 매개 변수를 캡처하는 것 보다 많은 작업을 수행 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="1c929-121">다른 처리 비용은 필요할 때까지 지연 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-121">The cost of any other processing should be delayed until required.</span></span>

<span data-ttu-id="1c929-122">**✓ DO** 해당 되는 경우에 인스턴스 생성자에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>

<span data-ttu-id="1c929-123">이러한 생성자가 필요한 경우 **✓** 은 클래스에서 매개 변수가 없는 public 생성자를 명시적으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-123">**✓ DO** explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>

<span data-ttu-id="1c929-124">형식에 대 한 생성자를 명시적으로 선언 하지 않으면와 C#같은 많은 언어에서 매개 변수가 없는 public 생성자가 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="1c929-125">추상 클래스는 보호 된 생성자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-125">(Abstract classes get a protected constructor.)</span></span>

<span data-ttu-id="1c929-126">매개 변수가 있는 생성자를 클래스에 추가 하면 컴파일러가 매개 변수가 없는 생성자를 추가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="1c929-127">이로 인해 실수로 인 한 변경 사항이 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-127">This often causes accidental breaking changes.</span></span>

<span data-ttu-id="1c929-128">X 구조체에서 매개 변수가 없는 생성자를 명시적으로 정의 **하지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="1c929-128">**X AVOID** explicitly defining parameterless constructors on structs.</span></span>

<span data-ttu-id="1c929-129">이렇게 하면 매개 변수가 없는 생성자가 정의 되지 않은 경우 배열의 모든 슬롯에서 실행할 필요가 없기 때문에 배열을 더 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="1c929-130">를 비롯 C#한 대부분의 컴파일러에서는 이러한 이유로 구조체에 매개 변수가 없는 생성자를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>

<span data-ttu-id="1c929-131">**X AVOID** 개체의 생성자 내에서 가상 멤버를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>

<span data-ttu-id="1c929-132">가장 많이 파생 된 형식의 생성자가 아직 완전히 실행 되지 않은 경우에도 가상 멤버를 호출 하면 가장 많이 파생 된 재정의가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>

## <a name="type-constructor-guidelines"></a><span data-ttu-id="1c929-133">형식 생성자 지침</span><span class="sxs-lookup"><span data-stu-id="1c929-133">Type Constructor Guidelines</span></span>

<span data-ttu-id="1c929-134">**✓ DO** 정적 생성자를 private입니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-134">**✓ DO** make static constructors private.</span></span>

<span data-ttu-id="1c929-135">클래스 생성자 라고도 하는 정적 생성자는 형식을 초기화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="1c929-136">CLR에서는 형식의 첫 번째 인스턴스가 만들어지거나 해당 형식의 정적 멤버가 호출 되기 전에 정적 생성자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="1c929-137">사용자는 정적 생성자가 호출 되는 시기를 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="1c929-138">Static 생성자가 private이 아니면 CLR 이외의 코드에서 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="1c929-139">생성자에서 수행 되는 작업에 따라 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="1c929-140">컴파일러 C# 는 정적 생성자를 private로 강제로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-140">The C# compiler forces static constructors to be private.</span></span>

<span data-ttu-id="1c929-141">**X DO NOT** 정적 생성자에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-141">**X DO NOT** throw exceptions from static constructors.</span></span>

<span data-ttu-id="1c929-142">형식 생성자에서 예외가 throw 되는 경우 현재 응용 프로그램 도메인에서 형식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>

<span data-ttu-id="1c929-143">**✓ CONSIDER** 런타임 형식에서 명시적으로 정의 된 정적 생성자를 갖지 않는의 성능을 최적화할 수 있기 때문에 정적 생성자를 사용 하 여 명시적으로 보다는 정적 필드 인라인을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>

<span data-ttu-id="1c929-144">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="1c929-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="1c929-145">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="1c929-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="1c929-146">참조</span><span class="sxs-lookup"><span data-stu-id="1c929-146">See also</span></span>

- [<span data-ttu-id="1c929-147">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="1c929-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="1c929-148">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="1c929-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
