---
description: '자세한 정보: 확장명 메서드'
title: 확장 메서드
ms.date: 10/22/2008
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
ms.openlocfilehash: 2f71ec86252045687558bd61337164ac3afbcd20
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642060"
---
# <a name="extension-methods"></a>확장 메서드

확장 메서드는 인스턴스 메서드 호출 구문을 사용하여 정적 메서드를 호출할 수 있는 언어 기능입니다. 이러한 메서드는 메서드가 작동해야 하는 인스턴스를 나타내는 매개 변수를 하나 이상 사용해야 합니다.

 이러한 확장 메서드를 정의하는 클래스를 “스폰서” 클래스라고 하며 이 클래스는 정적으로 선언해야 합니다. 확장 메서드를 사용하려면 스폰서 클래스를 정의하는 네임스페이스를 가져와야 합니다.

 ❌ 확장 메서드, 특히 소유하지 않는 형식을 경솔하게 정의하면 안 됩니다.

 형식의 소스 코드를 소유하는 경우 일반적인 인스턴스 메서드를 대신 사용하는 것이 좋습니다. 소유하지 않는 경우 메서드를 추가하려면 매우 주의해야 합니다. 확장 메서드를 자유롭게 사용하면 이러한 메서드를 사용하도록 설계되지 않은 형식의 API가 복잡해질 수 있습니다.

 ✔️ 다음과 같은 시나리오에서는 확장 메서드를 사용하는 것이 좋습니다.

- 모든 인터페이스 구현과 관련된 도우미 기능을 제공하려는 경우 핵심 인터페이스 측면에서 기능을 작성할 수 있습니다. 다른 방법으로는 구체적 구현을 인터페이스에 할당할 수 없기 때문입니다. 예를 들어 `LINQ to Objects` 연산자는 모든 <xref:System.Collections.Generic.IEnumerable%601> 형식에 대해 확장 메서드로 구현됩니다. 따라서 `IEnumerable<>` 구현은 자동으로 LINQ를 지원합니다.

- 인스턴스 메서드가 일부 형식에 대해 종속성을 도입하는데 이러한 종속성이 종속성 관리 규칙을 위반하는 경우입니다. 예를 들어 <xref:System.Uri?displayProperty=nameWithType>에 대한 <xref:System.String>의 종속성은 바람직하지 않을 수 있으므로 `System.Uri`를 반환하는 `String.ToUri()` 인스턴스 메서드는 종속성 관리 관점에서 잘못된 디자인이 됩니다. `System.Uri`를 반환하는 정적 확장 메서드 `Uri.ToUri(this string str)`가 훨씬 더 나은 디자인입니다.

 ❌ <xref:System.Object?displayProperty=nameWithType>에서 확장 메서드를 정의하면 안 됩니다.

 VB 사용자는 확장 메서드 구문을 사용하여 개체 참조에서 이러한 메서드를 호출할 수 없습니다. VB에서 참조를 개체로 선언하면 모든 메서드 호출이 런타임에 바인딩(호출된 실제 멤버가 런타임에 결정)되고 확장 메서드에 대한 바인딩은 컴파일 시간에 결정(초기 바인딩)되므로 VB는 이러한 메서드 호출을 지원하지 않습니다.

 이 지침은 동일한 바인딩 동작이 있거나 확장 메서드가 지원되지 않는 다른 언어에도 적용됩니다.

 ❌ 인터페이스에 메서드를 추가하거나 종속성 관리를 위한 경우가 아니라면 확장 형식과 동일한 네임스페이스에 확장 메서드를 넣지 마세요.

 ❌ 서로 다른 네임스페이스에 있는 경우에도 동일한 시그니처로 둘 이상의 확장 메서드를 정의하면 안 됩니다.

 ✔️ 형식이 인터페이스인 경우와 확장 메서드를 대부분의 경우나 모든 경우에 사용하려는 경우 확장 형식과 동일한 네임스페이스에서 확장 메서드를 정의하는 것이 좋습니다.

 ❌ 일반적으로 다른 기능과 연결된 네임스페이스에서는 기능을 구현하는 확장 메서드를 정의하지 마세요. 대신 확장 메서드가 속한 기능과 연결된 네임스페이스에서 정의하세요.

 ❌ 확장 메서드 전용 네임스페이스의 일반 이름(예: “확장”)을 지정하면 안 됩니다. 대신 설명이 포함된 이름(예: “라우팅”)을 사용하세요.

 *Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [멤버 디자인 지침](member.md)
- [프레임워크 디자인 지침](index.md)
