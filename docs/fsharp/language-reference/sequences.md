---
title: 시퀀스
description: 순서가 지정 된 데이터 F# 컬렉션이 크고 모든 요소를 반드시 사용할 필요는 없는 경우 시퀀스를 사용 하는 방법을 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: 34e03f1cead0a9f678f637afcb6c8397ef7572bc
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971438"
---
# <a name="sequences"></a>시퀀스

> [!NOTE]
> 이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

*시퀀스* 는 단일 형식의 논리적 일련의 요소입니다. 시퀀스는 광범위 하 고 정렬 된 데이터 컬렉션이 있지만 모든 요소를 반드시 사용할 필요는 없는 경우에 특히 유용 합니다. 개별 시퀀스 요소는 필요에 따라 계산 되므로 모든 요소가 사용 되지 않는 상황에서 시퀀스는 목록 보다 더 나은 성능을 제공할 수 있습니다. 시퀀스는 <xref:System.Collections.Generic.IEnumerable%601>에 대 한 별칭인 `seq<'T>` 형식으로 표시 됩니다. 따라서 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현 하는 모든 .NET 형식을 시퀀스로 사용할 수 있습니다. [Seq 모듈](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) 은 시퀀스와 관련 된 조작을 지원 합니다.

## <a name="sequence-expressions"></a>시퀀스 식

*시퀀스 식은* 시퀀스로 계산 되는 식입니다. 시퀀스 식은 많은 폼을 사용할 수 있습니다. 가장 간단한 형태는 범위를 지정 합니다. 예를 들어 `seq { 1 .. 5 }`은 끝점 1과 5를 포함 하 여 다섯 개의 요소를 포함 하는 시퀀스를 만듭니다. 두 개의 double 기간 사이에 증가 (또는 감소)를 지정할 수도 있습니다. 예를 들어 다음 코드는 10의 배수로 이루어진 시퀀스를 만듭니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

시퀀스 식은 시퀀스의 값을 F# 생성 하는 식으로 구성 됩니다. 값을 프로그래밍 방식으로 생성할 수도 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

앞의 예제에서는 `->` 연산자를 사용 하 여 해당 값이 시퀀스의 일부가 될 식을 지정할 수 있습니다. 뒤에 오는 코드의 모든 부분에서 값을 반환 하는 경우에만 `->`을 사용할 수 있습니다.

또는 다음과 같은 선택적 `yield`를 사용 하 여 `do` 키워드를 지정할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

다음 코드에서는 표를 나타내는 배열에 대 한 인덱스와 함께 좌표 쌍의 목록을 생성 합니다. 첫 번째 `for` 식에는 `do`를 지정 해야 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

시퀀스에 사용 되는 `if` 식은 필터입니다. 예를 들어 소수 숫자만 포함 하는 시퀀스를 생성 하려면 `int -> bool`형식의 함수가 `isprime` 경우 다음과 같이 시퀀스를 생성 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

앞에서 설명한 것 처럼 `if`와 함께 `else` 분기가 없으므로 여기에 `do` 필요 합니다. `->`를 사용 하려고 하면 모든 분기에서 값을 반환 하지 않는다는 오류가 표시 됩니다.

## <a name="the-yield-keyword"></a>`yield!` 키워드

경우에 따라 요소의 시퀀스를 다른 시퀀스에 포함할 수 있습니다. 다른 시퀀스 내에 시퀀스를 포함 하려면 `yield!` 키워드를 사용 해야 합니다.

```fsharp
// Repeats '1 2 3 4 5' ten times
seq {
    for _ in 1..10 do
        yield! seq { 1; 2; 3; 4; 5}
}
```

`yield!`를 고려 하는 또 다른 방법은 내부 시퀀스를 평면화 한 다음 포함 하는 시퀀스에이를 포함 하는 것입니다.

식에 `yield!`를 사용 하는 경우 다른 모든 단일 값은 `yield` 키워드를 사용 해야 합니다.

```fsharp
// Combine repeated values with their values
seq {
    for x in 1..10 do
        yield x
        yield! seq { for i in 1..x -> i}
}
```

