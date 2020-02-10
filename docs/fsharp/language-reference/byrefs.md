---
title: Byref
description: 하위 수준 프로그래밍에 사용 되는의 F#byref 및 byref와 유사한 형식에 대해 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: 2d98d325dc4ad26548fb2cc6aa5b872e152ee0a8
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092790"
---
# <a name="byrefs"></a><span data-ttu-id="555c4-103">Byref</span><span class="sxs-lookup"><span data-stu-id="555c4-103">Byrefs</span></span>

<span data-ttu-id="555c4-104">F#에는 하위 수준 프로그래밍의 공간을 처리 하는 두 가지 주요 기능 영역이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="555c4-105">`byref`/`inref``outref` /관리 되는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="555c4-106">런타임에 잘못 된 프로그램을 컴파일할 수 없도록 사용에 대 한 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="555c4-107">의미 체계가 비슷하며 `byref<'T>`와 동일한 컴파일 시간 제한이 있는 [구조인](structures.md) `byref`같은 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="555c4-108">한 가지 예는 <xref:System.Span%601>입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="555c4-109">구문</span><span class="sxs-lookup"><span data-stu-id="555c4-109">Syntax</span></span>

```fsharp
// Byref types as parameters
let f (x: byref<'T>) = ()
let g (x: inref<'T>) = ()
let h (x: outref<'T>) = ()

// Calling a function with a byref parameter
let mutable x = 3
f &x

// Declaring a byref-like struct
open System.Runtime.CompilerServices

[<Struct; IsByRefLike>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

## <a name="byref-inref-and-outref"></a><span data-ttu-id="555c4-110">Byref, inref 및 outref</span><span class="sxs-lookup"><span data-stu-id="555c4-110">Byref, inref, and outref</span></span>

<span data-ttu-id="555c4-111">다음과 같은 세 가지 형식의 `byref`있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="555c4-112">`inref<'T>`내부 값을 읽기 위한 관리 되는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="555c4-113">`outref<'T>`기본 값에 쓰기 위한 관리 되는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="555c4-114">기본 값을 읽고 쓰기 위한 관리 되는 포인터인 `byref<'T>`입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="555c4-115">`byref<'T>` `inref<'T>` 필요한 위치에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="555c4-116">마찬가지로 `outref<'T>` 필요한 위치에 `byref<'T>`를 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="555c4-117">Byref 배열과 같은 사용</span><span class="sxs-lookup"><span data-stu-id="555c4-117">Using byrefs</span></span>

<span data-ttu-id="555c4-118">`inref<'T>`을 사용 하려면 `&`를 사용 하 여 포인터 값을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="555c4-119">`outref<'T>` 또는 `byref<'T>`를 사용 하 여 포인터에 쓰려면 `mutable`포인터를 가져오는 값도 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

<span data-ttu-id="555c4-120">포인터를 읽는 대신만 작성 하는 경우에는 `byref<'T>`대신 `outref<'T>`를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="555c4-121">Inref 의미 체계</span><span class="sxs-lookup"><span data-stu-id="555c4-121">Inref semantics</span></span>

<span data-ttu-id="555c4-122">다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="555c4-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="555c4-123">의미 체계가 며,이는 다음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="555c4-124">`x` 포인터의 소유자는이 값만 사용 하 여 값을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="555c4-125">`SomeStruct` 내에 중첩 된 `struct` 필드를 가져오는 모든 포인터에는 `inref<_>`형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="555c4-126">다음도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-126">The following is also true:</span></span>

* <span data-ttu-id="555c4-127">다른 스레드나 별칭에는 `x`에 대 한 쓰기 권한이 없다는 의미는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="555c4-128">`inref``x` 덕분에 `SomeStruct`를 변경할 수 없다는 의미는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="555c4-129">그러나 변경할 수 F# **없는 값** 형식의 경우 `this` 포인터는 `inref`으로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="555c4-130">이러한 모든 규칙은 `inref` 포인터의 소유자가 가리키는 메모리의 즉시 콘텐츠를 수정할 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="555c4-131">Outref 의미 체계</span><span class="sxs-lookup"><span data-stu-id="555c4-131">Outref semantics</span></span>

