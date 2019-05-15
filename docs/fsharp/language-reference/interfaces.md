---
title: 인터페이스
description: 에 대해 알아봅니다 하는 방법 F# 인터페이스는 다른 클래스에서 구현 관련된 멤버의 집합을 지정 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: 5b57769af6c05b83b3a112635033abf4efaca772
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645370"
---
# <a name="interfaces"></a>인터페이스

*인터페이스* 다른 클래스를 구현 하는 관련된 멤버의 집합을 지정 합니다.

## <a name="syntax"></a>구문

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a>설명

인터페이스 선언을 멤버가 구현 되는 점을 제외 하 고 클래스 선언과를 비슷합니다. 대신, 모든 멤버는 키워드로 표시 된 대로 추상 `abstract`합니다. 추상 메서드에 대 한 메서드 본문을 제공 하지 않습니다. 또한 함께 메서드로 별도 멤버의 정의 포함 하 여 기본 구현을 제공할 수 있습니다는 `default` 키워드입니다. 이렇게 하는 것은 다른.NET 언어의 기본 클래스의 가상 메서드를 만드는 것과 같습니다. 이러한 가상 메서드는 인터페이스를 구현 하는 클래스에서 재정의할 수 있습니다.

인터페이스에 대 한 기본 액세스 가능성은 `public`합니다.

필요에 따라 이름을 지정할 수 있습니다 각 메서드 매개 변수를 사용 하 여 일반 F# 구문:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

위의 `ISprintable` 예제에서는 합니다 `Print` 메서드 형식의 단일 매개 변수가 `string` 이름의 `format`합니다.

인터페이스를 구현 하는 방법은 두 가지: 개체 식을 사용 하 고 클래스 형식을 사용 하 여 합니다. 두 경우 모두 클래스 형식이 나 개체 식 인터페이스의 추상 메서드에 대 한 메서드 본문을 제공합니다. 구현은은 인터페이스를 구현 하는 각 형식에 적용 됩니다. 따라서 다른 형식의 인터페이스 메서드는 서로 다를 수 있습니다.

키워드 `interface` 고 `end`, 시작 및 정의의 끝을 표시 하는 간단한 구문을 사용 하는 경우 선택 사항입니다. 이러한 키워드를 사용 하지 않는 경우 컴파일러는 형식이 클래스 또는 인터페이스를 사용 하는 구문 분석 하 여 인지 여부를 유추 하려고 합니다. 멤버를 정의 하거나 다른 클래스 구문을 사용 하는 경우 형식은 클래스로 해석 됩니다.

대문자를 사용 하 여 모든 인터페이스를 시작 하는 코딩 스타일.NET `I`합니다.

## <a name="implementing-interfaces-by-using-class-types"></a>클래스 형식을 사용 하 여 인터페이스를 구현 합니다.

사용 하 여 클래스 형식에 하나 이상의 인터페이스를 구현할 수는 `interface` 키워드, 인터페이스의 이름 및 `with` 인터페이스 멤버 정의 뒤에 다음 코드 에서처럼 키워드.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

인터페이스 구현은 상속 되므로, 모든 파생된 클래스에서는를 구현할 필요가 없습니다.

## <a name="calling-interface-methods"></a>인터페이스 메서드 호출

인터페이스 메서드는 인터페이스를 구현 하는 형식의 개체를 통해서가 아니라 인터페이스를 통해서만 호출할 수 있습니다. 따라서 해야 인터페이스 형식으로 업 캐스트를 사용 하 여 합니다 `:>` 연산자 또는 `upcast` 이러한 메서드를 호출 하기 위해 연산자입니다.

형식의 개체를 해야 하는 경우 인터페이스 메서드를 호출 하려면 `SomeClass`, 다음 코드 에서처럼 개체 인터페이스 형식으로 업 캐스트 해야 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

대신 해당 업캐스팅 개체에서 메서드를 선언 하는 다음 예제와 같이 인터페이스 메서드를 호출 하며

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a>개체 식을 사용 하 여 인터페이스를 구현 합니다.

개체 식에는 인터페이스를 구현 하는 간단한 방법을 제공 합니다. 명명 된 형식을 만들 필요가 없습니다 및 추가 메서드 없이 인터페이스 메서드를 지 원하는 개체를 원하는 경우에 유용 합니다. 개체 식 다음 코드에 나와 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a>인터페이스 상속

인터페이스는 하나 이상의 기본 인터페이스에서 상속할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [개체 식](object-expressions.md)
- [클래스](classes.md)
