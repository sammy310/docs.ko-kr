---
title: 추상 클래스 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 018dd353024e75e9819f5a97008f2f422ecad291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739060"
---
# <a name="abstract-class-design"></a>추상 클래스 디자인

추상 형식에서 public 또는 protected internal 생성자를 정의 하지 ❌.

 생성자는 사용자가 형식의 인스턴스를 만들어야 하는 경우에만 public 이어야 합니다. 추상 형식의 인스턴스를 만들 수 없기 때문에 public 생성자가 포함 된 추상 형식이 잘못 디자인 되 고 사용자의 잘못 된 형식이 됩니다.

 추상 클래스에서 protected 또는 internal 생성자를 정의 ✔️ 합니다.

 Protected 생성자는 보다 일반적 이며, 하위 형식이 만들어질 때 기본 클래스에서 자체 초기화를 수행할 수 있습니다.

 내부 생성자를 사용 하 여 추상 클래스의 구체적인 구현을 클래스를 정의 하는 어셈블리로 제한할 수 있습니다.

 제공 하는 각 추상 클래스에서 상속 되는 하나 이상의 구체적 형식을 제공 ✔️ 합니다.

 이렇게 하면 추상 클래스 디자인의 유효성을 검사 하는 데 도움이 됩니다. 예를 들어 <xref:System.IO.FileStream?displayProperty=nameWithType>은 <xref:System.IO.Stream?displayProperty=nameWithType> 추상 클래스의 구현입니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [형식 디자인 지침](../../../docs/standard/design-guidelines/type.md)
- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
