---
title: 생성자 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
ms.openlocfilehash: 7ab795cd4c6e0ff5e1451c05987848c41bd69577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401246"
---
# <a name="constructor-design"></a>생성자 디자인

생성자는 형식 생성자와 인스턴스 생성자의 두 가지 종류가 있습니다.

형식 생성자는 정적이며 형식을 사용하기 전에 CLR에서 실행됩니다. 인스턴스 생성자는 형식의 인스턴스가 만들어질 때 실행됩니다.

형식 생성자는 매개 변수를 취할 수 없습니다. 인스턴스 생성자는 할 수 있습니다. 매개 변수를 수행하지 않는 인스턴스 생성자는 매개 변수 없는 생성자라고도 합니다.

생성자는 형식의 인스턴스를 만드는 가장 자연스러운 방법입니다. 대부분의 개발자는 인스턴스를 만드는 다른 방법(예: 팩터리 메서드)을 고려하기 전에 생성기를 검색하고 사용하려고 합니다.

✔️ 간단하고 이상적으로 기본 생성자 제공을 고려하십시오.

간단한 생성자는 매우 적은 수의 매개 변수를 가지며 모든 매개 변수는 기본 또는 열거형입니다. 이러한 간단한 생성자는 프레임워크의 유용성을 높입니다.

✔️ 원하는 작업의 의미 체계가 새 인스턴스의 구성에 직접 매핑되지 않거나 생성자 설계 지침을 따르는 경우 생성자 대신 정적 팩터리 메서드를 사용하는 것이 좋습니다.

✔️ do는 생성자 매개 변수를 기본 속성을 설정하기 위한 바로 가프로 사용합니다.

빈 생성자 뒤에 일부 속성 집합을 사용 하 여 여러 인수와 생성자 사용 사이 의미 체계에 차이가 없어야 합니다.

✔️ 생성자 매개 변수를 단순히 속성을 설정 하는 데 사용 하는 경우 생성자 매개 변수 및 속성에 대 한 동일한 이름을 사용 합니다.

이러한 매개 변수와 속성 간의 유일한 차이점은 대/소문자여야 합니다.

✔️ 생성자에서 최소한의 작업을 수행합니다.

생성자는 생성자 매개 변수를 캡처하는 것 외에는 많은 작업을 수행하지 않아야 합니다. 다른 처리 비용은 필요할 때까지 지연되어야 합니다.

✔️ 적절한 경우 인스턴스 생성자에서 예외를 throw합니다.

✔️ 이러한 생성자가 필요한 경우 클래스에서 public 매개 변수 없는 생성자임을 명시적으로 선언합니다.

형식에 대한 생성자도 명시적으로 선언하지 않으면 많은 언어(예: C#)가 자동으로 public 매개 변수 없는 생성자가 추가됩니다. (추상 클래스는 보호된 생성자입니다.)

클래스에 매개 변수화된 생성자를 추가하면 컴파일러가 매개 변수 없는 생성자를 추가할 수 없습니다. 이로 인해 우발적인 주요 변경 사항이 발생하는 경우가 많습니다.

❌구조체에서 매개 변수 없는 생성자정의를 명시적으로 정의하지 마십시오.

이렇게 하면 매개 변수 없는 생성자가 정의되지 않은 경우 배열의 모든 슬롯에서 실행할 필요가 없으므로 배열 생성 속도가 빨라집니다. C#을 포함한 많은 컴파일러에는 이러한 이유로 구조체에 매개 변수 없는 생성자가 있는 것을 허용하지 않습니다.

❌생성자 내부의 개체에서 가상 멤버를 호출하지 마십시오.

가상 멤버를 호출하면 가장 파생된 형식의 생성자가 아직 완전히 실행되지 않은 경우에도 가장 많이 파생된 재정의가 호출됩니다.

## <a name="type-constructor-guidelines"></a>유형 생성자 지침

✔️ 정적 생성자 개인으로 만듭니다.

클래스 생성자라고도 하는 정적 생성자는 형식을 초기화하는 데 사용됩니다. CLR은 형식의 첫 번째 인스턴스가 만들어지거나 해당 형식의 정적 멤버가 호출되기 전에 정적 생성자를 호출합니다. 정적 생성자가 호출되는 시기를 사용자가 제어할 수 없습니다. 정적 생성자가 개인적이지 않은 경우 CLR 이외의 코드에서 호출할 수 있습니다. 생성자에서 수행되는 작업에 따라 예기치 않은 동작이 발생할 수 있습니다. C# 컴파일러는 정적 생성자를 비공개로 강제합니다.

❌정적 생성자에서 예외를 throw하지 마십시오.

형식 생성자에서 예외가 throw된 경우 현재 응용 프로그램 도메인에서 형식을 사용할 수 없습니다.

✔️ 런타임은 명시적으로 정의된 정적 생성자가 없는 형식의 성능을 최적화할 수 있기 때문에 정적 생성기를 명시적으로 사용하는 대신 인라인으로 정적 필드를 초기화하는 것을 고려합니다.

*2005년, 2009년 마이크로소프트© 판권.*

*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)
- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