<span data-ttu-id="555c4-132">`outref<'T>` 목적은 포인터를에만 써야 함을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="555c4-133">예기치 않게 `outref<'T>`는 이름에도 불구 하 고 기본 값을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="555c4-134">이는 호환성을 위해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-134">This is for compatibility purposes.</span></span> <span data-ttu-id="555c4-135">의미 체계가 `outref<'T>` `byref<'T>`와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="555c4-136">C\# 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="555c4-136">Interop with C\#</span></span>

<span data-ttu-id="555c4-137">C#`ref` 반환 하는 것 외에도 `in ref` 및 `out ref` 키워드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="555c4-138">다음 표에서는에서 내보내는 F# 항목 C# 을 해석 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="555c4-139">C#구축</span><span class="sxs-lookup"><span data-stu-id="555c4-139">C# construct</span></span>|<span data-ttu-id="555c4-140">F#어떻게</span><span class="sxs-lookup"><span data-stu-id="555c4-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="555c4-141">반환 값 `ref`</span><span class="sxs-lookup"><span data-stu-id="555c4-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="555c4-142">반환 값 `ref readonly`</span><span class="sxs-lookup"><span data-stu-id="555c4-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="555c4-143">`in ref` 매개 변수</span><span class="sxs-lookup"><span data-stu-id="555c4-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="555c4-144">`out ref` 매개 변수</span><span class="sxs-lookup"><span data-stu-id="555c4-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="555c4-145">다음 표에서는 내보내는 항목 F# 을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="555c4-146">F#구축</span><span class="sxs-lookup"><span data-stu-id="555c4-146">F# construct</span></span>|<span data-ttu-id="555c4-147">내보낸 구문</span><span class="sxs-lookup"><span data-stu-id="555c4-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="555c4-148">`inref<'T>` 인수</span><span class="sxs-lookup"><span data-stu-id="555c4-148">`inref<'T>` argument</span></span>|<span data-ttu-id="555c4-149">인수의 `[In]` 특성</span><span class="sxs-lookup"><span data-stu-id="555c4-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="555c4-150">반환 `inref<'T>`</span><span class="sxs-lookup"><span data-stu-id="555c4-150">`inref<'T>` return</span></span>|<span data-ttu-id="555c4-151">값의 `modreq` 특성</span><span class="sxs-lookup"><span data-stu-id="555c4-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="555c4-152">추상 슬롯 또는 구현에서 `inref<'T>`</span><span class="sxs-lookup"><span data-stu-id="555c4-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="555c4-153">인수에 `modreq` 또는 반환</span><span class="sxs-lookup"><span data-stu-id="555c4-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="555c4-154">`outref<'T>` 인수</span><span class="sxs-lookup"><span data-stu-id="555c4-154">`outref<'T>` argument</span></span>|<span data-ttu-id="555c4-155">인수의 `[Out]` 특성</span><span class="sxs-lookup"><span data-stu-id="555c4-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="555c4-156">형식 유추 및 오버 로드 규칙</span><span class="sxs-lookup"><span data-stu-id="555c4-156">Type inference and overloading rules</span></span>

<span data-ttu-id="555c4-157">다음 경우에는 F# 컴파일러에서 `inref<'T>` 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="555c4-158">`IsReadOnly` 특성이 있는 .NET 매개 변수 또는 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="555c4-159">변경할 필드가 없는 구조체 형식의 `this` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="555c4-160">다른 `inref<_>` 포인터에서 파생 된 메모리 위치의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="555c4-161">`inref`의 암시적 주소를 사용 하는 경우 `inref<SomeType>`형식의 인수를 사용 하는 오버 로드에 `SomeType` 형식의 인수를 사용 하는 오버 로드를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="555c4-162">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-162">For example:</span></span>

```fsharp
type C() =
    static member M(x: System.DateTime) = x.AddDays(1.0)
    static member M(x: inref<System.DateTime>) = x.AddDays(2.0)
    static member M2(x: System.DateTime, y: int) = x.AddDays(1.0)
    static member M2(x: inref<System.DateTime>, y: int) = x.AddDays(2.0)

let res = System.DateTime.Now
let v =  C.M(res)
let v2 =  C.M2(res, 4)
```

<span data-ttu-id="555c4-163">두 경우 모두 `System.DateTime`를 수행 하는 오버 로드는 `inref<System.DateTime>`를 수행 하는 오버 로드가 아니라 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="555c4-164">Byref와 유사한 구조체</span><span class="sxs-lookup"><span data-stu-id="555c4-164">Byref-like structs</span></span>

