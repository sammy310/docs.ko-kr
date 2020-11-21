---
title: 조각
description: '기존 F # 데이터 형식에 대 한 조각을 사용 하는 방법 및 다른 데이터 형식에 대 한 사용자 고유의 조각을 정의 하는 방법을 알아봅니다.'
ms.date: 11/20/2020
ms.openlocfilehash: 9c072648ed46ae29871f2be5cc64b493f6a9b857
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95098959"
---
# <a name="slices"></a><span data-ttu-id="9b86c-103">조각</span><span class="sxs-lookup"><span data-stu-id="9b86c-103">Slices</span></span>

<span data-ttu-id="9b86c-104">이 문서에서는 기존 F # 형식에서 조각을 가져오는 방법 및 사용자 고유의 조각을 정의 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-104">This article explains how to take slices from existing F# types and how to define your own slices.</span></span>

<span data-ttu-id="9b86c-105">F #에서 조각은 모든 데이터 형식의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-105">In F#, a slice is a subset of any data type.</span></span>  <span data-ttu-id="9b86c-106">조각은 [인덱서와](./members/indexed-properties.md)비슷하지만 기본 데이터 구조에서 단일 값을 생성 하는 대신 여러 개를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-106">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span> <span data-ttu-id="9b86c-107">조각은 `..` 연산자 구문을 사용 하 여 데이터 형식에서 지정 된 인덱스의 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-107">Slices use the `..` operator syntax to select the range of specified indices in a data type.</span></span> <span data-ttu-id="9b86c-108">자세한 내용은 [반복 식 참조 문서](./loops-for-in-expression.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b86c-108">For more information, see the [looping expression reference article](./loops-for-in-expression.md).</span></span>

<span data-ttu-id="9b86c-109">F #에는 현재 조각화 문자열, 목록, 배열 및 다차원 (2D, 3D, 4D) 배열에 대 한 기본 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-109">F# currently has intrinsic support for slicing strings, lists, arrays, and multidimensional (2D, 3D, 4D) arrays.</span></span> <span data-ttu-id="9b86c-110">조각화는 F # 배열 및 목록과 가장 일반적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-110">Slicing is most commonly used with F# arrays and lists.</span></span> <span data-ttu-id="9b86c-111">`GetSlice`형식 정의 또는 범위 내 [형식 확장](type-extensions.md)에서 메서드를 사용 하 여 사용자 지정 데이터 형식에 조각화를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-111">You can add slicing to your custom data types by using the `GetSlice` method in your type definition or in an in-scope [type extension](type-extensions.md).</span></span>

## <a name="slicing-f-lists-and-arrays"></a><span data-ttu-id="9b86c-112">F # 목록 및 배열 조각화</span><span class="sxs-lookup"><span data-stu-id="9b86c-112">Slicing F# lists and arrays</span></span>

<span data-ttu-id="9b86c-113">가장 일반적으로 분리 되는 데이터 형식은 F # 목록 및 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-113">The most common data types that are sliced are F# lists and arrays.</span></span>  <span data-ttu-id="9b86c-114">다음 예제에서는 목록을 조각화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-114">The following example demonstrates how to slice lists:</span></span>

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

<span data-ttu-id="9b86c-115">조각화 된 배열을 조각화 목록 처럼 분리 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-115">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="9b86c-116">다차원 배열 조각화</span><span class="sxs-lookup"><span data-stu-id="9b86c-116">Slicing multidimensional arrays</span></span>

<span data-ttu-id="9b86c-117">F #은 F # 핵심 라이브러리의 다차원 배열을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-117">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="9b86c-118">1 차원 배열과 마찬가지로 다차원 배열의 조각이 유용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-118">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="9b86c-119">그러나 추가 차원의 도입은 특정 행과 열의 조각을 가져올 수 있도록 약간 다른 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-119">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="9b86c-120">다음 예제에서는 2D 배열을 조각화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-120">The following examples demonstrate how to slice a 2D array:</span></span>

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

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="9b86c-121">다른 데이터 구조에 대 한 조각 정의</span><span class="sxs-lookup"><span data-stu-id="9b86c-121">Defining slices for other data structures</span></span>

