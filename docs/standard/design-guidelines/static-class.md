---
title: 정적 클래스 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 35bcf1d403c78cdfcbb476b2eb5de2251a564b9a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709064"
---
# <a name="static-class-design"></a>정적 클래스 디자인
정적 클래스는 정적 멤버만 포함 하는 클래스로 정의 됩니다. 예를 들어 <xref:System.Object?displayProperty=nameWithType>에서 상속 되는 인스턴스 멤버 외에도 전용 생성자가 될 수도 있습니다. 일부 언어에서는 정적 클래스에 대 한 기본 제공 지원을 제공 합니다. 2\.0 C# 이상에서 클래스가 정적으로 선언 되 면 sealed, abstract 이며 인스턴스 멤버를 재정의 하거나 선언할 수 없습니다.  
  
 정적 클래스는 순수 개체 지향 디자인과 단순성 간의 손상입니다. 이러한 메서드는 일반적으로 다른 작업 (예: <xref:System.IO.File?displayProperty=nameWithType>), 확장 메서드 소유자 또는 전체 개체 지향 래퍼 (<xref:System.Environment?displayProperty=nameWithType>)가 불필요 한 상승을 기능에 대 한 바로 가기를 제공 하는 데 사용 됩니다.  
  
 **✓ DO** 가급적 정적 클래스를 사용 합니다.  
  
 정적 클래스는 프레임 워크의 개체 지향 코어에 대 한 지원 클래스로만 사용 해야 합니다.  
  
 **X DO NOT** 정적 클래스를 기타 버킷으로 처리 합니다.  
  
 **X DO NOT** 선언 또는 정적 클래스에 인스턴스 멤버를 재정의 합니다.  
  
 **✓ DO** 봉인, 추상으로 정적 클래스를 선언 하 고 선택한 프로그래밍 언어에 정적 클래스에 대 한 기본 제공 지원 없는 경우 전용 인스턴스 생성자를 추가 합니다.  
  
 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*  
  
 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>참조

- [형식 디자인 지침](../../../docs/standard/design-guidelines/type.md)
- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
