---
title: 형식 확장
description: 형식 확장 F# 을 사용 하 여 이전에 정의한 개체 형식에 새 멤버를 추가 하는 방법을 알아봅니다.
ms.date: 02/05/2020
ms.openlocfilehash: 9ab3a007783f67fd8d80cff840ac3085fdcd60f7
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092683"
---
# <a name="type-extensions"></a><span data-ttu-id="e609d-103">형식 확장</span><span class="sxs-lookup"><span data-stu-id="e609d-103">Type extensions</span></span>

<span data-ttu-id="e609d-104">형식 확장명 ( _확대_이 라고도 함)은 이전에 정의 된 개체 형식에 새 멤버를 추가할 수 있는 기능 패밀리입니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="e609d-105">세 가지 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-105">The three features are:</span></span>

- <span data-ttu-id="e609d-106">내장 형식 확장</span><span class="sxs-lookup"><span data-stu-id="e609d-106">Intrinsic type extensions</span></span>
- <span data-ttu-id="e609d-107">선택적 형식 확장</span><span class="sxs-lookup"><span data-stu-id="e609d-107">Optional type extensions</span></span>
- <span data-ttu-id="e609d-108">확장 메서드</span><span class="sxs-lookup"><span data-stu-id="e609d-108">Extension methods</span></span>

<span data-ttu-id="e609d-109">각각 서로 다른 시나리오에서 사용할 수 있으며 서로 다른 장단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="e609d-110">구문</span><span class="sxs-lookup"><span data-stu-id="e609d-110">Syntax</span></span>

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [<Extension>]
    static member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="e609d-111">내장 형식 확장</span><span class="sxs-lookup"><span data-stu-id="e609d-111">Intrinsic type extensions</span></span>

