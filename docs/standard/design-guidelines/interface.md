---
title: 인터페이스 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
ms.openlocfilehash: f589d47d5b945179430275598996b2fb77e92848
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289033"
---
# <a name="interface-design"></a>인터페이스 디자인
대부분의 Api는 클래스 및 구조체를 사용 하 여 모델링 하는 것이 좋지만 인터페이스가 더 적합 하거나 유일한 옵션입니다.

 CLR은 다중 상속을 지원 하지 않습니다. 즉, CLR 클래스는 둘 이상의 기본 클래스에서 상속할 수 없지만 기본 클래스에서 상속 하는 것 외에도 형식이 하나 이상의 인터페이스를 구현할 수 있습니다. 따라서 여러 상속의 영향을 얻기 위해 인터페이스가 종종 사용 됩니다. 예를 들어 <xref:System.IDisposable> 는 형식이 참여 하려는 다른 상속 계층 구조와 독립적으로 disposability을 지원할 수 있도록 하는 인터페이스입니다.

 인터페이스를 정의 하는 다른 상황은 일부 값 형식을 포함 하 여 여러 형식에서 지원할 수 있는 공용 인터페이스를 만드는 것입니다. 값 형식은 이외의 형식에서 상속할 수 <xref:System.ValueType> 없지만 인터페이스를 구현할 수 있으므로 공통 기본 형식을 제공 하기 위해 인터페이스를 사용 하는 것이 유일한 옵션입니다.

 값 형식을 포함 하는 형식 집합에서 몇 가지 공통 API를 지원 해야 하는 경우 인터페이스를 정의 ✔️ 합니다.

 다른 형식에서 이미 상속 된 형식에 대해 해당 기능을 지원 해야 하는 경우 인터페이스를 정의 하는 것이 좋습니다. ✔️

 ❌마커 인터페이스 (멤버가 없는 인터페이스)를 사용 하지 마십시오.

 클래스를 특정 특성 (표식)으로 표시 해야 하는 경우 일반적으로 인터페이스가 아닌 사용자 지정 특성을 사용 합니다.

 인터페이스를 구현 하는 하나 이상의 형식을 제공 ✔️ 합니다.

 이렇게 하면 인터페이스 디자인의 유효성을 검사 하는 데 도움이 됩니다. 예를 들어 <xref:System.Collections.Generic.List%601> 는 인터페이스의 구현입니다 <xref:System.Collections.Generic.IList%601> .

 ✔️는 정의 하는 각 인터페이스를 사용 하는 하나 이상의 API를 제공 합니다 (인터페이스를 매개 변수로 사용 하는 메서드 또는 인터페이스로 형식화 된 속성).

 이렇게 하면 인터페이스 디자인의 유효성을 검사 하는 데 도움이 됩니다. 예를 들어는 <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> 인터페이스를 사용 <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> 합니다.

 ❌이전에 제공 된 인터페이스에 멤버를 추가 하지 않습니다.

 이렇게 하면 인터페이스의 구현이 중단 됩니다. 버전 관리 문제를 방지 하기 위해 새 인터페이스를 만들어야 합니다.

 이러한 지침에 설명 된 상황을 제외 하 고 일반적으로 관리 코드 재사용 가능 라이브러리 디자인에서 인터페이스 대신 클래스를 선택 해야 합니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [형식 디자인 지침](type.md)
- [프레임 워크 디자인 지침](index.md)
