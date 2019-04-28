---
title: 시퀀스
description: 사용 하는 방법을 알아봅니다 F# 시퀀스는 많은 경우 데이터의 컬렉션을 정렬 하지만 모든 요소를 사용 하 여 반드시 예상 하지도 않습니다.
ms.date: 02/19/2019
ms.openlocfilehash: a7791be5e8bd07d81fe9e890fc5896b181f0cb39
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770476"
---
# <a name="sequences"></a>시퀀스

> [!NOTE]
> 이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

A *시퀀스* 논리는 일련의 요소는 한 가지 유형의 모든 합니다. 시퀀스는 대규모 데이터의 컬렉션을 정렬 있지만 모든 요소를 사용 하려면 반드시 예상 되지 않는 경우에 특히 유용 합니다. 시퀀스는 목록의 모든 요소는 사용할 수 있는 경우 보다 더 나은 성능을 제공할 수 있도록 개별 시퀀스 요소로만 계산 됩니다 필요 합니다. 시퀀스가 표시 됩니다는 `seq<'T>` 별칭인 형식에 대 한 `System.Collections.Generic.IEnumerable`합니다. 구현 하는.NET Framework 형식 따라서 `System.IEnumerable` 시퀀스로 사용할 수 있습니다. 합니다 [Seq 모듈](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) 시퀀스를 포함 하는 조작에 대 한 지원을 제공 합니다.

## <a name="sequence-expressions"></a>시퀀스 식

A *식 시퀀스* 시퀀스 계산 되는 식입니다. 시퀀스 식에는 여러 가지 형식 걸릴 수 있습니다. 가장 간단한 형태는 범위를 지정 합니다. 예를 들어 `seq { 1 .. 5 }` 끝점 1과 5를 포함 하는 5 개 요소가 포함 된 시퀀스를 만듭니다. 있습니다 하거나 지정할 수는 증가 (감소) double 두 기간 사이입니다. 예를 들어, 다음 코드는 10의 배수 시퀀스를 만듭니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

시퀀스 식으로 이루어져 있습니다 F# 시퀀스의 값을 생성 하는 식입니다. 사용할 수는 `yield` 시퀀스에 포함 되는 값을 생성 하는 키워드입니다.

다음은 예제입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

사용할 수는 `->` 연산자 대신 `yield`, 경우 생략할 수 있습니다는 `do` 키워드를 다음 예제에서와 같이 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

다음 코드에서 표를 나타내는 배열을 인덱스와 함께 좌표 쌍의 목록을 생성 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

`if` 는 필터 식 시퀀스에서 사용 합니다. 예를 들어 함수가 있다고 가정 하 고만 소수 시퀀스를 생성 하 `isprime` 형식의 `int -> bool`, 다음과 같은 시퀀스를 생성 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

사용 하는 경우 `yield` 또는 `->` 반복에서 반복 될 때마다 것으로 예상 되는 시퀀스의 단일 요소를 생성 합니다. 각 반복에서 요소의 시퀀스를 생성 하는 경우 사용 하 여 `yield!`입니다. 이 경우 각 반복에 대해 생성 된 요소는 최종 시퀀스를 생성 하기 위해 연결 됩니다.

시퀀스 식에서 함께 여러 식을 결합할 수 있습니다. 각 식에 의해 생성 된 요소는 서로 연결 됩니다. 예를 들어이 항목의 "예" 섹션을 참조 하세요.

## <a name="examples"></a>예제

첫 번째 예제에서는 반복, 필터 및 배열을 생성 하는 yield를 포함 하는 시퀀스 식을 사용 합니다. 이 코드는 1과 100 콘솔로 사이의 소수 숫자 시퀀스를 인쇄합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

다음 코드에서는 `yield` 두 및 제품으로 구성 된 각 3 개 요소의 튜플로 구성 된 곱하기 테이블을 만듭니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

