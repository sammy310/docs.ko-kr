---
title: 인덱싱된 속성
description: 인덱싱된 속성에 대해 알아봅니다 F#를 정렬 된 데이터에 대 한 배열 유사 액세스를 허용 합니다.
ms.date: 10/17/2018
ms.openlocfilehash: 7fc8f46e029255c6ed985a43b92c8f7c2908c428
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489482"
---
# <a name="indexed-properties"></a>인덱싱된 속성

순서가 지정 된 데이터에 대 한 추상화 하는 클래스를 정의 하는 경우 기본 구현에 노출 하지 않고 해당 데이터에 대 한 인덱싱된 액세스를 제공 하는 데 도움이 경우가 있습니다. 그러려면는 `Item` 멤버입니다.

## <a name="syntax"></a>구문

```fsharp
// Indexed property that can be read and written to
member self-identifier.Item
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property can only be read
member self-identifier.Item
    with get(index-values) =
        get-member-body

// Indexed property that can only be set
member self-identifier.Item
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a>설명

이전 구문 형식의 둘 다 있는 인덱싱된 속성을 정의 하는 방법을 보여 줍니다는 `get` 및 `set` 메서드를가 `get` 메서드만 있거나는 `set` 방법 으로만 할당 합니다. 또한만 get 및 set만 나와 있는 구문에 대 한 표시 된 구문은 모두 결합 하 고 get 및 set를 둘 다 있는 속성을 만들 수 있습니다. 이 두 번째 형식은 get에 다른 액세스 가능성 한정자 및 특성을 배치 하 고 방법을 설정할 수 있습니다.

이름을 사용 하 여 `Item`, 컴파일러는 인덱싱된 기본 속성으로 속성을 처리 합니다. A *인덱싱된 기본 속성* 개체 인스턴스에서 배열 유사 구문을 사용 하 여 액세스할 수 있는 속성입니다. 예를 들어 경우 `o` 구문은이 속성을 정의 하는 형식의 개체인 `o.[index]` 속성에 액세스 하는 데 사용 됩니다.

기본이 아닌 인덱싱된 속성에 액세스 하기 위한 구문은 속성 및 일반 멤버와 마찬가지로 괄호로 인덱스의 이름을 지정 합니다. 예를 들어 경우 속성 `o` 라고 `Ordinal`, 작성 `o.Ordinal(index)` 액세스할 수 있습니다.

사용 하는 폼에 관계 없이 항상 set 메서드 인덱싱된 속성에 대 한 커리 된 폼을 사용 해야 합니다. 커리 된 함수에 대 한 자세한 내용은 [함수](../functions/index.md)합니다.

## <a name="example"></a>예제

다음 코드 예제에서는 정 및 기본 및 get 및 set 메서드는 기본이 아닌 인덱싱된 속성의 사용을 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>출력

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a>여러 인덱스 값을 사용 하 여 인덱싱된 속성

인덱싱된 속성 둘 이상의 인덱스 값을 가질 수 있습니다. 이 경우 값 속성을 사용 하는 경우 쉼표로 구분 됩니다. 이러한 속성의 set 메서드에 두 개의 커리 된 인수는 첫 번째는 키가 포함 된 튜플 및는 두 번째 값을 설정 하는 있어야 합니다.

다음 코드는 여러 인덱스 값을 사용 하 여 인덱싱된 속성의 사용을 보여 줍니다.

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member __.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a>참고자료

- [멤버](index.md)
