---
title: 구조체
description: 에 대 한 자세한는 F# 구조체, 종종 간단한 개체 형식으로 적은 양의 데이터 적고 동작이 단순한 형식에 대해 클래스 보다 더 효율적입니다.
ms.date: 05/16/2016
ms.openlocfilehash: c091dc91765d6e828426de21e9bc5f79bfdebc6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925881"
---
# <a name="structures"></a><span data-ttu-id="53d20-103">구조체</span><span class="sxs-lookup"><span data-stu-id="53d20-103">Structures</span></span>

<span data-ttu-id="53d20-104">A *구조* 적은 양의 데이터 적고 동작이 단순한 형식에 대 한 클래스 보다 효율적일 수 있는 간단한 개체 형식인 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="53d20-105">구문</span><span class="sxs-lookup"><span data-stu-id="53d20-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="53d20-106">설명</span><span class="sxs-lookup"><span data-stu-id="53d20-106">Remarks</span></span>

<span data-ttu-id="53d20-107">구조체가 *값 형식*, 즉, 스택에 직접 또는으로 사용 되는 저장 된 필드 또는 배열 요소를 부모에 대 한 인라인 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="53d20-108">클래스나 레코드와 달리 구조체는 pass-by-value 의미 체계를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="53d20-109">따라서 기본적으로 자주 액세스 및 복사하는 소규모 데이터 집계에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="53d20-110">위 구문에는 두 개의 폼이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="53d20-111">첫 번째는 간단한 구문은 아니지만 자주 사용됩니다. `struct` 및 `end` 키워드를 사용하는 경우 두 번째 구문에 나와 있는 `StructAttribute` 특성을 생략할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="53d20-112">즉, `StructAttribute`를 `Struct`로 간략하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="53d20-113">합니다 *형식-정의-요소-및-멤버* 이전 구문에서 멤버 선언 및 정의 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-113">The *type-definition-elements-and-members* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="53d20-114">구조체는 생성자 및 변경 가능/불가능한 필드를 포함할 수 있으며 멤버 및 인터페이스 구현을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="53d20-115">자세한 내용은 [멤버](members/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-115">For more information, see [Members](members/index.md).</span></span>

