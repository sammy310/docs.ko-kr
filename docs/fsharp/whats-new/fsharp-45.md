---
title: 'F # 4.5 - F # 가이드의 새로운 내용'
description: F# 4.5에서 사용할 수 있는 새로운 기능에 대한 개요를 확인하세요.
ms.date: 11/27/2019
ms.openlocfilehash: 560e3dd941f79b76d3b864ba0f6560be154ebc1a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186130"
---
# <a name="whats-new-in-f-45"></a><span data-ttu-id="50fdc-103">F # 4.5의 새로운 내용</span><span class="sxs-lookup"><span data-stu-id="50fdc-103">What's new in F# 4.5</span></span>

<span data-ttu-id="50fdc-104">F # 4.5는 F # 언어에 여러 가지 개선 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="50fdc-105">이러한 기능 중 많은 기능이 함께 추가되어 F#에서 효율적인 코드를 작성하는 동시에 이 코드의 안전도 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="50fdc-106">이렇게 하면 언어에 몇 가지 개념을 추가하고 이러한 구문에서 사용할 때 상당한 양의 컴파일러 분석을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="50fdc-107">시작하기</span><span class="sxs-lookup"><span data-stu-id="50fdc-107">Get started</span></span>

<span data-ttu-id="50fdc-108">F# 4.5는 모든 .NET 코어 배포판 및 Visual Studio 툴링에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="50fdc-109">[F#로 시작하여](../get-started/index.md) 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="50fdc-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="50fdc-110">스팬 및 바이프 와 같은 구조체</span><span class="sxs-lookup"><span data-stu-id="50fdc-110">Span and byref-like structs</span></span>

<span data-ttu-id="50fdc-111">.NET Core에 도입된 <xref:System.Span%601> 형식을 사용하면 강력한 형식의 방식으로 메모리의 버퍼를 나타낼 수 있으며, F# 4.5부터 F#에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly-typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="50fdc-112">다음 예제에서는 다른 버퍼 <xref:System.Span%601> 표현으로 에서 작동하는 함수를 다시 사용하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

```fsharp
let safeSum (bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

// managed memory
let arrayMemory = Array.zeroCreate<byte>(100)
let arraySpan = new Span<byte>(arrayMemory)

safeSum(arraySpan) |> printfn "res = %d"

// native memory
let nativeMemory = Marshal.AllocHGlobal(100);
let nativeSpan = new Span<byte>(nativeMemory.ToPointer(), 100)

safeSum(nativeSpan) |> printfn "res = %d"
Marshal.FreeHGlobal(nativeMemory)

// stack memory
let mem = NativePtr.stackalloc<byte>(100)
let mem2 = mem |> NativePtr.toVoidPtr
let stackSpan = Span<byte>(mem2, 100)

safeSum(stackSpan) |> printfn "res = %d"
```

