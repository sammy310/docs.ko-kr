---
title: 조각 (F#)
description: 기존 분할 영역을 사용 하는 방법에 알아봅니다 F# 데이터 형식 및 다른 데이터 형식에 대 한 사용자 고유의 조각을 정의 하는 방법입니다.
ms.date: 01/22/2019
ms.openlocfilehash: 1d8bb029ad18c8853ab58888959967ed279fb368
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925997"
---
# <a name="slices"></a>조각

F#, 조각은 데이터 형식의 하위 집합입니다. 하거나 정의 해야 데이터 형식을 데이터 형식에서 조각을 가져올 수는 `GetSlice` 메서드 또는 [확장명을 입력](type-extensions.md) 범위입니다. 이 문서에서는 기존 분할 영역을 사용 하는 방법을 설명 F# 형식 및 사용자 지정 하는 방법입니다.

조각이 비슷합니다 [인덱서](members/indexed-properties.md), 하지만 여러 세션 대신 기본 데이터 구조에서 단일 값이 구해지 기를 생성 합니다.

F#현재는 문자열, 목록, 배열 및 2D 배열 조각화에 대 한 내장 지원 합니다.

## <a name="basic-slicing-with-f-lists-and-arrays"></a>사용 하 여 기본 조각화 F# 목록 및 배열

분할 되는 가장 일반적인 데이터 형식은 F# 목록과 배열입니다. 다음 예제에서는 목록을 사용 하 여이 작업을 수행 하는 방법에 설명 합니다.

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

배열 조각화 같으며 목록 조각화:

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

## <a name="slicing-multidimensional-arrays"></a>다차원 배열 조각화

F#다차원 배열을 지원 합니다 F# 핵심 라이브러리입니다. 1 차원 배열과 마찬가지로 다차원 배열 조각도 유용할 수 있습니다. 그러나 특정 행과 열에 대 한 부분을 수행할 수 있도록 추가 차원이 미치는 구문은 약간 다릅니다 한다고 규정 합니다.

다음 예제에서는 2 차원 배열 조각화 하는 방법을 보여 줍니다.

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

F# 핵심 라이브러리를 정의 하지 않습니다 `GetSlice`3D 배열에 대 한 합니다. 정의 해야 합니다 또는 다른 배열을 한 차원 조각화 하려는 경우는 `GetSlice` 멤버 직접.

## <a name="defining-slices-for-other-data-structures"></a>기타 데이터 구조에 대 한 슬라이스를 정의합니다.

F# 핵심 라이브러리는 형식의 제한 된 집합에 대 한 슬라이스를 정의 합니다. 자세한 데이터 형식에 대 한 조각을 정의 하려는 경우 형식 정의 자체 또는 형식 확장에서이 수행할 수 있습니다.

예를 들어 다음과 같습니다 하는 방법에 대 한 슬라이스를 정의할 수 있습니다는 <xref:System.ArraySegment%601> 편리한 데이터 조작을 위한 클래스:

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(?start, ?finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a>필요한 경우 boxing을 방지 하려면 인라인 처리 사용

좋습니다 구조체 실제로 된 형식에 대 한 조각을 정의 하는 경우 있습니다 `inline` 는 `GetSlice` 멤버입니다. F# 컴파일러 조각화의 결과로 모든 힙 할당을 방지 하는 선택적 인수를 최적화 합니다. 이 같은 구문을 조각화 하는 데 매우 중요 <xref:System.Span%601> 힙에 할당할 수 없습니다.

```fsharp
open System

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..2] // |2; 3|]
```

## <a name="see-also"></a>참고자료

- [인덱싱된 속성](members/indexed-properties.md)
