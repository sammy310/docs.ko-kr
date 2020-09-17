---
title: 컬렉션 형식
description: 'F # 컬렉션 형식 및 컬렉션 형식과 .NET의 차이점에 대해 알아봅니다.'
ms.date: 08/14/2020
ms.openlocfilehash: 0b5be8f656d6728fe382b1944bda0a410a94d226
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720337"
---
# <a name="f-collection-types"></a>F # 컬렉션 형식

이 항목을 검토 하 여 특정 요구에 가장 적합 한 F # 컬렉션 형식을 확인할 수 있습니다. 이러한 컬렉션 형식은 네임 스페이스에 있는 것과 같은 .NET의 컬렉션 형식과 다릅니다 `System.Collections.Generic` . 여기서 F # 컬렉션 형식은 개체 지향 큐브 뷰가 아닌 함수형 프로그래밍 관점에서 디자인 되었습니다. 구체적으로 말하자면 배열 컬렉션에만 변경 가능한 요소가 있습니다. 따라서 컬렉션을 수정 하는 경우 원래 컬렉션을 변경 하는 대신 수정 된 컬렉션의 인스턴스를 만듭니다.

또한 컬렉션 형식은 개체가 저장 되는 데이터 구조의 형식에 따라 다릅니다. 해시 테이블, 연결 된 목록 및 배열과 같은 데이터 구조에는 서로 다른 성능 특성과 사용 가능한 작업 집합이 있습니다.

## <a name="table-of-collection-types"></a>컬렉션 형식 표

다음 표에서는 F # 컬렉션 형식을 보여 줍니다.

|유형|Description|관련 링크|
|----|-----------|-------------|
|[목록](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-fsharplist-1.html)|동일한 형식의 변경 되지 않은 순서가 지정 된 일련의 요소입니다. 연결 된 목록으로 구현 됩니다.|[목록](lists.md)<br /><br />[List 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)|
|[배열](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-array-1.html)|동일한 형식의 연속 데이터 요소에 대 한 변경 가능한 고정 크기 컬렉션 (0부터 시작)입니다.|[배열](arrays.md)<br /><br />[Array 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html)<br /><br />[Array2D 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html)<br /><br />[Array3D 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array3dmodule.html)|
|[차이가](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seq-1.html)|단일 형식의 논리적 일련의 요소입니다. 시퀀스는 데이터의 순서가 지정 된 컬렉션이 크고 모든 요소를 사용할 필요가 없는 경우에 특히 유용 합니다. 개별 시퀀스 요소는 필요한 경우에만 계산 되므로 모든 요소가 사용 되지 않는 경우 시퀀스가 목록 보다 더 잘 수행 될 수 있습니다. 시퀀스는 `seq<'T>` 의 별칭인 형식으로 표현 됩니다 `IEnumerable<T>` . 따라서을 구현 하는 모든 .NET Framework 형식을 `System.Collections.Generic.IEnumerable<'T>` 시퀀스로 사용할 수 있습니다.|[시퀀스](sequences.md)<br /><br />[Seq 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html)|
|[Map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-fsharpmap-2.html)|요소에 대 한 변경할 수 없는 사전입니다. 요소는 키로 액세스 됩니다.|[지도 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-mapmodule.html)|
|[설정](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-fsharpset-1.html)|이진 트리를 기반으로 하는 변경할 수 없는 집합입니다. 비교는 `System.IComparable` 키 값에 대 한 인터페이스 구현을 사용 하는 F # 구조적 비교 함수입니다.|[모듈 설정](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-setmodule.html)|

### <a name="table-of-functions"></a>함수 테이블

이 섹션에서는 F # 컬렉션 형식에서 사용할 수 있는 함수를 비교 합니다. 함수의 계산 복잡성이 제공 됩니다. 여기서 N은 첫 번째 컬렉션의 크기이 고 M은 두 번째 컬렉션의 크기 (있는 경우)입니다. 대시 (-)는이 함수를 컬렉션에서 사용할 수 없음을 나타냅니다. 시퀀스는 지연 계산 되기 때문에와 같은 함수는 `Seq.distinct` 를 즉시 반환 하기 때문에 O (1)가 될 수 있습니다. 하지만이 함수는 열거 될 때 시퀀스의 성능에 여전히 영향을 줍니다.

