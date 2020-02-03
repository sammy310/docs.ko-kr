---
title: 열거형 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
ms.openlocfilehash: 3b24bfefd3edb0585e9c6369e9b8151b17151661
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741707"
---
# <a name="enum-design"></a><span data-ttu-id="83a38-102">열거형 디자인</span><span class="sxs-lookup"><span data-stu-id="83a38-102">Enum Design</span></span>

<span data-ttu-id="83a38-103">열거형은 특수 한 종류의 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="83a38-104">열거형에는 단순 열거형과 플래그 열거형의 두 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-104">There are two kinds of enums: simple enums and flag enums.</span></span>

<span data-ttu-id="83a38-105">단순 열거형은 작은 닫힌 선택 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="83a38-106">간단한 열거형의 일반적인 예는 색 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-106">A common example of the simple enum is a set of colors.</span></span>

<span data-ttu-id="83a38-107">플래그 열거형은 열거형 값에 대 한 비트 연산을 지원 하도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="83a38-108">플래그 열거의 일반적인 예는 옵션의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-108">A common example of the flags enum is a list of options.</span></span>

<span data-ttu-id="83a38-109">✔️는 열거형을 사용 하 여 값 집합을 나타내는 강력한 형식 매개 변수, 속성 및 반환 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-109">✔️ DO use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>

<span data-ttu-id="83a38-110">정적 상수 대신 열거형을 사용 하 여 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-110">✔️ DO favor using an enum instead of static constants.</span></span>

<span data-ttu-id="83a38-111">❌ 개방형 집합 (예: 운영 체제 버전, 친구 이름 등)에 대해 열거형을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-111">❌ DO NOT use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>

<span data-ttu-id="83a38-112">❌는 나중에 사용 하기 위해 예약 된 열거형 값을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-112">❌ DO NOT provide reserved enum values that are intended for future use.</span></span>

