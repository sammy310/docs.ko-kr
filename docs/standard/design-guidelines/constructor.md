---
description: '자세한 정보: 생성자 디자인'
title: 생성자 디자인
ms.date: 10/22/2008
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
ms.openlocfilehash: 2a5c85e1dea3349f897c24fa5d40d73c6e1f9d7f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642320"
---
# <a name="constructor-design"></a>생성자 디자인

형식 생성자와 인스턴스 생성자라는 두 종류의 생성자가 있습니다.

형식 생성자는 정적이며 형식을 사용하기 전에 CLR에서 실행됩니다. 인스턴스 생성자는 형식의 인스턴스를 만들 때 실행됩니다.

형식 생성자는 매개 변수를 사용할 수 없으며, 인스턴스 생성자는 사용할 수 있습니다. 매개 변수를 사용하지 않는 인스턴스 생성자를 종종 매개 변수가 없는 생성자라고 합니다.

생성자는 형식의 인스턴스를 만드는 가장 일반적인 방법입니다. 대부분의 개발자는 인스턴스를 만드는 다른 방법(예: 팩터리 메서드)을 고려하기 전에 생성자를 검색하고 사용하려고 합니다.

✔️ 간단한 생성자, 이상적으로는 기본 생성자를 제공하는 것이 좋습니다.

간단한 생성자에는 매우 적은 수의 매개 변수가 있으며, 모든 매개 변수는 기본 형식 또는 열거형입니다. 이러한 간단한 생성자는 프레임워크의 유용성을 향상합니다.

✔️ 원하는 작업의 의미 체계가 새 인스턴스 생성에 직접 매핑되지 않거나 생성자 디자인 지침 수행이 일반적이지 않은 경우 생성자 대신 정적 팩터리 메서드를 사용하는 것이 좋습니다.

✔️ 생성자 매개 변수를 주요 속성 설정의 바로 가기로 사용하세요.

빈 생성자를 사용한 다음 일부 속성 세트를 사용하는 경우와 여러 인수가 있는 생성자를 사용하는 경우 의미 체계에 차이가 없어야 합니다.

✔️ 생성자 매개 변수가 단순히 속성을 설정하는 데 사용되는 경우 생성자 매개 변수와 속성에 동일한 이름을 사용하세요.

이러한 매개 변수와 속성의 유일한 차이점은 대/소문자를 구분해야 한다는 점입니다.

✔️ 생성자에서 최소한의 작업만 수행하세요.

생성자는 생성자 매개 변수를 캡처하는 것 외에 많은 작업을 수행하면 안 됩니다. 다른 모든 처리 비용이 필요할 때까지 지연됩니다.

✔️ 해당되는 경우 인스턴스 생성자에서 예외를 throw하세요.

✔️ 매개 변수가 없는 퍼블릭 생성자가 필요한 경우 클래스에서 이러한 생성자를 명시적으로 선언하세요.

형식에 대해 생성자를 명시적으로 선언하지 않으면 많은 언어(예: C#)에서 매개 변수가 없는 퍼블릭 생성자를 자동으로 추가합니다. 추상 클래스는 보호된 생성자를 가져옵니다.

매개 변수가 있는 생성자를 클래스에 추가하면 컴파일러에서 매개 변수가 없는 생성자를 추가할 수 없습니다. 따라서 호환성이 손상되는 변경이 실수로 발생하는 경우가 종종 있습니다.

❌ 구조체에서 매개 변수가 없는 생성자를 명시적으로 정의하면 안 됩니다.

매개 변수가 없는 생성자를 정의하지 않으면 배열의 모든 슬롯에서 실행할 필요가 없기 때문에 배열을 더 빠르게 만들 수 있습니다. 이러한 이유로 C#을 포함한 많은 컴파일러에서는 구조체에 매개 변수가 없는 생성자를 사용할 수 없습니다.

❌ 생성자 내의 개체에서 가상 멤버를 호출하면 안 됩니다.

가상 멤버를 호출하면 가장 많이 파생된 형식의 생성자가 완전히 실행되지 않은 경우에도 가장 많이 파생된 재정의가 호출됩니다.

## <a name="type-constructor-guidelines"></a>형식 생성자 지침

✔️ 정적 생성자를 프라이빗으로 설정하세요.

클래스 생성자라고도 하는 정적 생성자는 형식을 초기화하는 데 사용됩니다. CLR은 형식의 첫 번째 인스턴스가 만들어지거나 해당 형식에서 정적 멤버가 호출되기 전에 정적 생성자를 호출합니다. 사용자는 정적 생성자가 호출되는 시기를 제어할 수 없습니다. 정적 생성자가 프라이빗이 아닌 경우 CLR 이외의 코드에서 호출할 수 있습니다. 따라서 생성자에서 수행된 작업에 따라 예기치 않은 동작이 발생할 수 있습니다. C# 컴파일러는 강제로 정적 생성자를 프라이빗으로 설정합니다.

❌ 정적 생성자에서 예외를 throw하지 마세요.

형식 생성자에서 예외가 throw되는 경우 현재 애플리케이션 도메인에서 형식을 사용할 수 없습니다.

✔️ 런타임은 정적 생성자를 명시적으로 정의하지 않은 형식의 성능을 최적화할 수 있으므로 정적 생성자를 명시적으로 사용하는 대신 정적 필드를 인라인으로 초기화하는 것이 좋습니다.

*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [멤버 디자인 지침](member.md)
- [프레임워크 디자인 지침](index.md)
