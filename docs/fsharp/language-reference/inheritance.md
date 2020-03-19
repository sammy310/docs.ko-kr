---
title: 상속
description: "'상속' 키워드를 사용하여 F# 상속 관계를 지정하는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401132"
---
# <a name="inheritance"></a>상속

상속은 개체 지향 프로그래밍에서 "is-a" 관계 또는 하위 타이핑을 모델링하는 데 사용됩니다.

## <a name="specifying-inheritance-relationships"></a>상속 관계 지정

클래스 선언에서 키워드를 `inherit` 사용 하 여 상속 관계를 지정 합니다. 기본 구문 형태는 다음 예제에 나와 있습니다.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

클래스는 하나의 직접 기본 클래스를 가질 수 있습니다. `inherit` 키워드를 사용하여 기본 클래스를 지정하지 않으면 클래스가 암시적으로 `System.Object`에서 상속됩니다.

## <a name="inherited-members"></a>상속된 멤버

클래스가 다른 클래스에서 상속되는 경우 파생 클래스의 메서드 및 멤버는 파생 클래스의 직접 멤버인 것처럼 파생 클래스의 사용자가 사용할 수 있습니다.

let 바인딩 및 생성자 매개 변수는 클래스에 대한 전용이므로 파생 클래스에서 액세스할 수 없습니다.

키워드는 `base` 파생 클래스에서 사용할 수 있으며 기본 클래스 인스턴스를 나타냅니다. 자체 식별자처럼 사용됩니다.

## <a name="virtual-methods-and-overrides"></a>가상 메서드 및 재정의

가상 메서드(및 속성)는 다른 .NET 언어와 비교하여 F#에서 다소 다르게 작동합니다. 새 가상 멤버를 선언하려면 `abstract` 키워드를 사용합니다. 해당 메서드에 대 한 기본 구현을 제공 하는지 여부에 관계 없이이 작업을 수행 합니다. 따라서 기본 클래스의 가상 메서드에 대한 완전한 정의는 다음 패턴을 따릅니다.

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

파생 클래스에서 이 가상 메서드의 재정의는 다음 패턴을 따릅니다.

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

기본 클래스에서 기본 구현을 생략하면 기본 클래스가 추상 클래스가 됩니다.

다음 코드 예제에서는 기본 클래스에서 새 `function1` 가상 메서드의 선언 및 파생 된 클래스에서 재정의 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>생성자 및 상속

기본 클래스에 대 한 생성자는 파생 된 클래스에서 호출 해야 합니다. 기본 클래스 생성자의 인수는 `inherit` 절의 인수 목록에 나타납니다. 사용되는 값은 파생 된 클래스 생성자에 제공 된 인수에서 결정 되어야 합니다.

다음 코드는 파생 된 클래스상속 절에서 base 클래스 생성자 호출 하는 base 클래스와 파생 된 클래스를 보여 주며 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

여러 생성자의 경우 다음 코드를 사용할 수 있습니다. 파생된 클래스 생성자의 첫 번째 줄은 `inherit` 절이며 필드는 `val` 키워드로 선언된 명시적 필드로 나타납니다. 자세한 내용은 [명시적 필드: `val` 키워드](./members/explicit-fields-the-val-keyword.md)를 참조하십시오.

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

## <a name="alternatives-to-inheritance"></a>상속에 대한 대안

형식을 약간 수정해야 하는 경우 상속 대신 개체 식을 사용하는 것이 좋습니다. 다음 예제에서는 새 파생 된 형식을 만드는 대신 개체 식을 사용 하 여 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

개체 표현식에 대한 자세한 내용은 [개체 표현식을](object-expressions.md)참조하십시오.

개체 계층구조를 만들 때 상속 대신 구별된 공용 구조체를 사용하는 것이 좋습니다. 구별된 공용 구조체는 공통 전체 형식을 공유하는 다양한 개체의 다양한 동작을 모델링할 수도 있습니다. 단일 구별 된 공용 구조체는 종종 서로의 사소한 변형인 파생 클래스의 수가 필요하지 않습니다. 차별된 공용 구조체에 대한 자세한 내용은 [차별 조합을](discriminated-unions.md)참조하십시오.

## <a name="see-also"></a>참고 항목

- [개체 식](object-expressions.md)
- [F # 언어 참조](index.md)
