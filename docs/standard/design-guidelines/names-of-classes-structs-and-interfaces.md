---
title: 클래스, 구조체 및 인터페이스의 이름
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: 2c528348c0e84037a80df9797c56f03b51c73adc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401240"
---
# <a name="names-of-classes-structs-and-interfaces"></a>클래스, 구조체 및 인터페이스의 이름
다음에 있는 명명 지침은 일반 형식 이름 지정에 적용됩니다.

 ✔️ pascalCasing을 사용하여 명사 또는 명사 구를 사용하여 클래스와 구조체를 이름 지정합니다.

 이렇게 하면 동사 구로 이름이 지정된 메서드와 형식 이름을 구별합니다.

 ✔️ DO 는 형용사 구또는 때때로 명사 또는 명사 구와 인터페이스를 이름 지정합니다.

 명사 및 명사 구는 거의 사용해야 하며 형식이 인터페이스가 아닌 추상 클래스여야 함을 나타낼 수 있습니다.

 ❌클래스 이름에 접두사(예: "C")를 지정하지 마십시오.

 ✔️ 기본 클래스의 이름으로 파생 된 클래스의 이름을 종료 고려 합니다.

 이것은 매우 읽을 수 있으며 관계를 명확하게 설명합니다. 코드에서 이것의 몇 가지 `ArgumentOutOfRangeException`예는 다음과 `Exception`같습니다. `SerializableAttribute` `Attribute` 그러나 이 지침을 적용할 때 합리적인 판단을 사용하는 것이 중요합니다. 예를 들어 `Button` 클래스는 일종의 `Control` 이벤트이지만 `Control` 이름에는 나타나지 않습니다.

 ✔️ do do 인터페이스 이름을 문자 I로 사용하여 형식이 인터페이스임을 나타냅니다.

 예를 `IComponent` 들어(설명 명사), `ICustomAttributeProvider` (명사 구) `IPersistable` 및 (형용사)는 적절한 인터페이스 이름입니다. 다른 형식 이름과 마찬가지로 약어는 사용하지 마십시오.

 ✔️ 클래스가 인터페이스의 표준 구현인 클래스 인터페이스 쌍을 정의할 때 인터페이스 이름의 "I" 접두사에 의해서만 이름이 달라지도록 합니다.

## <a name="names-of-generic-type-parameters"></a>제네릭 형식 매개 변수의 이름
 제네릭이 .NET 프레임워크 2.0에 추가되었습니다. 이 기능은 *type 매개 변수라는*새로운 종류의 식별자를 도입했습니다.

 ✔️ DO는 단일 문자 이름이 완전히 설명이 되고 설명이 있는 이름이 값을 추가하지 않는 한 설명이 있는 제네릭 형식 매개 변수를 이름 지정합니다.

 ✔️ 단일 `T` 문자 형식 매개 변수가 있는 형식에 대한 형식 매개 변수 이름으로 사용하는 것을 고려합니다.

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 ✔️ do 를 사용 하 고 `T`설명 형식 매개 변수 이름을 접두사

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 ✔️ 매개 변수의 이름으로 형식 매개 변수에 배치 된 제약 조건을 나타냅니다.

 예를 들어 로 제한된 `ISession` 매개 변수를 호출할 `TSession`수 있습니다.

## <a name="names-of-common-types"></a>공통 형식의 이름
 ✔️ 특정 .NET Framework 형식에서 파생된 형식의 이름을 지정하거나 구현할 때 다음 표에 설명된 지침을 따릅니다.

|Base Type|파생/구현 유형 지침|
|---------------|------------------------------------------|
|`System.Attribute`|✔️ 사용자 지정 특성 클래스의 이름에 접미사 "특성"을 추가합니다.|
|`System.Delegate`|✔️ 이벤트에 사용되는 대리자의 이름에 접미사 "EventHandler"를 추가합니다.<br /><br /> ✔️ 이벤트 처리기로 사용되는 대리자 이외의 이름에 접미사 "콜백"을 추가합니다.<br /><br /> ❌대리인에 접미사 "대리자"를 추가하지 마십시오.|
|`System.EventArgs`|✔️ 접미사 "EventArgs"를 추가합니다.|
|`System.Enum`|❌이 클래스에서 파생되지 마십시오. 대신 언어에서 지원하는 키워드를 사용합니다. 예를 들어 C#에서 키워드를 `enum` 사용합니다.<br /><br /> ❌접미사 "열거형" 또는 "플래그"를 추가하지 마십시오.|
|`System.Exception`|✔️ 접미사 "예외"를 추가합니다.|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|✔️ 접미사 "사전"을 추가합니다. 특정 `IDictionary` 유형의 컬렉션이지만 이 지침은 다음에 오는 보다 일반적인 컬렉션 지침보다 우선합니다.|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|✔️ 접미사 "컬렉션"을 추가합니다.|
|`System.IO.Stream`|✔️ 접미사 "스트림"을 추가합니다.|
|`CodeAccessPermission IPermission`|✔️ 접미사 "권한"을 추가합니다.|

## <a name="naming-enumerations"></a>이름 지정 열거형
 열거형 형식(열거형이라고도 함)의 이름은 일반적으로 표준 형식 명명 규칙(파스칼케이팅 등)을 따라야 합니다. 그러나 열거형에 특별히 적용되는 추가 지침이 있습니다.

 ✔️ 값이 비트 필드가 아니면 열거형에 단수 형식 이름을 사용합니다.

 ✔️ dodo는 비트 필드가 있는 열거형에 대해 플래그 열거형이라고도 하는 값으로 복수 형식 이름을 사용합니다.

 ❌열거형 유형 이름에 "열거형" 접미사를 사용하지 마십시오.

 ❌열거형 유형 이름에는 "플래그" 또는 "플래그" 접미사를 사용하지 마십시오.

 ❌열거형 값 이름에 는 접두사를 사용하지 마십시오(예: ADO 열거형의 경우 "광고", "rtf" 등).

 *2005년, 2009년 마이크로소프트© 판권.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
