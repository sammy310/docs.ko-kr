---
description: '자세한 정보: 보호된 멤버'
title: 보호된 멤버
ms.date: 10/22/2008
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
ms.openlocfilehash: 5860828a5a469c77fbee001d01460a488fda4edf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731762"
---
# <a name="protected-members"></a>보호된 멤버

보호된 멤버는 그 자체로 확장성을 제공하지 않지만 서브클래스를 통해 확장성을 더 강력하게 만들 수 있습니다. 보호된 멤버를 사용하면 기본 퍼블릭 인터페이스를 쓸데없이 복잡하게 만들지 않고도 고급 사용자 지정 옵션을 노출할 수 있습니다.

 “보호된”이라는 이름이 잘못된 보안의 의미를 제공할 수 있기 때문에 프레임워크 디자이너에서 보호된 멤버를 사용할 때는 주의해야 합니다. 누구나 봉인되지 않은 클래스를 서브클래싱하고 보호된 멤버에 액세스할 수 있으므로 퍼블릭 멤버에 사용되는 모든 동일한 방어적인 코딩 방식이 보호된 멤버에 적용됩니다.

 ✔️ 고급 사용자 지정에는 보호된 멤버를 사용하는 것이 좋습니다.

 ✔️ 보안, 문서화, 호환성 분석을 위해 봉인되지 않은 클래스의 보호된 멤버를 퍼블릭으로 처리하세요.

 누구나 클래스에서 상속하고 보호된 멤버에 액세스할 수 있습니다.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](index.md)
- [확장성을 위한 디자인](designing-for-extensibility.md)
