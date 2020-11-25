---
title: 확장 메서드
ms.date: 10/22/2008
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
ms.openlocfilehash: 02a421c9a4b73c779474a392e77104d4ccfbb109
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734714"
---
# <a name="extension-methods"></a>확장 메서드

확장 메서드는 인스턴스 메서드 호출 구문을 사용 하 여 정적 메서드를 호출할 수 있도록 하는 언어 기능입니다. 이러한 메서드는 메서드가 작동 하는 인스턴스를 나타내는 매개 변수를 하나 이상 사용 해야 합니다.

 이러한 확장 메서드를 정의 하는 클래스를 "스폰서" 클래스 라고 하며 정적으로 선언 해야 합니다. 확장 메서드를 사용 하려면 스폰서 클래스를 정의 하는 네임 스페이스를 가져와야 합니다.

 ❌ 특히 소유 하지 않는 형식에 대 한 확장 메서드를 정의 하는 frivolously을 피합니다.

 형식의 소스 코드를 소유 하는 경우 대신 일반 인스턴스 메서드를 사용 하는 것이 좋습니다. 소유 하 고 있지 않은 경우에는 메서드를 추가 하는 것이 좋습니다. 확장 메서드를 자유롭게 사용 하면 이러한 메서드를 사용 하도록 설계 되지 않은 복잡 한 형식의 Api가 발생할 수 있습니다.

 다음 시나리오에서는 확장 메서드를 사용 하는 것이 좋습니다 ✔️.

- 인터페이스의 모든 구현과 관련 된 도우미 기능을 제공 하려는 경우 핵심 인터페이스를 기준으로 기능을 작성할 수 있습니다. 구체적 구현은 인터페이스에 할당할 수 없기 때문입니다. 예를 들어 `LINQ to Objects` 연산자는 모든 형식에 대해 확장 메서드로 구현 됩니다 <xref:System.Collections.Generic.IEnumerable%601> . 따라서 모든 `IEnumerable<>` 구현은 자동으로 LINQ를 사용 하도록 설정 됩니다.

- 인스턴스 메서드가 일부 형식에 대 한 종속성을 도입할 때 이러한 종속성은 종속성 관리 규칙을 중단 합니다. 예를 들어에서로의 <xref:System.String> 종속성 <xref:System.Uri?displayProperty=nameWithType> 이 바람직하지 않을 수 있으므로,이를 반환 하는 `String.ToUri()` 인스턴스 메서드는 `System.Uri` 종속성 관리 관점에서 잘못 된 디자인입니다. 을 반환 하는 정적 확장 메서드는 `Uri.ToUri(this string str)` `System.Uri` 훨씬 더 나은 디자인입니다.

 ❌ 에 확장 메서드를 정의 하지 마십시오 <xref:System.Object?displayProperty=nameWithType> .

 VB 사용자는 확장 메서드 구문을 사용 하 여 개체 참조에서 이러한 메서드를 호출할 수 없습니다. VB에서 참조를 개체로 선언 하면 런타임에 바인딩된 (실제 멤버는 런타임에 결정 됨), 확장명 메서드에 대 한 바인딩은 컴파일 시간 (초기 바인딩)에서 결정 되기 때문에 이러한 메서드 호출은 지원 되지 않습니다.

 이 지침은 동일한 바인딩 동작이 있는 다른 언어나 확장 메서드가 지원 되지 않는 경우에 적용 됩니다.

 ❌ 인터페이스에 메서드를 추가 하거나 종속성을 관리 하는 경우를 제외 하 고 확장 형식과 동일한 네임 스페이스에 확장 메서드를 배치 하지 마십시오.

 ❌ 서로 다른 네임 스페이스에 있는 경우에도 동일한 서명으로 두 개 이상의 확장 메서드를 정의 하지 마십시오.

 형식이 인터페이스인 경우 확장 형식과 동일한 네임 스페이스에 확장 메서드를 정의 하는 것이 좋습니다. 대부분의 경우 또는 모든 경우에 확장 메서드를 사용 하려는 경우에 ✔️ 합니다.

 ❌ 일반적으로 다른 기능과 연결 된 네임 스페이스의 기능을 구현 하는 확장 메서드를 정의 하지 마세요. 대신 자신이 속한 기능과 연결 된 네임 스페이스에서 정의 합니다.

 ❌ 확장 메서드 (예: "확장")에 전용으로 사용 되는 네임 스페이스의 일반적인 이름을 지정 하지 마십시오. 대신 설명이 포함 된 이름 (예: "라우팅")을 사용 합니다.

 *&copy;2005 부분, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참조

- [멤버 디자인 지침](member.md)
- [프레임 워크 디자인 지침](index.md)
