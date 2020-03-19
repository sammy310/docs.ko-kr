---
title: Byref
description: 낮은 수준의 프로그래밍에 사용되는 F#에서 byref 및 byref와 같은 형식에 대해 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: 527f465ee87fe153a2deae1306b6730531dc4123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187045"
---
# <a name="byrefs"></a><span data-ttu-id="e0e41-103">Byref</span><span class="sxs-lookup"><span data-stu-id="e0e41-103">Byrefs</span></span>

<span data-ttu-id="e0e41-104">F# 낮은 수준의 프로그래밍의 공간에서 다루는 두 가지 주요 기능 영역이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="e0e41-105">`byref` / 관리되는 `outref` 포인터인 형식입니다. `inref` /</span><span class="sxs-lookup"><span data-stu-id="e0e41-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="e0e41-106">런타임에 유효하지 않은 프로그램을 컴파일할 수 없도록 사용 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="e0e41-107">`byref`-like struct는 의미체계와 컴파일 타임 제한이 비슷한 [구조입니다.](structures.md) `byref<'T>`</span><span class="sxs-lookup"><span data-stu-id="e0e41-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="e0e41-108">한 가지 <xref:System.Span%601>예는 .</span><span class="sxs-lookup"><span data-stu-id="e0e41-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="e0e41-109">구문</span><span class="sxs-lookup"><span data-stu-id="e0e41-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="e0e41-110">바이레프, 인레프, 아웃레프</span><span class="sxs-lookup"><span data-stu-id="e0e41-110">Byref, inref, and outref</span></span>

<span data-ttu-id="e0e41-111">세 가지 형태가 `byref`있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="e0e41-112">`inref<'T>`- 기본 값을 읽기 위한 관리되는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="e0e41-113">`outref<'T>`- 기본 값에 쓰기 위한 관리되는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="e0e41-114">`byref<'T>`- 기본 값을 읽고 쓰기 위한 관리되는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="e0e41-115">`inref<'T>` A는 `byref<'T>` 예상되는 곳에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="e0e41-116">마찬가지로 a가 `byref<'T>` 예상되는 곳에 `outref<'T>` 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="e0e41-117">바이레프 사용</span><span class="sxs-lookup"><span data-stu-id="e0e41-117">Using byrefs</span></span>

<span data-ttu-id="e0e41-118">을 `inref<'T>`사용하려면 `&`다음과 같은 포인터 값을 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="e0e41-119">또는 를 사용하여 포인터에 쓰려면 `mutable`에 대한 포인터를 잡는 값도 만들어야 합니다. `byref<'T>` `outref<'T>`</span><span class="sxs-lookup"><span data-stu-id="e0e41-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="e0e41-120">포인터를 읽는 대신 포인터만 쓰는 경우 `outref<'T>` 을 `byref<'T>`사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="e0e41-121">인레프 의미론</span><span class="sxs-lookup"><span data-stu-id="e0e41-121">Inref semantics</span></span>

<span data-ttu-id="e0e41-122">다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="e0e41-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="e0e41-123">의미상, 이것은 다음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="e0e41-124">`x` 포인터의 홀더는 값을 읽는 데만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="e0e41-125">내에 `struct` `SomeStruct` 중첩된 필드에 대해 획득한 `inref<_>`모든 포인터에는 형식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="e0e41-126">다음은 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-126">The following is also true:</span></span>

* <span data-ttu-id="e0e41-127">다른 스레드 또는 별칭에 쓰기 액세스 권한이 없다는 `x`의미는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="e0e41-128">`inref`. `SomeStruct` `x`</span><span class="sxs-lookup"><span data-stu-id="e0e41-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="e0e41-129">그러나 변경할 수 없는 **are** F# 값 형식의 경우 포인터는 `this` `inref`로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="e0e41-130">이러한 모든 규칙은 `inref` 포인터 의 소유자가 가리키는 메모리의 즉각적인 내용을 수정하지 않을 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="e0e41-131">아웃레프 의미론</span><span class="sxs-lookup"><span data-stu-id="e0e41-131">Outref semantics</span></span>