<span data-ttu-id="83a38-113">이후 단계에서 항상 기존 열거형에 값을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="83a38-114">열거형에 값을 추가 하는 방법에 대 한 자세한 내용은 [열거형에 값 추가](#add_value) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83a38-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="83a38-115">예약 된 값은 실제 값의 집합만 pollute 사용자 오류가 발생 하는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>

<span data-ttu-id="83a38-116">❌ 한 값만 포함 된 열거형을 공개적으로 노출 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-116">❌ AVOID publicly exposing enums with only one value.</span></span>

<span data-ttu-id="83a38-117">이후 C Api의 확장성을 보장 하는 일반적인 방법은 메서드 시그니처에 예약 된 매개 변수를 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="83a38-118">이러한 예약 된 매개 변수는 단일 기본값을 포함 하는 열거형으로 표현 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="83a38-119">이는 관리 되는 Api에서 수행 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="83a38-120">메서드 오버 로드를 사용 하면 이후 릴리스에서 매개 변수를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-120">Method overloading allows adding parameters in future releases.</span></span>

<span data-ttu-id="83a38-121">❌에는 열거형의 센티널 값이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-121">❌ DO NOT include sentinel values in enums.</span></span>

<span data-ttu-id="83a38-122">개발자는 프레임 워크 개발자에 게 유용 하지만 센티널 값은 프레임 워크의 사용자에 게 혼동을 주는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="83a38-123">열거형이 나타내는 집합의 값 중 하나가 아니라 열거형의 상태를 추적 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>

<span data-ttu-id="83a38-124">✔️ 단순 열거형에 0 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-124">✔️ DO provide a value of zero on simple enums.</span></span>

<span data-ttu-id="83a38-125">"None"과 같은 값을 호출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="83a38-126">이러한 특정 열거형에 적절 한 값이 없는 경우 열거형의 가장 일반적인 기본값은 0의 기본 값을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>

<span data-ttu-id="83a38-127">다음 중 하나에 해당 하지 않는 한 열거형의 기본 형식으로 <xref:System.Int32> (대부분의 프로그래밍 언어의 기본값)를 사용 하는 것이 좋습니다. ✔️</span><span class="sxs-lookup"><span data-stu-id="83a38-127">✔️ CONSIDER using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>

- <span data-ttu-id="83a38-128">열거형이 플래그 열거형 이며 32 개 이상의 플래그를 포함 하거나 앞으로 더 많은 것이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>

- <span data-ttu-id="83a38-129">다른 크기의 열거를 기대 하는 비관리 코드와의 상호 운용성을 위해 기본 형식은 <xref:System.Int32>과 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>

- <span data-ttu-id="83a38-130">기본 형식이 작을수록 공간이 크게 절약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="83a38-131">열거를 주로 제어 흐름에 대 한 인수로 사용 하는 경우 크기는 약간 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="83a38-132">크기 절감은 다음과 같은 경우에 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-132">The size savings might be significant if:</span></span>

  - <span data-ttu-id="83a38-133">가장 자주 인스턴스화되는 구조체 또는 클래스에서 열거형을 필드로 사용할 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>

  - <span data-ttu-id="83a38-134">사용자가 많은 배열 또는 열거형 인스턴스의 컬렉션을 만들 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-134">You expect users to create large arrays or collections of the enum instances.</span></span>

  - <span data-ttu-id="83a38-135">많은 수의 열거형 인스턴스가 serialize 될 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-135">You expect a large number of instances of the enum to be serialized.</span></span>

<span data-ttu-id="83a38-136">메모리 내 사용의 경우 관리 되는 개체는 항상 `DWORD`맞춰져 있으므로 전체 인스턴스 크기는 항상 `DWORD`으로 반올림 되기 때문에 더 작은 열거형을 압축 하려면 인스턴스의 여러 열거형 또는 다른 작은 구조를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>

<span data-ttu-id="83a38-137">✔️ DO name은 복수 명사 또는 명사구를 사용 하는 열거형과 단일 명사 또는 명사구를 사용 하는 단순 열거형을 플래그 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-137">✔️ DO name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>

<span data-ttu-id="83a38-138">❌ <xref:System.Enum?displayProperty=nameWithType>를 직접 확장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-138">❌ DO NOT extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="83a38-139"><xref:System.Enum?displayProperty=nameWithType>은 CLR에서 사용자 정의 열거형을 만드는 데 사용 하는 특수 한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="83a38-140">대부분의 프로그래밍 언어는이 기능에 대 한 액세스를 제공 하는 프로그래밍 요소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="83a38-141">예를 들어 C# `enum` 키워드는 열거형을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>

<a name="design"></a>

### <a name="designing-flag-enums"></a><span data-ttu-id="83a38-142">플래그 열거형 디자인</span><span class="sxs-lookup"><span data-stu-id="83a38-142">Designing Flag Enums</span></span>

<span data-ttu-id="83a38-143"><xref:System.FlagsAttribute?displayProperty=nameWithType>을 플래그 열거형에 적용 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-143">✔️ DO apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="83a38-144">단순 열거형에는이 특성을 적용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="83a38-144">Do not apply this attribute to simple enums.</span></span>

<span data-ttu-id="83a38-145">✔️는 플래그 열거형 값으로 2의 거듭제곱을 사용 하므로 비트 OR 연산을 사용 하 여 자유롭게 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-145">✔️ DO use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>

<span data-ttu-id="83a38-146">일반적으로 사용 되는 플래그 조합에 특수 한 열거형 값을 제공 하는 것이 좋습니다 ✔️.</span><span class="sxs-lookup"><span data-stu-id="83a38-146">✔️ CONSIDER providing special enum values for commonly used combinations of flags.</span></span>

<span data-ttu-id="83a38-147">비트 연산은 고급 개념 이므로 간단한 작업에는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="83a38-148"><xref:System.IO.FileAccess.ReadWrite>은 이러한 특수 값의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>

<span data-ttu-id="83a38-149">값의 특정 조합이 유효 하지 않은 경우 플래그 열거형을 만들지 않도록 ❌ 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-149">❌ AVOID creating flag enums where certain combinations of values are invalid.</span></span>

<span data-ttu-id="83a38-150">값이 "모든 플래그가 지워졌습니다."를 나타내고 다음 지침에서 설명한 대로 이름을 적절 하 게 지정 하지 않으면 플래그 열거형 값을 0으로 사용 하지 않습니다. ❌</span><span class="sxs-lookup"><span data-stu-id="83a38-150">❌ AVOID using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>

<span data-ttu-id="83a38-151">✔️ 플래그 열거형의 0 값 `None`합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-151">✔️ DO name the zero value of flag enums `None`.</span></span> <span data-ttu-id="83a38-152">플래그 열거형의 경우 값은 항상 "모든 플래그가 지워졌습니다."을 의미 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a><span data-ttu-id="83a38-153">열거형에 값 추가</span><span class="sxs-lookup"><span data-stu-id="83a38-153">Adding Value to Enums</span></span>

<span data-ttu-id="83a38-154">이미 제공 된 후에는 열거형에 값을 추가 해야 한다는 것을 발견 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="83a38-155">잘못 작성 된 응용 프로그램은 새 값을 올바르게 처리 하지 못할 수 있으므로 새로 추가 된 값이 기존 API에서 반환 될 때 응용 프로그램 호환성 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>

<span data-ttu-id="83a38-156">약간의 호환성 위험에도 불구 하 고 열거형에 값을 추가 하는 것이 좋습니다. ✔️</span><span class="sxs-lookup"><span data-stu-id="83a38-156">✔️ CONSIDER adding values to enums, despite a small compatibility risk.</span></span>

<span data-ttu-id="83a38-157">열거형 추가로 인 한 응용 프로그램 호환성 문제에 대 한 실제 데이터가 있는 경우 새 값과 이전 값을 반환 하는 새 API를 추가 하 고 이전 값만 반환 하는 이전 API를 사용 중단 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="83a38-158">이렇게 하면 기존 응용 프로그램이 호환 되는 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a38-158">This will ensure that your existing applications remain compatible.</span></span>

<span data-ttu-id="83a38-159">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="83a38-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="83a38-160">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="83a38-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="83a38-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83a38-161">See also</span></span>

- [<span data-ttu-id="83a38-162">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="83a38-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="83a38-163">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="83a38-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
