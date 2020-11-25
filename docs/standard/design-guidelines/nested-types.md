---
title: 중첩 형식
ms.date: 10/22/2008
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
ms.openlocfilehash: bc0aee32b5cc1d40afdd9cce8260d5b5341a687d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706400"
---
# <a name="nested-types"></a>중첩 형식

중첩 형식은 바깥쪽 형식 이라고 하는 다른 형식의 범위 내에 정의 된 형식입니다. 중첩 형식에는 바깥쪽 형식의 모든 멤버에 대 한 액세스 권한이 있습니다. 예를 들어 바깥쪽 형식에 정의 된 private 필드와 바깥쪽 형식의 모든 상위 항목에 정의 된 보호 된 필드에 액세스할 수 있습니다.

 일반적으로 중첩 형식은 자주 사용 해야 합니다. 여기에는 여러 가지 이유가 있습니다. 일부 개발자는 이러한 개념을 완벽 하 게 알지 못합니다. 예를 들어 이러한 개발자는 중첩 형식의 변수를 선언 하는 구문에 문제가 있을 수 있습니다. 중첩 형식은 바깥쪽 형식과 매우 긴밀 하 게 결합 되어 있으므로 범용 형식에 적합 하지 않습니다.

 중첩 형식은 바깥쪽 형식의 구현 세부 정보를 모델링 하는 데 가장 적합 합니다. 최종 사용자는 중첩 형식의 변수를 선언 하는 것은 거의 필요 하지 않으며 중첩 형식을 명시적으로 인스턴스화할 필요가 없습니다. 예를 들어 컬렉션의 열거자는 해당 컬렉션의 중첩 형식일 수 있습니다. 열거자는 일반적으로 바깥쪽 형식에 의해 인스턴스화되고 많은 언어에서 foreach 문을 지원 하므로 최종 사용자가 열거자 변수를 거의 선언 하지 않아도 됩니다.

 중첩 형식과 해당 외부 형식 사이의 관계를 사용 하 여 멤버 액세스 가능성을 적절 하 게 사용 하는 경우에는 중첩 형식을 사용 ✔️ 합니다.

 ❌ 공용 중첩 형식을 논리적 그룹화 구문으로 사용 하지 마십시오. 이에 대 한 네임 스페이스를 사용 합니다.

 ❌ 공개적으로 노출 된 중첩 형식을 사용 하지 않습니다. 단, 중첩 형식의 변수를 서브클래싱 또는 다른 고급 사용자 지정 시나리오와 같은 드문 시나리오 에서만 선언 해야 하는 경우는 예외입니다.

 ❌ 포함 하는 형식 외부에서 형식을 참조할 가능성이 있는 경우에는 중첩 형식을 사용 하지 마십시오.

 예를 들어 클래스에 정의 된 메서드에 전달 된 열거형은 클래스에서 중첩 형식으로 정의 되어서는 안 됩니다.

 ❌ 클라이언트 코드에서 인스턴스화해야 하는 경우에는 중첩 형식을 사용 하지 마십시오.  형식에 public 생성자가 있는 경우 중첩 되지 않아야 합니다.

 형식을 인스턴스화할 수 있는 경우 형식에 프레임 워크의 위치가 있음을 나타내는 것 처럼 보일 수 있습니다. 즉, 외부 형식을 사용 하지 않고 작업을 만들어 사용 하 고 사용 하 여 제거할 수 있으므로 중첩 되어서는 안 됩니다. 외부 형식에 관계 없이 외부 형식의 외부에서 내부 형식을 널리 재사용 해서는 안 됩니다.

 ❌ 중첩 형식을 인터페이스의 멤버로 정의 하지 마십시오. 많은 언어에서 이러한 구문을 지원 하지 않습니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참조

- [형식 디자인 지침](type.md)
- [프레임 워크 디자인 지침](index.md)
