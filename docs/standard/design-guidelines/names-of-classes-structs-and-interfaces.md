---
title: 클래스, 구조체 및 인터페이스의 이름
description: .NET 라이브러리를 확장 하 고 상호 작용 하는 라이브러리를 디자인 하기 위한 지침의 일부로 클래스, 구조체 및 인터페이스의 이름을 지정 하는 데 이러한 지침을 사용 합니다.
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
ms.openlocfilehash: b9de9329cc8e1bfc47a46523c7119bb3b2c244d8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290216"
---
# <a name="names-of-classes-structs-and-interfaces"></a>클래스, 구조체 및 인터페이스의 이름
다음 명명 지침은 일반적인 형식 이름 지정에 적용 됩니다.

 ✔️는 명사 또는 명사구를 사용 하 여 클래스와 구조체의 이름을 지정할 합니다.

 이는 동사 구와 이름이 지정 된 메서드의 형식 이름을 구분 합니다.

 ✔️는 형용사 구를 사용 하 여 인터페이스를 만들거나 명사 또는 명사구를 사용 하는 경우도 있습니다.

 명사 및 명사구는 거의 사용 되지 않으며 형식이 인터페이스가 아닌 추상 클래스 여야 함을 나타낼 수 있습니다.

 ❌클래스 이름을 접두사로 지정 하지 마십시오 (예: "C").

 기본 클래스의 이름을 사용 하 여 파생 클래스의 이름을 종료 하는 것이 좋습니다 ✔️.

 이는 매우 읽기 쉬우며 관계를 명확 하 게 설명 합니다. 코드에서이에 대 한 몇 가지 예는 이며 일종의, `ArgumentOutOfRangeException` `Exception` 및 `SerializableAttribute` 입니다. `Attribute` 그러나이 지침을 적용할 때 적절 한 판단을 사용 하는 것이 중요 합니다. 예를 들어 `Button` 클래스는 일종의 이벤트 이지만 `Control` `Control` 이름에는 표시 되지 않습니다.

 인터페이스 이름 앞에 문자 I를 사용 하 여 형식이 인터페이스 임을 나타내려면 ✔️ 합니다.

 예를 들어 `IComponent` (설명 명사), `ICustomAttributeProvider` (명사 구) 및 `IPersistable` (형용사)는 적절 한 인터페이스 이름입니다. 다른 형식 이름과 마찬가지로 약어를 사용 하지 마십시오.

 클래스가 인터페이스의 표준 구현인 클래스-인터페이스 쌍을 정의 하는 경우 인터페이스 이름에서 "I" 접두사에 의해서만 이름이 다른 지 확인 ✔️ 합니다.

## <a name="names-of-generic-type-parameters"></a>제네릭 형식 매개 변수의 이름
 제네릭을 .NET Framework 2.0에 추가 했습니다. 이 기능에는 *형식 매개 변수*라는 새로운 종류의 식별자가 도입 되었습니다.

 단일 문자 이름이 완전히 설명이 없는 경우 설명이 포함 된 이름을 사용 하 여 제네릭 형식 매개 변수 이름을 지정 하 ✔️ 합니다.

 ✔️ 하나의 `T` 단일 문자 형식 매개 변수를 사용 하는 형식에 대 한 형식 매개 변수 이름으로를 사용 하는 것이 좋습니다.

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 을 사용 하 여 설명 형식 매개 변수 이름에 접두사를 ✔️ `T` 합니다.

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 매개 변수 이름에서 형식 매개 변수에 적용 되는 제약 조건을 표시 하는 것이 좋습니다 ✔️.

 예를 들어로 제한 된 매개 변수를 `ISession` 호출할 수 있습니다 `TSession` .

## <a name="names-of-common-types"></a>공용 형식의 이름
 ✔️에서 파생 된 형식을 명명 하거나 특정 .NET Framework 형식을 구현할 때 다음 표에 설명 된 지침을 따릅니다.

|Base Type|파생/구현 형식 지침|
|---------------|------------------------------------------|
|`System.Attribute`|✔️ 사용자 지정 특성 클래스의 이름에 "Attribute" 접미사를 추가 합니다.|
|`System.Delegate`|✔️ 이벤트에 사용 되는 대리자 이름에 "EventHandler" 접미사를 추가 합니다.<br /><br /> 이벤트 처리기로 사용 된 대리자 이외의 이름에 "Callback" 접미사를 추가 ✔️ 합니다.<br /><br /> ❌"Delegate" 접미사를 대리자에 추가 하지 마십시오.|
|`System.EventArgs`|"EventArgs" 접미사를 추가 ✔️ 합니다.|
|`System.Enum`|❌이 클래스에서 파생 되지 않습니다. 대신 해당 언어로 지원 되는 키워드를 사용 합니다. 예를 들어 c #에서는 키워드를 사용 `enum` 합니다.<br /><br /> ❌"Enum" 또는 "Flag" 접미사는 추가 하지 마십시오.|
|`System.Exception`|✔️ 접미사 "Exception"을 추가 합니다.|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|✔️ 접미사 "Dictionary"를 추가 합니다. 는 `IDictionary` 특정 유형의 컬렉션 이지만이 지침은 다음과 같은 보다 일반적인 컬렉션 지침 보다 우선적으로 적용 됩니다.|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|"Collection" 접미사를 추가 ✔️ 합니다.|
|`System.IO.Stream`|접미사 "Stream"을 추가 ✔️ 합니다.|
|`CodeAccessPermission IPermission`|✔️ 접미사 "Permission"을 추가 합니다.|

## <a name="naming-enumerations"></a>열거형 이름 지정
 일반적으로 열거형 형식 (열거형이 라고도 함)의 이름은 표준 형식 명명 규칙을 따라야 합니다 (예를 들어). 그러나 열거형에는 특별히 적용 되는 추가 지침이 있습니다.

 값이 비트 필드인 경우를 제외 하 고는 열거형에 대해 단 수 형식 이름을 사용 ✔️ 합니다.

 비트 필드를 값으로 사용 하는 열거형 (플래그 열거형이 라고도 함)에는 복수형 형식 이름을 사용 ✔️ 합니다.

 ❌열거형 형식 이름에 "Enum" 접미사를 사용 하지 마십시오.

 ❌열거형 형식 이름에는 "Flag" 또는 "Flags" 접미사를 사용 하지 마십시오.

 ❌열거형 값 이름에 접두사를 사용 하지 마십시오 (예: ADO 열거형의 경우 "ad", 서식 있는 텍스트 열거형의 경우 "rtf").

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임 워크 디자인 지침](index.md)
- [명명 지침](naming-guidelines.md)
