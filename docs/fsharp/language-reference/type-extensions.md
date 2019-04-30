---
title: 형식 확장
description: 에 대해 알아봅니다 하는 방법 F# 형식 확장을 이용 하면 이전에 정의 된 개체 형식에 새 멤버를 추가 합니다.
ms.date: 02/08/2019
ms.openlocfilehash: 69fb3b771b5334c5771f2ac75341b38c1dad5b90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982607"
---
# <a name="type-extensions"></a><span data-ttu-id="0962c-103">형식 확장명</span><span class="sxs-lookup"><span data-stu-id="0962c-103">Type extensions</span></span>

<span data-ttu-id="0962c-104">형식 확장명 (라고도 _확대_)은 이전에 정의 된 개체 형식에 새 멤버를 추가할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="0962c-105">세 가지 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-105">The three features are:</span></span>

* <span data-ttu-id="0962c-106">기본 형식 확장</span><span class="sxs-lookup"><span data-stu-id="0962c-106">Intrinsic type extensions</span></span>
* <span data-ttu-id="0962c-107">선택적 형식 확장</span><span class="sxs-lookup"><span data-stu-id="0962c-107">Optional type extensions</span></span>
* <span data-ttu-id="0962c-108">확장 메서드</span><span class="sxs-lookup"><span data-stu-id="0962c-108">Extension methods</span></span>

<span data-ttu-id="0962c-109">각 다양 한 시나리오에서 사용할 수 있고 다른 절충 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="0962c-110">구문</span><span class="sxs-lookup"><span data-stu-id="0962c-110">Syntax</span></span>

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
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="0962c-111">기본 형식 확장</span><span class="sxs-lookup"><span data-stu-id="0962c-111">Intrinsic type extensions</span></span>

<span data-ttu-id="0962c-112">내장 형식 확장은 사용자 정의 형식을 확장 하는 형식 확장.</span><span class="sxs-lookup"><span data-stu-id="0962c-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="0962c-113">기본 형식 확장이 동일한 파일에 정의 되어야 합니다 **및** 동일한 네임 스페이스 또는 확장 되는 해당 형식으로는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="0962c-114">다른 정의 해도 되 [선택적 형식 확장의](type-extensions.md#optional-type-extensions)합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="0962c-115">내장 형식 확장은 경우에 따라 형식 선언에서 기능을 분리 하는 깔끔한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="0962c-116">다음 예제에서는 내장 형식 확장을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-116">The following example shows how to define an intrinsic type extension:</span></span>

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

<span data-ttu-id="0962c-117">형식 확장을 사용 하 여 다음의 각 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-117">Using a type extension allows you to separate each of the following:</span></span>

* <span data-ttu-id="0962c-118">선언의 한 `Variant` 형식</span><span class="sxs-lookup"><span data-stu-id="0962c-118">The declaration of a `Variant` type</span></span>
* <span data-ttu-id="0962c-119">인쇄 하는 기능을 `Variant` "모양"에 따라 클래스</span><span class="sxs-lookup"><span data-stu-id="0962c-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
* <span data-ttu-id="0962c-120">개체 스타일을 사용 하 여 인쇄 기능에 액세스 하는 방법을 `.`-표기법</span><span class="sxs-lookup"><span data-stu-id="0962c-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="0962c-121">이의 모든 멤버를 정의 하는 대신 `Variant`합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="0962c-122">하지 않으면 기본적으로 더 나은 접근 방식을 상황에 따라 기능의 클리너 표현 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="0962c-123">기본 형식 확장을 보강 하며 리플렉션을 통해 형식을 검사할 때 형식에 나타나는 형식의 멤버로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="0962c-124">선택적 형식 확장</span><span class="sxs-lookup"><span data-stu-id="0962c-124">Optional type extensions</span></span>

