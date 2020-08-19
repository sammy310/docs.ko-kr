---
title: 옵션
description: '명명 된 값 또는 변수에 대 한 실제 값이 없을 수 있는 경우 F # 옵션 유형을 사용 하는 방법에 대해 알아봅니다.'
ms.date: 08/13/2020
ms.openlocfilehash: 0618590c10f6ecac51a23483ca0ab6cd66f2df4f
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557570"
---
# <a name="options"></a>옵션

F #의 옵션 유형은 명명 된 값 또는 변수에 대 한 실제 값이 없을 수 있는 경우에 사용 됩니다. 옵션에는 기본 형식이 있으며 해당 형식의 값을 포함 하거나 값이 없을 수 있습니다.

## <a name="remarks"></a>설명

다음 코드는 옵션 유형을 생성 하는 함수를 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

여기서 볼 수 있듯이 입력 `a` 이 0 보다 크면 `Some(a)` 이 생성 됩니다.  그렇지 않으면 `None` 이 생성 됩니다.

값은 `None` 옵션에 실제 값이 없을 때 사용 됩니다. 그렇지 않으면 식에서 `Some( ... )` 옵션에 값을 제공 합니다. 및 값 `Some` 은 `None` 다음 함수와 같이 패턴 일치에 유용 합니다 .이 함수는 `exists` 옵션에 `true` 값이 있는 경우를 반환 하 고 그렇지 않으면를 반환 `false` 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>USING 옵션

옵션은 다음 코드와 같이 검색에서 일치 하는 결과를 반환 하지 않는 경우에 일반적으로 사용 됩니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

위의 코드에서는 목록이 재귀적으로 검색 됩니다. 함수는 `tryFindMatch` `pred` 부울 값을 반환 하는 조건자 함수와 검색할 목록을 사용 합니다. 조건자를 만족 하는 요소가 발견 되 면 재귀가 종료 되 고 함수는 값을 식의 옵션으로 반환 합니다 `Some(head)` . 빈 목록이 일치 하면 재귀가 종료 됩니다. 이 시점에서 값을 `head` 찾을 수 없으며 `None` 이 반환 됩니다.

컬렉션에서 존재 하거나 존재 하지 않을 수 있는 값을 검색 하는 많은 F # 라이브러리 함수는 `option` 형식을 반환 합니다. 규칙에 따라 이러한 함수는 접두사로 시작 `try` 합니다 (예:) [`Seq.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFindIndex) .

값을 생성 하려고 할 때 예외가 throw 될 수 있는 경우와 같이 값이 없는 경우에도 옵션이 유용할 수 있습니다. 다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

`openFile`이전 예제의 함수는 `string -> File option` `File` 파일이 성공적으로 열리고 예외가 발생 하는 경우 개체를 반환 하므로 형식이 있습니다 `None` . 상황에 따라 예외를 전파 하도록 허용 하는 것이 아니라 예외를 catch 하는 것이 적절 한 디자인이 아닐 수도 있습니다.

또한 `null` 옵션의 경우 null 또는 null 값을 전달할 수 있습니다 `Some` . 일반적으로이를 방지 하는 것이 일반적 이며 일반적으로 루틴 F # 프로그래밍에 있지만 .NET의 참조 형식 특성 때문에 가능 합니다.

## <a name="option-properties-and-methods"></a>옵션 속성 및 메서드

옵션 형식은 다음 속성 및 메서드를 지원 합니다.

|속성 또는 메서드|Type|Description|
|------------------|----|-----------|
|[없음](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#None)|`'T option`|값을 포함 하는 옵션 값을 만들 수 있도록 하는 정적 속성입니다 `None` .|
|[IsNone](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#IsNone)|`bool`|`true`옵션 값이 이면를 반환 `None` 합니다.|
|[IsSome](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#IsSome)|`bool`|`true`옵션에이 아닌 값이 있으면를 반환 `None` 합니다.|
|[개](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#Some)|`'T option`|값이이 아닌 옵션을 만드는 정적 멤버입니다 `None` .|
|[값](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#Value)|`'T`|내부 값을 반환 하거나, `System.NullReferenceException` 값이 인 경우을 throw 합니다 `None` .|

## <a name="option-module"></a>옵션 모듈

옵션에 대 한 작업을 수행 하는 유용한 함수를 포함 하는 모듈 ( [옵션](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html))이 있습니다. 일부 함수는 속성의 기능을 반복 하지만 함수가 필요한 컨텍스트에서는 유용 합니다. [옵션. isSome](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#isSome) 및 [Option. issome](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#isNone) 은 옵션에 값이 포함 되어 있는지 여부를 테스트 하는 모듈 함수입니다. [Option. get](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#get) 값 (있는 경우)을 가져옵니다. 값이 없으면이 throw `System.ArgumentException` 됩니다.

[옵션. bind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#bind) 함수는 값이 있는 경우 값에 대해 함수를 실행 합니다. 함수는 인수를 하나만 사용 해야 하 고 해당 매개 변수 형식이 옵션 형식 이어야 합니다. 함수의 반환 값은 또 다른 옵션 유형입니다.

옵션 모듈에는 목록, 배열, 시퀀스 및 기타 컬렉션 형식에 사용할 수 있는 함수에 해당 하는 함수도 포함 되어 있습니다. 이러한 함수에는 [`Option.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#map) ,, [`Option.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#iter) [`Option.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#forall) ,,, [`Option.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#exists) [`Option.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#foldBack) [`Option.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#fold) 및 [`Option.count`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#count) 가 포함 됩니다. 이러한 함수를 사용 하면 0 개 또는 한 개의 요소 컬렉션과 같은 옵션을 사용할 수 있습니다. 자세한 내용 및 예제는 [목록](lists.md)에서 컬렉션 함수에 대 한 설명을 참조 하세요.

## <a name="converting-to-other-types"></a>다른 형식으로 변환

옵션은 목록 또는 배열로 변환할 수 있습니다. 옵션을 이러한 데이터 구조 중 하나로 변환 하는 경우 결과 데이터 구조에는 0 또는 1 개의 요소가 있습니다. 옵션을 배열로 변환 하려면를 사용 [`Option.toArray`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#toArray) 합니다. 옵션을 목록으로 변환 하려면를 사용 [`Option.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#toList) 합니다.

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
- [F# 형식](fsharp-types.md)