이전 예제에서 `x`만 지정 하면 시퀀스에서 값을 생성 하지 않습니다.

## <a name="examples"></a>예제

첫 번째 예에서는 반복, 필터 및 양보를 포함 하는 시퀀스 식을 사용 하 여 배열을 생성 합니다. 이 코드는 1에서 100 사이의 일련 번호 시퀀스를 콘솔에 출력 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

다음 예에서는 두 개의 요소로 구성 된 튜플로 구성 된 곱하기 테이블을 만듭니다. 각 요소는 두 개의 요소와 제품으로 구성 됩니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

다음 예에서는 `yield!`를 사용 하 여 개별 시퀀스를 단일 최종 시퀀스로 결합 하는 방법을 보여 줍니다. 이 경우 이진 트리의 각 하위 트리에 대 한 시퀀스는 재귀적 함수에서 연결 되어 최종 시퀀스를 생성 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a>시퀀스 사용

시퀀스는 [목록과](lists.md)동일한 많은 기능을 지원 합니다. 시퀀스는 키 생성 함수를 사용 하 여 그룹화 및 계산 등의 작업도 지원 합니다. 시퀀스는 버킷이라고을 추출 하는 더 다양 한 함수도 지원 합니다.

목록, 배열, 집합 및 맵과 같은 많은 데이터 형식은 열거 가능한 컬렉션 이므로 암시적으로 시퀀스 됩니다. 시퀀스를 인수로 사용 하는 함수는 `System.Collections.Generic.IEnumerable<'T>`을 구현 하는 .NET 데이터 F# 형식 외에도 모든 공통 데이터 형식에서 작동 합니다. 목록을 인수로 사용 하는 함수와 대조 하 여 목록만 사용할 수 있습니다. `seq<'T>` 형식은 `IEnumerable<'T>`의 형식 약어입니다. 즉, 배열, 목록, 집합 및 맵을 F#포함 하는 제네릭 `System.Collections.Generic.IEnumerable<'T>`를 구현 하는 모든 형식 및 대부분의 .net 컬렉션 형식은 `seq` 형식과 호환 되며 시퀀스가 필요한 모든 위치에서 사용할 수 있습니다.

## <a name="module-functions"></a>모듈 함수

[Fsharp.core 네임 스페이스](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) 의 [Seq 모듈](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) 에는 시퀀스 작업을 위한 함수가 포함 되어 있습니다. 이러한 함수는 모두 열거 가능 하므로 시퀀스로 처리 될 수 있기 때문에 목록, 배열, 맵 및 집합 에서도 작동 합니다.

## <a name="creating-sequences"></a>시퀀스 만들기

앞에서 설명한 대로 시퀀스 식을 사용 하거나 특정 함수를 사용 하 여 시퀀스를 만들 수 있습니다.

[Seq](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59)를 사용 하 여 빈 시퀀스를 만들거나 [seq. singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7)을 사용 하 여 지정 된 요소의 시퀀스를 만들 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet9.fs)]

[Seq. init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) 를 사용 하면 사용자가 제공 하는 함수를 사용 하 여 요소가 생성 되는 시퀀스를 만들 수 있습니다. 또한 시퀀스의 크기를 제공 합니다. 이 함수는 시퀀스가 반복 될 때까지 요소가 생성 되지 않는다는 점을 제외 하 고는 [List. init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83)와 동일 합니다. 다음 코드는 `Seq.init`를 사용 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet10.fs)]

출력은 다음과 같습니다.

```console
0 10 20 30 40
```