<span data-ttu-id="0962c-125">선택적 형식 확장에는 원래 모듈, 네임 스페이스 또는 확장 되는 형식의 어셈블리 외부에 표시 되는 확장이입니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="0962c-126">선택적 형식 확장의 직접 정의 하지 않은 형식을 확장 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="0962c-127">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="0962c-127">For example:</span></span>

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

<span data-ttu-id="0962c-128">이제 액세스할 수 있습니다 `RepeatElements` 의 멤버인 것 처럼 <xref:System.Collections.Generic.IEnumerable%601> 으로 `Extensions` 모듈에서 작업 하는 범위에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="0962c-129">선택적 확장 리플렉션을 통해 검사 하는 경우 확장된 형식에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="0962c-130">확장 모듈 이어야 하며 있을 때만 범위 확장을 포함 하는 모듈 열려 또는 그렇지 않은 경우 범위는 경우에 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="0962c-131">선택적 확장 멤버는 정적 멤버는 개체 인스턴스를 암시적으로 매개 변수로 전달 되는 첫 번째 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="0962c-132">그러나 인스턴스 멤버 또는 선언 하는 방법에 따라 정적 멤버인 것 처럼 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

<span data-ttu-id="0962c-133">선택적 확장 멤버도 표시 되지 않습니다 C# 또는 VB 소비자입니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-133">Optional extension members are also not visible to C# or VB consumers.</span></span> <span data-ttu-id="0962c-134">다른만 사용할 수 있습니다 F# 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-134">They can only be consumed in other F# code.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="0962c-135">기본 및 선택적 형식 확장의 일반 제한 사항</span><span class="sxs-lookup"><span data-stu-id="0962c-135">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="0962c-136">형식 변수가 제한 되는 제네릭 형식에 형식 확장을 선언 하는 것이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-136">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="0962c-137">요구 사항 확장 선언의 제약 조건이 선언 된 형식의 제약 조건과 일치 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-137">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="0962c-138">그러나 제약 조건이 선언된 된 형식 사이의 형식 확장을 일치 하는 경우에 있기 제약 조건의 형식 매개 변수에 선언 된 형식 보다 다양 한 요구 사항을 적용 하는 확장된 멤버의 본문에서 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-138">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="0962c-139">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="0962c-139">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="0962c-140">이 코드는 선택적 형식 확장을 사용 하는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-140">There is no way to get this code to work with an optional type extension:</span></span>

* <span data-ttu-id="0962c-141">그대로 합니다 `Sum` 멤버 다양 한 제약 조건을 갖기 `'T` (`static member get_Zero` 및 `static member (+)`) 형식 확장을 정의 하는 보다.</span><span class="sxs-lookup"><span data-stu-id="0962c-141">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
* <span data-ttu-id="0962c-142">형식 확장으로 동일한 제약 조건이 수정 `Sum` 더 이상 일치 하지 정의 된 제약 조건에서 `IEnumerable<'T>`합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-142">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
* <span data-ttu-id="0962c-143">변경 `member this.Sum` 에 `member inline this.Sum` 형식 제약 조건이 일치 하지 않으면 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-143">Changing `member this.Sum` to `member inline this.Sum` will give an error that type constraints are mismatched.</span></span>

<span data-ttu-id="0962c-144">경우 원하는 정적 메서드는 "공간에서 부동" 및 형식을 확장 하는 것 처럼 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-144">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="0962c-145">확장 메서드 필요할입니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-145">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="0962c-146">확장 메서드</span><span class="sxs-lookup"><span data-stu-id="0962c-146">Extension methods</span></span>

<span data-ttu-id="0962c-147">마지막으로, 확장 메서드 (라고도 "C# 확장 멤버 스타일")에서 선언할 수 있습니다 F# 클래스의 정적 멤버 메서드로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-147">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="0962c-148">확장 메서드는 제네릭 형식 변수를 제한 하는 형식에 확장을 정의 하려는 경우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-148">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="0962c-149">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="0962c-149">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="0962c-150">를 사용 하면이 코드는 표시 되도록 처럼 `Sum` 에 정의 된 <xref:System.Collections.Generic.IEnumerable%601>. 단, `Extensions` 열린 또는 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-150">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

