---
title: 레코드
description: 에 대해 알아봅니다 하는 방법 F# 레코드는 멤버를 사용 하 여 필요에 따라 명명 된 값의 간단한 집계를 나타냅니다.
ms.date: 06/09/2019
ms.openlocfilehash: cfb8de8272b479571119ae4cf91ea1d6fd5db73c
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816197"
---
# <a name="records"></a>레코드

레코드는 명명된 값의 간단한 집계(경우에 따라 멤버가 포함된)를 나타냅니다. 이러한 구조체 또는 참조 형식이 될 수 있습니다.  기본적으로 참조 형식입니다.

## <a name="syntax"></a>구문

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a>설명

이전 구문에서 *typename* 이름 레코드 형식입니다 *label1* 하 고 *label2* 라고 하는 값의 이름이 *레이블*, 및 *type1* 하 고 *type2* 유형은 다음이 값 중입니다. *멤버 목록* 멤버 유형에 대 한 선택적 목록입니다.  사용할 수는 `[<Struct>]` 특성 참조 형식인 레코드 대신 구조체 레코드를 만듭니다.

다음은 몇 가지 예입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

각 레이블에 이면 별도 줄에 세미콜론 선택 사항입니다.

라고 하는 식의 값을 설정할 수 있습니다 *식을 기록*합니다. 컴파일러는 (레이블은 다른 레코드 형식의 충분히 다릅니다) 하는 경우 사용 되는 레이블에서 형식을 유추 합니다. 중괄호 ({}) 레코드 식을 묶습니다. 다음 코드에서는 레이블과 함께 float 요소를 세 개를 사용 하 여 레코드를 초기화 하는 레코드 식이 `x`하십시오 `y` 및 `z`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

다른 형식에도 동일한 레이블이 될 수 있는 경우에 축약 형태를 사용 하지 마세요.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

가장 최근에 선언 된 형식의 레이블을 우선 이전에 선언 된 형식의 따라서 앞의 예에서 `mypoint3D` 로 유추 됩니다 `Point3D`합니다. 레코드 형식은 다음 코드와 같이 명시적으로 지정할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

클래스 형식에서와 마찬가지로 레코드 유형에 대 한 메서드를 정의할 수 있습니다.

## <a name="creating-records-by-using-record-expressions"></a>레코드 식을 사용 하 여 레코드 만들기

레코드에서 정의 되는 레이블을 사용 하 여 레코드를 초기화할 수 있습니다. 이 작업을 수행 하는 식 이라고 하는 *식 기록*합니다. 중괄호를 사용 하 여 레코드 식을 묶는를 구분 기호로 세미콜론을 사용 합니다.

다음 예제에서는 레코드를 만드는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

레코드 식에 형식 정의의 마지막 필드 뒤에 세미콜론은 여부에 관계 없이 필드를 모두 한 줄 선택 사항입니다.

레코드를 만든 경우 각 필드에 대 한 값을 제공 해야 합니다. 모든 필드에 대 한 초기화 식에서 다른 필드의 값을 참조할 수 없습니다.

다음 코드에서 형식의 `myRecord2` 필드의 이름에서 유추 됩니다. 필요에 따라 형식 이름을 명시적으로 지정할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

다른 형식의 레코드 생성 된 기존 레코드를 복사 하 고 필드 값의 일부 변경 해야 할 경우에 유용 합니다. 다음 코드 줄이에 대해 설명 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

이 형태의 레코드 식 이라고 합니다 *복사 및 업데이트 레코드 식*합니다.

레코드를 기본적으로 변경할 수 없는 경우 그러나 복사 및 업데이트 식을 사용 하 여 수정 된 레코드를 쉽게 만들 수 있습니다. 변경 가능한 필드를 명시적으로 지정할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

레코드 필드를 사용 하 여 DefaultValue 특성을 사용 하지 마세요. 기본값으로 초기화 되는 필드를 사용 하 여 레코드의 기본 인스턴스를 정의 및 다음 복사본을 사용 하 여 업데이트 레코드 식의 기본 값과 다른 모든 필드를 설정 하는 것이 좋습니다.

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="creating-mutually-recursive-records"></a>상호 재귀 레코드 만들기

레코드를 만들 때에 잠시 나중에 정의 하려는 다른 형식에 종속 되 게 하는 것이 좋습니다. 상호 재귀를 레코드 종류를 정의 하지 않으면 컴파일 오류입니다.

완료 정의 상호 재귀 레코드는 `and` 키워드입니다. 이렇게 하면 2 개 이상의 레코드 종류를 함께 연결할 수 있습니다.

예를 들어, 다음 코드는 정의 `Person` 고 `Address` 상호 재귀 형식:

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string }
```

없이 앞의 예제를 정의 하는 경우는 `and` 키워드를 컴파일되지 않습니다. `and` 상호 재귀 정의 대 한 키워드를 사용 합니다.

## <a name="pattern-matching-with-records"></a>레코드를 사용한 패턴 일치

레코드 패턴 일치에 사용할 수 있습니다. 일부 필드를 명시적으로 지정 하 고 일치 하는 경우에 할당 되는 다른 필드에 대 한 변수를 제공할 수 있습니다. 다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

이 코드의 출력은 다음과 같습니다.

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a>레코드와 클래스 간의 차이점

레코드 필드에는 자동으로 속성으로 노출 된 것 이며 생성에 사용 되 고 레코드의 복사 클래스에서 다릅니다. 레코드 생성 클래스 생성에서도 서로 다릅니다. 레코드 형식에서 생성자를 정의할 수 없습니다. 대신이 항목에 설명 된 구문이 적용 됩니다. 클래스는 생성자 매개 변수, 필드 및 속성 간에 직접 관계가 없는 경우

공용 구조체 및 구조체 형식과 마찬가지로 레코드 구조적 같음 의미 체계를 가집니다. 클래스에는 참조 같음 의미 체계. 다음 코드 예제에서는 이 작업을 보여줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

이 코드의 출력은 다음과 같습니다.

```
The records are equal.
```

클래스를 사용 하 여 동일한 코드를 작성 하는 경우 두 클래스 개체가 같지 두 값 힙에 두 개체를 나타내는 것 이므로 주소만 비교 됨 (해당 클래스 형식는 `System.Object.Equals` 메서드).

레코드에 대 한 같음, 참조 해야 하는 경우 추가 특성 `[<ReferenceEquality>]` 레코드 위에 있습니다.

## <a name="see-also"></a>참고자료

- [F# 형식](fsharp-types.md)
- [클래스](classes.md)
- [F# 언어 참조](index.md)
- [Reference-Equality](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [패턴 일치](pattern-matching.md)
