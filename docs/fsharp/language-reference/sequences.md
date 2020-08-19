---
title: 시퀀스
description: '데이터의 순서가 지정 된 컬렉션이 크고 모든 요소를 사용할 필요가 없는 경우 F # 시퀀스를 사용 하는 방법에 대해 알아봅니다.'
ms.date: 08/13/2020
ms.openlocfilehash: c84e0aebcc79a595c0ae3b9075648fb629bdd65c
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559039"
---
# <a name="sequences"></a>시퀀스

*시퀀스* 는 단일 형식의 논리적 일련의 요소입니다. 시퀀스는 광범위 하 고 정렬 된 데이터 컬렉션이 있지만 모든 요소를 반드시 사용할 필요는 없는 경우에 특히 유용 합니다. 개별 시퀀스 요소는 필요에 따라 계산 되므로 모든 요소가 사용 되지 않는 상황에서 시퀀스는 목록 보다 더 나은 성능을 제공할 수 있습니다. 시퀀스는 `seq<'T>` 의 별칭인 형식으로 표현 됩니다 <xref:System.Collections.Generic.IEnumerable%601> . 따라서 인터페이스를 구현 하는 모든 .NET 형식을 <xref:System.Collections.Generic.IEnumerable%601> 시퀀스로 사용할 수 있습니다. [Seq 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html) 은 시퀀스와 관련 된 조작을 지원 합니다.

## <a name="sequence-expressions"></a>시퀀스 식

*시퀀스 식은* 시퀀스로 계산 되는 식입니다. 시퀀스 식은 많은 폼을 사용할 수 있습니다. 가장 간단한 형태는 범위를 지정 합니다. 예를 `seq { 1 .. 5 }` 들어는 끝점 1과 5를 포함 하 여 다섯 개의 요소를 포함 하는 시퀀스를 만듭니다. 두 개의 double 기간 사이에 증가 (또는 감소)를 지정할 수도 있습니다. 예를 들어 다음 코드는 10의 배수로 이루어진 시퀀스를 만듭니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

시퀀스 식은 시퀀스의 값을 생성 하는 F # 식으로 구성 됩니다. 값을 프로그래밍 방식으로 생성할 수도 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

이전 예제에서는 연산자를 사용 하 여 해당 `->` 값이 시퀀스의 일부가 될 식을 지정할 수 있습니다. `->`뒤에 오는 코드의 모든 부분에서 값을 반환 하는 경우에만를 사용할 수 있습니다.

또는 키워드를 지정 하 고 다음과 같은 옵션을 지정할 수 있습니다 `do` `yield` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

다음 코드에서는 표를 나타내는 배열에 대 한 인덱스와 함께 좌표 쌍의 목록을 생성 합니다. 첫 번째 식에는를 `for` `do` 지정 해야 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

`if`시퀀스에 사용 되는 식은 필터입니다. 예를 들어, 형식이 인 함수를 포함 하 고 있다고 가정 하 고 소수 숫자만 포함 하는 시퀀스를 생성 하려면 `isprime` `int -> bool` 다음과 같이 시퀀스를 생성 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

앞에서 설명한 것 처럼 `do` `else` 와 함께 이동 하는 분기가 없기 때문에이 필요 `if` 합니다. 를 사용 하려고 하면 `->` 모든 분기에서 값을 반환 하지 않는다는 오류가 표시 됩니다.

## <a name="the-yield-keyword"></a>`yield!` 키워드

경우에 따라 요소의 시퀀스를 다른 시퀀스에 포함할 수 있습니다. 시퀀스를 다른 시퀀스 내에 포함 하려면 키워드를 사용 해야 합니다 `yield!` .

```fsharp
// Repeats '1 2 3 4 5' ten times
seq {
    for _ in 1..10 do
        yield! seq { 1; 2; 3; 4; 5}
}
```

를 고려 하는 또 다른 방법은 `yield!` 내부 시퀀스를 평면화 한 다음 포함 하는 시퀀스에이를 포함 하는 것입니다.

`yield!`식에를 사용 하는 경우 다른 모든 단일 값은 키워드를 사용 해야 합니다 `yield` .

```fsharp
// Combine repeated values with their values
seq {
    for x in 1..10 do
        yield x
        yield! seq { for i in 1..x -> i}
}
```