다음 예제에서는 사용 `yield!` 개별 시퀀스를 단일 최종 시퀀스로 결합 합니다. 이 경우 이진 트리의 각 하위 시퀀스는 마지막 시퀀스를 생성 하는 재귀 함수에 연결 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a>시퀀스 사용

시퀀스를 지 원하는 다양 한 기능을 동일 [나열](lists.md)합니다. 시퀀스는 그룹화 키 생성 함수를 사용 하 여 계산 등 작업을 지원 합니다. 또한 시퀀스는 하위 시퀀스를 추출 하는 것에 대 한 더 다양 한 함수를 지원 합니다.

목록, 배열, 집합 및 지도 같은 많은 데이터 형식을 열거 가능한 컬렉션 이기 때문에 암시적으로 시퀀스입니다. 일반적인 중 하나를 사용 하 여 작동 하므로 인수 시퀀스를 사용 하는 함수 F# 데이터 형식을 구현 하는.NET Framework 데이터 형식 외에도 `System.Collections.Generic.IEnumerable<'T>`합니다. 이 목록에만 사용할 수 있습니다는 인수로 목록을 사용 하는 함수를 대조해 보세요. 형식 `seq<'T>` 에 대 한 형식 약어 `IEnumerable<'T>`합니다. 즉, 제네릭 구현 하는 형식 `System.Collections.Generic.IEnumerable<'T>`, 설정 및 맵 배열, 목록, 포함 하는 F#, 및도 대부분의.NET Framework 컬렉션 형식을와 호환 되는 `seq` 입력 하 고 시퀀스 필요한 곳 마다 사용할 수 있습니다 .

## <a name="module-functions"></a>모듈 함수

합니다 [Seq 모듈](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) 에 [Microsoft.FSharp.Collections 네임 스페이스](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) 시퀀스를 사용 하 여 작업 하기 위한 함수가 포함 되어 있습니다. 이러한 함수 목록, 배열, 맵 및 집합 에서도 때문에 작업할 해당 유형의 모든 열거할 이며 시퀀스로 취급 될 수 있습니다.

## <a name="creating-sequences"></a>시퀀스 만들기

앞에서 설명한 대로 시퀀스 식을 사용 하 여 또는 특정 함수를 사용 하 여 시퀀스를 만들 수 있습니다.

사용 하 여 빈 시퀀스를 만들 수 있습니다 [Seq.empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59)를 사용 하 여 하나의 지정 된 요소의 시퀀스를 만들 수 있습니다 [Seq.singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7)합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet9.fs)]

사용할 수 있습니다 [Seq.init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) 요소를 제공 하는 함수를 사용 하 여 생성 됩니다 순서를 만드는 합니다. 또한 시퀀스의 크기를 제공합니다. 이 함수는 마찬가지로 [List.init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83)한다는 점을 제외 하는 요소 시퀀스를 반복 될 때까지 만들어지지 않습니다. 다음 코드에서는 `Seq.init`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet10.fs)]

출력은 다음과 같습니다.

```
0 10 20 30 40
```

사용 하 여 [Seq.ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) 하 고 [Seq.ofList&#60;없습니다&#62; 함수](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), 배열 및 목록에서 순서를 만들 수 있습니다. 그러나 변환할 수도 있습니다 배열과 목록을 순서에 캐스트 연산자를 사용 하 여 합니다. 두 가지 방법은 모두 다음 코드에 표시 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet11.fs)]

사용 하 여 [Seq.cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334)에 정의 된 것 처럼 약하게 형식화 된 컬렉션에서 시퀀스를 만들 수 있습니다 `System.Collections`합니다. 이러한 약한 형식의 컬렉션 요소 형식이 `System.Object` 제네릭이 아닌을 사용 하 여 열거 되 고 `System.Collections.Generic.IEnumerable&#96;1` 형식입니다. 다음 코드의 사용을 보여 줍니다 `Seq.cast` 변환할는 `System.Collections.ArrayList` 시퀀스로 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet12.fs)]

