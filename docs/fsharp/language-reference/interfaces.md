---
title: 인터페이스
description: 'F # 인터페이스가 다른 클래스에서 구현 하는 관련 멤버의 집합을 지정 하는 방법에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 0cef2932045dae401f5aa069107815543457ca4a
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557053"
---
# <a name="interfaces"></a>인터페이스

*인터페이스* 는 다른 클래스에서 구현 하는 관련 멤버의 집합을 지정 합니다.

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

인터페이스 선언은 멤버가 구현 되지 않는다는 점을 제외 하 고 클래스 선언과 비슷합니다. 대신 모든 멤버는 키워드에 의해 표시 된 대로 추상적 `abstract` 입니다. 추상 메서드에는 메서드 본문을 제공 하지 않습니다. 그러나 키워드와 함께 멤버의 개별 정의를 메서드로 포함 하 여 기본 구현을 제공할 수도 있습니다 `default` . 이렇게 하려면 다른 .NET 언어의 기본 클래스에서 가상 메서드를 만드는 것과 동일 합니다. 이러한 가상 메서드는 인터페이스를 구현 하는 클래스에서 재정의할 수 있습니다.

인터페이스에 대 한 기본 액세스 가능성은 `public` 입니다.

필요에 따라 일반 F # 구문을 사용 하 여 각 메서드 매개 변수에 이름을 지정할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

위의 예제에서 `ISprintable` `Print` 메서드에는 이름이 인 형식의 단일 매개 변수가 있습니다 `string` `format` .

인터페이스를 구현 하는 방법에는 개체 식 사용, 클래스 형식 사용 등 두 가지가 있습니다. 두 경우 모두 클래스 형식 또는 개체 식은 인터페이스의 추상 메서드에 대 한 메서드 본문을 제공 합니다. 구현은 인터페이스를 구현 하는 각 형식에만 적용 됩니다. 따라서 다른 형식에 대 한 인터페이스 메서드는 서로 다를 수 있습니다.

`interface` `end` 간단한 구문을 사용 하는 경우 정의의 시작과 끝을 표시 하는 및 키워드는 선택 사항입니다. 이러한 키워드를 사용 하지 않는 경우 컴파일러는 사용 하는 구문을 분석 하 여 형식이 클래스 인지 또는 인터페이스 인지를 유추 하려고 합니다. 멤버를 정의 하거나 다른 클래스 구문을 사용 하는 경우 형식은 클래스로 해석 됩니다.

.NET 코딩 스타일은 모든 인터페이스를 대문자로 시작 하는 것입니다 `I` .

여러 매개 변수를 두 가지 방법으로 지정할 수 있습니다. F # 스타일 및입니다. NET 스타일입니다. 둘 다 .NET 소비자에 대해 동일한 방식으로 컴파일되지만 f # 스타일은 f # 스타일 매개 변수 응용 프로그램 및를 사용 하도록 합니다. NET 스타일은 F # 호출자가 튜플 인수 응용 프로그램을 사용 하도록 강제 합니다.

```fsharp
type INumeric1 =
    abstract Add: x: int -> y: int -> int

type INumeric2 =
    abstract Add: x: int * y: int -> int
```

## <a name="implementing-interfaces-by-using-class-types"></a>클래스 형식을 사용 하 여 인터페이스 구현

`interface`다음 코드에 표시 된 것 처럼 키워드, 인터페이스 이름 및 키워드를 사용 하 여 클래스 형식에서 하나 이상의 인터페이스를 구현 하 고 인터페이스 멤버 정의를 구현할 수 있습니다 `with` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

인터페이스 구현은 상속 되므로 파생 된 클래스는이를 다시 구현할 필요가 없습니다.

## <a name="calling-interface-methods"></a>인터페이스 메서드 호출

인터페이스 메서드는 인터페이스를 통해 인터페이스를 구현 하는 형식의 개체를 통해 호출할 수 없습니다. 따라서 `:>` 이러한 메서드를 호출 하려면 연산자 또는 연산자를 사용 하 여 인터페이스 형식으로 업 캐스트 할 수 있습니다 `upcast` .

형식의 개체가 있을 때 인터페이스 메서드를 호출 하려면 `SomeClass` 다음 코드와 같이 개체를 인터페이스 형식에 업 캐스트 해야 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

다른 방법은 다음 예제와 같이 업캐스팅 하 고 인터페이스 메서드를 호출 하는 개체에 대 한 메서드를 선언 하는 것입니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a>개체 식을 사용 하 여 인터페이스 구현

개체 식은 인터페이스를 구현 하는 간단한 방법을 제공 합니다. 명명 된 형식을 만들 필요가 없고 인터페이스 메서드를 지 원하는 개체를 추가 메서드 없이 사용 하려는 경우에 유용 합니다. 다음 코드에서는 개체 식을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a>인터페이스 상속

인터페이스는 하나 이상의 기본 인터페이스에서 상속할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="implementing-interfaces-with-default-implementations"></a>기본 구현을 사용 하 여 인터페이스 구현

C #은 다음과 같이 기본 구현으로 인터페이스를 정의 합니다.

```csharp
using System;

namespace CSharp
{
    public interface MyDim
    {
        public int Z => 0;
    }
}
```

F #에서 직접 사용할 수 있습니다.

```fsharp
open CSharp

// You can implement the interface via a class
type MyType() =
    member _.M() = ()

    interface MyDim

let md = MyType() :> MyDim
printfn $"DIM from C#: %d{md.Z}"

// You can also implement it via an object expression
let md' = { new MyDim }
printfn $"DIM from C# but via Object Expression: %d{md'.Z}"
```

가상 멤버 재정의와 같이를 사용 하 여 기본 구현을 재정의할 수 있습니다 `override` .

기본 구현이 없는 인터페이스의 멤버는 여전히 명시적으로 구현 되어야 합니다.

## <a name="implementing-the-same-interface-at-different-generic-instantiations"></a>서로 다른 제네릭 인스턴스화에 동일한 인터페이스 구현

F #에서는 다음과 같이 서로 다른 제네릭 인스턴스화에 동일한 인터페이스를 구현할 수 있습니다.

```fsharp
type IA<'T> =
    abstract member Get : unit -> 'T

type MyClass() =
    interface IA<int> with
        member x.Get() = 1
    interface IA<string> with
        member x.Get() = "hello"

let mc = MyClass()
let iaInt = mc :> IA<int>
let iaString = mc :> IA<string>

iaInt.Get() // 1
iaString.Get() // "hello"
```

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
- [개체 식](object-expressions.md)
- [클래스](classes.md)