## <a name="other-remarks"></a><span data-ttu-id="0962c-151">다른 설명</span><span class="sxs-lookup"><span data-stu-id="0962c-151">Other remarks</span></span>

<span data-ttu-id="0962c-152">형식 확장명 다음 특성도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-152">Type extensions also have the following attributes:</span></span>

* <span data-ttu-id="0962c-153">액세스할 수 있는 모든 형식을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-153">Any type that can be accessed can be extended.</span></span>
* <span data-ttu-id="0962c-154">기본 및 선택적 형식 확장을 정의할 수 있습니다 _모든_ 멤버 유형, 뿐 아니라 메서드.</span><span class="sxs-lookup"><span data-stu-id="0962c-154">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="0962c-155">확장 속성은 예를 들어도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-155">So extension properties are also possible, for example.</span></span>
* <span data-ttu-id="0962c-156">`self-identifier` 토큰을 [구문](type-extensions.md#syntax) 일반 멤버와 마찬가지로 호출 되는 형식의 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-156">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
* <span data-ttu-id="0962c-157">확장 된 멤버 인스턴스 멤버 또는 정적 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-157">Extended members can be static or instance members.</span></span>
* <span data-ttu-id="0962c-158">형식 확장의 형식이 변수 선언 된 형식의 제약 조건 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-158">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="0962c-159">형식 확장에 대 한 다음과 같은 제한 사항이 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-159">The following limitations also exist for type extensions:</span></span>

* <span data-ttu-id="0962c-160">형식 확장에서 가상 또는 추상 메서드를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-160">Type extensions do not support virtual or abstract methods.</span></span>
* <span data-ttu-id="0962c-161">형식 확장명 확대도 재정의 메서드를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-161">Type extensions do not support override methods as augmentations.</span></span>
* <span data-ttu-id="0962c-162">형식 확장을 지원 하지 않습니다 [정적으로 확인 한 형식 매개](generics/statically-resolved-type-parameters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-162">Type extensions do not support [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>
* <span data-ttu-id="0962c-163">선택적 형식 확장 확대도 생성자를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-163">Optional Type extensions do not support constructors as augmentations.</span></span>
* <span data-ttu-id="0962c-164">에 형식 확장을 정의할 수 없습니다 [형식 약어](type-abbreviations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-164">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
* <span data-ttu-id="0962c-165">형식 확장에 대해 올바르지 않습니다. `byref<'T>` (경우에 선언 될 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="0962c-165">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
* <span data-ttu-id="0962c-166">(경우에 선언 될 수 있습니다) 형식 확장 특성에 대해 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-166">Type extensions are not valid for attributes (though they can be declared).</span></span>
* <span data-ttu-id="0962c-167">동일한 이름의 다른 메서드 오버 로드 하는 확장을 정의할 수 있지만 F# 모호한 호출이 발생할 경우 컴파일러에서 확장 되지 않은 메서드에 우선권을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-167">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="0962c-168">마지막으로, 한 형식에 대 한 여러 기본 형식 확장이 존재 하는 경우 모든 구성원은 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-168">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="0962c-169">동일한 형식으로 서로 다른 형식 확장의 멤버는 선택적 형식 확장에 대 한 이름과 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-169">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="0962c-170">모호성 오류가 클라이언트 코드는 동일한 멤버 이름을 정의 하는 두 개의 서로 다른 범위를가 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0962c-170">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="0962c-171">참고자료</span><span class="sxs-lookup"><span data-stu-id="0962c-171">See also</span></span>

- [<span data-ttu-id="0962c-172">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="0962c-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0962c-173">멤버</span><span class="sxs-lookup"><span data-stu-id="0962c-173">Members</span></span>](members/index.md)
