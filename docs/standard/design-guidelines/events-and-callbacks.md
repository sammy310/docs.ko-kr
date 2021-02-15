---
description: '자세한 정보: 이벤트 및 콜백'
title: 이벤트 및 콜백
ms.date: 10/22/2008
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
ms.openlocfilehash: 8a9049808ec0f7a490889ab1f17c4d8b8e8bd2b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642151"
---
# <a name="events-and-callbacks"></a>이벤트 및 콜백

콜백은 프레임워크가 대리자를 통해 사용자 코드를 다시 호출할 수 있도록 하는 확장 포인트입니다. 이러한 대리자는 일반적으로 메서드의 매개 변수를 통해 프레임워크에 전달됩니다.

 이벤트는 대리자(이벤트 처리기)를 제공하기 위한 편리하고 일관된 구문을 지원하는 콜백의 특수한 경우입니다. 또한 Visual Studio의 문 완성 및 디자이너는 이벤트 기반 API 사용에 대한 도움말을 제공합니다. [이벤트 디자인](event.md)을 참조하세요.

 ✔️ 사용자가 프레임워크에서 실행할 사용자 지정 코드를 제공할 수 있도록 하려면 콜백을 사용하는 것이 좋습니다.

 ✔️ 사용자가 개체 지향 디자인을 이해할 필요 없이 프레임워크의 동작을 사용자 지정할 수 있도록 하려면 이벤트를 사용하는 것이 좋습니다.

 ✔️ 이벤트가 더욱 광범위한 개발자에게 더 익숙하고 Visual Studio 문 완성과 통합되어 있으므로 일반 콜백보다 이벤트를 사용하세요.

 ❌ 성능이 중요한 API에서는 콜백을 사용하면 안 됩니다.

 ✔️ 콜백으로 API를 정의할 때는 사용자 지정 대리자 대신 새로운 `Func<...>`, `Action<...>` 또는 `Expression<...>` 형식을 사용하세요.

 `Func<...>` 및 `Action<...>`은 제네릭 대리자를 나타냅니다. `Expression<...>`은 컴파일한 후 런타임에 호출할 수 있고 직렬화하여 원격 프로세스에 전달할 수도 있는 함수 정의를 나타냅니다.

 ✔️ `Func<...>` 및 `Action<...>` 대리자를 사용하는 대신 `Expression<...>`을 사용할 때 성능에 미치는 영향을 측정하고 이해하세요.

 대부분의 경우 `Expression<...>` 형식은 `Func<...>` 및 `Action<...>` 대리자와 논리적으로 동일합니다. 둘의 주요 차이점은 대리자는 로컬 프로세스 시나리오에서 사용하기 위한 것이며, 식은 원격 프로세스나 머신에서 식을 평가하는 것이 유용하고 가능한 경우를 위한 것이라는 점입니다.

 ✔️ 대리자를 호출하면 임의 코드를 실행하는 것이며 보안, 정확성, 호환성에 영향을 줄 수 있다는 점을 이해하세요.

 *Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [확장성을 위한 디자인](designing-for-extensibility.md)
- [프레임워크 디자인 지침](index.md)