<span data-ttu-id="e609d-112">내장 형식 확장은 사용자 정의 형식을 확장 하는 형식 확장명입니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="e609d-113">내장 형식 확장은 확장 하는 형식과 동일한 파일 **및** 네임 스페이스 또는 모듈에서 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="e609d-114">다른 모든 정의는 [선택적 형식 확장이](type-extensions.md#optional-type-extensions)됩니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="e609d-115">형식 선언에서 기능을 분리 하는 것이 기본 형식 확장의 경우에 따라 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="e609d-116">다음 예제에서는 내장 형식 확장을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-116">The following example shows how to define an intrinsic type extension:</span></span>

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

<span data-ttu-id="e609d-117">형식 확장을 사용 하면 다음을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-117">Using a type extension allows you to separate each of the following:</span></span>

- <span data-ttu-id="e609d-118">`Variant` 형식의 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-118">The declaration of a `Variant` type</span></span>
- <span data-ttu-id="e609d-119">"셰이프"에 따라 `Variant` 클래스를 인쇄 하는 기능</span><span class="sxs-lookup"><span data-stu-id="e609d-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
- <span data-ttu-id="e609d-120">개체 스타일 `.`표기법으로 인쇄 기능에 액세스 하는 방법</span><span class="sxs-lookup"><span data-stu-id="e609d-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="e609d-121">이는 `Variant`의 멤버로 모든 항목을 정의 하는 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="e609d-122">본질적으로 더 나은 방법은 아니지만 일부 상황에서 기능을 보다 명확 하 게 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="e609d-123">내장 형식 확장은 사용자가 확장 하는 형식의 멤버로 컴파일되며 리플렉션을 통해 형식을 검사할 때 형식에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="e609d-124">선택적 형식 확장</span><span class="sxs-lookup"><span data-stu-id="e609d-124">Optional type extensions</span></span>

<span data-ttu-id="e609d-125">선택적 형식 확장은 확장 중인 형식의 원래 모듈, 네임 스페이스 또는 어셈블리 외부에 표시 되는 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="e609d-126">선택적 형식 확장은 직접 정의 하지 않은 형식을 확장 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="e609d-127">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-127">For example:</span></span>

```fsharp
module Extensions

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for _ in 1 .. n -> x
        }
```

<span data-ttu-id="e609d-128">이제 `Extensions` 모듈이 작업 중인 범위에서 열려 있는 한 <xref:System.Collections.Generic.IEnumerable%601>의 멤버인 것 처럼 `RepeatElements`에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="e609d-129">리플렉션을 통해 검사할 때 확장 형식에는 선택적 확장이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="e609d-130">선택적 확장은 모듈에 있어야 하며 확장을 포함 하는 모듈이 열려 있거나 달리 범위에 있는 경우에만 범위에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="e609d-131">선택적 확장 멤버는 개체 인스턴스가 첫 번째 매개 변수로 암시적으로 전달 되는 정적 멤버로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="e609d-132">그러나 이러한 사용자는 선언 된 방법에 따라 인스턴스 멤버 또는 정적 멤버인 것 처럼 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

<span data-ttu-id="e609d-133">선택적 확장 멤버도 또는 Visual Basic 소비자에 게 C# 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-133">Optional extension members are also not visible to C# or Visual Basic consumers.</span></span> <span data-ttu-id="e609d-134">다른 F# 코드 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-134">They can only be consumed in other F# code.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="e609d-135">내장 및 선택적 형식 확장의 일반적인 제한 사항</span><span class="sxs-lookup"><span data-stu-id="e609d-135">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="e609d-136">형식 변수가 제한 되는 제네릭 형식에 대해 형식 확장을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-136">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="e609d-137">요구 사항은 확장 선언의 제약 조건이 선언 된 형식의 제약 조건과 일치 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-137">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="e609d-138">그러나 제약 조건이 선언 된 형식과 형식 확장명 사이에 일치 하는 경우에도 선언 된 형식에 비해 형식 매개 변수에 대해 다른 요구 사항을 적용 하는 확장 멤버의 본문에서 제약 조건을 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-138">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="e609d-139">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-139">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="e609d-140">선택적 형식 확장을 사용 하 여이 코드를 가져올 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-140">There is no way to get this code to work with an optional type extension:</span></span>

- <span data-ttu-id="e609d-141">`Sum` 멤버는 형식 확장에서 정의 하는 것과 `'T` (`static member get_Zero` 및 `static member (+)`)에 대해 다른 제약 조건을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-141">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
- <span data-ttu-id="e609d-142">`Sum`와 동일한 제약 조건을 갖도록 형식 확장을 수정 하면 `IEnumerable<'T>`에 대해 정의 된 제약 조건과 더 이상 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-142">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
- <span data-ttu-id="e609d-143">`member inline this.Sum` `member this.Sum`를 변경 하면 형식 제약 조건이 일치 하지 않는 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-143">Changing `member this.Sum` to `member inline this.Sum` will give an error that type constraints are mismatched.</span></span>

<span data-ttu-id="e609d-144">필요한 것은 "공간에 배치" 되 고 형식을 확장 하는 것 처럼 표시 될 수 있는 정적 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-144">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="e609d-145">여기서는 확장 메서드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-145">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="e609d-146">확장 메서드</span><span class="sxs-lookup"><span data-stu-id="e609d-146">Extension methods</span></span>

<span data-ttu-id="e609d-147">마지막으로, 확장 메서드 ("C# 스타일 확장 멤버" 라고도 함)를 클래스의 F# 정적 멤버 메서드로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-147">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="e609d-148">확장 메서드는 형식 변수를 제약 하는 제네릭 형식에 대 한 확장을 정의 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-148">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="e609d-149">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-149">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="e609d-150">이 코드를 사용 하면 `Extensions`가 열리거나 범위 내에 있는 한 <xref:System.Collections.Generic.IEnumerable%601>에 `Sum` 정의 된 것 처럼 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-150">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

<span data-ttu-id="e609d-151">VB.NET 코드에 확장을 사용할 수 있도록 하려면 어셈블리 수준에서 추가 `ExtensionAttribute` 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-151">For the extension to be available to VB.NET code, an extra `ExtensionAttribute` is required at the assembly level:</span></span>

```fsharp
module AssemblyInfo
open System.Runtime.CompilerServices
[<assembly:Extension>]
do ()
```

## <a name="other-remarks"></a><span data-ttu-id="e609d-152">기타 설명</span><span class="sxs-lookup"><span data-stu-id="e609d-152">Other remarks</span></span>

<span data-ttu-id="e609d-153">형식 확장에는 다음과 같은 특성도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-153">Type extensions also have the following attributes:</span></span>

- <span data-ttu-id="e609d-154">액세스할 수 있는 모든 형식을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-154">Any type that can be accessed can be extended.</span></span>
- <span data-ttu-id="e609d-155">내장 함수와 선택적 형식 확장은 메서드 뿐 _아니라 멤버 형식을_ 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-155">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="e609d-156">따라서 확장명 속성도 가능 합니다 (예:).</span><span class="sxs-lookup"><span data-stu-id="e609d-156">So extension properties are also possible, for example.</span></span>
- <span data-ttu-id="e609d-157">[구문의](type-extensions.md#syntax) `self-identifier` 토큰은 일반 멤버와 마찬가지로 호출 중인 형식의 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-157">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
- <span data-ttu-id="e609d-158">확장 멤버는 정적 또는 인스턴스 멤버일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-158">Extended members can be static or instance members.</span></span>
- <span data-ttu-id="e609d-159">형식 확장의 형식 변수는 선언 된 형식의 제약 조건과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-159">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="e609d-160">형식 확장에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-160">The following limitations also exist for type extensions:</span></span>

- <span data-ttu-id="e609d-161">형식 확장은 가상 또는 추상 메서드를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-161">Type extensions do not support virtual or abstract methods.</span></span>
- <span data-ttu-id="e609d-162">형식 확장은 재정의 메서드를 확대으로 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-162">Type extensions do not support override methods as augmentations.</span></span>
- <span data-ttu-id="e609d-163">형식 확장은 정적으로 [확인 된 형식 매개 변수](./generics/statically-resolved-type-parameters.md)를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-163">Type extensions do not support [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>
- <span data-ttu-id="e609d-164">선택적 형식 확장은 확대로 생성자를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-164">Optional Type extensions do not support constructors as augmentations.</span></span>
- <span data-ttu-id="e609d-165">형식 [약어](type-abbreviations.md)에는 형식 확장을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-165">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
- <span data-ttu-id="e609d-166">형식 확장을 선언할 수는 있지만 `byref<'T>`에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-166">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
- <span data-ttu-id="e609d-167">형식 확장은 선언 될 수 있지만 특성에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-167">Type extensions are not valid for attributes (though they can be declared).</span></span>
- <span data-ttu-id="e609d-168">같은 이름의 다른 메서드를 오버 로드 하는 확장을 정의할 수 있지만 모호한 F# 호출이 있는 경우 컴파일러는 비 확장 메서드에 대 한 우선 순위를 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-168">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="e609d-169">마지막으로 한 형식에 대해 여러 개의 내장 형식 확장이 있는 경우 모든 멤버가 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-169">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="e609d-170">선택적 형식 확장의 경우 동일한 형식에 대 한 다른 형식 확장의 멤버는 동일한 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-170">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="e609d-171">모호성 오류는 클라이언트 코드가 동일한 멤버 이름을 정의 하는 두 개의 서로 다른 범위를 연 경우에만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e609d-171">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="e609d-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e609d-172">See also</span></span>

- [<span data-ttu-id="e609d-173">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="e609d-173">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e609d-174">멤버</span><span class="sxs-lookup"><span data-stu-id="e609d-174">Members</span></span>](./members/index.md)
