---
title: 추상화 구현을 위한 기본 클래스
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
ms.openlocfilehash: af62658ce728dd480df630cf6162549f33f28b4d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709545"
---
# <a name="base-classes-for-implementing-abstractions"></a>추상화 구현을 위한 기본 클래스
엄격 하 게 말하면 클래스에서 다른 클래스가 파생 될 때 클래스는 기본 클래스가 됩니다. 그러나이 섹션의 목적을 위해 기본 클래스는 주로 일반적인 추상화를 제공 하거나 상속을 통해 일부 기본 구현을 다시 사용 하기 위해 다른 클래스에 대해 디자인 된 클래스입니다. 일반적으로 기본 클래스는 계층 구조의 루트에 있는 추상화와 아래쪽의 여러 사용자 지정 구현 사이에서 상속 계층의 중간에 있습니다.  
  
 이는 추상화 구현을 위한 구현 도우미 역할을 합니다. 예를 들어, 순서가 지정 된 항목 컬렉션에 대 한 프레임 워크의 추상화 중 하나는 <xref:System.Collections.Generic.IList%601> 인터페이스입니다. <xref:System.Collections.Generic.IList%601>를 구현 하는 것은 간단 하지 않으므로 프레임 워크는 사용자 지정 컬렉션을 구현 하기 위한 도우미 역할을 하는 <xref:System.Collections.ObjectModel.Collection%601> 및 <xref:System.Collections.ObjectModel.KeyedCollection%602>와 같은 몇 가지 기본 클래스를 제공 합니다.  
  
 기본 클래스는 너무 많은 구현을 포함 하는 경향이 있기 때문에 일반적으로 자체적으로 추상화 역할을 하는 데 적합 하지 않습니다. 예를 들어 `Collection<T>` 기본 클래스에는 제네릭이 아닌 `IList` 인터페이스를 구현 하는 것과 관련 된 많은 구현이 포함 되어 있습니다 (제네릭이 아닌 컬렉션과 통합 하기 위해). 또한이 클래스는 해당 필드 중 하나에서 메모리에 저장 된 항목의 컬렉션 이라는 사실에 해당 합니다.  
  
 앞에서 설명한 것 처럼 기본 클래스는 추상화를 구현 해야 하는 사용자에 게 귀중 한 도움을 제공할 수 있지만, 동시에 중요 한 책임이 있을 수 있습니다. 이를 통해 노출 영역을 추가 하 고 상속 계층 구조 수준을 높이고 프레임 워크를 개념적으로 복잡 하 게 됩니다. 따라서 기본 클래스는 프레임 워크의 사용자에 게 중요 한 값을 제공 하는 경우에만 사용 해야 합니다. 프레임 워크의 구현자 에게만 값을 제공 하는 경우에는 피해 야 합니다 .이 경우 기본 클래스에서 상속 하는 대신 내부 구현에 대 한 위임은 강력 하 게 고려 되어야 합니다.  
  
 **✓ CONSIDER** 함으로써 기본 추상 멤버가 포함 하지 않는 경우에 추상 클래스입니다. 이는 클래스가 상속을 위해서만 디자인 된 사용자와 명확 하 게 통신 합니다.  
  
 **✓ CONSIDER** 주요 시나리오 형식에서 별도 네임 스페이스에 기본 클래스를 배치 합니다. 정의에 따라 기본 클래스는 고급 확장성 시나리오를 위한 것 이므로 대부분의 사용자에 게는 유용 하지 않습니다.  
  
 **X AVOID** 클래스가 공용 Api에서 사용 하기 위한 경우 "기본" 접미사를 사용 하 여 기본 클래스 이름을 지정 합니다.  
  
 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*  
  
 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>참조

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
