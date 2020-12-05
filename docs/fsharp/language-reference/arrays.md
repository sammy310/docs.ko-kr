---
title: 배열
description: 'F # 프로그래밍 언어에서 배열을 만들고 사용 하는 방법에 대해 알아봅니다.'
ms.date: 08/13/2020
ms.openlocfilehash: 96b0d7eaf10d5afcd9a647681d5c2ef2d2fba335
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739753"
---
# <a name="arrays"></a>배열

배열은 동일한 형식의 연속 데이터 요소에 대 한 고정 크기의 변경 가능한 컬렉션으로, 0부터 시작 합니다.

## <a name="create-arrays"></a>배열 만들기

여러 가지 방법으로 배열을 만들 수 있습니다. 다음 예제와 같이 및 사이에 연속 값을 나열 `[|` 하 `|]` 고 세미콜론으로 구분 하 여 작은 배열을 만들 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet1.fs)]

각 요소를 별도의 줄에 배치할 수도 있습니다 .이 경우 세미콜론 구분 기호는 선택 사항입니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet2.fs)]

배열 요소의 형식은 사용 된 리터럴에서 유추 되며 일치 해야 합니다. 다음 코드는 1.0가 float이 고 2와 3이 정수 이므로 오류가 발생 합니다.

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

시퀀스 식을 사용 하 여 배열을 만들 수도 있습니다. 다음은 1에서 10 사이의 정수 제곱 배열을 만드는 예제입니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet3.fs)]

모든 요소가 0으로 초기화 되는 배열을 만들려면를 사용 `Array.zeroCreate` 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="access-elements"></a>액세스 요소

점 연산자 ( `.` )와 대괄호 (및)를 사용 하 여 배열 요소에 액세스할 수 있습니다 `[` `]` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet5.fs)]

배열 인덱스는 0부터 시작 합니다.

배열의 하위 범위를 지정 하는 데 사용할 수 있는 조각 표기법을 사용 하 여 배열 요소에 액세스할 수도 있습니다. 조각 표기법의 예는 다음과 같습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet51.fs)]

조각 표기법을 사용 하면 배열의 새 복사본이 만들어집니다.

## <a name="array-types-and-modules"></a>배열 형식 및 모듈

모든 F # 배열의 형식은 .NET Framework 형식입니다 <xref:System.Array?displayProperty=nameWithType> . 따라서 F # 배열은에서 사용할 수 있는 모든 기능을 지원 <xref:System.Array?displayProperty=nameWithType> 합니다.

[ `Array` 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html) 은 1 차원 배열에 대 한 작업을 지원 합니다. 모듈 `Array2D` , 및에는 `Array3D` `Array4D` 각각 2, 3 및 4 차원 배열에 대 한 작업을 지 원하는 함수가 포함 되어 있습니다. 을 사용 하 여 4 보다 큰 차수 배열을 만들 수 있습니다 <xref:System.Array?displayProperty=nameWithType> .

### <a name="simple-functions"></a>간단한 함수

