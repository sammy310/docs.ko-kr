---
title: 일급 함수
description: 첫 번째 클래스 함수 및의 함수형 프로그래밍에 대 한 중요 한 됩니다 하는 방법에 대해 알아봅니다 F#입니다.
ms.date: 10/29/2018
ms.openlocfilehash: 505ad686614b53d779cb617fc04ac74c2a88b31b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772764"
---
# <a name="first-class-functions"></a>일급 함수

함수형 프로그래밍 언어의 대표적인 특징은 함수 최상위 상태를 상승 합니다. 모든 다른 기본 제공 형식의 값을 사용 하 여 수행할를 비교할 수 있는 수준의 노력을 사용 하 여 이렇게 할 수는 함수를 사용 하 여 할 수 있어야 합니다.

일반적인 측정값 최고 수준의 상태는 다음과 같습니다.

- 식별자에 함수를 바인딩할 수 있습니다. 즉, 있습니다 수 이름을?

- 저장할 수 있습니다 하 데이터 구조체에는 함수 같은 목록의?

- 함수 호출에서 인수로 서 함수를 전달할 수 있습니다?

- 함수 호출에서 함수를 반환할 수 있습니다.

마지막 두 측정값 정의 일명 *고차 operations* 또는 *고차 함수*합니다. 고차 함수는 함수를 인수로 수락 하 고 함수 호출의 값으로 함수를 반환 합니다. 이러한 작업에는 매핑 함수 및 함수 조합으로 함수형 프로그래밍의 핵심적 지원 합니다.

## <a name="give-the-value-a-name"></a>값 이름을

함수는 첫 번째 클래스 값 이면 해야 이름을 할 것 처럼 정수, 문자열 및 다른 기본 제공 형식 이름을 지정할 수 있습니다. 이 식별자 값에 바인딩 함수형 프로그래밍 문서에서 참조 됩니다. F#사용 하 여 [ `let` 바인딩을](../language-reference/functions/let-bindings.md) 이름 값에 바인딩할: `let <identifier> = <value>`합니다. 다음 코드는 두 가지 예제를 보여줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

