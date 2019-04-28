---
title: Byref
description: Byref 및 byref와 유사한 형식에 대 한 자세한 F#에 낮은 수준의 프로그래밍에 사용 됩니다.
ms.date: 09/02/2018
ms.openlocfilehash: c0bad26672fbb9eb315eee1c3e275183ddeb9297
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703194"
---
# <a name="byrefs"></a><span data-ttu-id="5883f-103">Byref</span><span class="sxs-lookup"><span data-stu-id="5883f-103">Byrefs</span></span>

<span data-ttu-id="5883f-104">F#하위 수준 프로그래밍의 공간에서 처리 하는 두 가지 주요 기능 영역에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="5883f-105">합니다 `byref` / `inref` / `outref` 형식인 관리 되는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-105">The `byref`/`inref`/`outref` types, which are a managed pointers.</span></span> <span data-ttu-id="5883f-106">런타임 시 유효 하지 않은 프로그램을 컴파일할 수 있도록 사용 현황에 대 한 제한 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-106">They have restrictions on usage so that you cannot compile a program that is invalid at runtime.</span></span>
* <span data-ttu-id="5883f-107">A `byref`-인 구조체와 마찬가지로 [구조](structures.md) 비슷한 의미 체계와 같은 컴파일 시간 제한이 있는 `byref<'T>`합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="5883f-108">한 가지 예는 <xref:System.Span%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="5883f-109">구문</span><span class="sxs-lookup"><span data-stu-id="5883f-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="5883f-110">Byref, inref, 및 outref</span><span class="sxs-lookup"><span data-stu-id="5883f-110">Byref, inref, and outref</span></span>

<span data-ttu-id="5883f-111">세 가지 `byref`:</span><span class="sxs-lookup"><span data-stu-id="5883f-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="5883f-112">`inref<'T>`를 기본 값을 읽기 위한 관리 되는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="5883f-113">`outref<'T>`를 기본 값에 쓰기에 대 한 관리 되는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="5883f-114">`byref<'T>`읽기 및 쓰기는 내부 값에 대 한 관리 되는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="5883f-115">A `byref<'T>` 를 전달할 수는 `inref<'T>` 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="5883f-116">마찬가지로 `byref<'T>` 를 전달할 수는 `outref<'T>` 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="5883f-117">Byref를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="5883f-117">Using byrefs</span></span>

<span data-ttu-id="5883f-118">사용 하는 `inref<'T>`를 사용 하 여 포인터 값을 가져올 필요가 `&`:</span><span class="sxs-lookup"><span data-stu-id="5883f-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    
let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="5883f-119">사용 하 여 포인터에 대 한 작성 하는 `outref<'T>` 또는 `byref<'T>`에 대 한 포인터를 잡고 값도 확인 해야 `mutable`합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="5883f-120">읽는 대신 포인터에만 작성 하는 경우 사용을 고려 `outref<'T>` 대신 `byref<'T>`합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="5883f-121">Inref 의미 체계</span><span class="sxs-lookup"><span data-stu-id="5883f-121">Inref semantics</span></span>

<span data-ttu-id="5883f-122">다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="5883f-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="5883f-123">의미상으로 다음이 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="5883f-124">소유자는 `x` 포인터 에서만 사용할 수 값을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="5883f-125">포인터를 획득 `struct` 필드 내에 중첩 `SomeStruct` 형식이 지정 됩니다 `inref<_>`합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="5883f-126">다음 true 이기도합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-126">The following is also true:</span></span>

* <span data-ttu-id="5883f-127">더 다른 스레드가 없거나 별칭에 대 한 쓰기 없는 `x`합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="5883f-128">더입니다 `SomeStruct` 됨 변경할 수 없는 `x` 되는 `inref`합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="5883f-129">그러나 F# 값 형식에 **됩니다** 변경할 수 없는 합니다 `this` 포인터로 유추 됩니다는 `inref`합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="5883f-130">이러한 규칙을 함께 모두 의미는 보유자는 `inref` 포인터가 가리키는 메모리의 즉각적인 내용을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="5883f-131">Outref 의미 체계</span><span class="sxs-lookup"><span data-stu-id="5883f-131">Outref semantics</span></span>

