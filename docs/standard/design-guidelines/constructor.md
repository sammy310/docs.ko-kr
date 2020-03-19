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
ms.openlocfilehash: 7ab795cd4c6e0ff5e1451c05987848c41bd69577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401246"
---
# <a name="constructor-design"></a><span data-ttu-id="5e318-102">생성자 디자인</span><span class="sxs-lookup"><span data-stu-id="5e318-102">Constructor Design</span></span>

<span data-ttu-id="5e318-103">생성자는 형식 생성자와 인스턴스 생성자의 두 가지 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>

<span data-ttu-id="5e318-104">형식 생성자는 정적이며 형식을 사용하기 전에 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="5e318-105">인스턴스 생성자는 형식의 인스턴스가 만들어질 때 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-105">Instance constructors run when an instance of a type is created.</span></span>

<span data-ttu-id="5e318-106">형식 생성자는 매개 변수를 취할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="5e318-107">인스턴스 생성자는 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-107">Instance constructors can.</span></span> <span data-ttu-id="5e318-108">매개 변수를 수행하지 않는 인스턴스 생성자는 매개 변수 없는 생성자라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>

<span data-ttu-id="5e318-109">생성자는 형식의 인스턴스를 만드는 가장 자연스러운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="5e318-110">대부분의 개발자는 인스턴스를 만드는 다른 방법(예: 팩터리 메서드)을 고려하기 전에 생성기를 검색하고 사용하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>

<span data-ttu-id="5e318-111">✔️ 간단하고 이상적으로 기본 생성자 제공을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="5e318-111">✔️ CONSIDER providing simple, ideally default, constructors.</span></span>

<span data-ttu-id="5e318-112">간단한 생성자는 매우 적은 수의 매개 변수를 가지며 모든 매개 변수는 기본 또는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="5e318-113">이러한 간단한 생성자는 프레임워크의 유용성을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-113">Such simple constructors increase usability of the framework.</span></span>

<span data-ttu-id="5e318-114">✔️ 원하는 작업의 의미 체계가 새 인스턴스의 구성에 직접 매핑되지 않거나 생성자 설계 지침을 따르는 경우 생성자 대신 정적 팩터리 메서드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-114">✔️ CONSIDER using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>

<span data-ttu-id="5e318-115">✔️ do는 생성자 매개 변수를 기본 속성을 설정하기 위한 바로 가프로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-115">✔️ DO use constructor parameters as shortcuts for setting main properties.</span></span>

<span data-ttu-id="5e318-116">빈 생성자 뒤에 일부 속성 집합을 사용 하 여 여러 인수와 생성자 사용 사이 의미 체계에 차이가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>

<span data-ttu-id="5e318-117">✔️ 생성자 매개 변수를 단순히 속성을 설정 하는 데 사용 하는 경우 생성자 매개 변수 및 속성에 대 한 동일한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-117">✔️ DO use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>

<span data-ttu-id="5e318-118">이러한 매개 변수와 속성 간의 유일한 차이점은 대/소문자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-118">The only difference between such parameters and the properties should be casing.</span></span>

<span data-ttu-id="5e318-119">✔️ 생성자에서 최소한의 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-119">✔️ DO minimal work in the constructor.</span></span>

<span data-ttu-id="5e318-120">생성자는 생성자 매개 변수를 캡처하는 것 외에는 많은 작업을 수행하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="5e318-121">다른 처리 비용은 필요할 때까지 지연되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-121">The cost of any other processing should be delayed until required.</span></span>

<span data-ttu-id="5e318-122">✔️ 적절한 경우 인스턴스 생성자에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-122">✔️ DO throw exceptions from instance constructors, if appropriate.</span></span>

<span data-ttu-id="5e318-123">✔️ 이러한 생성자가 필요한 경우 클래스에서 public 매개 변수 없는 생성자임을 명시적으로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-123">✔️ DO explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>

<span data-ttu-id="5e318-124">형식에 대한 생성자도 명시적으로 선언하지 않으면 많은 언어(예: C#)가 자동으로 public 매개 변수 없는 생성자가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="5e318-125">(추상 클래스는 보호된 생성자입니다.)</span><span class="sxs-lookup"><span data-stu-id="5e318-125">(Abstract classes get a protected constructor.)</span></span>

<span data-ttu-id="5e318-126">클래스에 매개 변수화된 생성자를 추가하면 컴파일러가 매개 변수 없는 생성자를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="5e318-127">이로 인해 우발적인 주요 변경 사항이 발생하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-127">This often causes accidental breaking changes.</span></span>

<span data-ttu-id="5e318-128">❌구조체에서 매개 변수 없는 생성자정의를 명시적으로 정의하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5e318-128">❌ AVOID explicitly defining parameterless constructors on structs.</span></span>

<span data-ttu-id="5e318-129">이렇게 하면 매개 변수 없는 생성자가 정의되지 않은 경우 배열의 모든 슬롯에서 실행할 필요가 없으므로 배열 생성 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="5e318-130">C#을 포함한 많은 컴파일러에는 이러한 이유로 구조체에 매개 변수 없는 생성자가 있는 것을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>

<span data-ttu-id="5e318-131">❌생성자 내부의 개체에서 가상 멤버를 호출하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5e318-131">❌ AVOID calling virtual members on an object inside its constructor.</span></span>

<span data-ttu-id="5e318-132">가상 멤버를 호출하면 가장 파생된 형식의 생성자가 아직 완전히 실행되지 않은 경우에도 가장 많이 파생된 재정의가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>

## <a name="type-constructor-guidelines"></a><span data-ttu-id="5e318-133">유형 생성자 지침</span><span class="sxs-lookup"><span data-stu-id="5e318-133">Type Constructor Guidelines</span></span>

<span data-ttu-id="5e318-134">✔️ 정적 생성자 개인으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-134">✔️ DO make static constructors private.</span></span>

<span data-ttu-id="5e318-135">클래스 생성자라고도 하는 정적 생성자는 형식을 초기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="5e318-136">CLR은 형식의 첫 번째 인스턴스가 만들어지거나 해당 형식의 정적 멤버가 호출되기 전에 정적 생성자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="5e318-137">정적 생성자가 호출되는 시기를 사용자가 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="5e318-138">정적 생성자가 개인적이지 않은 경우 CLR 이외의 코드에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="5e318-139">생성자에서 수행되는 작업에 따라 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="5e318-140">C# 컴파일러는 정적 생성자를 비공개로 강제합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-140">The C# compiler forces static constructors to be private.</span></span>

<span data-ttu-id="5e318-141">❌정적 생성자에서 예외를 throw하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5e318-141">❌ DO NOT throw exceptions from static constructors.</span></span>

<span data-ttu-id="5e318-142">형식 생성자에서 예외가 throw된 경우 현재 응용 프로그램 도메인에서 형식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>

<span data-ttu-id="5e318-143">✔️ 런타임은 명시적으로 정의된 정적 생성자가 없는 형식의 성능을 최적화할 수 있기 때문에 정적 생성기를 명시적으로 사용하는 대신 인라인으로 정적 필드를 초기화하는 것을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="5e318-143">✔️ CONSIDER initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>

<span data-ttu-id="5e318-144">*2005년, 2009년 마이크로소프트© 판권.*</span><span class="sxs-lookup"><span data-stu-id="5e318-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="5e318-145">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="5e318-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="5e318-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e318-146">See also</span></span>

- [<span data-ttu-id="5e318-147">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="5e318-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="5e318-148">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="5e318-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
