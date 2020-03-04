---
title: 액세스 한정자 - C# 프로그래밍 가이드
ms.date: 03/08/2020
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
ms.openlocfilehash: 749d53344a2518966cfa5d937069ba73dfd6be8f
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628230"
---
# <a name="access-modifiers-c-programming-guide"></a><span data-ttu-id="af94f-102">액세스 한정자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="af94f-102">Access Modifiers (C# Programming Guide)</span></span>

<span data-ttu-id="af94f-103">모든 형식과 형식 멤버에는 액세스 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-103">All types and type members have an accessibility level.</span></span> <span data-ttu-id="af94f-104">액세스 수준은 사용 중인 어셈블리나 다른 어셈블리에서 형식 또는 형식 멤버를 사용할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-104">The accessibility level controls whether they can be used from other code in your assembly or other assemblies.</span></span> <span data-ttu-id="af94f-105">다음 액세스 한정자를 사용하여 형식 또는 멤버를 선언할 때 해당 항목의 액세스 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-105">Use the following access modifiers to specify the accessibility of a type or member when you declare it:</span></span>

- <span data-ttu-id="af94f-106">[public](../../language-reference/keywords/public.md): 동일한 어셈블리의 다른 코드나 해당 어셈블리를 참조하는 다른 어셈블리의 코드에서 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-106">[public](../../language-reference/keywords/public.md): The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>
- <span data-ttu-id="af94f-107">[private](../../language-reference/keywords/private.md): 같은 `class` 또는 `struct`의 코드에서만 형식 또는 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-107">[private](../../language-reference/keywords/private.md): The type or member can be accessed only by code in the same `class` or `struct`.</span></span>
- <span data-ttu-id="af94f-108">[protected](../../language-reference/keywords/protected.md): 같은 `class` 또는 해당 `class`에서 파생된 `class`의 코드에서만 형식 또는 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-108">[protected](../../language-reference/keywords/protected.md): The type or member can be accessed only by code in the same `class`, or in a `class` that is derived from that `class`.</span></span>
- <span data-ttu-id="af94f-109">[internal](../../language-reference/keywords/internal.md): 동일한 어셈블리의 코드에서는 형식이나 멤버에 액세스할 수 있지만 다른 어셈블리의 코드에서는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-109">[internal](../../language-reference/keywords/internal.md): The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>
- <span data-ttu-id="af94f-110">[protected internal](../../language-reference/keywords/protected-internal.md): 형식 또는 멤버가 선언된 어셈블리의 모든 코드에서 또는 다른 어셈블리의 파생 `class` 내에서 형식 또는 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-110">[protected internal](../../language-reference/keywords/protected-internal.md): The type or member can be accessed by any code in the assembly in which it's declared, or from within a derived `class` in another assembly.</span></span>
- <span data-ttu-id="af94f-111">[private protected](../../language-reference/keywords/private-protected.md): 형식 또는 멤버가 선언된 어셈블리, 같은 `class`나 해당 `class`에서 파생된 형식의 코드에서만 형식 또는 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-111">[private protected](../../language-reference/keywords/private-protected.md): The type or member can be accessed only within its declaring assembly, by code in the same `class` or in a type that is derived from that `class`.</span></span>

<span data-ttu-id="af94f-112">다음 예제에서는 형식 및 멤버에 대해 액세스 한정자를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-112">The following examples demonstrate how to specify access modifiers on a type and member:</span></span>

