---
title: 형식 디자인 지침
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
ms.openlocfilehash: 17bd300277a039818a3d563c8f2d5f99eb2fc68d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289566"
---
# <a name="type-design-guidelines"></a>형식 디자인 지침
CLR 관점에서 두 가지 종류의 형식 (참조 형식 및 값 형식)만 있습니다. 하지만 프레임 워크 디자인에 대 한 논의의 목적을 위해 각각 고유한 특정 디자인 규칙을 가진 더 많은 논리 그룹으로 형식을 나눕니다.

 클래스는 참조 형식의 일반적인 경우입니다. 대부분의 프레임 워크에서 대부분의 형식을 구성 합니다. 클래스는 사용자가 지 원하는 다양 한 개체 지향 기능 집합 및 일반적인 적용 가능성을 미납 합니다. 기본 클래스와 추상 클래스는 확장성과 관련 된 특수 한 논리 그룹입니다.

 인터페이스는 참조 형식 및 값 형식 둘 다에서 구현 될 수 있는 형식입니다. 따라서 참조 형식 및 값 형식의 다형 계층 구조를 사용할 수 있습니다. 또한 인터페이스를 사용 하 여 CLR에서 기본적으로 지원 되지 않는 여러 상속을 시뮬레이션할 수 있습니다.

 구조체는 값 형식의 일반적인 사례 이며 언어 기본 형식과 유사 하 게 작은 단순 형식에 대해 예약 되어야 합니다.

 열거형은 요일, 콘솔 색 등의 짧은 값 집합을 정의 하는 데 사용 되는 값 형식의 특수 한 경우입니다.

 정적 클래스는 정적 멤버에 대 한 컨테이너로 사용 되는 형식입니다. 이러한 작업은 일반적으로 다른 작업에 바로 가기를 제공 하는 데 사용 됩니다.

 대리자, 예외, 특성, 배열 및 컬렉션은 모두 특정 용도에 적합 한 참조 형식의 모든 특수 한 사례 이며 디자인 및 사용에 대 한 지침은이 책의 다른 곳에 설명 되어 있습니다.

 ✔️ 각 형식이 관련 되지 않은 기능의 임의 컬렉션이 아니라 잘 정의 된 관련 멤버 집합 인지 확인 합니다.

## <a name="in-this-section"></a>섹션 내용
 [클래스와 구조체](choosing-between-class-and-struct.md) [추상 클래스](abstract-class.md) 를 선택 합니다. 추상 클래스 디자인 [정적 클래스](static-class.md) 디자인 [인터페이스](interface.md) 디자인 [구조체](struct.md) 디자인 [열거형](enum.md) 디자인 [중첩 형식](nested-types.md) *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임 워크 디자인 지침](index.md)
