---
title: 추상화 구현을 위한 기본 클래스
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
ms.openlocfilehash: 6af63373b7cbb571265f14ac36028953525fcc7f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280571"
---
# <a name="base-classes-for-implementing-abstractions"></a>추상화 구현을 위한 기본 클래스
엄격 하 게 말하면 클래스에서 다른 클래스가 파생 될 때 클래스는 기본 클래스가 됩니다. 그러나이 섹션의 목적을 위해 기본 클래스는 주로 일반적인 추상화를 제공 하거나 상속을 통해 일부 기본 구현을 다시 사용 하기 위해 다른 클래스에 대해 디자인 된 클래스입니다. 일반적으로 기본 클래스는 계층 구조의 루트에 있는 추상화와 아래쪽의 여러 사용자 지정 구현 사이에서 상속 계층의 중간에 있습니다.

 이는 추상화 구현을 위한 구현 도우미 역할을 합니다. 예를 들어 정렬 된 항목 컬렉션에 대 한 프레임 워크의 추상화 중 하나는 <xref:System.Collections.Generic.IList%601> 인터페이스입니다. 구현은 <xref:System.Collections.Generic.IList%601> 간단 하지 않으므로 프레임 워크는 <xref:System.Collections.ObjectModel.Collection%601> <xref:System.Collections.ObjectModel.KeyedCollection%602> 사용자 지정 컬렉션을 구현 하기 위한 도우미 역할을 하는 및와 같은 여러 기본 클래스를 제공 합니다.

 기본 클래스는 너무 많은 구현을 포함 하는 경향이 있기 때문에 일반적으로 자체적으로 추상화 역할을 하는 데 적합 하지 않습니다. 예를 들어, 기본 클래스에는 제네릭이 아닌 인터페이스를 구현 하는 것 `Collection<T>` 과 관련 된 많은 구현이 포함 되어 있습니다 `IList` (제네릭이 아닌 컬렉션과 통합) 및 해당 필드의 메모리에 저장 된 항목의 컬렉션 이라는 사실에 대 한 것입니다.

 앞에서 설명한 것 처럼 기본 클래스는 추상화를 구현 해야 하는 사용자에 게 귀중 한 도움을 제공할 수 있지만, 동시에 중요 한 책임이 있을 수 있습니다. 이를 통해 노출 영역을 추가 하 고 상속 계층 구조 수준을 높이고 프레임 워크를 개념적으로 복잡 하 게 됩니다. 따라서 기본 클래스는 프레임 워크의 사용자에 게 중요 한 값을 제공 하는 경우에만 사용 해야 합니다. 프레임 워크의 구현자 에게만 값을 제공 하는 경우에는 피해 야 합니다 .이 경우 기본 클래스에서 상속 하는 대신 내부 구현에 대 한 위임은 강력 하 게 고려 되어야 합니다.

 추상 멤버를 포함 하지 않는 경우에도 기본 클래스를 추상으로 만드는 것이 좋습니다. ✔️ 이는 클래스가 상속을 위해서만 디자인 된 사용자와 명확 하 게 통신 합니다.

 기본 클래스를 주요 시나리오 형식과 다른 네임 스페이스에 배치 하는 것이 좋습니다 ✔️. 정의에 따라 기본 클래스는 고급 확장성 시나리오를 위한 것 이므로 대부분의 사용자에 게는 유용 하지 않습니다.

 ❌클래스가 공용 Api에서 사용 되는 경우 "Base" 접미사를 사용 하 여 기본 클래스의 이름을 지정 하지 마십시오.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임 워크 디자인 지침](index.md)
- [확장성을 위한 디자인](designing-for-extensibility.md)