사용 하 여 무한 시퀀스를 정의할 수 있습니다 합니다 [Seq.initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) 함수입니다. 이러한 시퀀스 요소 인덱스에서 각 요소를 생성 하는 함수를 제공할 수 있습니다. 지연 평가 인해 무한 시퀀스는 가능한 요소를 지정 하는 함수를 호출 하 여 필요에 따라 만들어집니다. 다음 코드 예제에서는 부동 소수점 숫자를이 예제의 교대로 반복 되는 일련의 연속 된 정수 제곱의 평균은 무한 시퀀스를 생성 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet13.fs)]

[Seq.unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) 상태를 사용 하 고 시퀀스의 각 후속 요소를 생성 하기 위해 변환 하는 계산 함수에서 시퀀스를 생성 합니다. 상태는 각 요소를 계산 하는 데 사용 되 고 각 요소는 계산 된 대로 변경할 수 있는 값만. 두 번째 인수를 `Seq.unfold` 는 시퀀스를 시작 하는 데 사용 되는 초기 값입니다. `Seq.unfold` 옵션 형식을 반환 하 여 시퀀스를 종료 하는 상태에 대 한 사용을 `None` 값입니다. 다음 코드는 시퀀스의 두 가지 예제를 보여 줍니다. `seq1` 하 고 `fib`를 통해 생성 된는 `unfold` 작업 합니다. 첫 번째 `seq1`, 단순한 20 까지의 숫자를 사용 하 여 간단한 시퀀스입니다. 두 번째 `fib`를 사용 하 여 `unfold` 피보나치 시퀀스를 계산 합니다. 피보나치 시퀀스의 각 요소는 이전 두 피보나치 수의 합 이기 때문에 상태 값은 시퀀스에서 이전 두 숫자의 구성 된 튜플입니다. 초기 값은 `(1,1)`, 시퀀스에서 처음 두 번호입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet14.fs)]

출력은 다음과 같습니다.

```
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

다음 코드는 많은 생성 하 고 무한 시퀀스의 값을 계산 합니다. 여기에 설명 된 시퀀스 모듈 함수를 사용 하는 예제입니다. 코드를 실행 하는 데는 몇 분 정도 걸릴 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a>검색 및 요소 찾기

시퀀스는 목록을 사용 하 여 사용할 수 있는 기능을 지원합니다. [Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565)합니다 [Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8)를 [Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3)를 [Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq.tryFind ](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47), 및 [Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a)합니다. 시퀀스에 사용할 수 있는 이러한 함수의 버전은 검색 되는 요소까지만 시퀀스를 평가 합니다. 예제를 보려면 [나열](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)합니다.

## <a name="obtaining-subsequences"></a>시퀀스 가져오기

[Seq.filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) 하 고 [Seq.choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) 은 해당 함수와 목록에 사용할 수 있는 점을 제외 하 고 필터링과 선택 시퀀스 요소를 계산할 때까지 발생 하지 않습니다.

[Seq.truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) 다른 시퀀스의 시퀀스를 만들지만 시퀀스 요소의 지정 된 수를 제한 합니다. [Seq.take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) 지정된 된 수의 시퀀스의 시작 요소를 포함 하는 새 시퀀스를 만듭니다. 을 사용 하려면 지정한 것 보다 더 적은 요소가 순서로 `Seq.take` throw를 `System.InvalidOperationException`입니다. 차이점 `Seq.take` 하 고 `Seq.truncate` 는 `Seq.truncate` 요소 수가 지정 개수 보다 적은 경우 오류를 생성 하지 않습니다.

다음 코드의 동작을 표시 하 고 간의 차이점 `Seq.truncate` 고 `Seq.take`입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet16.fs)]

출력은 오류가 발생 하기 전에 다음과 같습니다.

```
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100 
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100
```

사용 하 여 [Seq.takeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), 조건자 함수 (부울 함수)를 지정 하는 조건자가 원래 시퀀스의 해당 요소의 다른 시퀀스에서 시퀀스를 만들려면 `true`, 하지만 중지 합니다. 조건자 반환 하는 첫 번째 요소 앞 `false`합니다. [Seq.skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) 다른 시퀀스의 첫 번째 요소의 지정 된 수를 건너뛰고 나머지 요소를 반환 하는 시퀀스를 반환 합니다. [Seq.skipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) 조건자를 반환 하는 있다면 다른 시퀀스의 첫 번째 요소를 건너뛴 시퀀스 반환 `true`, 다음 조건자 반환하는첫번째요소를사용하여시작하고나머지요소를반환하고`false`.

다음 코드 예제에서는의 동작을 보여 줍니다과 차이점이 `Seq.takeWhile`, `Seq.skip`, 및 `Seq.skipWhile`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet17.fs)]

출력은 다음과 같습니다.

```
1 4 9 
36 49 64 81 100 
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>시퀀스 변환