[!code-csharp[PublicAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#PublicAccess)]

<span data-ttu-id="af94f-113">모든 액세스 한정자를 모든 컨텍스트에서 모든 형식 또는 멤버에서 사용할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-113">Not all access modifiers are valid for all types or members in all contexts.</span></span> <span data-ttu-id="af94f-114">형식 멤버의 액세스 수준이 해당 형식 멤버를 포함하는 형식의 액세스 수준으로 제한되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-114">In some cases, the accessibility of a type member is constrained by the accessibility of its containing type.</span></span>

## <a name="class-and-struct-accessibility"></a><span data-ttu-id="af94f-115">클래스 및 구조체 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="af94f-115">Class and struct accessibility</span></span>  

<span data-ttu-id="af94f-116">네임스페이스 내에서 직접 선언된(즉, 다른 클래스 또는 구조체 내에 중첩되지 않은) 클래스와 구조체는 `public`과 `internal` 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-116">Classes and structs declared directly within a namespace (in other words, that aren't nested within other classes or structs) can be either `public` or `internal`.</span></span> <span data-ttu-id="af94f-117">액세스 한정자가 지정되지 않은 경우 기본값은 `Internal`입니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-117">`Internal` is the default if no access modifier is specified.</span></span>  

<span data-ttu-id="af94f-118">구조체 멤버(중첩 클래스 및 구조체 포함)는 `public`, `internal` 또는 `private`으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-118">Struct members, including nested classes and structs, can be declared `public`, `internal`, or `private`.</span></span> <span data-ttu-id="af94f-119">클래스 멤버(중첩 클래스 포함)는 `public`, `protected internal`, `protected`, `internal`, `private protected` 또는 `private`으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-119">Class members, including nested classes and structs, can be `public`, `protected internal`, `protected`, `internal`, `private protected`, or `private`.</span></span> <span data-ttu-id="af94f-120">클래스 멤버와 구조체 멤버(중첩 클래스 및 구조체 포함)의 액세스 수준은 기본적으로 `private`입니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-120">Class and struct members,  including nested classes and structs, have `private` access by default.</span></span> <span data-ttu-id="af94f-121">private 중첩 형식은 해당 형식을 포함하는 형식 외부에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-121">Private nested types aren't accessible from outside the containing type.</span></span>

<span data-ttu-id="af94f-122">파생 클래스는 기본 형식보다 높은 액세스 수준을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-122">Derived classes can't have greater accessibility than their base types.</span></span> <span data-ttu-id="af94f-123">internal 클래스 `A`에서 파생된 public 클래스 `B`를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-123">You can't declare a public class `B` that derives from an internal class `A`.</span></span> <span data-ttu-id="af94f-124">이것이 허용된다면 파생 클래스에서 `A`의 모든 `protected` 또는 `internal` 멤버에 액세스할 수 있게 되므로 결과적으로 `A`가 public이 되는 것과 같아집니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-124">If allowed, it would have the effect of making `A` public, because all `protected` or `internal` members of `A` are accessible from the derived class.</span></span>

<span data-ttu-id="af94f-125">다른 특정 어셈블리에서 internal 형식에 액세스할 수 있도록 하려면 `InternalsVisibleToAttribute`를 시용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-125">You can enable specific other assemblies to access your internal types by using the `InternalsVisibleToAttribute`.</span></span> <span data-ttu-id="af94f-126">자세한 내용은 [Friend 어셈블리](../../../standard/assembly/friend.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af94f-126">For more information, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>

## <a name="class-and-struct-member-accessibility"></a><span data-ttu-id="af94f-127">클래스 및 구조체 멤버 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="af94f-127">Class and struct member accessibility</span></span>  

<span data-ttu-id="af94f-128">중첩 클래스 및 구조체를 포함한 클래스 멤버는 6가지 액세스 형식으로 선언될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-128">Class members (including nested classes and structs) can be declared with any of the six types of access.</span></span> <span data-ttu-id="af94f-129">구조체는 상속을 지원하지 않으므로 구조체 멤버는 `protected`, `protected internal` 또는 `private protected`로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-129">Struct members can't be declared as `protected`, `protected internal`, or `private protected` because structs don't support inheritance.</span></span>

<span data-ttu-id="af94f-130">일반적으로 멤버의 액세스 수준은 해당 멤버를 포함하는 형식의 액세스 수준보다 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-130">Normally, the accessibility of a member isn't greater than the accessibility of the type that contains it.</span></span> <span data-ttu-id="af94f-131">그러나 멤버가 인터페이스 메서드를 구현하거나 public 기본 클래스에 정의된 가상 메서드를 재정의하는 경우에는 어셈블리 외부에서 internal 클래스의 `public` 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-131">However, a `public` member of an internal class might be accessible from outside the assembly if the member implements interface methods or overrides virtual methods that are defined in a public base class.</span></span>

<span data-ttu-id="af94f-132">멤버의 필드, 속성 또는 이벤트 형식은 멤버 자체의 액세스 수준 이상을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-132">The type of any member field, property, or event must be at least as accessible as the member itself.</span></span> <span data-ttu-id="af94f-133">마찬가지로, 메서드, 인덱서 또는 대리자의 반환 형식과 매개 변수 형식은 멤버 자체의 액세스 수준 이상을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-133">Similarly, the return type and the parameter types of any method, indexer, or delegate must be at least as accessible as the member itself.</span></span> <span data-ttu-id="af94f-134">예를 들어 `C`도 `public`이 아닌 이상 클래스 `C`를 반환하는 `public` 메서드 `M`이 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-134">For example, you can't have a `public` method `M` that returns a class `C` unless `C` is also `public`.</span></span> <span data-ttu-id="af94f-135">마찬가지로, `A`가 `private`으로 선언되었다면 `A` 형식의 `protected` 속성이 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-135">Likewise, you can't have a `protected` property of type `A` if `A` is declared as `private`.</span></span>

<span data-ttu-id="af94f-136">사용자 정의 연산자는 항상 `public` 및 `static`으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-136">User-defined operators must always be declared as `public` and `static`.</span></span> <span data-ttu-id="af94f-137">자세한 내용은 [연산자 오버로드](../../language-reference/operators/operator-overloading.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af94f-137">For more information, see [Operator overloading](../../language-reference/operators/operator-overloading.md).</span></span>

<span data-ttu-id="af94f-138">종료자에는 접근성 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-138">Finalizers can't have accessibility modifiers.</span></span>

<span data-ttu-id="af94f-139">`class` 또는 `struct` 멤버의 액세스 수준을 설정하려면 다음 예제와 같이 멤버 선언에 해당 키워드를 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="af94f-139">To set the access level for a `class` or `struct` member, add the appropriate keyword to the member declaration, as shown in the following example.</span></span>

[!code-csharp[MethodAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#MethodAccess)]

## <a name="other-types"></a><span data-ttu-id="af94f-140">기타 형식</span><span class="sxs-lookup"><span data-stu-id="af94f-140">Other types</span></span>

<span data-ttu-id="af94f-141">네임스페이스 내에서 직접 선언된 인터페이스는 `public` 또는 `internal`일 수 있고, 클래스 및 구조체와 마찬가지로 인터페이스도 기본적으로 `internal` 액세스로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-141">Interfaces declared directly within a namespace can be `public` or `internal` and, just like classes and structs, interfaces default to `internal` access.</span></span> <span data-ttu-id="af94f-142">인터페이스는 다른 형식이 클래스나 구조체에 액세스하는 데 사용되므로 인터페이스 멤버는 기본적으로 `public`입니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-142">Interface members are `public` by default because the purpose of an interface is to enable other types to access a class or struct.</span></span> <span data-ttu-id="af94f-143">인터페이스 멤버 선언은 모든 액세스 한정자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-143">Interface member declarations may include any access modifier.</span></span> <span data-ttu-id="af94f-144">이는 정적 메서드가 모든 클래스 구현자에 필요한 공통된 구현을 제공하도록 할 때 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-144">This is most useful for static methods to provide common implementations needed by all implementors of a class.</span></span>

<span data-ttu-id="af94f-145">열거형 멤버는 항상 `public`이고 어떤 액세스 한정자도 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-145">Enumeration members are always `public`, and no access modifiers can be applied.</span></span>

<span data-ttu-id="af94f-146">대리자는 클래스 및 구조체처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-146">Delegates behave like classes and structs.</span></span> <span data-ttu-id="af94f-147">기본적으로 대리자는 네임스페이스 내에서 직접 선언된 경우 `internal` 액세스를 갖고 중첩된 경우 `private` 액세스를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="af94f-147">By default, they have `internal` access when declared directly within a namespace, and `private` access when nested.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="af94f-148">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="af94f-148">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="af94f-149">참조</span><span class="sxs-lookup"><span data-stu-id="af94f-149">See also</span></span>

- [<span data-ttu-id="af94f-150">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="af94f-150">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="af94f-151">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="af94f-151">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="af94f-152">인터페이스</span><span class="sxs-lookup"><span data-stu-id="af94f-152">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="af94f-153">private</span><span class="sxs-lookup"><span data-stu-id="af94f-153">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="af94f-154">public</span><span class="sxs-lookup"><span data-stu-id="af94f-154">public</span></span>](../../language-reference/keywords/public.md)
- [<span data-ttu-id="af94f-155">internal</span><span class="sxs-lookup"><span data-stu-id="af94f-155">internal</span></span>](../../language-reference/keywords/internal.md)
- [<span data-ttu-id="af94f-156">protected</span><span class="sxs-lookup"><span data-stu-id="af94f-156">protected</span></span>](../../language-reference/keywords/protected.md)
- [<span data-ttu-id="af94f-157">protected internal</span><span class="sxs-lookup"><span data-stu-id="af94f-157">protected internal</span></span>](../../language-reference/keywords/protected-internal.md)
- [<span data-ttu-id="af94f-158">private protected</span><span class="sxs-lookup"><span data-stu-id="af94f-158">private protected</span></span>](../../language-reference/keywords/private-protected.md)
- [<span data-ttu-id="af94f-159">class</span><span class="sxs-lookup"><span data-stu-id="af94f-159">class</span></span>](../../language-reference/keywords/class.md)
- [<span data-ttu-id="af94f-160">struct</span><span class="sxs-lookup"><span data-stu-id="af94f-160">struct</span></span>](../../language-reference/builtin-types/struct.md)
- [<span data-ttu-id="af94f-161">interface</span><span class="sxs-lookup"><span data-stu-id="af94f-161">interface</span></span>](../../language-reference/keywords/interface.md)