<span data-ttu-id="9b86c-122">F # 핵심 라이브러리는 제한 된 형식 집합에 대 한 조각을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-122">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="9b86c-123">더 많은 데이터 형식에 대 한 조각을 정의 하려는 경우 형식 정의 자체 나 형식 확장에서이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-123">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="9b86c-124">예를 들어, <xref:System.ArraySegment%601> 편리한 데이터 조작을 허용 하기 위해 클래스의 조각을 정의 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-124">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

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

<span data-ttu-id="9b86c-125">및 유형을 사용 하는 다른 예는 <xref:System.Span%601> <xref:System.ReadOnlySpan%601> 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-125">Another example using the <xref:System.Span%601> and <xref:System.ReadOnlySpan%601> types:</span></span>

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

## <a name="built-in-f-slices-are-end-inclusive"></a><span data-ttu-id="9b86c-126">기본 제공 F # 조각은 끝이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-126">Built-in F# slices are end-inclusive</span></span>

<span data-ttu-id="9b86c-127">F #의 모든 내장 조각이 끝에 포함 됩니다. 즉, 상한이 조각에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-127">All intrinsic slices in F# are end-inclusive; that is, the upper bound is included in the slice.</span></span> <span data-ttu-id="9b86c-128">시작 인덱스 및 끝 인덱스를 포함 하는 지정 된 조각에 대해 `x` `y` *yth* 값이 결과 조각에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-128">For a given slice with starting index `x` and ending index `y`, the resulting slice will include the *yth* value.</span></span>

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="built-in-f-empty-slices"></a><span data-ttu-id="9b86c-129">기본 제공 F # 빈 조각</span><span class="sxs-lookup"><span data-stu-id="9b86c-129">Built-in F# empty slices</span></span>

<span data-ttu-id="9b86c-130">구문에서 존재 하지 않는 조각을 생성할 수 있는 경우 F # 목록, 배열, 시퀀스, 문자열, 다차원 (2D, 3D, 4D) 배열은 모두 빈 조각을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-130">F# lists, arrays, sequences, strings, multidimensional (2D, 3D, 4D) arrays will all produce an empty slice if the syntax could produce a slice that doesn't exist.</span></span>

<span data-ttu-id="9b86c-131">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b86c-131">Consider the following example:</span></span>

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

