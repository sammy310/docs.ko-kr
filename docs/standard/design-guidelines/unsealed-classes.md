---
title: 봉인되지 않은 클래스
ms.date: 10/22/2008
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: b2e14b435aa567f231230da34307014210d46ccb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828519"
---
# <a name="unsealed-classes"></a>봉인되지 않은 클래스
Sealed 클래스는에서 상속 될 수 없으며 확장성을 방지 합니다. 반면에서 상속할 수 있는 클래스는 봉인 되지 않은 클래스 라고 합니다.

 더 저렴 한 방법으로 프레임 워크에 대 한 저렴 한 확장성을 제공 하는 좋은 방법으로 추가 된 가상 또는 보호 된 구성원이 없는 봉인 되지 않은 클래스 사용을 고려 ✔️.

 개발자는 종종 사용자 지정 생성자, 새 메서드 또는 메서드 오버 로드와 같은 편리한 멤버를 추가 하기 위해 봉인 되지 않은 클래스에서 상속 하려고 합니다. 예를 들어  `System.Messaging.MessageQueue` 은 봉인 되지 않으므로 사용자가 특정 큐 경로에 대 한 기본 사용자 지정 큐를 만들거나 특정 시나리오에 대 한 API를 간소화 하는 사용자 지정 메서드를 추가할 수 있습니다.

 대부분의 프로그래밍 언어에서 클래스는 기본적으로 봉인 되지 않으므로 프레임 워크의 대부분의 클래스에 권장 되는 기본값 이기도 합니다. 봉인 되지 않은 형식에서 제공 하는 확장성은 프레임 워크 사용자에 게 많은 감사를 보내고 봉인 되지 않은 형식과 관련 하 여 상대적으로 낮은 테스트 비용으로 인해 제공 하기에 많은 비용이 듭니다

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임 워크 디자인 지침](index.md)
- [확장성을 위한 디자인](designing-for-extensibility.md)
- [봉인](sealing.md)
