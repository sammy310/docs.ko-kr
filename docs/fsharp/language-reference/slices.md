---
title: 조각
description: '기존 F # 데이터 형식에 대 한 조각을 사용 하는 방법 및 다른 데이터 형식에 대 한 사용자 고유의 조각을 정의 하는 방법을 알아봅니다.'
ms.date: 12/23/2019
ms.openlocfilehash: a3920ad9e1b205b506aaee92c4606bcebf94feba
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557079"
---
# <a name="slices"></a><span data-ttu-id="bb53b-103">조각</span><span class="sxs-lookup"><span data-stu-id="bb53b-103">Slices</span></span>

<span data-ttu-id="bb53b-104">F #에서 조각은 `GetSlice` 해당 정의 또는 범위 내 [형식 확장](type-extensions.md)에서 메서드를 포함 하는 모든 데이터 형식의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-104">In F#, a slice is a subset of any data type that has a `GetSlice` method in its definition or in an in-scope [type extension](type-extensions.md).</span></span> <span data-ttu-id="bb53b-105">F # 배열 및 목록과 가장 일반적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-105">It is most commonly used with F# arrays and lists.</span></span> <span data-ttu-id="bb53b-106">이 문서에서는 기존 F # 형식에서 조각을 가져오는 방법 및 사용자 고유의 조각을 정의 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-106">This article explains how to take slices from existing F# types and how to define your own slices.</span></span>

<span data-ttu-id="bb53b-107">조각은 [인덱서와](./members/indexed-properties.md)비슷하지만 기본 데이터 구조에서 단일 값을 생성 하는 대신 여러 개를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-107">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="bb53b-108">F #에는 현재 조각화 문자열, 목록, 배열 및 2D 배열에 대 한 기본 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="bb53b-109">F # 목록 및 배열을 사용 하 여 기본 조각화</span><span class="sxs-lookup"><span data-stu-id="bb53b-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="bb53b-110">가장 일반적으로 분리 되는 데이터 형식은 F # 목록 및 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="bb53b-111">다음 예제에서는 목록을 사용 하 여이 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-111">The following example demonstrates how to do this with lists:</span></span>

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

<span data-ttu-id="bb53b-112">조각화 된 배열을 조각화 목록 처럼 분리 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-112">Slicing arrays is just like slicing lists:</span></span>

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="bb53b-113">다차원 배열 조각화</span><span class="sxs-lookup"><span data-stu-id="bb53b-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="bb53b-114">F #은 F # 핵심 라이브러리의 다차원 배열을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="bb53b-115">1 차원 배열과 마찬가지로 다차원 배열의 조각이 유용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="bb53b-116">그러나 추가 차원의 도입은 특정 행과 열의 조각을 가져올 수 있도록 약간 다른 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="bb53b-117">다음 예제에서는 2D 배열을 조각화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-117">The following examples demonstrate how to slice a 2D array:</span></span>

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn "Full matrix:\n %A" A

// Take the first row
let row0 = A.[0,*]
printfn "Row 0: %A" row0

// Take the first column
let col0 = A.[*,0]
printfn "Column 0: %A" col0

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn "%A" subA

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn "%A" subA'

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn "%A" twoByTwo
```

<span data-ttu-id="bb53b-118">F # 핵심 라이브러리는 현재 3D 배열을 정의 하지 않습니다 `GetSlice` .</span><span class="sxs-lookup"><span data-stu-id="bb53b-118">The F# core library does not currently define `GetSlice` for 3D arrays.</span></span> <span data-ttu-id="bb53b-119">3D 배열 또는 다른 차원의 다른 배열을 조각화 하려는 경우 `GetSlice` 멤버를 직접 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-119">If you wish to slice 3D arrays or other arrays of more dimensions, define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="bb53b-120">다른 데이터 구조에 대 한 조각 정의</span><span class="sxs-lookup"><span data-stu-id="bb53b-120">Defining slices for other data structures</span></span>

<span data-ttu-id="bb53b-121">F # 핵심 라이브러리는 제한 된 형식 집합에 대 한 조각을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="bb53b-122">더 많은 데이터 형식에 대 한 조각을 정의 하려는 경우 형식 정의 자체 나 형식 확장에서이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="bb53b-123">예를 들어, <xref:System.ArraySegment%601> 편리한 데이터 조작을 허용 하기 위해 클래스의 조각을 정의 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(start, finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

<span data-ttu-id="bb53b-124">및 유형을 사용 하는 다른 예는 <xref:System.Span%601> <xref:System.ReadOnlySpan%601> 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-124">Another example using the <xref:System.Span%601> and <xref:System.ReadOnlySpan%601> types:</span></span>

```fsharp
open System