<span data-ttu-id="5883f-132">목적은 `outref<'T>` 나타내는 포인터에서 읽을 수만 해야 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-132">The purpose of `outref<'T>` is to indicate that the pointer should only be read from.</span></span> <span data-ttu-id="5883f-133">예기치 않게 `outref<'T>` 이름과 달리 기본 읽기 허용 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="5883f-134">호환성을 위해입니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-134">This is for compatibility purposes.</span></span> <span data-ttu-id="5883f-135">의미상 `outref<'T>` 다르지 않습니다 `byref<'T>`합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="5883f-136">C와의 상호 운용성\#</span><span class="sxs-lookup"><span data-stu-id="5883f-136">Interop with C\#</span></span>

<span data-ttu-id="5883f-137">C# 지원 합니다 `in ref` 및 `out ref` 외에에서 키워드 `ref` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="5883f-138">다음 표는 어떻게 F# 새로운 해석 C# 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="5883f-139">C# 구문</span><span class="sxs-lookup"><span data-stu-id="5883f-139">C# construct</span></span>|<span data-ttu-id="5883f-140">F#유추</span><span class="sxs-lookup"><span data-stu-id="5883f-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="5883f-141">`ref` 반환 값</span><span class="sxs-lookup"><span data-stu-id="5883f-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="5883f-142">`ref readonly` 반환 값</span><span class="sxs-lookup"><span data-stu-id="5883f-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="5883f-143">`in ref` 매개 변수</span><span class="sxs-lookup"><span data-stu-id="5883f-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="5883f-144">`out ref` 매개 변수</span><span class="sxs-lookup"><span data-stu-id="5883f-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="5883f-145">다음 표에서 보여 줍니다 F# 를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="5883f-146">F#구문</span><span class="sxs-lookup"><span data-stu-id="5883f-146">F# construct</span></span>|<span data-ttu-id="5883f-147">내보낸된 구문</span><span class="sxs-lookup"><span data-stu-id="5883f-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="5883f-148">`inref<'T>` 인수</span><span class="sxs-lookup"><span data-stu-id="5883f-148">`inref<'T>` argument</span></span>|<span data-ttu-id="5883f-149">`[In]` 인수에는 특성</span><span class="sxs-lookup"><span data-stu-id="5883f-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="5883f-150">`inref<'T>` 반환</span><span class="sxs-lookup"><span data-stu-id="5883f-150">`inref<'T>` return</span></span>|<span data-ttu-id="5883f-151">`modreq` 특성 값을</span><span class="sxs-lookup"><span data-stu-id="5883f-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="5883f-152">`inref<'T>` 추상 슬롯 또는 구현</span><span class="sxs-lookup"><span data-stu-id="5883f-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="5883f-153">`modreq` 인수 또는 반환</span><span class="sxs-lookup"><span data-stu-id="5883f-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="5883f-154">`outref<'T>` 인수</span><span class="sxs-lookup"><span data-stu-id="5883f-154">`outref<'T>` argument</span></span>|<span data-ttu-id="5883f-155">`[Out]` 인수에는 특성</span><span class="sxs-lookup"><span data-stu-id="5883f-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="5883f-156">형식 유추 및 규칙을 오버 로드</span><span class="sxs-lookup"><span data-stu-id="5883f-156">Type inference and overloading rules</span></span>

<span data-ttu-id="5883f-157">`inref<'T>` 형식에서 유추 되는 F# 컴파일러에서 다음과 같은 경우:</span><span class="sxs-lookup"><span data-stu-id="5883f-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="5883f-158">.NET 매개 변수 또는 반환 형식에는 `IsReadOnly` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="5883f-159">`this` 변경할 수 없는 필드가 있는 구조체 형식에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="5883f-160">다른 메모리 위치의 주소를 파생 `inref<_>` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="5883f-161">때 암시적 주소는 `inref` 가져오는 동안에 형식의 인수를 사용 하 여 오버 로드 `SomeType` 형식의 인수를 사용 하 여 오버 로드에 선호 `inref<SomeType>`합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="5883f-162">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="5883f-162">For example:</span></span>

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