<span data-ttu-id="555c4-165">`outref` 3 개 숫자 /`inref``byref`/외에도 `byref`와 유사한 의미 체계를 따를 수 있는 고유한 구조체를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="555c4-166"><xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> 특성을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="555c4-167">`IsByRefLike`은 `Struct`을 의미 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="555c4-168">둘 다 형식에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-168">Both must be present on the type.</span></span>

<span data-ttu-id="555c4-169">의 F# "`byref`유사" 구조체는 스택 바인딩된 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="555c4-170">이는 관리 되는 힙에 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="555c4-171">`byref`같은 구조체는 수명 및 비 캡처에 대 한 강력한 검사 집합으로 적용 되므로 고성능 프로그래밍에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="555c4-172">규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-172">The rules are:</span></span>

* <span data-ttu-id="555c4-173">함수 매개 변수, 메서드 매개 변수, 지역 변수, 메서드 반환으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="555c4-174">클래스 또는 일반 구조체의 정적 또는 인스턴스 멤버일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="555c4-175">이러한 메서드는 클로저 구문 (`async` 메서드 또는 람다 식)에서 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="555c4-176">제네릭 매개 변수로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="555c4-177">이 마지막 지점은 `|>`가 입력 F# 형식을 매개 변수화 하는 제네릭 함수 이기 때문에 파이프라인 스타일 프로그래밍에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="555c4-178">이 제한은 인라인으로 `|>` 나중에 완화 될 수 있으며 본문에서 인라인 되지 않은 제네릭 함수를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="555c4-179">이러한 규칙은 사용을 강력 하 게 제한 하지만 안전 하 게 고성능 컴퓨팅의 약속을 달성 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="555c4-180">Byref 반환</span><span class="sxs-lookup"><span data-stu-id="555c4-180">Byref returns</span></span>

<span data-ttu-id="555c4-181">Byref는 함수 F# 또는 멤버를 생성 하 고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="555c4-182">`byref`반환 메서드를 사용 하는 경우이 값은 암시적으로 역참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="555c4-183">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) = 
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

<span data-ttu-id="555c4-184">Byref 값을 반환 하려면 값을 포함 하는 변수가 현재 범위 보다 오래 지속 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-184">To return a value byref, the variable that contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="555c4-185">또한 byref를 반환 하려면 `&value`을 사용 합니다. 여기서 value는 현재 범위 보다 오래 지속 되는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-185">Also, to return byref, use `&value` (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="555c4-186">여러 개의 연결 된 호출을 통해 참조를 전달 하는 것과 같이 암시적 역참조를 방지 하려면 `&x`을 사용 합니다. 여기서 `x`는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="555c4-187">반환 `byref`에 직접 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="555c4-188">다음 (매우 명령적) 프로그램을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-188">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override _.ToString() = String.Join(' ', nums)

    member _.FindLargestSmallerThan(target: int) =
        let mutable ctr = nums.Length - 1

        while ctr > 0 && nums.[ctr] >= target do ctr <- ctr - 1

        if ctr > 0 then &nums.[ctr] else &nums.[0]

[<EntryPoint>]
let main argv =
    let c = C()
    printfn "Original sequence: %s" (c.ToString())

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn "New sequence:      %s" (c.ToString())

    0 // return an integer exit code
```

<span data-ttu-id="555c4-189">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="555c4-190">Byref 배열과 같은에 대 한 범위 지정</span><span class="sxs-lookup"><span data-stu-id="555c4-190">Scoping for byrefs</span></span>

<span data-ttu-id="555c4-191">`let`바인딩된 값은 해당 참조가 정의 된 범위를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="555c4-192">예를 들어 다음은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-192">For example, the following is disallowed:</span></span>

```fsharp
let test2 () =
    let x = 12
    &x // Error: 'x' exceeds its defined scope!

let test () =
    let x =
        let y = 1
        &y // Error: `y` exceeds its defined scope!
    ()
```

<span data-ttu-id="555c4-193">이렇게 하면 최적화를 사용 하 여 컴파일하는 경우에 따라 다른 결과를 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="555c4-193">This prevents you from getting different results depending on if you compile with optimizations or not.</span></span>