[Seq.pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) 연속 입력된 시퀀스 요소의 튜플로 그룹화 되는 새 시퀀스를 만듭니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq.windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) 비슷합니다 `Seq.pairwise`튜플 시퀀스를 생성 하는 대신 인접 요소의 복사본을 포함 하는 배열의 시퀀스를 생성 한다는 점을 제외 하면, (한 *창*) 시퀀스에서 합니다. 각 배열에 있는 인접 한 요소 수를 지정 합니다.

다음 코드 예제에서는 `Seq.windowed`의 사용법을 보여줍니다. 이 경우 창에서 요소 수는 3입니다. 이 예제에서는 사용 `printSeq`, 이전 코드 예제에 정의 되어 있는 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet180.fs)]

출력은 다음과 같습니다.

초기 시퀀스:

```
1.0 1.5 2.0 1.5 1.0 1.5 

Windows of length 3: 
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|] 

Moving average: 
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>여러 시퀀스를 사용 하 여 작업

[Seq.zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) 하 고 [Seq.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) 시퀀스 두 또는 세 개 및 튜플 시퀀스를 생성 합니다. 이러한 함수는 해당 함수에 사용할 수 있는 비슷합니다 [나열](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)합니다. 두 개 이상의 시퀀스를 단일 시퀀스로 구분 하는 해당 기능은 없습니다. 시퀀스에 대해이 기능을 해야 하는 경우 목록에 시퀀스를 변환 하 고 사용 하 여 [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)합니다.

## <a name="sorting-comparing-and-grouping"></a>정렬, 비교 및 그룹화

정렬 함수 목록에 대 한 지원 되는 시퀀스와도 작동 합니다. 여기에 [Seq.sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) 하 고 [Seq.sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f)합니다. 이러한 함수는 전체 시퀀스를 반복합니다.

사용 하 여 두 시퀀스를 비교 합니다 [Seq.compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) 함수입니다. 함수를 연속 요소를 비교 하 여 같지 않은 첫 번째 쌍을 발견할 때 중지 됩니다. 모든 추가 요소가 비교에 기여 하지 않습니다.

다음 코드는 `Seq.compareWith`의 사용법을 보여줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet19.fs)]

이전 코드에서 첫 번째 요소에만 계산 및 조사를 하 고 결과-1입니다.

[Seq.countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) 이라고 하는 값을 생성 하는 함수를 *키* 각 요소에 대 한 합니다. 키를 각 요소에 대해이 함수를 호출 하 여 각 요소에 대해 생성 됩니다. `Seq.countBy` 키 값 및 키의 각 값을 생성 하는 요소의 개수를 포함 하는 시퀀스를 반환 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet201.fs)]

출력은 다음과 같습니다.

```
(1, 34) (2, 33) (0, 33)
```

이전 출력 키 2를 생성 하는 3만 3천 값 및 0 키를 생성 하는 3만 3천 값 1, 키를 생성 하는 원래 시퀀스의 34 요소 되었음을 보여 줍니다.

호출 하 여 시퀀스의 요소를 그룹화 할 수 있습니다 [Seq.groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd)합니다. `Seq.groupBy` 시퀀스 및 요소에서 키를 생성 하는 함수를 사용 합니다. 함수는 시퀀스의 각 요소에 대해 실행 됩니다. `Seq.groupBy` 튜플에 있는 각 튜플의 첫 번째 요소 키가 고 두 번째는 해당 키를 생성 하는 요소 시퀀스의 시퀀스를 반환 합니다.

다음 코드 예제에서는 `Seq.groupBy` 100부터 1 까지의 숫자 시퀀스 키 값이 각각 0, 1 및 2에 있는 3 개의 그룹으로 분할 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet202.fs)]

출력은 다음과 같습니다.

```
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