[Seq. ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) 및 [Seq. ofarray&#60;&#62; 함수](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d)를 사용 하 여 배열 및 목록에서 시퀀스를 만들 수 있습니다. 그러나 캐스트 연산자를 사용 하 여 배열 및 목록을 시퀀스로 변환할 수도 있습니다. 다음 코드에서는 두 가지 방법을 모두 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet11.fs)]

[Seq. 캐스트](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334)를 사용 하 여 `System.Collections`에 정의 된 것과 같은 약하게 형식화 된 컬렉션에서 시퀀스를 만들 수 있습니다. 이러한 약하게 형식화 된 컬렉션에는 `System.Object` 요소 형식이 있으며 제네릭이 아닌 `System.Collections.Generic.IEnumerable&#96;1` 형식을 사용 하 여 열거 됩니다. 다음 코드는 `Seq.cast`를 사용 하 여 `System.Collections.ArrayList`를 시퀀스로 변환 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet12.fs)]

[Seq. initinfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) 함수를 사용 하 여 무한 시퀀스를 정의할 수 있습니다. 이러한 시퀀스의 경우 요소의 인덱스에서 각 요소를 생성 하는 함수를 제공 합니다. 지연 계산으로 인해 무한 시퀀스를 사용할 수 있습니다. 요소는 지정 된 함수를 호출 하 여 필요에 따라 만들어집니다. 다음 코드 예제에서는 부동 소수점 숫자의 무한 시퀀스를 생성 합니다 .이 경우 연속 되는 정수의 사각형 reciprocals 교대로 반복 되는 연속 된 정수입니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet13.fs)]

[펼침](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) 는 상태를 사용 하는 계산 함수에서 시퀀스를 생성 하 고 시퀀스의 각 후속 요소를 생성 하도록 변환 합니다. 상태는 각 요소를 계산 하는 데 사용 되는 값 이며 각 요소가 계산 될 때 변경 될 수 있습니다. `Seq.unfold`에 대 한 두 번째 인수는 시퀀스를 시작 하는 데 사용 되는 초기 값입니다. `Seq.unfold`는 상태에 대해 옵션 유형을 사용 합니다 .이를 통해 `None` 값을 반환 하 여 시퀀스를 종료할 수 있습니다. 다음 코드는 `unfold` 작업에 의해 생성 되는 `seq1` 및 `fib`시퀀스의 두 가지 예를 보여 줍니다. 첫 번째 `seq1`은 최대 20 개의 숫자가 있는 간단한 시퀀스입니다. 두 번째 `fib`는 `unfold`를 사용 하 여 피보나치 시퀀스를 계산 합니다. 피보나치 시퀀스의 각 요소는 이전의 두 피보나치 번호의 합계 이므로 상태 값은 시퀀스의 이전 두 숫자로 구성 된 튜플입니다. 초기 값은 시퀀스에서 처음 두 개의 숫자인 `(1,1)`입니다.

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

시퀀스는 다음과 같은 목록에서 사용할 수 있는 기능을 지원 합니다. [seq. exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [array.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), seq. [Find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [seq. findindex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [Seq. pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [seq. trfind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47)및 [seq.](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a) 시퀀스에 사용할 수 있는 이러한 함수 버전은 검색 되는 요소 까지만 시퀀스를 평가 합니다. 예제는 [목록](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)을 참조 하세요.

## <a name="obtaining-subsequences"></a>버킷이라고 가져오기

[Seq. 필터](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) 및 [seq. 선택](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) 은 시퀀스 요소가 평가 될 때까지 필터링 및 선택이 발생 하지 않는다는 점을 제외 하면 목록에 사용할 수 있는 해당 함수와 유사 합니다.

[Seq. truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) 은 다른 시퀀스에서 시퀀스를 만들지만 시퀀스를 지정 된 수의 요소로 제한 합니다. [Seq](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) 는 시퀀스의 시작 부분부터 지정 된 수의 요소만 포함 하는 새 시퀀스를 만듭니다. 시퀀스에 지정 된 것 보다 더 많은 요소가 있는 경우 `Seq.take` `System.InvalidOperationException`throw 됩니다. `Seq.take`와 `Seq.truncate`의 차이점은 요소 수가 지정 된 숫자 보다 작은 경우 `Seq.truncate`에서 오류를 생성 하지 않는다는 것입니다.

다음 코드에서는 `Seq.truncate`와 `Seq.take`간의 동작과 차이점을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet16.fs)]

오류가 발생 하기 전의 출력은 다음과 같습니다.

```console
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
```

TakeWhile를 사용 하 여 조건자 함수 (부울 함수)를 지정 하 고 조건자가 `true`되는 원래 시퀀스의 요소로 구성 된 다른 시퀀스에서 시퀀스를 만들 수 있지만,에 대 한 첫 번째 요소 앞에서 중지 됩니다 [.](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92) 조건자가 `false`반환 합니다. [Seq. skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) 은 다른 시퀀스의 지정 된 수의 첫 번째 요소를 건너뛰고 나머지 요소를 반환 하는 시퀀스를 반환 합니다. [SkipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) 는 조건자가 `true`반환 하는 한 다른 시퀀스의 첫 번째 요소를 건너뛴 다음 조건자가 `false`반환 하는 첫 번째 요소부터 시작 하 여 나머지 요소를 반환 하는 시퀀스를 반환 합니다.

다음 코드 예제에서는 `Seq.takeWhile`, `Seq.skip`및 `Seq.skipWhile`의 동작과 차이점을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet17.fs)]

