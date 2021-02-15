---
description: '자세한 정보: 중첩 형식'
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
ms.openlocfilehash: 07d81827d67e50351f442ec15ca6cb18a63160fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713379"
---
# <a name="nested-types"></a>중첩 형식

중첩 형식은 바깥쪽 형식이라는 다른 형식의 범위 내에 정의된 형식입니다. 중첩 형식은 바깥쪽 형식의 모든 멤버에 액세스할 수 있습니다. 예를 들어 바깥쪽 형식에 정의된 프라이빗 필드와 바깥쪽 형식의 모든 상위 항목에 정의된 보호된 필드에 액세스할 수 있습니다.

 일반적으로 중첩 형식은 필요한 경우에만 사용해야 합니다. 여기에는 여러 가지 이유가 있습니다. 일부 개발자는 개념을 충분히 이해하지 못합니다. 예를 들어 이러한 개발자는 중첩 형식의 변수를 선언하는 구문에서 문제를 느낄 수 있습니다. 또한 중첩 형식은 바깥쪽 형식과 매우 긴밀하게 결합되어 있으므로 범용 형식에 적합하지 않습니다.

 중첩 형식은 바깥쪽 형식의 구현 세부 정보를 모델링하는 데 가장 적합합니다. 최종 사용자는 중첩 형식의 변수를 거의 선언할 필요가 없으며 중첩 형식을 명시적으로 인스턴스화할 필요도 없습니다. 예를 들어 컬렉션의 열거자는 해당 컬렉션의 중첩 형식일 수 있습니다. 일반적으로 열거자는 바깥쪽 형식에 의해 인스턴스화되며, 대부분의 언어에서 foreach 문을 지원하기 때문에 최종 사용자가 열거자 변수를 선언해야 하는 경우가 거의 없습니다.

 ✔️ 중첩 형식과 외부 형식 간 관계가 멤버 접근성 의미 체계처럼 바람직한 경우 중첩 형식을 사용하세요.

 ❌ 퍼블릭 중첩 형식을 논리적 그룹화 생성자로 사용하지 마세요. 대신 네임스페이스를 사용하세요.

 ❌ 공개적으로 노출된 중첩 형식을 사용하면 안 됩니다. 단, 중첩 형식의 변수를 서브클래싱 또는 다른 고급 사용자 지정 시나리오 같은 드문 시나리오에서만 선언해야 하는 경우는 예외입니다.

 ❌ 형식이 포함하는 형식 외부에서 참조될 가능성이 있는 경우 중첩 형식을 사용하지 마세요.

 예를 들어 클래스에 정의된 메서드에 전달된 열거형은 클래스에서 중첩 형식으로 정의할 수 없습니다.

 ❌ 클라이언트 코드에서 인스턴스화해야 하는 경우 중첩 형식을 사용하지 마세요.  형식에 퍼블릭 생성자가 있는 경우 중첩할 수 없습니다.

 형식을 인스턴스화할 수 있는 경우 형식이 프레임워크에 자체적으로 배치(외부 형식을 사용하지 않고 만들고, 사용하고, 제거할 수 있음)되는 것처럼 보이므로 중첩할 수 없습니다. 내부 형식은 외부 형식에 대한 관계가 없으면 외부 형식의 외부에서 광범위하게 다시 사용할 수 없습니다.

 ❌ 중첩 형식을 인터페이스의 멤버로 정의하지 마세요. 대부분의 언어에서 이러한 구문을 지원하지 않습니다.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [형식 디자인 지침](type.md)
- [프레임워크 디자인 지침](index.md)
