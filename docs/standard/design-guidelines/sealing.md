---
title: 봉인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
ms.openlocfilehash: ddf463e98fb6a9c5ccaae90e9cfc74b5691b13a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743617"
---
# <a name="sealing"></a>봉인
개체 지향 프레임 워크의 기능 중 하나는 개발자가 프레임 워크 디자이너에서 예기치 않은 방식으로 확장 하 고 사용자 지정할 수 있다는 것입니다. 이는 확장 가능한 디자인의 기능과 위험입니다. 프레임 워크를 설계할 때, 원하는 경우 확장성을 신중 하 게 디자인 하 고, 위험에 따라 확장성을 제한 하는 것이 매우 중요 합니다.

 확장성을 방지 하는 강력한 메커니즘입니다. 클래스 또는 개별 멤버를 봉인할 수 있습니다. 클래스를 봉인 하면 사용자가 클래스에서 상속 하지 않습니다. 멤버를 봉인 하면 사용자가 특정 멤버를 재정의할 수 없습니다.

 이러한 작업을 수행 해야 하는 이유를 제외 하 고 클래스를 봉인 하지 ❌.

 확장성 시나리오를 고려할 수 없기 때문에 클래스를 봉인 하는 것은 좋은 이유가 아닙니다. 편리한 멤버를 추가 하는 등의 다양 한 이유로 클래스에서 상속 하는 것과 같은 프레임 워크 사용자입니다. 사용자가 형식에서 상속 하려는 명백한 이유의 예는 봉인 되지 않은 [클래스](../../../docs/standard/design-guidelines/unsealed-classes.md) 를 참조 하세요.

 클래스를 봉인 하는 좋은 이유는 다음과 같습니다.

- 클래스가 정적 클래스입니다. [정적 클래스 디자인](../../../docs/standard/design-guidelines/static-class.md)을 참조 하세요.

- 클래스는 보안에 중요 한 비밀을 상속 된 protected 멤버에 저장 합니다.

- 클래스는 많은 가상 멤버를 상속 하 고 개별적으로 봉인 하는 비용은 클래스를 봉인 되지 않은 경우의 이점 보다 더 큽니다.

- 클래스는 매우 빠른 런타임 조회를 필요로 하는 특성입니다. 봉인 된 특성의 성능 수준은 봉인 되지 않은 특성 보다 약간 높습니다. [특성](../../../docs/standard/design-guidelines/attributes.md)을 참조 하세요.

 ❌는 sealed 형식에 대해 protected 또는 virtual 멤버를 선언 하지 않습니다.

 정의에 따라 sealed 형식은에서 상속 될 수 없습니다. 이는 sealed 형식의 보호 된 멤버를 호출할 수 없고 sealed 형식의 가상 메서드를 재정의할 수 없음을 의미 합니다.

 재정의 하는 멤버를 봉인 하는 것을 고려 ✔️.

 가상 멤버를 도입할 때 발생할 수 있는 문제 ( [가상 멤버](../../../docs/standard/design-guidelines/virtual-members.md)에 설명 됨)는 약간 낮은 수준 이지만 재정의에도 적용 됩니다. 재정의를 봉인 하면 상속 계층 구조의 해당 지점부터 시작 하 여 이러한 문제를 해결할 수 있습니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참조

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [봉인되지 않은 클래스](../../../docs/standard/design-guidelines/unsealed-classes.md)
