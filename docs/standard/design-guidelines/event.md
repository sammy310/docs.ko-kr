---
title: 이벤트 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
ms.openlocfilehash: 78d765a7af77b1e6a6ecd483677cea2d4c6b0d5b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709428"
---
# <a name="event-design"></a>이벤트 디자인
이벤트는 가장 일반적으로 사용 되는 콜백 형태입니다 (프레임 워크가 사용자 코드를 호출할 수 있도록 하는 구문). 다른 콜백 메커니즘에는 대리자, 가상 멤버 및 인터페이스 기반 플러그 인을 사용 하는 멤버가 포함 되어 있습니다. 유용성 연구의 데이터는 대부분의 개발자가 다른 콜백 메커니즘을 사용 하는 것 보다 많은 이벤트를 사용 하는 것이 더 편안 함을 의미 합니다. . 이벤트는 Visual Studio 및 많은 언어와 잘 통합 됩니다.  
  
 이벤트의 두 그룹에는 이벤트의 상태를 변경 하기 전에 발생 하는 이벤트, 사전 이벤트 라는 이벤트, 상태 변경 후 발생 한 이벤트 (사후 이벤트)가 있습니다. 이전 이벤트의 예는 폼을 닫기 전에 발생 하는 `Form.Closing`입니다. 사후 이벤트의 예는 폼이 닫힌 후에 발생 하는 `Form.Closed`됩니다.  
  
 **✓ DO** "발생" 이라는 용어를 사용 하 여 이벤트 보다는 "발생" 시키는"또는"트리거"입니다.  
  
 **✓ DO** 사용 <xref:System.EventHandler%601?displayProperty=nameWithType> 수동으로 이벤트 처리기로 사용할 새 대리자를 만드는 대신 합니다.  
  
 **✓ CONSIDER** 의 서브 클래스를 사용 하 여 <xref:System.EventArgs> 이벤트 인수로 제외 이벤트 데이터를 이벤트 처리 메서드를 필요가 없습니다 확실히 경우에서 사용할 수 있습니다는 `EventArgs` 직접 입력 합니다.  
  
 `EventArgs`를 사용 하 여 직접 API를 제공 하는 경우 호환성을 위반 하지 않고 이벤트와 함께 수행할 데이터를 추가할 수 없습니다. 서브 클래스를 사용 하는 경우 처음에는 완전히 비어 있더라도 필요할 때 하위 클래스에 속성을 추가할 수 있습니다.  
  
 **✓ DO** 보호 된 가상 메서드를 사용 하 여 각 이벤트를 발생 시킵니다. 이는 구조체, 봉인 클래스 또는 정적 이벤트가 아니라 봉인 되지 않은 클래스의 비정적 이벤트에만 적용 됩니다.  
  
 메서드의 목적은 파생 클래스에서 재정의를 사용 하 여 이벤트를 처리 하는 방법을 제공 하는 것입니다. 재정의는 파생 클래스에서 기본 클래스 이벤트를 처리 하는 보다 유연 하 고, 빠르고, 자연스럽는 방법입니다. 규칙에 따라 메서드 이름은 "On"으로 시작 하 고 이벤트 이름을 따라야 합니다.  
  
 파생 클래스는 재정의에서 메서드의 기본 구현을 호출 하지 않도록 선택할 수 있습니다. 기본 클래스가 제대로 작동 하는 데 필요한 메서드의 처리를 포함 하지 않고이를 준비 해야 합니다.  
  
 **✓ DO** 하나의 매개 변수는 이벤트를 발생 시키는 보호 된 메서드를 사용 합니다.  
  
 매개 변수 이름은 `e`로 지정 해야 하며 이벤트 인수 클래스로 입력 해야 합니다.  
  
 **X DO NOT** 비정적 이벤트를 발생 시킬 때 보낸 사람으로 null을 전달 합니다.  
  
 **✓ DO** 정적 이벤트를 발생 시킬 때 보낸 사람으로 null을 전달 합니다.  
  
 **X DO NOT** 이벤트를 발생 시키는 경우 이벤트 데이터 매개 변수와 null을 전달 합니다.  
  
 이벤트 처리 메서드에 데이터를 전달 하지 않으려는 경우 `EventArgs.Empty`를 전달 해야 합니다. 개발자는이 매개 변수가 null이 아닌 것으로 간주 합니다.  
  
 **✓ CONSIDER** 최종 사용자가 취소할 수 있는 이벤트를 발생 합니다. 이는 사전 이벤트에만 적용 됩니다.  
  
 최종 사용자가 이벤트를 취소할 수 있도록 하려면 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> 또는 해당 하위 클래스를 이벤트 인수로 사용 합니다.  
  
### <a name="custom-event-handler-design"></a>사용자 지정 이벤트 처리기 디자인  
 프레임 워크에서 제네릭을 지원 하지 않는 이전 버전의 CLR과 함께 작업 해야 하는 경우와 같이 `EventHandler<T>`를 사용할 수 없는 경우가 있습니다. 이러한 경우 사용자 지정 이벤트 처리기 대리자를 디자인 하 고 개발 해야 할 수 있습니다.  
  
 **✓ DO** 이벤트 처리기에 대 한 void의 반환 형식을 사용 합니다.  
  
 이벤트 처리기는 여러 개체에서 여러 이벤트 처리 메서드를 호출할 수 있습니다. 이벤트 처리 메서드가 값을 반환할 수 있는 경우 각 이벤트 호출에 대해 여러 개의 반환 값이 있을 수 있습니다.  
  
 **✓ DO** 사용 `object` 이벤트 처리기의 첫 번째 매개 변수 형식으로 버전을 호출 `sender`합니다.  
  
 **✓ DO** 사용 <xref:System.EventArgs?displayProperty=nameWithType> 또는 해당 하위 클래스의 이벤트 처리기의 두 번째 매개 변수 형식으로 버전을 호출 `e`합니다.  
  
 **X DO NOT** 이벤트 처리기에 두 개 이상의 매개 변수가 있어야 합니다.  
  
 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*  
  
 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>참조

- [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)
- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