쉽게 함수를 이름을 지정할 수 있습니다. 다음 예제에서는 명명 된 함수를 정의 `squareIt` 식별자를 바인딩하여 `squareIt` 에 [람다 식](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`. 함수 `squareIt` 하나의 매개 변수가 `n`, 해당 매개 변수의 사각형을 반환 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

F#다음 기능을 제공 더 간결한 구문을 입력으로 동일한 결과 얻을 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

주로 나오는 예제에서는 첫 번째 스타일을 사용 하 여 `let <function-name> = <lambda-expression>`, 함수 선언 및 다른 유형의 값 선언 간의 유사성을 강조 하기. 그러나 모든 명명 된 함수 간결한 구문을 사용 하 여 작성할 수도 있습니다. 일부 예제에서는 두 가지 방식으로 작성 됩니다.

## <a name="store-the-value-in-a-data-structure"></a>데이터 구조에서 값을 저장 합니다.

데이터 구조에는 첫 번째 클래스 값을 저장할 수 있습니다. 다음 코드는 튜플 목록에 값을 저장 하는 예를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

튜플에 저장 된 함수 이름을 않습니다 함수로 계산 실제로 있는지를 확인 하려면 다음 예제에서는 합니다 `fst` 하 고 `snd` 튜플 로부터 첫 번째 및 두 번째 요소를 추출 하는 연산자 `funAndArgTuple`합니다. 튜플의 첫 번째 요소는 `squareIt` 이 고 두 번째 요소는 `num`합니다. 식별자 `num` 정수로 10에 대 한 유효한 인수 앞의 예제에서 바인딩되는 `squareIt` 함수입니다. 두 번째 식 튜플의 두 번째 요소 튜플의 첫 번째 요소에 적용: `squareIt num`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

마찬가지로, 식별자로 `num` 정수 10 수 식별자 수 있으므로 서로 교대로 사용 `squareIt` 람다 식 및 `fun n -> n * n`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]

## <a name="pass-the-value-as-an-argument"></a>값을 인수로 전달

값에 최상위 상태 언어의 경우 함수에 인수로 전달할 수 있습니다. 예를 들어, 정수 및 문자열 인수로 전달에 공통적으로 적용 됩니다. 다음 코드에서는 정수 및 문자열에 인수로 전달 된 F#입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

함수는 최상위 상태에 있는 경우에 동일한 방식으로 인수로 전달할 수 해야 합니다. 고차 함수의 첫 번째 특징에 유의 합니다.

다음 예제에서는 작동 `applyIt` 두 개의 매개 변수가 `op` 고 `arg`입니다. 에 대 한 하나의 매개 변수가 있는 함수에 전송 하는 경우 `op` 및 함수에 대 한 적절 한 인수로 `arg`, 함수를 적용 한 결과 반환 합니다. `op` 하려면 `arg`합니다. 다음 예제에서는 정수 인수 및 함수 인수는 동일한 방법으로 전송 됩니다 해당 이름을 사용 하 여.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

다른 함수에 인수로 맵 또는 필터 작업 같은 함수형 프로그래밍 언어에서 일반적인 추상화의 기반이 되는 함수를 보낼 수 있습니다. 예를 들어 맵 작업에는 목록을 단계별로 각 요소에 작업을 수행 하 고 다음 결과의 목록을 반환 하는 함수에서 공유 하는 계산을 캡처하는 고차 함수입니다. 정수 목록의 각 요소를 증가 시킬 각 요소인 정사각형 또는 문자열 목록의 각 요소를 대문자로 변경 좋습니다. 계산의 오류가 발생 하기 쉬운 부분 재귀 프로세스 목록을 통해 해당 단계 이며 반환할 결과의 목록을 작성 합니다. 일부는 매핑 함수에 캡처됩니다. 특정 응용 프로그램 작성 해야 모든는 개별적으로 목록의 각 요소에 적용 하려는 하는 함수 (추가, 제곱 대/소문자 바꾸기). 함수를 보내 인수로 하도록 매핑 함수 처럼 `squareIt` 보낼 `applyIt` 이전 예제에서 합니다.

F#같은 대부분의 컬렉션 형식에 대 한 지도 메서드를 제공 [나열](../language-reference/lists.md)를 [배열을](../language-reference/arrays.md), 및 [시퀀스](../language-reference/sequences.md)합니다. 다음 예제에서는 목록을 사용 합니다. 구문은 `List.map <the function> <the list>`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

자세한 내용은 [나열](../language-reference/lists.md)합니다.

## <a name="return-the-value-from-a-function-call"></a>함수 호출에서 값을 반환 합니다.

마지막으로, 함수 언어에서 최고 수준의 상태 있으면 해야 함수 호출의 값으로 반환할 수 정수 및 문자열과 같은 다른 형식의 경우 반환 되는 것입니다.

다음 함수 호출은 정수를 반환 하 고 표시 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

다음 함수 호출은 문자열을 반환 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

부울 값을 반환 하는 다음 함수 호출을 인라인을 선언 합니다. 표시 되는 값은 `True`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

함수 호출의 값으로 함수를 반환 하는 기능은 고차 함수의 두 번째 특징입니다. 다음 예에서 `checkFor` 인수 하나를 사용 하는 함수 정의 됩니다. `item`, 해당 값으로 새 함수를 반환 합니다. 반환 된 함수는 목록을 인수로 `lst`, 검색 `item` 에서 `lst`합니다. 하는 경우 `item` 가 있으면 반환 `true`합니다. 하는 경우 `item` 가 없으면 반환 `false`합니다. 이전 섹션에서와 같이 다음 코드에서는 제공 된 목록 함수 [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8)를 목록을 검색 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

다음 코드에서는 `checkFor` 목록에서 하나의 인수, 목록 및 7에 대 한 검색을 사용 하는 새 함수를 만듭니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

다음 예제에서는 최상위 상태에서 함수의 F# 함수를 선언 하 `compose`, 컴퍼지션 두 함수 인수를 반환 하는 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]

> [!NOTE]
> 더 짧게 버전인 다음 섹션인 "Curried 함수입니다."을 참조 하세요.

다음 코드는 두 함수에 대 한 인수로 보냅니다 `compose`모두 동일한 형식의 단일 인수를 사용 하는 중입니다. 반환 값은 두 개의 함수 인수의 혼합 된 새 함수입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]

> [!NOTE]
> F#두 연산자를 제공 `<<` 및 `>>`를 구성 하는 함수입니다. 예를 들어 `let squareAndDouble2 = doubleIt << squareIt` 같습니다 `let squareAndDouble = compose doubleIt squareIt` 이전 예제에서 합니다.

함수 호출의 값으로 함수를 반환 하는 다음 예제에서는 간단한 맞추기 게임을 만듭니다. 게임을 만들려면 호출 `makeGame` 값을 사용 하 여 다른 사람이 추측 하기 원하는 전송에 대 한 `target`합니다. 함수에서 반환 값 `makeGame` 는 하나의 인수 (추측) 및 추측이 올바른지 여부를 보고 하는 함수입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

다음 코드 호출 `makeGame`에 값을 전송 `7` 에 대 한 `target`합니다. 식별자 `playGame` 반환 된 람다 식에 바인딩됩니다. 따라서 `playGame` 에 대 한 값을 하나의 인수로 사용 하는 함수는 `guess`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]

## <a name="curried-functions"></a>커리 된 함수

암시적의 활용 하 여 더 간결 하 게 작성할 수 다양 한 이전 섹션에서 예제 *커리* 에서 F# 함수 선언이 있습니다. (Currying) 각각에 단일 매개 변수가 포함 된 함수의 계열로 둘 이상의 매개 변수가 있는 함수를 변환 하는 프로세스입니다. F#를 둘 이상의 매개 변수가 있는 함수는 본질적으로 변환 합니다. 예를 들어 `compose` 이전 섹션에서 작성할 수 있습니다 다음 간결한 스타일에서 세 개의 매개 변수를 사용 하 여 표시 된 것과 같이 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

그러나 결과 함수에 표시 된 대로 다른 함수의 매개 변수 하나를 반환 하는 하나의 매개 변수는 함수를 반환 하는 하나의 매개 변수의 `compose4curried`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

여러 가지 방법으로이 함수에 액세스할 수 있습니다. 다음 예에서는 각각 반환 하 고 18를 표시 합니다. 바꿀 수 있습니다 `compose4` 사용 하 여 `compose4curried` 의 예제입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

이전과 여전히 작동 하는지 확인 하려면 원래 테스트 사례를 다시 시도 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]

> [!NOTE]
> 튜플에 매개 변수를 포함 하 여 (currying)을 제한할 수 있습니다. 자세한 내용은 "매개 변수 패턴"를 참조 하세요 [매개 변수 및 인수](../language-reference/parameters-and-arguments.md)합니다.

다음 예제에서는 암시적 (currying)의 짧은 버전 쓸 `makeGame`합니다. 하는 방법의 세부 정보 `makeGame` 생성 및 반환 된 `game` 함수는이 형식으로 명시적 덜 있지만 결과 동일 원래 테스트 사례를 사용 하 여 확인할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

(Currying) 하는 방법에 대 한 자세한 내용은 "응용 프로그램의 인수 부분"를 참조 하세요 [함수](../language-reference/functions/index.md)합니다.

## <a name="identifier-and-function-definition-are-interchangeable"></a>식별자 및 함수는 서로 바꿔 사용할 수

변수 이름 `num` 이전 예제에서는 정수, 10으로 계산 되 고 것은 놀라운 된 `num` 은 유효한 10도 유효 합니다. 함수 식별자 및 해당 값의 마찬가지입니다: 함수 이름을 사용할 수 있습니다 원격가 바인딩되는 람다 식을 사용할 수 있습니다.

다음 예제에서는 정의 `Boolean` 함수 호출 `isNegative`, 다음 함수의 이름과 함수 정의 같은 의미로 사용 됩니다. 다음 세 가지 예제 모두 반환 하 여 표시 `False`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

한 단계 추가, 값을 대체 하는 `applyIt` 에 대 한에 바인딩되어 `applyIt`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a>함수는 f #의 첫 번째 클래스 값\#

이전 섹션의 예제에서 함수를 보여 줍니다. F# 에서 첫 번째 클래스 값에 대 한 조건을 충족 F#:

- 함수 정의에 식별자를 바인딩할 수 있습니다.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- 데이터 구조에 함수를 저장할 수 있습니다.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- 함수를 인수로 전달할 수 있습니다.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- 함수 호출의 값으로 함수를 반환할 수 있습니다.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

에 대 한 자세한 내용은 F#를 참조 합니다 [ F# 언어 참조](../language-reference/index.md)합니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 코드는이 항목의 모든 예제를 포함합니다.

### <a name="code"></a>코드

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]

## <a name="see-also"></a>참고자료

- [목록](../language-reference/lists.md)
- [튜플](../language-reference/tuples.md)
- [함수](../language-reference/functions/index.md)
- [`let` Bindings](../language-reference/functions/let-bindings.md)
- [람다 식: `fun` 키워드](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
