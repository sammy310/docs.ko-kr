---
title: 상속
description: 지정 하는 방법을 알아봅니다 F# '상속' 키워드를 사용 하 여 상속 관계입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 2fad2ddafbc0174903d3d24be3ce5412f7e1f9ed
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641817"
---
# <a name="inheritance"></a>상속

상속 "은-a" 관계를 모델링 하는 개체 지향 프로그래밍에서 동등 또는 합니다.

## <a name="specifying-inheritance-relationships"></a>상속 관계를 지정합니다.

사용 하 여 상속 관계를 지정 합니다 `inherit` 클래스 선언에서 키워드입니다. 기본 구문 형식은 다음 예제에 표시 됩니다.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

클래스는 직접 기본 클래스는 최대 하나만 있을 수 있습니다. 기본 클래스를 지정 하지 않으면 사용 하 여 합니다 `inherit` 키워드를 클래스에서 암시적으로 상속 `System.Object`합니다.

## <a name="inherited-members"></a>상속 된 멤버

클래스가 다른 클래스에서 상속 하는 경우 메서드 및 기본 클래스의 멤버는 파생된 클래스의 직접 멤버인 것 처럼 파생된 클래스의 사용자에 게 제공 됩니다.

모든 let 바인딩 및 생성자 매개 변수는 클래스에 개인 따라서 파생된 클래스에서 액세스할 수 없습니다.

키워드 `base` 기본 클래스 인스턴스를 참조 하는 파생된 클래스에서 사용할 수 있습니다. 자체 식별자 처럼 사용 됩니다.

## <a name="virtual-methods-and-overrides"></a>가상 메서드 및 재정의

가상 메서드 (및 속성)에서 약간 다르게 작동 F# 다른.NET 언어를 비교 하 여 합니다. 새 가상 멤버를 선언 하려면 사용 된 `abstract` 키워드입니다. 해당 메서드에 대 한 기본 구현을 제공 하는 여부에 관계 없이이 작업을 수행 합니다. 따라서 기본 클래스에서 가상 메서드의 완료 정의이 패턴을 따릅니다.

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

및이 가상 메서드를 재정의 하는 파생된 클래스에서이 패턴을 따릅니다.

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

기본 클래스의 기본 구현은 생략 하면 기본 클래스는 추상 클래스를 됩니다.

다음 코드 예제는 새 가상 메서드로 선언 `function1` 기본 클래스 및 파생된 클래스에서 재정의 하는 방법입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>생성자 및 상속

기본 클래스의 생성자는 파생된 클래스에서 호출 되어야 합니다. 기본 클래스 생성자에 대 한 인수는 인수 목록에 표시 된 `inherit` 절. 파생된 클래스 생성자에 제공 된 인수에서 사용 되는 값을 결정 해야 합니다.

다음 코드는 파생된 클래스는 상속 절에서 기본 클래스 생성자를 호출 하는 경우 기본 클래스 및 파생된 클래스를 보여줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

생성자가 여러 개인 경우 다음 코드를 사용할 수 있습니다. 파생된 클래스 생성자의 첫 번째 줄은는 `inherit` 절 및 필드를 사용 하 여 선언 된 필드를 명시적으로 표시 된 `val` 키워드입니다. 자세한 내용은 참조 하세요. [명시적 필드: 합니다 `val` 키워드](members/explicit-fields-the-val-keyword.md)합니다.

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a>상속에 대 한 대안

형식의 약간만 수정 하면 필요한 경우에서 상속 하는 대신 개체 식을 사용 하는 것이 좋습니다. 다음 예제에서는 파생된 형식을 새로 만드는 대신 개체 식의 사용을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

개체 식에 대 한 자세한 내용은 참조 하세요. [개체 식](object-expressions.md)합니다.

개체 계층 구조를 만들 때에 상속 하는 대신 구별된 된 공용 구조체를 사용 하는 것이 좋습니다. 구별 된 공용 구조체는 전체 공용 형식을 공유 하는 다른 개체의 동작을 모델링할 수도 있습니다. 단일 구별 된 공용 구조체 파생된 클래스는 서로 조금씩 여러 필요가 종종 수 없습니다. 구별 된 공용 구조체에 대 한 정보를 참조 하세요 [구별 된 공용 구조체](discriminated-unions.md)합니다.

## <a name="see-also"></a>참고자료

- [개체 식](object-expressions.md)
- [F# 언어 참조](index.md)