호출 하 여 중복 요소를 제거 하는 시퀀스를 만들 수 있습니다 [Seq.distinct](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401)합니다. 사용할 수 있습니다 [Seq.distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), 각 요소에 대해 호출할 키 생성 함수를 사용 합니다. 결과 시퀀스; 고유 키가 원래 시퀀스의 요소를 포함 합니다. 이전 요소에 중복 키를 생성 하는 이후 요소가 삭제 됩니다.

다음 코드 예제에서는 `Seq.distinct`합니다. `Seq.distinct` 이진 숫자를 나타내는 시퀀스를 생성 한 다음만 고유한 요소는 0과 1을 표시 하 여 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet22.fs)]

다음 코드에서는 `Seq.distinctBy` 양수 및 음수를 포함 하는 시퀀스를 사용 하 여 시작 하 고 키 생성 함수 절대 값 함수를 사용 하 여 합니다. 결과 시퀀스 시퀀스 앞에 표시 되는 음수 이므로 같은 절대 있는 양수 대신 선택 됩니다 시퀀스의 음수 값에 해당 하는 모든 양수 없습니다. 값 또는 키입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a>읽기 전용 및 캐시 된 순서

[Seq.readonly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) 시퀀스의 읽기 전용 복사본을 만듭니다. `Seq.readonly` 배열 같은 읽기 전용 컬렉션에 있고 원래 컬렉션을 수정 하지 않을 때 유용 합니다. 이 함수는 데이터 캡슐화를 유지 하기 위해 사용할 수 있습니다. 다음 코드 예제에서는 배열을 포함 하는 형식이 만들어집니다. 배열 속성을 노출 하지만 사용 하 여 배열에서 만든 시퀀스를 반환 배열에 반환 하는 대신 `Seq.readonly`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq.cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) 시퀀스의 저장 된 버전을 만듭니다. 사용 하 여 `Seq.cache` 시퀀스를 사용 하는 여러 스레드를 가질 수 있지만 각 요소에 한 번만 대상이 되는 있는지 확인 해야 하는 경우 시퀀스의 재평가 방지 하려면. 여러 스레드에서 사용 되는 시퀀스에 있는 경우 하나의 스레드를 열거 하 고 원래 순서에 대 한 값을 계산 있을 수 있으며 나머지 스레드는 캐시 된 시퀀스를 사용할 수 있습니다.

## <a name="performing-computations-on-sequences"></a>시퀀스에 대 한 계산 수행

간단한 산술 연산은 목록 같은 같은 [Seq.average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8)를 [Seq.sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a)를 [Seq.averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8)를 [Seq.sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)등.

[Seq.fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [Seq.reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9), 및 [Seq.scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) 목록에 사용할 수 있는 해당 함수와 같은 됩니다. 시퀀스는 지원이 요약 되어 있는 이러한 함수의 전체 변형은 하위 집합을 지원 합니다. 자세한 내용 및 예제를 참조 하세요 [나열](lists.md)합니다.

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [F# 형식](fsharp-types.md)