<span data-ttu-id="e0e41-132">그 `outref<'T>` 목적은 포인터만 작성해야 함을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="e0e41-133">예기치 `outref<'T>` 않게 이름에도 불구하고 기본 값을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="e0e41-134">이는 호환성을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-134">This is for compatibility purposes.</span></span> <span data-ttu-id="e0e41-135">시상적으로, `outref<'T>` 와 다르지 `byref<'T>`않다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="e0e41-136">C와 인터롭\#</span><span class="sxs-lookup"><span data-stu-id="e0e41-136">Interop with C\#</span></span>

<span data-ttu-id="e0e41-137">C#은 `in ref` `out ref` `ref` 반품 외에도 및 키워드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="e0e41-138">다음 표에서는 F#이 C#이 내하는 것을 해석하는 방법을 보여 주십습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="e0e41-139">C# 구문</span><span class="sxs-lookup"><span data-stu-id="e0e41-139">C# construct</span></span>|<span data-ttu-id="e0e41-140">F # 추론</span><span class="sxs-lookup"><span data-stu-id="e0e41-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="e0e41-141">`ref`반환 값</span><span class="sxs-lookup"><span data-stu-id="e0e41-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="e0e41-142">`ref readonly`반환 값</span><span class="sxs-lookup"><span data-stu-id="e0e41-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="e0e41-143">`in ref` 매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0e41-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="e0e41-144">`out ref` 매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0e41-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="e0e41-145">다음 표에서는 F#이 내는지 보여 주십을 보여 주십습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="e0e41-146">F# 구문</span><span class="sxs-lookup"><span data-stu-id="e0e41-146">F# construct</span></span>|<span data-ttu-id="e0e41-147">내보낸 구문</span><span class="sxs-lookup"><span data-stu-id="e0e41-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="e0e41-148">`inref<'T>` 인수</span><span class="sxs-lookup"><span data-stu-id="e0e41-148">`inref<'T>` argument</span></span>|<span data-ttu-id="e0e41-149">`[In]`인수에 속성</span><span class="sxs-lookup"><span data-stu-id="e0e41-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="e0e41-150">`inref<'T>`반환</span><span class="sxs-lookup"><span data-stu-id="e0e41-150">`inref<'T>` return</span></span>|<span data-ttu-id="e0e41-151">`modreq`값에 속성</span><span class="sxs-lookup"><span data-stu-id="e0e41-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="e0e41-152">`inref<'T>`추상 슬롯 또는 구현</span><span class="sxs-lookup"><span data-stu-id="e0e41-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="e0e41-153">`modreq`인수 또는 반환 시</span><span class="sxs-lookup"><span data-stu-id="e0e41-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="e0e41-154">`outref<'T>` 인수</span><span class="sxs-lookup"><span data-stu-id="e0e41-154">`outref<'T>` argument</span></span>|<span data-ttu-id="e0e41-155">`[Out]`인수에 속성</span><span class="sxs-lookup"><span data-stu-id="e0e41-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="e0e41-156">형식 추론 및 오버로드 규칙</span><span class="sxs-lookup"><span data-stu-id="e0e41-156">Type inference and overloading rules</span></span>

<span data-ttu-id="e0e41-157">`inref<'T>` 다음과 같은 경우 형식은 F# 컴파일러에 의해 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="e0e41-158">.NET 매개 변수 또는 특성이 있는 return 형식입니다. `IsReadOnly`</span><span class="sxs-lookup"><span data-stu-id="e0e41-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="e0e41-159">변경할 `this` 수 있는 필드가 없는 구조체 형식의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="e0e41-160">다른 `inref<_>` 포인터에서 파생된 메모리 위치의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="e0e41-161">an의 `inref` 암시적 주소를 취할 때 형식 `SomeType` 인수가 있는 오버로드는 형식 `inref<SomeType>`인수가 있는 오버로드에 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="e0e41-162">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-162">For example:</span></span>

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