<span data-ttu-id="5883f-163">두 경우 모두 오버 로드가 `System.DateTime` 걸리는 오버 로드 하는 대신 해결 `inref<System.DateTime>`합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="5883f-164">Byref와 유사한 구조체</span><span class="sxs-lookup"><span data-stu-id="5883f-164">Byref-like structs</span></span>

<span data-ttu-id="5883f-165">이외에 `byref` / `inref` / `outref` 도움을 받을, 수를 준수 하는 사용자 고유의 구조체를 정의할 수 있습니다 `byref`-같은 의미 체계.</span><span class="sxs-lookup"><span data-stu-id="5883f-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="5883f-166">사용 하 여 <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> 특성:</span><span class="sxs-lookup"><span data-stu-id="5883f-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="5883f-167">`IsByRefLike` 의미 하지는 않습니다 `Struct`합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="5883f-168">두 형식에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-168">Both must be present on the type.</span></span>

<span data-ttu-id="5883f-169">"`byref`-같은" 구조체에서 F# 스택 바인딩된 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="5883f-170">관리 되는 힙에 할당 되지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="5883f-171">`byref`-같은 구조체 유용 고성능 프로그래밍에 대 한 일련의 수명 및 비캡처 하는 방법에 대 한 강력한 검사를 사용 하 여 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="5883f-172">규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-172">The rules are:</span></span>

* <span data-ttu-id="5883f-173">사용할 수 있습니다 함수 매개 변수, 메서드 매개 변수, 지역 변수, 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="5883f-174">정적 이어야 하거나 멤버 클래스 또는 일반 구조체의 인스턴스 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="5883f-175">모든 클로저 생성으로 캡처할 수 없습니다 (`async` 메서드 또는 람다 식).</span><span class="sxs-lookup"><span data-stu-id="5883f-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="5883f-176">제네릭 매개 변수로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="5883f-177">이 마지막 기능은 매우 중요 한 F# 파이프라인 스타일 프로그래밍으로 `|>` 는 해당 입력된 형식 매개 변수화 되는 제네릭 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="5883f-178">경우이 제한이 완화 될 수 있습니다 `|>` 나중에 인라인 되 고 본문에서 인라인되지 않은 제네릭 함수를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="5883f-179">이러한 규칙은 매우 강력 하 게 사용을 제한, 있지만 그렇게 안전한 방식으로 고성능 컴퓨팅의 약속을 충족 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-179">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="5883f-180">Byref 반환</span><span class="sxs-lookup"><span data-stu-id="5883f-180">Byref returns</span></span>

<span data-ttu-id="5883f-181">Byref 반환에서 F# 함수 또는 멤버 생성 및 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="5883f-182">사용 하는 경우는 `byref`-메서드를 반환 값을 암시적으로 역참조 됩니다. 합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="5883f-183">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="5883f-183">For example:</span></span>

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

<span data-ttu-id="5883f-184">여러 연결 된 호출을 통해 참조를 전달 하는 같은 암시적 역참조를 방지 하려면 `&x` (여기서 `x` 값인).</span><span class="sxs-lookup"><span data-stu-id="5883f-184">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="5883f-185">Return에 직접 할당할 수 있습니다 `byref`합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-185">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="5883f-186">다음 (항상 필수) 프로그램을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-186">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override __.ToString() = String.Join(' ', nums)

    member __.FindLargestSmallerThan(target: int) =
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

<span data-ttu-id="5883f-187">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-187">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="5883f-188">Byref에 대 한 범위 지정</span><span class="sxs-lookup"><span data-stu-id="5883f-188">Scoping for byrefs</span></span>

<span data-ttu-id="5883f-189">`let`-바인딩된 값 이전에 정의 된 범위를 초과 하는 참조를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-189">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="5883f-190">예를 들어, 다음은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-190">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="5883f-191">이를 끄거나 최적화를 사용 하 여 컴파일하는 경우에 따라 다른 결과 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5883f-191">This prevents you from getting different results depending on if you compile with optimizations on or off.</span></span>