let emptyList = l.[-2..(-1)]
let emptyArray = a.[-2..(-1)]
let emptyString = s.[-2..(-1)]
```

> [!IMPORTANT]
> <span data-ttu-id="9b86c-132">C # 개발자는 빈 조각을 생성 하는 대신 예외를 throw 하는 것으로 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-132">C# developers may expect these to throw an exception rather than produce an empty slice.</span></span> <span data-ttu-id="9b86c-133">이는 빈 컬렉션이 F #에서 작성 한다는 사실을 기반으로 하는 디자인 결정입니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-133">This is a design decision rooted in the fact that empty collections compose in F#.</span></span> <span data-ttu-id="9b86c-134">빈 F # 목록을 다른 F # 목록으로 구성 하거나, 빈 문자열을 기존 문자열에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-134">An empty F# list can be composed with another F# list, an empty string can be added to an existing string, and so on.</span></span> <span data-ttu-id="9b86c-135">일반적으로는 매개 변수로 전달 된 값을 기반으로 조각을 가져오고, F # 코드의 compositional 특성에 맞게 빈 컬렉션을 생성 하 여 범위를 벗어난 >을 허용 하는 것이 일반적 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-135">It can be common to take slices based on values passed in as parameters, and being tolerant of out-of-bounds > by producing an empty collection fits with the compositional nature of F# code.</span></span>

## <a name="fixed-index-slices-for-3d-and-4d-arrays"></a><span data-ttu-id="9b86c-136">3D 및 4D 배열의 고정 인덱스 조각</span><span class="sxs-lookup"><span data-stu-id="9b86c-136">Fixed-index slices for 3D and 4D arrays</span></span>

<span data-ttu-id="9b86c-137">F # 3D 및 4D 배열의 경우 특정 인덱스를 "수정" 하 고 해당 인덱스가 고정 된 다른 차원을 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-137">For F# 3D and 4D arrays, you can "fix" a particular index and slice other dimensions with that index fixed.</span></span>

<span data-ttu-id="9b86c-138">이를 설명 하기 위해 다음 3D 배열을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-138">To illustrate this, consider the following 3D array:</span></span>

<span data-ttu-id="9b86c-139">*z = 0*</span><span class="sxs-lookup"><span data-stu-id="9b86c-139">*z = 0*</span></span>

| <span data-ttu-id="9b86c-140">x\y</span><span class="sxs-lookup"><span data-stu-id="9b86c-140">x\y</span></span>   | <span data-ttu-id="9b86c-141">0</span><span class="sxs-lookup"><span data-stu-id="9b86c-141">0</span></span> | <span data-ttu-id="9b86c-142">1</span><span class="sxs-lookup"><span data-stu-id="9b86c-142">1</span></span> |
|-------|---|---|
| <span data-ttu-id="9b86c-143">**0**</span><span class="sxs-lookup"><span data-stu-id="9b86c-143">**0**</span></span> | <span data-ttu-id="9b86c-144">0</span><span class="sxs-lookup"><span data-stu-id="9b86c-144">0</span></span> | <span data-ttu-id="9b86c-145">1</span><span class="sxs-lookup"><span data-stu-id="9b86c-145">1</span></span> |
| <span data-ttu-id="9b86c-146">**1**</span><span class="sxs-lookup"><span data-stu-id="9b86c-146">**1**</span></span> | <span data-ttu-id="9b86c-147">2</span><span class="sxs-lookup"><span data-stu-id="9b86c-147">2</span></span> | <span data-ttu-id="9b86c-148">3</span><span class="sxs-lookup"><span data-stu-id="9b86c-148">3</span></span> |

<span data-ttu-id="9b86c-149">*z = 1*</span><span class="sxs-lookup"><span data-stu-id="9b86c-149">*z = 1*</span></span>

| <span data-ttu-id="9b86c-150">x\y</span><span class="sxs-lookup"><span data-stu-id="9b86c-150">x\y</span></span>   | <span data-ttu-id="9b86c-151">0</span><span class="sxs-lookup"><span data-stu-id="9b86c-151">0</span></span> | <span data-ttu-id="9b86c-152">1</span><span class="sxs-lookup"><span data-stu-id="9b86c-152">1</span></span> |
|-------|---|---|
| <span data-ttu-id="9b86c-153">**0**</span><span class="sxs-lookup"><span data-stu-id="9b86c-153">**0**</span></span> | <span data-ttu-id="9b86c-154">4</span><span class="sxs-lookup"><span data-stu-id="9b86c-154">4</span></span> | <span data-ttu-id="9b86c-155">5</span><span class="sxs-lookup"><span data-stu-id="9b86c-155">5</span></span> |
| <span data-ttu-id="9b86c-156">**1**</span><span class="sxs-lookup"><span data-stu-id="9b86c-156">**1**</span></span> | <span data-ttu-id="9b86c-157">6</span><span class="sxs-lookup"><span data-stu-id="9b86c-157">6</span></span> | <span data-ttu-id="9b86c-158">7</span><span class="sxs-lookup"><span data-stu-id="9b86c-158">7</span></span> |

<span data-ttu-id="9b86c-159">배열에서 조각을 추출 하려면 `[| 4; 5 |]` 고정 인덱스 조각을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-159">If you want to extract the slice `[| 4; 5 |]` from the array, use a fixed-index slice.</span></span>

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

<span data-ttu-id="9b86c-160">마지막 줄은 `y` 3d 배열의 및 인덱스를 수정 하 `z` 고 `x` 행렬에 해당 하는 값의 나머지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9b86c-160">The last line fixes the `y` and `z` indices of the 3D array and takes the rest of the `x` values that correspond to the matrix.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b86c-161">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9b86c-161">See also</span></span>

- [<span data-ttu-id="9b86c-162">인덱싱된 속성</span><span class="sxs-lookup"><span data-stu-id="9b86c-162">Indexed properties</span></span>](./members/indexed-properties.md)
