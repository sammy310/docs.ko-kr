---
title: 명명 규칙
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: 20531e379ddf9b93a278795e9b3c0eb91b47e077
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398346"
---
# <a name="visual-basic-naming-conventions"></a>Visual Basic 명명 규칙
Visual Basic 응용 프로그램에서 요소의 이름을 지정할 때 해당 이름의 첫 문자는 영문자 또는 밑줄 이어야 합니다. 그러나 밑줄로 시작 하는 이름은 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS)와 호환 되지 않습니다.  
  
 다음 제안 사항이 이름 지정에 적용 됩니다.  
  
- 및에서와 같이 이름에 대문자를 사용 하 여 각각의 개별 단어를 시작 `FindLastRecord` `RedrawMyForm` 합니다.  
  
- 또는 에서처럼 동사를 사용 하 여 함수 및 메서드 이름을 `InitNameArray` 시작 `CloseDialog` 합니다.  
  
- 또는에서와 같이 명사를 사용 하 여 클래스, 구조체, 모듈 및 속성 이름을 시작 `EmployeeName` `CarAccessory` 합니다.  
  
- 접두사 "I"를 사용 하 여 인터페이스 이름을 시작 하 고,과 같이 명사 또는 명사구를 입력 `IComponent` 하거나,와 같은 인터페이스의 동작을 설명 하는 형용사를 사용 하 여 인터페이스 이름을 시작 `IPersistable` 합니다. 약어는 혼동을 일으킬 수 있으므로 밑줄을 사용 하지 말고 약어를 사용 하는 경우에만 사용 합니다.  
  
- 이벤트 처리기 이름 앞에 ""와 같이 "" 접미사와 이벤트 유형을 설명 하는 명사를 사용 하 여 시작 `EventHandler` `MouseEventHandler` 합니다.  
  
- 이벤트 인수 클래스 이름에 "" 접미사를 포함 `EventArgs` 합니다.  
  
- 이벤트의 개념이 "before" 또는 "after" 인 경우 "" 또는 ""와 같이 현재 또는 과거 시제에 접미사를 사용 `ControlAdd` `ControlAdded` 합니다.  
  
- 길고 자주 사용 되는 용어의 경우 약어를 사용 하 여 이름 길이를 적절 하 게 유지 합니다 (예: "HTML(Hypertext Markup Language)" 대신 "HTML"). 일반적으로 32 자를 초과 하는 변수 이름은 낮은 해상도로 설정 된 모니터에서 읽기 어렵습니다. 또한 약어가 전체 응용 프로그램 전체에서 일관 되는지 확인 합니다. "HTML"과 "HTML(Hypertext Markup Language)" 간에 프로젝트를 임의로 전환 하면 혼동을 일으킬 수 있습니다.  
  
- 외부 범위의 이름과 동일한 내부 범위에서 이름을 사용 하지 마십시오. 잘못 된 변수에 액세스 하면 오류가 발생할 수 있습니다. 변수와 이름이 같은 키워드 사이에 충돌이 발생 하는 경우 적절 한 형식 라이브러리를 사용 하 여 키워드 앞에 키워드를 식별 해야 합니다. 예를 들어, 라는 변수를 사용 하는 경우 `Date` 를 호출 해야만 내장 함수를 사용할 수 있습니다 `Date` <xref:System.DateTime.Date%2A?displayProperty=nameWithType> .  
  
## <a name="see-also"></a>참고 항목

- [코드에서 요소 이름으로 사용되는 키워드](keywords-as-element-names-in-code.md)
- [Me, My, MyBase 및 MyClass](me-my-mybase-and-myclass.md)
- [Declared Element Names](../language-features/declared-elements/declared-element-names.md)
- [프로그램 구조 및 코드 규칙](program-structure-and-code-conventions.md)
- [Visual Basic 언어 참조](../../language-reference/index.md)