<span data-ttu-id="53d20-116">구조체는 상속에 참가할 수 없고, `let` 또는 `do` 바인딩을 포함할 수 없으며, 자신의 형식으로 된 필드를 재귀적으로 포함할 수 없습니다. 그러나 자신의 형식을 참조하는 참조 셀은 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="53d20-117">구조체는 `let` 바인딩을 허용하지 않으므로 구조체에서는 `val` 키워드를 사용하여 필드를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="53d20-118">`val` 키워드는 필드와 해당 형식을 정의하지만 초기화는 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="53d20-119">대신 `val` 선언이 null 또는 0으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="53d20-120">따라서 암시적 생성자(선언에서 구조체 이름 바로 뒤에 지정되는 매개 변수)를 포함하는 구조체에서는 `val` 선언을 `DefaultValue` 특성으로 주석 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="53d20-121">정의된 생성자가 있는 구조체도 0으로의 초기화를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="53d20-122">그러므로 `DefaultValue` 특성은 이러한 0 값이 필드에 유효함을 나타내는 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="53d20-123">구조체의 암시적 생성자는 아무런 작업도 수행하지 않습니다. 해당 형식에 대해서는 `let` 및 `do` 바인딩이 허용되지 않지만 전달되는 암시적 생성자 매개 변수 값은 개인 필드로 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="53d20-124">명시적 생성자에서는 필드 값이 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="53d20-125">명시적 생성자를 포함하는 구조체는 0으로의 초기화도 지원합니다. 그러나 `DefaultValue` 선언에서 `val` 특성을 사용하는 경우 명시적 생성자와 충돌하므로 해당 특성은 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="53d20-126">에 대 한 자세한 내용은 `val` 선언을 참조 [명시적 필드: 합니다 `val` 키워드](members/explicit-fields-the-val-keyword.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="53d20-127">특성 및 액세스 가능성 한정자는 구조체에서 허용되며 다른 형식과 동일한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="53d20-128">자세한 내용은 [특성](attributes.md) 하 고 [Access Control](access-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="53d20-129">다음 코드 예제에서는 구조체 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a><span data-ttu-id="53d20-130">ByRefLike 구조체</span><span class="sxs-lookup"><span data-stu-id="53d20-130">ByRefLike structs</span></span>

<span data-ttu-id="53d20-131">수를 준수 하는 사용자 고유의 구조체를 정의할 수 있습니다 `byref`-같은 의미 체계: 참조 [Byref](byrefs.md) 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-131">You can define your own structs that can adhere to `byref`-like semantics: see [Byrefs](byrefs.md) for more information.</span></span> <span data-ttu-id="53d20-132">사용 하 여 <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> 특성:</span><span class="sxs-lookup"><span data-stu-id="53d20-132">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="53d20-133">`IsByRefLike` 의미 하지는 않습니다 `Struct`합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-133">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="53d20-134">두 형식에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-134">Both must be present on the type.</span></span>

<span data-ttu-id="53d20-135">"`byref`-같은" 구조체에서 F# 스택 바인딩된 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-135">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="53d20-136">관리 되는 힙에 할당 되지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-136">It is never allocated on the managed heap.</span></span> <span data-ttu-id="53d20-137">`byref`-같은 구조체 유용 고성능 프로그래밍에 대 한 일련의 수명 및 비캡처 하는 방법에 대 한 강력한 검사를 사용 하 여 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-137">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="53d20-138">규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-138">The rules are:</span></span>

* <span data-ttu-id="53d20-139">사용할 수 있습니다 함수 매개 변수, 메서드 매개 변수, 지역 변수, 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-139">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="53d20-140">정적 이어야 하거나 멤버 클래스 또는 일반 구조체의 인스턴스 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-140">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="53d20-141">모든 클로저 생성으로 캡처할 수 없습니다 (`async` 메서드 또는 람다 식).</span><span class="sxs-lookup"><span data-stu-id="53d20-141">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="53d20-142">제네릭 매개 변수로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-142">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="53d20-143">이러한 규칙은 매우 강력 하 게 사용을 제한, 있지만 그렇게 안전한 방식으로 고성능 컴퓨팅의 약속을 충족 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-143">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="53d20-144">읽기 전용 구조체</span><span class="sxs-lookup"><span data-stu-id="53d20-144">ReadOnly structs</span></span>

<span data-ttu-id="53d20-145">구조체를 사용 하 여 주석을 추가할 수는 <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-145">You can annotate structs with the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> attribute.</span></span> <span data-ttu-id="53d20-146">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="53d20-146">For example:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="53d20-147">`IsReadOnly` 의미 하지는 않습니다 `Struct`합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-147">`IsReadOnly` does not imply `Struct`.</span></span> <span data-ttu-id="53d20-148">모두 추가 해야는 `IsReadOnly` 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-148">You must add both to have an `IsReadOnly` struct.</span></span>

<span data-ttu-id="53d20-149">이 특성을 사용 하는 메타 데이터 수 있도록 내보냅니다 F# 및 C# 로 처리할 알고 `inref<'T>` 하 고 `in ref`각각.</span><span class="sxs-lookup"><span data-stu-id="53d20-149">Use of this attribute emits metadata letting F# and C# know to treat it as `inref<'T>` and `in ref`, respectively.</span></span>

<span data-ttu-id="53d20-150">읽기 전용 구조체 내에서 변경할 수 있는 값을 정의 했는데 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-150">Defining a mutable value inside of a readonly struct produces an error.</span></span>

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="53d20-151">구조체 레코드 및 구분 된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="53d20-151">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="53d20-152">나타낼 수 있습니다 [레코드](records.md) 하 고 [구별 된 공용 구조체](discriminated-unions.md) 사용 하 여 구조체로 `[<Struct>]` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="53d20-152">You can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="53d20-153">자세한 내용은 각 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53d20-153">See each article to learn more.</span></span>

## <a name="see-also"></a><span data-ttu-id="53d20-154">참고자료</span><span class="sxs-lookup"><span data-stu-id="53d20-154">See also</span></span>

- [<span data-ttu-id="53d20-155">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="53d20-155">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="53d20-156">클래스</span><span class="sxs-lookup"><span data-stu-id="53d20-156">Classes</span></span>](classes.md)
- [<span data-ttu-id="53d20-157">레코드</span><span class="sxs-lookup"><span data-stu-id="53d20-157">Records</span></span>](records.md)
- [<span data-ttu-id="53d20-158">멤버</span><span class="sxs-lookup"><span data-stu-id="53d20-158">Members</span></span>](members/index.md)