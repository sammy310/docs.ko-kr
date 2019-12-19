---
title: 4\.5의 F# 새로운 기능- F# 가이드
description: 4\.5에서 F# 사용할 수 있는 새 기능에 대 한 개요를 확인 하세요.
ms.date: 11/27/2019
ms.openlocfilehash: 780b33a564432aae5ec99c70ff8620988b553fd1
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644159"
---
# <a name="whats-new-in-f-45"></a><span data-ttu-id="d4440-103">4\.5의 F# 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="d4440-103">What's new in F# 4.5</span></span>

<span data-ttu-id="d4440-104">F#4.5는 언어에 대 한 F# 여러 가지 향상 된 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="d4440-105">이러한 기능 중 상당수가 함께 추가 되어 코드를 안전 하 게 유지 하면서 F# 도에서 효율적인 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="d4440-106">이렇게 하면 이러한 구문을 사용 하는 경우 언어에 대 한 몇 가지 개념과 많은 양의 컴파일러 분석이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="d4440-107">시작</span><span class="sxs-lookup"><span data-stu-id="d4440-107">Get started</span></span>

<span data-ttu-id="d4440-108">F#4.5는 모든 .NET Core 배포 및 Visual Studio 도구에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="d4440-109">를 [시작 F# ](../get-started/index.md) 하 여 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d4440-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="d4440-110">Span 및 byref와 유사한 구조체</span><span class="sxs-lookup"><span data-stu-id="d4440-110">Span and byref-like structs</span></span>

<span data-ttu-id="d4440-111">.NET Core에 도입 된 <xref:System.Span%601> 형식을 사용 하면 메모리의 버퍼를 강력한 형식의 방식으로 나타낼 수 있으며, 이제 F# F# 4.5부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly-typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="d4440-112">다음 예에서는 다른 버퍼 표현으로 <xref:System.Span%601>에서 작동 하는 함수를 다시 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

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

<span data-ttu-id="d4440-113">이에 대 한 중요 한 측면은 범위 및 기타 [byref와 비슷한 구조체](../language-reference/structures.md#byreflike-structs) 에는 예기치 않은 방식으로 사용을 제한 하는 컴파일러에서 매우 엄격한 정적 분석이 수행 된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="d4440-114">4\.5에 F# 도입 된 성능, 표현을 및 보안 간의 기본적인 단점입니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="d4440-115">개선 된 byref 배열과 같은</span><span class="sxs-lookup"><span data-stu-id="d4440-115">Revamped byrefs</span></span>

<span data-ttu-id="d4440-116">4\.5 이전에는 여러 응용 F# 프로그램에 대 한 [byref](../language-reference/byrefs.md) 배열과 같은가 안전 하지 않으며 소리가 들리지 않았습니다.  F#</span><span class="sxs-lookup"><span data-stu-id="d4440-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="d4440-117">Byref 배열과 같은에 대 한 적합성 문제는 4.5 F# 에서 해결 되었으며, 범위 및 byref와 비슷한 구조체에 대해 수행 되는 동일한 정적 분석도 적용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="d4440-118">inref < ' > 및 outref < ' t e m ></span><span class="sxs-lookup"><span data-stu-id="d4440-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="d4440-119">읽기 전용, 쓰기 전용 및 읽기/쓰기 관리 되는 포인터의 개념을 나타내기 위해 F# 4.5에는 각각 읽기 전용 및 쓰기 전용 포인터를 나타내기 위해 `inref<'T>``outref<'T>` 형식이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="d4440-120">각에는 서로 다른 의미 체계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-120">Each have different semantics.</span></span> <span data-ttu-id="d4440-121">예를 들어 `inref<'T>`에 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="d4440-122">기본적으로 형식 유추는 변경 되지 않은 것으로 선언 된 경우를 제외 하 고는 변경 불가능 F# 한 코드 특성을 사용 하 여 `inref<'T>`으로 관리 되는 포인터를 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="d4440-123">쓰기 가능한 항목을 만들려면 해당 주소를 조작 하는 함수 또는 멤버에 해당 주소를 전달 하기 전에 형식을 `mutable`로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="d4440-124">자세히 알아보려면 [byref 배열과 같은](../language-reference/byrefs.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4440-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="d4440-125">읽기 전용 구조체</span><span class="sxs-lookup"><span data-stu-id="d4440-125">Readonly structs</span></span>

<span data-ttu-id="d4440-126">F# 4.5부터 다음과 같이 <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute>를 사용 하 여 구조체에 주석을 달 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="d4440-127">이렇게 하면 구조체에서 변경 가능한 멤버를 선언 하 고 어셈블리에서 사용 될 때 F# 및 C# 를 readonly로 처리할 수 있는 메타 데이터를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="d4440-128">자세히 알아보려면 [ReadOnly 구조체](../language-reference/structures.md#readonly-structs) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4440-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs)</span></span>

## <a name="void-pointers"></a><span data-ttu-id="d4440-129">Void 포인터</span><span class="sxs-lookup"><span data-stu-id="d4440-129">Void pointers</span></span>

<span data-ttu-id="d4440-130">`voidptr` 형식은 다음 함수와 같이 4.5 F# 에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="d4440-131">void 포인터를 네이티브 int 포인터로 변환 `NativePtr.ofVoidPtr`</span><span class="sxs-lookup"><span data-stu-id="d4440-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="d4440-132">네이티브 int 포인터를 void 포인터로 변환 `NativePtr.toVoidPtr`</span><span class="sxs-lookup"><span data-stu-id="d4440-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="d4440-133">이는 void 포인터를 사용 하는 네이티브 구성 요소와 상호 작용할 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="d4440-134">`match!` 키워드</span><span class="sxs-lookup"><span data-stu-id="d4440-134">The `match!` keyword</span></span>

<span data-ttu-id="d4440-135">`match!` 키워드는 계산 식 내부에서 패턴 일치를 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

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

<span data-ttu-id="d4440-136">이를 통해 옵션 (또는 기타 형식)을 async와 같은 계산 식과 혼합 하는 코드를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="d4440-137">자세히 알아보려면 [일치!](../language-reference/computation-expressions.md#match)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4440-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="d4440-138">배열, 목록 및 시퀀스 식의 완화 업캐스팅 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4440-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="d4440-139">배열, 목록 및 시퀀스 식의 내부에서 상속할 수 있는 형식을 혼합 하는 것은 `:>` 또는 `upcast`를 사용 하 여 파생 형식을 부모 형식으로 업 캐스트 하는 데 일반적으로 필요 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="d4440-140">이제 다음과 같이 완화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="d4440-141">배열 및 목록 식에 대 한 들여쓰기 완화</span><span class="sxs-lookup"><span data-stu-id="d4440-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="d4440-142">F# 4.5 이전에는 메서드 호출에 인수로 전달 될 때 배열 및 목록 식을 과도 하 게 들여쓰는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="d4440-143">더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting = 
    System.Console.WriteLine(format="{0}", arg = [| 
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
