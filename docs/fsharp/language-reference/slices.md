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
# <a name="slices"></a>조각

F #에서 조각은 `GetSlice` 해당 정의 또는 범위 내 [형식 확장](type-extensions.md)에서 메서드를 포함 하는 모든 데이터 형식의 하위 집합입니다. F # 배열 및 목록과 가장 일반적으로 사용 됩니다. 이 문서에서는 기존 F # 형식에서 조각을 가져오는 방법 및 사용자 고유의 조각을 정의 하는 방법을 설명 합니다.

조각은 [인덱서와](./members/indexed-properties.md)비슷하지만 기본 데이터 구조에서 단일 값을 생성 하는 대신 여러 개를 생성 합니다.

F #에는 현재 조각화 문자열, 목록, 배열 및 2D 배열에 대 한 기본 지원이 있습니다.

## <a name="basic-slicing-with-f-lists-and-arrays"></a>F # 목록 및 배열을 사용 하 여 기본 조각화

가장 일반적으로 분리 되는 데이터 형식은 F # 목록 및 배열입니다. 다음 예제에서는 목록을 사용 하 여이 작업을 수행 하는 방법을 보여 줍니다.

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

조각화 된 배열을 조각화 목록 처럼 분리 하는 것입니다.

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

F #은 F # 핵심 라이브러리의 다차원 배열을 지원 합니다. 1 차원 배열과 마찬가지로 다차원 배열의 조각이 유용할 수도 있습니다. 그러나 추가 차원의 도입은 특정 행과 열의 조각을 가져올 수 있도록 약간 다른 구문을 사용 합니다.

다음 예제에서는 2D 배열을 조각화 하는 방법을 보여 줍니다.

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

F # 핵심 라이브러리는 현재 3D 배열을 정의 하지 않습니다 `GetSlice` . 3D 배열 또는 다른 차원의 다른 배열을 조각화 하려는 경우 `GetSlice` 멤버를 직접 정의 합니다.

## <a name="defining-slices-for-other-data-structures"></a>다른 데이터 구조에 대 한 조각 정의

F # 핵심 라이브러리는 제한 된 형식 집합에 대 한 조각을 정의 합니다. 더 많은 데이터 형식에 대 한 조각을 정의 하려는 경우 형식 정의 자체 나 형식 확장에서이 작업을 수행할 수 있습니다.

예를 들어, <xref:System.ArraySegment%601> 편리한 데이터 조작을 허용 하기 위해 클래스의 조각을 정의 하는 방법은 다음과 같습니다.

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

및 유형을 사용 하는 다른 예는 <xref:System.Span%601> <xref:System.ReadOnlySpan%601> 다음과 같습니다.

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

## <a name="built-in-f-slices-are-end-inclusive"></a>기본 제공 F # 조각은 끝이 포함 됩니다.

F #의 모든 내장 조각이 끝에 포함 됩니다. 즉, 상한이 조각에 포함 됩니다. 시작 인덱스 및 끝 인덱스를 포함 하는 지정 된 조각에 대해 `x` `y` *yth* 값이 결과 조각에 포함 됩니다.

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="built-in-f-empty-slices"></a>기본 제공 F # 빈 조각

구문에서 존재 하지 않는 조각을 생성할 수 있는 경우 F # 목록, 배열, 시퀀스, 문자열, 2D 배열, 3D 배열 및 4D 배열이 모두 빈 조각을 생성 합니다.

다음을 살펴보세요.

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

let emptyList = l.[-2..(-1)]
let emptyArray = a.[-2..(-1)]
let emptyString = s.[-2..(-1)]
```

C # 개발자는 빈 조각을 생성 하는 대신 예외를 throw 하는 것으로 예측할 수 있습니다. 이는 빈 컬렉션이 F #에서 작성 한다는 사실을 기반으로 하는 디자인 결정입니다. 빈 F # 목록을 다른 F # 목록으로 구성 하거나, 빈 문자열을 기존 문자열에 추가할 수 있습니다. 매개 변수로 전달 된 값을 기반으로 조각을 가져오고, F # 코드의 compositional 특성과 일치 하는 빈 컬렉션을 생성 하 여 범위를 벗어나는 것을 허용 하는 것이 일반적 일 수 있습니다.

## <a name="fixed-index-slices-for-3d-and-4d-arrays"></a>3D 및 4D 배열의 고정 인덱스 조각

F # 3D 및 4D 배열의 경우 특정 인덱스를 "수정" 하 고 해당 인덱스가 고정 된 다른 차원을 분할할 수 있습니다.

이를 설명 하기 위해 다음 3D 배열을 고려 합니다.

*z = 0*
| x\y   | 0 | 1 |
|-------|---|---|
| **0** | 0 | 1 |
| **1** | 2 | 3 |

*z = 1*
| x\y   | 0 | 1 |
|-------|---|---|
| **0** | 4 | 5 |
| **1** | 6 | 7 |

배열에서 조각을 추출 하려면 `[| 4; 5 |]` 고정 인덱스 조각을 사용 합니다.

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

마지막 줄은 `y` `z` 3d 배열의 및 인덱스를 수정 하 고 `x` 행렬에 해당 하는 값의 나머지를 가져옵니다.

## <a name="see-also"></a>참조

- [인덱싱된 속성](./members/indexed-properties.md)
