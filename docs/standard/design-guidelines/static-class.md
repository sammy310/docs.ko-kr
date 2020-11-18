---
title: 정적 클래스 디자인
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: efa5ca6e7b5e7b7d03cbe1d55471a388f3faab37
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828662"
---
# <a name="static-class-design"></a>정적 클래스 디자인
정적 클래스는 정적 멤버만 포함 하는 클래스로 정의 됩니다 (물론에서 상속 되는 인스턴스 멤버 <xref:System.Object?displayProperty=nameWithType> 와 전용 생성자 일 수 있음). 일부 언어에서는 정적 클래스에 대 한 기본 제공 지원을 제공 합니다. C # 2.0 이상에서 클래스가 정적으로 선언 되 면 sealed, abstract 이며 인스턴스 멤버를 재정의 하거나 선언할 수 없습니다.

 정적 클래스는 순수 개체 지향 디자인과 단순성 간의 손상입니다. 이러한 메서드는 일반적으로 다른 작업 (예: <xref:System.IO.File?displayProperty=nameWithType> ), 확장 메서드 소유자 또는 전체 개체 지향 래퍼가 불필요 한 상승을 (예:)에 대 한 기능에 대 한 바로 가기를 제공 하는 데 사용 됩니다 <xref:System.Environment?displayProperty=nameWithType> .

 ✔️는 정적 클래스를 자주 사용 하지 않습니다.

 정적 클래스는 프레임 워크의 개체 지향 코어에 대 한 지원 클래스로만 사용 해야 합니다.

 ❌ 정적 클래스를 기타 버킷으로 처리 하지 마십시오.

 ❌ 정적 클래스의 인스턴스 멤버를 선언 하거나 재정의 하지 마세요.

 정적 클래스를 기본적으로 지원 하지 않는 경우 정적 클래스를 sealed, abstract로 선언 하 고 전용 인스턴스 생성자를 추가 ✔️ 합니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [형식 디자인 지침](type.md)
- [프레임 워크 디자인 지침](index.md)
