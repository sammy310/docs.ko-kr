---
title: 확장성을 위한 디자인
ms.date: 10/22/2008
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 9e75ef433f3bd9af34e8dd40331a8267755e59fe
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821387"
---
# <a name="designing-for-extensibility"></a>확장성을 위한 디자인
프레임 워크를 설계할 때 중요 한 한 가지 측면은 프레임 워크의 확장성을 신중 하 게 고려 하는 것입니다. 이렇게 하려면 다양 한 확장성 메커니즘과 관련 된 비용 및 혜택을 이해 해야 합니다. 이 장은 프레임 워크의 요구 사항을 가장 잘 충족할 수 있는 하위 클래스, 이벤트, 가상 멤버, 콜백 등의 확장성 메커니즘을 결정 하는 데 도움이 됩니다.  
  
 여러 가지 방법으로 프레임 워크에서 확장성을 허용할 수 있습니다. 강력 하지만 비용이 저렴 하지만 매우 강력 하지만 비용이 저렴 합니다. 지정 된 확장성 요구 사항에 대 한 요구 사항을 충족 하는 최소 비용 확장성 메커니즘을 선택 해야 합니다. 일반적으로 나중에 확장성을 더 추가할 수 있지만, 주요 변경 사항을 도입 하지 않고 다시 사용할 수는 없습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [봉인 되지 않은 클래스](unsealed-classes.md)  
 [보호 된 멤버](protected-members.md)  
 [이벤트 및 콜백](events-and-callbacks.md)  
 [가상 멤버](virtual-members.md)  
 [추상화 (추상 형식 및 인터페이스)](abstractions-abstract-types-and-interfaces.md)  
 [추상화 구현을 위한 기본 클래스](base-classes-for-implementing-abstractions.md)  
 [봉인](sealing.md)  
 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*  
  
 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>참고 항목

- [프레임 워크 디자인 지침](index.md)
