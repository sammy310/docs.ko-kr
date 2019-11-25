---
title: 인덱싱된 속성
description: 정렬 된 데이터에 대 F#한 배열 유사 액세스를 허용 하는의 인덱싱된 속성에 대해 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: f6cf3bfa737d2bf458e379594be5884696cee3e1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976606"
---
# <a name="indexed-properties"></a>인덱싱된 속성

순서가 지정 된 데이터를 추상화 하는 클래스를 정의 하는 경우 기본 구현을 노출 하지 않고 해당 데이터에 대 한 인덱싱된 액세스를 제공 하는 것이 유용할 수 있습니다. `Item` 멤버를 사용 하 여 수행 됩니다.

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

## <a name="remarks"></a>주의

이전 구문의 형식은 `get` 및 `set` 메서드를 모두 포함 하거나 `get` 메서드만 포함 하거나 `set` 메서드만 포함 하는 인덱싱된 속성을 정의 하는 방법을 보여 줍니다. Get only에 표시 된 구문과 set only에 대 한 구문을 함께 사용할 수도 있으며 get 및 set이 모두 있는 속성을 생성 합니다. 이 두 번째 형식을 사용 하면 get 및 set 메서드에 다른 액세스 가능성 한정자 및 특성을 추가할 수 있습니다.

컴파일러는 이름 `Item`를 사용 하 여 속성을 인덱싱된 기본 속성으로 처리 합니다. *인덱싱된 기본 속성* 은 개체 인스턴스에서 배열 형식 구문을 사용 하 여 액세스할 수 있는 속성입니다. 예를 들어 `o`이이 속성을 정의 하는 형식의 개체 이면 `o.[index]` 구문을 사용 하 여 속성에 액세스 합니다.

기본이 아닌 인덱싱된 속성에 액세스 하기 위한 구문은 일반 멤버와 마찬가지로 속성의 이름과 인덱스를 괄호로 묶어 제공 하는 것입니다. 예를 들어 `o`의 속성을 `Ordinal`호출 하는 경우 `o.Ordinal(index)`를 작성 하 여 액세스 합니다.

사용 하는 폼에 관계 없이 항상 인덱싱된 속성의 set 메서드에 대해 커리 된 형식을 사용 해야 합니다. 커리 되는 함수에 대 한 자세한 내용은 [함수](../functions/index.md)를 참조 하세요.

## <a name="example"></a>예제

다음 코드 예제에서는 get 및 set 메서드를 사용 하는 기본 및 기본이 아닌 인덱싱된 속성을 정의 하 고 사용 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Output

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a>여러 인덱스 값이 있는 인덱싱된 속성

인덱싱된 속성에는 두 개 이상의 인덱스 값이 있을 수 있습니다. 이 경우 속성을 사용할 때 값은 쉼표로 구분 됩니다. 이러한 속성의 set 메서드에는 두 개의 커리 된 인수가 있어야 하 고, 첫 번째 인수는 키를 포함 하는 튜플이 고, 두 번째 인수는 설정 하려는 값입니다.

다음 코드에서는 여러 인덱스 값이 있는 인덱싱된 속성을 사용 하는 방법을 보여 줍니다.

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member _.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a>참조

- [멤버](index.md)