type ReadOnlySpan<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

type Span<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..3] // |2; 3|]
```

## <a name="built-in-f-slices-are-end-inclusive"></a><span data-ttu-id="bb53b-125">기본 제공 F # 조각은 끝이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-125">Built-in F# slices are end-inclusive</span></span>

<span data-ttu-id="bb53b-126">F #의 모든 내장 조각이 끝에 포함 됩니다. 즉, 상한이 조각에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-126">All intrinsic slices in F# are end-inclusive; that is, the upper bound is included in the slice.</span></span> <span data-ttu-id="bb53b-127">시작 인덱스 및 끝 인덱스를 포함 하는 지정 된 조각에 대해 `x` `y` *yth* 값이 결과 조각에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-127">For a given slice with starting index `x` and ending index `y`, the resulting slice will include the *yth* value.</span></span>

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="built-in-f-empty-slices"></a><span data-ttu-id="bb53b-128">기본 제공 F # 빈 조각</span><span class="sxs-lookup"><span data-stu-id="bb53b-128">Built-in F# empty slices</span></span>

<span data-ttu-id="bb53b-129">구문에서 존재 하지 않는 조각을 생성할 수 있는 경우 F # 목록, 배열, 시퀀스, 문자열, 2D 배열, 3D 배열 및 4D 배열이 모두 빈 조각을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-129">F# lists, arrays, sequences, strings, 2D arrays, 3D arrays, and 4D arrays will all produce an empty slice if the syntax could produce a slice that doesn't exist.</span></span>

<span data-ttu-id="bb53b-130">다음을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="bb53b-130">Consider the following:</span></span>

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

let emptyList = l.[-2..(-1)]
let emptyArray = a.[-2..(-1)]
let emptyString = s.[-2..(-1)]
```

<span data-ttu-id="bb53b-131">C # 개발자는 빈 조각을 생성 하는 대신 예외를 throw 하는 것으로 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-131">C# developers may expect these to throw an exception rather than produce an empty slice.</span></span> <span data-ttu-id="bb53b-132">이는 빈 컬렉션이 F #에서 작성 한다는 사실을 기반으로 하는 디자인 결정입니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-132">This is a design decision rooted in the fact that empty collections compose in F#.</span></span> <span data-ttu-id="bb53b-133">빈 F # 목록을 다른 F # 목록으로 구성 하거나, 빈 문자열을 기존 문자열에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-133">An empty F# list can be composed with another F# list, an empty string can be added to an existing string, and so on.</span></span> <span data-ttu-id="bb53b-134">매개 변수로 전달 된 값을 기반으로 조각을 가져오고, F # 코드의 compositional 특성과 일치 하는 빈 컬렉션을 생성 하 여 범위를 벗어나는 것을 허용 하는 것이 일반적 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-134">It can be common to take slices based on values passed in as parameters, and being tolerant of out-of-bounds by producing an empty collection fits with the compositional nature of F# code.</span></span>

## <a name="fixed-index-slices-for-3d-and-4d-arrays"></a><span data-ttu-id="bb53b-135">3D 및 4D 배열의 고정 인덱스 조각</span><span class="sxs-lookup"><span data-stu-id="bb53b-135">Fixed-index slices for 3D and 4D arrays</span></span>

<span data-ttu-id="bb53b-136">F # 3D 및 4D 배열의 경우 특정 인덱스를 "수정" 하 고 해당 인덱스가 고정 된 다른 차원을 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-136">For F# 3D and 4D arrays, you can "fix" a particular index and slice other dimensions with that index fixed.</span></span>

<span data-ttu-id="bb53b-137">이를 설명 하기 위해 다음 3D 배열을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-137">To illustrate this, consider the following 3D array:</span></span>