이전 예에서는의 값 `x` 을 각각에 대해에서로 생성 합니다 `1` `x` `x` .

## <a name="examples"></a>예제

첫 번째 예에서는 반복, 필터 및 양보를 포함 하는 시퀀스 식을 사용 하 여 배열을 생성 합니다. 이 코드는 1에서 100 사이의 일련 번호 시퀀스를 콘솔에 출력 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

다음 예에서는 두 개의 요소로 구성 된 튜플로 구성 된 곱하기 테이블을 만듭니다. 각 요소는 두 개의 요소와 제품으로 구성 됩니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

다음 예제에서는를 사용 하 여 `yield!` 개별 시퀀스를 단일 최종 시퀀스로 결합 하는 방법을 보여 줍니다. 이 경우 이진 트리의 각 하위 트리에 대 한 시퀀스는 재귀적 함수에서 연결 되어 최종 시퀀스를 생성 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a>시퀀스 사용

시퀀스는 [목록과](lists.md)동일한 많은 기능을 지원 합니다. 시퀀스는 키 생성 함수를 사용 하 여 그룹화 및 계산 등의 작업도 지원 합니다. 시퀀스는 버킷이라고을 추출 하는 더 다양 한 함수도 지원 합니다.

목록, 배열, 집합 및 맵과 같은 많은 데이터 형식은 열거 가능한 컬렉션 이므로 암시적으로 시퀀스 됩니다. 시퀀스를 인수로 사용 하는 함수는을 구현 하는 .NET 데이터 형식 외에도 일반적인 F # 데이터 형식과 함께 사용할 수 `System.Collections.Generic.IEnumerable<'T>` 있습니다. 목록을 인수로 사용 하는 함수와 대조 하 여 목록만 사용할 수 있습니다. 형식은 `seq<'T>` 에 대 한 형식 약어입니다 `IEnumerable<'T>` . 즉, `System.Collections.Generic.IEnumerable<'T>` F #의 배열, 목록, 집합 및 맵을 포함 하는 제네릭을 구현 하는 모든 형식 및 대부분의 .net 컬렉션 형식은 형식과 호환 되며 `seq` 시퀀스가 필요한 모든 곳에서 사용할 수 있습니다.

## <a name="module-functions"></a>모듈 함수

[Fsharp.core 네임 스페이스](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections.html) 의 [Seq 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html) 에는 시퀀스 작업을 위한 함수가 포함 되어 있습니다. 이러한 함수는 모두 열거 가능 하므로 시퀀스로 처리 될 수 있기 때문에 목록, 배열, 맵 및 집합 에서도 작동 합니다.

## <a name="creating-sequences"></a>시퀀스 만들기

앞에서 설명한 대로 시퀀스 식을 사용 하거나 특정 함수를 사용 하 여 시퀀스를 만들 수 있습니다.

[Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#empty)를 사용 하 여 빈 시퀀스를 만들거나 [seq. singleton](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#singleton)을 사용 하 여 지정 된 요소의 시퀀스를 만들 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet9.fs)]

[Seq.init](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#init) 를 사용 하 여 사용자가 제공 하는 함수를 사용 하 여 요소가 생성 되는 시퀀스를 만들 수 있습니다. 또한 시퀀스의 크기를 제공 합니다. 이 함수는 시퀀스를 반복할 때까지 요소가 생성 되지 않는다는 점을 제외 하 고는 [List.init](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#init)와 동일 합니다. 다음 코드에서는를 사용 하는 방법을 보여 줍니다 `Seq.init` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet10.fs)]

출력은 다음과 같습니다.

```console
0 10 20 30 40
```

[Seq.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#ofArray) [&#60;&#62; 함수](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#ofList)를 사용 하 여 배열 및 목록에서 시퀀스를 만들 수 있습니다. 그러나 캐스트 연산자를 사용 하 여 배열 및 목록을 시퀀스로 변환할 수도 있습니다. 다음 코드에서는 두 가지 방법을 모두 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet11.fs)]

[Seq. 캐스트](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#cast)를 사용 하 여에 정의 된 것과 같은 약하게 형식화 된 컬렉션에서 시퀀스를 만들 수 있습니다 `System.Collections` . 이러한 약하게 형식화 된 컬렉션은 요소 형식을 가지 `System.Object` 며 제네릭이 아닌 형식을 사용 하 여 열거 됩니다 `System.Collections.Generic.IEnumerable&#96;1` . 다음 코드에서는를 사용 하 여를 `Seq.cast` 시퀀스로 변환 하는 방법을 보여 줍니다 `System.Collections.ArrayList` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet12.fs)]

[Seq.initInfinite](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#initInfinite) 함수를 사용 하 여 무한 시퀀스를 정의할 수 있습니다. 이러한 시퀀스의 경우 요소의 인덱스에서 각 요소를 생성 하는 함수를 제공 합니다. 지연 계산으로 인해 무한 시퀀스를 사용할 수 있습니다. 요소는 지정 된 함수를 호출 하 여 필요에 따라 만들어집니다. 다음 코드 예제에서는 부동 소수점 숫자의 무한 시퀀스를 생성 합니다 .이 경우 연속 되는 정수의 사각형 reciprocals 교대로 반복 되는 연속 된 정수입니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet13.fs)]

[펼침](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#unfold) 는 상태를 사용 하는 계산 함수에서 시퀀스를 생성 하 고 시퀀스의 각 후속 요소를 생성 하도록 변환 합니다. 상태는 각 요소를 계산 하는 데 사용 되는 값 이며 각 요소가 계산 될 때 변경 될 수 있습니다. 에 대 한 두 번째 인수는 `Seq.unfold` 시퀀스를 시작 하는 데 사용 되는 초기 값입니다. `Seq.unfold` 는 상태에 대해 옵션 유형을 사용 합니다 .이를 통해 값을 반환 하 여 시퀀스를 종료할 수 있습니다 `None` . 다음 코드에서는 `seq1` 작업에 의해 생성 되는 및 시퀀스의 두 가지 예를 보여 줍니다 `fib` `unfold` . 첫 번째는 `seq1` 숫자를 20 개까지 포함 하는 간단한 시퀀스 일 뿐입니다. 두 번째는를 사용 하 여 `fib` `unfold` 피보나치 시퀀스를 계산 합니다. 피보나치 시퀀스의 각 요소는 이전의 두 피보나치 번호의 합계 이므로 상태 값은 시퀀스의 이전 두 숫자로 구성 된 튜플입니다. 초기 값은 `(1,1)` 시퀀스에서 처음 두 개의 숫자입니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet14.fs)]

출력은 다음과 같습니다.

```console
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

다음 코드는 무한 시퀀스의 값을 생성 하 고 계산 하기 위해 여기에 설명 된 다양 한 시퀀스 모듈 함수를 사용 하는 예제입니다. 코드를 실행 하는 데 몇 분 정도 걸릴 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a>요소 검색 및 찾기

시퀀스는 다음과 같은 목록에서 사용할 수 있는 기능을 지원 합니다. [seq. exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#exists), [array.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#exists), seq. [Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#find), [seq. findindex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#findIndex), [Seq. pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#pick), [seq. trfind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFind)및 [seq.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFindIndex) 시퀀스에 사용할 수 있는 이러한 함수 버전은 검색 되는 요소 까지만 시퀀스를 평가 합니다. 예제는 [목록](lists.md)을 참조 하세요.

## <a name="obtaining-subsequences"></a>버킷이라고 가져오기

[Seq. 필터](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#filter) 및 [seq. 선택](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#choose) 은 시퀀스 요소가 평가 될 때까지 필터링 및 선택이 발생 하지 않는다는 점을 제외 하면 목록에 사용할 수 있는 해당 함수와 유사 합니다.

[Seq. truncate](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#truncate) 은 다른 시퀀스에서 시퀀스를 만들지만 시퀀스를 지정 된 수의 요소로 제한 합니다. [Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#take) 는 시퀀스의 시작 부분부터 지정 된 수의 요소만 포함 하는 새 시퀀스를 만듭니다. 시퀀스에 지정 된 것 보다 더 많은 요소가 있으면에서을 `Seq.take` throw `System.InvalidOperationException` 합니다. 와의 차이 `Seq.take` 는 `Seq.truncate` `Seq.truncate` 요소 수가 지정한 수보다 적으면에서 오류를 생성 하지 않는다는 것입니다.

다음 코드에서는 및의 동작과의 차이점을 보여 `Seq.truncate` 줍니다 `Seq.take` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet16.fs)]

오류가 발생 하기 전의 출력은 다음과 같습니다.

```console
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
```

[TakeWhile](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#takeWhile)를 사용 하 여 조건자 함수 (부울 함수)를 지정 하 고 조건자가 인 원래 시퀀스의 요소로 구성 된 다른 시퀀스에서 시퀀스를 만든 다음 조건자가 반환 하는 `true` 첫 번째 요소 앞에서 중지할 수 있습니다 `false` . [Seq. skip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#skip) 은 다른 시퀀스의 지정 된 수의 첫 번째 요소를 건너뛰고 나머지 요소를 반환 하는 시퀀스를 반환 합니다. [SkipWhile](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#skipWhile) 는 조건자가 반환 되는 한 다른 시퀀스의 첫 번째 요소를 건너뛴 `true` 다음 조건자가 반환 하는 첫 번째 요소부터 시작 하 여 나머지 요소를 반환 하는 시퀀스를 반환 `false` 합니다.

다음 코드 예제에서는, 및의 차이점을 보여 줍니다 `Seq.takeWhile` `Seq.skip` `Seq.skipWhile` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet17.fs)]

출력은 다음과 같습니다.

```console
1 4 9
36 49 64 81 100
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>시퀀스 변환

[Seq. 쌍](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#pairwise) 은 입력 시퀀스의 연속 요소가 튜플로 그룹화 되는 새 시퀀스를 만듭니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#windowed) 는와 유사 합니다. `Seq.pairwise` 단, 튜플 시퀀스를 생성 하는 대신 시퀀스에서 인접 한 요소 ( *창*)의 복사본을 포함 하는 배열 시퀀스를 생성 합니다. 각 배열에 원하는 인접 요소 수를 지정 합니다.

다음 코드 예제에서는 `Seq.windowed`의 사용법을 보여줍니다. 이 경우 창의 요소 수는 3입니다. 이 예제에서는 `printSeq` 앞의 코드 예제에서 정의 된를 사용 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet180.fs)]

출력은 다음과 같습니다.

초기 시퀀스:

```console
1.0 1.5 2.0 1.5 1.0 1.5

Windows of length 3:
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|]

Moving average:
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>여러 시퀀스를 사용 하는 작업

[Seq.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#zip) 및 [Seq.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#zip3) 은 두 개 또는 세 개의 시퀀스를 사용 하 고 튜플 시퀀스를 생성 합니다. 이러한 함수는 [목록](lists.md)에 사용할 수 있는 해당 함수와 유사 합니다. 한 시퀀스를 두 개 이상의 시퀀스로 분리 하는 기능이 없습니다. 시퀀스에이 기능이 필요한 경우 시퀀스를 목록으로 변환 하 고 [list. 압축 풀기](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip)를 사용 합니다.

## <a name="sorting-comparing-and-grouping"></a>정렬, 비교 및 그룹화

목록에 대해 지원 되는 정렬 함수도 시퀀스와 함께 사용할 수 있습니다. 여기에는 [seq. sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sort) 및 [sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sortBy)가 포함 됩니다. 이러한 함수는 전체 시퀀스를 반복 합니다.

[Seq. compareWith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#compareWith) 함수를 사용 하 여 두 시퀀스를 비교 합니다. 함수는 연속 된 요소를 차례로 비교 하 고, 첫 번째 같지 않은 쌍을 발견할 경우 중지 합니다. 추가 요소는 비교에 영향을 주지 않습니다.

다음 코드는 `Seq.compareWith`의 사용법을 보여줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet19.fs)]

위의 코드에서는 첫 번째 요소만 계산 및 검사 되 고 결과는-1입니다.

[Seq.countby](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#countBy) 는 각 요소에 대 한 *키* 라는 값을 생성 하는 함수를 사용 합니다. 각 요소에 대해이 함수를 호출 하 여 각 요소에 대 한 키를 생성 합니다. `Seq.countBy` 그런 다음는 키 값을 포함 하는 시퀀스와 키의 각 값을 생성 한 요소 수의 개수를 반환 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet201.fs)]

출력은 다음과 같습니다.

```console
(1, 34) (2, 33) (0, 33)
```

위의 출력은 키 1, 키 2를 생성 한 33 값 및 키 0을 생성 한 33 값을 생성 한 원래 시퀀스의 요소가 34 개 있음을 보여 줍니다.

[Seq. groupBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#groupBy)를 호출 하 여 시퀀스의 요소를 그룹화 할 수 있습니다. `Seq.groupBy` 요소에서 키를 생성 하는 시퀀스 및 함수를 사용 합니다. 함수는 시퀀스의 각 요소에 대해 실행 됩니다. `Seq.groupBy` 각 튜플의 첫 번째 요소가 키이 고 두 번째 요소가 해당 키를 생성 하는 요소의 시퀀스인 경우 튜플 시퀀스를 반환 합니다.

다음 코드 예제에서는를 사용 하 여 `Seq.groupBy` 1에서 100 사이의 숫자 시퀀스를 고유 키 값이 0, 1, 2 인 세 개의 그룹으로 분할 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet202.fs)]

출력은 다음과 같습니다.

```console
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

[Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#distinct)를 호출 하 여 중복 요소를 제거 하는 시퀀스를 만들 수 있습니다. 또는 각 요소에서 키 생성 함수를 호출 하는 [seq.distinctby](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#distinctBy)를 사용할 수 있습니다. 결과 시퀀스에는 고유 키가 있는 원래 시퀀스의 요소가 포함 됩니다. 이전 요소에 대 한 중복 키를 생성 하는 이후 요소는 삭제 됩니다.

다음 코드 예제에서는를 사용 하는 방법을 보여 줍니다 `Seq.distinct` . `Seq.distinct` 이진 숫자를 나타내는 시퀀스를 생성 한 다음 유일한 고유 요소만 0과 1 임을 보여 주는 것을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet22.fs)]

다음 코드에서는 `Seq.distinctBy` 음수 및 양수가 포함 된 시퀀스를 시작 하 고 절대 값 함수를 키 생성 함수로 사용 하는 방법을 보여 줍니다. 음수는 시퀀스에서 앞에 표시 되 고 동일한 절대값 또는 키를 갖는 양수 대신 선택 되므로 시퀀스의 음수에 해당 하는 모든 양수가 결과 시퀀스에 누락 됩니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a>읽기 전용 및 캐시 된 시퀀스

[Seq. readonly](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#readonly) 는 시퀀스의 읽기 전용 복사본을 만듭니다. `Seq.readonly` 는 배열과 같은 읽기/쓰기 컬렉션이 있고 원래 컬렉션을 수정 하지 않으려는 경우에 유용 합니다. 이 함수는 데이터 캡슐화를 유지 하는 데 사용할 수 있습니다. 다음 코드 예제에서는 배열을 포함 하는 형식이 생성 됩니다. 속성은 배열을 노출 하지만 배열을 반환 하는 대신를 사용 하 여 배열에서 만든 시퀀스를 반환 합니다 `Seq.readonly` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq. cache](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#cache) 는 시퀀스의 저장 된 버전을 만듭니다. 를 사용 `Seq.cache` 하 여 시퀀스의 재평가를 방지 하거나 시퀀스를 사용 하는 스레드가 여러 개 있는 경우 각 요소가 한 번만 처리 되도록 해야 합니다. 여러 스레드에서 사용 되는 시퀀스를 사용 하는 경우 원래 시퀀스에 대 한 값을 열거 하 고 계산 하는 하나의 스레드를 사용 하 고 나머지 스레드는 캐시 된 시퀀스를 사용할 수 있습니다.

## <a name="performing-computations-on-sequences"></a>시퀀스에 대 한 계산 수행

간단한 산술 연산은 [seq. average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#average), [seq. sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sum), [Array.averageby](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#averageBy), [seq. sumby](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sumBy)등의 목록에서와 같습니다.

[Seq. 접기](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#fold), [seq. 감소](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#reduce)및 [seq. scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#scan) 은 목록에 사용할 수 있는 해당 함수와 유사 합니다. 시퀀스는 지원을 나열 하는 이러한 함수의 전체 변형 하위 집합을 지원 합니다. 자세한 내용 및 예제는 [목록](lists.md)을 참조 하십시오.

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
- [F# 형식](fsharp-types.md)
