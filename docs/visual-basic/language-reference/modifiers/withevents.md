---
title: WithEvents(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 50d5a768393e90d28d150b451405e35e6f4c7953
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583037"
---
# <a name="withevents-visual-basic"></a>WithEvents(Visual Basic)
하나 이상의 선언 된 멤버 변수가 이벤트를 발생 시킬 수 있는 클래스의 인스턴스를 참조 하도록 지정 합니다.

## <a name="remarks"></a>주의

@No__t_0를 사용 하 여 변수를 정의 하는 경우 메서드가 `Handles` 키워드를 사용 하 여 변수의 이벤트를 처리 하도록 선언적으로 지정할 수 있습니다.

클래스 또는 모듈 수준 에서만 `WithEvents`를 사용할 수 있습니다. 즉, `WithEvents` 변수의 선언 컨텍스트는 클래스 또는 모듈 이어야 하며 소스 파일, 네임 스페이스, 구조 또는 프로시저일 수 없습니다.

구조체 멤버에는 `WithEvents`를 사용할 수 없습니다.

@No__t_0를 사용 하 여 배열이 아닌 개별 변수만 선언할 수 있습니다.

## <a name="rules"></a>규칙

**요소 형식.** 클래스 인스턴스를 사용할 수 있도록 `WithEvents` 변수를 개체 변수로 선언 해야 합니다. 그러나 `Object`로 선언할 수 없습니다. 이벤트를 발생 시킬 수 있는 특정 클래스로 선언 해야 합니다.

이 컨텍스트에서는 `WithEvents` 한정자를 사용할 수 있습니다. [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)

## <a name="example"></a>예제

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a>참조

- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [C++ 키워드](../../../visual-basic/language-reference/keywords/index.md)
- [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
