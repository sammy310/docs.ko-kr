---
description: '자세한 정보: 추상화 구현을 위한 기본 클래스'
title: 추상화 구현을 위한 기본 클래스
ms.date: 10/22/2008
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
ms.openlocfilehash: 255891695583e36977663153b0ccac98b7fff4c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642346"
---
# <a name="base-classes-for-implementing-abstractions"></a>추상화 구현을 위한 기본 클래스

엄격한 의미에서 다른 클래스가 파생되는 클래스가 기본 클래스가 됩니다. 그러나 이 섹션에서 기본 클래스는 주로 일반적인 추상화를 제공하도록 설계된 클래스 또는 다른 클래스가 상속을 통해 일부 기본 구현을 다시 사용하도록 설계된 클래스입니다. 일반적으로 기본 클래스는 상속 계층 구조의 중간 즉, 계층 구조의 루트에 있는 추상화와 아래쪽에 있는 여러 사용자 지정 구현 사이에 있습니다.

 기본 클래스는 추상화 구현을 위한 구현 도우미 역할을 합니다. 예를 들어 순서가 지정된 항목 컬렉션에 대한 프레임워크의 추상화 중 하나는 <xref:System.Collections.Generic.IList%601> 인터페이스입니다. <xref:System.Collections.Generic.IList%601> 구현은 간단하지 않으므로 프레임워크는 사용자 지정 컬렉션 구현의 도우미 역할을 하는 여러 가지 기본 클래스(예: <xref:System.Collections.ObjectModel.Collection%601> 및 <xref:System.Collections.ObjectModel.KeyedCollection%602>)를 제공합니다.

 기본 클래스는 너무 많은 구현을 포함하는 경향이 있기 때문에 일반적으로 그 자체로 추상화 역할을 하는 데 적합하지 않습니다. 예를 들어 `Collection<T>` 기본 클래스는 제네릭이 아닌 `IList` 인터페이스를 구현하여 제네릭이 아닌 컬렉션과 더 잘 통합된다는 사실 및 해당 필드 중 하나의 메모리에 저장된 항목 컬렉션이라는 사실과 관련된 많은 구현을 포함합니다.

 앞에서 설명한 대로 기본 클래스는 추상화를 구현해야 하는 사용자에게 유용한 도움을 제공할 수 있지만 동시에 중요한 책임을 질 수도 있습니다. 기본 클래스는 노출 영역을 추가하고 상속 계층 구조의 깊이를 늘리므로 개념적으로 프레임워크가 복잡해집니다. 따라서 기본 클래스는 프레임워크의 사용자에게 중요한 가치를 제공하는 경우에만 사용해야 합니다. 프레임워크의 구현자에게 값만 제공하는 경우에는 사용하면 안 됩니다. 이런 경우 기본 클래스의 상속 대신 내부 구현에 대한 위임을 사용하는 것이 가장 좋습니다.

 ✔️ 추상 멤버를 포함하지 않는 경우에도 기본 클래스를 추상으로 설정하는 것이 좋습니다. 그러면 클래스가 상속을 위해서만 설계되었다는 점이 사용자에게 명확히 전달됩니다.

 ✔️ 주요 시나리오 유형과 다른 별도의 네임스페이스에 기본 클래스를 배치하는 것이 좋습니다. 정의에 따라 기본 클래스는 고급 확장성 시나리오에 사용되므로 대다수 사용자에게 흥미롭지 않습니다.

 ❌ 클래스가 퍼블릭 API에서 사용하게 되어 있는 경우 “Base” 접미사를 사용하여 기본 클래스의 이름을 지정하면 안 됩니다.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](index.md)
- [확장성을 위한 디자인](designing-for-extensibility.md)
