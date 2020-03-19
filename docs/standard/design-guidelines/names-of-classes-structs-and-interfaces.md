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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401240"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="b5beb-102">클래스, 구조체 및 인터페이스의 이름</span><span class="sxs-lookup"><span data-stu-id="b5beb-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="b5beb-103">다음에 있는 명명 지침은 일반 형식 이름 지정에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-103">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="b5beb-104">✔️ pascalCasing을 사용하여 명사 또는 명사 구를 사용하여 클래스와 구조체를 이름 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-104">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="b5beb-105">이렇게 하면 동사 구로 이름이 지정된 메서드와 형식 이름을 구별합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="b5beb-106">✔️ DO 는 형용사 구또는 때때로 명사 또는 명사 구와 인터페이스를 이름 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-106">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="b5beb-107">명사 및 명사 구는 거의 사용해야 하며 형식이 인터페이스가 아닌 추상 클래스여야 함을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="b5beb-108">❌클래스 이름에 접두사(예: "C")를 지정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b5beb-108">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="b5beb-109">✔️ 기본 클래스의 이름으로 파생 된 클래스의 이름을 종료 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-109">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="b5beb-110">이것은 매우 읽을 수 있으며 관계를 명확하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="b5beb-111">코드에서 이것의 몇 가지 `ArgumentOutOfRangeException`예는 다음과 `Exception`같습니다. `SerializableAttribute` `Attribute`</span><span class="sxs-lookup"><span data-stu-id="b5beb-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="b5beb-112">그러나 이 지침을 적용할 때 합리적인 판단을 사용하는 것이 중요합니다. 예를 들어 `Button` 클래스는 일종의 `Control` 이벤트이지만 `Control` 이름에는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="b5beb-113">✔️ do do 인터페이스 이름을 문자 I로 사용하여 형식이 인터페이스임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-113">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="b5beb-114">예를 `IComponent` 들어(설명 명사), `ICustomAttributeProvider` (명사 구) `IPersistable` 및 (형용사)는 적절한 인터페이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="b5beb-115">다른 형식 이름과 마찬가지로 약어는 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b5beb-115">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="b5beb-116">✔️ 클래스가 인터페이스의 표준 구현인 클래스 인터페이스 쌍을 정의할 때 인터페이스 이름의 "I" 접두사에 의해서만 이름이 달라지도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-116">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="b5beb-117">제네릭 형식 매개 변수의 이름</span><span class="sxs-lookup"><span data-stu-id="b5beb-117">Names of Generic Type Parameters</span></span>
 <span data-ttu-id="b5beb-118">제네릭이 .NET 프레임워크 2.0에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="b5beb-119">이 기능은 *type 매개 변수라는*새로운 종류의 식별자를 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="b5beb-120">✔️ DO는 단일 문자 이름이 완전히 설명이 되고 설명이 있는 이름이 값을 추가하지 않는 한 설명이 있는 제네릭 형식 매개 변수를 이름 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-120">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="b5beb-121">✔️ 단일 `T` 문자 형식 매개 변수가 있는 형식에 대한 형식 매개 변수 이름으로 사용하는 것을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-121">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="b5beb-122">✔️ do 를 사용 하 고 `T`설명 형식 매개 변수 이름을 접두사</span><span class="sxs-lookup"><span data-stu-id="b5beb-122">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="b5beb-123">✔️ 매개 변수의 이름으로 형식 매개 변수에 배치 된 제약 조건을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-123">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="b5beb-124">예를 들어 로 제한된 `ISession` 매개 변수를 호출할 `TSession`수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="b5beb-125">공통 형식의 이름</span><span class="sxs-lookup"><span data-stu-id="b5beb-125">Names of Common Types</span></span>
 <span data-ttu-id="b5beb-126">✔️ 특정 .NET Framework 형식에서 파생된 형식의 이름을 지정하거나 구현할 때 다음 표에 설명된 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-126">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="b5beb-127">Base Type</span><span class="sxs-lookup"><span data-stu-id="b5beb-127">Base Type</span></span>|<span data-ttu-id="b5beb-128">파생/구현 유형 지침</span><span class="sxs-lookup"><span data-stu-id="b5beb-128">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="b5beb-129">✔️ 사용자 지정 특성 클래스의 이름에 접미사 "특성"을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-129">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="b5beb-130">✔️ 이벤트에 사용되는 대리자의 이름에 접미사 "EventHandler"를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-130">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="b5beb-131">✔️ 이벤트 처리기로 사용되는 대리자 이외의 이름에 접미사 "콜백"을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-131">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="b5beb-132">❌대리인에 접미사 "대리자"를 추가하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b5beb-132">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="b5beb-133">✔️ 접미사 "EventArgs"를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-133">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="b5beb-134">❌이 클래스에서 파생되지 마십시오. 대신 언어에서 지원하는 키워드를 사용합니다. 예를 들어 C#에서 키워드를 `enum` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-134">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="b5beb-135">❌접미사 "열거형" 또는 "플래그"를 추가하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b5beb-135">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="b5beb-136">✔️ 접미사 "예외"를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-136">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="b5beb-137">✔️ 접미사 "사전"을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-137">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="b5beb-138">특정 `IDictionary` 유형의 컬렉션이지만 이 지침은 다음에 오는 보다 일반적인 컬렉션 지침보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="b5beb-139">✔️ 접미사 "컬렉션"을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-139">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="b5beb-140">✔️ 접미사 "스트림"을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-140">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="b5beb-141">✔️ 접미사 "권한"을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-141">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="b5beb-142">이름 지정 열거형</span><span class="sxs-lookup"><span data-stu-id="b5beb-142">Naming Enumerations</span></span>
 <span data-ttu-id="b5beb-143">열거형 형식(열거형이라고도 함)의 이름은 일반적으로 표준 형식 명명 규칙(파스칼케이팅 등)을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="b5beb-144">그러나 열거형에 특별히 적용되는 추가 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-144">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="b5beb-145">✔️ 값이 비트 필드가 아니면 열거형에 단수 형식 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-145">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="b5beb-146">✔️ dodo는 비트 필드가 있는 열거형에 대해 플래그 열거형이라고도 하는 값으로 복수 형식 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5beb-146">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="b5beb-147">❌열거형 유형 이름에 "열거형" 접미사를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b5beb-147">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="b5beb-148">❌열거형 유형 이름에는 "플래그" 또는 "플래그" 접미사를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b5beb-148">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="b5beb-149">❌열거형 값 이름에 는 접두사를 사용하지 마십시오(예: ADO 열거형의 경우 "광고", "rtf" 등).</span><span class="sxs-lookup"><span data-stu-id="b5beb-149">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="b5beb-150">*2005년, 2009년 마이크로소프트© 판권.*</span><span class="sxs-lookup"><span data-stu-id="b5beb-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="b5beb-151">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="b5beb-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="b5beb-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5beb-152">See also</span></span>

- [<span data-ttu-id="b5beb-153">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b5beb-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="b5beb-154">명명 지침</span><span class="sxs-lookup"><span data-stu-id="b5beb-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