출력은 다음과 같습니다.

```console
1 4 9
36 49 64 81 100
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>시퀀스 변환

[Seq. 쌍](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) 은 입력 시퀀스의 연속 요소가 튜플로 그룹화 되는 새 시퀀스를 만듭니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) 는 `Seq.pairwise`와 비슷합니다. 단, 튜플 시퀀스를 생성 하는 대신 시퀀스에서 인접 한 요소 ( *창*)의 복사본을 포함 하는 배열 시퀀스를 생성 합니다. 각 배열에 원하는 인접 요소 수를 지정 합니다.

다음 코드 예제에서는 `Seq.windowed`의 사용법을 보여줍니다. 이 경우 창의 요소 수는 3입니다. 이 예제에서는 앞의 코드 예제에서 정의 된 `printSeq`를 사용 합니다.

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

[List.zip3 및 seq.](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) 는 두 개 또는 세 개의 시퀀스를 사용 하 고 튜플 시퀀스를 생성 [합니다.](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) 이러한 함수는 [목록](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)에 사용할 수 있는 해당 함수와 유사 합니다. 한 시퀀스를 두 개 이상의 시퀀스로 분리 하는 기능이 없습니다. 시퀀스에이 기능이 필요한 경우 시퀀스를 목록으로 변환 하 고 [list. 압축 풀기](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)를 사용 합니다.

## <a name="sorting-comparing-and-grouping"></a>정렬, 비교 및 그룹화

목록에 대해 지원 되는 정렬 함수도 시퀀스와 함께 사용할 수 있습니다. 여기에는 [seq. sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) 및 [sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f)가 포함 됩니다. 이러한 함수는 전체 시퀀스를 반복 합니다.

[Seq. compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) 함수를 사용 하 여 두 시퀀스를 비교 합니다. 함수는 연속 된 요소를 차례로 비교 하 고, 첫 번째 같지 않은 쌍을 발견할 경우 중지 합니다. 추가 요소는 비교에 영향을 주지 않습니다.

다음 코드는 `Seq.compareWith`의 사용법을 보여줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet19.fs)]

위의 코드에서는 첫 번째 요소만 계산 및 검사 되 고 결과는-1입니다.

[Seq.countby](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) 는 각 요소에 대 한 *키* 라는 값을 생성 하는 함수를 사용 합니다. 각 요소에 대해이 함수를 호출 하 여 각 요소에 대 한 키를 생성 합니다. 그런 다음 키 값이 포함 된 시퀀스와 키의 각 값을 생성 한 요소 수의 개수를 반환 합니다. `Seq.countBy`

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet201.fs)]

출력은 다음과 같습니다.

```console
(1, 34) (2, 33) (0, 33)
```

위의 출력은 키 1, 키 2를 생성 한 33 값 및 키 0을 생성 한 33 값을 생성 한 원래 시퀀스의 요소가 34 개 있음을 보여 줍니다.

[Seq. groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd)를 호출 하 여 시퀀스의 요소를 그룹화 할 수 있습니다. `Seq.groupBy`는 요소에서 키를 생성 하는 시퀀스 및 함수를 사용 합니다. 함수는 시퀀스의 각 요소에 대해 실행 됩니다. `Seq.groupBy`은 튜플 시퀀스를 반환 합니다. 여기서 각 튜플의 첫 번째 요소는 키이 고 두 번째 요소는 해당 키를 생성 하는 요소의 시퀀스입니다.

다음 코드 예제에서는 `Seq.groupBy`를 사용 하 여 1에서 100 사이의 숫자 시퀀스를 고유 키 값이 0, 1, 2 인 3 개의 그룹으로 분할 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet202.fs)]

출력은 다음과 같습니다.

```console
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