|기능|배열|목록|순서|지도|설정|Description|
|--------|-----|----|--------|---|---|-----------|
|추가|O (N)|O (N)|O (N)|-|-|첫 번째 컬렉션의 요소와 두 번째 컬렉션의 요소를 포함 하는 새 컬렉션을 반환 합니다.|
|add|-|-|-|O (log (N))|O (log (N))|요소가 추가 된 새 컬렉션을 반환 합니다.|
|average|O (N)|O (N)|O (N)|-|-|컬렉션에 있는 요소의 평균을 반환 합니다.|
|Array.averageby|O (N)|O (N)|O (N)|-|-|각 요소에 적용 된 제공 된 함수의 결과에 대 한 평균을 반환 합니다.|
|array.blit|O (N)|-|-|-|-|배열의 섹션을 복사 합니다.|
|캐시|-|-|O (N)|-|-|시퀀스의 요소를 계산 하 고 저장 합니다.|
|캐스트|-|-|O (N)|-|-|요소를 지정 된 형식으로 변환 합니다.|
|choose|O (N)|O (N)|O (N)|-|-|지정 된 함수를 `f` 목록의 각 요소에 적용 `x` 합니다. 함수가 반환 하는 각 요소에 대 한 결과를 포함 하는 목록을 반환 `Some(f(x))` 합니다.|
|collect|O (N)|O (N)|O (N)|-|-|지정 된 함수를 컬렉션의 각 요소에 적용 하 고 모든 결과를 연결 하 고 결합 된 목록을 반환 합니다.|
|Seq.comparewith|-|-|O (N)|-|-|지정 된 비교 함수를 사용 하 여 두 시퀀스를 요소 별로 비교 합니다.|
|concat|O (N)|O (N)|O (N)|-|-|지정 된 열거형 열거를 연결 된 단일 열거형으로 결합 합니다.|
|contains|-|-|-|-|O (log (N))|집합에 지정 된 요소가 포함 된 경우 true를 반환 합니다.|
|containsKey|-|-|-|O (log (N))|-|요소가 맵의 도메인에 있는지 여부를 테스트 합니다.|
|개수|-|-|-|-|O (N)|집합에 있는 요소 수를 반환합니다.|
|Seq.countby|-|-|O (N)|-|-|시퀀스의 각 요소에 키 생성 함수를 적용 하 고 원래 시퀀스에서 고유 키와 해당 항목 수를 생성 하는 시퀀스를 반환 합니다.|
|copy|O (N)|-|O (N)|-|-|컬렉션을 복사합니다.|
|create|O (N)|-|-|-|-|지정 된 값을 처음부터 모두 나타내는 전체 요소의 배열을 만듭니다.|
|delay|-|-|O(1)|-|-|시퀀스의 지정 된 지연 사양을 기반으로 하는 시퀀스를 반환 합니다.|
|차이점|-|-|-|-|O (M \* 로그 (N))|첫 번째 집합에서 두 번째 집합의 요소가 제거 된 새 집합을 반환 합니다.|
|distinct|||O(1)\*|||항목에 대 한 제네릭 해시 및 같음 비교에 따라 중복 항목을 포함 하지 않는 시퀀스를 반환 합니다. 요소가 시퀀스에서 여러 번 발생 하는 경우 나중에 발생 하는 것은 무시 됩니다.|
|Seq.distinctby|||O(1)\*|||지정 된 키 생성 함수에서 반환 하는 키에 대 한 제네릭 해시 및 같음 비교에 따라 중복 항목을 포함 하지 않는 시퀀스를 반환 합니다. 요소가 시퀀스에서 여러 번 발생 하는 경우 나중에 발생 하는 것은 무시 됩니다.|
|비어 있음|O(1)|O(1)|O(1)|O(1)|O(1)|빈 컬렉션을 만듭니다.|
|exists|O (N)|O (N)|O (N)|O (log (N))|O (log (N))|시퀀스의 요소가 지정 된 조건자를 충족 하는지 여부를 테스트 합니다.|
|array.exists2|O (min (N, M))|-|O (min (N, M))|||입력 시퀀스의 해당 요소 쌍이 지정 된 조건자를 충족 하는지 여부를 테스트 합니다.|
|fill|O (N)|||||배열의 요소 범위를 지정 된 값으로 설정 합니다.|
|filter|O (N)|O (N)|O (N)|O (N)|O (N)|지정 된 조건자가 반환 하는 컬렉션의 요소만 포함 하는 새 컬렉션을 반환 `true` 합니다.|
|찾기|O (N)|O (N)|O (N)|O (log (N))|-|지정 된 함수가 반환 하는 첫 번째 요소를 반환 `true` 합니다. `System.Collections.Generic.KeyNotFoundException`이러한 요소가 없으면를 반환 합니다.|
|findIndex|O (N)|O (N)|O (N)|-|-|배열에서 지정 된 조건자를 만족 하는 첫 번째 요소의 인덱스를 반환 합니다. `System.Collections.Generic.KeyNotFoundException`조건자를 충족 하는 요소가 없으면 발생 합니다.|
|Map.findkey|-|-|-|O (log (N))|-|컬렉션의 각 매핑에서 함수를 계산 하 고 함수가 반환 하는 첫 번째 매핑에 대 한 키를 반환 `true` 합니다. 이러한 요소가 없는 경우이 함수는를 발생 시킵니다 `System.Collections.Generic.KeyNotFoundException` .|
|으|O (N)|O (N)|O (N)|O (N)|O (N)|컬렉션의 각 요소에 함수를 적용 하 여 계산을 통해 누적기 인수를 스레딩 합니다. 입력 함수가 f이 고 요소가 i0 경우 에서이 함수는 f (...)를 계산 합니다. (f s i0) ...) 진행.|
|list.fold2|O (N)|O (N)|-|-|-|두 컬렉션의 해당 요소에 함수를 적용 하 여 계산을 통해 누적기 인수를 스레딩 합니다. 컬렉션의 크기는 동일 해야 합니다. 입력 함수가 f이 고 요소가 i0 경우 및 j0 jN,이 함수는 f (... (f s i0 j0) ...) jN의|
|foldBack|O (N)|O (N)|-|O (N)|O (N)|컬렉션의 각 요소에 함수를 적용 하 여 계산을 통해 누적기 인수를 스레딩 합니다. 입력 함수가 f이 고 요소가 i0 경우 에서이 함수는 f i0 (...)를 계산 합니다. (s에서 f)).|
|Array.foldback2|O (N)|O (N)|-|-|-|두 컬렉션의 해당 요소에 함수를 적용 하 여 계산을 통해 누적기 인수를 스레딩 합니다. 컬렉션의 크기는 동일 해야 합니다. 입력 함수가 f이 고 요소가 i0 경우 및 j0 jN,이 함수는 f i0 j0 (...)를 계산 합니다. (jN s의 f)).|
|forall|O (N)|O (N)|O (N)|O (N)|O (N)|컬렉션의 모든 요소가 지정 된 조건자를 충족 하는지 여부를 테스트 합니다.|
|list.forall2|O (N)|O (N)|O (N)|-|-|컬렉션의 모든 해당 요소가 지정 된 조건자를 충족 하는지 여부를 테스트 합니다.|
|get/n|O(1)|O (N)|O (N)|-|-|인덱스를 지정 하 여 컬렉션에서 요소를 반환 합니다.|
|head|-|O(1)|O(1)|-|-|컬렉션의 첫 번째 요소를 반환 합니다.|
|init|O (N)|O (N)|O(1)|-|-|요소를 계산 하기 위해 차원과 생성기 함수를 지정 하 여 컬렉션을 만듭니다.|
|Seq.initinfinite|-|-|O(1)|-|-|반복 될 때 지정 된 함수를 호출 하 여 연속 된 요소를 반환 하는 시퀀스를 생성 합니다.|
|intersect|-|-|-|-|O (log (N) \* log (M))|두 집합의 교집합을 계산 합니다.|
|Set.intersectmany|-|-|-|-|O (N1 \* N2 ...)|집합 시퀀스의 교집합을 계산 합니다. 시퀀스가 비어 있지 않아야 합니다.|
|isEmpty|O(1)|O(1)|O(1)|O(1)|-|`true`컬렉션이 비어 있으면를 반환 합니다.|
|Set.ispropersubset|-|-|-|-|O (M \* 로그 (N))|`true`첫 번째 집합의 모든 요소가 두 번째 집합에 있고 두 번째 집합의 요소 중 하나 이상이 첫 번째 집합에 없는 경우를 반환 합니다.|
|Set.ispropersuperset|-|-|-|-|O (M \* 로그 (N))|`true`두 번째 집합의 모든 요소가 첫 번째 집합에 있고 첫 번째 집합의 요소 중 하나 이상이 두 번째 집합에 없는 경우를 반환 합니다.|
|Set.issubset|-|-|-|-|O (M \* 로그 (N))|`true`첫 번째 집합의 모든 요소가 두 번째 집합에 있으면를 반환 합니다.|
|Set.issuperset|-|-|-|-|O (M \* 로그 (N))|`true`두 번째 집합의 모든 요소가 첫 번째 집합에 있으면를 반환 합니다.|
|iter|O (N)|O (N)|O (N)|O (N)|O (N)|지정 된 함수를 컬렉션의 각 요소에 적용 합니다.|
|list.iteri|O (N)|O (N)|O (N)|-|-|지정 된 함수를 컬렉션의 각 요소에 적용 합니다. 함수에 전달 되는 정수는 요소의 인덱스를 나타냅니다.|
|list.iteri2|O (N)|O (N)|-|-|-|두 배열의 일치 하는 인덱스에서 가져온 요소 쌍에 지정 된 함수를 적용 합니다. 함수에 전달 되는 정수는 요소의 인덱스를 나타냅니다. 두 배열의 길이는 같아야 합니다.|
|list.iter2|O (N)|O (N)|O (N)|-|-|두 배열의 일치 하는 인덱스에서 가져온 요소 쌍에 지정 된 함수를 적용 합니다. 두 배열의 길이는 같아야 합니다.|
|last|O(1)|O (N)|O (N)|-|-|해당 컬렉션의 마지막 항목을 반환 합니다.|
|length|O(1)|O (N)|O (N)|-|-|컬렉션의 요소 수를 반환 합니다.|
|map|O (N)|O (N)|O(1)|-|-|지정 된 함수를 배열의 각 요소에 적용 한 결과인 요소가 포함 된 컬렉션을 빌드합니다.|
|array.map2|O (N)|O (N)|O(1)|-|-|지정 된 함수를 두 컬렉션의 해당 요소에 한 쌍으로 적용 한 결과인 컬렉션을 빌드합니다. 두 입력 배열의 길이는 같아야 합니다.|
|list.map3|-|O (N)|-|-|-|지정 된 함수를 세 컬렉션의 해당 요소에 동시에 적용 한 결과로 얻어지는 요소가 포함 된 컬렉션을 빌드합니다.|
|만들었습니다|O (N)|O (N)|O (N)|-|-|지정 된 함수를 배열의 각 요소에 적용 한 결과인 요소가 포함 된 배열을 빌드합니다. 함수에 전달 된 정수 인덱스는 변환할 요소의 인덱스를 나타냅니다.|
|array.mapi2|O (N)|O (N)|-|-|-|요소의 인덱스를 전달 하 여 두 컬렉션의 해당 요소에 지정 된 함수를 쌍으로 적용 한 결과인 요소가 포함 된 컬렉션을 빌드합니다. 두 입력 배열의 길이는 같아야 합니다.|
|max|O (N)|O (N)|O (N)|-|-|[Max](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#max) 연산자를 사용 하 여 비교 하 여 컬렉션에서 가장 큰 요소를 반환 합니다.|
|maxBy|O (N)|O (N)|O (N)|-|-|함수 결과에서 [max](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#max) 를 사용 하는 것과 비교 하 여 컬렉션에서 가장 큰 요소를 반환 합니다.|
|Set.maxelement|-|-|-|-|O (log (N))|집합에 사용 된 순서에 따라 집합의 가장 큰 요소를 반환 합니다.|
|분|O (N)|O (N)|O (N)|-|-|[Min](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#min) 연산자를 사용 하 여 비교 하 여 컬렉션의 최소 요소를 반환 합니다.|
|minBy|O (N)|O (N)|O (N)|-|-|함수 결과에서 [min](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#min) 연산자를 사용 하는 것과 비교 하 여 컬렉션의 최소 요소를 반환 합니다.|
|Set.minelement|-|-|-|-|O (log (N))|집합에 사용 된 순서에 따라 집합의 최하위 요소를 반환 합니다.|
|List.ofarray|-|O (N)|O(1)|O (N)|O (N)|지정 된 배열과 동일한 요소를 포함 하는 컬렉션을 만듭니다.|
|Array.oflist|O (N)|-|O(1)|O (N)|O (N)|지정 된 목록과 동일한 요소를 포함 하는 컬렉션을 만듭니다.|
|List.ofseq|O (N)|O (N)|-|O (N)|O (N)|지정 된 시퀀스와 동일한 요소를 포함 하는 컬렉션을 만듭니다.|
|쌍|-|-|O (N)|-|-|두 번째 요소의 선행 작업 으로만 반환 되는 첫 번째 요소를 제외 하 고 입력 시퀀스에 있는 각 요소의 시퀀스와 해당 선행 작업을 반환 합니다.|
|partition|O (N)|O (N)|-|O (N)|O (N)|컬렉션을 두 개의 컬렉션으로 분할 합니다. 첫 번째 컬렉션에는 지정 된 조건자가 반환 하는 요소가 포함 되 `true` 고, 두 번째 컬렉션에는 지정 된 조건자가 반환 하는 요소가 포함 `false` 됩니다.|
|permute|O (N)|O (N)|-|-|-|지정 된 순열에 따라 요소가 순열 모든 요소가 포함 된 배열을 반환 합니다.|
|울|O (N)|O (N)|O (N)|O (log (N))|-|지정 된 함수를 연속 요소에 적용 하 여 함수가 Some을 반환 하는 첫 번째 결과를 반환 합니다. 함수가 Some을 반환 하지 않으면 `System.Collections.Generic.KeyNotFoundException` 이 발생 합니다.|
|readonly|-|-|O (N)|-|-|지정 된 시퀀스 개체에 위임 하는 시퀀스 개체를 만듭니다. 이 작업을 수행 하면 형식 캐스팅이 원래 시퀀스를 다시 검색 하 고 변경할 수 없습니다. 예를 들어 배열이 지정 된 경우 반환 된 시퀀스는 배열의 요소를 반환 하지만 반환 된 시퀀스 개체를 배열로 캐스트할 수는 없습니다.|
|reduce|O (N)|O (N)|O (N)|-|-|컬렉션의 각 요소에 함수를 적용 하 여 계산을 통해 누적기 인수를 스레딩 합니다. 이 함수는 처음 두 요소에 함수를 적용 하 고이 결과를 세 번째 요소와 함께 함수에 전달 하는 방식으로 시작 됩니다. 함수는 최종 결과를 반환 합니다.|
|Array.reduceback|O (N)|O (N)|-|-|-|컬렉션의 각 요소에 함수를 적용 하 여 계산을 통해 누적기 인수를 스레딩 합니다. 입력 함수가 f이 고 요소가 i0 경우 에서이 함수는 f i0 (...)를 계산 합니다. (의 f-1)).|
|remove|-|-|-|O (log (N))|O (log (N))|맵의 도메인에서 요소를 제거 합니다. 요소가 없으면 예외가 발생 하지 않습니다.|
|유사|-|O (N)|-|-|-|모든 요소를 지정 된 값으로 설정 하 여 지정 된 길이의 목록을 만듭니다.|
|역|O (N)|O (N)|-|-|-|요소가 역순으로 포함 된 새 목록을 반환 합니다.|
|검색|O (N)|O (N)|O (N)|-|-|컬렉션의 각 요소에 함수를 적용 하 여 계산을 통해 누적기 인수를 스레딩 합니다. 이 작업은 두 번째 인수 및 목록의 첫 번째 요소에 함수를 적용 합니다. 그런 다음 작업에서이 결과를 두 번째 요소와 함께 함수에 전달 합니다. 마지막으로 작업은 중간 결과 및 최종 결과의 목록을 반환 합니다.|
|Array.scanback|O (N)|O (N)|-|-|-|FoldBack 작업과 유사 하지만 중간 결과와 최종 결과를 모두 반환 합니다.|
|singleton|-|-|O(1)|-|O(1)|항목을 하나만 생성 하는 시퀀스를 반환 합니다.|
|set|O(1)|-|-|-|-|배열의 요소를 지정 된 값으로 설정 합니다.|
|skip|-|-|O (N)|-|-|기본 시퀀스의 N 개 요소를 건너뛴 다음 시퀀스의 나머지 요소를 생성 하는 시퀀스를 반환 합니다.|
|skipWhile|-|-|O (N)|-|-|반복 될 때 지정 된 조건자가 반환 하는 동안 기본 시퀀스의 요소를 건너뛴 `true` 다음 시퀀스의 나머지 요소를 생성 하는 시퀀스를 반환 합니다.|
|sort|O (N \* ) 평균<br /><br />O (N ^ 2) 최악의 경우|O (N \* 로그 (n))|O (N \* 로그 (n))|-|-|요소 값으로 컬렉션을 정렬 합니다. 요소는 [비교](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#compare)를 사용 하 여 비교 됩니다.|
|sortBy|O (N \* ) 평균<br /><br />O (N ^ 2) 최악의 경우|O (N \* 로그 (n))|O (N \* 로그 (n))|-|-|지정 된 프로젝션이 제공 하는 키를 사용 하 여 지정 된 목록을 정렬 합니다. [비교](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#compare)를 사용 하 여 키를 비교 합니다.|
|Array.sortinplace|O (N \* ) 평균<br /><br />O (N ^ 2) 최악의 경우|-|-|-|-|지정 된 비교 함수를 사용 하 여 배열 요소를 변경 하 여 정렬 합니다. 요소는 [비교](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#compare)를 사용 하 여 비교 됩니다.|
|Array.sortinplaceby|O (N \* ) 평균<br /><br />O (N ^ 2) 최악의 경우|-|-|-|-|현재 위치의 요소를 변경 하 고 해당 키에 대해 지정 된 프로젝션을 사용 하 여 배열의 요소를 정렬 합니다. 요소는 [비교](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#compare)를 사용 하 여 비교 됩니다.|
|Array.sortinplacewith|O (N \* ) 평균<br /><br />O (N ^ 2) 최악의 경우|-|-|-|-|지정 된 비교 함수를 순서 대로 사용 하 여 배열의 요소를 정렬 합니다.|
|Array.sortwith|O (N \* ) 평균<br /><br />O (N ^ 2) 최악의 경우|O (N \* 로그 (n))|-|-|-|지정 된 비교 함수를 순서 대로 사용 하 고 새 컬렉션을 반환 하 여 컬렉션의 요소를 정렬 합니다.|
|sub|O (N)|-|-|-|-|시작 인덱스 및 길이로 지정 된 지정 된 하위 범위를 포함 하는 배열을 빌드합니다.|
|sum|O (N)|O (N)|O (N)|-|-|컬렉션에 있는 요소의 합을 반환 합니다.|
|Array.sumby|O (N)|O (N)|O (N)|-|-|컬렉션의 각 요소에 함수를 적용 하 여 생성 되는 결과의 합을 반환 합니다.|
|비상|-|O(1)|-|-|-|첫 번째 요소 없이 목록을 반환 합니다.|
|take|-|-|O (N)|-|-|시퀀스의 요소를 지정 된 개수까지 반환 합니다.|
|takeWhile|-|-|O(1)|-|-|반복 될 때 지정 된 조건자가 반환 되는 동안 기본 시퀀스의 요소를 생성 하 고 `true` 더 이상 요소를 반환 하지 않는 시퀀스를 반환 합니다.|
|toArray|-|O (N)|O (N)|O (N)|O (N)|지정 된 컬렉션에서 배열을 만듭니다.|
|System.linq.enumerable.tolist|O (N)|-|O (N)|O (N)|O (N)|지정 된 컬렉션에서 목록을 만듭니다.|
|Array.toseq|O(1)|O(1)|-|O(1)|O(1)|지정 된 컬렉션에서 시퀀스를 만듭니다.|
|truncate|-|-|O(1)|-|-|열거 될 때 요소를 N 개 이하로 반환 하는 시퀀스를 반환 합니다.|
|List.tryfind|O (N)|O (N)|O (N)|O (log (N))|-|지정 된 조건자를 만족 하는 요소를 검색 합니다.|
|List.tryfindindex|O (N)|O (N)|O (N)|-|-|지정 된 조건자를 충족 하는 첫 번째 요소를 검색 하 고 일치 하는 요소의 인덱스를 반환 하거나, `None` 이러한 요소가 없는 경우을 검색 합니다.|
|Map.tryfindkey|-|-|-|O (log (N))|-|컬렉션에서 지정 된 조건자를 만족 하는 첫 번째 매핑의 키를 반환 하거나, 이러한 요소가 없으면를 반환 합니다 `None` .|
|Array.trypick|O (N)|O (N)|O (N)|O (log (N))|-|지정 된 함수를 연속 요소에 적용 하 여 함수가 `Some` 일부 값에 대해 반환 하는 첫 번째 결과를 반환 합니다. 이러한 요소가 없는 경우 작업은를 반환 `None` 합니다.|
|펼침|-|-|O (N)|-|-|지정 된 계산이 생성 하는 요소가 포함 된 시퀀스를 반환 합니다.|
|union|-|-|-|-|O (M \* 로그 (N))|두 집합의 합집합을 계산 합니다.|
|Set.unionmany|-|-|-|-|O (N1 \* N2 ...)|집합 시퀀스의 합집합을 계산 합니다.|
|unzip|O (N)|O (N)|O (N)|-|-|쌍의 목록을 두 개의 목록으로 분할 합니다.|
|list.unzip3|O (N)|O (N)|O (N)|-|-|삼중 쌍 목록을 세 개의 목록으로 분할 합니다.|
|창을|-|-|O (N)|-|-|입력 시퀀스에서 가져온 요소를 포함 하는 슬라이딩 윈도우를 생성 하는 시퀀스를 반환 합니다. 각 창은 새 배열로 반환 됩니다.|
|zip|O (N)|O (N)|O (N)|-|-|두 컬렉션을 쌍의 목록으로 결합 합니다. 두 목록의 길이는 같아야 합니다.|
|list.zip3|O (N)|O (N)|O (N)|-|-|세 개의 컬렉션을 삼중 쌍 목록으로 결합 합니다. 목록의 길이는 같아야 합니다.|

## <a name="see-also"></a>추가 정보

- [F# 형식](fsharp-types.md)
- [F# 언어 참조](index.md)