<span data-ttu-id="50fdc-113">이에 대한 중요한 측면은 Span 및 기타 [byref와 같은 구조체가](../language-reference/structures.md#byreflike-structs) 컴파일러에서 수행되는 매우 엄격한 정적 분석을 통해 예기치 않은 방식으로 사용을 제한한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="50fdc-114">이는 F# 4.5에 도입된 성능, 표현력 및 안전 사이의 근본적인 장단점입니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="50fdc-115">개조된 바이프</span><span class="sxs-lookup"><span data-stu-id="50fdc-115">Revamped byrefs</span></span>

<span data-ttu-id="50fdc-116">F# 4.5 이전에는 F#의 [Byrefs가](../language-reference/byrefs.md) 안전하지 않고 수많은 응용 프로그램에서 소리가 나지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="50fdc-117">byrefs 주변의 건전성 문제는 F # 4.5에서 해결되었으며 스팬 및 byref와 같은 구조체에 대해 수행 된 것과 동일한 정적 분석도 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="50fdc-118">inref<> 및 아웃레프<></span><span class="sxs-lookup"><span data-stu-id="50fdc-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="50fdc-119">읽기 전용, 쓰기 전용 및 읽기/쓰기 관리 포인터의 개념을 나타내기 위해 F# `inref<'T>` `outref<'T>` 4.5는 각각 읽기 전용 및 쓰기 전용 포인터를 나타내는 의 형식을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="50fdc-120">각각 다른 의미 체계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-120">Each have different semantics.</span></span> <span data-ttu-id="50fdc-121">예를 들어 `inref<'T>`다음 을 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="50fdc-122">기본적으로 형식 추론은 이미 변경 가능한 것으로 `inref<'T>` 선언된 것이 아니면 F# 코드의 불변 특성과 일치하는 것으로 관리되는 포인터를 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="50fdc-123">쓰기 가능한 것을 만들려면 주소를 조작하는 함수 `mutable` 나 멤버에 주소를 전달하기 전에 형식을 선언해야합니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="50fdc-124">자세한 내용은 [Byrefs](../language-reference/byrefs.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="50fdc-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="50fdc-125">읽기 전용 구조체</span><span class="sxs-lookup"><span data-stu-id="50fdc-125">Readonly structs</span></span>

<span data-ttu-id="50fdc-126">F # 4.5로 시작하여 다음과 <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> 같이 구조체에 추가 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="50fdc-127">이렇게 하면 구조체에서 변경 가능한 멤버를 선언할 수 없으며 F# 및 C#이 어셈블리에서 사용할 때만 읽기로 처리되도록 하는 메타데이터를 내보페습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="50fdc-128">자세한 내용은 [ReadOnly 구조체](../language-reference/structures.md#readonly-structs)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="50fdc-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span></span>

## <a name="void-pointers"></a><span data-ttu-id="50fdc-129">보이드 포인터</span><span class="sxs-lookup"><span data-stu-id="50fdc-129">Void pointers</span></span>

<span data-ttu-id="50fdc-130">형식은 `voidptr` 다음과 같은 함수와 마찬가지로 F# 4.5에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="50fdc-131">`NativePtr.ofVoidPtr`void 포인터를 네이티브 int 포인터로 변환하려면</span><span class="sxs-lookup"><span data-stu-id="50fdc-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="50fdc-132">`NativePtr.toVoidPtr`네이티브 int 포인터를 void 포인터로 변환하려면</span><span class="sxs-lookup"><span data-stu-id="50fdc-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="50fdc-133">이 기능은 void 포인터를 사용하는 네이티브 구성 요소와 상호 운용할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="50fdc-134">`match!` 키워드</span><span class="sxs-lookup"><span data-stu-id="50fdc-134">The `match!` keyword</span></span>

<span data-ttu-id="50fdc-135">키워드는 `match!` 계산 식 내부에서 패턴 일치를 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

```fsharp
// Code that returns an asynchronous option
let checkBananaAsync (s: string) =
    async {
        if s = "banana" then
            return Some s
        else
            return None
    }

// Now you can use 'match!'
let funcWithString (s: string) =
    async {
        match! checkBananaAsync s with
        | Some bananaString -> printfn "It's banana!"
        | None -> printfn "%s" s
}
```

<span data-ttu-id="50fdc-136">이렇게 하면 비동기와 같은 계산 식과 옵션(또는 다른 형식)을 혼합하는 경우가 많은 코드를 단축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="50fdc-137">자세한 내용은 [일치를 참조하십시오!](../language-reference/computation-expressions.md#match).</span><span class="sxs-lookup"><span data-stu-id="50fdc-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="50fdc-138">배열, 목록 및 시퀀스 식에서 완화된 업캐스팅 요구 사항</span><span class="sxs-lookup"><span data-stu-id="50fdc-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="50fdc-139">배열, 목록 및 시퀀스 식의 다른 내부에서 상속할 수 있는 형식을 혼합하는 형식은 일반적으로 `:>` 파생된 형식을 부모 형식 또는 `upcast`을 사용하여 상위 형식에 업캐스트해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="50fdc-140">이것은 이제 다음과 같이 설명, 완화된다 :</span><span class="sxs-lookup"><span data-stu-id="50fdc-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="50fdc-141">배열 및 목록 식에 대한 들여쓰기 완화</span><span class="sxs-lookup"><span data-stu-id="50fdc-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="50fdc-142">F # 4.5 이전에는 메서드 호출에 인수로 전달 될 때 배열을 과도하게 들여 쓰기하고 식을 나열해야합니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="50fdc-143">더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50fdc-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
