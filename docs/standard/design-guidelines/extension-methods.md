---
title: 확장명 메서드
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: KrzysztofCwalina
ms.openlocfilehash: ad78bae2dc7a3000b67224da6f1a8c578053087f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347026"
---
# <a name="extension-methods"></a>확장명 메서드
확장 메서드는 인스턴스 메서드 호출 구문을 사용 하 여 정적 메서드를 호출할 수 있도록 하는 언어 기능입니다. 이러한 메서드는 메서드가 작동 하는 인스턴스를 나타내는 매개 변수를 하나 이상 사용 해야 합니다.  
  
 이러한 확장 메서드를 정의 하는 클래스를 "스폰서" 클래스 라고 하며 정적으로 선언 해야 합니다. 확장 메서드를 사용 하려면 스폰서 클래스를 정의 하는 네임 스페이스를 가져와야 합니다.  
  
 **X AVOID** frivolously 소유 하지 않은 형식에서 특히 확장 메서드를 정의 합니다.  
  
 형식의 소스 코드를 소유 하는 경우 대신 일반 인스턴스 메서드를 사용 하는 것이 좋습니다. 소유 하 고 있지 않은 경우에는 메서드를 추가 하는 것이 좋습니다. 확장 메서드를 자유롭게 사용 하면 이러한 메서드를 사용 하도록 설계 되지 않은 복잡 한 형식의 Api가 발생할 수 있습니다.  
  
 **✓ CONSIDER** 확장 메서드를 사용 하 여 다음과 같은 시나리오 중 하나:  
  
- 인터페이스의 모든 구현과 관련 된 도우미 기능을 제공 하려는 경우 핵심 인터페이스를 기준으로 기능을 작성할 수 있습니다. 구체적 구현은 인터페이스에 할당할 수 없기 때문입니다. 예를 들어 `LINQ to Objects` 연산자는 모든 <xref:System.Collections.Generic.IEnumerable%601> 형식에 대 한 확장 메서드로 구현 됩니다. 따라서 `IEnumerable<>` 구현은 자동으로 LINQ를 사용 하도록 설정 됩니다.  
  
- 인스턴스 메서드가 일부 형식에 대 한 종속성을 도입할 때 이러한 종속성은 종속성 관리 규칙을 중단 합니다. 예를 들어 <xref:System.String>에서 <xref:System.Uri?displayProperty=nameWithType>로의 종속성이 바람직하지 않을 수 `String.ToUri()` 있으므로 `System.Uri`를 반환 하는 인스턴스 메서드는 종속성 관리 관점에서 잘못 된 디자인입니다. `System.Uri` 반환 하 `Uri.ToUri(this string str)` 정적 확장 메서드는 훨씬 더 나은 디자인입니다.  
  
 **X AVOID** 에서 확장 메서드를 정의 <xref:System.Object?displayProperty=nameWithType>합니다.  
  
 Visual Basic 사용자는 확장 메서드 구문을 사용 하 여 개체 참조에서 이러한 메서드를 호출할 수 없습니다. Visual Basic에서 참조를 개체로 선언 하면 그에 대 한 모든 메서드 호출이 런타임에 바인딩되고 (라는 실제 멤버가 런타임에 결정 됨)에는 확장 메서드에 대 한 바인딩이 런타임에 결정 되기 때문에 Visual Basic는 이러한 메서드 호출을 지원 하지 않습니다. 컴파일 시간 (초기 바인딩)입니다.  
  
 이 지침은 동일한 바인딩 동작이 있는 다른 언어나 확장 메서드가 지원 되지 않는 경우에 적용 됩니다.  
  
 **X DO NOT** 종속성 관리 또는 인터페이스에 메서드 추가 하지 않은 확장된 유형으로 동일한 네임 스페이스에 확장 메서드를 배치 합니다.  
  
 **X AVOID** 다른 네임 스페이스에 상주 하는 경우에 동일한 서명으로 두 개 이상의 확장 메서드를 정의 합니다.  
  
 **✓ CONSIDER** 형식이 인터페이스 및 확장 메서드는 대부분 또는 모든 경우에 사용 하려는 경우 확장된 유형으로 동일한 네임 스페이스의 확장 메서드를 정의 합니다.  
  
 **X DO NOT** 다른 기능과 함께 일반적으로 관련 된 네임 스페이스에는 기능을 구현 하는 확장 메서드를 정의 합니다. 대신 자신이 속한 기능과 연결 된 네임 스페이스에서 정의 합니다.  
  
 **X AVOID** 확장 메서드 (예: "확장")에 네임 스페이스의 일반 이름을 지정 합니다. 대신 설명이 포함 된 이름 (예: "라우팅")을 사용 합니다.  
  
 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*  
  
 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>참조

- [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)
- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