<span data-ttu-id="bb53b-138">*z = 0*</span><span class="sxs-lookup"><span data-stu-id="bb53b-138">*z = 0*</span></span>
| <span data-ttu-id="bb53b-139">x\y</span><span class="sxs-lookup"><span data-stu-id="bb53b-139">x\y</span></span>   | <span data-ttu-id="bb53b-140">0</span><span class="sxs-lookup"><span data-stu-id="bb53b-140">0</span></span> | <span data-ttu-id="bb53b-141">1</span><span class="sxs-lookup"><span data-stu-id="bb53b-141">1</span></span> |
|-------|---|---|
| <span data-ttu-id="bb53b-142">**0**</span><span class="sxs-lookup"><span data-stu-id="bb53b-142">**0**</span></span> | <span data-ttu-id="bb53b-143">0</span><span class="sxs-lookup"><span data-stu-id="bb53b-143">0</span></span> | <span data-ttu-id="bb53b-144">1</span><span class="sxs-lookup"><span data-stu-id="bb53b-144">1</span></span> |
| <span data-ttu-id="bb53b-145">**1**</span><span class="sxs-lookup"><span data-stu-id="bb53b-145">**1**</span></span> | <span data-ttu-id="bb53b-146">2</span><span class="sxs-lookup"><span data-stu-id="bb53b-146">2</span></span> | <span data-ttu-id="bb53b-147">3</span><span class="sxs-lookup"><span data-stu-id="bb53b-147">3</span></span> |

<span data-ttu-id="bb53b-148">*z = 1*</span><span class="sxs-lookup"><span data-stu-id="bb53b-148">*z = 1*</span></span>
| <span data-ttu-id="bb53b-149">x\y</span><span class="sxs-lookup"><span data-stu-id="bb53b-149">x\y</span></span>   | <span data-ttu-id="bb53b-150">0</span><span class="sxs-lookup"><span data-stu-id="bb53b-150">0</span></span> | <span data-ttu-id="bb53b-151">1</span><span class="sxs-lookup"><span data-stu-id="bb53b-151">1</span></span> |
|-------|---|---|
| <span data-ttu-id="bb53b-152">**0**</span><span class="sxs-lookup"><span data-stu-id="bb53b-152">**0**</span></span> | <span data-ttu-id="bb53b-153">4</span><span class="sxs-lookup"><span data-stu-id="bb53b-153">4</span></span> | <span data-ttu-id="bb53b-154">5</span><span class="sxs-lookup"><span data-stu-id="bb53b-154">5</span></span> |
| <span data-ttu-id="bb53b-155">**1**</span><span class="sxs-lookup"><span data-stu-id="bb53b-155">**1**</span></span> | <span data-ttu-id="bb53b-156">6</span><span class="sxs-lookup"><span data-stu-id="bb53b-156">6</span></span> | <span data-ttu-id="bb53b-157">7</span><span class="sxs-lookup"><span data-stu-id="bb53b-157">7</span></span> |

<span data-ttu-id="bb53b-158">배열에서 조각을 추출 하려면 `[| 4; 5 |]` 고정 인덱스 조각을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-158">If you want to extract the slice `[| 4; 5 |]` from the array, use a fixed-index slice.</span></span>

```fsharp
let dim = 2
let m = Array3D.zeroCreate<int> dim dim dim

let mutable count = 0

for z in 0..dim-1 do
    for y in 0..dim-1 do
        for x in 0..dim-1 do
            m.[x,y,z] <- count
            count <- count + 1

// Now let's get the [4;5] slice!
m.[*, 0, 1]
```

<span data-ttu-id="bb53b-159">마지막 줄은 `y` `z` 3d 배열의 및 인덱스를 수정 하 고 `x` 행렬에 해당 하는 값의 나머지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb53b-159">The last line fixes the `y` and `z` indicies of the 3D array and takes the rest of the `x` values that correspond to the matrix.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb53b-160">참조</span><span class="sxs-lookup"><span data-stu-id="bb53b-160">See also</span></span>

- [<span data-ttu-id="bb53b-161">인덱싱된 속성</span><span class="sxs-lookup"><span data-stu-id="bb53b-161">Indexed properties</span></span>](./members/indexed-properties.md)
