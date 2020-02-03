---
title: 클래스, 구조체 및 인터페이스의 이름
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: 2c528348c0e84037a80df9797c56f03b51c73adc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727792"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="73e97-102">클래스, 구조체 및 인터페이스의 이름</span><span class="sxs-lookup"><span data-stu-id="73e97-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="73e97-103">다음 명명 지침은 일반적인 형식 이름 지정에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-103">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="73e97-104">✔️는 명사 또는 명사구를 사용 하 여 클래스와 구조체의 이름을 지정할 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-104">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="73e97-105">이는 동사 구와 이름이 지정 된 메서드의 형식 이름을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="73e97-106">✔️는 형용사 구를 사용 하 여 인터페이스를 만들거나 명사 또는 명사구를 사용 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-106">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="73e97-107">명사 및 명사구는 거의 사용 되지 않으며 형식이 인터페이스가 아닌 추상 클래스 여야 함을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="73e97-108">클래스 이름을 접두사 (예: "C")로 지정 하지 ❌.</span><span class="sxs-lookup"><span data-stu-id="73e97-108">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="73e97-109">기본 클래스의 이름을 사용 하 여 파생 클래스의 이름을 종료 하는 것이 좋습니다 ✔️.</span><span class="sxs-lookup"><span data-stu-id="73e97-109">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="73e97-110">이는 매우 읽기 쉬우며 관계를 명확 하 게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="73e97-111">코드에서이에 대 한 몇 가지 예는 `ArgumentOutOfRangeException``Exception`, 일종의 `Attribute`인 `SerializableAttribute`입니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="73e97-112">그러나이 지침을 적용할 때 적절 한 판단을 사용 하는 것이 중요 합니다. 예를 들어 `Button` 클래스는 `Control` 이름에 표시 되지 않지만 `Control` 이벤트의 일종입니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="73e97-113">인터페이스 이름 앞에 문자 I를 사용 하 여 형식이 인터페이스 임을 나타내려면 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-113">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="73e97-114">예를 들어 `IComponent` (설명 명사), `ICustomAttributeProvider` (명사 구) 및 `IPersistable` (형용사)는 적절 한 인터페이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="73e97-115">다른 형식 이름과 마찬가지로 약어를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="73e97-115">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="73e97-116">클래스가 인터페이스의 표준 구현인 클래스-인터페이스 쌍을 정의 하는 경우 인터페이스 이름에서 "I" 접두사에 의해서만 이름이 다른 지 확인 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-116">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="73e97-117">제네릭 형식 매개 변수의 이름</span><span class="sxs-lookup"><span data-stu-id="73e97-117">Names of Generic Type Parameters</span></span>
 <span data-ttu-id="73e97-118">제네릭을 .NET Framework 2.0에 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="73e97-119">이 기능에는 *형식 매개 변수*라는 새로운 종류의 식별자가 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="73e97-120">단일 문자 이름이 완전히 설명이 없는 경우 설명이 포함 된 이름을 사용 하 여 제네릭 형식 매개 변수 이름을 지정 하 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-120">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="73e97-121">✔️ 하나의 단일 문자 형식 매개 변수를 사용 하 여 형식에 대 한 형식 매개 변수 이름으로 `T`를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-121">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="73e97-122">`T`를 사용 하 여 설명 형식 매개 변수 이름에 접두사를 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-122">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="73e97-123">매개 변수 이름에서 형식 매개 변수에 적용 되는 제약 조건을 표시 하는 것이 좋습니다 ✔️.</span><span class="sxs-lookup"><span data-stu-id="73e97-123">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="73e97-124">예를 들어 `ISession` 제한 된 매개 변수는 `TSession`호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="73e97-125">공용 형식의 이름</span><span class="sxs-lookup"><span data-stu-id="73e97-125">Names of Common Types</span></span>
 <span data-ttu-id="73e97-126">✔️에서 파생 된 형식을 명명 하거나 특정 .NET Framework 형식을 구현할 때 다음 표에 설명 된 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-126">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="73e97-127">Base Type</span><span class="sxs-lookup"><span data-stu-id="73e97-127">Base Type</span></span>|<span data-ttu-id="73e97-128">파생/구현 형식 지침</span><span class="sxs-lookup"><span data-stu-id="73e97-128">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="73e97-129">✔️ 사용자 지정 특성 클래스의 이름에 "Attribute" 접미사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-129">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="73e97-130">✔️ 이벤트에 사용 되는 대리자 이름에 "EventHandler" 접미사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-130">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="73e97-131">이벤트 처리기로 사용 된 대리자 이외의 이름에 "Callback" 접미사를 추가 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-131">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="73e97-132">❌ "Delegate" 접미사를 대리자에 추가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-132">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="73e97-133">"EventArgs" 접미사를 추가 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-133">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="73e97-134">❌이 클래스에서 파생 되지 않습니다. 대신 해당 언어로 지원 되는 키워드를 사용 합니다. 예를 들어에서 C#`enum` 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-134">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="73e97-135">❌ 접미사 "Enum" 또는 "Flag"를 추가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-135">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="73e97-136">✔️ 접미사 "Exception"을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-136">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="73e97-137">✔️ 접미사 "Dictionary"를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-137">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="73e97-138">`IDictionary`은 특정 유형의 컬렉션 이지만이 지침은 다음과 같은 보다 일반적인 컬렉션 지침 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="73e97-139">"Collection" 접미사를 추가 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-139">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="73e97-140">접미사 "Stream"을 추가 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-140">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="73e97-141">✔️ 접미사 "Permission"을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-141">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="73e97-142">열거형 이름 지정</span><span class="sxs-lookup"><span data-stu-id="73e97-142">Naming Enumerations</span></span>
 <span data-ttu-id="73e97-143">일반적으로 열거형 형식 (열거형이 라고도 함)의 이름은 표준 형식 명명 규칙을 따라야 합니다 (예를 들어).</span><span class="sxs-lookup"><span data-stu-id="73e97-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="73e97-144">그러나 열거형에는 특별히 적용 되는 추가 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-144">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="73e97-145">값이 비트 필드인 경우를 제외 하 고는 열거형에 대해 단 수 형식 이름을 사용 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-145">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="73e97-146">비트 필드를 값으로 사용 하는 열거형 (플래그 열거형이 라고도 함)에는 복수형 형식 이름을 사용 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-146">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="73e97-147">❌ 열거형 형식 이름에 "Enum" 접미사를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-147">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="73e97-148">❌ 열거형 형식 이름에 "Flags" 또는 "Flags" 접미사를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73e97-148">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="73e97-149">❌ 열거형 값 이름에는 접두사를 사용 하지 않습니다 (예: ADO 열거형의 경우 "ad", 서식 있는 텍스트 열거형의 경우 "rtf" 등).</span><span class="sxs-lookup"><span data-stu-id="73e97-149">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="73e97-150">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="73e97-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="73e97-151">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="73e97-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="73e97-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73e97-152">See also</span></span>

- [<span data-ttu-id="73e97-153">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="73e97-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="73e97-154">명명 지침</span><span class="sxs-lookup"><span data-stu-id="73e97-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
