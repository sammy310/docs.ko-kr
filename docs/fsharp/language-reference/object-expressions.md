---
title: 개체 식
description: '새 명명 된 형식을 만드는 데 필요한 추가 코드와 오버 헤드가 발생 하지 않도록 하려면 F # 개체 식을 사용 하는 방법을 알아봅니다.'
ms.date: 02/08/2019
ms.openlocfilehash: 8a3e40b7833b551eefb95ec62b935acd1ba7b1f9
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740304"
---
# <a name="object-expressions"></a>개체 식

*개체 식은* 기존 기본 형식, 인터페이스 또는 인터페이스 집합을 기반으로 하는 동적으로 생성 된 익명 개체 형식의 새 인스턴스를 만드는 식입니다.

## <a name="syntax"></a>구문

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>설명

이전 구문에서 *typename* 은 기존 클래스 형식 또는 인터페이스 형식을 나타냅니다. *형식* 매개 변수는 선택적 제네릭 형식 매개 변수를 설명 합니다. *인수* 는 생성자 매개 변수를 요구 하는 클래스 형식에만 사용 됩니다. *멤버 정의* 는 기본 클래스 메서드를 재정의 하거나 기본 클래스 또는 인터페이스에서 추상 메서드를 구현 하는 것입니다.

다음 예제에서는 다양 한 유형의 개체 식을 보여 줍니다.

```fsharp
// This object expression specifies a System.Object but overrides the
// ToString method.
let obj1 = { new System.Object() with member x.ToString() = "F#" }
printfn $"{obj1}"

// This object expression implements the IFormattable interface.
let delimiter(delim1: string, delim2: string, value: string) =
    { new System.IFormattable with
        member x.ToString(format: string, provider: System.IFormatProvider) =
            if format = "D" then
                delim1 + value + delim2
            else
                value }

let obj2 = delimiter("{","}", "Bananas!");

printfn "%A" (System.String.Format("{0:D}", obj2))

// Define two interfaces
type IFirst =
  abstract F : unit -> unit
  abstract G : unit -> unit

type ISecond =
  inherit IFirst
  abstract H : unit -> unit
  abstract J : unit -> unit

// This object expression implements both interfaces.
let implementer() =
    { new ISecond with
        member this.H() = ()
        member this.J() = ()
      interface IFirst with
        member this.F() = ()
        member this.G() = () }
```

## <a name="using-object-expressions"></a>개체 식 사용

새 명명 된 형식을 만드는 데 필요한 추가 코드와 오버 헤드가 발생 하지 않도록 하려면 개체 식을 사용 합니다. 프로그램에서 생성 되는 형식의 수를 최소화 하기 위해 개체 식을 사용 하는 경우 코드 줄 수를 줄이고 불필요 한 형식의 확산을 방지할 수 있습니다. 특정 상황을 처리 하기 위해 많은 형식을 만드는 대신 기존 형식을 사용자 지정 하거나 특정 사례에 대 한 적절 한 인터페이스 구현을 제공 하는 개체 식을 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
