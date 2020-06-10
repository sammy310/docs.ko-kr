---
title: 형식 멤버의 이름
description: 메서드, 속성, 이벤트 및 필드와 같은 .NET의 형식 멤버를 명명 하는 방법에 대 한 지침을 알아봅니다.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
ms.openlocfilehash: de613673989bd174ac80adda566d04600059642d
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662500"
---
# <a name="names-of-type-members"></a>형식 멤버의 이름
형식은 메서드, 속성, 이벤트, 생성자 및 필드 등의 멤버로 이루어집니다. 다음 섹션에서는 형식 멤버 이름 지정에 대한 지침을 설명합니다.

## <a name="names-of-methods"></a>메서드 이름
 메서드가 작업을 수행하는 수단이기 때문에 디자인 지침에서는 메서드 이름이 동사 또는 동사구여야 합니다. 또한 이 지침을 따르면 명사 또는 형용사구인 속성 및 형식 이름과 메서드 이름을 구분할 수 있습니다.

 동사 또는 동사 구의 메서드 이름을 제공 하는 ✔️ 합니다.

```csharp
public class String {
    public int CompareTo(...);
    public string[] Split(...);
    public string Trim();
}
```

## <a name="names-of-properties"></a>속성 이름
 다른 멤버와 달리 속성은 명사구 또는 형용사 이름이 지정되어야 합니다. 속성이 데이터를 나타내기 때문에 속성 이름은 이를 반영해야 합니다. PascalCasing은 속성 이름에 항상 사용됩니다.

 명사, 명사구 또는 형용사를 사용 하 여 이름 속성을 ✔️ 합니다.

 ❌다음 예제와 같이 "Get" 메서드의 이름과 일치 하는 속성이 없습니다.

 `public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`

 이 패턴은 일반적으로 속성이 실제로 메서드임을 나타냅니다.

 단일 구를 사용 하는 대신 "List" 또는 "Collection"을 사용 하는 것이 아니라 컬렉션의 항목을 설명 하는 복수 구를 사용 하 여 컬렉션 속성의 이름을 ✔️ 합니다.

 찬성 문구 (대신)를 사용 하 여 부울 속성의 이름을 ✔️ `CanSeek` `CantSeek` 합니다. 필요에 따라 부울 속성에 "Is", "Can" 또는 "Is"를 접두사로 추가 하 고 값을 추가할 수도 있습니다.

 속성에 해당 형식과 같은 이름을 지정 하는 것이 좋습니다 ✔️.

 예를 들어, 다음 속성은 현재 올바르게 `Color`라는 열거형 값을 설정하므로 속성 이름은 `Color`입니다.

```csharp
public enum Color {...}
public class Control {
    public Color Color { get {...} set {...} }
}
```

## <a name="names-of-events"></a>이벤트 이름
 이벤트는 발생 중인 작업 또는 발생한 작업 중 하나를 가리킵니다. 따라서 메서드와 마찬가지로 이벤트는 동사를 사용하여 명명하고 동사 시제는 이벤트가 발생할 시간을 나타내는 데 사용됩니다.

 동사 또는 동사 구를 사용 하 여 이름 이벤트를 ✔️ 합니다.

 예를 들면 `Clicked`, `Painting`, `DroppedDown` 등입니다.

 ✔️는 현재 및 이전 시제를 사용 하 여 전후에 이벤트 이름을 제공 합니다.

 예를 들어 창이 닫히기 전에 발생하는 닫기 이벤트는 `Closing`이라고 하고 창이 닫힌 후에 발생하는 닫기 이벤트는 `Closed`라고 합니다.

 ❌사전 및 사후 이벤트를 나타내려면 "Before" 또는 "After" 접두사 또는 postfixes를 사용 하지 마십시오. 위에서 설명한 대로 현재 및 과거 시제를 사용합니다.

 다음 예제에 표시 된 것 처럼 "EventHandler" 접미사를 사용 하 여 이벤트 처리기 (이벤트 유형으로 사용 되는 대리자)의 이름을 ✔️ 합니다.

 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`

 이벤트 처리기에서 및 라는 두 매개 변수를 사용 ✔️ `sender` `e` 합니다.

 보낸 사람 매개 변수는 이벤트를 발생시킨 개체를 나타냅니다. 보낸 사람 매개 변수는 보다 구체적인 형식을 적용할 수 있더라도 일반적으로 `object` 형식입니다.

 "EventArgs" 접미사를 사용 하 여 이벤트 인수 클래스의 이름을 ✔️ 합니다.

## <a name="names-of-fields"></a>필드 이름
 필드 명명 지침은 공용 및 보호된 고정 필드에 적용됩니다. 내부 및 개인 필드는 지침에서 다루지 않고 공용 또는 보호된 인스턴스 필드는 [멤버 디자인 지침](member.md)에서 허용하지 않습니다.

 필드 이름에는 대/소문자 구분을 사용 ✔️ 합니다.

 명사, 명사구 또는 형용사를 사용 하 여 이름 필드를 ✔️ 합니다.

 ❌필드 이름에는 접두사를 사용 하지 마십시오.

 예를 들어 "g_" 또는 "s_"를 사용하여 고정 필드를 나타내지 마십시오.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임 워크 디자인 지침](index.md)
- [명명 지침](naming-guidelines.md)