[`Array.get`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#get) 요소를 가져옵니다. [`Array.length`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#length) 배열의 길이를 제공 합니다. [`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) 요소를 지정 된 값으로 설정 합니다. 다음 코드 예제에서는 이러한 함수를 사용 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet9.fs)]

출력은 다음과 같습니다.

```console
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a>배열을 만드는 함수

여러 함수는 기존 배열을 요구 하지 않고 배열을 만듭니다. [`Array.empty`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#empty) 요소가 포함 되지 않은 새 배열을 만듭니다. [`Array.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#create) 지정 된 크기의 배열을 만들고 모든 요소를 제공 된 값으로 설정 합니다. [`Array.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#init) 지정 된 차원과 요소를 생성 하는 함수를 지정 하 여 배열을 만듭니다. [`Array.zeroCreate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate) 모든 요소가 배열의 형식에 대해 0 값으로 초기화 되는 배열을 만듭니다. 다음 코드에서는 이러한 함수를 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet91.fs)]

출력은 다음과 같습니다.

```console
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

[`Array.copy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#copy) 기존 배열에서 복사 된 요소를 포함 하는 새 배열을 만듭니다. 복사본은 단순 복사본입니다. 즉, 요소 형식이 참조 형식이 면 참조만 복사 되 고 기본 개체는 복사 되지 않습니다. 다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet11.fs)]

위의 코드의 출력은 다음과 같습니다.

```console
[|Test1; Test2; |]
[|; Test2; |]
```

`Test1`새 요소를 만드는 작업은에서 참조를 덮어쓰므로 `firstArray` 에서 여전히에 있는 빈 문자열에 대 한 원래 참조에는 영향을 주지 않기 때문에이 문자열은 첫 번째 배열에만 나타납니다 `secondArray` . `Test2` `Insert` 형식에 대 한 작업이 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 두 배열에서 참조 되는 기본 개체에 영향을 주기 때문에 두 배열에 문자열이 모두 표시 됩니다 <xref:System.Text.StringBuilder?displayProperty=nameWithType> .

[`Array.sub`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sub) 배열의 하위 범위에서 새 배열을 생성 합니다. 시작 인덱스 및 길이를 제공 하 여 하위 범위를 지정 합니다. 다음 코드는 `Array.sub`의 사용법을 보여줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet12.fs)]

출력은 하위 배열을 요소 5에서 시작 하 고 10 개의 요소를 포함 하는 것을 보여 줍니다.

```console
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

[`Array.append`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#append) 두 개의 기존 배열을 결합 하 여 새 배열을 만듭니다.

다음 코드에서는 **배열. append** 를 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet13.fs)]

위의 코드는 다음과 같이 출력 됩니다.

```console
[|1; 2; 3; 4; 5; 6|]
```

[`Array.choose`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#choose) 새 배열에 포함할 배열의 요소를 선택 합니다. 다음 코드에서는을 보여 줍니다 `Array.choose` . 배열의 요소 형식은 옵션 형식에서 반환 되는 값의 형식과 일치할 필요가 없습니다. 이 예제에서 요소 형식은이 `int` 고 옵션은 다항식 함수의 결과인 `elem*elem - 1` 부동 소수점 숫자입니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet14.fs)]

위의 코드는 다음과 같이 출력 됩니다.

```console
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

[`Array.collect`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#collect) 기존 배열의 각 배열 요소에 대해 지정 된 함수를 실행 한 다음 함수에 의해 생성 된 요소를 수집 하 여 새 배열로 결합 합니다. 다음 코드에서는을 보여 줍니다 `Array.collect` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet15.fs)]

위의 코드는 다음과 같이 출력 됩니다.

```console
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

[`Array.concat`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#concat) 배열의 시퀀스를 사용 하 여 단일 배열로 결합 합니다. 다음 코드에서는을 보여 줍니다 `Array.concat` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet16.fs)]

위의 코드는 다음과 같이 출력 됩니다.

```console
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

[`Array.filter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#filter) 부울 조건 함수를 사용 하 고 조건이 true 인 입력 배열의 요소만 포함 하는 새 배열을 생성 합니다. 다음 코드에서는을 보여 줍니다 `Array.filter` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet17.fs)]

위의 코드는 다음과 같이 출력 됩니다.

```console
[|2; 4; 6; 8; 10|]
```

[`Array.rev`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#rev) 기존 배열의 순서를 반대로 하 여 새 배열을 생성 합니다. 다음 코드에서는을 보여 줍니다 `Array.rev` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet18.fs)]

위의 코드는 다음과 같이 출력 됩니다.

```console
"Hello world!"
```

다음 예제와 같이 파이프라인 연산자 ()를 사용 하 여 배열을 변환 하는 배열 모듈의 함수를 쉽게 결합할 수 있습니다 `|>` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet19.fs)]

출력은 다음과 같습니다.

```console
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a>다차원 배열

다차원 배열을 만들 수 있지만 다차원 배열 리터럴을 작성 하기 위한 구문이 없습니다. 연산자를 사용 [`array2D`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html) 하 여 배열 요소의 시퀀스 시퀀스에서 배열을 만듭니다. 시퀀스는 배열 또는 목록 리터럴일 수 있습니다. 예를 들어 다음 코드는 2 차원 배열을 만듭니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet20.fs)]