[Seq](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401)를 호출 하 여 중복 요소를 제거 하는 시퀀스를 만들 수 있습니다. 또는 각 요소에서 키 생성 함수를 호출 하는 [seq.distinctby](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75)를 사용할 수 있습니다. 결과 시퀀스에는 고유 키가 있는 원래 시퀀스의 요소가 포함 됩니다. 이전 요소에 대 한 중복 키를 생성 하는 이후 요소는 삭제 됩니다.

다음 코드 예제에서는 `Seq.distinct`를 사용 하는 방법을 보여 줍니다. `Seq.distinct`는 이진 숫자를 나타내는 시퀀스를 생성 한 다음 유일한 고유 요소만 0과 1 임을 보여 주는 것을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet22.fs)]

다음 코드에서는 음수 및 양수가 포함 된 시퀀스를 시작 하 고 절대 값 함수를 키 생성 함수로 사용 하 여 `Seq.distinctBy`를 보여 줍니다. 음수는 시퀀스에서 앞에 표시 되 고 동일한 절대값을 가진 양수 대신 선택 되기 때문에 결과 시퀀스에는 시퀀스의 음수에 해당 하는 모든 양수가 누락 됩니다. 값 또는 키입니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a>읽기 전용 및 캐시 된 시퀀스

[Seq. readonly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) 는 시퀀스의 읽기 전용 복사본을 만듭니다. `Seq.readonly`는 배열과 같은 읽기/쓰기 컬렉션이 있고 원래 컬렉션을 수정 하지 않으려는 경우에 유용 합니다. 이 함수는 데이터 캡슐화를 유지 하는 데 사용할 수 있습니다. 다음 코드 예제에서는 배열을 포함 하는 형식이 생성 됩니다. 속성은 배열을 노출 하지만 배열을 반환 하는 대신 `Seq.readonly`를 사용 하 여 배열에서 만든 시퀀스를 반환 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq. cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) 는 시퀀스의 저장 된 버전을 만듭니다. `Seq.cache`를 사용 하 여 시퀀스의 재평가를 방지 하거나 시퀀스를 사용 하는 스레드가 여러 개 있는 경우 각 요소가 한 번만 처리 되도록 해야 합니다. 여러 스레드에서 사용 되는 시퀀스를 사용 하는 경우 원래 시퀀스에 대 한 값을 열거 하 고 계산 하는 하나의 스레드를 사용 하 고 나머지 스레드는 캐시 된 시퀀스를 사용할 수 있습니다.

## <a name="performing-computations-on-sequences"></a>시퀀스에 대 한 계산 수행

간단한 산술 연산은 [seq. average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [seq. sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [Array.averageby](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [seq. sumby](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)등의 목록에서와 같습니다.

[Seq. 접기](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [seq. 감소](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9)및 [seq. scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) 은 목록에 사용할 수 있는 해당 함수와 유사 합니다. 시퀀스는 지원을 나열 하는 이러한 함수의 전체 변형 하위 집합을 지원 합니다. 자세한 내용 및 예제는 [목록](lists.md)을 참조 하십시오.

## <a name="see-also"></a>참조

- [F# 언어 참조](index.md)
- [F# 형식](fsharp-types.md)
