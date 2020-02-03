---
title: 가상 멤버
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 8ed519a01162056151d8ae6398c0d06495911afd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743533"
---
# <a name="virtual-members"></a>가상 멤버
가상 멤버를 재정의할 수 있으므로 하위 클래스의 동작을 변경할 수 있습니다. 이러한 항목은 제공 하는 확장성 측면에서 콜백과 매우 유사 하지만 실행 성능과 메모리 사용 측면에서 더 효율적입니다. 또한 가상 멤버는 특수 한 종류의 기존 형식 (특수화)을 만들어야 하는 시나리오에서 보다 자연스럽 게 느껴질 수 있습니다.

 가상 멤버는 콜백과 이벤트 보다 성능이 우수 하지만 비가상 메서드 보다는 성능이 더 우수 하지 않습니다.

 가상 멤버의 주요 단점은 컴파일할 때 가상 멤버의 동작을 수정할 수 있다는 것입니다. 콜백의 동작은 런타임에 수정할 수 있습니다.

 가상 멤버에 대 한 모든 호출은 예측할 수 없는 방식으로 재정의 될 수 있고 임의의 코드를 실행할 수 있기 때문에 콜백과 같은 가상 멤버는 디자인, 테스트 및 유지 관리 비용이 많이 듭니다. 또한 일반적으로 가상 멤버의 계약을 명확 하 게 정의 하는 데 더 많은 노력을 기울여야 하므로 이러한 작업을 디자인 하 고 문서화 하는 비용이 더 높습니다.

 이 작업을 수행 하는 데 적절 한 이유가 없는 한 구성원을 가상으로 만들지 말고 가상 멤버의 디자인, 테스트 및 유지 관리와 관련 된 모든 비용을 알고 ❌.

 가상 멤버는 호환성을 손상 시 키 지 않고 변경 내용을 적용할 수 있는 측면에서 더 낮습니다. 또한 가상 멤버에 대 한 호출은 인라인 되지 않으므로 가상 멤버가 아닌 멤버 보다 속도가 느립니다.

 ✔️ 확장성을 반드시 필요한 것 으로만 제한 하는 것이 좋습니다.

 가상 멤버에 대 한 공용 액세스 가능성을 통해 보호 된 접근성을 선호 하는 ✔️. Public 멤버는 보호 된 가상 멤버를 호출 하 여 확장성 (필요한 경우)을 제공 해야 합니다.

 클래스의 public 멤버는 해당 클래스의 직접 소비자에 게 올바른 기능 집합을 제공 해야 합니다. 가상 멤버는 서브 클래스에서 재정의 되도록 설계 되었으며, 보호 된 액세스 가능성은 모든 가상 확장 지점을 사용할 수 있는 위치로 범위를 지정할 수 있는 좋은 방법입니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