또한 함수를 사용 하 여 [`Array2D.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#init) 두 차원의 배열을 초기화할 수 있으며, 3 개 차원 및 4 차원 배열에도 유사한 함수를 사용할 수 있습니다. 이러한 함수는 요소를 만드는 데 사용 되는 함수를 사용 합니다. 함수를 지정 하는 대신 초기 값으로 설정 된 요소를 포함 하는 2 차원 배열을 만들려면 [`Array2D.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#create) 최대 4 차원 배열에도 사용할 수 있는 함수를 사용 합니다. 다음 코드 예제에서는 먼저 원하는 요소를 포함 하는 배열 배열을 만든 다음를 사용 하 여 `Array2D.init` 원하는 2 차원 배열을 생성 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet21.fs)]

배열 인덱싱 및 조각화 구문은 차수가 4 인 배열에 대해 지원 됩니다. 여러 차원에서 인덱스를 지정 하는 경우 다음 코드 예제에 나와 있는 것 처럼 쉼표를 사용 하 여 인덱스를 구분 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet22.fs)]

2 차원 배열의 형식은 `<type>[,]` (예:,)로 작성 되 `int[,]` `double[,]` 고 3 차원 배열의 형식은로 작성 되며, `<type>[,,]` 더 큰 차원의 배열에 대해서는로 작성 됩니다.

다차원 배열에는 1 차원 배열에 사용할 수 있는 함수의 하위 집합만 사용할 수 있습니다.

### <a name="array-slicing-and-multidimensional-arrays"></a>배열 조각화 및 다차원 배열

2 차원 배열 (행렬)에서 범위를 지정 하 고 와일드 카드 () 문자를 사용 하 여 하위 행렬을 추출 하 여 `*` 전체 행 또는 열을 지정할 수 있습니다.

```fsharp
// Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

다차원 배열을 같거나 낮은 차원의 subarrays으로 분해할 수 있습니다. 예를 들어 단일 행 또는 열을 지정 하 여 행렬에서 벡터를 가져올 수 있습니다.

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

요소 액세스 연산자 및 오버 로드 된 메서드를 구현 하는 형식에 대해이 조각화 구문을 사용할 수 있습니다 `GetSlice` . 예를 들어 다음 코드는 F # 2D 배열을 래핑하고 항목 속성을 구현 하 여 배열 인덱싱에 대 한 지원을 제공 하 고 세 가지 버전의를 구현 하는 행렬 유형을 만듭니다 `GetSlice` . 이 코드를 행렬 형식에 대 한 템플릿으로 사용할 수 있는 경우이 단원에서 설명 하는 모든 조각 작업을 사용할 수 있습니다.

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn $"{submatrix}"

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn $"{firstCol}"
```

### <a name="boolean-functions-on-arrays"></a>배열의 부울 함수

[`Array.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists) [`Array.exists2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists2) 각각 하나 또는 두 배열의 함수 및 테스트 요소입니다. 이러한 함수는 테스트 함수를 사용 하 고 `true` `Array.exists2` 조건을 충족 하는 요소 또는에 대 한 요소 쌍이 있는 경우를 반환 합니다.

다음 코드에서는 및를 사용 하는 방법을 보여 줍니다 `Array.exists` `Array.exists2` . 이러한 예제에서는 인수 중 하나 (이 경우에는 함수 인수)만 적용 하 여 새 함수를 만듭니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet23.fs)]

위의 코드는 다음과 같이 출력 됩니다.

```console
true
false
false
true
```

