---
title: 구조
description: 작은 양의 데이터와 간단한 동작이 있는 형식에 대한 클래스보다 더 효율적인 소형 개체 유형인 F# 구조에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 1e9652cc4776e4d1d52eb20e41b6dd87a6c5ba05
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401126"
---
# <a name="structures"></a><span data-ttu-id="81fe7-103">구조</span><span class="sxs-lookup"><span data-stu-id="81fe7-103">Structures</span></span>

<span data-ttu-id="81fe7-104">*구조체는* 적은 양의 데이터와 간단한 동작이 있는 형식에 대한 클래스보다 더 효율적일 수 있는 컴팩트한 개체 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="81fe7-105">구문</span><span class="sxs-lookup"><span data-stu-id="81fe7-105">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a><span data-ttu-id="81fe7-106">설명</span><span class="sxs-lookup"><span data-stu-id="81fe7-106">Remarks</span></span>

<span data-ttu-id="81fe7-107">구조체는 *값 형식이며*스택에 직접 저장되거나 필드 또는 배열 요소로 사용되는 경우 부모 형식의 인라인입니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="81fe7-108">클래스나 레코드와 달리 구조체는 pass-by-value 의미 체계를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="81fe7-109">따라서 기본적으로 자주 액세스 및 복사하는 소규모 데이터 집계에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="81fe7-110">위 구문에는 두 개의 폼이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="81fe7-111">첫 번째는 간단한 구문은 아니지만 자주 사용됩니다. `struct` 및 `end` 키워드를 사용하는 경우 두 번째 구문에 나와 있는 `StructAttribute` 특성을 생략할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="81fe7-112">즉, `StructAttribute`를 `Struct`로 간략하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="81fe7-113">이전 구문의 *형식 정의 요소 및 멤버는* 멤버 선언 및 정의를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-113">The *type-definition-elements-and-members* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="81fe7-114">구조체는 생성자 및 변경 가능/불가능한 필드를 포함할 수 있으며 멤버 및 인터페이스 구현을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="81fe7-115">자세한 내용은 [멤버 를](./members/index.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="81fe7-115">For more information, see [Members](./members/index.md).</span></span>