<span data-ttu-id="e0e41-163">두 경우 모두 을 `System.DateTime` 받는 오버로드가 아닌 인차지 하는 오버로드가 `inref<System.DateTime>`해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="e0e41-164">바이레프와 같은 구조체</span><span class="sxs-lookup"><span data-stu-id="e0e41-164">Byref-like structs</span></span>

<span data-ttu-id="e0e41-165">`byref` / `inref` / 트리오 외에도 의미와 같은 의미체계를 준수할 수 있는 `byref`고유한 구조체를 정의할 수 있습니다. `outref`</span><span class="sxs-lookup"><span data-stu-id="e0e41-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="e0e41-166">이 작업은 다음과 <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> 같은 특성으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="e0e41-167">`IsByRefLike`을 의미하지는 `Struct`않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="e0e41-168">둘 다 형식에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-168">Both must be present on the type.</span></span>

<span data-ttu-id="e0e41-169">F#의 "-like"`byref`구조체는 스택 바인딩된 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="e0e41-170">관리되는 힙에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="e0e41-171">`byref`-like 구조체는 수명 및 비캡처에 대한 강력한 검사 집합으로 적용되기 때문에 고성능 프로그래밍에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="e0e41-172">규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-172">The rules are:</span></span>

* <span data-ttu-id="e0e41-173">함수 매개 변수, 메서드 매개 변수, 로컬 변수, 메서드 반환으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="e0e41-174">정적 또는 인스턴스 멤버가 클래스 또는 일반 구조체일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="e0e41-175">모든 클로저 구문(메서드`async` 또는 람다 식)에 의해 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="e0e41-176">일반 매개 변수로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="e0e41-177">이 마지막 지점은 입력 형식을 매개변수화하는 제네릭 함수와 마찬가지로 `|>` F# 파이프라인 스타일 프로그래밍에 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="e0e41-178">이 제한은 인라인이며 본문에 인라인되지 않은 제네릭 함수를 호출하지 않으므로 나중에 완화될 `|>` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="e0e41-179">이러한 규칙은 사용을 강력하게 제한하지만 안전한 방식으로 고성능 컴퓨팅의 약속을 이행하기 위해 그렇게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="e0e41-180">바이레프 반환</span><span class="sxs-lookup"><span data-stu-id="e0e41-180">Byref returns</span></span>

<span data-ttu-id="e0e41-181">Byref F# 함수 또는 멤버에서 반환 생성 하 고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="e0e41-182">-returning `byref`메서드를 사용 하는 경우 값이 암시적으로 디레참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="e0e41-183">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

<span data-ttu-id="e0e41-184">값 byref를 반환하려면 값을 포함하는 변수가 현재 범위보다 오래 유지되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-184">To return a value byref, the variable that contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="e0e41-185">또한 byref를 반환하려면 `&value` (값이 현재 범위보다 오래 사는 변수인 경우)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-185">Also, to return byref, use `&value` (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="e0e41-186">여러 개의 체인 호출을 통해 참조를 전달하는 것과 같은 `&x` 암시적 디레퍼런스를 방지하려면 (값은 어디에) `x` 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0e41-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="e0e41-187">반환에 `byref`직접 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="e0e41-188">다음과 같은(매우 명령적인) 프로그램을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0e41-188">Consider the following (highly imperative) program:</span></span>

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

<span data-ttu-id="e0e41-189">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="e0e41-190">바이레프에 대한 범위 지정</span><span class="sxs-lookup"><span data-stu-id="e0e41-190">Scoping for byrefs</span></span>

<span data-ttu-id="e0e41-191">`let`-bound 값은 참조가 정의된 범위를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="e0e41-192">예를 들어 다음을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-192">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="e0e41-193">이렇게 하면 최적화를 통해 컴파일하는지 여부에 따라 다른 결과를 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e41-193">This prevents you from getting different results depending on if you compile with optimizations or not.</span></span>