마찬가지로 함수는 [`Array.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall) 배열을 테스트 하 여 모든 요소가 부울 조건을 충족 하는지 여부를 확인 합니다. [`Array.forall2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall2)동일한 길이의 두 배열의 요소를 포함 하는 부울 함수를 사용 하 여 변형이 동일한 작업을 수행 합니다. 다음 코드에서는 이러한 함수를 사용 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet24.fs)]

이러한 예제에 대 한 출력은 다음과 같습니다.

```console
false
true
true
false
```

### <a name="search-arrays"></a>검색 배열

[`Array.find`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#find) 부울 함수를 사용 하 여 함수가 반환 하는 첫 번째 요소를 반환 `true` 하거나 <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> 조건을 충족 하는 요소가 없는 경우을 발생 시킵니다. [`Array.findIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#findIndex) 는 `Array.find` 요소 자체 대신 요소의 인덱스를 반환 한다는 점을 제외 하 고와 비슷합니다.

다음 코드에서는 및를 사용 하 여 `Array.find` `Array.findIndex` 완전 한 정사각형과 완전 한 큐브인 숫자를 찾습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet25.fs)]

출력은 다음과 같습니다.

```console
The first element that is both a square and a cube is 64 and its index is 62.
```

[`Array.tryFind`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFind) 는 `Array.find` 결과가 옵션 형식 이라는 점을 제외 하 고는와 유사 하며, `None` 요소를 찾을 수 없는 경우를 반환 합니다. `Array.tryFind``Array.find`일치 하는 요소가 배열에 있는지 여부를 알 수 없는 경우 대신를 사용 해야 합니다. 마찬가지로 [`Array.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFindIndex) `Array.findIndex` 옵션 유형이 반환 값 이라는 점을 제외 하 고는와 유사 합니다. 요소를 찾을 수 없는 경우 옵션은 `None` 입니다.

다음 코드는 `Array.tryFind`의 사용법을 보여줍니다. 이 코드는 이전 코드에 따라 달라 집니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet26.fs)]

출력은 다음과 같습니다.

```console
Found an element: 1
Found an element: 729
Failed to find a matching element.
```

[`Array.tryPick`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryPick)요소를 찾을 뿐만 아니라 요소를 변환 해야 하는 경우에 사용 합니다. 결과는 함수에서 변환 된 요소를 옵션 값으로 반환 하는 첫 번째 요소 이거나, `None` 이러한 요소가 없는 경우입니다.

다음 코드는 `Array.tryPick`의 사용법을 보여줍니다. 이 경우 람다 식 대신 코드를 단순화 하기 위해 몇 가지 로컬 도우미 함수가 정의 됩니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet27.fs)]

출력은 다음과 같습니다.

```console
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
Did not find an element that is both a perfect square and a perfect cube.
```

### <a name="perform-computations-on-arrays"></a>배열에서 계산 수행

[`Array.average`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#average)함수는 배열의 각 요소에 대 한 평균을 반환 합니다. 정수로 정확히 나누기를 지 원하는 요소 형식으로 제한 됩니다. 여기에는 부동 소수점 형식이 포함 되지만 정수 계열 형식은 포함 되지 않습니다. [`Array.averageBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#averageBy)함수는 각 요소에 대해 함수를 호출한 결과의 평균을 반환 합니다. 정수 계열 형식의 배열에 대해를 사용 하 `Array.averageBy` 고 함수에서 각 요소를 계산에 대 한 부동 소수점 형식으로 변환할 수 있습니다.

[`Array.max`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#max) [`Array.min`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#min) 요소 형식이 지 원하는 경우 또는를 사용 하 여 maximum 또는 minimum 요소를 가져옵니다. 마찬가지로 [`Array.maxBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#maxBy) 및 [`Array.minBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#minBy) 는 비교를 지 원하는 형식으로 변환 하는 등의 방법으로 함수를 먼저 실행할 수 있습니다.

[`Array.sum`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sum) 배열의 요소를 추가 하 고 [`Array.sumBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sumBy) 각 요소에 대해 함수를 호출 하 고 결과를 함께 추가 합니다.

반환 값을 저장 하지 않고 배열의 각 요소에 대해 함수를 실행 하려면를 사용 [`Array.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter) 합니다. 길이가 같은 두 배열이 포함 된 함수의 경우를 사용 [`Array.iter2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter2) 합니다. 함수의 결과 배열을 유지 해야 하는 경우에 [`Array.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map) [`Array.map2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map2) 는 한 번에 두 배열에 대해 작동 하는 또는를 사용 합니다.

변형을 사용 하 여 [`Array.iteri`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri) [`Array.iteri2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri2) 요소의 인덱스를 계산에 포함 시킬 수 있습니다. 및의 경우에도 [`Array.mapi`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi) 마찬가지입니다. [`Array.mapi2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi2)

,, [`Array.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold) ,, 및 함수는 [`Array.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack) [`Array.reduce`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduce) [`Array.reduceBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduceBack) [`Array.scan`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scan) [`Array.scanBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scanBack) 배열의 모든 요소를 포함 하는를 실행 합니다. 마찬가지로, 변형이 [`Array.fold2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold2) [`Array.foldBack2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack2) 두 배열에 대해 계산을 수행 합니다.

계산을 수행 하는 이러한 함수는 [목록 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)에 있는 동일한 이름의 함수에 해당 합니다. 사용 예제는 [목록](lists.md)을 참조 하십시오.

### <a name="modify-arrays"></a>배열 수정

[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) 요소를 지정 된 값으로 설정 합니다. [`Array.fill`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fill) 배열의 요소 범위를 지정 된 값으로 설정 합니다. 다음 코드에서는의 예제를 제공 합니다 `Array.fill` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet28.fs)]

출력은 다음과 같습니다.

```console
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

[`Array.blit`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#blit)를 사용 하 여 한 배열의 하위 섹션을 다른 배열로 복사할 수 있습니다.

### <a name="convert-to-and-from-other-types"></a>다른 형식으로 변환

[`Array.ofList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofList) 목록에서 배열을 만듭니다. [`Array.ofSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofSeq) 시퀀스에서 배열을 만듭니다. [`Array.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toList) 및 [`Array.toSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toSeq) 는 배열 형식에서 이러한 다른 컬렉션 형식으로 변환 합니다.

### <a name="sort-arrays"></a>배열 정렬

[`Array.sort`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sort)제네릭 비교 함수를 사용 하 여 배열을 정렬 하는 데 사용 합니다. 키 [`Array.sortBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortBy) 에 대 한 제네릭 비교 함수를 사용 하 여 정렬 하려면 *키* 라고 하는 값을 생성 하는 함수를 지정 하는 데 사용 합니다. [`Array.sortWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortWith)사용자 지정 비교 함수를 제공 하려는 경우를 사용 합니다. `Array.sort`, `Array.sortBy` 및는 `Array.sortWith` 모두 정렬 된 배열을 새 배열로 반환 합니다. [`Array.sortInPlace`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlace), 및 변형은 [`Array.sortInPlaceBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceBy) [`Array.sortInPlaceWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceWith) 새 배열을 반환 하는 대신 기존 배열을 수정 합니다.

### <a name="arrays-and-tuples"></a>배열 및 튜플

함수 [`Array.zip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip) 및는 [`Array.unzip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip) 튜플 쌍의 배열을 배열의 튜플로 변환 하 고 그 반대의 경우도 마찬가지입니다. [`Array.zip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip3) 및는 세 개의 요소로 된 튜플 [`Array.unzip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip3) 또는 세 개의 배열로 된 튜플로 작업 한다는 점을 제외 하 고는 유사 합니다.

## <a name="parallel-computations-on-arrays"></a>배열에 대 한 병렬 계산

모듈에는 [`Array.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule-parallel.html) 배열에 대 한 병렬 계산을 수행 하는 함수가 포함 되어 있습니다. 버전 4 이전 버전의 .NET Framework를 대상으로 하는 응용 프로그램에서는이 모듈을 사용할 수 없습니다.

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
- [F# 형식](fsharp-types.md)