<span data-ttu-id="81fe7-116">구조체는 상속에 참가할 수 없고, `let` 또는 `do` 바인딩을 포함할 수 없으며, 자신의 형식으로 된 필드를 재귀적으로 포함할 수 없습니다. 그러나 자신의 형식을 참조하는 참조 셀은 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="81fe7-117">구조체는 `let` 바인딩을 허용하지 않으므로 구조체에서는 `val` 키워드를 사용하여 필드를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="81fe7-118">`val` 키워드는 필드와 해당 형식을 정의하지만 초기화는 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="81fe7-119">대신 `val` 선언이 null 또는 0으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="81fe7-120">따라서 암시적 생성자(선언에서 구조체 이름 바로 뒤에 지정되는 매개 변수)를 포함하는 구조체에서는 `val` 선언을 `DefaultValue` 특성으로 주석 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="81fe7-121">정의된 생성자가 있는 구조체도 0으로의 초기화를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="81fe7-122">그러므로 `DefaultValue` 특성은 이러한 0 값이 필드에 유효함을 나타내는 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="81fe7-123">구조체의 암시적 생성자는 아무런 작업도 수행하지 않습니다. 해당 형식에 대해서는 `let` 및 `do` 바인딩이 허용되지 않지만 전달되는 암시적 생성자 매개 변수 값은 개인 필드로 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="81fe7-124">명시적 생성자에서는 필드 값이 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="81fe7-125">명시적 생성자를 포함하는 구조체는 0으로의 초기화도 지원합니다. 그러나 `DefaultValue` 선언에서 `val` 특성을 사용하는 경우 명시적 생성자와 충돌하므로 해당 특성은 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="81fe7-126">선언에 대한 `val` 자세한 내용은 [명시적 `val` 필드: 키워드](./members/explicit-fields-the-val-keyword.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="81fe7-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="81fe7-127">특성 및 액세스 가능성 한정자는 구조체에서 허용되며 다른 형식과 동일한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="81fe7-128">자세한 내용은 [속성](attributes.md) 및 [액세스 제어](access-control.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="81fe7-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="81fe7-129">다음 코드 예제에서는 구조체 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a><span data-ttu-id="81fe7-130">ByRefLike 구조체</span><span class="sxs-lookup"><span data-stu-id="81fe7-130">ByRefLike structs</span></span>

<span data-ttu-id="81fe7-131">의미와 같은 의미체계를 준수할 `byref`수 있는 고유한 구조체를 [정의할](byrefs.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-131">You can define your own structs that can adhere to `byref`-like semantics: see [Byrefs](byrefs.md) for more information.</span></span> <span data-ttu-id="81fe7-132">이 작업은 다음과 <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> 같은 특성으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-132">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="81fe7-133">`IsByRefLike`을 의미하지는 `Struct`않습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-133">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="81fe7-134">둘 다 형식에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-134">Both must be present on the type.</span></span>

<span data-ttu-id="81fe7-135">F#의 "-like"`byref`구조체는 스택 바인딩된 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-135">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="81fe7-136">관리되는 힙에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-136">It is never allocated on the managed heap.</span></span> <span data-ttu-id="81fe7-137">`byref`-like 구조체는 수명 및 비캡처에 대한 강력한 검사 집합으로 적용되기 때문에 고성능 프로그래밍에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-137">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="81fe7-138">규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-138">The rules are:</span></span>

- <span data-ttu-id="81fe7-139">함수 매개 변수, 메서드 매개 변수, 로컬 변수, 메서드 반환으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-139">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
- <span data-ttu-id="81fe7-140">정적 또는 인스턴스 멤버가 클래스 또는 일반 구조체일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-140">They cannot be static or instance members of a class or normal struct.</span></span>
- <span data-ttu-id="81fe7-141">모든 클로저 구문(메서드`async` 또는 람다 식)에 의해 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-141">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
- <span data-ttu-id="81fe7-142">일반 매개 변수로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-142">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="81fe7-143">이러한 규칙은 사용량을 매우 강력하게 제한하지만 안전한 방식으로 고성능 컴퓨팅의 약속을 이행하기 위해 그렇게 합니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-143">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="81fe7-144">읽기전용 구조체</span><span class="sxs-lookup"><span data-stu-id="81fe7-144">ReadOnly structs</span></span>

<span data-ttu-id="81fe7-145">특성을 통해 구조체에 추가할 <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-145">You can annotate structs with the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> attribute.</span></span> <span data-ttu-id="81fe7-146">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-146">For example:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="81fe7-147">`IsReadOnly`을 의미하지는 `Struct`않습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-147">`IsReadOnly` does not imply `Struct`.</span></span> <span data-ttu-id="81fe7-148">구조체를 `IsReadOnly` 갖려면 둘 다 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-148">You must add both to have an `IsReadOnly` struct.</span></span>

<span data-ttu-id="81fe7-149">이 특성을 사용하면 F# 및 C#이 각각 `inref<'T>` 해당 `in ref`특성과 로 처리하도록 알리는 메타데이터가 방출됩니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-149">Use of this attribute emits metadata letting F# and C# know to treat it as `inref<'T>` and `in ref`, respectively.</span></span>

<span data-ttu-id="81fe7-150">읽기 전용 구조체 내부에서 가변 값을 정의할 때 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-150">Defining a mutable value inside of a readonly struct produces an error.</span></span>

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="81fe7-151">구조기록 및 차별된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="81fe7-151">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="81fe7-152">[레코드](records.md) 및 [구별된 공용 구조체를](discriminated-unions.md) `[<Struct>]` 특성이 있는 구조체로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81fe7-152">You can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="81fe7-153">자세한 내용은 각 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="81fe7-153">See each article to learn more.</span></span>

## <a name="see-also"></a><span data-ttu-id="81fe7-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81fe7-154">See also</span></span>

- [<span data-ttu-id="81fe7-155">F # 언어 참조</span><span class="sxs-lookup"><span data-stu-id="81fe7-155">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="81fe7-156">클래스</span><span class="sxs-lookup"><span data-stu-id="81fe7-156">Classes</span></span>](classes.md)
- [<span data-ttu-id="81fe7-157">레코드</span><span class="sxs-lookup"><span data-stu-id="81fe7-157">Records</span></span>](records.md)
- [<span data-ttu-id="81fe7-158">멤버</span><span class="sxs-lookup"><span data-stu-id="81fe7-158">Members</span></span>](./members/index.md)
